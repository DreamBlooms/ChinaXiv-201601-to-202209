# PRELIMINARY PERFORMANCE SIMULATION OFMICROWAVE IMAGER COMBINED ACTIVE/PASSIVE -A NEW INSTRUMENT FOR CHINESE SALINITY MISSION

Xiaobin Yinl\*, Lanjie Zhangl'2, Hao Liul, Risheng Yun',Lin $W u ^ { I }$ , Xingou $X u ^ { I }$ ,Di Zhul

1. Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of   
Sciences, Beijing, China   
2. University of Chinese Academy of Sciences, Beijing, China

# ABSTRACT

A 1-D interferometric system at 1.4GHz, 6.9GHz, 18.7 GHz and 23.8GHz combined with a scatterometer at 1.26GHz, called microwave imager combined active/passive (MICAP) has been proposed to retrieve sea surface salinity(SSS) and to reduce geophysical errors due to surface roughness and sea surface temperature (SST). The MICAP will bea candidate payload onboard the Ocean Salinity Satellite of China.Thesensitivityofactive/passivemicrowave observations to SSS，SST and wind is analyzed and the stability requirement of the instruments is estimated,with the objective of designing an optimized satellite instrument, dedicated to an "all-weather" estimate of the SSS with high accuracy from space.

IndexTerms- combined active/passive,SSS, instrument performance simulation

# 1.INTRODUCTION

The development of Sea Surface Salinity(SSS) observations with satellite L-band radiometers can improve temporal and spatial resolution,monitor the large-scale salinity events.In order to satisfy the need for measuring high-quality global observations of SSS from space， two L-band satelite missionshave been launched in November 2OO9 and June 2011,the SMOS (the European Soil Moisture and Ocean Salinity） and Aquarius (the NASA Aquarius/SAC-D）, respectively.Theywillprovidenewglobal sSS, complementary to in situ measurements [1,2].

The L-band has been chosen for the sea surface salinity (SSS) remote sensing because it features a sensitivity of sea surface radiometric measurements to changes in salinity that issignificantly larger than at higher frequencies and it is protected against human-made emissions.However,even at this frequency，SSS remote sensing is very challenging because the sensitivity of brightness temperature(TB） to

SSS remains low: in the range of 0.35 K·pss-1 to $0 . 8 \mathrm { ~ K ~ }$ \*pss1 for the vertical polarization and O.2 K·pss-1 to O.6 K·pss-1 for the horizontal polarization. The main geophysical sources of error in the retrieval of SSS from L-band TB come from the uncertainty of the ocean surface emissivity related to the surface roughness and sea surface temperature (SST).

However, the above salinity observation systems,like SMOSandAquarius， requireadditionalauxiliary information to retrieve SSS,suchas sea surfacewind field andsea surface temperature(SST） predicted bythe European Center for Medium Range Weather Forecasts (ECMWF) operational system or the National Centers for Environmental Prediction (NCEP). However, the accuracy of these auxiliary information will affect the retrievals of sss.

A candidate payload,called the microwave imager combined active/passive (MICAP)，for the Sea Surface Salinity Remote Sensing Satellite mission of State Oceanic Administration of China has been proposed to retrieve SSS simultaneously with SST and wind.The MICAP has the capability of L/C/K multi-band passive and L-band active measurement. The new mission objective is to produce SSS with an accuracy of1 psu at a single glance and O.1 psu for a monthly average, ground resolution of $5 0 ~ \mathrm { k m }$ as well as global coverage time less than 3 days.Table 1 presents the comparison between the SSS satellite of China and other SSS satellites in orbits.

The configuration of the MICAP is briefly introduced in section I and the method of performance simulation of the MICAP is presented in section III. The results are presented in section IV.

# 2.MICROWAVEIMAGERCOMBINED ACTIVE/PASSIVE

The passive radiometer of MICAP is an interferometric microwave imaging system in order to avoid the problems such as manufacturing and oscillating due to mechanical scanning for large size antenna of traditional real aperture radiometer.Thecombinedactive/passivemulti-band microwave remote sensing system is based on the common parabolic cylindrical-reflector antenna. Fig. 1 gives the schematic diagram of cylindrical-reflector antennaof MICAP.TheL/C/K-bandradiometerand L-band scatterometer share the same $3 ^ { * } 5 . 5 \mathrm { ~ m ~ }$ cylindrical-reflector, and multi-frequency array feed are arranged in the focal line of cylindrical-reflector.They are used to implement the one dimensional interferometric radiometer and digital beam scanning scatterometer simultaneously. The perspective characteristics of MICAP are given in Table 2.

Table 1 The comparison between the Chinese SSS satellite and other SSS satellites in orbits.   

<html><body><table><tr><td>Mission</td><td>Ocean salinity satellite</td><td>SMOS</td><td>Aquarius/SAC-D</td></tr><tr><td>Accuracy of monthly SSS</td><td>0.1psu @ 200km</td><td>0.1psu@200km</td><td>0.2psu @150km</td></tr><tr><td>Swath width</td><td>>950 km</td><td>>1000 km</td><td>390 km Pixel 1: 94x76 km</td></tr><tr><td>Ground resolution</td><td>~50 km</td><td>~40 km</td><td>Pixel 2: 120x84 km Pixel 3:156x96 km</td></tr><tr><td>Simultaneous auxiliary products</td><td>SST Wind Speed</td><td>None</td><td>Wind Speed</td></tr><tr><td>Revisit time</td><td>3days</td><td>3 days</td><td>7 days</td></tr></table></body></html>

![](images/13fd9b8150a29e184b94cb68006d158060e3b8734f153c41362d6a1bba85fa66.jpg)  
Fig.1 The schematic diagram of parabolic cylindricalreflectorantenna of microwave imagercombined active/passive.

The sensitivity of brightness temperature(TB） to SSS remains high only in low frequency(\~1GHZ,L-band),and it will rapidly decrease with increasing microwave frequency. The sensitivity of TB to SST remains high in C-band (reaches the peak at 7GHz)，to wind speed is basically consistent at frequency higher than $1 0 \mathrm { G H z }$ ，and to atmospheric water vapor is relatively high in K-band (reaches the peak at $2 3 . 8 \mathrm { G H z }$ ).Therefore,the sensitivity of TB at different frequencies to the physical parameters is different. This is the basic principle of the simultaneously remote sensing of SSS, SST,WS,etal.with MICAP.

Table 2 Perspective characteristics ofMICAP.   

<html><body><table><tr><td>Specification</td><td>Value</td></tr><tr><td>System</td><td>L/C/K band1D MIRs +L-band DBF SCAT (parabolic cylinder reflector)</td></tr><tr><td>Frequency</td><td>Radiometer:1.4-, 6.9-,18.7-, 23.8 GHz</td></tr></table></body></html>

<html><body><table><tr><td></td><td>Scatterometer:1.26GHz</td></tr><tr><td>Sensitivity</td><td>L: 0.1K/0.1dB;C/K:0.3K</td></tr><tr><td>Polarization</td><td>L: H,V,T3; C/K:H,V</td></tr><tr><td>Antenna size</td><td>Reflector: >3.0mx5.5 Feed array:>4mx0.5m</td></tr><tr><td>Incident angle</td><td>30~55°</td></tr><tr><td>Spatial resolution</td><td>Cross-track: 50~100km Along-track: L/C/K: 65/15/15km</td></tr></table></body></html>

Compared to the two dimensional interferometric radiometer onboard the SMOS satellite,one dimensional (1D) interferometric radiometer has lower complexity,and it is easier to implement higher accurate temperature control, and thus have higher stability and calibration accuracy. Comparedtotherealaperturesystemonboard Aquarius/SAC-D，MICAP can achieve the better spatial resolution as well as wider swath.

![](images/7d6ad05bd1ce2a27b7aece63efdc6a7025a0ba3f45e21d95a35ac60ecfa8335b.jpg)

![](images/bb597e5150e35f6af6db4b42479a14b3e920ff7e80609cb390eb1af6db5b3022.jpg)  
Fig.2 The schematic diagram of field of view for the radiometer (top) and the scatterometer (bottom).   
Fig.3The flowchartofretrievalsimulation

The radiometer and scatterometer from microwave imager combined active/passive can form sector beam field of view on the ground,as shown in Fig.2. The alias-free fieldofview(AF-FOV)for theswathofradiometerand the beam scanning range of scatterometer were limited by the periodic repetition of the array spacing.

# 3.FORWARDMODEL ANDSIMULATIONMETHOD

# A.Forward model

The forward model used to compute the TB at the top of the atmosphere without considering the Faraday rotation in the Earth reference frame can be expressed as

$$
T B = \left( T b _ { \it f l a t } + T b _ { \it w i n d } + T b _ { \it D N } \Gamma + T b _ { \it g a l \_ r e f } \right) e ^ { - \tau _ { a t m } } + T b _ { \it U P } ,
$$

where $T b _ { f l a t }$ is the brightness temperature for a flat sea, $T b _ { w i n d }$ is the wind-induced contribution to sea surface TB, $T b _ { D N }$ is the downward emitted atmospheric radiation, $\boldsymbol { { \cal T } }$ is the sea surface reflection coefficient computed as1 $\cdot ( T b _ { f l a t } +$ $T b _ { w i n d } ) / \mathrm { S S T }$ ，which takes into account the scattering by the ocean surface assuming that $T b _ { D N }$ is homogeneous in all directions, $T b _ { g a l \_ r e f }$ is the cosmic and galactic contribution already scattered by the sea surface taking into account the directional inhomogeneities of the galactic signal, $T b _ { U P }$ is the upwelling atmospheric emission to the antenna and $e ^ { - { \tau _ { a t m } } }$ is the attenuationby the atmosphere.

The L-band forward model implemented in the ESA L2OS processor is used.It simulates the flat sea emission with the Klein and Swift (1977） model [3] and other contributions from the rough sea surface,the atmospheric emission and absorption [4],and the scattering of galactic noise and atmospheric radiation by the ocean surface.The community radiative transfer code RTTOV[5]is used for the CandKbandforwardmodel.

An L-band ocean geophysical model function (GMF) derived from PALSAR[6] is used for the GMF ofL-band scatterometer.

The analysis of the sensitivity and stability of the MICAP observations is based on a simulated data set, calculated from surface and atmospheric information derived from the European Center for Medium Range Forecasting (ECMWF).

# B.Retrievalmethod

Theretrievalsarebased on thenonlineariterative convergence method. The first guess geophysical inputs,i.e. SSS, SST,wind speed (WS), vapor (V) and cloud liquid (L) are adjusted in order to minimize a “cost function” $\chi ^ { 2 }$ expressed by

$$
\begin{array} { c c l } { \displaystyle \mathcal { X } ^ { 2 } = \sum _ { p = V , H } \frac { ( T _ { B _ { p , \perp } \perp D } - T _ { B _ { p , m , \perp } \perp D } ) ^ { 2 } } { \Delta T _ { p , \perp \perp D } ^ { 2 } } + \sum _ { p = V , H } \frac { ( T _ { B _ { p , \perp } \perp T } - T _ { B _ { p m , c } } ) ^ { 2 } } { \Delta T _ { p , c } ^ { 2 } } + } \\ { \displaystyle \sum _ { p = V , H } \frac { ( T _ { B _ { p , E } \perp \mathrm { B } } - T _ { B _ { p , m , \perp } \perp \mathrm { B } } ) ^ { 2 } } { \Delta T _ { p , \perp \mathrm { B } } ^ { 2 } } + \sum _ { p = V , H } \frac { ( T _ { B _ { p , E } \perp 3 } - T _ { B _ { p m , \perp } \perp 3 } ) ^ { 2 } } { \Delta T _ { p , k \perp \mathrm { B } } ^ { 2 } } + } \\ { \displaystyle \sum _ { p = V , H } \frac { ( T _ { 0 , p } - \sigma _ { 0 _ { p , m } } ) ^ { 2 } } { ( \gamma _ { p } \sigma _ { 0 _ { p } } ) ^ { 2 } } + \frac { ( S S S - S S S _ { a } ) ^ { 2 } } { \Delta S S ^ { 2 } } + \frac { ( S S T - S S T _ { a } ) ^ { 2 } } { \Delta S S ^ { 2 } } + } \\ { \displaystyle \frac { ( W S - W S _ { a } ) ^ { 2 } } { \Delta W S ^ { 2 } } + \frac { ( W D - W D _ { a } ) ^ { 2 } } { \Delta W D ^ { 2 } } + \frac { ( V - V _ { a } ) ^ { 2 } } { \Delta V ^ { 2 } } + \frac { ( L - L _ { a } ) ^ { 2 } } { \Delta L ^ { 2 } } } \end{array}
$$

where $V$ and $H$ are the vertical polarization and the horizontal polarization, $T _ { B p f }$ and $T _ { B p m f }$ are the measured Tb of multi-incident angles and simulated TB of the forward model at four frequencies $f , \sigma _ { 0 p }$ and ${ \sigma } _ { 0 p m }$ are the measured and simulated backscatter at $1 . 2 6 \mathrm { G H z }$ . The right foot marks an express the initial fields of variables.The value of $\Delta$ is representative of the expected error of each item.

The initial values of auxiliary data   
: SSS,SST,WS,WD,atmospheric   
parameters,etc.   
1.4,6.9,18.7 and 23.8GHz model:   
TB of rough surface,Atmosphere   
and cosmic background radiation Measurement : Brightness temperature data   
Simulation values of atmospheric of1.4,6.9,18.7and 23.8GHz   
top brightness temperature plus backscattering at 1.26GHz Multi-parameter nonlinear Correction of Faraday rotation iterative retrieval 1.4GHz T3 data Main Products: SSS,SST,WS Byproducts:water vapor content and cloud liquid watercontent

Monte Carlo simulations are used to analyze the performance of MICAP (Fig.3).The simulated data are generated by adding a Gaussian random component to GMF predictions of TB and backscattering and repeated 2000 times.The passive GMFs used here benefit from SMOS L band,AMSR-E C andKband models,and the passive GMF benefits from the PALSARL band model. The retrievals are based on the nonlinear iterative convergence method (LM method).

# 4.RESULTS

In the case we studied, root mean square (rms) errors of SSS, SST and WS are around O.6 psu, $0 . 8 ^ { \circ } \mathrm { C }$ and $1 . 0 \ \mathrm { m / s }$ and varies with incidence angle,since the radiometric resolution of MICAP change across the swath (Fig. 4).

![](images/1bc7130a914494a77a82d15ada0e2311e8a6c0427381ca549579c65a8575f554.jpg)  
Fig.4 Error estimate of SSS，SST and wind speed from MICAP.

We have also tested performances of MICAP with other configurations，such as without 23.8 GHz H-pol., without 18.7 GHz V-pol. and 23.8 GHz H-pol.,without 18.7 GHz H- and V-pol.,and without $2 3 . 8 \mathrm { G H z H - }$ and V-pol. It seems that the rms error of SSS without 23.8 GHz H-pol. and without 18.7 GHz V-pol. is close to that with the default configuration listed in table 2(Fig.5).The rms error of SSS degrades if $1 8 . 7 \mathrm { G H z }$ or $2 3 . 8 \ : \mathrm { G H z }$ is not used (Fig. 5).

![](images/969a70ebd8a66d4ed0e5a2013e4ab8468e3471498f746044f08fe51f84fe7212.jpg)  
Fig.5 Error estimate of SSS from different configurations.

# 5.SUMMARY

A 1-D interferometric system at 1.4-，6.9-，18.7- and $2 3 . 8 \mathrm { G H z }$ combined with a scatterometer at 1.26GHz,called microwaveimagercombinedactive/passive(MICAP), which is the candidate payload for the Ocean Salinity Satellite of State Oceanic Administration of China,has been proposed to retrieve SSS and to reduce geophysical errors due to the surface roughness and SST.Theoretical basis of synergetic retrievals of multi-parameters including SSS using MICAP is introduced.

AshortintroductionofMICAP'sprinciple characteristics isgiven and theperformance of this instrument is estimated based on Monte Carlo simulations and a combined active/passive SSS retrieval algorithm. The estimated rms errors of SSS,SST and WS are expected to meet the requirement of the Ocean Salinity Satellite of State Oceanic Administration of China.

# 6.REFERENCES

[1] J.Font,A.Camps,A.Borges,M.Martin-Neira,J.Boutin,N. Reul,Y.Kerr，A.Hahne，and S.Mecklenburg,“SMOS:The challenging measurement of sea surface salinity from space,”Proc. IEEE,vol.98,no.5,pp.649-66,May 2010.   
[2]D.Le Vine,G.Lagerloef and S.Torrusio,“Aquarius and remote sensing of sea surface salinity from space",Proc.IEEE,vol. 98,no.5,pp.688-703,May 2010.   
[3]L.Klein and C.Swift,“An improved model for the dielectric constant of sea water at microwave frequencies,”IEEE Trans. Antennas Propag.,vol.AP-25,no.1,pp.104-111,Jan.1977. [4] H. Liebe,G. Hufford,and M. Cotton,“Propagation modeling ofmoist air and suspended water/ice particles at frequencies below 1000 GHz,” presented at the AGARD 52nd Specialists’Meeting Electromagnetic Wave Propagation Panel, Palma de Mallorca, Spain,1993.   
[5] O.Isoguchi,and M. Shimada,“An L-band ocean geophysical model function derived from PALSAR,”IEEE Trans.Geosci. Remote Sens.,vol.47,no.7,pp.1925-1936,July 2009.   
[6]M.Matricardi,G. Chevallier,and J-N.Thepaut,“An improved general fast radiative transfer model for the assimilation of radiance observations,”Q. J. Roy. Meteorol. Soc.，vol. 30，pp. 153-173,2004.