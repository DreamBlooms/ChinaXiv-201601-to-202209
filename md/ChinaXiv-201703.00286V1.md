# TEMPERATURE AND HUMIDITY PROFILES RETRIEVING OVER LAND USINGCLEAR SKYMEASUREMENTS OFMICROWAVE HUMIDITY-TEMPERATURESOUNDERONCHINESEFY-3CSATELLITE

Qiurui $H e ^ { I , 2 }$ , Zhenzhan Wang', Jieying $H e ^ { I }$ 1. CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing,100190, China 2. University of Chinese Academy of Sciences, Beijing,1Oo049, China.

# ABSTRACT

# 1.INTRODUCTION

An one-dimensional variational retrieval system was developed to retrieve the clear sky atmospheric temperature and humidity profiles over land using the measurements of microwave humidity-temperaturesounder(MWHTS) on Chinese FY-3C satellite. The system parameters are configured by analyzing the MWHTS channel properties and the climate condition over land. The retrieval results are evaluated by root mean square error (rmse） with respect to European Centre for Medium-RangeWeatherForecasts(ECMWF) reanalysis data. The validated results show that the maximum root mean square error of temperature and humidity are 2.59K and $1 1 . 8 7 \%$ ，respectively. The retrieval results,compared with National Centers for Environmental Prediction(NCEP）6 hour forecast profiles，show that the background profiles can affect the accuracy of retrievalprofliesand FY-3C/MWHTS measurements canimprove forecast precision of humidity.

Index Terms— FY-3C/MWHTS, one-dimensional variational retrieval system,clear sky, temperature and humidity profiles, land

Temperature and humidityplayavery important role in meteorological research. Such parameters may not only be used to assess the atmospheric stability and to assist in nowcasting of convective weather but also to monitor climate[1]. There are a lot of public literature researching on retrieving these two parameters usingsatellite measurements[2,3].Physical retrieving is considered to be the basic method which obtain the atmospheric parameters by solving the radiative transfer equation, and to be the most effective way to improve retrieval accuracy. The FY-3C satellites was successfully launched on 23 September 2013 and carries the Microwave humidity-temperature sounder onboard whose measurements can be used to retrieve the atmospherictemperature and humidityprofiles simultaneously[4].

In this paper, we first analyze the parameters of anone-dimensional variational retrievial system which affect the retrieval accuracy,and then choose the optimum parameter combinations for MWHTS. Theretrieval system of MWHTS use the measurements of China land in clear sky to retrieve the temperature and humidity profiles，and the preliminary results show that this system has higher accuracy.

# 2.ONE-DIMENSIONALVARIATIONAL RETRIEVALSYSTEM

# 2.1 one-dimensional variational retrieval system mathematicalbasis

Theone-dimensionalvariationalretrieval system employs the RTTOV as the forward radiative transfer model to calculate the simulated brightness temperatures.The iterative process of this system used in this paper aims at minimizing the following cost function[3]:

$$
\begin{array} { l } { { \displaystyle { J ( X ) = [ \frac { 1 } { 2 } ( X - X ^ { B } ) \times B ^ { - 1 } \times ( X - X ^ { B } ) ] + } } } \\ { { \displaystyle { [ \frac { 1 } { 2 } ( Y ^ { o } - Y ( X ) ) ^ { T } \times E ^ { - 1 } \times ( Y ^ { o } - Y ( X ) ) ] } } } \end{array}
$$

where $X ^ { B }$ and $B$ are the background and error covariance matrix of $X$ ，which is the parameter to be retrieved， respectively. $E$ is the measurement error covariance matrix,including the observation error covariance matrix and the modeling error covariancematrix. $Y ^ { o }$ and $Y ( X )$ are the observationsandsimulatedmeasurements. The minimization of this cost function is the basis for the variational retrieval. The solution that minimizes this cost function is found by solving for

$$
\frac { \partial J ( X ) } { \partial X } = 0
$$

This results in the following solution:

$$
\begin{array} { r l } & { \Delta X _ { n + 1 } = [ B K _ { n } ^ { T } ( K _ { n } B K _ { n } ^ { T } + E ) ^ { - 1 } ] } \\ & { \times [ ( Y ^ { O } - Y ( X _ { n } ) ) + K _ { n } \Delta X _ { n } ] } \end{array}
$$

where $n$ is the iteration index. $K$ ，in this case,is the Jacobian or the derivative of $Y$ with respect to $X$

# 2.2 one-dimensional variational retrieval system parameters

In this paper, in order to assess the accuracy improvement of NCEP 6 hour forecast profiles by the retrieval, the retrieval system selects the NCEP 6 hour forecast profiles as the background profiles. Thebackgrounderrorcovariancematrixis generated using ECMWF reanalysis data, the exact formula is given as follows [3]:

$$
\sigma _ { i j } ^ { 2 } = \frac { 1 } { N } \underset { i = 1 } { \overset { N } { \sum } } \underset { j = 1 } { \overset { N } { \sum } } ( x _ { i } - \overline { { x } } _ { i } ) \times ( x _ { j } - \overline { { x } } _ { j } )
$$

where $\sigma _ { i j } ^ { 2 }$ is one of the elements of the matrix corresponding to row $i$ and column $j$ ： $N$ is the number of profiles,and $\overline { { x } }$ is the average value along the row or along the column.

For the difference between the observations and the simulated brightness temperatures,a statistic regression method is proposed to correct the bias piexl by piexl. The exact formula is given in the following[5]:

$$
\begin{array} { r } { T _ { i j } ^ { * } = a _ { i j } T _ { i j } + b _ { i j } a b } \end{array}
$$

where $\boldsymbol { T } _ { i j } ^ { * }$ are the correct MWHTS brightness temperatures and $T _ { _ { i j } }$ are the original observed brightness temperatures, $i$ is channel index and $j$ is pixel index. $a$ and $b$ are the slope and intercept coefficients，respectively. The measurement error covariance matrix is generated using the forward model error and the channel noise.

# 2.3 convergence check

The following quantity is computed to check the convergence

$$
\frac { \left| J _ { n + 1 } - J _ { n } \right| } { J _ { n } } < 0 . 0 1
$$

That is,if the relative value of the cost function changes within O.O1,and the maximum number of iteration is less than 1O, then the iteration is stoped, and the retrieval is set to the background profiles.

# 3.RETRIEVALACCURACYANDERROR ANALYSIS

In thispaper，root mean square erroris considered as the standard quantification to validate the retrieval with ECMWF ERA Interim reanalysis data. FY-3C/MWHTS data from April and May 2015 were used in a detailed comparison between MWHTS sounding profiles and ECMWF reanalysis profiles，as well as the background profiles.Only MWHTS data in clear sky over China land within 0.5h of ECMWF reanalysis data and $0 . 0 5 ^ { \circ }$ latitude/longitude are used in retrieval validation. Fig.1 shows the vertical distribution of rmse of the retrieval profiles and the background profiles with respect to ECMWF reanalysis data. The accuracy of the retrieval is 2.59K for the temperature and $1 1 . 8 7 \%$ for the relative humidity. The validated results show that this retrieval system has higher accuracy. The rmse ofthe retrieval for humidity profilesis smaller than that of the background profiles, especially from $2 5 0 \ \mathrm { h P a }$ to $7 5 0 \mathrm { { h P a } }$ ， this suggests that the retrieval for humidity can improve the background profiles,i.e.NCEP 6 hour forecasts profiles.

![](images/e0925bd5b80f81c46034ec63114304f9ffff42edf0b4231c204ed6b6fb01807d.jpg)  
Fig.1 Retrieval results

![](images/0880a089cff8a870596d4e7b6cda12184e613b8e1515222a558126443d21d048.jpg)  
Fig.2 The effect of background profiles on the retrieval accuracy

In order to assess the effect of the background profileson the retrieval accuracy， we use the ECMWF reanalysis data as the background profiles to get the retrievals.The validated resultsare show in Fig.2. The rmse of the retrieval is decreased compared with that in Fig.1,especially for humidity profiles,which show that the background profiles which can bring a serious error are important to the retrieval system.

# 4.CONCLUSION

The paper built an one-dimensional variational retrieval system for FY-3C/MWHTS to retrieve the atmospheric temperature and humidity profiles in clear sky over land. The retrieval has higher accuracy,and can improve the accuracy of NCEP 6 hourforecastprofiles,therefore,FY-3C/MWHTS is significant to numerical weather prediction. The background profiles,which are major error sources, can affect retrieval accuracy, we can select another data source which has higher accuracy with respect to the true state of atmosphere as the background profiles to improve the performance of the retrieval systeminthe furtherresearch.

# 5.REFERENCES

[1] Alexander Polyakov, Yurii M. Timofeyev, Yana Virolainen. Comparison of different technique in atmospheric temperature-humiditysensing from space， International Journal of Remote Sensing, vol. 35, no. 15, pp. 5899-5912, 2014. [2]Fatima Karbou,Filipe Aires, Catherine Prigent. Potential ofAdvancedMicrowaveSounding Unit-A(AMSU-A) and AMSU-B measurements for atmosp-heric temperature and humidity profiling over land. Journal of Geophysical Research,vol.

110,no.D7, pp. d0710901-d0710916,2005. [3] Sid-Ahmed Boukabara,Kevin Garrett,Wanchun Chen, etal. MIRS: An All-Weather 1DVAR Satellite Data Assimilation and Retrieval System[J]. IEEE Transactions on Geoscience and Remote Sensing, vol. 49,no.9, pp. 3311-3333,2011. [4] Bao J H. The principle of FY-3C satellite microwave humidity and temperature sounder and preliminary analysis on its in-orbit performance. Beijing: National space science center, Chinese Academy of Sciences,2014. [5] Jun Li, Walter W. Wolf. Global Sounding of the Atmosphere From ATOVS Measurements: The Algorithm and Validation， Journal of Applied Meteorol0gy, vol. 39, no. 8, pp. 1248-1268,2014.