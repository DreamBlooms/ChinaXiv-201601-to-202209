# International time transfer of the Galileo initial service Based on the PPP method

Ouyang Mingjun1,2.3,Sun Baoqi1,2,4,\* Ge Yulong1,2,3, Yang Xuhai1,2,4

1 National Time Service Center, Chinese Academy of Sciences, Xi'an 710600,China   
2 Key Laboratory of Precise Navigation, Positioning and Timing Technology, Chinese Academy of Sciences, Xi'an 71060o, China 3 University of Chinese Academy of Sciences, Beijing 1Ooo49, China   
4 School of Astronomy and Space Science, University of Chinese Academy of Sciences, Beijing 100049, China \*Corresponding author, e-mail: sunbaoqi@ntsc.ac.cn

Abstract: The Galileo initial service is officially launched in December 15, 2016, by the European Commission (EC)，owner of the European Galileo global navigation satellite system. This paper performs various experiments to test the Galileo initial service using the Precise Point Position (PPP) method and selecting the time transfer links,and investigate its feasibility for the international time transfer. The time transfer links are constituted of the PTBB site and MEGX sites connected with high-precision atomic clocks. We consider the results of the GPS PPP as reference,with a total of 138 days observation data, i.e. from December 15,2016 to May 1,2017. To investigate the reliability of the Galileo PPP based on the International UTC/TAI, we will design and carry out seven solutions with different options on the parameter selection， products utilization and the frequency selection. The experimental results show that the STD (Standard Deviation) ranges from 0.2ns to 0.5ns. This means, the PPP method reduces the time transfer of the service of the international to nanosecond.

Keywords: Galileo, precise point positioning, international time transfer, initial service

# 1. Introduction

The precise point positioning (PPP） technology is firstly proposed by

Zumberge in the Jet Propulsion Laboratory (JPL） in 1997 [1]. The positioning accuracy of this technology may reach 1cm in the horizontal direction and $2 \mathrm { c m }$ in the vertical direction using the dual frequency code pseudo-range,carrier phase observations， the precise satellite orbit and the clock products of the IGS (International GNSS Service） [2]. To compare the Universal Time Coordinate (UTC) and the International Atomic Time (TAI), the Bureau International des Poids et Mesures proposed to test the carrier phase time transfer link at the CCITT conference, and official published results and data from 20O6 on FTP [2]. Afterwards, the PPP technology has been applied to the field of time transfer, and in 2009, the GPS PPP was distinguished as one of the International Atomic Time routine delivery technologies [2].

According to the BIPM official website, by the end of February 2017 more than 76 time Laboratories participate in the comparison of the Universal Time Coordinated (UTC) and the International Atomic Time (TAI). Among them, 28 laboratories apply the GPS PPP method and 10 laboratories use a method which is the combination of the TWSTT (the two-way satellite time transfer) and the GPS PPP [2]. Currently, only the observed values of the GPS and the GLONASS are used in the international time transfer link with the PPP method. However, there is lack of study in the BDS and the Galileo system time transfer, as the research and application of the PPP method of the time transfer are mostly based on the GPS and GLONASS. The CSRS-PPP software developed by the Canada resources environment research center, are used for the International Atomic Time comparison trial by BIPM[3]. From 2004 to 2006, Jiang Zhiheng and G.Petit adopted the GPS PPP for the time transmission, and achieved a sub-nanosecond time transfer accuracy，and pointed out that the GPS PPP provides a higher accuracy than the TWSTFT for short-term stability [4]. In 2014, Guang Wei in the National time service center (NTSC), Chinese Academy of Sciences, performed the experiment on the BDS PPP and showed that short time transfer stability of the BDS PPP may reach 1E-13/960s,1E-14/day [5].

The Multi-GNSS Experiment and Pilot Project (MGEX) provides multiple system orbits and clock products,as well as part of the international time link time Laboratories such as PTB，ROA，ROB，CNES,and NTSC receiver observations contain multiple system observation data. This provides the possibility of exploring new navigation systems such as the Galileo and the BDS

for time transmission.

Considering the announcement of the Galileo initial service, this study designs and carries out seven solutions to investigate the reliability of the Galileo PPP method on the International UTC/TAI comparison, referring to the GPS PPP.

The rest of this paper is organized as follows. Section 2 presents the time transfer principle of the PPP method. Next, the data processing strategy and the method of evaluation will be described in Sec. 3. Then, Sec. 4 investigates the performance of the Galileo PPP, and analyses the time transfer results of 7 solutions and compares them within 138 days. Finally, Sec. 5 concludes the paper.

# 2.Time transfer basedon PPP method

Figure 1 shows the principle of the time transfer based on the PPP method. The Conventional PPP method is applied for the geodetic survey [6]-[8]. Such system performs the time and frequency transfer, where receivers of each station are connected to their time and frequency reference generators, e.g. 1 PPS signal and $5 / 1 0 ~ \mathrm { M H z }$ frequency signal [5]. Each station calculates its clock difference between the UTC(i) and the IGST and achieves the difference between them. This may be expressed as

![](images/d3aca9b2eb33b2160713997d5e07ede2d0ba5e2e861d5549cb1c00bf931689a1.jpg)  
Figure 1.Principle of the PPP time transfer.

# 3. Data and processing strategy

# 3.1. Observation data and sites

Figure 2 illustrates the distribution of selected sites for this trial. Currently, the PTBB is the center node of the international time comparison link in the international time comparison link of the time laboratory site. Considering the prerequisite of the Galileo, i.e. the tracking ability and external high precision time reference,we choose eight GNSS tracking stations from the IGS tracking network and the TAI international network. We prepared thirty-second sampling interval observation for processing,within 138 days,i.e. from the beginning of December 15, 2016 until the end of May 1, 2017.

![](images/a6af7c817753ebe4ba93c97816be0c151d0f1a54cb0c62cb6d19d077c41e8280.jpg)  
Figure 2.Distribution of different sites chosen for the trial.

Table 1 lists the receiver type and the external atomic clock of the selected sites in Fig. 2.

Table 1.The equipment of the selected sites.   

<html><body><table><tr><td>Station</td><td>Receiver</td><td>Clock</td></tr><tr><td>PTBB</td><td>SEPTPOLARX4TR</td><td>H-MASER</td></tr><tr><td>BRUX</td><td>SEPTPOLARX4TR</td><td>CESIUM</td></tr><tr><td>ROAP</td><td>SEPTPOLARX4TR</td><td>H-MASER</td></tr><tr><td>TLSE</td><td>SEPTPOLARX4TR</td><td>DORIS</td></tr><tr><td>DLF1</td><td>TRIMBLENETR9</td><td>CESIUM</td></tr><tr><td>GMSD</td><td>TRIMBLENETR9</td><td>CESIUM</td></tr><tr><td>NNOR</td><td>SEPTPOLARX4</td><td>CRYSTAL</td></tr><tr><td>USN8</td><td>SEPTPOLARX4TR</td><td>H-MASER</td></tr></table></body></html>

# 3.2. Solution strategy

The BIPM provides the 3O days arc solutions of the GPS PPP, which uses the IGR products provided by the IGS about the station in the international timing laboratories (ftp://ftp2.bipm.org/pub/tai/). In this experiment, we applythe adaptation of Bernese5.2 software of the iGMAS Analysis Center of NTSC, Chinese Academy of Sciences. The validation of the availability of this software applied to the time transfer is reported in the paper of feasibility analysis of BDS PPP in the international time comparison [9]. The data preprocessing tactics contains the Melbourne-Wubbena Linear Combination L6 which is judgment of the cycle slip or gross errors, Geometry-Free Linear Combination L4 which is used to detect the size of cycle slip and Ionosphere-Free Combination L3 which detects residual crude caused by the coarse code observations.Finally, this trial smooths the observational data code using the carrier phase observation data.

The unknown parameters include the station coordinates, troposphere zenith, receiver clock error and the carrier phase ambiguity.Table 2 lists the details of the solving strategy of the PPP.

Table 2.The solution strategy of the Galileo PPP time transfer.   

<html><body><table><tr><td>Items</td><td>Descriptions</td></tr><tr><td>Number of stations</td><td>8</td></tr><tr><td>Estimator</td><td>Least squares (LSQ) estimator</td></tr><tr><td>Observables</td><td>Ionosphere-free combined observation for code and phase observations</td></tr><tr><td>Signal selection</td><td>GPS: L1/L2; Galileo: E1/E5a,E1/E5b;</td></tr><tr><td>Elevation cutoff</td><td>3°</td></tr><tr><td>Phase wind-up</td><td>Corrected [10]</td></tr><tr><td>Tropospheric delay</td><td>ZHD: corrected with GMF model [11]</td></tr></table></body></html>

<html><body><table><tr><td></td><td>ZWD: estimated as a continuous piece-wise linear function (2h parameter spacing), GMF mapping function [11]</td></tr><tr><td>Tidal displacements</td><td>Solid earth tide,pole tide, ocean tide loading corrections refer to the IERS Conventions 2010 [12]</td></tr><tr><td>Relative effect</td><td>Corrected</td></tr><tr><td>Sagnac effect</td><td>Corrected</td></tr><tr><td>Satellites antenna PCOs and PCVs</td><td>PCO and PCV corrections for the GPS from igs08.atx</td></tr><tr><td>Receiver clock</td><td>Estimatedaswhitenoise</td></tr><tr><td>Station coordinates</td><td>Estimated as static</td></tr><tr><td>Phase ambiguities</td><td>Estimated, float value</td></tr></table></body></html>

Next, we select seven strategies to further investigate the unknown parameters. These parameters represent the impacts of the solving strategy for the Galileo PPP time transfer and include the analysis center products, sampling interval of the precision clock, frequency selection and other aspects. Table 3 shows these parameters. The Galileo PPP is implemented by different precise products for the solutions 1,2,3 and 4.Moreover, we consider the GPS PPP solutions as the external values. The purpose is to investigate the impact of the time transfer on constrain of the troposphere and coordinate. To investigate the effect of Galileo PPP by using different products, frequency and sampling rate of clock. the experiment of solutions5, solutions6, solutions7 and solutions8 were done.

Table 3.Seven solutions selected for the test.   

<html><body><table><tr><td></td><td>GBM</td><td>COM</td><td>With coordinate fixed</td><td>With tropospher e fixed</td><td>Both fixed</td><td>30s clock</td><td>300s clock</td><td>E1/E5b</td></tr><tr><td>Solution 1</td><td>×</td><td></td><td></td><td></td><td></td><td>×</td><td></td><td></td></tr><tr><td>Solution 2</td><td>×</td><td></td><td>X</td><td></td><td></td><td>×</td><td></td><td></td></tr><tr><td>Solution 3</td><td>×</td><td></td><td></td><td>×</td><td></td><td>X</td><td></td><td></td></tr><tr><td>Solution 4</td><td>×</td><td></td><td></td><td></td><td>×</td><td>×</td><td></td><td></td></tr><tr><td>Solution 5</td><td>×</td><td></td><td></td><td></td><td></td><td></td><td>×</td><td></td></tr></table></body></html>

<html><body><table><tr><td>Solution 6</td><td>X</td><td></td><td></td><td></td><td></td><td>X</td><td></td><td>X</td></tr><tr><td>Solution 7</td><td></td><td>×</td><td></td><td></td><td></td><td></td><td>×</td><td></td></tr></table></body></html>

# 3.3.Evaluation method

It should be noted that, regardless of the day boundary discontinuity, this paper considers the difference between the time links of the Galileo PPP and the GPS PPP methods. The specific calculation formula for this difference reads

$$
S T D = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( x _ { i } - \mu ) ^ { 2 } }
$$

In equation (2), $x _ { i }$ represents the whole time series of this test which are the difference between the time links of the Galileo PPP and the corresponding time links of the GPS PPP, $N$ represents the number of time series,and $\mu$ denotes the average of the time series.

# 4.Results and Analysis

# 4.1.Statisticalresults

Figure 3 shows the experimental results for the STD, the difference between the Galileo PPP method and the GPS PPP. We designed and performed seven solutions,according to different options on parameter setting, products using and frequency selection in this test, the experimental results show that the STD ranges from O.2ns to O.5ns.It means that the international time transfer based on the Galileo system of initial service with PPP method is reliable.

![](images/702a1e00b3181ceb3f74243a11a787cbc36eebf760157d8042892fe3193be3be.jpg)  
Figure 3. Statistical results of the STD in eq.(2) for 7 solutions.

Figure 4 plots the skyplot and number of visible satellites in the PTBB site, DOY 350, 2016. In this figure, charts A and C present a skyplot and satellite visible number of the GPS, while charts B and D plot the skyplot and satellite visible number of the the Galileo respectively, in December 15, 2016 in the PTBB site. It may be seen from these diagrams that, considering the structure of the current GPS and the Galileo system, the number of the GPS visible satellites is much larger than that of the Galileo system. It is desirable and exciting that the Galileo used for the time transfer provides such magnitude.

![](images/b7eaaac476382829d98f9b599b3ba15e05a5fa55fad80e11965378b4ce163d00.jpg)

![](images/e1231ed327fe3c0256ced265680032da12a290f6c96cf4275fcf7a4da52ec22a.jpg)  
Figure 4.The skyplot and number of visible satellites in the PTBB site,DOY 350,2016.

(a) Skyplot of the GPS. (b) Skyplot of the Galilio. (c) Number of visible satelites of the GPS. (d) Number of visible satellites of the Galilio.

# 4.2.Statistic of the STD, RMS and Mean of solution 1

Table 4 lists the statistical result of solution 1,i.e.with the GBM products,30s clock and E1/E5a. Since the paper emphasizes on the analysis of the time transfer stability, and the equipment delay and other system errors are not calibrated, some of the RMS and Mean results are less than one nanoseconds and some reach to 20ns.The STD of the time series calculated by the difference of the Galileo PPP and the GPS PPP ranges between 0.2ns and 0.5ns.

Table 4 Galileo PPP- GPS PPP statistical results with solution1   

<html><body><table><tr><td>Time links</td><td>STD/ns</td><td>RMS/ns</td><td>Mean/ns</td></tr><tr><td>PTBB-BRUX</td><td>0.2879</td><td>1.9300</td><td>-1.9084</td></tr><tr><td>PTBB-DLF1</td><td>0.3846</td><td>26.6341</td><td>26.6314</td></tr><tr><td>PTBB-GMSD</td><td>0.5210</td><td>21.3306</td><td>21.3242</td></tr><tr><td>PTBB-NNOR</td><td>0.4664</td><td>0.4687</td><td>-0.0467</td></tr><tr><td>PTBB-ROAP</td><td>0.3709</td><td>0.3995</td><td>0.1484</td></tr><tr><td>PTBB-TLSE</td><td>0.4717</td><td>18.6876</td><td>18.6816</td></tr><tr><td>PTBB-USN8</td><td>0.4369</td><td>3.7238</td><td>-3.6981</td></tr></table></body></html>

![](images/509aaefd8d72c88d540bc097fba28599d45965d91616caafe325f124e0c2c1ff.jpg)  
Figure 5Time series ofGalileo PPP-GPS PPP with solution1

Figure 5 plots the time series which is the difference between the time links of the two PPPs,i.e. the GPS PPP and the Galileo PPP. It may be seen that the results of solution 1 are relatively stable within the whole 138 day for 7 time links. The missing results of some links are due to the lack of the observation data and the poor quality failure solution.

# 4.3.Comparison of solutions

# 4.3.1. Comparison between the coordinate and the troposphere fixed

Figure 6 compares the coordinate and the troposphere fixed and shows statistic of the results. The left chart of this figure plots the time series and its STD statistic of the Galileo PPP - GPS PPP with the time link PTBB-BRUX, considering different solutions,i.e. the unfixed, coordinates fixed, troposphere fixed and both fixed. Figure 6 reveals that, the three fixed solutions,i.e. the coordinates fixed, the troposphere fixed and both fixed, smooth the time links comparison results. The right chart of Fig. 4 shows that, the STD decrease compared with parameters not be fixed. The main reason is that, reducing the number of the parameters to be estimated leads to the improvement of the structure of the equation and the redundancy of the data, and thus, provides relatively better calculation results.

![](images/2df6c170c0c3ab4d479381c9babe22bd6bae5c735fa2e43c2095f5052016f2d6.jpg)  
Figure 6. Comparison between the coordinate and the troposphere fixed and statistic of the results.

Figure 7 compares the statistical results of the STD with different solutions. We may see that the result of the time links differences is below O.lns with different MGEX products in the A diagram. The differences in the accuracy and the satellite statistics between different analysis centers do not affect the result of the time links of the Galileo system. This may provide the same conclusion as the experimental study on the BDS PPP in the international time comparison [9].

# 4.3.2 Comparison of 30s clock and 300s clock

It is previously reported that in the short term，in comparison with the 5 minutes sampling rate satellite clock products, the 3O seconds sampling rate satellite clock products significantly improves the static PPP clock solutions of the frequency stability. It is seen from the B diagram in Fig. 7 that, the calculation results of the STD are larger than 30Os clock of the reference of the 3Os clock.

# 4.3.3.Comparison of E1/E5a and E1/E5b

Next, we choose two solutions for the comparison of the frequency combination, where the difference of the STD is mainly caused by the noise level. The frequency E1/E5b presents higher noise level in comparison with the E1/E5a. Fig. 7(c) reveals that the time links are solved with the E1/E5b frequency points, where the statistical STD is larger than that of the E1/E5a frequency points.

![](images/68246bc4dd4f1a310289de47c8a2278970dbca762d1df436a45f2eae73f69565.jpg)  
Figure 7. Statistical comparison results of the STD with different solutions.

# 5.Conclusion

We investigated the performance of the Galileo PPP applied to the time transfer, which its initial service was offcially announced in December 15, 2016. The GPS PPP results are considered as reference in our experiments.We designed seven solutions, where the STD of the time series calculated by the difference between them ranges from O.2ns to O.5ns. This reveals that the Galileo of initial service with PPP method is capable of reducing the service of international time transfer to less than one nanosecond. It is observed that, taking a fixed coordinate or fixed troposphere strategy, using 3Os the sampling clock products,using the

E1/E5a dual frequency data for the Galileo PPP, the time transfer provides better results. With the high-speed development of the Galileo in recent years, the time transfer based on the Galileo PPP technology will play an important role in the remote time transfer among the time laboratories, where this article made a preliminary exploration.

Acknowledgments The authors gratefully acknowledge the IGS MGEX and BIPM for providing products and data.

# References

[1]Zumberge JF，H.M.， Jefferson DC，Watkins MM，Webb FH,1997.Precise point positioning for the efficient and robust analysis of GPS data from large networks. J Geophys Res B3, 5005-5017.   
[2] https://www.bipm.org   
[3]htp://www.geod.nrcan.ca   
[4] Petit,G.， Jiang，Z.，2008.GPS All in View time transfer for TAI computation. Metrologia 45, 35-45.   
[5]Guang,W. Zhang, P., Yuan, H.,Li, W., Zhang, Q., Huang, G., Zhang,R., 2014. The Research on carrier Phase time tranfer of BeiDou navigation statellite system. European Frequency and Time Forum (EFTF),2014.IEEE,2014.   
[6] Cai，C.，Gao，Y.， Pan，L.， Zhu，J.，2015. Precisepoint positioning with quad-constellations: GPS,BeiDou，GLONASS and Galileo. Advances in Space Research 56,133-143.   
[7]Ge，M.，Gendt, G.，Rothacher， M.， Shi,C.，Liu,J.，2007. Resolution of GPS carrier-phase ambiguities in Precise Point Positioning (PPP) with daily observations. Journal of Geodesy 82, 389-399.   
[8]Li，X.，Zhang，X.，Ren，X.，Fritsche，M.，Wickert, J.，Schuh，H.，2015b.Precise positioning with current multi-constellation Global Navigation Satellite Systems: GPS, GLONASS, Galileo and BeiDou. Sci Rep 5,8328.   
[9]Li,Zhang,FeasibilityanalysisofBDS PPP in international time comparison[D].Beijing:University of Chinese Academy of Sciences,2017.   
[10] Wu, J.T.，Wu, S. C., Hajj,G.A.， Bertiger,W. I.,& Lichten, S. M,1992. Effects of antenna orienation on GPS carrier phase. In Astrodynamics Vol., pp.1647-1660.   
[11] Boehm, J., Heinkelmann, R., Schuh, H., 2007. Short Note: A global model of pressure and temperature for geodetic applications. Journal of Geodesy 81, 679-683.   
[12] Petit, G.,& Luzum,B, 2010. IERS conventions (2010) BUREAU INTERNATIONAL DES POIDS ET MESURES SEVRES (FRANCE).(No.IERS-TN-36).   
[13] Zhang, X., Cai, S., Li, X.x., Guo, F., 2010. Accuracy Analysis of Time and Frequency Transfer Based on Precise Point Positioning. Geomatics and Information Science of Wuhan University 135,274-278.