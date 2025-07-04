# Preliminary results of centroiding experiment for the STEP mission

Haitao ${ \mathrm { L i } } ^ { * _ { \mathrm { a , b } } }$ , Baoquan Li², Yang Caoa, Ding Chen², and Ligang Lib.c aNational Space Science Center, Chinese Academy of Sciences, Beijing, China; b Key Laboratory of Planetary Sciences, Chinese Academy of Sciences, Shanghai , China;‘ Shanghai Astronomical Observatory, Chinese Academy of Sciences, Shanghai , China

# ABSTRACT

Search for Terrestrial Exo-Planet (STEP)[1] was originally proposed in2O13 bythe National Space Science Center, Chinese AcademyofSciences,which is currently being under background engineering study phase in China.The STEP mission is a space astrometry telescope working at visible light wavelengths.The STEP aims at the nearby terrestrial planets detection through micro-arcsecond-level astrometry. Determination of the separation between star images on a detector with high precision is very important for astrometric exoplanets detection through the observation of star wobbles due to planets.The requirement of centroiding acuracyfor STEP is le-5 pixel.A centroiding experiment have ben carried out on a metrology testbed in open laboratory.In this paper，we present the preliminary resultsof determining the separations betweenstarimages.Without calibrationof pixel positions and intra-pixelresponse,we have demonstrated thatthestandard deviationof diferentialcentroiding is below7.4e-3 pixel bythealgorithmof linear corrected photon weighted means(LCPWM)[2,3].For comparison,the photon weighted means(PWM) and Gaussfting are also usedin the data reduction.These results pave the way for the geometricalcalibration andthe intra-pixel quantum efficiency(QE) calibration of detector array equipment for micro-pixel accuracy centroiding.

KEYWORDS: STEP, exoplanets, centroiding, linear corrected photon weighted means, Gaus fitting

# 1.INTRODUCTION

In 1992, two planets around the pulsar PSR $1 2 5 7 + 1 2$ are discovered based on the timing measurements of the periodic variationof the pulsar's radio pulses[4].The discoveryof the first extra-solar planet surounding a main-sequence star was announced in 1995 by measuring the periodic radial velocityvariations of the steler reflex motion[5].Several methods for detecting exoplanets have been developed: Doppler measurements,transit observations，microlensing, astrometry,and direct imagingand so forth.Since the discoveryof51 Peg b,an increasing numberof planets and planetary candidates.

Most of the planets found outside the Solar Systemare gas giants,because theyare more easily detectable.Beter instruments and improved detection limits have pushed our capabilities towards the detection of low-mass and smal planets.Although astrometry is the mostancient technique of astronomy,the technique has enormous potential and is complementary toother methods.Fortunately,withthe successful launch of the Gaia satelite,the prospects for spacebased astrometric planet searches are good. It will also pave the way for future space astrometry misions aiming at detecting the Earth-like planets around nearby stars[6].

The STEP mision aims at the nearby earth-alike planets detection,comprehensive research on the planetary system and the calibration of the cosmos distance with $1 ~ \mu \mathrm { a s }$ astrometry precision in the space and get the fruitful achievements in the planetary and astrometry research fields.The FOV of STEP is $0 . 4 4 \times 0 . 4 4$ square degrees,based on $1 . 2 \mathrm { m }$ primary and focus length is $3 1 \mathrm { m }$ .The Cassegrain and TMA design(different from NEAT design[7-11]), mosaic APS and the laser metrology technique will be taken to achieve $1 \mu \mathrm { a s }$ astrometry precision[1].

Theheterodyne laser interference metrologyand the high precision centroiding is the key technology forthe STEP.In this work,we willpresent the preliminary results of acentroiding experiment.The paper is organized as follows.The design of the experiment is presented in Sec.2.In Sec.3,the datareduction method andthe results are presented.The discussion and summary are given in Sec.4.

# 2.DESIGNOF THE EXPERIMENT

![](images/b3e1bd86ea22d12a23aafe55dda9d15e380948d0049342d0083f9ed6eeb53091.jpg)  
Figure 1. Schematic of the metrology and centroiding testbed.

The testbed contains two sub systems: the heterodyne laser interference system and the pseudo star system.A similar optical designappeared in the NEATcentroiding testbed[12-15].The heterodyne laser interference system is used to calibrate the detector arrayequipment.The AOMs are introduced in the optical path to offset the frequencyof two coherent laser beams.Thus the moving fringes canbe generatedon the detector.The moving fringes areused to calibrate thegeometrical characteristics and the intra-pixel QE of the detector array.A white source and a single mode fiber bundle is used to generate the pseudo star source.With thesphericalmirorreflecting the lightonto the detector,everal point spread functions can be obtained.The separations between these star images can be measured using many kinds of centroiding algorithms.The schematic of the metrology and centroiding testbed is shown inFigure 1.The parameters of the testbed is listed in Table 1.

Table 1. The main technical parameters of testbed.   

<html><body><table><tr><td rowspan="2">Laser wave- length (nm)</td><td rowspan="2">Pupils of spherical mirror (mm)</td><td rowspan="2">Focal lemh</td><td rowspan="2">CMOS</td><td rowspan="2">(μm)</td><td rowspan="2"></td><td rowspan="2">Wavelength of white source (nm)</td></tr><tr><td>Pixel size No. of fiber cores</td></tr><tr><td>632.8</td><td>5</td><td>600</td><td>2048x 2048/</td><td>11×11/ 3.75×3.75</td><td>5</td><td>440-800</td></tr></table></body></html>

# 3.DATA ACQUISITION,REDUCTION AND RESULTS

Firstly，in order to demonstratethe image acquisition capability of the heterodyne laser interference system the metrology fringes are captured through a commercial camera with $9 6 0 { \times } 1 2 8 0$ array.With these frames we evaluate the data quality.Secondly,the pseudo star images are captured.The separation between twoof them is used as a metric in our experiment.We put the point spread functions (PSFs)on51 diferent positions ofthe detector.Then theseparation betweentwoof them are measured 51times andthe standard deviation are calculated.While thedark frames andthe flat field frames are captured.

# 3.1The darkand flat field calibration

The firststepis thedark fieldsubtractionandflatfielding.Weuse thesame exposure time with the fringe frames and the star fieldframes toobtain thedark frames.Theflat field framesareobtained fromthe integrating sphere.Thefinal data are derived through the dark subtraction and the flat fielding.The flat field response of a $3 8 0 \times 6 5 0$ pixel array is shown in Figure 2. These pixels are used to calculated the separation of the stars.

![](images/c1a644f5e560cd02201ad25eb5053fb550f835497cf47d5e945fd68cdb991d13.jpg)  
Figure 2.The flat field calibration result by integrating sphere.The area shown here contains $3 8 0 \times 6 5 0$ pixels.The peak to valley (PV) value is 0.0515.The standard deviation of photo-response non-uniformity(PRNU) is 0.0056.

# 3.2 The metrology fringes

Two orthogonal interference base lines are chosen,thus theorthogonal fringes are derived.Because the fringes move across the CMOS,every pixel on the detector willseea sine wave variation of the intensity.The fringes and the pixel intensity variation with time are shown in Figure 3 and 4.

![](images/a533b7216e8359c05df123a535a9e799cbeec75dcdec25772c78da5a2fcceb53.jpg)  
Figure 3.The horizontal fringes and vertical fringes.Two corners are shown here for clarity.

![](images/89ee8533948a9921ff4529fb457eff0c93f6d516982cddfa8a51bf85464a672d.jpg)  
Figure 4.The sinusoidal waves ofintensity variation for7randomly selected pixels from l fringe data cube.

# 3.3 The pseudo star field

In our experiment,5 star images are obtained through asingle mode fiberbundle.The star images are shown in Figure 5. As shown inFigure 5,we measured the distance between star Aand starB.The star field is put on 51 different positions of the detector through the translation of the stage. The translation step is $1 0 \mu \mathrm { m } ( \sim 2 . 5 \mathrm { p i x e l } )$

![](images/156df133746d962329bc90dcd58ba117ff0271bf6f88666ff82290767261e572.jpg)  
Figure 5.The pseudo starfieldfromasingle mode fiberbundleconsist with5cores.Forconvenience,thefive star images arelabeledwithA,B,C,D,E.

# 3.4The centroidcalculation

In thestar field datareduction，weuse three algorithms todothecalculationof thecentroid,namely,the photon weighted means(PWM),the linear corrected photon weighted means(LCPWM)[2,3]and the Gaussfiting.The standard deviationsare derived.We findthat the standarddeviation byLCPWMis the most smalest.There isasystematic deviationbetween the Gaussfitingand the PWM/LCPWMfor X dierential centroid,but thefluctuation trend and the mean values of Y differential centroid calculated with the three algorithms are in good agreement.

Xdiffrential centroid 123.19 (a) -LCPWM(std=0.0073504,meanvalue=123.1344) 314.54 (b) Y diffrential centroid 123.18 Gauss(std=0.0093032,meanvalue123.1653) PWM(std=0.0099641meanvalue=123.1365) 314.53 123.17 314.52 000 （eeid loneegeiia reneeo 314.51 Ma 314.5 314.49 314.48 -LCPWM(std=0.0067938,meanvalue=314.5038) 314.47 PWM(std=0.012371,meanvalue=314.5044) Gauss (std=0.014717,meanvalue=314.5092) 123.11 314.46 0 10 20 30 40 50 60 0 10 20 30 40 50 60 Measurementtimes Measurement times

# 4. SUMMARY

We have carred out measurements ofcentroid of artificial star images ona CMOS detector to investigate the accuracy of the positions of the stars,using three algorithms for comparison.Finally,we have demonstrated that the standard deviation of the measurements for the diferential positions of the star images is below 7.4e-3 pixels for 51 measurements.Folow-on investigations willinclude a more thorough characterization of back iluminated CMOS,such as the geometrical calibration and the intra-pixel QE calibration of the detector array.

# ACKNOWLEDGMENTS

Thanks to the support of the advanced research project in Chinese Strategic Pioneer Program (SPP)on Space Science. The Work was also funded bythe KeyLaboratoryof Planetary Sciences,Shanghai Astronomical Observatory/Purple Mountain Observatory,Chinese Academyof Sciences(NO.PSL15_13).We also thank to the help and dicussions from M. Shao, F. Malbet, A. Legar and Peng Sang.

# REFERENCES

[1] Chen D.，"STEP mission: high-precision space astrometry to search for terrstrial exoplanets. Journal of Instrumentation," 9:C04040(April 2014).   
[2] Triebes,K., Gillan,L.,Hilby,T.et al.,"Full Sky Astrometric Mapping Explorer,FAME,CCD Centroiding Experiment," Proc. of SPIE,4013 (2000).   
[3]Yano,T.,Gouda,N.,Kobayashi,Y.,Tsujimoto,T.,Nakajima,T.,Hanada,H.,Kan-ya,Y.,Yamada,Y.,Araki, H.,Tazawa, S.,Asari, K., Tsuruta, S.,and Kawano,N.,"CCD centroiding experiment for the japan astrometry satelite misson(jasmine)and in situ lunar orientation measurement(ilom)," Publications of the Astronomical Society of the Pacific,116(821), 667-673 (2004).   
[4] Wolszczan, A.，and D.A. Frail., "A planetary system around the millisecond pulsar PSR $1 2 5 7 + 1 2$ ," Nature 355(6356), 145-7(1992).   
[5] Mayor,M.and Queloz,D.,"A Jupiter-mass companion to a solar-type star," Nature 378,355-359(1995).   
[6]Lidegren,.,Babusiaux, C.,Bailer-Jones,C.,Bastian,U.,Brown,A. G.A., Cropper,M., Hog,E., Jordi, C, Katz,D.,van Leeuwen,F.,Luri,X.,Mignard,F.,de Bruijne,J.H.J.and Prusti.T.,"The Gaia mission: science, organization and present status," In W.J. Jin,I. Platais,and M. A. C.Perryman, editors,IAU Symposium, 248, 217-223, (July 2008).   
[7] Shao,M.,Nemati,B.,Zhai, C.,and Goulioud,R., "NEAT: a Microarcsec Astrometric Telescope,"Proc.of SPIE 8151,81510V-1-81510V-7(2011).   
[8] Malbet,F.,Leger,A.,Shao,M., Goulloud,R.,Lagage,P.-O.,Brown,A. G.A., Cara,C.,Durand,G.,Eiroa,C, Feautrier,P.Jakobson,B.,Hinglais,E.,Kaltenegger,L.,Labadie,L.,Lagrange,A.-M.,Laskar,J.,Liseau,R, Lunine,J.,Maldonado,J.,Mercier,M.,Mordasini,C.,Queloz,D., Quirrenbach,A.,Sozzeti,A.,Traub,W, Absil, O.,Alibert,Y.,Andrei,A.H.,Arenou,F.,Beichman,C.,Cheli,A.,Cockel, C.S.,Duvert, G,Foreille T., Garcia,P.J.V., Hobbs,D.， Krone-Martins,A.，Lammer,H.，Meunier, N., Minardi, S.,Moitinho de Almeida,A.,Rambaux,N.,Raymond, S.,Rottgering,H. J. A.，Sahlmann, J., Schuller,P.A., Segransan,D, Selsis,F.,Surdej,J.,Vilaver,E.,White,G.J.,and Zinnecker,H.,"High precision astrometry mission forthe detection and characterization of nearby habitable planetary systems with the nearby earth astrometric telescope (neat),"Experimental Astronomy,109 (Sep 2011).   
[9]Malbet,F.,Goulioud,R.,Lagage,P.,Leger,A.,Shao,M.,Crouzier,A.,and consortium NEAT,"Neat:aspace born astrometric mission for the detection and characterization of nearby habitable planetary systems," Proc. of SPIE 8442 (2012).   
[10]Malbet,F.，Crouzier,A.,Leger,A.， Shao,M., Goullioud,R.，and Duigou, J.-M.L.，"Neat: ultra-precise diferential astrometry to characterize planetary systems with earth-mass exoplanets in the vicinity of our sun," Proc. of SPIE 9143 (2014).   
[11]Malbet,F., Crouzier,A.,Leger,A.,and al.,"Neat: an astrometric mision to detect nearby planetarysystems down to the earth mass," Proc.of SPIE 8864 (2013).   
[12]Zhai, C.,Shao,M.,Goulioud,R.,and Nemati,B.,"Micro-pixel accuracycentroid displacement estimationand detector calibration," Royal Society of London Proceedings Series A 467,3550-3569 (2011).   
[13]Nemati,B.,Shao,M.,Zhai,C.,Erlig,H., Wang, X.,and Goulioud,R.,"Micro-pixel image positionsensing testbed," Proc.of SPIE 8151 (2011).   
[14]Crouzier,A.,Malbet,F.,Preis,O.,Henault,F.,Kern,P.,Martin,G.,Feautrier,P.,Cara, C.,Lagage,P.O.,L' eger,A.,LeDuigou, J.M., Shao.,M.，and Goulioud,R., "An experimental testbed for neat to demonstrate micro-pixel accuracy," Proc. of SPIE 8445 (2012).   
[15]Crouzier,A.,Malbet,F.,Preis,O.,Henault,F.,Kern,P.,Martin,G.,Feautrier,P.,Cara, C.,Lagage,P.O.,L' eger,A.,LeDuigou, J. M., Shao.,M.,and Goullioud,R.,"First experimental results of very high accuracy centroiding measurements for the neat astrometric mission," Proc. of SPIE 8864 (2013).