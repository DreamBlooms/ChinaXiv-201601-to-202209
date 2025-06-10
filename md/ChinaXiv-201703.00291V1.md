# ANALYSIS AND SIMULATION OF GIMS OBSERVATION ON DYNAMIC TARGETS

Ying ZHANGl,², Hao LIUl, Ji WUl, Cheng ZHANGl, Jieying HEl

1Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences 2University of Chinese Academy of Sciences

# ABSTRACT

Imagingperiodisanimportantconsiderationto geostationary interferometric microwave sounder (GIMS) when mapping fast changing target such as typhoon. GIMS simulation system with near real case observation target can evaluatesystemperformanceindifferentsystem configurations and thus help determine the optimal imaging period. In this paper，GIMS simulation system using MATLAB and near real case observation modeled by FNL/WRF/RTTOV method has been used to analyze the effect of imagingperiodon imagequality. System simulation results for each frequency channel will be presented and analyses of imaging period's effect on image quality will also be given.

Index Terms- GIMS， imaging period， simulation system, imaging quality

# 1.INTRODUCTION

Microwave atmospheric sounding from geostationary earth orbit(GEO） have attracted more and more attentions recently. The advantage of continuously monitoring the full earth disk of GEO overLEO observation,together with the ability to detect the vertical distribution of temperature and humidity in troposphere of microwave sounding make GEO microwave sounding very appealing for monitoring fast changing weather such as tropical cyclone.

In order to achieve a moderate spatial resolution around oxygen band (53GHz) in GEO observation,a quite large real aperture antenna is needed. However， deployingand scanning the large traditional real aperture antenna poses a big challenge in satellite application. The technique of interferometric aperture synthesis is considered to be an alternative to help solve this problem [1]. It uses signals intercepted by multiple small antennas to yield the angular response characteristics of a much larger antenna,realizing high spatial resolution while relieving system complexity. Some GEO instruments with this idea have been proposed including GeoSTAR proposed by the Jet Propulsion

Laboratory，NASA [2];GAS proposed by the European Space Research and Technology Center，ESA [3]；and GIMS proposed by the National Space Science Center, Chinese Academy of Sciences [4].

Geostationaryinterferometricmicrowavesounder (GIMS） has been proposed for China's next generation geostationary meteorological satellite. It uses a rotating circular array [5] and is supposed to be working in the timesharing mode [6].Unlike the stationary array system,which collects all the visibilities in one integral period and implements snap-shot imaging，the rotating circular array system collects part of visibilities in one integral period and needs to rotate half a circle to complete collecting all the visibilities needed for image retrieval (i.e. time-sharing sampling),thus leading to a longer imaging period. Since atmospheric parameters are under continuousvariation, resultingintime-variantobservationalbrightness temperatures of the full earth disk,observation with longer imaging period might introduce some blurring to the retrieved image. Through target brightness temperature modeling for GIMS[7]，it is assured that brightness temperature change isparticularly obvious in tropical cyclone region，which is one of the most important meteorological situations to be observed by GIMS.For this reason, it is necessary to evaluate imaging quality under different imaging period configurations for GIMS when observing target of time-variant brightness temperatures, which can help determine the optimal imaging period that can be accepted or drive us to think about algorithm to overcome the blurring under unaccepted imaging period.

# 2.EVALUATIONTOOL—GIMSSIMULATION SYSTEM

To evaluate the effect of imaging period on imaging quality, GIMS simulation system has been constructed.Fig1 shows the framework of GIMS simulation system，which consists ofobservation target modeling， observational process simulation of the sensor,an optional part of observational data processing aiming at correcting the error along with time-sharing sampling,and brightness temperature retrieval from the (optionally processed) observational data.

![](images/4fb156776081bcc88060f824ff50b3af5cdfc13da801299625b0b8508d35e754.jpg)  
Fig1.Framework of GIMS simulation system

# 2.1. Observation target modeling

Theobservation targetmodelingpartutilize FNL/WRF/RTTOV method to generate GEO observational brightness temperature near real case.To put it simply,the NCEP FNL (Final） Operational Global Analysisdata prepared operational every six hours [8] are used as the initial field to drive a state-state-the-art atmospheric modeling system （WRF）[9] capable of meteorological research and numerical weather prediction to generate predictions of surface parameters and vertical atmospheric profiles at specified time and spatial resolution，which is used as inputs into a radiative transfer model(RTTOV)[10] that accounts for propagation and viewing geometries from GEO.In this study，target modeling is set to generate brightness temperatures of the full-earth-disk at $1 0 \mathrm { k m }$ spatial resolution and 1Os temporal resolution during 18:OO to 24:00 on September 19th 2013,when the tropical cyclone “Usagi" upgraded to super typhoon and therefore can be treated as a short-termfast-changingobservationtargetforour evaluation.Fig 2 demonstrates target modeling result of the $5 2 . 8 \mathrm { G H z }$ frequency full-earth-disk brightness temperature map at one particular time.

![](images/d9c655fcde4e487a5a69420bcc732b1f2067e2558318e0f50e5cdbf76e241e92.jpg)  
Fig2.52.8GHz full-earth-disk brightness temperature modeled byFNL/WRF/RTTOV method (K)

# 2.2. Observational process simulation

Theobservational processsimulation mainly simulates function of GIMS sensor,i.e. generates visibilities from fullearth-disk brightness temperature maps using time-sharing sampling mode of the rotating circular array.The simulation have configurable parameters such as system frequency, integral time,imaging period, array configuration and size, and antenna pattern etc.So we can acquire visibilities corresponding to different imaging periods by adjusting the imaging period parameter individually.

# 2.3. Observational data processing

Observational data processing is an optional part in the simulation system.It is first introduced to mitigate the blur along with observing target of rapid change using timesharing sampling.In this study,this part is not used and furthermore it is the conclusion of this study that determines whether this processing part is needed or the threshold for this processing part if the part is necessary.

# 2.4.Brightness temperature retrieval

Brightness temperature retrieval part accomplishes the task of transforming visibilities obtained in observational process simulation part to the final retrieved image.This part utilizes thepseudo-polarFFT algorithm to first interpolate visibilities into pseudo-polar grids and then perform inverse Fourier transform[11].

# 3.PRELIMINARYRESULT

Through GIMS simulation system， the effect of imaging period on imaging quality in time-variant scene observation canbeevaluated byproperlyadjustingsimulation configurations and comparing the retrieved image and the referential image that generated from the observation target modeling part (i.e.image under observation of the sensor). Fig3 displays a retrieved image generated from GIMS simulation system. Imaging period is set to 5min in this case. Root mean square error (RMSE） between this retrieved image and the referential observational image at the middle of the imaging period is 1.1O7K. The error comes from both the image-retrieving algorithm and the blur caused by timevariant target observation.

![](images/ea5644995904d7f76f1c1bffaa225846059f93c02443d566d4a793d142d2203b.jpg)  
Fig3.52.8GHz brightness temperature map retrieved from GIMS simulation system

![](images/e6baadf57b95a20f965d42bfde9dacb6dfc7498fd7e07220650d166c6688c3ec.jpg)  
Fig 4.Relationship between RMSE of retrieved image and imaging period

To illustrate effect of imaging period on blurring caused by time-variant target observation,RMSE value of retrieved image for different imaging period configurations have been calculated and curve of relationship between this RMSE value and imaging period is displayed in fig 4.Each subplot demonstrates curves for one of the seven frequency channels.Red line reveals RMSE for tropical cyclone area, while blur line demonstrates RMSE for the full earth disk. Imaging period of O means observing a static target, namely the snap-shot imaging. Therefore,RMSE at imaging period of O corresponds to inherent error in image-retrieving algorithm and can be used as a contrast to indicate blurring caused by time-variant target observation.

The ascent curves in fig 4 verify the blurring effect of imaging period on retrieved image. And the blurring effect is more severe in tropical cyclone area than full earth disk since curves for tropical cyclone area have larger slope values as marked in the figure.This is due to the fact that tropical cyclone is the main dynamic part in full earth disk. Furthermore，the blurring effect decreases as frequency increases,which means lower frequencies in 5O\~56GHz should be configured with relatively shorter imaging periods to guarantee image quality.

# 4.CONCLUSION

In this study,GIMS simulation system and a set of near real casebrightnesstemperaturemapsmodeledby FNL/WRF/RTTOV method that characterize the full earth diskwith dynamic target of tropical cyclone have been used to quantify the imaging error resulted from dynamic scene observation. By configuring different imaging period, the relationship between quality of retrieved image and imaging period has been clarified.It is verified that longer imaging period indeed affect imaging quality especially for tropical cyclone area and lower frequencies in 5O\~56GHz.In future works,an algorithm that utilizes temporal characteristics of visibilities collected by time-sharing sampling method is expected to be employed to mitigate the error along with time-variant target observation.

# ACKNOWLEDGEMENT

The work is supported by the National High Technology Research and Development Program (863 program),and the Special Fund for Meteorological Research in the Public Interest.

# REFERENCES

[1] C.S. Ruf,C. T. Swift,A. B.Tanner,and D.M. Levine, “Interferometric Synthetic Aperture Microwave Radiometry for the Remote-Sensing of the Earth,”IEEE Trans.Geosci. Remote Sens., vol. 26,no.7, pp.597-611, Sep.1988.

[2]A.B.Tanner，W.J.Wilson,and B.H.Lambrigsten et al., "Initial resultsof the geostationary synthetic thinned array radiometer(GeoSTAR）demonstrator instrument,”IEEE Trans. Geosci.Remote Sens.,vol.45,no.7,pp.1947-1957,Jul.2007. [3] J.Christensen,A.Carlstrom,and H.Ekstrom et al.,“GAS: the Geostationary Atmospheric Sounder,”in Proc.IGARSS,Barcelona. Spain,Jul. 23-27,2007,pp.223-226.   
[4]H.Liu,J.Wu,and S.W. Zhang et al.,“Conceptual design and breadboardingactivitiesofGeostationaryInterferometric Microwave Sounder (GIMS),” in Proc. IGARSS,Cape Town, South Africa, Jul.12-17,2009,pp.III-1039-III-1042.   
[5] C. Zhang，H. Liu, and J. Wu et al.，“Geostationary Interferometric Microwave Sounder Demonstrator,”IEEE Trans. Geosci. Remote Sens.,vol.53,no.1,pp.207-218.   
[6] H.Liu, J.Wu,and S.W. Zhang et al.,“The Geostationary Interferometric Microwave Sounder(Gims):Instrument Overview andRecent Progress,”in Proc.IGARSS,Vancouver,BC,Canada, Jul. 24-29,2011,pp.3629-3632.   
[7] Y.Zhang,H. Liu,and J. Wu et al.，“Target Brightness Temperature Simulation and Analysis for the Geostationary Interferometric Microwave Sounder(GIMS),”in Proc.IGARSS, Milan,Italy,Jul.26-31,2015,pp.3477-3480.   
[8]National Centers for Environmental Prediction/National Weather Service/NOAA/U.S.Department of Commerce，2000, NCEP FNL Operational Model Global Tropospheric Analyses, continuing fromJuly 1999.Research Data Archive at the National Center for Atmospheric Research,Computational and Information SystemsLaboratory，Boulder， CO.[Availableonlineat http://dx.doi.0rg/10.5065/D6M043C6].   
[9]W.C. Skamarock,J.B.Klemp,J.Dudhia,D.O. Gill, and D.M. Barker et al.,A Description of the Advanced Research WRF Version 3,NCAR Tech.Note NCAR/TN-475+STR.[Available online at http://www2.mmm.ucar.edu/wrf/users/docs/arw_v3.pdf]. [10]J.Hocking,P.Rayer,D.Rundle andR.Saunders,RTTOVv11 Users Guide， NWPSAF-MO-UD-028.[Available onlineat http://nwpsaf.eu/deliverables/rtm/docs_rttov11/users_guide_11_v1 .3.pdf].   
[11]C.Zhang,J.Wu,W.Y.Sun,“Applications ofPseudo-Polar FFT in Synthetic Aperture Radiometer Imaging,”PIERS Online, vol. 3, no. 1, pp. 25-30, 2007.