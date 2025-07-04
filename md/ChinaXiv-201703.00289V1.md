# ESTIMATING THE SEA STATE BIAS OF HY-2A RADAR ALTIMETER BY USING A THREE-DIMENTIONALNONPARAMETRICMODEL

Maofei Jiangl,2, Ke Xul, Yalong Liu³, Lei Wang

1 CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences,Beijing 100190, China 2 University of Chinese Academy of Sciences, Beijing 1Oo049, China   
3 Yantai Marine Environmental Monitoring Center Station, State Oceanic Administration, Yantai 264000, China

# ABSTRACT

The sea state bias (SSB） has become the dominant source of error in satellite altimetry. The operational SSB correction models are two-dimensional (2-D） nonparametric models based on the wind speed (U） and the significant wave height(SWH) that can be directly measured by the altimeters. This paper estimates the sea state bias of HY-2A radaraltimeterusingathree-dimensional(3-D) nonparametric model based on SWH from HY_2A interim geophysical dataset records (IGDR),U and the mean wave period (MWP） from the European Centre for MediumRange Weather Forecasts(ECMWF） reanalysis project ERA-Interim. The 3-D SSB estimates can increase the explained variance by $1 . 7 2 ~ \mathrm { c m } ^ { 2 }$ ,or $1 . 3 1 \mathrm { \ c m \ R M S }$ relative to the traditional 2-D SSB estimates based on U and SWH.

Index Terms—HY-2A,radar altimeter,sea state bias, crossover differences,3-D nonparametric model

# 1.INTRODUCTION

Sea level rise mainly caused by global warming has attracted more and more people's attention. One of the main purposes of radar altimeters is to measure the mean sea level. However,the sea level measured by radar altimeters is lower than the true sea level because wave troughs are better reflectors of radar energy than wave crests.This effect is called the electromagnetic bias (EM bias). There are two other sea-state-related biases:theskewness and tracker biases[1].The EM bias together with the skewness bias and the tracker bias is generally called the sea state bias (SSB). Thankstotheimprovement oftheprecise orbit determination technology and other geophysical corrections, the sea state bias has become the dominant source of error in satellite altimetry.

Theoperational SSB correction modelsare twodimensional (2-D） empirical models based on the wind speed (U) and the significant wave height(SWH) that can be directly measured by the altimeters.However,these 2-D SSB models can not entirely parameterize the range bias variability and the SSB uncertainty maybe lowered through improved SSB models by including additional measurable or predictable correlatives [2]. This paper estimates the sea state bias of HY-2A radar altimeter by using a 3-D nonparametric model based on U,SWH and MWP.The model is developed using the crossover sea surface height (SSH) differences.Compared with the SSB corrections in HY-2AIGDR and the traditional 2-D SSB estimates, the 3- D SSB estimates can greatly reduce the standard deviation (STD) of the crossover SSH differences and the STD of the sea level anomalies (SLAs).The enhancement from 2-D to 3-D SSB estimate is of great significance for improving the precision of HY-2A altimeter product.

# 2. METHODOLOGY

In this paper,we developed the 3-D SSB model using crossover SSH differences fromHY-2Aaltimeter.

The sea surface height measurement uncorrected for the SSB is denoted as SSH'. SSH' includes the geoid $( h _ { g } )$ ，the dynamic topography $( \eta )$ ，the SSB and some measurement noise $( \omega )$ ：：

$$
S S H ^ { ' } = h _ { g } + \eta + S S B + \omega
$$

At crossover points, the geoid signal can be eliminated by forming differences between two $S S H ^ { ' }$ measurements taken onthe ascendingarc (index1) and the descendingarc (index 2) respectively.

$$
S S H _ { 2 } ^ { ' } - S S H _ { 1 } ^ { ' } = ( S S B _ { 2 } - S S B _ { 1 } ) + ( \eta _ { 2 } - \eta _ { 1 } ) + ( \omega _ { 2 } - \omega _ { 1 } )
$$

Assume $( \eta _ { 2 } - \eta _ { 1 } ) + ( \omega _ { 2 } - \omega _ { 1 } )$ can be considered as a single zero-mean noise term $\varepsilon$ ．The observation equation (2） for the SSH differences can be written as:

$$
S S H _ { 2 } ^ { ' } - S S H _ { 1 } ^ { ' } = S S B _ { 2 } - S S B _ { 1 } + \varepsilon
$$

Assume the SSB is a function $\varphi$ of $\mathbf { x } = ( U , S W H , M W P ) :$

$$
\mathbf { S } \mathbf { S } \mathbf { B } = \varphi ( \mathbf { x } )
$$

Noting $y = S S H _ { 2 } ^ { ' } - S S H _ { 1 } ^ { ' }$ ,the observation equation (3) can be Written as:

$$
\mathbf { y } = \varphi ( \mathbf { x } _ { 2 } ) - \varphi ( \mathbf { x _ { 1 } } ) + \varepsilon
$$

Equation (5） can be solved by using a nonparametric estimation method based on kernel smoothing introduced by Gaspar [3, 4].

# 3. DATA

The input parameters of the 3-D SSB model developed are U, SWH and MWP.U and SWH usually are obtained from the altimeter observations.However, the wind speed in HY-2A IGDR is not good, so we used the wind speed from

ECMWF reanalysis project ERA-Interim. Fig.1 gives U and SWH from ECMWF and Jason-2 GDR respectively. Jason2altimeter has been fully calibrated.Both ECMWF derived U and SWH have high accuracy compared to Jason-2 GDR data.Fig.2 gives U and SWH from ECMWF and HY-2A IGDR respectively. The root mean square error (RMSE) of the differences between ECMWF derived SWHandHY-2A IGDR derived SWHis only $0 . 3 6 5 \mathrm { m }$ ：Therefore,the SWH from HY-2A IGDR can be used to develop the SSB model. TheRMSEof thedifferencesbetween ECMWFderivedU and HY-2A IGDR derived U is larger than $5 \mathrm { m / s }$ (The backscattering coefficient in HY-2A IGDR has not been fully calibrated,after the backscattering coefficient is fully calibrated, the derivedU will be better),so we use ECMWF derived U to estimate the SSB of HY-2A altimeter.

![](images/5ec944895177016b7a5a0cc5f23aea1f1f2483a38399301cafc9f0b46b0a793a.jpg)

Fig.2 U and SWH comparison between ECMWF and HY-2A altimeter (left: U; right: SWH)

# 3.1ERA-Interim reanalysis

ERA-Interim isthe third global reanalysisproject produced by the European Centre for Medium-Range Weather Forecasts(ECMWF). ERA-Interim provides reanalysis data from 1979 to the present time and updates in near real time.The objective of the ERA-Interim project is to prepare for a new global reanalysis project to replace ERA-4O gradually. Compared with ERA-40,ERA-Interim has some improvements in data assimilation, forecast model and observing system. A variety of data in uniform latitude/longitude grids can be obtained from ERA-Interim datasets.The mean wave period and the wind speed we used are projected on the grid of $0 . 2 5 ^ { \circ } \times 0 . 2 5 ^ { \circ }$ ：

# 3.2HY-2A altimeter

HY-2A satellite was launched on 16 August, 2011. HY2Ais a polar-orbit satellite with an orbit height of $9 7 1 ~ \mathrm { k m }$ The instruments on HY-2A include a dual-band (13.58 and 5.25GHz) radar altimeter (RA)， a Ku-band radar scatterometer (SCAT) and a microwave imager (MWI).The

RA is equipped with a three-channel (18.7,23.8 and $3 7 \mathrm { G H z }$ 0 microwave radiometer for wet troposphere delay correction.

In this paper,we used the cycle 42-56 of the HY-2A 1-Hz IGDR data to develop the SSB models.

# 4.RESULTS

# 4.1HY-2A SSB estimates

The 2-D SSB estimates are shown in Fig.3 in the form of 2-D grids with contours given in cm. As is shown in Fig.3, the magnitude of the SSB generally increases with the increase of SWH.For a given SWH, the magnitude of the SSB first increases with U and then decreases at higher wind speeds.

![](images/514f07036567f7a96ce7e86deb7a82f74f5f7e81cc24f10759e8896ae519b254.jpg)  
Fig.3 HY-2A SSB estimates (in cm) obtained using a 2-D SSB model based on U and SWH. Shaded areas represent data density: (dark gray) when it is less than 5 samples,(red) when itis between 5 between 30,(yellow) when it is between 30 and 1OO,and (white) when itis larger than 1OO samples.

The 3-D SSB model based on U，SWH and MWP is presented as a 3-D lookup table and the ranges of U, SWH and MWP are respectively $0 { - } 3 0 \mathrm { m / s }$ ， $0 { - } 1 2 \mathrm { m }$ and O-18s.In order to better represent the 3-D SSB model,we present the correction values in the form of 2-D arrays by fixing a third parameter.Contours of the SSB values are displayed in cm and they are shown in Fig.4.The fixed values are near the mean values to ensure that there are enough measurements. In our study, the three fixed value we choose are $\mathrm { \Delta M W P = 9 s }$ $\mathrm { U } { = } 7 . 5 \mathrm { m }$ and $\operatorname { S W H } { = } 2 . 5 \mathrm { m }$ respectively. Fig.4 (a） agrees closely with Fig.3.When U and MWP are fixed,the magnitude of the SSB is an increasing function of SWH. In contrast,as can be seen in Fig.4 (b),the magnitude of the SSB is a decreasing function of MWP when U and SWH are fixed.In the data-rich region,there is an approximately $4 \mathrm { c m }$ variation versus MWP，with the magnitude of the SSB decreasing as the wave period increases.As can be observed in Fig.4 (c),when SWH is fixed, variations with MWP are more obvious than that with U in data-rich region. For a given U,the magnitude of the SSB is a decreasing function ofMWP.

# 4.2Assessment of the 3-D SSB estimates

We used the explained variance to evaluate the 3-D SSB model. The explained variance is the reduction of the variance of the crossover SSH differences obtained after applying the given SSB correction and it is a main criterion to assess the quality of a SSB model.We first used the global data to calculate the explained variances. The variances explained by 3-D SSB estimates，2-D SSB estimates and the SSB corrections in HY-2A IGDR are 29.95,28.23 and $2 6 . 4 7 \mathrm { c m } ^ { 2 }$

![](images/9c395bdcf641aa06238977e014550da53e650670167d225ddd34fcf0235e2fa6.jpg)  
Fig.4 HY-2A SSB estimates (in cm) obtained using a 3-D SSB model based on U, SWH and MWP.This is shown using three 2-D arrays with the respective third variable held constant. The fixed valuesare(a) $\mathrm { \Delta M W P = 9 s }$ ，（b） $\mathrm { U } { = } 7 . 5 \mathrm { m / s }$ ，（c） $\operatorname { S W H } { = } 2 . 5 \mathrm { m }$ respectively.Shaded areas represent data density:(dark gray) holding no data,(red)when it is between1between 5,(yellow) when itis between 5 and 1O,and(white) when itis larger than 10 samples.

We then binned the crossover data into $1 0 ^ { \circ }$ latitude bands and computed the explained variance in each band.The explained variance in comparison to the 1D $( - 3 . 8 \% \mathrm { S W H } )$ SSB model is given in Fig.5.3-D SSB estimates are better at most latitude regions.

![](images/390dff08c57eb70a3cc29785bcc2d7e32fd9c388c7a9c5070f5b74737c1a069f.jpg)  
Fig.5 Latitude distribution of the variance explained by 3D SSB estimate and 2D SSB estimate respectively in comparison to a 1D $( - 3 . 8 \% \mathrm { S W H } )$ benchmark.The variance explained by the SSB corrections in HY-2A IGDR data is also given.

Crossover SSH differences are the main tool to analyze the whole altimetry system performance.They allow us to analyze the SSH consistency between ascending and descending passes [5]. Fig.6 gives the standard deviation (STD) of the crossover SSH differences after using different SSB corrections. Results are obtained cycle per cycle. Obviously,the 3-D SSB estimates can greatly reduce the STD of the crossover SSH differences.

![](images/d212913605d18edd8d3dbe6df33d74019547088bba25708c5ab4aa68df375a34.jpg)  
Fig.6 The standard deviation (STD） of the crossover SSH differences after using 3-D SSB estimates,2-D SSB estimates and the SSB corrections in HY-2A IGDR data respectively.

Along track analyze is also used to assess the altimeter system performance by computing the sea level anomalies (SLAs). SLAs are computed along track by subtracting the mean sea surface(MSS） from the instantaneous SSH measurements.The SLAs variance gives an estimate of the errors of the system [6].Fig.7 gives the STD of SLAs after using different SSB corrections.The STD of SLAs can be reduced after replacing the traditional 2-D SSB estimates with the 3-D SSB estimates.

![](images/f0fa8c5551014d79ba7456735d5339a75769c0f84adeac58f41f28ccbbde998e.jpg)  
Fig.7 The standard deviation (STD） of the along-track sea level anomalies (SLAs) after using 3-D SSB estimates,2-D SSB estimates and the SSB corrections in HY-2A IGDR data respectively.

# 5.CONCLUSIONS

This paper estimates the SSB of HY-2A radar altimeter using a 3-D nonparametric model. Crossover SSH differences are used to develop the SSB model. Compared with the traditional 2-D SSB estimates,the 3-D SSB estimates can greatly reduce the STD of the crossover SSH differences and SLAs.Therefore,the 3-D SSB estimates can improve the precision of HY-2A altimeter product.

# REFERENCES

[1] P. Gaspar,F. Ogor, P.Y.Letraon,and O. Z. Zanife,"Estimating the Sea-State Bias of the Topex and Poseidon Altimeters from Crossover Differences," Journal of Geophysical Research-Oceans, vol. 99,pp.24981-24994,Dec 15 1994.   
[2]N.Tran,D.Vandemark,B.Chapron,S.Labroue,HFeng,B. Beckley，etal.,"Newmodelsfor satellitealtimeter seastatebias correction developed using global wave model data,"Journal of GeophysicalResearch-Oceans,vol.111,Sep6 2006.   
[3]P.Gaspar and J.P.Florens,"Estimation of the sea state bias in radar altimeter measurements of sea level:Results from a new nonparametric method," Journal ofGeophysical Research-Oceans, vol.103,pp.15803-15814, Jul 15 1998.   
[4]P.Gaspar,S.Labroue,F.Ogor,G.Lafitte,L.Marchal,and M.Rafanel, "Improving nonparametric estimates of the sea state bias in radar altimeter measurements of sea level,"Journal of Atmospheric and Oceanic Technology，vol.19,pp.1690-1707,Oct 2002.   
[5]M.Ablain,S.Philipps,N.Picot,and E.Bronner,"Jason-2 Global Statistical Assessment and Cross-Calibration with Jason-1," Marine Geodesy,vol.33,pp.162-185,2010.   
[6]J.Dorandeu,M.Ablain,Y.FaugeRe,F.Mertz,B. Soussi,and P.Vincent,"Jason-1 global statistical evaluation and performance assessment: Calibration and cross-calibration results," Marine Geodesy，vol.27,pp.345-372,2004/07/01 2004.