# THE ALTIMETER PRECISION COMPARISON BETWEEN SAR MODE AND CONVENTIONAL MODE THROUGH AIRBORNE EXPERIMENT

Ke XUl, Peng LIUl,2, Lingwei SHIl, Lei WANG 1.2, Xiufen YUl lCAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing, China, 100190 2The Graduate Universityof the Chinese Academy of Sciences,Beijing, China,100049 xuke@mirslab.cn, liupeng@mirslab.cn, shilingwei@mirslab.cn, wanglei@mirslab.cn, yuxiufen@mirslab.cn

# ABSTRACT

Compared with conventional radaraltimeter(CRA), synthetic aperture radar altimeter (SARAL） is a new generation radar altimeter and has better height precision and spatial resolution.As using synthetic aperture technique, SARAL data processing is very different from CRA.To verify the performance and the processing algorithm,an airborne experimental system of SARAL is developed. The experimental system was installed in Y-12 aircraft,and a lot of data was obtained in the October 2014.The echo signal with SAR mode and conventional mode are obtained at the same time,so the standard deviations of the two modes are compared. The results indicate that the height precision of SARAL is improved about 1 times. The significant wave height value extracted from the SARAL waveform is very close to that of the buoy deployed at the experiment area.

IndexTerms—SARAL， CRA， heightprecision, airborne flight experiment

# 1.INTRODUCTION

SARAL (Also called Delay/Doppler altimeter, DDA) uses the synthetic aperture technique in along-track direction, so it is pulse-limited in across-track and beam-limited in alongtrack[1,2,3,4]. The new technique aims at reducing the measurement noise and increasing the along-track resolution in comparison with CRA[5]. Speckle reduction is obtained by increasing the number of observations.So the precision of the range, the significant wave height (SWH),and the wind speed become better compared with CRA.

In SARAL,a new waveform model [4] and new data processing methods are used.To verify the performance and the processing algorithm,an airborne experimental system of SARAL is developed. The system was installed in Y-12 aircraft with fixed wings,and a lot of data was obtained in the October 2014.

In the flight experiment, the conventional mode data can also be obtained simultaneously by extracting SAR mode

I/Q signal with 1:1O ratio. The measurement precision of the two modes can be compared.

In this paper, the height precision of SARAL,the design of the hardware,the data processing,and the experiment results are analyzed and discussed.

# 2.THEPRECISIONOFRADARALTIMETER

# 2.1.Spaceborne radar altimeter precision analysis

SARAL can provide better height parameter estimates [1, 2]. Using the instrument hardware parameters in Table 1,we can get the height precisions(Table 2) of SAR mode and conventional mode with 1s time resolution. So the height precision of SARAL is about1 times better than the CRA.

Table 1 The spaceborne instrument hardware parameters   

<html><body><table><tr><td>radarwavelength</td><td>2.2cm (Ku-band)</td></tr><tr><td>pulse bandwidth</td><td>320 MHz</td></tr><tr><td>antenna beamwidth</td><td>1.3 degree</td></tr><tr><td>burst rate</td><td>85 Hz</td></tr><tr><td>Pulse repeat frequency</td><td>18KHz</td></tr><tr><td>burst duration</td><td>11.7 ms</td></tr><tr><td>pulses per burst</td><td>64</td></tr><tr><td>pulse duration</td><td>51.2 μs</td></tr><tr><td>satellite velocity</td><td>7.5 Km/s</td></tr><tr><td>satellite height</td><td>800Km</td></tr></table></body></html>

Table 2 The spaceborne instrument range precision of the two modes   

<html><body><table><tr><td>SWH(m)</td><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>Mode CRA (cm)</td><td>0.92</td><td>1.11</td><td>1.35</td><td>1.59</td></tr><tr><td>SARAL (cm)</td><td>0.53</td><td>0.63</td><td>0.70</td><td>0.77</td></tr></table></body></html>

# 2.2 The main specifications and range precision of airborneradaraltimeter

To verify above performance and the data processing (introduced in Sec 4),an airborne experimental system of SARAL is developed. The main specifications of the hardware are the following:

Operation frequency: $1 3 . 5 8 \ : \mathrm { G H z }$ and 5.41 GHz   
·Peak RF power:1W   
·Pulse width: $1 2 . 8 ~ \mu \mathrm { s }$ Signal bandwidth: $3 2 0 / 8 0 / 2 0 ~ \mathrm { M H z }$ PRF: 5 KHz (for SARAL mode) $0 . 5 \mathrm { K H z }$ (for CRA mode) Antenna beam width: $2 5 ^ { \circ }$ Antenna gain: 17 dB Type of onboard tracker: OCOG AGC dynamic range: 60 dB Number of I/Q sample points: 256 Flight altitude: $3 6 0 0 \mathrm { m }$ Speed of flight: $2 5 0 \mathrm { K m / h }$

The range precision of CRA and SARAL is calculated with different SWH,and shown in Table 3(the time resolution is1 second).

Table 3 The airborne instrument range precision of the two modes   

<html><body><table><tr><td>MSWH(m)</td><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>CRA (cm)</td><td>2.51</td><td>2.62</td><td>2.91</td><td>3.16</td></tr><tr><td>SARAL (cm)</td><td>1.30</td><td>1.54</td><td>1.70</td><td>1.85</td></tr></table></body></html>

# 2.3.The SSHprecisionsoftheairbornealtimeter

SSH is an important parameter measured by radar altimeter. It should be corrected by atmospheric refraction corrections, external geophysical adjustments and sea-state bias etc. In this airborne flight experiment, the aircraft's flight height is about $3 6 0 0 ~ \mathrm { ~ m ~ }$ ，and the affect of the atmosphere and ionosphere can be ignored. Sea state and geophysical parameters are unchanged in the experiment area,so they can be ignored when comparing precision in the two modes.

The SSH precision contains two parts, introduced by the altimeter instrument and the flight orbit.The orbit location is determined by differential GPS.Since the orbit precision and instrument precision are independent of each other, the precision of SSH can be expressed as:

$$
\sigma _ { _ { S S H } } = \sqrt { \sigma _ { _ { A L T } } ^ { 2 } + \sigma _ { _ { G P S } } ^ { 2 } }
$$

Where $\sigma _ { S S H }$ is the precision of SSH, $\sigma _ { \scriptscriptstyle { G P S } }$ isthe precision of airplane locations, $\sigma _ { A L T }$ is the precision of range measured by the altimeter.

The precision of differential GPS is not a constant value at different position and attitude.In this experiment, the orbit radial precision of1 second is about $2 { \cdot } 4 ~ \mathrm { c m }$ ，so the final SSH precision is within a numerical interval (in Table 4).However in this experiment,the SAR mode and the conventional mode are measured at the same time,so the two modes have the same $\sigma _ { \scriptscriptstyle { G P S } }$ ．Since the $\sigma _ { \scriptscriptstyle A L T }$ of SAR mode is better than that of the conventional mode,the final $\sigma _ { S S H }$ of the SAR mode is also better than the conventional mode.

Using the data in Table 3 and the $\sigma _ { \scriptscriptstyle \mathit { G P S } }$ value, the $\sigma _ { S S H }$ is listed in table 4.The $\sigma _ { S S H }$ ratio of the conventional mode and the SAR mode are also calculated,and the ratio is within $1 . 1 { \sim } 1 . 3$ ：

Table 4 The analysis SSH precision of airborne instrument and the ratio of conventional mode and SAR mode.   

<html><body><table><tr><td>SWH(m) Mode</td><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>CRA(cm)</td><td>3.21 ~4.72</td><td>3.30 ~4.78</td><td>3.53 ~4.94</td><td>3.74 ~5.1</td></tr><tr><td>SARAL(cm)</td><td>2.38 ~4.2</td><td>2.52 ~4.29</td><td>2.62 ~4.35</td><td>2.72 ~4.4</td></tr><tr><td>Ratio</td><td>1.12 ~1.34</td><td>1.12 ~1.31</td><td>1.14 ~1.34</td><td>1.16 ~1.38</td></tr></table></body></html>

# 3.THEAIRBORNEALTIMETERHARDWARE DISCRIPTION

The airborne SAR altimeter hardware consists of antenna unit,microwave front-end, frequency synthesizer, solid power amplifier, transmitting unit, receiving unit, processing unit, and power supply unit.

In SAR mode, the altimeter transmits and receives signal at a fixed Pulse Repetition Frequency(PRF) of 5KHz. The instrument generates either C-Band or Ku-Band pulses (1 Cband pulse surrounded by $6 4 ~ \mathrm { K u }$ -band pulses as shown in Fig.1).It should be emphasized that the $6 4 ~ \mathrm { K u }$ -bandpulses are generated coherently in order to carry out azimuth resolutionenhancementbyDopplerfiltering.After deramping and digital filtering, the echo pulses are sampled by $2 5 6 \mathrm { ~ I / Q }$ points. The conventional mode data can be obtained by extracting SAR mode I/Q signal with1:10 ratio.

# 4.THESARALDATAPROCESSING

# 4.1.Data processing scheme

SARAL transmits chirp signal towards sea surface and then receive echo signal.After full deramp processing,the echo signal is sampled and stored along track in 2-D data matrix. The next step processing is along track Fourier Transform (AFFT),then the fan-beam sharpening in along track is performed. Before range compression，range correction is performed. The following step is Doppler position map and multi-look processing. Then we can get the SAR mode waveform.

# 4.2.The mean echo model of SARAL

The mean echo model of SARAL is the convolution of three terms[4,6,7],which are the average flat surface impulse response $P _ { F S }$ , the point target impulse response of the radar $S _ { r }$ , and the sea wave height probability density function $q _ { s }$ ：

$$
W ( f _ { { d c } } , \tau ) = P _ { { F S } } ( f _ { { d c } } , \tau ) * S _ { { r } } ( \tau ) * q _ { s } ( \tau )
$$

In the equation 2, the $f _ { d c }$ is frequency of fan-beam, $\tau$ is the two way travel time.

The average flat surface impulse response of the fan-beam corresponding to Doppler frequency could be described as:

$$
\begin{array} { c } { { P _ { F S } ( f _ { d c } , \tau ) = \displaystyle \frac { \sigma ^ { 0 } c \lambda ^ { 2 } } { \left( 4 \pi \right) ^ { 3 } L _ { p } 2 \kappa ( \Delta f ) ^ { 2 } h ^ { 3 } } } } \\ { { \displaystyle \cdot \int _ { 0 } ^ { 2 \pi } G _ { b } ( \tau , \Psi , f _ { d c } ) G ( \tau , \Psi , \xi , \Psi _ { 0 } ) d \Psi } } \end{array}
$$

where $c$ is the electromagnetic velocity, $L _ { p }$ is two-way propagation loss, $\Delta f$ is Doppler bandwidth, $\kappa$ is the orbital factor, $\xi$ and $\Psi _ { 0 }$ are the radar antenna pointing angle, $( \tau , \Psi , f _ { d c } )$ is the sharp fan-beam pattern, $G ( \tau , \Psi , \xi , \Psi _ { 0 } )$ is the antenna pattern.

# 4.3. Waveform retracking

Waveform retracking is the post processing to extract the parameters from the waveform. This paper uses the least squares algorithm to estimate the parameters of the multilook waveform.

# 5.THEEXPERIMENTRESULTS

The experiment results are given in this section. The top of Fig.2 shows the 2-D data after along track FFT as described at Sec 4.The bottom of Fig.2 is the echo after doppler correction.Fig.3 presents the waveforms of the two operating modes.Fig.4 illustrates the SSH values obtained in this experiment.The blue line is for the conventional mode, the green line is for the SAR mode,and the red line is for the model value. So the conventional results are more divergent than the SAR results,and that means the SAR altimeter has better precision.

Table 5 The airborne experiment SSH precision ratio of CRA and SARAL   

<html><body><table><tr><td>Data</td><td rowspan="2">Oct 30th</td><td rowspan="2">Oct 31th</td><td rowspan="2">Nov 1st</td></tr><tr><td>Mode</td></tr><tr><td>CR (cm)</td><td>3.89</td><td>4.52</td><td>3.99</td></tr><tr><td>SAR (cm)</td><td>3.04</td><td>3.67</td><td>2.92</td></tr><tr><td>CR/SAR</td><td>1.28</td><td>1.23</td><td>1.37</td></tr></table></body></html>

Table 5 gives the SSH precision ratio of the conventional mode to the SAR mode for three days.The ratios (1.28,1.23 and1.37) do agree with the analysis results in Sec 2.3.The similar results are also given in the literature [8].So we can see that the range precision of SAR altimeter is better than the conventional altimeter about1times.

The SWH value is also extracted from the SAR waveform and conventional waveform,and it is very close to that of the buoy deployed at the experiment area.

# 6.CONCLUSION

SARAL has the ability to reduce the measurement noise by increasing the number of observations (looks),and by which it can provide better geophysical parameter estimation. In this paper,an airborne experimental system of SARAL is developed to verify the performance and the processing algorithm of SAR altimeter. The results prove that the SARAL has the better performance than CRA.

# 7.REFERENCES

[1]R Keith Raney，“ The delay/doppler radaraltimeter,” Transactions on Geoscience and Remote Sensing,vol.36,no.5, pp.1578-1588,1998.

[2]JRobert Jensen and R Keith Raney，“Delay/Doppler radar altimeter: Better measurement precision,”in Geoscience and Remote Sensing Symposium Proceedings. IEEE,1998,vol. 4, pp. 2011-2013.

[3] Le Roy et al.,“Sral sar radar altimeter for sentinel-3 mission,” in Geoscience and Remote Sensing Symposium, 2007,pp.219- 222.

[4]Yang Shuang-Bao,Liu He-Guang,Xu Ke,and $\mathrm { { X u \ X i \mathrm { { - Y u } } } }$ “ The mean echo model and data process of sar altimeter,” in International Geoscience and Remote Sensing Symposium. IEEE, 2011,pp.2077-2080.

[5]AbderrahimHalimi,Corinne Mailhes,J-Y Tourneret,Francois Boy,and Thomas Moreau,“Including antenna mispointing in a semi-analytical model for delay/Doppler altimetry,’Transactions on Geoscience and Remote Sensing,vol.53,no.2,pp.598-608, 2015.

[6]Cristina Martin-Puig and Giulio Ruffini,“SAR altimeter retrackerperformance bound over water surfaces,"in International Geoscience and Remote Sensing Symposium.IEEE,20o9,vol.5, pp. V-449.

[7]LPhalippou and F Demeestere,“Optimal re-tracking of SAR altimeter echoes over open ocean: From theory to results for siral2,"Proc. OSTST Meet, pp.19-21,2011.

[8]Abderrahim Halimi,Corinne Mailhes,J-Y Tourneret,Pierre Thibaut,and Francois Boy，“ A semi-analytical model for delay/doppler altimetry and its estimation algorithm,”Geoscience and Remote Sensing,IEEE Transactions on,vol. 52,no. 7,pp. 4248-4258,2014.

![](images/30ee28d41b616dbd12f2cb31ac7c119bbc24a7019493b626bc2cc0da37c4477f.jpg)  
Fig.1 The timing sequence of SARAL

![](images/da1286dacb95bb1067fb95bf895f8acc403a2eb21af6290badf2d56f47e12653.jpg)  
Fig.2 The echoes before and after range correction

![](images/39ba4b3c0e7d47e6b62d9514962d7520bf2f251f25603a408cabb412b6a161bb.jpg)  
Fig.3 The echo waveformsof SARAL and CRA

![](images/7a46cf7c5483a4d758d2a56e5d69f3ed94e86607cd0595f97cd2c08441dd002f.jpg)  
Fig.4 The SSH values(blue is for conventional mode, green is for SAR mode, and the red is for the model value)