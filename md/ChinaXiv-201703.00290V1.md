# DECONVOLUTION METHODFOR RESOLUTION ENHANCEMENT OFDUALFREQUENCYPOLARIZEDSCATTEROMETER

Liling Liul² Xiaolong Dong' Jintai Zhu³ Di Zhu'

1. The CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing 100190, China 2. University of Chinese Academy of Sciences, Beijing 100049, China 3.DFH Satellite co., Ltd, Beijing,100094, China

# ABSTRACT

Dual-Frequency Polarized Scatterometer (DFPSCAT） is a new system utilizing Doppler beam sharpening (DBS) technologyforazimuthalresolutionenhancement. Considering the DBS technology is inapplicable for the middle areas of the swath，a theoretical framework of deconvolution signal processing is proposed to improve resolution. A deconvolution method of the nonlocally centralized sparse representation (NCSR）is adopted to verify its feasibility,and simulation results show that the deconvolution method have obviously better resolution enhancement and higher recovery accuracy than these of the classical scatterometer image reconstruction(SIR) method.

Index Terms—DFPSCAT，resolution enhancement, deconvolutionmethod

# 1.INTRODUCTION

A scatterometer is a radar device that collects normalized radar backscatter $( \sigma ^ { 0 } )$ measurements over the earth. Scatterometer is originally intended to measure near-surface wind vector over the ocean.Due to its frequently global coverage,it is also a desirable candidate for land and ice applications,in which the improvement of spatial resolution is the key issue.The pencil-beam scatterometers are realaperture systems and employ the range-gate discrimination to enhance the slant resolution;nevertheless,the resolution in the azimuth direction is limited by the antenna beamwidth The limitation has been overcome partially with the advent ofscatterometer image reconstruction (SIR） algorithm, which has been successfully utilized to detect polar sea ice extent, track icebergs and other applications [1].However, the resolution is still too coarse for many geophysical applications， such assnowwater equivalent(SWE) estimation.In this situation, spatial resolution is desired to be $1 { - } 5 \mathrm { k m }$ [2].

To achieve the desired spatial resolution,the Doppler Beam Sharpening (DBS) technology together with the pulse compression technology are adopted for the dual frequency polarized scatterometer(DFPSCAT） onboard the Water CycleObservationMission(WCOM)satellite[3]. DFPSCAT is a pencil-beam scatterometer employing a $1 . 5 \mathrm { m }$ dish antenna operating at 9.6 and 17GHz for SWE measurement and frozen thorn detection.However, the DBS is inapplicable for the middle areas of the swath where the azimuth resolutionislimitedby the antenna beamwidthand it is about a few tens kilometers.Respecting the low resolutionofthemiddleswathofDFPSCAT，the deconvolution signal processing method is explored to settle the problem.

The paper establishes a scatterometer measurement model,and proposes a new surface $\boldsymbol { \sigma } ^ { 0 }$ grid definition convenientforsolvingthemodelthroughsome deconvolution methods. A deconvolution algorithm of nonlocally centralized sparse representation (NCSR）is utilized to realize the resolution enhancement. Some simulations are carried out to verify the feasibility. The results show that the proposed framework has obvious resolution improvement than that of the well-founded SIR processing.

# 2.MEASUREMENTMODELFORDFPSCAT

# 2.1.Measurement model

![](images/3301e4b4395dcd6d4c952f1af0b49e6b116e7e8d425ebecff867272e2f4504f5.jpg)  
Fig.1DFPSCAT measurement geometry

Figure 1 shows the DFPSCAT measurement geometry.The antenna beam is conically scanning around the nadir axis with the predesigned rotating speed at a constant incidence angle $\theta$ ，The measurement power $P _ { r }$ from a transmitted pulse equals the sum of the backscattered signal power $P _ { s }$ and the noise power $P _ { n } ,$ which is introduced by thermal noise in the receiver,radiometric noise and speckle.The power reflected from the surface is

$$
P _ { s } = \frac { P _ { t } \lambda ^ { 2 } } { \left( 4 \pi \right) ^ { 3 } L } { \int _ { A } \frac { G ( \vec { \nu } ) ^ { 2 } \sigma ^ { 0 } \left( \vec { \nu } \right) } { R ( \vec { \nu } ) ^ { 4 } } d \vec { \nu } }
$$

where $\boldsymbol { P } _ { t }$ is the transmitted power, $\lambda$ is the wavelength, $L$ is the system loss, $G$ is the antenna gain, $\boldsymbol { \sigma } ^ { 0 }$ denotes the true normalized radar backscatter of the earth's surface, $R$ is the slant range,and $A$ is the area illuminated by the antenna, $\nu$ represents a defined coordinate system.

Using the radar equation,a weighted spatial average of ${ \boldsymbol { \sigma } } ^ { 0 } , { \boldsymbol { \bar { \sigma } } } ^ { 0 }$ , is derived as

$$
\overline { { \sigma } } ^ { 0 } = \frac { P _ { s } } { X } = \int _ { A } h ( \vec { \nu } ) \sigma ^ { 0 } ( \vec { \nu } ) d \vec { \nu }
$$

where $X = \frac { P _ { t } \lambda ^ { 2 } } { \left( 4 \pi \right) ^ { 3 } L } { \int _ { A } \frac { G ( \vec { \nu } ) ^ { 2 } } { R { ( \vec { \nu } ) } ^ { 4 } } d \vec { \nu } }$ ,isthe calibration factor,and $h$ represents the spatial response function (SRF) defined by

$$
h { = } \frac { G ( \vec { \nu } ) ^ { 2 } } { R ( \vec { \nu } ) ^ { 4 } } { \Bigg / } { \int _ { A } } \frac { G ( \vec { \nu } ) ^ { 2 } } { R ( \vec { \nu } ) ^ { 4 } } d \vec { \nu }
$$

Generally, $P _ { s }$ is estimated through subtracting $P _ { n }$ which is measured by the noise-only channel from $P _ { r }$ Besides, the calibration error resulting from the uncertainty of radar system parameters also introduces errors between $\overline { { \sigma } } ^ { 0 }$ and measured $\hat { \sigma } ^ { 0 }$ . The total errors $\scriptstyle n = { \hat { \sigma } } ^ { 0 } - { \overline { { \sigma } } } ^ { 0 }$ is characterized by the scatterometer noise model, i.e. $n \bigstar \bigstar \bigstar \bigstar \bigstar \bigstar \bigstar$ ，where $K _ { p }$ is the normalized standard deviation of $\hat { \sigma } ^ { 0 }$ .Then，we obtain the following scatterometer measurement model.

$$
\hat { \sigma } ^ { 0 } = \overline { { { \sigma } } } ^ { 0 } + n = \int _ { A } h ( \vec { \nu } ) \sigma ^ { 0 } ( \vec { \nu } ) d \vec { \nu } + n
$$

# 2.2.Surface $\pmb { \sigma } ^ { 0 }$ grid

In the above measurement model, the observed $\hat { \sigma } ^ { 0 }$ is made withasampled apertureapproach inwhichthe measurements are spatially filtered surface $\boldsymbol { \sigma } ^ { 0 }$ data sampled over a two-dimensional (2-D) grid.

Typically,the 2-D grid is defined as a uniform grid takes the along track and cross track direction of satellite as coordinate axis [4]. Fig.2 depicts the typical grid definition, where $r$ is a distance from nadir point to center of SRF,and the azimuth angle $\varphi$ denotes the instantaneous scan position of the antenna beam. Fig.3 illustrates three SRF $h$ at $\varphi = 7 7 ^ { \circ }$ $8 3 ^ { \circ }$ ， $9 0 ^ { \circ }$ ,respectively.Note that $h$ varied with each rotation location. $\hat { \sigma } ^ { 0 }$ is not equal to a convolution operation of a fixed $h$ and $\boldsymbol { \sigma } ^ { 0 }$ ，and thus some existing deconvolution method arenot available for the case.

![](images/a0a3d2f56a3166cb04200af561305b63a908d2fe50f49dba614c2f9e1fb3990d.jpg)  
Fig.2 Typical grid definition

![](images/72f09a2300aad5052666201488223a39a8e0b8432b5a93310910ee83c758ff3a.jpg)  
Fig.3 Anillustration of SRF for several antenna rotation angle.

To settle the problem， we proposed a new grid definition. The new grid is composed of iso-range lines and the iso-azimuth lines that the beam boresight line projected on the surface，as shown in Fig.4.Fig.5 depicted the corresponding $h$ with the same locations as Fig.3,and $h$ is almost same for varied scan angle.In the case,the measured data $\hat { \sigma } ^ { 0 }$ is equivalent to the regularly sampling of surface $\boldsymbol { \sigma } ^ { 0 }$ convolved with a fixed $h$ ,that is

$$
\hat { \sigma } ^ { 0 } = h \otimes \sigma ^ { 0 } + n
$$

where $\otimes$ denotes the convolution symbol.

![](images/f7905093973b834725caaf89b31422030fc2d461ee7583e9accbbbfe28f262fd.jpg)  
Fig.4 A new grid definition

![](images/7989dec377f1c602bcbd0a5dad673ad7442c8da4e50705c139a5880129315e3a.jpg)  
Fig. 5 An illustration of SRF in the new grid at azimuth angle as Fig. 3

# 3.DECONVOLUTIONMETHOD

Typically, the DFPSCAT backscatter return from each pulse of each beam is partitioned into several “slices”using range gateprocessing.Assuming each slice isstatistically independent and has its own slice spatial response function. Based on the above proposed 2-D grid, the slice spatial response function is fixed for measurements.Then，the measured $\hat { \sigma } ^ { 0 }$ corresponds to each slice can be written as

$$
\hat { \sigma } ^ { 0 } = h _ { s } ^ { k } \otimes \sigma ^ { 0 } + n , k = 1 , 2 \cdots m
$$

where $m$ is the slice number and $h _ { s } ^ { k }$ represents the spatial response function for $k$ th slice,. Using multiple overlapping slice measurements,the surface $\boldsymbol { \sigma } ^ { 0 }$ field is reconstructed through the deconvolution method.

Due to the ill-posed nature of deconvolution problem, the regularization-based techniques are used to regularize solution spaces. Since the classic regularization models like Tikhonovregularizationandthetotalvariant(TV) regularization result in over-smooth solutions,the recent sparsity-based regularization used in image restoration is the optimal alternative.In the paper, the nonlocally centralized sparse representation (NCSR） model proposed by Dong is adopted to solve Eq.(6） [5]. Specifically，the highresolution $\tilde { \sigma } ^ { 0 }$ is obtained through

$$
{ \tilde { \sigma } } ^ { 0 } = \arg \operatorname* { m i n } _ { \sigma } \left\{ \left\| { \hat { \sigma } } ^ { 0 } ( \varphi ) - h _ { s } ^ { k } \otimes \sigma ^ { 0 } \right\| _ { 2 } ^ { 2 } - \sum _ { i } \left\| \alpha _ { i } - \beta _ { i } \right\| _ { 1 } \right\} ,
$$

$$
s . t . \sigma ^ { 0 } = D \circ \alpha
$$

where $\beta _ { i }$ is defined as the weighted average of $\alpha _ { i }$

Let $\sigma _ { i } ^ { 0 } = P _ { i } \sigma ^ { 0 }$ be a patch extracted at position $i$ $( i = 1$ $2 , . . . , N )$ ，where $P _ { i }$ is the patch extraction operator and $N$ is the number of pixels in the $\boldsymbol { \sigma } ^ { 0 }$ . Given a dictionary $D$ ，the patch $\boldsymbol { \sigma } _ { i } ^ { 0 }$ can be sparsely encoded over $D$ and result in a sparse coding vector $\alpha _ { i }$ . Once the coding vectors of all $\boldsymbol { \sigma } ^ { 0 }$ patches are obtained, the whole $\boldsymbol { \sigma } ^ { 0 }$ can be reconstructed by

$$
\scriptstyle \sigma ^ { 0 } = D \circ \alpha \operatorname { \bigtriangledown } \left( \sum _ { i = 1 } ^ { N } P _ { i } ^ { T } P _ { i } \right) ^ { - 1 } \sum _ { i = 1 } ^ { N } P _ { i } ^ { T } D \alpha _ { i }
$$

where $\alpha$ is the concatenation of all $\alpha _ { i }$ ．More detailed explanations on NCSR can be found in [5].

# 4.PERFORMANCEANALYSIS

To verify the feasibility of NCSR deconvolution method for scatterometer resolution enhancement,some simulations are carried out.In the simulation, the slice response function contours are approximately 1km in the range direction and 16km in the azimuth direction. The azimuth-sampling interval is set as 1km.In the paper, $K _ { \mathrm { p } }$ is assumed as $0 . 5 \mathrm { d B }$

At first,a synthetic $\boldsymbol { \sigma } ^ { 0 }$ field reconstruction was taken as an example for performance investigation. For the $\boldsymbol { \sigma } ^ { 0 }$ field over the proposed 2-D grid， the left squares are $1 \mathrm { k m } \times 1 \mathrm { k m }$ in size and spaced $2 \mathrm { k m }$ apart, the right square is $2 \mathrm { k m }$ width,and the width of the narrow lines and broad ones correspond to $1 \mathrm { k m }$ and $2 \mathrm { k m }$ ，respectively.For comparison, the measurement $\hat { \sigma } ^ { 0 }$ and the reconstructed $\tilde { \sigma } ^ { 0 }$ after SIR algorithm are shown.

Figure 6 shows the simulation results for DFPSCAT resolution enhancement.As expected, the reconstucted $\tilde { \sigma } ^ { 0 }$ after SIR is excessively smooth and seriously spread out. The result of the proposed deconvolution algorithm has the most obvious resolution enhancement; nevertheless,it tends to more noise amplification compared with the others.

To future investigate the processing accuracy， the horizontal cut of values extracted from Fig. 6 across the top row of spots is analyzed,as shown in Fig.7.It is apparent that the proposed deconvolution method can reconstruct the truth signal with highest accuracy.

![](images/36146e20d1129f4b2b928cf56c28b69fd579b30abc5aac263483ee2563e0a993.jpg)  
Fig.6 Simulation results for DFPSCAT resolution enhancement (a) synthetic $\boldsymbol { \sigma } ^ { 0 }$ field (b) measurement (c) SIR reconstruction (d) NCSR deconvolution

![](images/6a47dbecc8c9d9e0a26e721e32d13179262d97e1f523a78ea2f07583ca332231.jpg)  
Fig. 7 Plot of $\boldsymbol { \sigma } ^ { 0 }$ values extracted from top row of Fig. 6

Second, a real $\boldsymbol { \sigma } ^ { 0 }$ field reconstruction is implemented for further validation.The $\boldsymbol { \sigma } ^ { 0 }$ field is obtained by a SWE forward model of DMRT-QCA [6] with SWE distribution data centered at $4 9 ^ { \circ } \mathrm { N }$ ， $1 1 5 ^ { \circ } \mathrm { W }$ with areas of $2 ^ { \circ } { \times } 2 ^ { \circ }$ for February 29 in 2OO4,where the SWE distribution data is acquired from Snow Data Assimilation System [7]. The reconstruction results are displayed in Fig.8.Itis noted that the NCSR deconvolution methods discriminates the edge areas clearly and preserves more detail information.Overall, the deconvolution method produces the more obvious resolution enhancement and higher recovery accuracy compared with the classical SIR processing.

![](images/9e9906509b7fc14c18e94564eeea5c37263bb05f3b484806369f7d6da729b127.jpg)  
Fig. 8 Real $\boldsymbol { \sigma } ^ { 0 }$ field reconstruction (a) real $\boldsymbol { \sigma } ^ { 0 }$ field (b) measurement (c) SIR reconstruction (d) NCSR deconvolution

# 5.CONCLUSION

Thispaperintroducesadeconvolutiontheoretical framework for scatterometer $\boldsymbol { \sigma } ^ { 0 }$ resolution enhancement,in which the slice measurement model of scatteometer is established based on a new defined 2-D surface $\boldsymbol { \sigma } ^ { 0 }$ grid. A deconvolution algorithm of nonlocally centralized sparse representation(NCSR) isutilized for the DFPSCAT middle swath to verify its feasibility. Some simulation experiments are conducted and the results show that the reconstructed $\boldsymbol { \sigma } ^ { 0 }$ after the deconvolution method produces obvious better resolution enhancement and higher recovery accuracy compared with the classical SIR algorithm.

# 6.REFERENCES

[1]D.G.Long,P.J.Hardin,and P.T.Whiting,"Resolution enhancementofspacebornescatterometerdata,"IEEE Transactions on Geoscience and Remote Sensing,vol.31,pp.700- 715,1993.   
[2]M. W.Spencer,T.Wu-Yang,and D.G.Long，"Highresolutionmeasurementswithaspacebornepencil-beam scatterometerusingcombined range/Dopplerdiscrimination techniques,” IEEE Transactions on Geoscience and Remote Sensing, vol. 41, pp. 567-581,2003.   
[3]W.Gang,D.Xiaolong,B.Qingliu,Z.Di,and X.Xingou, "An unfocused SAR design to improve azimuth resolution of dualfrequency full-polarized scatterometer,"2O15 IEEE International Geoscience and Remote Sensing Symposium (IGARSS)，，pp. 4878-4881,26-31 July 2015.   
[4] D.S.Early and D.G. Long，"Image reconstruction and enhanced resolution imaging from irregularsamples," IEEE Transactions on Geoscience and Remote Sensing,vol.39,pp.291- 302,Feb. 2001.   
[5]D.Weisheng，Z. Lei， S.Guangming，and L. Xin, "Nonlocally Centralized SparseRepresentation forImage Restoration," IEEE Transactions on Image Processing, vol. 22, pp. 1620-1630,2013.   
[6]T.Leung,P. Jin,L.Ding,L. Zhongxin,D.W. Cline,and T. Yunhua,"Modeling Active Microwave Remote Sensing of Snow Using Dense Media Radiative Transfer(DMRT）Theory With Multiple-Scattering Effects," IEEE Transactions on Geoscience and Remote Sensing, vol. 45, pp. 990-1004,2007.   
[7]N. O.H. R. S. Center,Snow Data Assimilation System (SNODAS）Data Products at NSIDC,Boulder,Colorado USA: National Snow and Ice Data Center.