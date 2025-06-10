# AN UNFOCUSED SAR APPROACH TO IMPROVE AZIMUTH RESOLUTIONOF DUAL-FREQUENCY POLARIZED SCATTEROMETER(DFPSCAT)

Gang Wangl,² , Xiaolong Dong' ,Qingliu Baol,²,， Di Zhul, Xingou Xul

1. CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences,Beijing, 100190, China 2. University of Chinese Academy of Sciences, Beijing,10o049, China. Email: wangganggreat@163.com

# 1.ABSTRACT

For the spaceborne scanning pencil-beam scaterometer,the azimuth resolution is low that could not meet the demands.Based on the motion of platform and the scanning rules of the spaceborne scaterometer,this paper takes an unfocused SAR approach to improve the Azimuth Resolution.   
Index Terms— scatterometer,unfocused SAR,Doppler, azimuth resolution

# 2.INTRODUCTION

WCOM(WaterCycle ObservationMisson） proposesa X-Ku band dual-frequencypolarized SCATterometer(DFPSCAT） with relative high resolution and a $1 0 0 0 \mathrm { k m }$ swath for mapping of snow water equivalent and freeze-thaw processes [1].The retrieval of snow water equivalent is very complicated, especially on snow mountains the retrieval error is very high when the resolution is above $1 0 \mathrm { k m }$ ，so the resolution is required to be $2 { \sim } 5 \mathrm { k m }$ [2]. The spaceborne scanning pencil-beam scatterometer can provide high SNR, but shorter dwell time and it does have the advantage of covering a larger cover area than SAR.As with al scaterometers. DFPSCAT will use Pulse compression by linear frequency modulation along the elevation direction,which provides range resolution of about $5 0 \mathrm { m } ( \mathrm { B } { = } 5 \mathrm { M H z } )$ and $2 5 \mathrm { m } ( \mathrm { B } { = } 1 0 \mathrm { M H z } )$ ).Given that the requirement of resolution is $2 { \sim } 5 \mathrm { k m }$ ,the area could theoretically be resolved into as many as $2 0 0 0 { \div } 5 0 { = } 4 0$ or $5 0 0 0 \div 5 0 = 1 0 0$ separate elements,each constituting one independent samples,and corresponding to a normalized-measurement standard deviation of $1 / \sqrt { 4 0 }$ and 1/10 [3]. To achieve an improved resolution along the azimuth direction,the system will use an unfocused synthetic aperture technique where the Doppler effect is exploited to synthesize a longer aperture,as well as super-resolution reconstruction by oversampling in the direction of the azimuth.

# 3.SYSTEMPARAMETERS

In order to have both high accuracy measurement of backscatering coefficient and relative high resolution of the snow water equivalent measurement,the system parameters should be a compromise between the two variables for the system design of DFPSCAT.

The unfocused SAR method should not be used when the azimuth is less than 35 degree,which some other methods willbe used,such as resolution reconstruction. At the far swath,the footprint of azimuth corresponds to a Doppler bandwidth of approximately $2 0 \mathrm { { k H z } }$ ,while at near swath this corresponds to a Doppler bandwidth of about $1 0 \mathrm { k H z }$ ,and thus requires a minimum $2 0 \mathrm { { k H z } }$ PRF in order to unambiguously resolve the scene in azimuth[4]. To acquire high resolution in azimuth direction,the rotation rate should be designed small,and meanwhile satisfies the no gap coverage of the footprint. Some key specifications are shown in Table 1.

<html><body><table><tr><td>frequency</td><td>9.6, 14/17GHz</td></tr><tr><td>bandwidth</td><td>5MHz/10MHz</td></tr><tr><td>peak power</td><td>400W</td></tr><tr><td>polarization</td><td>HH, VV, HV/VH</td></tr><tr><td>antenna dimension</td><td>1.5m X 0.3m</td></tr><tr><td>raw resolution</td><td>50m(elevation) X 15km(azimuth)</td></tr><tr><td>resolution after processing</td><td>2~5km</td></tr></table></body></html>

Table 1 system parameters

# 4.BASICPRINCIPLE

According to the echo signal property of the target,the secondary phase item of Taylor series for the echo equation can be used to ensure coherent accumulation without correction.

When the secondary phase item is no more than ,the coherent accumulation time should satisfy:

$$
T _ { s } \le { \frac { 1 } { V _ { s a t } } } \sqrt { \lambda R _ { \scriptscriptstyle 0 } / ( 1 - \cos _ { \gamma } ^ { 2 } \sin _ { \varphi } ^ { 2 } ) }
$$

Where $\varphi$ is angle between satellite nadir point and antenna direction and $\gamma$ is azimuth. When the error of phase center is small enough that the targets do not have migration through resolution cell, thus

$$
T _ { s } < \frac { c } { 2 B V _ { s a t } \cos \gamma _ { \scriptscriptstyle 0 } \sin \varphi }
$$

A general goal in this method is to make sure the numbers of the beam sharpening ratio are stable, which we can have two methods:1)change PRF according to the azimuth but the numbers of accumulation pulse are stable; 2)change the numbers of accumulation pulse according to the azimuth,but the PRF is stable.

Considering the enginering realization, we usuallyuse the second method,which uses constant PRFand rotation rate,to change the numbers of the accumulation pulse according to the azimuth.The numbers of the accumulation pulse can be approximately equal to the numbers of the echoes from one beam width, while each target radial velocity relative to the radar is different,so each echo of the beam may have the frequency difference of arrval. A set of narrow-band filters，whose center frequencies correspond to the echo's,can accomplish the division of Doppler frequency.The specific choice of filter bandwidths is based in system parameters and resolution acquirements. The key factors that affect unfocused synthetic aperture method:

1)system parameters;

2) Doppler Centroid Estimation;

3)phase center;

4)constant sharpening ratio in different azimuth.

The quality of unfocused SAR approach is associated with the accuracy of Doppler centroid estimation, which can influence the target location and change the Doppler centroid frequency.DFPSCAT can not only measure the HH/VV and HV/VH,but also can measure the phase information, thus the center of phase is very important.

# 5. SIMULATION

According to the requirements of the beam sharpening ratio,we simulate the relationship between the beam sharpening ratio and azimuth in different PRF,see Figure 1.The beam sharpening ratio will get larger with he PRF arise,so the PRFshould be large enough.The choice of the coherent accumulation time is shown in Figure2 under condition that the coherent accumulation time is allowed when the band width is 5MHz.

![](images/afb1b2ce2f3dd523521c672d59592ba5a7f0b493229f6f51ed94b6b5e7b0f166.jpg)  
Figure 1.Sharpening ratio with the azimuth

![](images/324e8ef27e94b2bb147056906527145e412c4f048aa704f1bf4673bfc340c769.jpg)  
Figure 2.The limitation of the coherent accumulation time

As discussed at above, the antenna rotation rate of $4 ~ \mathrm { r p m }$ combined with PRF of $3 0 0 \mathrm { H z }$ ，produces approximate 4500 pulses during one circle.The numbers of coherent accumulation pulse are four,see Figure 3,with the requirements to satisfy $2 { \sim } 5 \mathrm { k m }$ resolution after processing.

![](images/d42eeece3cea32fc3b940df1f1ac7574b2151547c4729c86a83f3172a6d60fda.jpg)  
Figure 3.The numbers ofcoherent accumulation pulse

# 6.CONCLUSION

An unfocused SAR processing method is introduced in this paper，which can acquire azimuth resolution enhancement without using SAR technology.Through the simulation, it was demonstrated that this approach can be used on the engineering and improve the azimuth resolution.

# 7.REFERENCES

[1] Dong X, Liu H, Wang Z, et al. WCOM: The mission concept and payloads of a global water cycle observation mision[CJ. Geoscience and Remote Sensing Symposium (IGARSS),2014 IEEE International. IEEE, 2014:3338 - 3341. [2] Shi J. Snow Water Equivalence Retrieval Using X and Ku band Dual-Polarization Radar[C]. Geoscience and Remote Sensing Symposium, IGARSS, IEEE International Conference on. IEEE,2006:2183 - 2185. [3]M W Spencer, C Wu, D G Long, et al. Improved Resolution Backscater Measurements with the SeaWinds Pencil-Beam Scaterometer[J]. IEEE Transactions on Geoscience and Remote Sensing,20O0,38(1):89-104. [4]D G Long,C-Y Chi and F K Li. The Design of an Onboard Digital Doppler Processor for a Spaceborne Scatterometer [J]. IEEE Transactions on Geoscience and Remote Sensing,1988,26(6): 869-878.