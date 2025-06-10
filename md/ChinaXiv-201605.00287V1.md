# CALIBRATIONCOMPAIGNSOF THE HY-2A SATELLITE ALTIMETER SIGNIFICANTWAVEHEIGHTBYAGNSSBUOY

Xu Xi-yu@， Shen Hua@②， Xu Ke?

①(The CAS Key Laboratory of Microwave Remote Sensing, Center for Space Science and Applied Research, Chinese Academy of Sciences, Beijing,100190) ②(University of Chinese Academy of Sciences, Beijing,100039) xuxiyu@mirslab.cn

# ABSTRACT

GNSS buoys are innovative ocean instruments,and can provide calibrations of the sea surface height and significant wave height (SWH) products of satellite altimeters.This paper investigated the principles of the wave retrieval by GNSS buoys，and proposed a method of calibration of altimeter SWH product by GNSS buoys.The error sources inthe calibration procedure were analyzed. Ocean calibration campaigns were implemented to measure the SWH at the HY-2 altimeter nadir points,and acquired a SWH biasof $+ 7 . 9 2 { \pm } 5 . 0 4 \$ cm using four-parameters retracking algorithm. The SWH bias was $+ 2 0 . 3 7 { \pm } 1 2 . 7 9 ~ \mathrm { c m }$ （20 base on the HY-2 operational SWH products. The calibration campaigns showed that, GNSS buoys could serve forthe satellite altimeter SWH calibration under low sea state condition,and the four-parameters retracking algorithm outperformed the conventional three-parameters retracking algorithm in accuracy and consistency,at least for SWH retrieving.

Index Terms— Altimetry，calibration，GNSS buoy, significantwave height

# 1.INTRODUCTION

Significant wave height (SWH) is one of the major parameters in the satellite ocean altimetry products [1]. Calibration of the altimetric SWH is an important and complicated task, applying several complementary methods. Inter-comparison with the global wave buoy network or alternate satellite altimeters can provide abundant data, but the space and time de-correlations may cause errors; on the other hand, simultaneous field calibration campaigns under the satellite nadir may provide more accurate (in despite of sparse） SWH references.Recently，successful retrieval of the SWH from digital communications satellite signals was achieved in Harvest calibration platform.This may be a promising approach，but the reported accuracy was not adequate for SWH calibration at this stage [2].

Traditionally， thein-situ SWH wasmeasured by accelerator buoys such as Wave-rider buoys,but in the last decade GNSS buoys were implemented to measure SWH. GNSS(global navigation satellite system） buoysare innovative ocean instrumentswhich can measure the dynamic sea surface height (SSH) precisely,and are widely deployed in altimeter calibration campaigns.Meanwhile, it can provide measurements of SWH under proper sea state condition.

# 2.CALIBRATIONCAMPAIGNS

The SWH retrieving algorithm by GNSS buoys are based on the standard deviation of the (high-pass filtered) SSH time series (usually 1Hz), $\sigma _ { s h r }$ [3].The variation of the GNSS buoy SSH series is the combination of the instrument noise and the ocean wave displacements:

$$
S W H = 4 \bullet \sigma _ { _ { w a v e } } = 4 \bullet \sqrt { \sigma _ { _ { s h r } } ^ { 2 } - \sigma _ { _ { G N S S } } ^ { 2 } }
$$

where $\sigma _ { w a v e }$ is the standard deviation of the ocean wave, which is one quarter of the SWH,and $\sigma _ { G N S S }$ is the GNSS buoynoise level, which can be measured in extremely calm water surface.We split the calm water surface SSH series to two-minutesessions, andfollowed the“ShortPeriod Precision(SPP)” defined by the Vanuatu Jason-1 calibration team [4]:

$$
S P P ( n ) = \sqrt { \frac { 1 } { 1 1 9 } \sum _ { i = n } ^ { n + 1 1 9 } \left( h _ { i } - \overline { { h } } _ { n } \right) ^ { 2 } }
$$

where $\overline { { h } } _ { n }$ is the mean SSH value over a session. $\sigma _ { G N S S }$ is the mean SPPs of all valid sessions.

To calibrate the HY-2A satellite altimeter we developed a GNSS buoy.The buoy is an active system with a similar design to the MK-I buoy in the Bass Strait calibration field (the GNSS receiver and antenna are both sealed in the buoy capsule) and can record the SSH automatically for over 72 hours. The GNSS receiver and antenna were Trimble geodetic devices.

We have carried out several experiments and the results were roughly consistent. In June $2 0 1 3 \ \sigma _ { \mathrm { G N S S } }$ was calibrated in a large reservoir. We acquired a stable time series over seven hours and computed a noise level of $5 . 5 6 \mathrm { m m }$

# 3.SWHCALIBRATIONCAMPAIGNS

In late July and early August,2O13，we carried out two calibration campaigns of HY-2A satellite altimeter with the GNSS buoy under a crossover of the HY-2A satellite in Weihai, Shandong,China. Each campaign acquired a sea surface height(SSH) series of four hours under the satellite nadir,and the central one hour were used to retrieve the SWH. The situations of the campaigns were summarized in Table 1,and Fig. 1 showed a glance of the GNSS-buoy working. The SSH (range) and SWH products were both calibrated in the same experiments.

Table 1. The general situations of the two campaigns   

<html><body><table><tr><td>Date</td><td>UTC Time</td><td>Longitude</td><td>Latitude</td><td>HY-2A Cycle</td><td>Pass No.</td></tr><tr><td>2013- 07-30</td><td>22:28</td><td>122.823E</td><td>36.933N</td><td>48</td><td>#300</td></tr><tr><td>2013- 08-03</td><td>09:31</td><td>122.8147E</td><td>36.9285N</td><td>49</td><td>#9</td></tr></table></body></html>

![](images/092009c45591fb28a699c084702ae69345a162f7c32665f3e3590add31883650.jpg)  
Fig 1.A glance of the GNSS-buoy working

# 4.RESULTS

TheSWHof theHY-2A altimeterwere retrieved from the retracking of the waveform (See Fig. 2).Firstly, the $2 0 \mathrm { { H z } }$ waveform were retracked (accounting for the altimeter instrument features [5]) using a four-parameters Maximum Likelihood Estimation algorithm (MLE4,which including the attitude angle in the iterative estimator),and then the KuBand SWHs were averaged over a seven-seconds $( \sim 5 0 \mathrm { k m } )$ window centered at the satellite nadir.We also extracted the official SWH (the parameter “swh_ku” in HY-2A IGDR, which wasgenerated by the three-parametersMLE retracking) for a counterpart.

The GNSS buoy SWH was retrieved by the algorithm in Eq.(1).The GNSS buoy SSH series was the antenna height series minus the antenna height above the sea surface (which was measured beforehand).The GNSS buoy antenna position (latitude，longitude，height） was solved by the dynamic differencetechniqueusing GAMIT/TRACKsoftware developed by the Massachusetts Institute of Technology (MIT).There are two GNSS reference stations included in the solution: one is the station owned by the campaign team, the other is the Continuous Operation Reference Station (CORS) in Rongcheng,Shandong, China.The two solutions got consistent results (the correlation coefficients were greater than 0.95,and the SWH difference between two solutions was within1cm).

The results were tabulated by Table 2. The calibration campaigns acquired a SWH bias of $+ 7 . 9 { \pm } 5 . 0 \ \$ cm (for low sea state) usingMLE4 retrackingalgorithm,and a SWHbias of $+ 2 0 . 3 7 { \pm } 1 2 . 7 9 \ \mathrm { c m }$ base on the HY-2 operational (MLE3) SWH products.

![](images/6b32e65b661eb439ac0e7fb7a881627448c811173631d85a398242aa36795fc3.jpg)  
Fig.2.TypicalHY-2Aaltimeter $2 0 \mathrm { { H z } }$ waveforms during the calibration campaign.

Table 1. The results of the two campaigns   

<html><body><table><tr><td>Date</td><td colspan="2">2013-07-30</td><td colspan="2">2013-8-3</td></tr><tr><td>GNSSreference Station</td><td>CORS</td><td>OWN</td><td>CORS</td><td>OWN</td></tr><tr><td>GNSS Buoy SWH</td><td>0.666m</td><td>0.666 m</td><td>0.915 m</td><td>0.925 m</td></tr><tr><td>Averaged GNSS Buoy SWH</td><td colspan="2">0.666 m</td><td colspan="2">0.920 m</td></tr><tr><td>Difference between GNSS solutions</td><td colspan="2">0.000 m</td><td colspan="2">0.010 m</td></tr><tr><td>Correlation between GNSS solutions</td><td colspan="2">0.9633</td><td colspan="2">0.9608</td></tr><tr><td>Raw Altimeter SWH (MLE4)</td><td colspan="2">0.848 m</td><td colspan="2">1.035 m</td></tr><tr><td>Corrected Altimeter SWH (MLE4)</td><td colspan="2">0.781 m</td><td colspan="2">0.963 m</td></tr><tr><td>HY-2 SWH Bias (MLE4)</td><td colspan="2">+0.115 m</td><td colspan="2">+0.043 m</td></tr><tr><td>Operational Altimeter SWH (MLE3)</td><td colspan="2">0.9600 m</td><td colspan="2">1.033 m</td></tr><tr><td>HY-2 SWH Bias (MLE3)</td><td colspan="2">+0.294 m</td><td colspan="2">+0.113 m</td></tr></table></body></html>

# 5.CONCLUSION

To test the capability of the SWH retrieval algorithm from GNSS buoys,and to validate the calibration method based on the GNSS buoys,two field campaigns were carried out under a HY-2A satellite crossover on the China's Yellow Sea.

The calibration campaigns showed that, GNSS buoys could serve for the satellite altimeter SWH calibration under low to moderate sea state condition.

Furthermore， the four-parameters retracking algorithm (MLE4） outperformed the conventional three-parameters retracking algorithm (MLE3） in accuracy and consistency, comparing to the in-situ measurements,at least for SWH retrieving. In consideration of the limited experiment samples,the campaigns were only a demonstration of the calibration method,and the more accurate and reliable SWH bias results demands more experiments.

# 6.REFERENCES

[1]D.B.Chelton,J.C.Ries,B.J.Haines,L.L.Fu,and P.S. Callahan,“Satellitealtimetry".in Satellite Altimetry and Earth Sciences:A Handbook of Techniques and Applications,San Diego, CA, USA: Academic,pp. 1-168,2001   
[2]R.Shah,J.L.Garrison.“Estimation of significant wave height from digital communications satellite signals", IGARSS Proceedings,pp. 3899-3902, Jul. 2013   
[3] Bonnefond P,Exertier P,Laurain O,et,al.“Leveling sea surface using a GPS catamaran".Special issue on Jason-1 calibration/validation,Part1.MarineGeodesy,vol.26,no.3-4, pp.319-334,2003   
[4]Bouin M-N.,Ballu V,Calmant S,et,al.“A kinematic GPS methodology for sea surface mapping,Vanuatu".JGeodesy,vol. 83,pp.1203-1217,2009   
[5] Xu Xi-Yu, Xu Ke,Wang Zhen-Zhan,Liu He-Guang,Wang Lei. “Compensating the PTR and LPF featuresof the HY-2A satellite altimeter utilizing look-up tables”,IEEE J. Sel.Topics Appl. Earth Observ.Remote Sens.，vol.8,no.1,pp.149-159,Jan. 2015