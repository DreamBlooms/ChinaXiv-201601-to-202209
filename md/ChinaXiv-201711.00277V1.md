# Linear trend of resting-state fMRI time series

Xin-Di Wanga,b, Chao-Gan Yanc.d\*, Yu-Feng Zange f,\* äState Key Laboratory of Cognitive Neuroscience and Learning & IDG/McGovern Institute for Brain Research,Beijing Normal University,Beijing,lOo875,China

bCenter for Collaboration and Innovation in Brain and Learning Sciences, Beijing Normal University, Beijing,100875,China

The Nathan Kline Institute for Psychiatric Research,140 Old Orangeburg Road, Orangeburg, NY, 10962, USA

dDepartment of Child and Adolescent Psychiatry, New York University Langone Medical Center, New York,NY,10016,USA

eCenterfor Cognition and Brain Disorders,Hangzhou Normal University, Hangzhou, 31ll21,China

Zhejiang Key Laboratory for Research in Assessment of Cognitive Impairments, Hangzhou, 311121,

China

\*Corresponding:   
Chao-Gan Yan,The Nathan Kline Institute for Psychiatric Research,140 Old Orangeburg Road, Orangeburg, NY, USA.

Email: ycg.yan@ gmail.com

Yu-Feng Zang, Center for Cognition and Brain Disorders, Hangzhou Normal University, Hangzhou, 310015, China.

email: zangyf@ gmail.com

Abstract: Although linear trend removing has often been implemented as a routine preprocessing step in resting-state functional magnetic resonance imaging (RS-fMRI) data analysis, the spatial distribution of the magnitude of linear trend is still unclear. Further, it is interesting whether there will be any difference of the linear trend magnitude between different resting-states. For the first aim, we analyzed 5 RS-fMRI datasets from 5 different scanners (namely Beijing-Simens-3T, Cambridge-Siemens3T, CCBD-GE750-3T,Milwaukee-GE-3T,and Oulu-GE-1.5T). One-sample t-tests on the regression coefficient (i.e., the magnitude of linear trend) were performed for each datasets.For the second aim, we used 2 datasets in each of which different states were compared, one containing eyes-open resting-state (EO-RS) vs. eyes-closed resting-state (EC-RS) and the other containing two steady-state tasks, i.e., real-time finger force feedback (RT-FFF) and sham finger force feedback (S-FFF) tasks.Paired t-tests were performed between EO-RS and EC-RS,and between RT-FFF and S-FFF. One-sample t-tests showed that the spatial pattern of linear trend of RS-fMRI time series were quite different between different manufactures. The 3T SIEMENS scanners showed positive linear trend in almost al part of the brain,while GE scanners showed primarily negative linear trend in most part of the brain. Paired ttests showed some differences between paired conditions; differences between EO-RS and EC-RS were mainly in cuneus and eyeballs, and differences between RT-FFF and S-FFF were found in the thalamus,anterior cingulate gyrus, and right sensorimotor cortex. The current study indicated that, while the manufacturer-dependent linear

trend of RS-fMRI time series were mostly scanner-related noise, the linear trend may also be physiological noise (eyeballs) or even physiologically meaningful, especially during steady-state tasks.

Key words: resting-state fMRI; linear trend of time series; manufacturer-specificity; eyes-closed and eyes open; real-time feedback

# Introduction

Since the first study by Biswal and colleagues (Biswal et al.,1995), blood oxygen level dependent (BOLD) resting-state functional magnetic resonance imaging (RSfMRI) has been widely utilized to explore the spontaneous or intrinsic brain activity, as well as to investigate the pathological progress of brain disorders. There have been routine procedures for data preprocessing, e.g., slice timing, head motion correction, spatial normalization, spatial smoothing, linear trend removing,and temporal filtering. Amongst these procedures, linear trend removing is a well-accepted procedure (Bai et al., 2008; Zhang et al., 2008; Fox et al., 2009; Qiu et al., 2011). A common practice to remove linear trend is detrending (regression) with general linear model (Bandetini et al.,1993; Cox, 1996; Zhang et al., 2008; Fox et al., 2009) during preprocessing in RSfMRI. Although it has been speculated that the linear trend of fMRI signal was a system noise arising from scanner instability (Huettel et al., 2Oo4), few studies, however, have systematically investigated the spatial distribution of the linear trend of RS-fMRI signal in the brain. Further, no study has investigated whether, even a small

part of, the linear trend of RS-fMRI signal is different between different resting states.   
Such difference might be of physiological importance.

The first aim of the current study was to systematically investigate the spatial distribution of the linear trend of RS-fMRI signal across the brain on data from various research sites with different scanners. The second aim was to investigate the potential difference of the linear trend between resting-state with eyes closed (EC-RS) and resting-state with eyes open (EO-RS). We also compared the linear trend between two states of continuous performance, i.e., real-time finger force feedback (RT-FFF) and sham finger force feedback (S-FFF) (Dong et al., 2012).

# Materialsand methods

# Participants and imaging protocols

We implemented our analyses on six imaging datasets (See Table 1 for details): 1) "Beijing EO/EC" dataset with two resting-state conditions (EC-RS and EO-RS without fixation) counterbalanced across participants, 2) “Beijing Feedback” dataset with two conditions (RT-FFF and S-FFF,counterbalanced) (Dong et al., 2012) (also see below for experiment design), 3) “Cambridge” dataset, 4) “CCBD” dataset, 5) "Milwaukee” dataset,and 6)“Oulu” dataset. Datasets 1, 3, 5,6 were from the “1000 Functional Connectomes Project” and the “International Neuroimaging Data-sharing Initiative” (INDI) (http://fcon_1000.projects.nitrc.org). Dataset 2 was scanned at Beijing Normal University Imaging Center. Dataset 4 was acquired from the Center for Cognition and Brain Disorders (CCBD) at Hangzhou Normal University. The data acquisition of each dataset was approved by the corresponding institutional review board. All participants gave written informed consent before scanning.

# The experimental design of “Beijing Feedback" dataset

The data was from a study designed to investigate the brain mechanism of real-time feedback (Dong et al., 2O12). During fMRI scanning, the participants were asked to continuously maintain a pinch force at about $2 0 \mathrm { c m }$ $\mathrm { H } _ { 2 } \mathrm { O }$ . In the RT-FFF condition, the pinch force was shown to the participant in a real-time way on a monitor. But in the sham condition, a pinch force video of another participant was shown to the participant. These procedures were implemented by a multiple-channel MRIcompatible physiological monitor (model MP150, BIOPAC Systems, Inc., Goleta, CA). Detailed experimental procedure was described in the original paper (Dong et al., 2012).

# Data Preprocessing

Unless otherwise stated, all preprocessing was performed using the Data Processing Assistant for Resting-State fMRI (DPARSF) (Yan and Zang, 2010) (http://www.restfmri.net) which is based on Statistical Parametric Mapping (SPM8) (http://www.fil.ion.ucl.ac.uk/spm) and Resting-State fMRI Data Analysis Toolkit (REST) (Song et al., 2011) (http://www.restfmri.net). The first 10 image volumes were discarded for scanner calibration and for participants to get used to the

circumstance.Then slice acquisition dependent time shifts were corrected per volum The time series of images for each participant were realigned using a six-parameter (rigid body) linear transformation with a two-pass procedure (registered to the first image and then registered to the mean of the images after the first realignment). Spatial smoothing was performed using a $4 \mathrm { m m }$ Gaussian kernel. All volumes were then normalized with EPI template to obtain transformations from individual native space to MNI space.

# Linear trend estimation

Linear regression analysis was performed in a voxel-by-voxel way to calculate the regression coefficient (beta) of the time series against time at individual native space. The beta maps were then registered into MNI space with re-sampled $3 ~ \mathrm { m m } ^ { 3 }$ cubic voxels by using transformations acquired from spatial normalization procedure. Onesample t-tests were performed for each dataset on the beta maps. And paired t-tests were used to compare differences of beta between EO-RS and EC-RS as well as between RT-FFF and S-FFF for“Beijing EO/EC" dataset and “Beijing Feedback" dataset, respectively. All statistical t maps were corrected by Gaussian random field (GRF, voxel p $\cdot < 0 . 0 0 1$ ,cluster $\mathfrak { p } < 0 . 0 5 )$ ）within the whole bounding box (271633 voxels in all) in order to investigate the linear trend both inside and outside of the brain.

# Results

# The spatial distribution of the linear trend of fMRI signal

The linear trend maps were shown in figure 1. The pattern of linear trend of fMRI signal showed a manufacturer-specific spatial distribution: SIMENS scanners showed positive linear drift, and GE scanners showed negative linear drift in most parts of the brain. In addition, linear trend in the white matter is stronger than that in the gray matter for all datasets. Specifically, the Cambridge SIEMENS scanner showed apparently higher drift than Beijing SIEMENS scanner, partially due to its larger sample size. For the 3 GE scanners, the drift was apparently the highest for Oulu, the lowest for CCBD,and moderate for Milwaukee. Although the GE scanners showed primarily decreasing drift, the CCBD and Oulu scanners showed an increasing drift in the orbitofrontal midline area.

# Difference of linear trend between different states

In the EO-RS vs. EC-RS map, visual area (V1) showed a significantly smaller linear trend in the EO-RS state than EC-RS state, and eyeball showed a significantly larger linear trend in the EO-RS state than EC-RS state (Figure 2, Table 2). In the RTFFF vs. S-FFF map, the bilateral thalamus, bilateral anterior cingulate gyrus (BA 32), and the right sensorimotor cortex showed significantly smaller linear trend in the RTFFF state than S-FFF state (Figure 2, Table 2).

# Discussion and Conclusion

This study demonstrated a manufacturer-specific pattern of linear trend of RS-fMRI BOLD signal, suggesting a thermal noise over time. However, it is difficult to interpret the opposite direction of linear drift between SIEMENS and GE scanners. Our results would be helpful for the manufacturers to further analyze the linear drift and hence to improve the signal stability.

Although the above results strongly support that removing linear trend should be a routine procedure during preprocessing of RS-fMRI, the significant differences of linear trend between EO-RS and EC-RS as well as between RT-FFF and S-FFF indicated that the linear trend of RS-fMRI BOLD signal is not completely scanner noise. It would be informative to compare the linear trend between groups or between conditions before removing the linear trend.

# Acknowledgments

This work was supported by the National Natural Science Foundation of China (Grant Nos. 81020108022, 81271652, 31471084) and the National Institute of Mental Health (Grant No. 5R33MH086952). Dr. Zang is partly supported by “Qian Jiang Distinguished Professor” program.

# Conflict of interest

None.

References   
Bai, F., Zhang, Z., Yu, H., Shi, Y., Yuan, Y., Zhu, W., Zhang, X., Qian, Y., 2OO8. Default-mode network activity distinguishes amnestic type mild cognitive impairment from healthy aging: a combined structural and resting-state functional MRI study. Neuroscience Letters 438,111-115.   
Bandettini, P.A., Jesmanowicz, A., Wong, E.C.,Hyde, J.S.,1993. Processing strategies for time-course data sets in functional MRI of the human brain. Magn. Reson. Med. 3O,161-173.   
Bis wal,B., Yetkin,F., Haughton, V., Hyde,J.,1995.Functional connectivity in the motor cortex of resting human brain using echo-planar MRI. Magn. Reson. Med. 34, 537-541.   
Cox, R.W.,1996. AFNI: Software for analysis and visualization of functional magnetic resonance neuroimages. Comput. Biomed. Res. 29,162-173.   
Dong, Z.Y., Liu,D.Q., Wang, J., Qing, Z., Zang, Z.X., Yan, C.G., Zang, Y.F.,2012. Low-frequency fluctuation in continuous real-time feedback of finger force: a new paradigm for sustained attention. Neurosci. Bull. 28, 456-467.   
Fox,M.D., Zhang,D., Snyder,A.Z., Raichle,M.E.,2OO9.The global signal and observed anticorrelated resting state brain networks. J. Neurophysiol. 101, 3270-3283.   
Huettel, S.A., Song, A.W., McCarthy, G., 2O04. Functional magnetic resonance imaging, second ed. Sinauer Associates, Sunderland, pp. 258-259.   
Qiu, C.,Liao, W., Ding, J., Feng, Y., Zhu, C., Nie, X., Zhang, W., Chen, H., Gong, Q.,2011. Regional homogeneity changes in social anxiety disorder: a resting-state fMRI study. Neuroimaging 194, 47-53.   
Song, X.W., Dong, Z.Y., Long, X.Y., Li, S.F., Zuo, X.N., Zhu, C.Z., He, Y., Yan, C.G., Zang, Y.F., 2011. REST: a toolkit for resting-state functional magnetic resonance imaging data processing. PLoS ONE 6, e25031.   
Yan, C.G., Zang, Y.F.,2010. DPARSF: a MATLAB toolbox for “pipeline” data analysis of restingstate fMRI. Front. Syst. Neurosci. 4, 13.   
Zhang,D., Snyder, A.Z., Michael, M.D., Sansbury, M.W., Shimony, J.S., Raichle,M.E., 2008. Intrinsic functional relations between human cerebral cortex and thalamus.J.Neurophysiol.100, 1740-1748.

Table1.Detailed information ofdatasets.   

<html><body><table><tr><td rowspan="2">Dataset</td><td rowspan="2">N</td><td rowspan="2">Sex (M/F)</td><td rowspan="2">Handness</td><td rowspan="2">Age</td><td rowspan="2">EC-RS vs. EO-RS</td><td rowspan="2">Scanner</td><td rowspan="2">Magnet</td><td>TR</td><td>TE</td><td>Filp angle</td><td>Slice</td><td>Time</td></tr><tr><td></td><td>(ms) (ms)</td><td></td><td>number</td><td>points</td></tr><tr><td>Beijing EO/EC</td><td>42</td><td>21/21</td><td>42/0</td><td>22.3/1.6</td><td>Two counterbalanced</td><td>SIEMENS</td><td>3T</td><td>2000</td><td>30</td><td>90</td><td>33</td><td>240</td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td>sessions</td><td>TRIO</td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td></tr><tr><td></td><td></td></tr><tr><td>Beijing Feedback</td><td>38</td><td>19/19</td><td>38/0</td><td>22.3/1.6</td><td>Two counterbalanced</td><td>SIEMENS</td><td>3T</td><td>2000</td><td>30</td><td>90</td><td>33</td><td>240</td></tr><tr><td rowspan="2">Cambridge</td><td rowspan="2">198</td><td rowspan="2">75/123</td><td rowspan="2">171/27</td><td rowspan="2">21.0/2.3 Open</td><td>sessions</td><td>TRIO</td><td rowspan="2">3T</td><td rowspan="2">3000</td><td rowspan="2">30</td><td rowspan="2">85</td><td rowspan="2">47</td><td rowspan="2">119b</td></tr><tr><td></td><td>SIEMENS</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>TRIO</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CCBD</td><td>41</td><td>21/20</td><td>41/0</td><td>23.9/1.6</td><td>Close</td><td>GE 750</td><td>3T</td><td>2000</td><td>30</td><td>90</td><td>43</td><td>240</td></tr><tr><td>Milwaukee</td><td>45</td><td>15/30</td><td>＊</td><td>53.4/5.6</td><td>*</td><td>GE</td><td>3T</td><td>2000</td><td>*</td><td>＊</td><td>64</td><td>175°</td></tr><tr><td>Oulu</td><td>95°</td><td>31/64</td><td>86/9</td><td>21.6/0.6</td><td>Open, fixation</td><td>GE</td><td>1.5T</td><td>1800</td><td>*</td><td>*</td><td>28</td><td>245°</td></tr></table></body></html>

sessionorder,sexandage forcounterbalancing between EO-RSand EC-RSorbetweenRT-FFForS-FF,respectively.

c extra time points were removed in our study.

Therewere3partipantsin“Ouudataset,eigtpartipantsereremoedbecauseofbdspatialoralizatiooexcesiveadotio.

Table 2. Detailed information between different states in beta maps.   

<html><body><table><tr><td>States</td><td>Regions</td><td>BA</td><td>Cluster volume (mm2)</td><td>t-score of peak voxel</td><td>Coordinates of peak voxel</td></tr><tr><td>EO-RS vs. EC-RS</td><td>Right eye ball</td><td>N/A</td><td>4806</td><td>5.3036</td><td>42, 63,-39</td></tr><tr><td></td><td>Left eye ball</td><td>N/A</td><td>5076</td><td>5.6542</td><td>-36, 51, -51</td></tr><tr><td></td><td>Sub-Gyral</td><td>N/A</td><td>19737</td><td>-6.7337</td><td>27, 33, 15</td></tr><tr><td></td><td>Cuneus</td><td>19</td><td>810</td><td>-4.7407</td><td>3,-81,30</td></tr><tr><td></td><td>Sub-Gyral</td><td>N/A</td><td>1161</td><td>-4.6723</td><td>-27, -66,-9</td></tr><tr><td></td><td>Cuneus,</td><td>N/A</td><td>8910</td><td>-6.5379</td><td>30, -57, -3</td></tr><tr><td></td><td>Sub-Gyral</td><td>N/A</td><td>3969</td><td>-6.5393</td><td>48, -30,-12</td></tr><tr><td></td><td>Sub-Gyral</td><td>N/A</td><td>1593</td><td>-4.6042</td><td>33,-66, 21</td></tr><tr><td></td><td>Sub-Gyral</td><td>N/A</td><td>3159</td><td>-4.9170</td><td>-15, 12, 27</td></tr><tr><td>RT-FFF Vs. S-FFF</td><td>Thalamus, Extra-Nuclear</td><td>N/A</td><td>3645</td><td>-4.7279</td><td>6,-6,-3</td></tr><tr><td></td><td>Cingulate Gyrus</td><td>32</td><td>2457</td><td>-4.7617</td><td>-6, 15, 36</td></tr></table></body></html>

<html><body><table><tr><td>Extra-Nuclear</td><td>N/A</td><td>675</td><td>-4.6684</td><td>-30, 15,0</td></tr><tr><td>Extra-Nuclear</td><td>N/A</td><td>702</td><td>-4.5915</td><td>30, -36, 21</td></tr><tr><td>Extra-Nuclear</td><td>N/A</td><td>594</td><td>-4.4860</td><td>-24, -27, 18</td></tr><tr><td>Medial Frontal Gyrus,SMA</td><td>N/A</td><td>756</td><td>-4.7441</td><td>12, -3, 54</td></tr><tr><td>Inferior Parietal Lobule</td><td>N/A</td><td>1755</td><td>-4.5269</td><td>36, -39,54</td></tr><tr><td>Precentral Gyrus</td><td>N/A</td><td>621</td><td>-5.5698</td><td>33, -24, 57</td></tr></table></body></html>

# SIEMENS

Beijing EO/EC (EO) Beijing EO/EC （EC)

Beijing Feedback (RT-FFF)

![](images/f4eb66b9788308c454932f2f80bee99f327fbd425ee551c3737ffb0b59d1f7be.jpg)

Beijing Feedback (S-FFF)

Cambridge

# GE

![](images/d4f5017d04f9c5017cc0bb6e50e4d1344f01619104d670c7d5f8d42103ed6227.jpg)

Figure 1. Result of one-sample $t$ -tests $( p { < } 0 . 0 0 I$ ， cluster's $\scriptstyle p < 0 . 0 5$ ，GRF corrected) on the beta value acquired with SIEMENS (EC-RS, EO-RS， RT-FFF， S-FFF and Cambridge) and GE (CCBD, Milwaukee and Oulu) scanners. N is the number of subjects for each dataset.

# Different States

![](images/e02058ede5cbe75518ec8dab19485f7b5efc15c21b09f2754e9e583374ff5469.jpg)

Figure 2. Results of paired t-tests $( p { < } 0 . 0 0 I$ ，cluster's $p { > } 0 . 0 5$ ，GRF corrected) between EO-RS and EC-RS (upper row)， and between RT-FFF and S-FFF (lower row). N is the number of subjects.