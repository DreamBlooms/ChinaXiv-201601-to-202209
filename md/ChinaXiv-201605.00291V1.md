# EPROCESSINGANDSIMULATIONOFTHECFOSATRFSCA Risheng Yun,Xingou Xu, XiaolongDong,Di Zhu

The CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences. e-mail:yunrisheng@mirslab.cn

# ABSTRACT

The RFSCAT(Rotating Fan-beam SCATterometer） is one of the two payloads of CFOSAT,the China-France Oceanography Satellite.It is a radar scatterometer designed to measure the electromagnetic back-scatter from wind roughened ocean surface.The operating frequency of the scatterometer is 13.256GHz (Ku-band) and has a swath about 1,Ooo kilometers．In this paper，based on the characteristics of echo signal of RFSCAT,the on-board processing ofRFSCAT signal is introduced.A Doppler precompensation LUT and A slice division LUT are developed, and the signal processing algorithms are validated and the wind retrieval performances ofRFSCAT are analyzed based on the well-developed data simulation system of CFOSAT RFSCAT.

IndexTerms—CFOSAT， RFSCAT， on-board processing,simulation,wind retrieval.

# 1.INTRODUCTION

A frequency pre-shift LUT for transmiting signal by shifting central frequency of transmitting signal is used for narrowing the echo bandwidth and the tradeoff between the complexity of onboard signal processing implementation and accurate Doppler compensation is considered,and the residual Doppler frequency shift compensation and slice division processing onboard are combined into one step to implementviaawell-designed1-DLUT.The latitude and elevation dimensions are neglected and only the azimuth dimension is reserved by optimization in this processing.

The CFOSAT RFSCAT instrument uses two parallel, rotating slotted-waveguide array antennas with two fan beams corresponding to vertical and horizontal polarization that scanns in a conical pattern[1,2]. The operating frequency of the scatterometer is 13.256GHz (Ku-band) and has a swath about 1,OoO kilometer，which is centered on the spacecraft's nadir subtrack and covering about $90 \%$ of Earth's surface each day. The RFSCAT produces large overlaps on the observation regions within the total swath bysuccessive sweeps and provides a large number of sigmaO acquisitions with diverse azimuth and elevation combinations for a single surface resolution cell.It is expected to acquire frequent global coverage and high quality wind acquisitions[3].

A data simulation system of CFOSAT RFSCAT is developed for signal processing algorithm validation and performance analysis.Unlike the end-to-end theoretical simulation model,which is independent of hardware system realization of scatterometer and suitable for the system design phase and theoretical performance analysis; the new simulation system considered the actual CFOSAT RFSCAT onboard processing such as Doppler frequencyshift compensation and slice division.Meanwhile,the orbit parameters and propagation are also well considered. The SGP4/SDP4 orbit propagation model is used for pulse and cell observation geometry computation. The input could be simulated randomwind orECMWFNWPwind.Taking the pseudo-L1B data as the main output simulation data,the CFOSAT RFSCAT dataprocessingalgorithmsare developed and optimized.Based on the simulation system, the distance between ground slices after dimension reduction processing of slice are provided; and the Kpc coefficients of slices are computed and compared with approximate method.With the random input wind field, the 1 revolution dataofRFSCAT was simulated,and the wind speed bias and wind direction rms error are provided.

# 2.ON-BOARDPROCESSINGOFRFSCATSIGNAL

Unlike QuikSCAT and ASCAT scatterometers,the Doppler effects ofRFSCAT introduced byrelative motion between the scatterometer and the earth with its rotation are 3-D coupling distributions varying with latitude position of the satellite,as well as the azimuth and elevation of the resolution cells[4]. Improper Doppler processing will cause serious received signal frequency deviations which will effect onboard data accumulation,slice division and the product quality of retrieved wind fields.

Doppler frequency effects of RFSCAT are induced by relative movement between scatterometer platform and earth and the rotation of the earth.Figure 1 is the Doppler frequency shift distribution and residual Doppler frequency shift distribution of CFOSATRFSCAT,where the solid line denotes the beam far-end (outer part) and the dotted line denotes the beam near-end(Inner part) respectively,and two curves in the same color denote the same latitude interval.It can be shown that the Doppler frequency shift is significant determined jointly by azimuth angle,latitude and elevation direction.In elevation direction,the maximum values in beam near end are about $\pm 2 0 0 \mathrm { k H z }$ ,and the maximum values in beam far end are about $\pm 5 0 0 \mathrm { k H z }$ .In addition,for a specific azimuth angle, the Doppler shift difference between latitude intervals could be above $2 0 0 \mathrm { k H z }$ ：

![](images/6ddc29cf2a583f8832df9242e4609b06568f8204e0abbb7c6933a58aa796eed2.jpg)  
Figure 1:The Doppler frequency shift distribution and residual Doppler frequency shift distribution of CFOSAT RFSCAT(a) the Doppler frequency shift distribution of ascending orbit; (b) the Doppler frequency shift distribution of descending orbit;(c) the residual Doppler frequency shift distribution of ascending orbit;(d) the residual Doppler frequency shift distribution of descending orbit. The solid lines denote the beam far-end; the dotted lines denote the beam near-end. The red lines denote the [-85,-75] degree latitude interval; the green lines denote the [-5,5] degree latitude interval; the blue lines denote the[75,85] degree latitude interval.

Pre-compensation byshiftingcentral frequencyof transmitting signal is used for compensating the mean Doppler with reference to antenna azimuth direction.The pre-compensation values are the averaged Doppler in elevation and latitude dimensions with opposite sign(64 azimuth angle bins are adopted). It can be shown in figure 1 that the residual Doppler shift after pre-compensation is reduced to about $[ - 2 0 0 , 2 0 0 ] \mathrm { k H z }$

The transmitted pulse of RFSCAT is linear-frequency modulated chirp signal, the echoes are deramped by mixing with a chirped reference signal after digital downconversion to intermediate frequency (IF)[5.6]. To extract the range information,anFFT isperformed on the filtered signal and a periodogram is implemented by applying a magnitude squared operation.The effective bandwidth of deramped signal is about $5 0 0 ~ \mathrm { k H z }$ ，The sampling rate is less than $1 . 5 \mathrm { M H z }$ ，a 4096-FFT will be adopted to extract the range information from the deramped signal,and the final bins are summed into 40 energy slices for downloading.In the onboard processing chain,aDoppler compensationmodule is needed to control the frequency characteristic of the reference signal, so the center frequency of deramped signal will accord with the band-pass filter[7].

In order to extract the range information accurately and to implement appropriate accumulation processing of 4096 points in a pulse according to the approximate equal slice size on the ground,the residual Doppler frequency shift should be compensation carefully.However, the onboard processing complexity will be increased dramatically if the residual Doppler frequency shift is compensated completely. Figure 2 is the 3-D LUT dimension reduction and slice division diagram. After Doppler frequency shift precompensation, the echo frequency per pulse is computed. In order to optimize receiving,the sign ofchirp rate is changed for forward and backward azimuth scan (the sign of chirp rate is negative for [O,18O) degree azimuth angle, the sign is positive for[180,360] degree azimuth angle).The frequencies of equal ground slice size are obtained by spline interpolation according to the corresponding relationship between echo frequency and elevation angles and 3-D slice division LUT is obtained with respect to azimuth angle, latitude and elevation direction.An optimalLUT dimension reduction processing is adopted,and then the slice division is conducted on pulse echo power.In the LUT dimension reduction processing,fora specific azimuth angle bin,the accumulation point boundary of 1-D LUT is determined to ensure all the points in 3-D LUT are included and the accumulation slope of 1-D LUT is adjusted accordingly based on all the latitude accumulation slopes.

![](images/7b2ad1eb809d617ab5167e494bd95ba49699eae62c7ad4a23435abe1419018ed.jpg)  
Figure 2:3-DLUT dimension reduction and slice division diagram

The 3-DLUT dimension reduction and 1-D LUT-based slice division processing bring about the significant improvement of onboard processing complexity.On the other hand,because the existence of residual Doppler shift and the use of simplified 1-D LUT,the slice size on the ground couldn't be equal completely,and usually not all the downloaded 40 points per pulse stand for the approximate equal size slices.Generally,the effective downloaded point numbers corresponding to the slice numbers are between 25 and 35.Considering the low SNR and possible echo energy leakage，some marginal slices should be discarded for sigmaO extraction.The alterable resolution slices couldn't beavailableforCFOSATRFSCAT.

# 3.SIMULATIONANDPROCESSING OFRFSCATDATA

A data simulation system of CFOSAT RFSCAT is developed for data processing algorithm validation and performance analysis.Unlike the end-to-end theoretical simulation model,whichisindependent of hardware system realization of scatterometer and suitable for the system design phase and theoretical performance analysis; the new simulation system considered the actual CFOSATRFSCAT onboard processing such as Doppler shift compensation and slice division.SGP4/SDP4 orbit propagation model is used for generation of the platform status vector and FRSCAT observation geometry.After the positions of ground WVCs are determined, the observation geometry of every pulse is computed.The pre-compensation LUT and slice division LUT are read in and the positions of slices,the X-factor and Kpc coefficients are computed.After the pseudo level 1B data is produced, the sigmaOs of WVCs are generated and the wind retrieval and performance analysis are conducted. The wind retrieval and performance analysis module could accept both the simulated random wind field and external wind field such as ECWMF wind as input data.The MLE wind retrieval and median-filter-based ambiguity removal algorithm are adopted in the RFSCAT simulation system.

The orbit parameters and system parameters of CFOSAT RFSCAT are listed in table 1．In this paper,only 1 revolutionof $2 5 \mathrm { k m }$ resolution simulated scatterometer pseudo level 1B data is simulated and used for performance analysis.In the simulation,the value of normalized standard deviation of calibration error Kpr is set to $0 . 2 \mathrm { d B }$ . NSCAT-2 GMF is used for simulation and wind retrieval,and the normalized standard deviation of themodel erroris computed as

$$
\dot { K _ { p m } } = \left\{ \begin{array} { l l } { { \left( 0 . 0 1 3 9 W ^ { 2 } - 0 . 0 3 8 1 W + 0 . 2 7 5 3 \right) \cdot \sqrt [ 3 ] { \frac { r } { 5 0 } } } } & { { \quad W \leq 1 5 } } \\ { { 0 . 0 1 } } & { { \quad W > 1 5 } } \end{array} \right.
$$

Where, $W$ is wind speed (unit is $\mathrm { m / s }$ ）, $r$ is the resolution (unit is km).

Kpc defined as the normalized standard deviation of the echo is used to indicate the magnitude of the measurement variations due to the instrument thermal noise and radar signal fading effects.Kpc coefficients are functions of the instrumentantennapattern,illuminationgeometry, modulation format, transmit pulse modulation,and receiver filter characteristics.

Figure 3 is the slice sizes on the ground for different azimuth angle.It is showed that most of the slice sizes on the ground approximately equals to $1 0 \mathrm { k m }$ 、The slice with bigger size usually lies on the position far from beam center, especially for azimuth angle is O degree or l8O degree,and the slice size could be greater than $1 5 ~ \mathrm { k m }$ In Figure 4, the Kpc coefficients of RFSCAT are provided and the compare between the Kpc coefficients derived from the analytical

Table1 The orbit parameters and system parameters of CFOSAT   

<html><body><table><tr><td colspan="2">CFOSAT Orbit Parameters</td><td colspan="2">CFOSAT system parameters</td></tr><tr><td>Semi major (km) 1</td><td>6891.984</td><td>Transmit power (W)</td><td>120</td></tr><tr><td>Eccentricity</td><td>0.00123</td><td>Carrier frequency (GHz)</td><td>13.256</td></tr><tr><td>Inclination (deg.)</td><td>97.464</td><td>Pulse width (ms)</td><td>1.35</td></tr><tr><td>Aargment fpgrige</td><td>90</td><td>PRF (Hz)</td><td>75</td></tr><tr><td>Descending time</td><td>7:00 PM</td><td>TranswitsigMHz)</td><td>0.5</td></tr></table></body></html>

![](images/1559663287e0260af8523256af1062627e85fb6d3ad0f9579735940c93cb03ed.jpg)  
Figure 3:Slice sizes on the ground for different azimuth angle.The dash dotted line is minimum slice size on the ground w.r.t 40 downloaded points; the dotted line is maximum slice size on the ground; the solid line is the averaged slice size on the ground w.r.t specific slice.For the convenience ofaveraging,not all the slices are showed.(a） The slice sizes ofO degree azimuth angle.(b) The slice sizes of 90 degree azimuth angle.(c) The slice sizes of 18O degree azimuth angle.(d) The slice sizes of 270 degree azimuth angle.

![](images/e1439d1dc40a27e4d522a77eaebd3736de480902ed411a322b2872b82c223c6d.jpg)  
Figure 4:The Kpc coefficients for different azimuth.The red line denotes the coefficient A; the green line denotes the coefficient B;and the blue line denotes the coefficient C.The dotted lines stand for the coefficients obtained by approximate formula; the solid lines stand for the coefficients obtained by analytical formula.(a)The Kpc coefficients of O degree azimuth angle.(b) The Kpc coefficients of 90 degree azimuth angle.(c) The Kpc coefficients of 18o degree azimuth angle.(d) The Kpc coefficients of 270 degree azimuth angle.

formula and those derived from the approximate formula. The approximate formula used for Kpc computation is

$$
\begin{array} { c } { A = \displaystyle \frac { 1 } { B _ { s } \tau _ { p } } } \\ { B = \displaystyle \frac { 2 } { B _ { s } \tau _ { g } } } \\ { C = \displaystyle \frac { 1 } { B _ { s } \tau _ { g } } } \end{array}
$$

Where, $B _ { s }$ is measurement bandwidth of slice, $\boldsymbol { \tau } _ { p }$ is transmit pulse width, $\tau _ { g }$ is the receiving window width.

Form figure 4,we find that the values between the Kpc coefficients derived from the analytical and that derived from approximate is very close.For CFOSAT RFSCAT,in most situations,the Kpc coefficients could be computed by approximate formula,which dramatically improves the computing efficiency.

![](images/848314af1b01ab36f06257b221aefd1ae179e282d9db544bded4981ebdcac731.jpg)  
Figure5:The wind retrieval performance estimation of CFOSAT RFSCAT. (a)is the averaged wind speed bias on different wind speed interval; (b) is the averaged wind direction rms error on different wind speed interval.

Figure 5 is the wind retrieval performance estimation of CFOSAT RFSCAT.From figure 5(a),we find that the wind speed bias is greater at nadir and outer part of the swath than that of inner part of swath.Generally,the wind speed bias increases with the increasing of wind speed. The maximum averaged wind bias is about $2 . 5 \mathrm { m / s }$ which corresponding to the [15,24] $\mathrm { m / s }$ wind speed interval. Consistent with wind speed bias,the wind direction retrieval performance is also deteriorated at nadir and outer part of the swath.On the contrary,the wind direction rms error decreases with the increasing of wind speed.The averaged wind direction rms error on wind speed interval[8,15) $\mathrm { m / s }$ and [15,20) $\mathrm { m / s }$ are almost below 2O degree.For wind speed interval $[ 0 , 4 ] ~ \mathrm { m / s }$ ，the wind direction rms error on inner WVCs is close to 4O degree,and the wind direction rms error of nadir WVCs is about 60 degree.

The Doppler effects of CFOSAT RFSCAT are 3-D coupling distributions.A frequency pre-shift LUT is used, and the residual Doppler frequency shift compensation and

# 4.SUMMARY ANDCONCLUSION

slice division processing onboard are combined into one step to implement via a well-designed 1-D LUT.The latitude and elevation dimensions are neglected and only the azimuth dimension is reserved in this processing.A data simulation system of CFOSAT RFSCAT considering the actual CFOSAT RFSCAT onboard processing such as Doppler shift compensation and slice division is developed for signal processing algorithm validation and performance analysis.Based on the simulation system,the slice size on the ground after dimension reduction processing of slice are proposed; and the Kpc coefficients of slices are computed and compared.With the random input wind field,the 1 revolution data of RFSCAT was simulated,and thewind speed bias and wind direction rms error are provided.

Slice sizes on the ground shows that the on-board Doppler compensation and slice division processing perform well for CFOSAT RFSCAT,which obtain optimal tradeoff between the demand of subsequent data processing and the complexity of on-board signal processing.For CFOSAT RFSCAT,in most situations,in order to improve the processing efficiency, the approximate Kpc coefficients could be used,rather than analytical formula.Based on the well-developed simulation system，the echo signal and downloadeddataofCFOSATRFSCAT areobtained,and the wind retrieval performance is estimated.The statistics of wind speed bias and wind direction rms error show that the CFOSAT RFSCAT could provide high quality wind acquisitions.Furthermore,the wind retrieval performance could be improved by algorithm optimization in the future.

# 5.REFERENCES

[1]XiaolongDong,Di Zhu,Jintai Zhu and Tao Wang,“Progress of Development of CFOSAT Scatterometer”,Proceedings of IGARSS'2012,pp.237-240,2012.   
[2] Xiaolong Dong,Daozhi Liu,Jintai Zhu,Di Zhu,and Wenming Lin,“Some Consideration of In-orbit Calibration of Spaceborne Rotating Fan Beam Radar Scatterometer,Proceedings of   
IGARSS'2011,pp.965-968,2011.   
[3] Chung-ChiLin,BjornRommen,J.J.W.Wilson,et al.,“An AnalysisofaRotating,Range-Gated,Fanbeam Spaceborne   
Scatterometer Concept",IEEE Trans.Geosci. Remote Sensing, 38(5),2114-2121, Sep.,2000.   
[4]Risheng Yun,XiaolongDong,Di zhu,Xinou Xu,CFOSAT Scatterometer Doppler processing and Data Development,   
IOVWST2014,Brest,France   
[5] Risheng Yun,Xiaolong Dong,Di Zhu,Wenming Lin,RealTime Signal ProcessingDesign For Spaceborne Rotating,FanBeamScatterometer,EUMETSAT/ESAScatterometer Science Conference 2011,Darmstadt,Germany,April,2011.   
[6] Di Zhu,Lei Zhang,Xiaolong Dong,Xing-ou Xu, Zhongguo Song,Shuyan Lang and Shaobo Wang,“Airborne Experiments Validating the Spaceborne RFSCAT on CFPSAT",Proceedings of IGARSS'13,pp.1673-1675,2013.   
[7] Di Zhu, Xiaolong Dong,Wenming Lin,Risheng Yun,Doppler effect and compensation ina Rotating Fanbeam Spaceborne   
Scatterometer,ProceedingsofIGARSS'2010IEEEInternational, July,Hawaii