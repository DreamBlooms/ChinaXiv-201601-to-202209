# Remedial dosing recommendations for valproic acid in nonadherence patients with epilepsy

Chen-yu Wangl; Jun-jie Ding²; Zheng Jiao1,3\*; Er-qian $\mathrm { Y u } ^ { 1 , 4 }$ ; Guo-xing Zhu5

1 Department of Pharmacy,Huashan Hospital,Fudan University,Shanghai, China

2 Department of Pharmacy,Children's Hospital,Fudan University, Shanghai, China

3 Department of Pharmacy,Shanghai Chest Hospital, Shanghai Jiaotong University,Shanghai, China

4 Department of Pharmacy,The First Afiliated Hospital of Wenzhou Medical University,Wenzhou, Zhejiang,

China

5 Department of Neurology,Huashan Hospital,Fudan University, Shanghai, China.

C.Y.W., J.J.D.and Z.J. conceived and designed the research; C.Y.W.and E.Q.Y.analysed the data with the contribution of G.X.Z. and J.J.D. C.Y.W.and Z.J. wrote the first draft of the manuscript; All authors edited and commented on the manuscript.

Key words: Epilepsy, Antiepileptic drugs, Adherence, Population pharmacokinetcs, Monte Carlo simulation

Summary   
Objective: This study investigated the effect of delayed or missed doses on the pharmacokinetics (PK) of valproic acid (VPA) in patients with epilepsy and   
established remedial dosing recommendations for nonadherence patients.   
Methods: The Monte Carlo simulations based on all previous population   
pharmacokinetic models for pediatric, adult and elder patients with epilepsy receiving valproic acid, which is the most commonly used first-line AED. The following thee remedial approaches were investigated for each delayed dose: A) A partial dose was administered immediately, and the regular dose was administered at the next   
scheduled time.B) The delayed dose was administered immediately, followed by a partial dose at the next scheduled time. C) The delayed and partial doses were coadministered immediately, the next scheduled dose was skipped, and the regular dosing was resumed at the subsequent scheduled time.   
Results: The most appropriate remedial regimen was that with the shortest deviation time from the therapeutic window. The effect of nonadherence on PK was dependent on the delay duration and daily dose,and the recommended remedial dose was related to the delay duration and concomitant antiepileptic drugs. Remedial dosing strategies A and B were almost equivalent, whereas C showed a larger PK deviation time. If one dose was missed, double doses were not recommended for the next scheduled time. Significance: Simulations provide quantitative insight into the remedial regimens for nonadherence patients and clinicians should select the optimal regimen based on the status of patients.

# 1.INTRODUCTION

Epilepsy is one of the most common and disabling neurological disorders and requires long-term and even life-long antiepileptic drug (AED) treatment1. Adherence to the regimen is an important issue in the control of seizures2;3. Delayed or missed doses often occur in the treatment of patients with epilepsy4. It has been reported that approximately $30 \% { - } 5 0 \%$ of patients with epilepsy are non-adherent to their   
prescribed AED therapies and more than $70 \%$ of respondents reported AED dose omisions5-7. This nonadherence can lead to sub-therapeutic drug concentrations and increase the risk of seizures5. Inappropriate over-remedial doses may lead to clinical toxicity, with effects including change or loss of consciousness and fainting $^ 8 ( 8 )$ Valproic acid (VPA) is a broad spectrum AED used in the treatment of both generalized and focal seizures 9-1.It is also used incombination with otherAEDs in patients with multiple seizure types. As required by the US Food and Drug   
Administration (FDA), the package insert of VPA recommends that “If a dose is missed,it should be taken as soon as possible, unless it is almost time for the next dose. If a dose is skipped, the patient should not double the next dose"8(8). However, no clear remedial dose regimen is provided for the missed dose. Moreover, no comprehensive evaluation of the effect of nonadherence and the corresponding remedial dosing regimens has been performed.   
Monte Carlo simulation based on population pharmacokinetic (PPK) models provides the most appropriate means to investigate the effect of delayed or missed doses12-14.Tis methodis widelyaceptedforthedevelopmentoftreatmentprotocos, avoiding unnecessary clinical studies. Prospective studies in patients whose medications are intentionally delayed or interrupted for experimental purposes may not be acceptable for ethical reasons15.In addition, retrospective data is difficult to collect, accurately.   
To date, the perturbative effect of delayed or missed doses,along with   
subsequent remedial of the missed dose(s), on the VPA has not been examined. This study aims to investigate the effects of delayed or missed doses on pharmacokinetics of VPA and to provide practical recommendations for patients by Monte Carlo simulation.

# 2.MATERIALSANDMETHODS

# 2.1 Typical patients and dose regimens

Typical patients and the investigated corresponding dose regimen were based on the following criteria: (1） the weight of paediatric patients was based on the World Health Organization （WHO) Child Growth Standards,and the weight of adult and elderly patients was fixed at $7 0 ~ \mathrm { k g }$ ；(2）all patients were assumed to receive VPA monotherapy; (3） the dose regimen was selected according to the FDA's label and treatment guidelines published by international league against epilepsy (ILAE),which includes formulation, dose strength and dosing interval.

# 2.2 PPK characteristics for simulations

The PPK characteristics for the simulations and further investigations were   
extracted from previous studies.A systematic review of PPK studies published before   
31 Dec.2O18 was conducted with PubMed and Web of Science. The relevant   
identification, screening and assessment steps followed the Preferred Reporting Items   
for Systematic Reviews and Meta-Analyses (PRISMA) statement. Published studies were included if they(1） evaluated patients with epilepsy   
receiving valproate and (2) had complete PPK parameters. The studies were excluded   
if they (1) didn't include syrup or tablet forms and (2) were studies with overlapping   
data or cohorts. Only the most recent or the one with the largest sample size was   
included. The reference lists of all selected articles were also evaluated (Table S1). The following PPK parameters were collected from each identified study:   
apparent clearance (CL/F),apparent volume of distribution (V/F),absorption rate (Ka)   
and corresponding between subject variabilityand residual variability. The

lemographic characteristics of the study cohorts were also extracted.

# 2.3 Simulation

Monte Carlo simulations with nested random effects were conducted using the $\$ 5$ SIMULATION block in the NONMEM software(Version 7.4; Icon Incorporation, PA， USA） with theONLYSIMULATIONandSUBPROBLEMSoption. Post-processing of output was performed by the R package (version 3.4.0, www.r-project.com). Each simulation included 1OOO virtual subjects. These patients with full adherence were assumed to have expected seizure control with undesired adverse drug reactions for each investigated scenario. Concentration-time profiles of VPA were generated using the PPK parameters extracted from the identified studies for each scenario.

The therapeutic range of VPA for each scenario was defined as the 5th-95th percentile of the simulated data and was employed in the further analysis, according to guidelines for therapeutic drug monitoring of AEDs16; 17. The effect of nonadherence was estimated as the percentage of subjects outside their individual therapeutic ranges at a specified time. For each scenario and remedial regimen, deviation time,which is defined as the time outside the individual therapeutic range, was estimated. The regimen that has the lowest deviation time is the most appropriate remedial regimen. If the difference in deviation time was less than $0 . 5 \mathrm { h }$ among competitive regimens, those regimens could be considered equivalent.

# 2.4 Sensitivity analysis

When monotherapy is unsuccessful, combination therapy is usually tried in an attempt to improve efficacy, tolerability or both. Combination therapy was used in $79 \%$ of adults and $7 5 \%$ of children. 18 In multiple treatments, the combined drugs may be inducers of valproic acid (such as carbamazepine) or inhibitors (such as topiramate)19; 20.These willaect the Ke value of valproic acid. Moreover, the Ka values in the previous PPK models of VPA were fixed, and the between subject variability was set to zero,which may not represent the real clinical setting. Therefore， it is very helpful to investigate the effect of Ka and the combination with other AEDs on the dosage recommendation in the event of nonadherence. The scenarios in which patients with different Ka values and in which VPA was combined with other AEDs were chosen for the sensitivity analysis. Therefore, this “noise” was added to the simulation scenario as a sensitivity analysis to investigate its effect on the concentration-time profile of VPA (Table 1).

# 3.RESULTS

# 3.1 Typical patients and dose regimens

Seven typical dose regimens were employed to examine the effects of nonadherence on the pharmacokinetic profile and to calculate the remedial dose regimen: 1 regimen for infants aged $\ L < 1$ year (120 mg ql2h),3 regimens for children or adolescents aged 1-18 years (240 mg q12h, 500 mg q12h and 500 mg q24h), 2 regimens for adults aged 18-65 years ( $\mathrm { 5 0 0 m g \thinspace q 1 2 h }$ and 1000 mg q12h) and 1 regimen for elderly individuals aged $> 6 5$ years (750 mg q12h). Only syrup was investigated for paediatric patients taking less than $5 0 0 \mathrm { m g }$ per dose. These patients were assumed to have expected seizure control with undesired adverse drug reactions. The detailed dosing regimens are listed in Table 2. The delayed dose scenarios for each medication regimen were $1 { \sim } 1 2 \mathrm { h }$ of delay for the every $1 2 \mathrm { { h } }$ (ql2h) dosing regimen or $1 { \sim } 2 4 \mathrm { h }$ of delay for the every $2 4 \mathrm { h }$ (q24h) dosing regimen. Missed dose scenarios for each medication included one and two missed doses.

# 3.2 Simulated population pharmacokinetics (PPK) characteristics

Eleven PPK studies were selected to extract PPK characteristics of VPA15 9-28.

The screening process is presented in Figure S1. Five studies were conducted in paediatricpat;2idul;er, studies in both adult and elderly patients21: 27 and 1 study in children,adults and elderly patients25. Moreover, five studies were conducted in East Asia (China and Japan), 3 in Europe,2 in the US and 1 in Mexico. The detailed information for each study is summarized in Table S1.

For each scenario, two sets of PPK parameters with the highest and lowest elimination rate (Ke) values in the identified studies were employed for further investigation and are listed in Table 2. The Ke ranged from O.027 to $0 . 0 8 1 \mathrm { h } ^ { - 1 }$ for infant and paediatric patients and 0.029 to $0 . 0 7 4 \mathrm { { h } ^ { - 1 } }$ for adult and elderly patients.

# 3.3Effect of nonadherence

The Monte Carlo simulation results show that the percentage of subjects outside their individual therapeutic ranges for VPA is related to the delayed time, dosing interval and Ke (Figure 1). The risk of patients in the sub-therapeutic range increased with delay time. For example, for $7 0 \mathrm { - k g }$ adult patients administered the VPA $5 0 0 \mathrm { m g }$ every 12 hours (q12h) regimen in the highest Ke group $( 0 . 0 7 4 \mathrm { h } ^ { - 1 } ) ^ { 1 9 }$ , the percentage of subjects in the sub-therapeutic range was $12 \%$ and $22 \%$ when the dose was delayed for up to 4 and $8 \mathrm { h }$ ,respectively (Figure 1b). The patients who received higher doses of VPA had a higher risk of being outside the therapeutic range than the patients who received lower doses. For example, in 70-kg adult patients with highest Ke $( 0 . 0 7 4 \mathrm { h } ^ { - 1 } ) ^ { 1 9 }$ who were administered VPA, the percentages of subjects in the sub-therapeutic range were $4 2 . 6 \%$ ， $54 \%$ and $65 \%$ for a scheduled dosing delay up to $2 4 \mathrm { h }$ from the scheduled time for the $5 0 0 \mathrm { m g }$ $7 5 0 \mathrm { m g }$ and $1 0 0 0 \mathrm { m g }$ q12h regimens, respectively (Figure 1b). Moreover, patients with higher Ke have a lower risk of reaching the sub-therapeutic range than patients with lower Ke. For instance, the percentage of $7 0 \mathrm { - k g }$ adult patients taking $5 0 0 { \mathrm { ~ m g ~ q 1 2 h } }$ who were in the sub-therapeutic range $( 4 2 . 6 \%$ VS $91 \%$ ） was lower for the patients with the highest Ke of $0 . 0 7 4 \mathrm { h } ^ { - 1 }$ than for those with the lowest Ke of $0 . 0 2 9 { \mathrm { h } } ^ { - 1 }$

# 3.4 Remedial dosing regimen

The dosing recommendations for resuming treatment after delayed and missed doses are shown in Table 3.We have also developed a tool which can be used to check remedy dose regimens under different scenarios. (Appendix e-1). If one dose was delayed, one of three remedial strategies with the same total remedial dose could be used. Strategies A and B for remedial dosing were almost pharmacokinetically equivalent, while strategy C had a larger deviation time than the other two strategies regardless of the patients' age and dosing interval (Figure 2). For example, if a dose was delayed $8 \mathrm { { h } }$ a $7 0 \mathrm { - k g }$ adult patient administered VPA at $5 0 0 \mathrm { m g }$ on the q12h regimen could receive $2 5 0 \mathrm { m g }$ immediately and $5 0 0 \mathrm { m g }$ at the next scheduled dose (strategy A) or $5 0 0 \mathrm { m g }$ immediately and $2 5 0 \mathrm { m g }$ at the next scheduled dose (strategy B). The deviation times were $9 . 2 \mathrm { h }$ for strategy A and $8 . 7 \mathrm { h }$ for strategy B. If the patient was administered $7 5 0 \mathrm { m g }$ immediately until the next scheduled time (strategy C), the deviation time could be $1 2 . 4 \mathrm { h }$ . Strategy C was recommended only when the delayed dose was close to the next scheduled dose (e.g. $> 1 0 \mathrm { h }$ for the ql2h regimen or $> 2 0 \mathrm { h }$ for the q24h regimen).

With increases in delay time from the scheduled dosing time, the total resumed dose decreased to keep the least deviation time from the individual therapeutic range. For example, a $7 0 \mathrm { - k g }$ adult patient was administered with VPA at $5 0 0 \mathrm { m g }$ on the q12h regimen and achieved a satisfactory therapeutic outcome. If a dose was delayed $2 \mathrm { h }$ ， patients could be administered $5 0 0 \mathrm { m g }$ immediately and $5 0 0 \mathrm { m g }$ at the next scheduled dose, i.e., a total of $1 0 0 0 \mathrm { m g }$ would be administered. If a dose was delayed for $1 0 \mathrm { { h } }$

patients could be administered $2 5 0 \mathrm { m g }$ immediately and $5 0 0 \mathrm { m g }$ at the next scheduled dose (or $5 0 0 \mathrm { m g }$ immediately and $2 5 0 \mathrm { m g }$ at the next scheduled dose), i.e., a total of $7 5 0 \mathrm { m g }$ would be administered (Figure 3). The recommended remedial dose was also dependent on the Ke of the patient. With the same dose delay time, Patients with higher Ke need a higher remedial dose than those with lower Ke. For example, for a $7 0 \mathrm { - k g }$ adult patient administered VPA at $7 5 0 \mathrm { m g }$ on the $\mathrm { q } 1 2 \mathrm { h }$ regimen, when the delay was $^ { 4 \mathrm { h } }$ from the scheduled time,750 mg and $5 0 0 \mathrm { m g }$ were recommended for immediate administration to the highest Ke group $( 0 . 0 7 4 \mathrm { h } ^ { - 1 } ) ^ { 1 9 }$ and the lowest Ke group $( 0 . 0 4 3 \mathrm { h } ^ { - 1 } ) ^ { 2 8 }$ , respectively.

# 3.5 Sensitivity analysis

The scenario of remedial doses administered at the next scheduled time after missing one dose in VPA regimen of $5 0 0 \mathrm { m g } { \mathrm { q } } 1 2 \mathrm { h }$ was chosen for the sensitivity analysis. The results are presented in Figure S2. Body weight, absorption rate (Ka) and co-therapy with other AEDs had no significant effect on the dose recommendation when a dose was delayed or missed. The best recommended dose remained unchanged. Dosing intervals of 1O-14 and $_ { 1 4 - 1 0 \mathrm { h } }$ for ql2h regimens and 22-26 and 26-22 h for q24h regimens had no significant effect on the remedial recommendations.

# 4.DISCUSSION

For the first time,we systematically established remedial regimens for no   
adherent patients with AEDs by Monte Carlo simulation based on all previous PPK   
studies.The effects of delayed and missed doses on AED concentrations were   
previously studied using basic pharmacokinetic methods29-34. However, these studies 11 Corresponding author: Zheng Jiao (E-mail: zjiao $@$ fudan.edu.cn)

did not fully consider the effects of between subject variabilities and residual variabilities of pharmacokinetics in the patients. Moreover, the effects of covariates, such as body weight, dose, and performance were not investigated either. Monte Carlo simulation based on the PPK is much closer to the real clinical settngs,which are helpful features for individualized medication research on patients with nonadherence15.

In our study,we employed the therapeutic range instead of a fixed reference range to investigate the effct of delayed or missed doses34:35. Previous retrospective or observational studies suggest that the reference ranges for VPA are $5 0 { \mathrm { - } } 1 0 0 \ \mathrm { m g / L }$ 1 However, the reference range has been a controversial concept, because it was initially defined on the basis of limited data for individual AEDs,which may not adequately describe the concentration-response relationship in patients with epilepsy. Currently, the tendency in epilepsy treatment is changing from reference ranges to therapeutic ranges (or individual therapeutic concentrations)36. The latter can be defined as the concentration (or range of concentrations) that has been empirically found to produce the optimal response in the individual patient (i.e., complete seizure control without undesired effects or if that goal is not achievable,the best compromise between seizure suppression and concentration-related adverse effects37). Therefore, in our study, the therapeutic range was used instead of the reference range employed in the previous studies to assess the effect of missed or delayed doses and to make remedial dose recommendations.   
In addition. the deviation time was used to assess the optimal remedial dose in the

present study. The longer the deviation time, the more likely the patient will relapse with epilepsy or cause adverse drug reactions. It is a better index to describe the risks of patients being in the sub-therapeutic range than the trough and peak concentrations. So we used deviation time to assess the benefits of different remedial strategies in this study.

In this study, we first proposed three different treatment strategies for different clinical scenarios and conducted detailed investigations. Strategy A was more appropriate for patients who have low seizure frequency because the concentration gradually returned to the therapeutic range and these patients might have a higher risk of breakthrough seizures than other strategies.At the same time, strategy B allowed the VPA concentration to quickly return to the therapeutic range, which was more suitable for patients with epilepsy who have high seizure frequency. However, it may have caused more concentration-related adverse effects such as headache, dizziness, nausea, and emesis. Strategy C resulted in a greater fluctuation in VPA concentration than did the other two strategies and can be used only for patients who are unable to take the next planned dose as specified or with a delay time close to the next scheduled time. The clinician can choose the best remedial strategy based on the patient's condition. Our study also showed that the effect of delayed or missed dose on the time-concentration profile of VPA is determined by the duration of delay and Ke of the patients. With increases in delay time from the scheduled dosing time, the total resumed dose decreased15. Based on the definition of therapeutic range, higher Ke leads to lower individual therapeutic range. Moreover, the decrease of concentration in higher Ke group was gentler than that of the lower Ke group, because its lower

limit of individual therapeutic range is closer to O.All these indicated that, patients with higher clearance Ke need a higher remedial dose than those with lower Ke. The most common co-therapy medications used with VPA are phenobarbital, phenytoin, and carbamazepine, which have a significant effect on the Ke of VPA. The effect of co-therapies on the pharmacokinetic profile of VPA was investigated. Additionally, sensitivity analysis was performed on the patients who had a wide range of individual body weights and different levels of Ka, which may make the results more applicable in clinical practice. These perimeters had no significant effect on the dose recommendation when a dose was delayed or missed.   
Moreover, the recommended remedial approaches for delayed/missed doses could be extended to other AEDs,such as carbamazepine and lamotrigine.15: 38   
This study has several limitations. The dose recommendation in the current study was based on the $90 \%$ of the virtually simulated patients.Physicians should carefully consider the risk of toxicity after patients take a remedial dose in cases of   
nonadherence, especially in paediatric and elderly patients.At the same time, this study only investigated sustained-release tablets and oral dosage forms, because of the lack of relevant PPK research.

# 5. CONCLUSION

Although the current study cannot represent all clinical settings, the findings   
could be helpful for the actual management of epilepsy, especially in light of the   
substantial degree of nonadherence observed in these patients. Our study showed that   
the dosing recommendations for delayed or missed doses are time related and regimen   
dependent. Monte Carlo simulation based on PPK is a useful tool to investigate the 14 Corresponding author: Zheng Jiao (E-mail: zjiao $@$ fudan.edu.cn)

effect of nonadherence and provide rational dose recommendations for clinicians to sufficiently maintain the appropriate therapeutic range

We thank Dr. Xun-yi Wu from Department of Neurology,Huashan Hospital, Fudan University for helpful discussions on the typical patients and dose regimens.We thank Xin-yi Zheng Ph.D candidate for double checking the reference retrieval. We thank Wei-wei Lin and Jason H. Williams for detail about their published model. Part of this work was presented in The American Conference on Pharmacometrics 2O15 (ACoP6) on October 3 to 8, 2015 in Crystal City, Virginia.

# FUNDING

Dr Zheng Jiao received grants from National Natural Science Foundation of China (No. 81573505)，“Weak Discipline Construction Project” (No. 2016ZB0301-01） of Shanghai Municipal Commission of Health and Family Planning and Western Medicine Guidance Project of Shanghai Science and Technology Committee (No. 15411968000).

# REFERENCE

1. Patsalos PN, Spencer EP, Berry DJ. Therapeutic drug monitoring of antiepileptic drugs in epilepsy: a 2018 update. Ther Drug Monit 2018;40:526-548.   
2. Manjunath R, Davis KL, Candrill SD,et al. Association of antiepileptic drug nonadherence with risk of seizures in adults with epilepsy. Epilepsy Behav 2009;14:372-378.   
3.Stanaway L，Lambie DG， Johnson RH. Non-compliance with anticonvulsant therapy as a cause of seizures. N Z Med J1985;98:150-152.   
4. Faught E,Duh MS,Weiner JR,et al. Nonadherence to antiepileptic drugs and increased mortality: findingsfrom the RANSOM Study. Neurology 2008;71:1572-1578.   
5. Cramer JA, Glassman M, Rienzi V. The relationship between poor medication compliance and seizures. Epilepsy Behav 2002;3:338-342.   
6.Davis KL, Candrili SD,Edin HM. Prevalence and cost of nonadherence with antiepilepticdrugsinanadultmanagedcarepopulation. Epilepsia 2008;49:446-454.   
7. Rosenfeld WE, Bramley TJ, Meyer KL. Patient compliance with topiramate vs. other antiepileptic drugs: a claims database analysis. Epilepsia 2Oo4;45:238.   
8.Depakene (valproic acid) [package insert]. North Chicago, IIlinois; AbbVie Inc.   
9.Landmark CJ. Antiepileptic drugs in non-epilepsy disorders. CNS drugs 2008;22:27-47.   
10. Johannessen CU, Johannessen S1. Valproate: past, present, and future. CNS drug reviews 2003;9:199-216.   
11. Fisher RS. The new classification of seizures by the International League Against Epilepsy 2017. Current neurology and neuroscience reports 2017;17:48.   
12.Bonate PL. A brief introduction to Monte Carlo simulation. Clin Pharmacokinet 2001;40:15-22.   
13. Kroese DP, Taimre T, Botev ZI. Handbook of monte carlo methods. John Wiley & Sons; 2013.   
14. Kiang TK， Sherwin CM, Spigarelli MG, et al. Fundamentals of Population

Pharmacokinetic Modelling. Clin Pharmacokinet 2012;51:515-525.

15.Ding JJ, Zhang YJ, Jiao Z, et al. The effect of poor compliance on the pharmacokinetics of carbamazepine and its epoxide metabolite using Monte Carlo simulation. Acta Pharmacol Sin 2012;33:1431-1440.

16. Eadie MJ. Therapeutic drug monitoring--antiepileptic drugs. Br J Clin Pharmacol 2001;52 Suppl 1:11s-20s.   
17. Gram L, Flachs H, Wurtz-Jorgensen A, et al. Sodium valproate, serum level and clinical effect in epilepsy: a controlled study. Epilepsia 1979;20:303-311.   
18.Malerba A, Ciampa C, De Fazio S,et al. Patterns of prescription of antiepileptic drugs in patients with refractory epilepsy at tertiary referral centres in Italy. Epilepsy research 2010;91:273-282.   
19. Vucicevic K, Miljkovic B, Pokrajac M, et al. The influence of drug-drug interaction and patients’ characteristics on valproic acid's clearance in adults with epilepsy using nonlinear mixed effects modeling. European Journal of Pharmaceutical Sciences 2009;38:512-518.   
20. Serrano BB, Sanchez MG, Otero M, et al. Valproate population pharmacokinetics in children. J Clin Pharm Ther 1999;24:73-80.   
21. Blanco - Serrano B, Otero M, Santos - Buelga D, et al. Population estimation of valproic acid clearance in adult patients using routine clinical pharmacokinetic data. Biopharm Drug Dispos 1999;20:233-240.   
22.Birnbaum AK,Ahn JE,Brundage RC,et al. Population pharmacokinetics of valproic acid concentrations in elderly nursing home residents. Ther Drug Monit 2007;29:571-575.   
23. Jiang D-c, Wang L, Wang Y-q, et al. Population pharmacokinetics of valproate in Chinese children with epilepsy. Acta Pharmacol Sin 2007;28:1677.   
24. Correa T, Rodriguez I, Romano S. Population pharmacokinetics of valproate in Mexican children with epilepsy. Biopharm Drug Dispos 2008;29:511-520.   
25. Jiang D, Bai X, Zhang Q, et al. Effects of CYP2C19 and CYP2C9 genotypes on pharmacokinetic variability of valproic acid in Chinese epileptic patients: nonlinear mixed-effect modeling. Eur J Clin Pharmacol 2009;65:1187.   
26. Williams JH, Jayaraman B, Swoboda KJ, et al. Population pharmacokinetics of

valproic acid in pediatric patients with epilepsy: considerations for dosing spinal muscularatrophypatients. TheJournalofClinicalPharmacology 2012;52:1676-1688.

27. Ogusu N, Saruwatari J, Nakashima H, et al. Impact of the superoxide dismutase 2 Val6Ala polymorphism on the relationship between valproic acid exposure and elevation of $\gamma$ -glutamyltransferase in patients with epilepsy: a population pharmacokinetic-pharmacodynamic analysis. PloS one 2O14;9:e111066.

28. Lin W-w, Jiao Z, Wang C-l, et al. Population pharmacokinetics of valproic acid in adult Chinese epileptic patients and its application in an individualized dosage regimen. Ther Drug Monit 2015;37:76-83.   
29. Ahmad A， Garnett WR. Carbamazepine extended-release capsulesvs. oxcarbazepine: computer simulations of the effect of missed doses on drug plasma concentrations. Curr Med Res Opin 2005;21:1363-1368.   
30. Riss J, Cloyd J, Gates J, et al. Benzodiazepines in epilepsy: pharmacology and pharmacokinetics. Acta Neurol Scand 2008;118:69-86.   
31. Garnett WR,McLean AM, Zhang Y, et al. Simulation of the effect of patient nonadherence on plasma concentrations of carbamazepine from twice-daily extended-release capsules. Curr Med Res Opin 2003;19:519-525.   
32. Gidal BE, Majid O, Ferry J, et al. The practical impact of altered dosing on perampanel plasma concentrations: pharmacokinetic modeling from clinical studies. Epilepsy Behav 2014;35:6-12.   
33.Brittain ST,Wheless JW. Pharmacokinetic simulations of topiramate plasma concentrationsfollowingdosing irregularitieswith extended-releasevs. immediate-release formulations. Epilepsy Behav 2015;52:31-36.   
34.Ahmad AM,Douglas Boudinot F,Barr WH,et al. The use of Monte Carlo simulations to study the effect of poor compliance on the steady state concentrations of valproic acid following administration of enteric-coated and extended release divalproex sodium formulations. Biopharm Drug Dispos   
2005;26:417-425.   
35.Dutta S,Reed RC. Effect of delayed and/or missed enteric-coated divalproex

doses on valproic acid concentrations: simulation and dose replacement recommendations for the clinician. J Clin Pharm Ther 2O06;31:321-329.

36.Patsalos PN,Berry DJ,Bourgeois BF, et al. Antiepileptic drugs--best practice guidelines for therapeutic drug monitoring: a position paper by the subcommission on therapeutic drug monitoring, ILAE Commission on Therapeutic Strategies. Epilepsia 2008;49:1239-1276.

37. Perucca E. Is there a role for therapeutic drug monitoring of new anticonvulsants? Clin Pharmacokinet 2000;38:191-204.

38. Yu E-Q, Jiao Z, Wang C-Y, et al. Remedial dosing recommendations for delayed or missed doses of lamotrigine in pediatric patients with epilepsy using Monte Carlo simulations. Epilepsy & Behavior 2019;96:132-140.

# TABLEANDFIGURELEGENDS

# TABLE 1. Dosing schedule design

TABLE 2. Dosing recommendations for patients with delayed or missed valproic acid doses.

# TABLE 3. Sensitivity analysis

# FIGURE 1. Percentage of the subjects outside their individual therapeutic ranges after the last dose.

(A) Children administered 12O mg q12h ( $\mathrm { \langle 8 k g \rangle }$ ,240 mg q12h $( 1 6 \mathrm { k g } )$ and $5 0 0 { \mathrm { ~ m g ~ q 1 2 h } }$ $( 3 0 \mathrm { k g } )$ by the lowest and highest elimination rate (Ke). (B） Adults of $7 0 \mathrm { - k g }$ administered $5 0 0 ~ \mathrm { m g }$ q12h, $7 5 0 ~ \mathrm { m g }$ q12h and $1 0 0 0 ~ \mathrm { { m g } }$ ql2h by the lowest and the highest Ke.

# FIGURE 2. Three remedial strategies identified for $\mathbf { 7 0 - k g }$ adults administered 500 mg ql2h simulated by the lowest elimination rate (Ke) model (Lin et al).

(A) Full adherence.(B) Remedial dosing using strategies A,B (C),and C (D) when the dose was delayed by up to $1 0 \mathrm { { h } }$ . The dark pink shadow represents the distribution of the 5th-95th percentiles of the simulated concentrations in $90 \%$ of the virtual subjects and the light pink shadows represent the distribution of the simulated concentrations outside the 5th-95th percentiles in the remaining $10 \%$ virtual subjects. Red solid line represents median of the simulated concentrations and dotted lines represent O.5th and 99.5th percentiles of the simulated concentrations,respectively. Black dotted lines represent the individual therapeutic range $( 4 8 \mathrm { ~ - ~ } 1 5 1 ~ \mathrm { m g / L } )$ .Black solid line represents the deviation time.

FIGURE 3. Difference in the time that concentrations were outside the therapeutic range of VPA between patients with full adherence and patients with nonadherence.

Adults of $7 0 \mathrm { - k g }$ administered $5 0 0 ~ \mathrm { m g }$ ql2h/750 mg ql2h were simulated by the lowest elimination rate (Ke) group $( 0 . 0 4 3 \mathrm { h } \mathrm { - } 1 \dot { } \cdot$ ). And adults of $7 0 \mathrm { - k g }$ administered 500 mg $\mathrm { q 1 2 h / 7 5 0 ~ m g ~ q 1 2 h }$ .were simulated by the highest Ke model $( 0 . 0 7 4 ~ \mathrm { h } \mathrm { - } 1 \dot { } \$ ). The values in parentheses are the doses taken immediately and the dose taken at the next scheduled dose.

# SUPPORTINGINFORMATION

Additional supporting information may be found online in the Supporting Information section at the end of the article.

Figure S1: PRISMA flow diagram of study identifications.

Figure S2. Sensitivity analysis results

Table S1: The detailed information for population pharmacokinetics characteristics.

Appendix S1: A tool complied by Excel Macro for checking remedial dosing recommendations easily.

Table 1. Dosing schedule design for simulation   

<html><body><table><tr><td rowspan="2">Age</td><td rowspan="2">Body</td><td rowspan="2">Dose</td><td rowspan="2">Dose</td><td rowspan="2">Dosing interval</td><td colspan="2">Elimination rate (h-1)</td></tr><tr><td>Minimum</td><td>Maximum</td></tr><tr><td>Children</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>8 month</td><td>8kg</td><td> syrup</td><td>120</td><td>q12h (8:00, 20:00)</td><td>0.076</td><td>0.081</td></tr><tr><td>5 years</td><td>16 kg</td><td>syrup</td><td>240</td><td>q12h (8:00, 20:00)</td><td>0.062</td><td>0.080</td></tr><tr><td>6 years</td><td>20 kg</td><td>tablet</td><td>500</td><td>q24h (8:00)</td><td>0.027</td><td>0.066</td></tr><tr><td>10 years</td><td>30 kg</td><td>tablet</td><td>500</td><td>q12h (8:00,20:00)</td><td>0.028</td><td>0.074</td></tr><tr><td>Adults</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>30 years</td><td>70 kg</td><td>tablet</td><td>500</td><td>q12h (8:00, 20:00)</td><td>0.029</td><td>0.074</td></tr><tr><td>50 years</td><td>70 kg</td><td>tablet</td><td>1000</td><td>q12h (8:00, 20:00)</td><td>0.043</td><td>0.074</td></tr><tr><td>70 years</td><td>70 kg</td><td>tablet</td><td>750</td><td>q12h (8:00,20:00)</td><td>0.035</td><td>0.074</td></tr></table></body></html>

Table 2. Dosing recommendations for patients with delayed or missed valproic acid doses.   

<html><body><table><tr><td rowspan="2">Regimens</td><td rowspan="2">Scenarios</td><td colspan="3">Dosing recommendations</td></tr><tr><td>Dose (mg)</td><td>Percentage (%)a</td><td>Remedial strategy</td></tr><tr><td>Adults</td><td></td><td></td><td></td><td></td></tr><tr><td>500 mg q12h</td><td>Delayed 0-6 h</td><td>1000</td><td>200</td><td>A/B</td></tr><tr><td></td><td>Delayed 6-8 h</td><td>750 or 1000</td><td>150 or 200</td><td>A/B</td></tr><tr><td rowspan="7">q12h 750 mg</td><td>Delayed 8-12 h</td><td>750</td><td>150</td><td>A/B/C</td></tr><tr><td>Missed one dose</td><td>750</td><td>150</td><td>C</td></tr><tr><td>Missed two</td><td>1000</td><td>200</td><td>C</td></tr><tr><td>doses</td><td></td><td></td><td></td></tr><tr><td>Delayed O-3 h</td><td>1500</td><td>200</td><td>A/B</td></tr><tr><td>Delayed 3-5 h</td><td>1250 or 1500</td><td>166 or 200</td><td>A/B</td></tr><tr><td>Delayed 5-12 h</td><td>1250</td><td>166</td><td>A/B/C</td></tr><tr><td rowspan="8">1000 mg q12h</td><td>Missed one dose</td><td>1250</td><td>166</td><td>C</td></tr><tr><td>Missed two</td><td>1250 or 1500</td><td>166 or 200</td><td>C</td></tr><tr><td>doses Delayed 0-3 h</td><td>2000</td><td>200</td><td>A/B</td></tr><tr><td>Delayed 3-5 h</td><td>1750 or 2000</td><td>175 or 200</td><td>A/B</td></tr><tr><td>Delayed 5-12 h</td><td>1750</td><td>175</td><td>A/B/C</td></tr><tr><td>Missed one dose</td><td>1500</td><td>150</td><td>C</td></tr><tr><td>Missed two</td><td>1750</td><td>175</td><td>C</td></tr><tr><td>doses</td><td></td><td></td><td></td><td></td></tr></table></body></html>

Table 2. (continued)   

<html><body><table><tr><td rowspan="2">Regimens</td><td rowspan="2">Scenarios</td><td colspan="3">Dosing recommendations</td></tr><tr><td>Dose (mg)</td><td>Percentage (%)a</td><td>Remedial strategy</td></tr><tr><td>Children</td><td></td><td></td><td></td><td></td></tr><tr><td>120 mg</td><td>Delayed 0-3 h</td><td>240</td><td>200</td><td>A/B</td></tr><tr><td>q12h</td><td>Delayed 4-10 h</td><td>240 or 200</td><td>200 or 166</td><td>A/B</td></tr><tr><td rowspan="8">240 mg q12h</td><td>Delayed 10-12 h</td><td>200</td><td>166</td><td>A/B/C</td></tr><tr><td>Missed one dose</td><td>160</td><td>133</td><td>C</td></tr><tr><td>Missed two</td><td>200 or 160</td><td>166 or 133</td><td>C</td></tr><tr><td>doses</td><td>480</td><td></td><td></td></tr><tr><td>Delayed 0-3 h</td><td>400</td><td>200 166</td><td>A/B</td></tr><tr><td>Delayed 3-7 h</td><td>400 or 360</td><td>166 or 150</td><td>A/B</td></tr><tr><td>Delayed 7-12 h Missed one dose</td><td>360</td><td>150</td><td>A/B/C</td></tr><tr><td>Missed two</td><td>480</td><td>200</td><td>C C</td></tr><tr><td>500 mg</td><td>doses</td><td></td><td></td><td></td></tr><tr><td>q12h</td><td>Delayed 0-3 h</td><td>1000</td><td>200</td><td>A/B</td></tr><tr><td></td><td>Delayed 3-5 h</td><td>1000 or 750</td><td>200 or 150</td><td>A/B</td></tr><tr><td></td><td>Delayed 5-12 h</td><td>750</td><td>150</td><td>A/B/C</td></tr><tr><td rowspan="7">500mg q24h</td><td>Missed one dose</td><td>750</td><td>150</td><td>C</td></tr><tr><td>Missed two</td><td></td><td>200</td><td>C</td></tr><tr><td>doses</td><td>1000</td><td></td><td></td></tr><tr><td>Delayed 0-6 h</td><td>1000</td><td>200</td><td>A/B</td></tr><tr><td>Delayed 6-10 h</td><td>1000 or 750</td><td>200 or 150</td><td>A/B</td></tr><tr><td>Delayed 10-24 h</td><td>750</td><td>150</td><td>A/B/C</td></tr><tr><td>Missed one dose</td><td>750</td><td>150</td><td>C</td></tr></table></body></html>

A,a partial dose was administered immediately, followed by the delayed dose at the next scheduled time;   
B, the delayed dose was administered immediately, followed by a partial dose at the next scheduled time;   
C, the delayed dose and the partial dose were coadministered immediately until the second next scheduled time.   
a The VPA dose to be given remedially compared to the original LTG dose.

Table 3. Sensitivity analysis settings   

<html><body><table><tr><td>Parameter</td><td>Setting</td></tr><tr><td>Weight</td><td>Children: 2.5 - 50 kg</td></tr><tr><td></td><td>Adults: 50 - 100 kg</td></tr><tr><td>Combined medication</td><td>If there are covariates in the elimination rate (Ke)</td></tr><tr><td>absorption rate (Ka)</td><td>Children: 1.2 - 2.6 1/h</td></tr><tr><td></td><td>Adults: 0.67 - 1.9 1/h</td></tr><tr><td>Dosing interval</td><td>Taking a dose 1 hour after the scheduled dose</td></tr><tr><td></td><td>Taking a dose 1 hour before the scheduled dose</td></tr></table></body></html>

![](images/4eb1f5ee0f96e824073cc293b2234854fc1c9332f9cbc93a72f40937c28e5ba0.jpg)

dose regimen:

120 mg q12h  
240 mgq12h  
500 mgq12h

![](images/46beb5fecc81c1083fcb08e2fe5a8a95e63dc29f6c25d0e2fe5140cc77b70d62.jpg)

Dose regimen:

500 mg q12h  
750 mgq12h  
1000 mg q12h

![](images/a392205946fc4e18c29a28afe39493f7f684f8d4583e70ade3f3db65fde3815c.jpg)

![](images/71c6ff7c870043e33abf54fee781101da153d3872fa44594352bfb1ac434a9b4.jpg)

![](images/922c065d464461891fba4e84b1d31a9a5dcf677e961ef7a726f7c82b2f9890a6.jpg)

![](images/c639673e41ed433ff5e28fa3facf90f4feae1e80697b7453df9afd96ebc3aa4c.jpg)

Remedial strategies:

Reference Strategy A Strategy B $\bullet$ Strategy C

![](images/23ffa8890ebb7e6596e8a06f75eaf4a9367811a8fcd1b254d8964a085c54853c.jpg)