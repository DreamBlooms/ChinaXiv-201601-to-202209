# THEORETICAL ANDEXPERIMENTAL ANALYSISOFSPATIAL DECORRELATIONOFDOPPLERSCATTEROMETER

Qingliu Baol² Xiaolong Dongl Di Zhul Xingou Xul

1. The CAS Key Laboratory of Microwave Remote Sensing,National Space Science Center, Chinese Academy of Science,Beijing 100190, China 2.University of Chinese Academy of Science, Beijing 10o049, China

# ABSTRACT

Ocean surface current is a very important parameter of ocean dynamic environment,which has been connected to global climate change,marine environment forecasting, marine navigation,engineering security and so on.Doppler scatterometer is a new type of scatterometer that can be used to measure ocean surface current as well as the ocean wind vector in space.The Doppler Scatterometer is based on a real aperture radar,which canachieveaverywide swath.It can provide the ocean surface current and wind vector information in a certain resolution and achieve global coverage quickly,which is very important for the marine environment forecasting and climate changes research.

IndexTerms—dopplerscatterometer, spatial decorrelation,correlation coefficient model

# 1.INTRODUCTION

The large-scale ocean circulation is fundamental to Earth's heat budget and climate variability.It is therefore a hot research topic in present driven to understand climate change more fully.Ocean surface currents are driven by wind stress and nonuniform buoyancy forcing caused by differences in atmospheric-ocean fluxes of heat and fresh water.Doppler scatterometer is a new type of scatterometer that can be used to measure ocean surface current as well as the ocean wind vector in space.The ocean current speed can beretrievedbytheinterferometricphase.Spatial decorrelation is one of the main factors of coherence model for spaceborne Doppler scatterometer.The accurate spatial decorrelation model is very important for PRF and pulse sequence design. Moreover， the spatial decorrelation determines the selection of echoes pairs,which are best for interference at different observation azimuth.The ocean current speed retrieval accuracy is related to the selection of echoes pairs directly.

Insection 2, thecorrelation model ofthe interferometricscatterometerisintroducedandthe theoretical calculation formulas of spatial decorrelation are given out. The airborne experiments principles and system parameters are described in section 3.In section 4,the correlation coefficient of the airborne experiments data are estimated and compared with the theoretical correlation coefficient.The conclusion is given in section 5.

# 2.SPATIALDECORRELATIONOFDOPPLER SCATTEROMETER

There are four decorrelation factors that should be considered in the correlation model, i.e.the thermal noise decorrelation,different observation regions decorrelation, spatial decorrelation,and temporal decorrelation.And the interferometric coherence can be expressed as the product of these factors[1,2]

$$
\gamma = \gamma _ { \mathrm { { t h e r m a l } } } \cdot \gamma _ { \mathrm { { f o o t p r i n t } } } \cdot \gamma _ { \mathrm { { s p a t i a l } } } \cdot \gamma _ { \mathrm { { t e m p o r a l } } }
$$

Thermal noise decorrelation is determined by the signal-noise-ratio (SNR).For spaceborne scatterometer the SNR is low,thus thermal noise decorrelation is dominated especially in low wind speed condition.For airborne scatterometer the thermal noise decorrelation is ignorable, because the SNR is larger than 2OdB in most cases. Different observation regions decorrelation and temporal decorrelation are related to the PRF.When the PRF is higher than $1 \mathrm { k H z }$ ,these two kinds of decorrelation are also ignorable.

Spatialdecorrelationisanotherdominating decorrelation factor.It is related with the length of baseline, observation azimuth and antenna size in azimuth.And the baseline of spatial decorrelation of Doppler scatterometer is different from that of Across-Track Interferometry (XTI) SAR,which is used to measure the terrain heights.The baseline of Doppler scatterometer is along-track,and the length of baseline can be expressed as $B = V _ { \mathrm { s a t } } T$ ,where $T$ is the time interval of the echo pairs that are used for interferometry.The spatial decorrelation is deduced as[1,2]

$$
\gamma _ { \mathrm { s p a t i a l } } = \frac { \displaystyle { \int _ { \varphi } } \exp \biggl ( - j \frac { 4 \pi } { \lambda } V _ { \mathrm { s a t } } T \sin \theta \cos \varphi \biggr ) \mathrm { s i n c } \biggl ( \frac { \varphi - \varphi _ { 0 } } { R _ { \varphi } } \biggr ) ^ { 2 } d \varphi } { \displaystyle { \int _ { \varphi } } \mathrm { s i n c } \biggl ( \frac { \varphi - \varphi _ { 0 } } { R _ { \varphi } } \biggr ) ^ { 2 } d \varphi }
$$

According to the Along-Track Interferometry，the variance of ocean current speed can be written as

$$
\sigma _ { { \scriptscriptstyle V } } = \frac { \lambda } { 4 \pi T } \sigma _ { \phi }
$$

From Eq.(2),We know that smaller time interval obtains greater correlation coefficient and smaller interferometric phase variance.But from Eq.(3)，we can see that ocean current speed variance $\sigma _ { { } _ { V } }$ is in inverse ratio to the time interval. Thus accurate spatial decorrelation is essential for the time interval selection.Fig.1 illustrates the best time interval for pulse interferometry at different observation azimuth,where $0 ^ { \circ }$ and $9 0 ^ { \circ }$ correspond to the along-track and cross-track direction respectively.

![](images/3bc8c1d6359d247100f908388f10f96aac302a77c75e4779a1bbd6b3856944f7.jpg)  
Fig.1 The best time interval for pulse interferometry （2 $( { \mathrm { P R F } } { = } 1 2 ~ { \mathrm { K H z } } )$ 1

# 3.AIRBORNESCATTEROMETEREXPERIMENTS PRINCIPLES

![](images/9a3becbc237525cae84086de1fbc1dfd9e9db4f382fa7c23a00f231fc7b8f6e4.jpg)  
Fig.3 The observation geometry of airborne experiment

TABLE 1 The main system parameters of airborne scatterometer   

<html><body><table><tr><td>No</td><td>Main system parameters</td><td>Airborne Scatterometer</td></tr><tr><td>1</td><td>Frequency</td><td>13.256 GHz</td></tr><tr><td>2</td><td>Polarization</td><td>HH,VV</td></tr><tr><td>3</td><td>ChirpBandwidth</td><td>2 MHz</td></tr><tr><td>4</td><td>Chirp Pulse Width</td><td>10us</td></tr><tr><td>5</td><td>PRF</td><td>1800 Hz</td></tr><tr><td>6</td><td>Beam Type</td><td>Fanbeam (Fixed)</td></tr><tr><td>7</td><td>Antenna size</td><td>~0.4m × 0.2 m× 0.2m</td></tr><tr><td>8</td><td>Beam Width</td><td>3.5°(azimuth) × 25° (elevation)</td></tr><tr><td>9</td><td>Antenna Gain</td><td>25dBi</td></tr><tr><td>10</td><td>Dynamic Range</td><td>>45 dB</td></tr><tr><td>11</td><td>TransmittedPower</td><td>10W</td></tr><tr><td>12</td><td>PlatformHeight</td><td>~3km</td></tr></table></body></html>

![](images/c4d16383a0786ce3cd1535373cde186396a596050d68e4f13acc9203d28bf0ce.jpg)  
Fig.2 The diagram of pulse sequence

The region of the airborne experiments is located at [122.055E，36.192N]，YellowSeaofChina.The observation geometry of the airborne experiment is shown in Fig.3.The height of the platform is about $3 0 0 0 \mathrm { m }$ and the platform speed is about $6 0 \mathrm { m / s }$ .The antenna is a set of dual polarization horns fed by slotted waveguide array.The observation incident angles are from $2 6 ^ { \circ }$ to $4 6 ^ { \circ }$ .The diagram of pulse sequence is shown in Fig.2 and the main system parameters are listed in TABLE1[3].

# 4.SPATIALDECORRELATIONCOMPARISON WITHEXPERIMENTDATA

The Maximum Likelihood Estimation (MLE）method is used to estimate the coherence magnitude of the airborne experiment data.Given $L$ signal measurements, the sample coherence $\delta$ can be written as[4]:

$$
\delta = { \frac { \sum _ { i = 1 } ^ { L } z _ { 1 i } z _ { 2 i } ^ { * } } { \sqrt { \sum _ { i = 1 } ^ { L } \left| z _ { 1 i } \right| ^ { 2 } } \sqrt { \sum _ { i = 1 } ^ { L } \left| z _ { 2 i } \right| ^ { 2 } } } }
$$

where $i$ is the sample number.The coherence magnitude estimate $d$ can be deduced as:

$$
d = \left| \delta \right|
$$

The sample coherence magnitude $d$ is biased towards higher values,especially when the coherence is low.The bias decreases with increasing number of independent samples $L$ as the MLE is asymptotically unbiased.

Theestimatedcorrelationcoefficientsof HH polarization and VV polarization of airborne experiment data are shown in Fig.4. The theoretical correlation coefficient of airborne scatterometer is illustrated in Fig.5, and they are calculated using Eq.(1) and system parameters.

![](images/588ef2700c275e8fdc08235c74931050c9fe9ed1cae3af831f6a39550cfee015.jpg)  
Fig.4The estimated correlation coefficients ofairborne experimentdata

From Fig.4 we can see that the two successive echoes of the airborne scatterometer are correlated with each other. When the time interval is $1 . 2 \mathrm { m s }$ ,the correlation coefficients are larger than that of $9 . 9 \mathrm { m s }$ obviously.The mean value of correlation coefficient,when the time interval is $1 . 2 \mathrm { m s }$ ，is about O.64 for both HH and VV polarizations.It agrees with that of the theoretical results (see Fig.5).When the time interval is $9 . 9 \mathrm { m s }$ ，the mean value of correlation coefficient is about O.27 for both polarizations.But the theoretical correlation coefficient is almost zero.The difference of estimated and theoretical correlation coefficient is due to the bias of MLE,which is very serious when the coherence is low.

![](images/d9d6827f03a1145bcad55143db95ab3c0fb8d7f9684613f70663bd8b0c52615d.jpg)  
Fig.5 The theoreticalcorrelation coefficient ofairborne scatterometer

# 5.CONCLUSION

Spatial decorrelation is vital for Doppler scatterometer design.It is dominated in the coherence model and determines the best time interval for pulse interferometry. The theoretical formula of spatial decorrelation is given in Eq.(2) which is deduced from the signal model of radar.The correlation coefficients of experiment data are estimated using MLE method and compared with the theoretical one. The results show that they are consistent with each other. The theoretical spatial decorrelation is accurate and can be used inDoppler scatterometer systemdesignand parameters optimization.

# 6.REFERENCES

[1]Q.Bao,X.Dong,D.Zhu,S.Lang,and X.Xu,"The Feasibility of Ocean Surface Current Measurement Using Pencil-Beam Rotating Scatterometer," IEEE Journalof Selected TopicsinApplied Earth Observationsand Remote Sensing, vol.PP,pp.1-11,2015.   
[2] B.Qingliu,D.Xiaolong,and Z.Di,"Ocean surface current measurement using pencil-beam rotating scatterometer," in IEEE Geoscience and Remote Sensing Symposium (IGARSS), pp. 684-687,2014.   
[3] Z.Di, Z. Lei, D. Xiaolong,X. Xing-ou, S. Zhongguo,L. Shuyan,and W. Shaobo,"Airborne experiments validating the spaceborne RFSCAT on CFOSAT,"in IEEE Geoscience and Remote Sensing Symposium (IGARSS),pp.1673-1675, 2013.   
[4] R．Touzi,A.Lopes,J.Bruniquel，and P.W.Vachon, "CoherenceestimationforSARimagery,"IEEE Transactions on Geoscience and Remote Sensing,vol. 37,pp. 135-149,1999.