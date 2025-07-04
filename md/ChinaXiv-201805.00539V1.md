# Enhancement of the Prediction Accuracy of Pole Coordinates withEmpirical Mode Decomposition

Zhao Danning1, ², Lei $\mathrm { Y u } ^ { 1 , 3 }$ , CaiHongbing 1,3 (1. National Time Service Center, Chinese Academy of Sciences, Xi'an 71060o, China; 2. University of Chinese Academy of Sciences, Beijing 100049, China; 3. Key Laboratory of Time and Frequency Primary Standards, Chinese Academy of Sciences, Xi'an 710600, China)

Abstract:This paper is aimed at separation treatment of low- and high-frequency components in polar motion forecasting and thenimproving time-series predictions. For the purpose， the empirical mode decomposition (EMD) is employed as a filter to extract low- and high-frequency signals from original pole coordinate data. The decomposition of the pole motion observations between l986 and 2015 from the International Earth Rotation and Reference Systems Service (IERS) CO4 seriesillustrates that the low-frequency fluctuations including inter-decadal, interannual， Chandler and annual wobbles and shorter-period high-frequency oscillationscan be separated from the observed time-series by the EMD. On the basis of separation, the least-squares (LS) extrapolation of models for annual and Chandler wobbles and for the linear trend are used for deterministic prediction of the low-frequency fluctuations， while the autoregressive (AR) technology is applied to forecasting the high-frequency oscillations plus LS fiting residuals. Pole coordinateforecasts are calculated as the sum of LS extrapolation and AR predictions (LS+AR).We have evaluated the accuracy of our long-term predictions (up to 1 year in the future) in comparison with the IERS official predictions in terms of year-by-year statistics of 5 years.It is shown that the accuracy of the ${ \mathrm { L S } } { \mathrm { + A R } }$ methodcan be significantly improved using a combination of the EMD and $\mathrm { L S ^ { + } A R }$ 1 $( \mathrm { E M D + L S + A R } )$ ．Also，the proposed prediction strategyoverall outperforms the IERS solutions. In addition, the predictions are compared with those from the Earth Orientation Parameters Prediction Comparison Campaign (EOP PCC). The comparison demonstrates that the developed schemeis a very accurate approach to predict polar motion. According to this study, it is concluded that polar motion predictions may be enhanced through separation treatment of different time-scale fluctuations and thus such processing sems to be necessary in pole coordinate prediction.

KeyWords: Polar Motion; Prediction; Empirical Mode Decomposition; Least-squares (LS); Autoregressive (AR) Model

中图分类号：P227.1 文献标志码：

文章编号：

# 1.Introduction

The Earth orientation parameters (EOP): universal time,， pole coordinates and nutation-precession corrections, describe the irregularities of the Earth's rotation. Technically, they are the parameters which provide the rotation of the International Terrestrial Reference System (ITRS) to the International Celestial Reference System (ICRS) as a function of time. EOP derived from modern space geodetic technologies, e.g., Very Long Baseline Interferometry (VLBI), Satellite Laser Ranging (SLR) and Global Navigation Satellite System (GNSS),are not available for users in real-time applications resulting from the complexity of data processing. Since rapid and accurate EOP predictions are required for various fieldsassociated withreference frames such as interplanetary spacecraft tracking and navigation， positional astronomy, geodesy and precise orbit determinations of artificial Earth satellites, it is essential to make high accuracy EOP predictions at least for a few days in the future[1].The currentpaper focuses on predicting， pole coordinatesup to 365 days in the future.Many different prediction approaches and techniques were used in the past to improve the prediction accuracy of polar motion. Most of these prediction approaches and techniques use only information within pole coordinate data, e.g., the combination of the least-squares (LS） extrapolationand autoregressive (AR） model （20 $( \mathrm { L S + A R } )$ ）[2-3land combination of the LS extrapolationand neural network $( \mathrm { L S ^ { + N N } } )$ [4- 5l. It has been reported that the $\mathrm { L S } { + } \mathrm { A R }$ combination is one of the most accurate techniques for pole coordinateforecast [6].

The basic problem in forecasting time-series is the necessity of separation treatment of high- and low-frequency variations[7l. This problem can be addressed by combination of the empirical mode decomposition (EMD)with the ${ \mathrm { L S } } { + } { \mathrm { A R } }$ model. Our work presents a hybrid EMD+LS+AR method for the enhancement of pole variation prediction. In this method, the low-frequency components consisting of the long-term trend, Chandler and annual wobbles determined by the EMD are first fitted and predicted by the LS extrapolation of thelinear polynomial and harmonic model,and then theshort-period and non-cyclichigh-frequency components together with the LS fiting residuals are modelled by the AR technique.The subsequently predicted high-frequency components and LS residuals areadded to the LS extrapolation in order to obtained the predicted values of pole coordinates.The comparison with the existing prediction methods and techniques shows that the presented $\mathrm { E M D + L S + A R }$ approach is atremendous tool for pole coordinate prediction.

# 2. Prediction methodology 2.1 Empirical mode decomposition

The EMD can decompose a signal into a limited number of IMFs whose instantaneous amplitude and frequency are physically meaningful. It works on a simple assumption that, at any given time, the data may have many many coexisting simple oscillatory modes of remarkably different frequency, one superimposed on the other.Each component is defined as an IMF satisfying the following conditions[8]. (1) In whole data set, the number of zero crossings and number of extrema must either be equal or differ at most by one. (2) At any data point, the mean value of the envelope defined using the localminima and the envelope defined using the localmaxima equals zero. With the above definition of an IMF, a signal can be decomposed into many

IMFs through the following sifting process.

Step 1: Identifyingall the local extrema in time-series .

Step 2: Connecting all the local minima (maxima) by a cubic spline line to form the lower (upper) envelopes.

Step 3: Calculating the mean value of the lower and upper envelopes,,and then computing the difference between and as a proto-IMF,,i.e.,

Step 4: Examining whether satisfies the above-mentioned conditions. If it does, can be regarded as an IMF component. If not, the above sifting process is repeated. In the iterating process, is treated as the data in the next iteration:

After times of iterations, and becomes the first IMF, i.e.,

Step 5: Computing the residual and then treating itas the new data, i.e.,

Step 6: Repeatedly applying the decomposition procedure to all subsequent .

The procedure finally stops when the residual becomes a monotonic function or a function with only one extremum from which no more IMF can be extracted. Through the above procedure the original data are decomposed into IMFs and one residual obtained,,which can be either a constant or the adaptive trend, i.e.,

# 2.2 Least-squares extrapolation

In accordance with the EMD-based separated low-frequency components of pole variation data, a LS model may be fitted. As the sampling interval of the International Earth Rotation and Reference Systems Service (IERS)EOP CO4 series are one solar day， we employ the following polynomial-sinusoidal function for LS fitting and extrapolation, i.e.,

where the biasand driftof the linear trend, amplitudes,and phases，of the annual and Chandler wobbles have to be estimated by the LS method using the separated lowfrequency fluctuation data, and ，.

The model is applied to deriving the LS fitting residuals as for all used to fit the LS model. In the process of prediction， is extrapolated to obtain a deterministic prediction of the low-frequency fluctuations.

# 2.3 Autoregressive model

Stationary time-series may be modelled by the AR model of order [ARO]. The technique allows one to capture the temporal dependence within stationary timeseries.A stationary, zero-mean stochastic process (in our case ） is said to be an AR( if it satisfies

(8) where is white noise with zero mean and variance,and are the AR coefficients.

The order can be selected by the information criterion (AIC)[9]. The AIC for an AR( is based on the following statistics:

where is a likelihood function， is a vector of AR coefficients for an AR(, is an estimate of a variance and is a number of points of data. One selectswhich minimizes the AIC statistics. There are several approaches to estimate the AR coefficients; however, we use the Yule-Walker procedure.

The fitted AR model to is applied to forecasting the LS fiting residuals plus the high-frequency oscillations of polar motion using the linear prediction operator. The forecasts for several steps in the future are computed recursively.

# 2.4 Prediction strategy

For prediction of ， pole coordinates, an integrated prediction strategy referred to as $\mathrm { E M D + L S + A R }$ is applied as described in the flowchart of Figure.1. The presented strategy comprises the following stages. In the first stage， the low-frequency components including the annual wobble, Chandler wobble and long-term trend in pole coordinates and the high-frequency signals containing the shorter-period and non-cyclic fluctuations extracted respectively from original data using the EMD algorithm as stated in Section 2.2. In the second stage, the extracted low-frequency Oscillations including the annual and Chandler wobbles are fitted and then extrapolated by the above LS model. In the next step,the AR technique are used to model the LS fittng residuals plus the separated high-frequency components of pole variations,i.e.，. The subsequently forecastedvalues of are then added to the LS extrapolation in order to obtain the predictions of pole coordinates.

![](images/af91502e0d10bda957c390269eaf78b699e2eb6b829417f5a77a509dedcd7026.jpg)  
Figure.1Flowchart of the EMD $+ \mathrm { L S ^ { + } } .$ ARstrategy for pole motion prediction

# 3. Numerical examples and results 3.1 Data description

The IERS publishes daily values of EOP series with a latent of several days after the processing of observations of all advanced space geodetic techniques including GNSS, VLBI and SLR gathered at the permanent tracking stations distributed around the world. The EOP are estimated together with the station coordinates and velocities from each technique. The subsequently estimated EOP from all the above-mentioned techniques are then combined to derive the EOP CO4 solutions[10]. These finally combined EOP solutions are regularly published at the oficial IERS website. In this work, the ， pole coordinate data from the IERS EOP O8 CO4 series are used as data basis to carry out the numerical experiments. The present accuracy of ， pole coordinates is about $3 0 \mu \mathrm { a s }$ for the 08 C04 solutions.

# 3.2 Separation of the low- and high-frequency oscillations in pole coordinates

Taking the pole coordinate as an example, Figure. 2 shows the decomposed results of the 30-year pole variations from January 1,1986 to December 31,2015. It can be seen in Figure. 2 that the pole coordinate can be decomposed into a limited number of IMFs using the EMD algorithm, indicating that the oscillations of different time-scale in the component of polar motion are characterized by a small number of IMFs. As can be found in Figure.2, two of the modes found, namely and ， show a noticeable seasonal oscillation in the range of a few hundreds of milliarcseconds,and thus can be considered as the two dominating oscillations along theand directions, namely annual wobble and Chandler wobble.In addition, we have found that the IMFs,，and with longer periods and the residuals arising from the EMD analysis can be identified as the inter-annual and inter-decadal signals and the long-term“natural” trend in the observations,and the modes ，and with the smaller amplitudes represent the shorterperiod oscillations and the very high-frequency non-wobbling components. It is noteworthy that due to the mode mixing problem in the EMD the mode separation may be difficult when the signal contains components having adjacent periods, as it occurs for the Chandler and annual wobbles. Since here we only focus on separation of the low- and high-frequency oscillations rather than extraction of a particular component, however, this mode mixing problem dose not limit our analysis.

A spectral analysis of the IMFs plus based on fast Fourier transform (FFT) is exhibited in Figure. 3.In comparison，we also perform a similar analysis of the original data as given in Fig. 3. Visually， pluscontains indeed contains the two dominant oscillating modes, i.e., Chandler and annual wobbles, with the same periods and amplitudes as the original observations do. Therefore, these finds confirm that the oscillating feature hidden in polar motion can be visually characterized by some Oscillatory IMFs having particular physical meaning. To extract the high-frequency components of pole coordinates the IMFs ， and are reconstructed, while the other modes are counted up to gain the low-frequency oscillations including the long-term trend,Chandler and annual wobbles.Figure.4 depicts the separated low-frequency time-series,high-frequency time-series of the ， pole coordinates as well as the raw data.Their plots in Figure. 4 suggest that the low-frequency components including the Chandler wobble,annual wobble and long-term trend can be described by a low-order polynomial and harmonic model, while the AR technique is suitable for modelling the high-frequency terms.

(a) Original observations (b)imf, se/x 00 >>W>>> se/ 0.00 io -0.5 -0.002 1980 1985 1990 1995 2000 2005 2010 2015 2020 1980 1985 1990 1995 2000 2005 2010 2015 2020 (c) imf (d)imf   
80 +车 8 \*+0++- 1980 1985 1990 1995 2000 2005 2010 2015 2020 1980 1985 1990 1995 2000 2005 2010 2015 2020 (e)imf4 (f)imfs se/ /ju! 0.5 0.5 W >>\~>>>>< r <>?<><> W 1980 1985 1990 1995 2000 2005 2010 2015 2020 1980 1985 1990 1995 2000 2005 2010 2015 2020 (g)imf (h)imf7   
se/ 0.0 0.05 > 8 1980 1985 1990 1995 2000 2005 2010 2015 2020 1980 1985 1990 1995 2000 2005 2010 2015 2020 (i) imf (imf   
se/ 000 se/ -0.02 0.02 1980 1985 1990 1995 2000 2005 2010 2015 2020 1980 1985 1990 1995 2000 2005 2010 2015 2020 year 0.10 （k） se/ 0.05 0.00 1980 1985 1990 1995 2000 2005 2010 2015 2020 year

Figure.2Original pole coordinate and its IMFs arising from the EMD algorithm

![](images/52a86c170d5472ffeba905e37cc19c94d9e83842687af12efe06d508d096a7c5.jpg)  
Figure. 3Spectral analysis of the oscillatory IMFs andoriginal pole coordinates

![](images/a6db0b6c5d8957490a883e1d6edb70e0690d42c42a5166b4753546d9b125ada5.jpg)  
Figure. 4 Original， pole coordinates， the low- and high-frequency components

# 3.3Predictionresults

EOP 08 CO4 series serve as data basis and the length of base data is 1O years. The predictions of ， pole coordinates are generated by means of the two prediction schemes: ${ \mathrm { L S } } + { \mathrm { A R } }$ and $\mathrm { E M D + L S + A R }$ .The length of all predictions is equal to 365 days.In order to compare with the official predictions from the IERS Bulletin A, whichcontains EOP predictions for 1 year into the future at daily intervals and is issued by the IERS Rapid Service/Prediction Centre at the U.S. Naval Observatory (USNO), all 365-day predictions of pole coordinate data are calculated every week at different starting prediction epochs from January 7， 2011 to December 31, 2015because theIERS Bulletin A gives an advanced solution updated weekly.The comparison of the polar motion predictions is carried out by means of the analysisof: (1) the absolute values of differences between the pole coordinate data from the EOP 08 C04 series and their forecasts,and (2) mean absolute error (MAE) prediction errors defined by the following[6]

where is the starting prediction epoch， isthe number of -step predictions, is the -step prediction of polar motion and is the corresponding observation of the IERS EOP C04 series.In our analysis,.

The maximum absolute valuesof the differences between the pole coordinate dataandtheir $\mathrm { L S } { + } \mathrm { A R }$ predictionscalculatedatdifferentstarting epochsexceed98mas.The larger differences are for the selected polar motion forecasts with predictions lengths greater than 5 months (Figure. 5). In the case of the polar motion predictions published by the IERS Bulletin A, the maximum values of the differences between the data and IERS predictionsdo not exceed 91mas and those differences are smaller than those computed for our ${ \mathrm { L S } } { + } { \mathrm { A R } }$ scheme (Figure. 6).For the tested data span, the combination of the EMD and $\mathrm { L S } { + } \mathrm { A R }$ model produces polar motion predictions with maximum absolute differences of less than 87masand the extreme perturbations are significantly smaller than for the ${ \mathrm { L S } } { + } { \mathrm { A R } }$ and IERS solutions (Figure. 7).

The representative statistic MAE as well asthe corresponding error bars for our predictions in comparison with those forthe IERS official predictions are shown yearby-yearin Figure. 8. The results indicate that the accuracy of the ${ \mathrm { L S } } { + } { \mathrm { A R } }$ combination can be remarkably improved by incorporating the EMD into the prediction model, especially in long-term predictions.In contrast tothe IERSpredictions,our results obtained by the EMD+LS+AR approachappear to be comparable with those from the IERS for near-term prediction. However, for long-term prediction the proposed method noticeably outperforms the IERS solutions except individual prediction days, as can be seen apparently in Figure. 8.

In order to furthermore demonstrate the effectiveness of the developed EMD+LS+AR prediction strategy, the results of thisstrategy arealso compared with those from the EOP PCC lasting from October 1,2005 to February 28,2008, in which the prediction period and validation scheme had been clearly specified in advance. Under the same rules and conditions, the comparison with the contemporary prediction methods and techniques involved in the EOP PCC is shown in Figure. 9, in which the data time span is same, the statistics are referred to the EOP 05 CO4 series and the MAE is used as the statistical measure.A list of participants and prediction methods can be found in [6].

From the comparison it can be said that the error of the predictions for $\textup { 1 } ^ { \sim } \ 1 0$ days in the future by the $\mathrm { E M D + L S + A R }$ model is equal to theerror of the most accurate prediction method for forecasting polar motion, namely the LS extrapolation of the harmonic model and AR prediction (Figure. 9(a)) and Figure. 9(b)). For shortterm (up to 30 days in the future) prediction, the prediction accuracy of the developed method is comparable with or slightly worse than the accuracy of the three most accurate prediction techniques used (Figure. 9(c)) and Figure. 9(d)). As to long-term forecast ,(up to 1 year in the future) the predictions are inferior to the most accurate results，in particular those ofdata. However, our results are significantly more accurate than the predictions contributed by the other participants (Figure. 9(e) and Figure. 9(f)).

![](images/62a2f7ffcd10f38c22b154a77753490287310e9af2cc4305983b43086e99ec70.jpg)  
Figure. 5Absolute differences (in mas) between the pole coordinate data and their ${ \mathrm { L S } } { + } { \mathrm { A R } }$ predictions calculated at different starting epochs

![](images/60d6788e912e5426acae36b56508210df4ec43aa6a37dac9a6457fc3f98b7dda.jpg)

![](images/99b2f9cf8f234425024dbfa13a677ddc0f4f6f1ca8ae2ca734df8f38247155a0.jpg)  
Figure. 6Absolute differences (in mas） between the pole coordinate data and their IERS predictions calculated at different starting epochs   
Figure. 7Absolute differences (in mas） between the pole coordinate data and their EMD+LS+AR predictions calculated at different starting epochs

（a)x LS+AR ENO0 (b)yp   
2011 111I1IIII 11   
2 H AAA 20 0 0 50 100 150 200 250 300 350 400 0 50 100 150 200 250 300 350 400 （c）x （@）yp   
40 2012 IIIII IIII 0 2012 IIH   
20 于 AAE 20   
0 0 0 50 100 150 200 250 300 350 400 0 50 100 150 200 250 300 350 400 (e）x ()yp   
40 2013 11 40 2013 士 IIITTII   
20 20 T   
0 0 0 50 100 150 200 250 300 350 400 0 50 100 150 200 250 300 350 400 2014 A u 60 2014 (h)y HI   
20 工 工   
0 。 0 50 100 150 200 250 300 350 400 0 50 100 150 200 250 300 350 400 x y 2015 0 2015   
20 40 美 H TH AAE 20 1i1lI1iE   
0 0 0 50 100 150 200 250 300 350 400 0 50 100 150 200 250 300 350 400 Day in the future Day in the future

![](images/bceade64a135eab8e2e8ba3e7453eaa1b807176678f2882c90104c8cfe510b2a.jpg)  
Figure. 8MAE for the $\mathrm { L S ^ { + } A R }$ ，EMD+LS+AR and IERS predictions of pole coordinates from 1 to 365 days in the future as well as the corresponding error bars   
Figure. 9MAE for the $\mathrm { E M D + L S + A R }$ predictions and those contributed to the EOP PCC for different prediction days

# 4. Summary and conclusion

Our investigations show that pole coordinate time-series were decomposed into a small number of IMFs representing different time-scale fluctuations, e.g.， seasonal, inter-annual and inter-decadal fluctuations. Therefore, the EMD can be considered as a filter to extract specific oscillatory signals in polar motion. For the purpose of separation treatment of different components in time-series prediction, the EMD is used as a filtering method for separating the low- and high-frequency components of pole variations in our work. The results have indicated that both the shorter-period high-frequency variations and the low-frequency oscillations including the long-term trend,Chandler and annual wobbles can be extracted through reconstruction of the partial IMFs. Based on the findings, the LS extrapolation of the low-order polynomial and harmonic model and AR technology are recommendedto predict the determined low-frequency and high-frequency components, respectively. The predictions of polar motion are generated by means of the combination of LS extrapolation and AR prediction. In order to evaluate the prediction accuracy of the proposed strategy, we have calculated the developed EMD+LS+AR as wel as LS+AR predictions year-byyear at different starting prediction epochs betweenJanuary 7, 2O1land December 31, 2015 in comparison with the IERS official forecasts. The figures of the MAE and absolute values of differences between pole coordinate data and their predictions illustrate that the presented hybrid approach indeedprovides the more accurate predictions more than the conventional ${ \mathrm { L S } } { + } { \mathrm { A R } }$ combination, implying that the performance of the ${ \mathrm { L S } } { + } { \mathrm { A R } }$ method can be enhanced by involving the EMD into prediction model.Our results gained by the proposed method are better than the predictions released by the IERS as well, although those for individual prediction days are exception. In addition, the comparison between our results and the forecasts from the EOP PCC confirms that the EMD+LS+AR combination is avery powerful toolto predict pole coordinate data. The main conclusionis that the prediction error can be decreased when the EMD is incorporated into the ${ \mathrm { L S } } { + } { \mathrm { A R } }$ combination. Furthermore，we conclude that the separation treatment of different time-scale Oscillations may enhance polar motion predictions and thus such processing seems to be of necessity in time-series prediction.

# References

[1] Gambis D, Luzum B. Earth rotation monitoring,UT1 determination and prediction [J]. Metrologia, 2011, 48(4): 65-170.

[2] Xu X Q, Zhou Y H. EOP prediction using least square fitting and autoregressive filter over optimized data intervals [J]. Advances in Space Research,2015, 56(10): 2248-2253.   
[3] Lei Yu, Cai Hongbing. Enhancing the prediction accuracy of the length of day change by eliminating the edge-effect of least squares fiting [J]. Astronomy Research and Technology, 2016, 13(4): 441-445.   
[4] Liao D C, Wang Q J, Zhou Y H, et al. Long-term prediction of the Earth orientation parameters by the artificial neural network technique[J]. Journal of Geodynamics, 2012, 62: 87-92.   
[5] Lei Yu, Cai Hongbing, Zhao Danning. Effects of training pattrns on predictions of variations of length of day using an extreme learning machine neural network [J]. Astronomy Research and Technology,2015,12(3): 299-305.   
[6] Kalarus M, Schuh H, Kosek W, et al. Achievements of the Earth orientation parameters prediction comparison campaign [J]. Journal of Geodynamics, 2010, 84(10): 587-596.   
[7] Kosek W.Future improvements in EOP prediction[J]. Geodesy for Plant Earth, International Association of Geodesy Symposia, 2011, 136: 513-520.   
[8] Huang N E,Wu Z H. A review on Hibert-Huang transform: method and its application to geophysical studies [J]. Reviews of Geophysics, 2018, 46(2): 1-23.   
[9] Akaike H. Autoregressive model fitting for control [J]. Annals of the Institute of Statistical Mathematics,1971,23:163-180.   
[10]Bizouard C，Gambis D.The combined solution CO4 for Earth orientation parameters consistent with international terrestrial reference frame 2Oo5[J].International Association of Geodesy Symposia,2009,134: 265-270.

# 利用经验模态分解提高极移预报精度

赵丹宁1,²，雷雨1,，蔡宏兵1,3（1.中国科学院国家授时中心，西安710600;2.中国科学院大学，北京100049;5．中国科学院时间频率基准重点实验室,西安 710600)

摘要：经验模态分解（Empirical Mode Decomposition，EMD）是一种数据驱动的自适应非线性、非平稳信号分解方法。为提高极移预报精度，将EMD应用于极移预报中。首先利用EMD方法对极移序列进行分解，获得极移的高频分量和低频分量；然后采用最小二乘（Least Squares，LS）外推模型对极移低频分量进行拟合，获得LS拟合残差；其次采用自回归（Autoregressive，AR）模型对极移高频分量和LS拟合残差之和进行建模预报；最后将LS模型和 AR模型外推值相加获得极移预报值。将EMD 和 $\mathrm { L S + A R }$ 组合模型预报结果与$\mathrm { L S + A R }$ 模型预报以及地球地球定向参数预报比较竞赛（EarthOrientationParameters Prediction Comparison Campaign，EOP PCC）的预报结果进行比较,13

结果表明，将EMD应用于极移预报中，可以明显改善极移预报精度。

关键词：极移;预报;经验模态分解;最小二乘；自回归模型