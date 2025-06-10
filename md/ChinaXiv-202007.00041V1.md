# BRAF mutation predicts survival after immunotherapy across multiple cancer types

# Author list:

Weiting $\mathsf { G e } ^ { 1 }$ ,Wen Cai1.2, Dehao Wu1, Wangxiong $\mathsf { H u } ^ { 1 }$ ,Weidong Han³, Shu Zheng\*1, Hanguang Hu\*1,4 Weitinge Ge,Wen Cai, and Dehao Wu contributed equally to this work.

1 Cancer Institute (Key Laboratory of Cancer Prevention and Intervention,   
China National Ministry of Education), the Second Affiliated Hospital, School   
of Medicine, Zhejiang University, Hangzhou, China   
2 Department of Gastroenterology, the Second Afiliated Hospital, School of   
Medicine, Zhejiang University, Hangzhou, China   
3 Department of Medical Oncology, Biomedical Research Center, Sir Run Run   
Shaw Hospital, School of Medicine, Zhejiang University, Hangzhou, China   
4 Department of Medical Oncology, the Second Afiliated Hospital, School of   
Medicine, Zhejiang University， Hangzhou, China

# Full address for correspondence:

Hanguang Hu; Department of Medical Oncology the Second Afiliated Hospital, School of Medicine, Zhejiang University, Hangzhou, China; E-mail: huhanguang@zju.edu.cn; Tel: 86-571- 87784718

Shu Zheng; Cancer Institute (Key Laboratory of Cancer Prevention and Intervention, China National Ministry of Education), the Second Affiliated Hospital, School of Medicine, Zhejiang University, 88 Jiefang Road, Hangzhou, China; E-mail: zhengshu@zju.edu.cn; Tel: 86-571-87783768

# Abstract:

Recently studies in selected tumors suggested that BRAF mutation may associates with survival benefit from immune checkpoint inhibitor (ICl) therapy1 3. To broadly investigate this association at a pan-cancer level, we analyzed two independent ICl treatment cohorts (MSKCC4: $n = 1 6 3 0$ , and Dana-Farber5: ${ \mathfrak { n } } =$ 249). BRAF-mutant patients exhibit better overall survival in the MSKCC cohort (Hazard ratio $[ \mathsf { H R } ] = 0 . 5 5$ ， $9 5 \%$ confidence interval [Cl]: 0.43-0.72; $P { < } . 0 0 1$ )and the result is validated by the Dana-Farber cohort ( $\mathrm { ' H R } = 0 . 6 8$ ， $9 5 \%$ Cl: 0.46-0.99; $P = . 0 4 5 )$ . A multivariate analysis adjusting tumor mutational burden, mismatch repair status,cancer type,age and sex confirmed the results (adjusted ${ \mathsf { H R } } =$ 0.58, $9 5 \%$ （ $\mathsf { C l } = 0 . 4 3 – 0 . 7 8$ ：， $P < . 0 0 1$ ).Immunogenomic features analysis of TCGA dataset indicated that patients may respond to immunotherapy in various mechanisms. This finding substantially improve the therapeutic prospects for a sizeable fraction of patients who benefit from immunotherapy.

Immune-checkpoint inhibitor (ICl) therapy has revolutionized the treatment of advanced cancer. However, durable benefit is limited to a minority of patients. Previously studies have suggested that PD-L1 immunochemistry, deficient mismatch repair (dMMR), tumor mutational burden (TMB) may correlate with clinical response4.6. BRAF mutation associates with bad prognosis and chemotherapy resistance in most of cancers,which new therapy choices were urgently needed.Recently,a phase Ill trial reported that BRAF-mutant melanoma patients who received first-line ICl treatment showed better overall survivals than wild type patients³. Also, BRAF-mutant glioblastoma and non-small cell lung cancer patients reported potential benefits from ICl treatment in retrospective studies1.2. However, it is unclear whether BRAF mutation associates with ICl treatment outcome across diverse human cancers. In this pan-cancer study,we identified that BRAF-mutant tumors associate with a better outcome after ICl treatment and present a small number of tumor neoantigens. Our study also indicates that patients with/without BRAF mutation may respond to immunotherapy in various mechanisms.

# Methods

All clinical and mutational data including TMB score were obtained from the cBioPortal database (https://www.cioportal.org) on May 25, 2020. The accession ID of two ICl treatment cohorts are TMB_MSKCC_20184 and

MIXED_ALLEN_20185. The immunogenomic data and MMR status were obtained from the published analyses of in the cohorts of TCGA PanCancer Atlas7 and MSKCC-IMPACT, respectively. All cases without BRAF mutation status or cancer type information were excluded.The Kaplan-Meier survival analysis with a two-sided log-rank test was employed to estimate BRAF mutation in relation to overall survival (OS). A multivariate Cox regression analysis was performed to determine the contribution of mutation to OS.A two-sided Mann-Whitney U test was used to examine the differences between groups. Statistical analysis was conducted with R v3.6.1. All analyses were conducted using deidentified public-use data.This study was deemed exempt from institutional review board approval and patient informed consent was waived.

# Results

After excluded 8518 cases without BRAF mutation status or cancer type information,we obtained 38142 patients across 30 cancer types in curated set of non-redundant studies from cBioPortal. Totally, 1292 patients with BRAF V600E, 858 patients with other BRAF mutations,and an overall mutation frequency of $5 . 6 \%$ were identified (Fig.1). The top three cancer types with the highest frequency of BRAF mutation are thyroid cancer $( 5 3 . 9 \% )$ ，melanoma $( 4 5 . 0 \% )$ and colorectal cancer $( 1 3 . 6 \% )$ L

We further employed the MSKCC ICl treatment cohort4 to investigate the association between BRAF mutation and OS.A Kaplan-Meier survival analysis was performed on 1630 patients with follow up data, including ten types of advanced cancer as previously described4. As showed in Fig2a, BRAF-mutant patients exhibit a significantly better OS than wild type (Hazard ratio $[ \mathsf { H R } ] = 0 . 5 5$ P $9 5 \%$ confidence interval [Cl]: 0.43-0.72; $P < . 0 0 1$ ). This result is validated by an independent ICl treatment cohort of Dana-Farber Cancer Institute including 249 patients with seven kinds of cancer ( $\prime H R = 0 . 6 8$ （204号 $9 5 \%$ Cl: 0.46-0.99; $P =$ .045; Fig2b). To adjust potential bias, we selected 1078 cases with sufficient data including BRAF mutation, TMB score, MMR status, cancer type,age and sex from the MSKCC cohort and perform a multivariate Cox regression analysis. After adjusting the above factors, the association between BRAF mutation and improved overall survival after ICl treatment is statistically significant (adjusted $\mathsf { H R } = 0 . 5 8$ ， $9 5 \% { \mathsf C } { \mathsf I } = 0 . 4 3 – 0 . 7 8$ $P < . 0 0 1 \$ ).The patient's clinical characteristics of two cohorts were showed in Supplementary Table 1 and 2.

We further employed TCGA immunogenomic data7 $( \mathsf { n } = 7 2 5 1$ to investigate the potential mechanism which could explain immunotherapy efficacy of BRAF-mutant patients.Although an increased number of tumor neoantigens has been linked to better response during immunotherapy5, patients without BRAF mutation exhibit a significantly higher number of neoantigens ( $\cdot P < 0 . 0 0 1$ ， Fig3a) rather than BRAF-mutant group. Then we compared intratumor heterogeneity (ITH) between groups. Previous studies stated that increased ITH associates with lower efficacy of immunotherapy in multiple cancer types7.As showed in Fig3b, BRAF-mutant patients exhibit a significantly lower ITH than the wild type patients $( P < . 0 0 1 )$ . We also compared six immune subtypes in order to systematically evaluate the immune landscape of cancer7. The results showed that the C3 (Inflammatory) subtype is enriched in BRAF-mutant group ( $5 5 . 4 \%$ versus $2 1 . 4 \%$ )，whereas the C4 (lymphocyte depleted) subtype is relatively higher in wild type group （ $1 3 . 3 \%$ versus $6 . 1 \%$ ,Fig3c).

# Discussion

Our study firstly reported that BRAF-mutant patients who received ICl treatment presented a better overall survival than wild type at a pan-cancer level. This finding will improve the situation that clinical response of ICl treatment is limited to a minority of unselected patients. Higher TMB score and dMMR,which have been identified as positive predictive markers4.9, define about $20 \%$ patients of MSKCC ICl treatment cohort. Our findings will include BRAF-mutant patients and substantially improve the therapeutic prospects for a sizeable fraction of patients $( 2 8 . 7 \% )$ .We still need to identify better biomarkers to define the likelihood of benefit from immunotherapy.

Higher TMB or dMMR patients occupy a higher number of tumor neoantigens presented on MHC molecules. ICl treatment promotes an antitumor immune response to recognize these neoantigens as foreign. Our study found that BRAF-mutant tumors present a small number of tumor neoantigens. However, these patients show a better clinical outcome after ICl treatment. This result suggests that mechanisms of immunotherapy response in BRAF-mutant tumors may not be entirely determined by tumor neoantigen presentation. Lower ITH is one of mechanisms to improve immunotherapy efficacy. Additionally, an immune landscape analysis shows that the C3 subtype,which is characterized by a balanced immune response7,occupies more than a half of BRAF-mutant tumors. In contrast, low lymphocyte infiltration subtype (C4) accounted for smal fraction in BRAF-mutant group, less than half of wild type group. Lower ITH and immune equilibrium that featured in our study partly explained good response of BRAF-mutant patients after ICl treatment.Therefore the relationship of BRAF and tumor immune microenvironment as previously reported10 deserves further analysis.

There are some limitations of our study. First, the findings of this study were mainly based on MSKCC and Dana-Farber ICl treatment cohorts,which didn't contain all kinds of cancer with frequently mutated BRAF (eg: thyroid cancer). Therefore, BRAF mutation still has great potential to identify more patients who response to immunotherapy in various cancer types. Second, our study made a bioinformatics analysis to investigated potential mechanisms of BRAF-mutant immunotherapy, which can inspire perspective studies and need to be validated in clinical trials.Also, the specific mechanisms of immunotherapy response of tumors with different driver

mutation or various microenvironment are not fully explained and worth to be further investigated.

# Reference

1. Zhao, J. et al. Immune and genomic correlates of response to anti-PD-1 immunotherapy in glioblastoma. Nat Med 25, 462-469 (2019).   
2. Arulananda, S.& Mitchell, P. BRAF Mutations-A Good News Story for Immune Checkpoint Inhibitors in Oncogene-Addicted NSCLC? J Thorac Oncol 13, 1055-1057 (2018).   
3.Wolchok, J.D. et al. Overall Survival with Combined Nivolumab and Ipilimumab in Advanced Melanoma. N Engl J Med 377, 1345-1356 (2017). 4. Samstein, R.M. et al. Tumor mutational load predicts survival after immunotherapy across multiple cancer types. Nature Genetics 51, 202-206 (2019).   
5. Miao, D.et al. Genomic correlates of response to immune checkpoint blockade in microsatellite-stable solid tumors.Nature Genetics 50, 1271-1281 (2018).   
6. Le DT et al. PD-1 Blockade in Tumors with Mismatch-Repair Deficiency. N Engl J Med 372, 2509-20 (2015).   
7. Thorsson, V. et al. The Immune Landscape of Cancer. Immunity 48, 812- 830.e14 (2018).   
8. Zehir, A. et al. Mutational landscape of metastatic cancer revealed from

prospective clinical sequencing of 10,0o0 patients. Nature Medicine 23, 703- 713 (2017).

9.Marabelle,A.et al. Efficacy of Pembrolizumab in Patients With Noncolorectal High Microsatellite Instability/Mismatch Repair-Deficient Cancer: Results From the Phase Il KEYNOTE-158 Study. J Clin Onco/38, 1- 10 (2020).

10.Liu, C.et al. BRAF inhibition increases tumor infiltration by T cells and enhances the antitumor activity of adoptive immunotherapy in mice. Clin Cancer Res 19, 393-403 (2013).

# Data availability

All clinical and mutational data is publicly available at   
https://www.cioportal.org_The accession ID of two ICl treatment cohorts are TMB_MSKCC_20181 and MIXED_ALLEN_2018².The immunogenomic data is publicly available in the published analyses of in the cohorts of TCGA PanCancer Atlas6. MMR status is publicly available in the published analyses of in the cohorts of MSKCC-IMPACT7.

# Code availability

The Kaplan-Meier survival analysis,multivariate Cox regression analysis, and Mann-Whitney U test were performed using R v3.6.1. All codes of this study are available from the corresponding author upon reasonable request.

# Competing interests

The authors declare no competing interests.

# Figure legend

Figure 1. Prevalence of BRAF mutation in 38142 patients across 30 cancer types. GIST: gastrointestinal stromal tumor; CNS: central nervous system. Figure 2. Kaplan-Meier survival analysis of BRAF mutation and overall survival after immunotherapy. Patients were obtained from MSKCC ICl treatment cohort and Dana-Farber ICl treatment cohort. ICl: immune checkpoint inhibitor; HR: hazard ratio; Mut: mutation; WT: wild type. Figure 3. Immunogenomic differences of patients with/without BRAF mutation. Patients were obtained from TCGA PanCancer Altas.

Thyroid Cancer (391/725) Melanoma (714/1586) Colorectal Cancer (344/2532) Skin Cancer (non-melanoma) (45/519) Cancer of Unknown Primary (13/207) Non-Small Cell Lung Cancer (202/3679) Endometrial Cancer (36/836) Bladder Cancer (48/1404) Ampullary Cancer (5/178) Pancreatic Cancer (32/1360) CNS Cancer (54/2476) Prostate Cancer (38/1937) Blood Cancer (83/4602) Sarcoma (15/966) Gastrointestinal Stromal Tumor (2/142) Small Cell Lung Cancer (4/280) Appendiceal Cancer (1/79) Liver Cancer (19/1483) Esophagogastric Cancer (21/1559) Cervical Cancer (3/247) Head and Neck Cancer BRAFV600E (11/925) Salivary Cancer □BRAF other mut (11/1019) Bone Cancer (3/376) Ovarian Cancer (6/774) BRAF Germ Cell Tumor V600E: (3/437) 1292 Breast Cancer (39/5597) Embryonal Tumor (1/190) Mesothelioma BRAF other mut: 858 (1/228) Kidney Cancer All patients:38142 (5/1676) Thymic Tumor (0/123) 0 10 20 30 40 50

Figure 2.

![](images/8b2878e6d4df72bf4444d8a1043d150b94d734d68ab02f4de1a07c35115d8278.jpg)

![](images/56d63a21f8afd5dde8f262db77bf22d917da2fad3c2bfddca08b05c9c3b4ac5b.jpg)  
Figure 3.

C

![](images/9e73e08d8e0a6da1c498f6caa9babcca1b4d5492a57dedb1c69a09b0616bd62d.jpg)

Supplementary Table 1.Patients' clinical characteristics in Mixed_Allen_2018 cohort   

<html><body><table><tr><td></td><td>Wild type (n=168)</td><td>BRAF mut (n=81)</td><td>P value</td></tr><tr><td>Age*, mean ±SD</td><td>61.8 ±13.0</td><td>56.1 ±17.0</td><td>0.023</td></tr><tr><td>Sex, n (%)</td><td></td><td></td><td>0.760</td></tr><tr><td>Fmale</td><td>63 (37.50)</td><td>32 (39.51)</td><td></td></tr><tr><td>Male</td><td>105 (62.50)</td><td>49 (60.49)</td><td></td></tr><tr><td>Cancer Type, n (%)</td><td></td><td></td><td><0.001</td></tr><tr><td>Melanoma</td><td>74 (44.05)</td><td>77 (95.06)</td><td></td></tr><tr><td>Non-Small Cell Lung Cancer</td><td>53 (31.55)</td><td>3 (3.70)</td><td></td></tr><tr><td>Bladder Cancer</td><td>26 (15.48)</td><td>1 (1.23)</td><td></td></tr><tr><td>Head and Neck Cancer</td><td>12 (7.14)</td><td>0 (0.00)</td><td></td></tr><tr><td>Anal Cancer</td><td>1 (0.60)</td><td>0 (0.00)</td><td></td></tr><tr><td>Small Cell Lung Cancer</td><td>1 (0.60)</td><td>0 (0.00)</td><td></td></tr><tr><td>Soft Tissue Sarcoma</td><td>1 (0.60)</td><td>0 (0.00)</td><td></td></tr><tr><td>Drug Type, n (%)</td><td></td><td></td><td><0.001</td></tr><tr><td>anti-CTLA-4</td><td>72 (42.86)</td><td>73 (90.12)</td><td></td></tr><tr><td>anti-PD-1/PD-L1</td><td>90 (53.57)</td><td>4 (4.94)</td><td></td></tr><tr><td>Combo</td><td>6 (3.57)</td><td>4 (4.94)</td><td></td></tr></table></body></html>

\*Data on age was missing for 66 patients of the wild type group,and 31 patients of the BRAF-mutant group. Statistical analyses were performed using the Statistical Package for the Social Science (SPSS), version 20. Difference in age was analyzed with t-test. Difference in sex was analyzed with Chi-square test. Difference in cancer type and drug type were analyzed with Fisher exact test.

Supplementary Table 2. Patients' clinical characteristics in TMB_MSKCC_2018 cohort   

<html><body><table><tr><td></td><td>Wild type (n=1461)</td><td>BRAF mut (n=169)</td><td>P value</td></tr><tr><td>Age,mean ±SD</td><td>61.6±13.4</td><td>60.5±15.3</td><td>0.319</td></tr><tr><td>Sex, n (%)</td><td></td><td></td><td>0.821</td></tr><tr><td>Fmale</td><td>549 (37.58)</td><td>62 (36.69)</td><td></td></tr><tr><td>Male</td><td>912 (62.42)</td><td>107 (63.31)</td><td></td></tr><tr><td>Cancer Type, n (%)</td><td></td><td></td><td><0.001</td></tr><tr><td>Melanoma</td><td>199 (13.62)</td><td>118 (69.82)</td><td></td></tr><tr><td>Non-Small Cell Lung Cancer</td><td>311 (21.29)</td><td>24 (14.20)</td><td></td></tr><tr><td>Colorectal Cancer</td><td>97 (6.64)</td><td>13 (7.69)</td><td></td></tr><tr><td>Bladder Cancer</td><td>206 (14.10)</td><td>6 (3.55)</td><td></td></tr><tr><td>Cancer of Unknown Primary</td><td>82 (5.61)</td><td>4 (2.37)</td><td></td></tr><tr><td>Head and Neck Cancer</td><td>136 (9.31)</td><td>2 (1.18)</td><td></td></tr><tr><td>Esophagogastric Cancer</td><td>122 (8.35)</td><td>1 (0.59)</td><td></td></tr><tr><td>Glioma</td><td>114 (7.80)</td><td>1 (0.59)</td><td></td></tr><tr><td>Renal Cell Carcinoma</td><td>150 (10.27)</td><td>0 (0.00)</td><td></td></tr><tr><td>Breast Cancer</td><td>43 (2.94)</td><td>0 (0.00)</td><td></td></tr><tr><td>Skin Cancer, Non-Melanoma</td><td>1 (0.07)</td><td>0 (0.00)</td><td></td></tr><tr><td>Drug Type, n (%)</td><td></td><td></td><td><0.001</td></tr><tr><td>anti-CTLA4</td><td>70 (4.79)</td><td>29 (17.16)</td><td></td></tr><tr><td>anti-PD-1/PD-L1</td><td>1193 (81.66)</td><td>85 (50.30)</td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>Combo</td><td>198 (13.55)</td><td>55 (32.54)</td><td></td></tr></table></body></html>

\*Statistical analyses were performed using the Statistical Package for the Social Science (SPSS), version 20. Difference in age was analyzed with t-test. Difference in sex and drug type were analyzed with Chi-square test. Difference in cancer type was analyzed with Fisher exact test