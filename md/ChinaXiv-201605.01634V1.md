# The modification of Ultraviolet Total Ozone Unit (TOU) for

# Absorbing Aerosol Index

Yongmei Wangl,Houmao Wangl,Weihe Wang²,Jianguo $\mathrm { F u } ^ { 1 }$ ,Liping $\mathrm { F u } ^ { 1 }$ 1National Space Science Center, Chinese Academy of Sciences 2National Satellite Meteorological Center, China Meteorological Administration

Abstract:Aerosol Absorbing Index (AAI) can be used for the observation of the absorbing aerosol including dust, biomass burning and volcano ash etc. Recently, with much more aerosol pollution events occurring,atmospheric environment is getting worse in China.The AAI derived from FY-3/TOU has been used for the atmospheric aerosol pollution observation since 2013 by China Meteorological Administration. In this paper, the precision factors analysis of AAI retrieval from TOU is made.Based on the analysis, the wavelengths most suitable for AAI retrieval are $3 5 4 ~ \mathrm { n m }$ and $3 8 8 ~ \mathrm { n m }$

Besides, considering the low spatial resolution of TOU $( 5 0 \times 5 0 ~ \mathrm { k m } ^ { 2 } )$ , a modified UV sensor is proposed with characters of much smaller size,higher sensitivity $( \mathrm { S N R } { > } 4 0 0 0 )$ 0 and higher spatial resolution $( < 5 ~ \mathrm { k m } )$ which is much more suitable for observing aerosol pollution events, especially in urban areas.

Keywords: absorbing aerosol index (AAI), aerosol observation, UV sensor, TOU

# 1Introduction

Aerosol is an important but complicated factor in climate and atmospheric chemistry. It cools the climate system by shortwave scattering,but heats it due to shortwave absorption (P. Stammes, 2002). Besides, it plays an important role in air pollution, especially in China in recent years.

Traditionally, aerosol measurements are being made using the sensor in the visible and infrared (IR) range. In the visible and near-IR, the complex and large surface albedos of different land types, e.g. urban area, make aerosol retrieval more difficult over these regions (M. de Graaf, 2Oo5). However, the surface albedos of both land and ocean are smallin the UV, which demonstrates that this wavelength range is suitable for aerosol observation.

The UV AAI used for the index indicating the presence of elevated absorbing aerosols in the troposphere is a quantity derived from the residue which emerged as an error estimate in the Total Ozone Mapping Spectrometer (TOMS） ozone retrieval algorithm (O. Torres et al.，1998) the precision of which is influenced strongly by absorbing aerosol such as dust， biomass burning，and volcano ash etc. As the atmospheric particulate matter pollution got worse, the UV AAI was used extensively to investigate aerosol impact on climate and atmospheric pollution. Compared to traditional method of visible and infrared bands, The UV AAI method cannot only distinguish the cloud/ice from land much more easily but also can reduce the influence of land/ocean because of much lower reflectance of them.

Since TOMS was launched in 1978, series of detecting instruments including European atmospheric research instruments such as the Global Ozone Monitoring Instrument (GOME) on ERS-2, the Scanning Imaging Absorption Spectrometer for Atmospheric CartograpHY(SCIAMACHY) on ENVISAT(J. P.Burrows,1992) and NASA's instruments such as the Ozone Monitoring Instrument (OMI) on the EOS-AURA satellite and Ozone Mapping Profiler Suite (OMPS) on NPP/NPOESS have been used for ozone observation and aerosol retrieval products which include total of ozone (J. de Vries,2001), AAI and UV-AOD etc. (Yang et al, 2013 ， O. Torres et al.,

2007). These products have been used for the global observation of ozone, heavy dust, biomass burning and volcanic eruption events etc.In China, the first instrument for ozone observation called Total Ozone Unit (TOU) was launched in 20o8. Since 2013, with the occurrence of fog and haze event, the AAI retrieval of TOU has been used for the observation. In this paper, the methodology and results analysis of AAI retrieved from TOU are shown in section 2 and 3 respectively. Based on the analysis, a modified absorbing aerosol observation system is proposed which provides with smaller volume, higher sensitivity and higher spatial resolution observation in section 4.

# 2Methodology

The AAI is defined as positive residue and calculated using the following equation:

$$
\begin{array} { r } { \mathrm { A A I } = - 1 0 0 l o g \left\{ \left[ \frac { I _ { \lambda _ { 1 } } } { I _ { \lambda _ { 2 } } } \right] _ { m e a s } \right\} + 1 0 0 l o g \left\{ \left[ \frac { I _ { \lambda _ { 1 } } ( A _ { L E R _ { \lambda _ { 1 } } } ) } { I _ { \lambda _ { 2 } } ( A _ { L E R _ { \lambda _ { 2 } } } ) } \right] _ { c a l c } \right\} } \end{array}
$$

Where $\boldsymbol { A } _ { L E R }$ is surface reflectance, $I$ is apparent reflectance, $\lambda$ is wavelength $( \lambda _ { I } \mathrm { i s } \ 3 3 1$ nm, $\lambda _ { 2 } \mathrm { i s } ~ 3 6 0 ~ \mathrm { n m }$ , subscript meas refers to instrument measurement and calc denotes the modeled simulation. The modeled reflectance is calculated for a cloud-free and aerosol free atmosphere in which only Rayleigh scattering,absorption by molecules as well as Lambertian surface reflection can take place(O. Torres et al., 2007).

The surface albedo $\mathbf { A } _ { \mathrm { L E R } }$ is,however, not meant to represent the actual ground albedo in any way. Its value is obtained from requiring that the simulated reflectance equals the measured reflectance at the calculation wavelengthl $\mathbf { \Phi } _ { I }$

$$
\mathrm { I } _ { \lambda _ { 1 } } ^ { m e a s } = \mathrm { I } _ { \lambda _ { 1 } } ^ { c a l c } ( \sf A _ { \mathrm { L E R } } )
$$

so we basically assume that the surface albedo is constant over the wavelength interval $[ \lambda _ { 1 } , \lambda _ { 2 } ]$ . In the UV, this is a good approximation for most surface types (Herman et al,1997). Therefore, the Eq. (1) can be reduced to:

$$
\begin{array} { r } { \mathrm { A A I } = 1 0 0 \times \log \left\{ \frac { I _ { \lambda _ { 2 } } ^ { \mathrm { { m e a s } } } } { I _ { \lambda _ { 2 } } ( A _ { L E R } _ { \lambda _ { 2 } } ) c a l c } \right\} } \end{array}
$$

using Eq.3,AAI can be calculated combining measurements of $\lambda _ { 2 }$ and modeled simulation of $\lambda _ { 2 }$ when $\boldsymbol { A } _ { L E R }$ is found.

The importance of the AAI lies in its ability to effectively detect the presence of absorbing aerosols even in the presence of clouds. When a positive AAI is found, absorbing aerosols are certainly present in the observed scene. Negative or zero value, on the other hand, suggests a definite absence of absorbing aerosols.

Since AAI is retrieved using the different absorption of two channels of aerosol such as dust, soot etc (Fig 1). In Fig 1, the aerosol absorption of UV is much stronger than near visible channel, which means that the aerosol can be observed using the difference of absorption of two wavelength channels.

![](images/96bcff2bfc9352223699a1ea48ee888183735db2ab2a82b9112d617e87141a5a.jpg)  
Fig.1 The influence of different absorbing aerosol types in the range of $3 3 0 { \sim } 5 0 0 \mathrm { n m }$

# 3 FY-3/TOU AAI observation

FY-3 satellites are Chinese second-generation polar orbit meteorological satellite series.Ultraviolet Total Ozone Unit (TOU） is one of the main payloads on FY-3 satellite. FY-3/TOU is a grating spectrometer, and its purpose is to measure the Earth backscatter ultraviolet radiation at six wavelengths for retrieving daily global map of atmospheric ozone(Y. Wang,2O1O). It is the first instrument for daily global coverage of total ozone monitoring in China. Based on the retrieval of ozone, AAI was tried to be calculated using two longest wavelengths ( $3 3 1 \ \mathrm { n m }$ and $3 6 0 \ \mathrm { n m } )$ ）of FY-3/TOU, following EP/TOMS, which are influenced relatively smaller by ozone absorption. As AAI is sensitive to absorbing aerosol, it can be used for heavy dust, haze and biomass burning observation in China (Fig2).

![](images/38167fc99e8a4fed2b0fe9e3b877bb28ca80690c214e19eaf1e196c9822437b4.jpg)  
Fig.2FY-3/TOU AAI of haze observation in China (20130129)

In Fig 2, the distribution of haze and fog pollution incident is shown with AAI retrieved from TOU. However, considering the influence of ozone absorption on 331 nm (Fig 3) and the Ring effect of $3 6 0 ~ \mathrm { n m }$ ， the AAI cannot be retrieved precisely. Therefore， the wavelength for observation should be re-selected. As AAI was calculated based on the two different wavelengths radiance of aerosol absorption, the selection of wavelength should be based on the following considerations: 1） little influence of ozone absorption and Ring effect, 2） small enough surface reflectance difference of two wavelengths. Considering the points above, $3 5 4 \mathrm { n m }$ and $3 8 8 ~ \mathrm { n m }$ are the most suitable for the retrieval of AAI. Besides, TOU with a low spatial resolution of $5 0 { \times } 5 0 ~ \mathrm { k m } ^ { 2 }$ is only suitable for aerosol pollution observation of wide area but not suitable for urban area. Therefore, the spatial resolution should be improved by the modification of the light observation system.

![](images/e794c208a63c3daef97d2595f0302fedf19948b0714f983c13bdba69f3f9adc2.jpg)  
Fig.3 Atmospheric transmittance of near UV from $3 1 0 { \sim } 3 9 0 \mathrm { n m }$

# 4Modified sensorfor AAI

Based on the analysis of AAI observation by FY-3/TOU, a modified sensor was proposed with characters of smaller size, higher sensitivity and higher spatial resolution. The specifications of the sensor are shown in Table 1.

Table 1 Specifications of ultraviolet Absorbing Aerosol Index (AAI) sensor   

<html><body><table><tr><td>Index</td><td>Specifications</td></tr><tr><td>Bands</td><td>Channell :354nm，FWHM1.5-2.0nm</td></tr><tr><td></td><td>Channel2 :388nm，FWHM1.5-2.0nm</td></tr><tr><td>Range of scanning</td><td>±55.8°</td></tr><tr><td>Field of angle</td><td>5.4°x5.4°</td></tr><tr><td>F number</td><td>10</td></tr><tr><td>Space resolution</td><td>< 5km (nadir point)</td></tr><tr><td>Signal to Noise Ratio</td><td>>4000</td></tr></table></body></html>

The optical system is composed of a depolarizer, a Kepler system, a splitter, two filters，two objective lenses,a prism reflector and a CCD sensor (Fig. 4). The depolarizer is used to reduce the impact of polarized light as there are different sensitivities on sensors with different polarized lights.So,a Lyot depolarizer is used here which has two wedge prisms with orthogonal crystal axes. The Kepler system is used to limit the field of angle,and to expand the light at the same time. The splitter with dual color mirrors can split light into two different bands.In this system, the key point is the prism reflector which can combine two channels of light on the same CCD.

![](images/22daed121c0e286fe4dde36c07e57faedefdd3b13060704c1aa4807ff6062a5b.jpg)  
Fig. 4 The scheme of ultraviolet Absorbing Aerosol Index(AAI) senor

# 5 Conclusions

In this paper, the precision factors analysis of AAI retrieval from TOU and the modification based on the analysis are made, which include the re-selection of wavelength and the improvement of spatial resolution. AAI retrieval from TOU uses $3 3 1 \ \mathrm { n m }$ and $3 6 0 \ \mathrm { n m }$ which are influenced by ozone absorption and Ring effect respectively. According to the influence of ozone absorption, surface reflectivity and aerosol own absorbing characters, the most suitable wavelengths for AAI retrieval are $3 5 4 \mathrm { n m }$ and $3 8 8 ~ \mathrm { n m }$ . Besides, the spatial resolution of TOU with $5 0 { \times } 5 0 \mathrm { k m } ^ { 2 }$ cannot be suitable for the urban atmospheric environment observation. Therefore, a modified absorbing aerosol observation system was proposed. It can provide with smaller volume,higher sensitivity $( \mathrm { S N R } { > } 4 0 0 0 )$ )and higher spatial resolution $( < 5 \mathrm { k m } )$ ,which is much more suitable for urban aerosol pollution events monitoring.

# References:

[1]Herman, J.R.,and E.A. Celarier (1997),Earth surface reflectivity climatology at $3 4 0 { - } 3 8 0 ~ \mathrm { n m }$ （204号 from TOMS data,J. Geophys. Res., 102(D23), 28,003-28,011, doi:10.1029/97JD02074   
[2]M. de Graaf, P. Stammes, O. Torres,R. B.A. Koelemeijer. Absorbing Aerosol Index: Sensitivity analysis,application to GOME and comparison with TOMS. JOURNAL OF GEOPHYSICAL RESEARCH,VOL.110,D01201,doi:10.1029/2004JD005178,2005   
[3]J. de Vries,G.H.J.van den Oord,E.Hilsenrath,M. te Plate,P.Levelt and R.Dirksen, Ozone Monitoring Instrument(OMI), Proc SPIE,2001,4480,315-325   
[4]J.P. Burrows and K. V. Chance,“SCIAMACHY and GOME: The Scientific Objectives,” in Optical Methods in Atmospheric Chemistry,SPIE,1992.   
[5]O.Torres,P.K.Bhartia， J.R. Herman,et al. Derivation of aerosol properties from satellite measurements of backscattered ultraviolet radiation: Theoretical basis. JOURNAL OF GEOPHYSICAL RESEARCH, VOL.103,NO.D14,PAGES 17,099-17,110, JULY 27,1998   
[6]O.Torres,J.R.Herman,PK.Bhartia，and A.Sinyuk,2002，AEROSOL PROPERTIES FROM EP-TOMS NEAR UV OBSERVATIONS,Adv. Space Rex Vol. 29, No. 11, pp. 1771-1780.2   
[7]O.Torres， P. K. Bhartia,A. Sinyuk,E. J. Welton,and B.Holben (2005),Total Ozone Mapping Spectrometer measurements of aerosol absorption from space: Comparison to SAFARI 2000 ground-based observations,J. Geophys.Res.,110, D10S18, doi:10.1029/2004JD004611.   
[8]O. Torres,A. Tanskanen, B. Veihelmann et al, 2O07,Aerosols and surface UV products from Ozone Monitoring Instrumentobservations: An overview, JOURNAL OF GEOPHYSICAL RESEARCH, VOL. 112, D24S47   
[9]P. Stammes，R. Noordhoek. OMI Algorithm Theoretical Basis Document (Volume III). ATBD-OMI-03, Version 2.0,August 2002   
[10] Yang,K.,R.R.Dickerson, S.A. Carn, C.Ge,and J. Wang (2013),First observations of SO2 from the satelite Suomi NPP OMPS: Widespread air pollution events over China, Geophys. Res. Lett., 40,doi:10.1002/grl.50952   
[11] Y. Wang,Y. Wang, W. Wang, Z. Zhang, J.Lu,L.Fu, et. al,“FY-3 satellite Ultraviolet Total Ozone Unit," Chinese Science Bulletin, vol. 55,pp. 84-89,2010.