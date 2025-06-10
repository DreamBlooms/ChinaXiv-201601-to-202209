# Inter-Element Phase Calibration for Geostationary Interferometric Microwave Sounder (GIMS)

Donghao Han,Hao Liu,Member,IEEE,JiWu,Fellow, IEEE,Zhang Cheng,Member, IEEE,Lijie Niu, Ying Zhang

Abstract—TheGeostationaryInterferometricMicrowave Sounder(GIMS） is a new concept of atmospheric microwave sounderforChina'sfuturegeostationaryearthorbit meteorological satellite (FY-4).A novel self-calibration method for interferometric radiometers with rotating thinned array, especially for GIMS,has been proposed in this paper.Compared with traditional relative phase calibration approach,neither dedicated hardware nor dedicated calibration working model is needed to achieved the relative phase calibration in this novel inter-element phase calibration.The self-calibration approach is inherently merged with the nominal observation working model of GIMS,thanks to the continuous array rotating of GIMS instrument.A running average scheme has been introduced into the self-calibration approach to enhance the signal to noise ratio (SNR) of the calibration data,whichisnormallyvery lowwith the natural earth scene.The method is demonstrated by both simulation and field imaging experiment.

Index Terms—inter-element phase calibration,Geostationary Interferometric Microwave Sounder(GIMS)， phase error, synthetic aperture radiometer,

GIMs[5] concept by NSSC.

GIMS is a millimeter wave imaging sounder concept proposedforChina'snextgenerationgeostationary meteorological satellite (FY-4M). GIMS is supposed to utilize arotating circular thinned array,instead ofa stationaryY-shape array, to reduce the required number of the antenna elements.A proof-of-concept $5 3 \mathrm { G H z }$ ground-based GIMS demonstrator with 28 elements has been successfully developed and tested during $2 0 0 9 { \sim } 2 0 1 2 ^ { [ 6 ] }$ . A new GIMS demonstrator development plan has been approved for further risk mitigation.A 70 element demonstratoris foreseento be finished before the end of 2016.Fig.1illustrates the artistic view of GIMS instrument in orbit.

# I．INTRODUCTION

Realizingmicrowave atmospheresoundingfrom geostationary earth orbit （GEO） is an emerging researching field since $\mathrm { 1 9 9 0 ^ { 9 } s ^ { [ 1 ] [ 2 ] } }$ . GEO can guarantee the fixed continuous observation to a particular region，while the relative low frequency band (compared with infrared waves) can guarantee all-weather observation with a 3D image capability for the atmospheric temperature and moisture.Those features make the GEO microwave sounding very appealing for short term meteorological forecasting.

The largest obstacle of GEO microwave observation is the restriction ofspatial resolution.Interferometric aperture synthesis is an effective solution to this problem,by using a thinned antenna array to replace the single large aperture antenna. Since $2 0 0 0 ^ { \circ } \mathrm { s } .$ ,several interferometry based instrument concepts have been proposed，including the GeoSTAR[3] concept by NASA/JPL, the $\mathrm { G A S } ^ { [ 4 ] }$ concept by ESA and the

![](images/d765953eaefde3e44d83cc8336697dc63b903dc2c39beff3b68bc8d9960ca9cf.jpg)  
Fig.1(a) Conceptual view of GIMS

The calibration of GIMS is a key process to ensure quantitative conversion of raw measurement data into scientific data with physical meaning. For GIMS， the periodical single-element total power calibration can be easily achieved bya cold sky mirror and a blackbody,which are installed on the fixed part of platform with a deployable mechanism and can be periodically switched to block the FOV of each element antenna[5]. Besides the single-element total power calibration, periodical inter-element phase calibration is also needed for an interferometric radiometer like GIMS.The traditional method is to use correlated noise injection[7],which would seriously increase hardware requirements and system complexity[8i. Different from this, some phase self-calibration methods have been proposed for GeoSTAR[9]l0]，in which， specific extra external source is necessary to improve measurement signal to noise ratio (SNR) in calibration[9].

In this paper,two new schemes have been introduced in GIMS inter-element phase calibration method.

(1). Thanks to the array rotating,each baseline can get a conjugated measurement after half array revolution. Taken advantage of this feature, running average scheme is proposed to reduce the effect of noise in phase calibration for GIMS,so extra point source is no longer needed.

(2). Taken advantage of the prior information of the brightness temperature distribution as viewed from geostationary orbit, the prior knowledge of the very short baseline phases is used to eliminate phase ambiguity.

Withaboveimprovements，acompletepractical inter-element phase calibration method has been set-up for GIMS.The method is demonstrated by both simulation and filed imaging experiment.

# II.GIMSINTER-ELEMENTPHASEMODEL

Asa microwave interferometric radiometer (MIR),the thinned antenna array of GIMS with 7O elements is shown in Fig. 2(a). Although the snapshot uv samples are very sparse and irregular,as shown in Fig.2(b),the full sampling coverage of spatial frequency domain will be achieved after half revolution,which is also necessary for inter-element phase calibration.

![](images/a2fb796918efc9ab427ed34136a147bbd1987dfc3791d75acab562947bb7538b.jpg)  
Fig.2. (a) Antenna array of GIMS (b) Corresponding snapshot uv samples

The longest baseline of the array in Fig.2 is about $6 1 7 \lambda$ ， while the maximum spacing between two adjacent antennas is controlled under $1 3 0 \lambda$ ，which is an important coefficient for inter-element phase calibration.Similar with the 28-element array of the proof-of-concept GIMS demonstrator[6], there are two kinds of antennas in the 7O-element GIMS array: three small aperture antennas to form the shortest baselines,and 67 large aperture antennas to form other baselines.It should be point out that, the second shortest antenna spacing is $6 . 3 \lambda$ ， which is short enough to be preset with a confidence interval in the following sections.

The output of receivers $i$ and $j$ is given by[11]

$$
\begin{array} { r l } & { V _ { i j } ( u , \mathrm { v } ) = \displaystyle \iint _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } \frac { T ( \xi , \eta ) - T _ { r } } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } { \cdot } F _ { i } ( \xi , \eta ) { \cdot } F _ { j } ^ { * } ( \xi , \eta ) \mathrm { \Omega } } \\ & { \quad \quad \quad \cdot \tilde { r } _ { i j } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) \cdot e ^ { - j 2 \pi ( u \xi + \nu \eta ) } d \xi d \eta } \end{array}
$$

In which, $u$ and $\nu$ are the projections over the X-Y axes of the vector defined between the two phase centers of the antennas normalized to the wavelength. Subscript $i$ and $j$ means channel number. (,n） are the director cosines[1], which respect to the (X,Y) axes, equal to $( \sin \theta \cos \theta , \sin \theta \sin \theta )$ ： $T _ { r }$ isthe receiver'sphysical temperature[11][12], assumed equal in all elements. The contribution of $T _ { r }$ is negligible in the GIMS prototype due to the low antenna coupling and the large antenna separation. $F ( \xi , \eta )$ describes the plural antenna pattern and $\tilde { r } _ { i j }$ presents the characteristics of interferometer receivers,whichis known as fringe washing function[13].

Measured visibility phase of $V _ { _ { i j } }$ is given by

$$
\phi _ { i j } = \psi _ { i j } + \alpha _ { i } - \alpha _ { j } + \alpha _ { i j } + \alpha _ { n }
$$

Where $\psi _ { i j }$ is the ideal phase of the visibility. $\alpha _ { n }$ is a random phase term introduced by thermal noise. $\alpha _ { i }$ and $\alpha _ { j }$ are the receivers phases. $\alpha _ { i j }$ is the inseparable phase error introduced by fringe washing，which can be considered negligible for the short and medium length baselines of GIMS.By running average scheme,which will bedescribed in the following sections, $\alpha _ { n }$ can also be reduced negligible. Then Eq.(2) can be further simplified as

$$
\phi _ { i j } = \psi _ { i j } + \alpha _ { i } - \alpha _ { j }
$$

# II.INTER-ELEMENTPHASECALIBRATION

Lots of redundant information can be achieved during observation for GIMS and element phase information will be implied in them.Inter-element phase calibration can extract this information by redundant observation in a reliable way.

# A.Optimized Redundancy Equations

Image of the physical world has the property of real value when looking from space. Therefore，itsideal Fourier transformation is a Hermitian type function that has the property

$$
V ( u , \nu ) = V ^ { * } ( - u , - \nu )
$$

In which,asterisk means Hermitian operator.Image will be assumed changeless during one period of array rotation, then $V ( u , \nu )$ and $V ( - u , - \nu )$ are both measured by the same baseline with $1 8 0 ^ { \circ }$ baseline rotation. Submitting the phase information of (4) into (3), we can get[9]

$$
\begin{array} { c }  { { \left\{ \begin{array} { l } { { \phi _ { i j } ^ { \theta } = { \psi } _ { i j } ^ { \theta } + \alpha _ { i } - \alpha _ { j } } \\ { { \phi } _ { i j } ^ { \theta + \pi } = - { \psi } _ { i j } ^ { \theta } + \alpha _ { i } - \alpha _ { j } } \end{array}  } } } \en\right.d{array} \end{array}
$$

The superscript $\theta$ means baseline rotation angle. $\phi _ { i j } ^ { \theta }$ and $\phi _ { i j } ^ { \theta + \pi }$ are the phase of $V _ { i j } ^ { \theta }$ and $V _ { i j } ^ { \theta + \pi }$ respectively. With a simple algebraic transformation

$$
\gamma _ { _ { i j } } = \alpha _ { i } - \alpha _ { _ j } = { \frac { \phi _ { _ { i j } } ^ { \theta } + \phi _ { _ { i j } } ^ { \theta + \pi } } { 2 } }
$$

However,this procedure would yield large errors in the estimation of phases because the phase $\gamma _ { i j }$ from $\phi _ { i j } ^ { \theta }$ and $\phi _ { i j } ^ { \theta + \pi }$ presents a large error in most visibility samples due to very poor measurement SNR.

Running average scheme is proposed to optimize Eq. (6).

Selecting an arbitrary time slice during the array rotation,we can get many pairs of $\phi _ { i j } ^ { \theta }$ and $\phi _ { i j } ^ { \theta + \pi }$ . By averaging them

$$
\hat { \gamma } _ { i j } = \frac { \displaystyle \sum _ { \theta = \theta _ { 0 } } ^ { \theta _ { 1 } } [ w _ { i j } ^ { \theta } ( { \phi } _ { i j } ^ { \theta } + { \phi } _ { i j } ^ { \theta + \pi } ) ] } { \displaystyle 2 \cdot \sum _ { \theta = \theta _ { 0 } } ^ { \theta _ { 1 } } [ w _ { i j } ^ { \theta } ] }
$$

$$
\hat { \Gamma } _ { e } = \mathbf { P } _ { e } \cdot \mathbf { A }
$$

Eq.(12) is welcome to be added to Eq.(1O), so the final redundancy equation is achieved:

$$
{ \left[ \hat { \mathbf { \Gamma } } _ { r } \right] } = { \left[ \mathbf { P } _ { r } \right] } . \mathbf { A }
$$

where the superscript bracket means the optimization of Yi $[ \theta _ { 0 } , \theta _ { 1 } ]$ is the rotation angle corresponding to the selected time slice. Eq. （7） implies that $( \phi _ { i j } ^ { \theta } + \phi _ { i j } ^ { \theta + \pi } )$ can be regarded as a measurement of $\gamma _ { i j }$ ，and $w _ { i j } ^ { \theta }$ is the weight of this measure. multiple measurements will be weighted averaged to improve measurement SNR，which can be defined as the radio of visibility amplitude to the standard variation of noise.

From another point of view,running average scheme is equivalent to extending integration time，and the standard variation of noise is inversely proportional to the square of the integration time. So $w _ { i j } ^ { \theta }$ can be optimized under the SNR optimization principle as

$$
w _ { i j } ^ { \theta } = \left( \left| V _ { i j } ^ { \theta } \right| + \left| V _ { i j } ^ { \theta + \pi } \right| \right) ^ { 2 }
$$

With running average scheme, the measurement SNR will not be restricted by measurement amplitude,but the extent of selected time slice,which is limited by the instrument stability.

Taking all of the baselines into account for an array which has $N$ channels similarly as Eq. (7)，the following set of equationscanbe established

$$
\left[ \begin{array} { l } { \hat { \gamma } _ { 1 2 } } \\ { \hat { \gamma } _ { 1 3 } } \\ { \cdots } \\ { \cdots } \\ { \hat { \gamma } _ { 1 N } } \\ { \hat { \gamma } _ { 2 3 } } \\ { \cdots } \\ { \cdots } \\ { \hat { \gamma } _ { ( N - 1 ) N } } \end{array} \right] = \left[ \begin{array} { l l l l l l l } { 1 } & { - 1 } & { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } \\ { 1 } & { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } \\ { \cdots } & { \cdots } & { \cdots } & { \cdots } & { \cdots } & { \cdots } \\ { 1 } & { 0 } & { 0 } & { \cdots } & { \cdots } & { \cdots } & { - 1 } \\ { 0 } & { 1 } & { - 1 } & { 0 } & { \cdots } & { \cdots } & { 0 } \\ { \cdots } & { \cdots } & { \cdots } & { \cdots } & { \cdots } & { \cdots } & { \cdots } \\ { 0 } & { 0 } & { \cdots } & { \cdots } & { 0 } & { 1 } & { - 1 } \end{array} \right] \left[ \begin{array} { l } { \alpha _ { 1 } } \\ { \alpha _ { 2 } } \\ { \cdots } \\ { \cdots } \\ { \cdots } \\ { \cdots } \\ { \alpha _ { N - 1 } } \\ { \alpha _ { N } } \end{array} \right]
$$

This can be written in a simplified form as

$$
\hat { \mathbf { I } } _ { r } = \mathbf { P } _ { r } \cdot \mathbf { A }
$$

When the first channel is set as a reference by assigning a zero phase to it. Eq.(1O) is proved a determined and complete system of equations for solving the unknown phases in a least-square sense as long as the equations related to all adjacent antenna pairs are preserved[9]. So the equations corresponding to long baselines should be removed because of the serious fringe washing or poor SNR.

Inaddition， equal length baselinescould produce redundancy equations during array rotation[10], which can be describedas

$$
\gamma _ { a b } - \gamma _ { i j } = ( \alpha _ { a } - \alpha _ { b } ) - ( \alpha _ { i } - \alpha _ { j } ) = \phi _ { a b } ^ { \theta } - \phi _ { i j } ^ { \theta }
$$

where baseline $a b$ and baseline $i j$ have the same length. Similar as Eq.(7),running average scheme and long baselines removing are also operated for Eq.(11),the optimized results ofall equallength baselines canbe written ina simplified form

# B. Phase Unwrapping

Phase ambiguity is produced by the division operation in Eq. (7)，so the solution of the final redundancy equation is $\mathbf { A } + \mathbf { k } \pi$ ，in which $\mathbf { k }$ is a vector consist of O and 1,other information must be added to get accurate $\mathbf { A }$ ：

For the very short baselines,which normally means the shortest and the second shortest baseline,the visibility is mainlydetermined by earth/skyand land/sea contours, insensitivity to the brightness temperature details of the earth disk.So the phase can be predicted in a confidence interval. Thus,the phase ambiguity of these baselines can be easy solved by a comparison between the solution of final redundancy equations and the preset confidence interval.

For other baselines,some techniques should be considered for phase unwrapping. One is closure phase[14], which is widely used in optical synthetic aperture field to eliminate the phase error of atmospheric disturbance.For microwave synthetic aperture radiometer,the closure phase relationship can be derived from

$$
\begin{array} { r l } { \phi _ { a b } ^ { t } + \phi _ { b c } ^ { t } + \phi _ { c a } ^ { t } = \psi _ { \ a b } ^ { t } + \alpha _ { a } - \alpha _ { b } } & { } \\ { + \psi _ { b c } ^ { t } + \alpha _ { b } - \alpha _ { c } + \psi _ { c a } ^ { t } + \alpha _ { c } - \alpha _ { a } } & { } \\ { = \psi _ { \ a b } ^ { t } + \psi _ { b c } ^ { t } + \psi _ { c a } ^ { t } } & { } \end{array}
$$

superscript $t$ means measurement moment.Baseline $a b , b c$ and $c a$ stick to each other in a closed loop,which is so-called phase closure.Eq. (14) implies that,if two of the phase closure have been phase unwrapped, the remaining one will be solved by closure phase relationship.

Another technique is equal length baselines,which has already involved in final redundancy equations and now is used again for phase unwrapping.

For equal length baselines $a b$ and $i j$ , we can get

$$
\psi _ { a b } ^ { \theta } = \psi _ { i j } ^ { \theta }
$$

In which,as one of these equal length baselines has been phase unwrapped, the remaining baselines will be solved.

Eq.(14) and Eq.(15) would also yield large errors due to very poor measurement SNR，which can be optimized by running average scheme similarly as Eq. (7).

What should be noticed that phase unwrapping can only deduce phase ambiguity and have no influence on the solution accuracy,which is decided by the final redundancy equations.

# IV.SIMULATIONANDEXPERIMENT

# A．Geo-image Simulation

In order to assist the implementation of GIMS,a simulator isdeveloped tocalculate thevisibility functionand reconstructed image[15]. Pseudo-polar Fast Fourier Transform Algorithm is used in the simulator[16].

The original input of simulation is a full earth imaging in $5 0 . 3 \mathrm { G H z }$ ，which is shown in Fig.3(a).The antennas arrayis showninFig.2(a).After brightness to visibility simulation, the maximum visibility amplitudes for each baseline are shown in Fig.3(b).In which,the visibility amplitude drops dramatically asthe increase of baseline length. Inter-element phase calibration has been conducted with the baselines less than $1 3 0 \lambda$ . The corresponding visibility amplitude is about O.25K.

![](images/9f3b957661c4462b89cfcf8f4bebecb2122e7cfed5af685e8046031a9f44f02f.jpg)  
Fig.3(a) original input imaging,(b) visibility amplitude corresponding to different baselines

During inversion simulation, thermal noise with standard deviation $\sigma = 0 . 0 6 K$ corresponding to $5 0 0 \mathrm { { m s } }$ integration time is add to the visibility.Random phase errors within $\pm 4 0 ^ { \circ }$ are added to the receiving elements.The reconstructed image without phase calibration is shown inFig.4(a).Annular fuzzy is serious because of the phase error.To calibrate this error, Snapshot SNR in Eq. (6) and Eq.(11)is just about 4.After optimized by running average scheme,in which the averaging time slice is selected as 5min. SNR can be improved larger than 26,which gives a random phase $\alpha _ { n }$ with a standard variation lower than $\sigma _ { \alpha _ { n } } = 1 . 3 ^ { \circ }$ . For the shortest baselines with a length $3 . 1 \lambda$ and the second shortest baselines with a length $6 . 3 \lambda$ ,the phase will be preset in $[ - \pi / 2 \sim \pi / 2 ]$ and $[ \pi / 2 \sim 3 \pi / 2 ]$ respectively.The reconstructed image after inter-element phase calibration is shown in Fig.4(b).

![](images/09bf974afbc7bfe124b2cfe6550b8ee4ee333cfac46955e7a5dd88f0cbbc2c71.jpg)  
Fig.4(a) rawretrieved imaging,(b) retrieved imagingafter inter-element phase calibration

To evaluate the influence of residual element phase error, radiometric error $\sigma _ { { \scriptscriptstyle T } }$ is defined as the standard deviation of $\Delta T ( \xi _ { m } , \eta _ { n } )$ , which is the difference between the ideal and the error contained retrieved image inside the circle with radius $r = 0 . 1$ ，corresponding to the $4 5 ^ { \circ }$ incidence angle from $\mathrm { G E O ^ { [ 9 ] } }$ . Element phase error $\sigma _ { D }$ is defined as the standard deviation of residual element phase error after inter-element phase calibration. Fig. 5 shows $\sigma _ { { \scriptscriptstyle T } }$ increase in relation to $\sigma _ { D } .$ Taking into account an overall radiometric error of 1.5K，if O.3K is assigned to phase errors, it must be constrained to $0 . 9 ^ { \circ }$ residual element phase error.

![](images/4a5dc10bb4ad9430ee86b3348104a098a2d27d25ec6f92f8dcb971a1dabaf3a6.jpg)

Fig.5 radiometric error due to element phase error, The residual phase error is largely depending on the length of averaging time slice for inter-element phase calibration. However, the time length cannot be arbitrarily extended due to the changing of objective image and instrument stability.After one hundred times of repeating experiments,the relationship between $\sigma _ { \Delta D }$ and averaging time is shown as Fig.6. $0 . 9 ^ { \circ }$ residual element phase error corresponds to 5min averaging time.

![](images/6c7a578d4029fd1ec2ccee3e9804f127ba5efba5c9754302b0a3ddb0ba83b786.jpg)  
Fig.6 residual element phase error after inter-element phase calibration

From Fig.5, the sensitivity to phase errors has been found to be $0 . 3 3 K / \mathrm { d e g }$ .However, it is know that the radiometric error is mainly contributed by phase errors in the shorter baselines due to the fact that it contains a larger amount of signal energy[17]．After this inter-element phase calibration, the residual baseline phase error is shown in Fig.7.It should be noticed that,the residual phase error is much better for short baselines because of the deliberate consideration in the final redundancy equations, which is important to reduce the radiometric error.

![](images/d59873bda5793c53971e43b3e0cf3592dd391a65b749a0577f13a3ee25030cdb.jpg)  
Fig.7 residual baseline phase error

# B.Field Image Calibration

A proof-of-concept demonstrator with 28 antenna/receiver units has already been achieved for GIMS advanced research[l1], as shown in Fig.8.It has the threshold system performance requirements proposed by application study,in which，the image refresh period is 5mins,and the radiometric accuracy is 1.5K.

Imaging tests had been conducted for some angularly small targets surrounded bycold sky at a far distance,which is beneficial to suppress aliasing effects.A chosen target is shown in Fig 9.

The reconstructed image without phase calibration is shown in Fig.1O(a). Improved imaging results have been reported in [6] by using an external point noise source for phase calibration. Here we reprocess the raw data by inter-element phase calibration approach. The reconstructed image is demonstrated in Fig.1O(b), compared with Fig.1O(a), the imaging is improved apparently.

![](images/0ffa35d88e0752a0b114c19aca11a73a87f523fb1a16a97ca0f93aad0c4b51ed.jpg)  
Fig.8 GIMS proof-of-concept demonstrator imaging of target   
Fig.9 optical

![](images/88995e9553e4fc8732b6ac0b69f77642daa6a081734c6b9b6c7237e5bf995c1c.jpg)  
Fig.1O (a) raw retrieved image (b) self-calibrated image

# V.CONCLUSION

The traditional phase calibration method of noise injection suffers from system complexity and excessive requirements on the calibration of noise injection network itself.In this paper, a new inter-element phase self-calibration method for rotation interferometric radiometers has been introduced,which uses the observation scene as reference without needing for extra hardware structure and auxiliary point source.

In the inter-element phase calibration approach,running average scheme is proposed to reduce the effect of noise and phase ambiguity is solved by preset-phase of very short baseline visibility. Simulation and experiments have been demonstrated that this method can effectively reduce system phase error.

As future work,some parameter in this new method should be optimized for GIMS and calibration precision should be further quantificational calculated for the evaluation of sensitivity.

# REFERENCES

[1] STAELIN D, GASIEWSKI A, KEREKES J,et al. Concept proposal for a GeostationaryMicrowave(GEM)Observatory.Preparedforthe NASA/NOAA Advanced Geostationary Sensor(AGS) Program,1998,23.   
[2]BIZZARRI B，GASIEWSKI A， STAELIN D. Initiativesfor millimetre/submillimetre-wavesoundingfromgeostationaryorbit; proceedings of the Geoscience and Remote Sensing Symposium,2002 IGARSS '02 2002 IEEE International,F2002,2002.   
[3] A.B.Tanner, et al.,“Initial Results of the Geostationary Synthetic Thinned Array Radiometer(GeoSTAR） Demonstrator Instrument,”IEEE Trans. Geosci.Remote Sens.,vol.45,no.7,pp.1947-1957,Jul 2007.   
[4] J.Christensen,A. Carlstrom, et al.,“GAS: the Geostationary Atmospheric Sounder,”in Proc.IGARSS,Barcelona, Spain,2007.   
[5] H.Liu,J.WU,et al.，“The Geostationary Interferometric Microwave Sounder(GIMS):instrument Overview and Recent Progress,”in Proc. IGARSS,Vancouver, Canada,2011.   
[6] C.Zhang,et al.,“Imaging Analysis and First Results of the Geostationary Interferometric Microwave Sounder Demonstrator,”IEEE Trans.Geosci. Remote Sens.,vol.53,no.1,pp.207-218,Jan 2015.   
[7] I. Corbella, et al.,“MIRAS end-to-end calibration: application to SMOS L1 processor,” IEEE Trans.Geosci.Remote Sens.，vol.43，no.5，pp. 1126-1134,May 2005.   
[8] M.A. Brown,et al.,“SMOS Calibration,”IEEE Trans.Geosci. Remote Sens.,vol.46,no.3,pp.646-658,Mar 2008.   
[9] F.Torres,et al.，“Analysis of Array Distortion in a Microwave Interferometric Radiometer:Application to the GeoSTAR Project,”IEEE Trans.Geosci. Remote Sens.,vol.45,no.7,pp.1958-1966,Jul 2007.   
[10] R.Jin,et al.,“An On-Board External Calibration Method for Aperture Synthesis Radiometer by Rotation,”IEEE Trans.Geosci.Remote Sens. Letters,vol.9,no.5,pp.901-905,Sep 2012.   
[11] I.Corbella,et al.,“The Visibility Function in Interferometric Aperture Synthesis Radiometry,”IEEE Trans.Geosci. Remote Sens.,vol.42,no.8, pp.1677-1682,Aug 2007.   
[12]I.Corbella,et al.,“Analysis of Correlation and Total Power Radiometer Front-Ends Using Noise Waves,”IEEE Trans.Geosci.Remote Sens., vol. 43, no.11, pp.2452-2459,Nov 2005.   
[13]R.Butora,“Fringe-washing function calibration in aperture synthesis microwave radiometry,”RADIO SCIENCE,vol.38,no.2,2003.   
[14] W.J.Fan,et al.,“Research ofFourier Phase in Optical Synthetic Aperture Imaging Technique,”Acta Optica Sinica,vol.24,no.3,Mar 2004.   
[15]Y.Zhang,H. Liu,J.Wu，et al.，“Target Brightness Temperature Simulation and Analysis for the Geostationary Interferometric Microwave Sounder(GIMS)"in Proc.IGARSS,Milan,Italy,2015,pp.3477-3480.   
[16] C.Zhang,et al.,“Applications of Pseudo-polar FFT in Synthetic Aperture Radiometer Imaging,”PIERS online,vol.3,no.1,2007

[17]F.Torres,A.B.Tanner,et al,“Robust array configuration for a microwave interferometric radiometer: Application to the GeoSTAR project,”IEEE Geosci.Remote Sens.Let.,vol.4,no.1,pp.97-101,Jan.2007.