# Research on Online Safety Precaution Technology of a High-medium Pressure Gas Regulator

HAO Xuejun1, LIU Xuhai1,LI Xiaxi², ZHAO Xin

1. Beijing University of Civil Engineering and Architecture,Beijing 1OoO44, China   
2. Beijing Gas Group Co.,Ltd, Beijing 100O44, China

$\circledcirc$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

In view of some of the characteristics of a high-medium pressure gas regulator, such as smallfault samples, many fault types and complex fault features etc,in order to improve the accuracyoffault precaution in this paper,a fault diagnosis method based on the combination of the improved wavelet packet and presure harmonic distortion rateis proposed.On the basis of the harmonic distortion rate of theoutlet pressure and the energy value of each frequency band obtained by improved wavelet packet decomposition,the rules for fault data were summarized.Finally,a safety precaution model of the high-medium pressure gas regulator is established.

# Keywords: high-medium pressure gas regulator, improved wavelet packet, harmonic distortion rate,safety precaution model

# Introduction

# AlgorithmIntroduction

The gas pressure regulator is the important component of gas transmission and distribution system,in view of the high operating pressure and complicated fault features, the stability and reliability of the gas regulator significantly influences the city gas supply. However,at present, the research on gas pressure regulator has mainly focused on the fault diagnosis of the gas pressure regulator(Mitsuhiro Toyoda and Kajiro Watanabe [1],2006; Gao Shunli, Yang Meng [2], 2O13),and the research literature on safety precaution technology of the gas pressure regulatorisrelatively scarce.Thus,itisvery important to realize the fault precaution of gas pressure regulator and ensure the safe operation of equipment by objectively and accurately extracting operating performance characteristics of the regulator with timely mastery of the regulator operating state.

# Waveletpacketalgorithm

The wavelet packet,which is the extension of wavelet transform,can implement more detailed decomposition and reconstruction of the signal. Compared with the Wavelet transform,the wavelet packet transform,which hasa better resolution,can decompose the high frequency part.It can focus on the arbitrary details of the object and extract more detailed information that reflects the signal characteristics.As a result,it is widely used for fault diagnosis [3] [4]. The double dimension equation of the wavelet packet transform is shown below:

$$
\left\{ \begin{array} { l } { { u _ { 2 n } \left( t \right) = \sqrt { 2 } \sum _ { k \in { \cal Z } } h \left( k \right) u _ { n } \left( 2 t - k \right) } } \\ { { u _ { 2 n + 1 } \left( t \right) = \sqrt { 2 } \sum _ { k \in { \cal Z } } g \left( k \right) u _ { n } \left( 2 t - k \right) } } \end{array} \right.
$$

However,with the increase in the layer number of the wavelet packet decomposition，it will produce large amounts of information，and the complexity of signal analysis and processing will also increase.However, some frequency bands contain little information,and can even be ignored. For this purpose, this paper proposes an improved wavelet packet algorithm.

# Improved wavelet packet algorithm

Signals of different frequencies can be separated using wavelet packet decomposition； removing interference signals of some frequency bands and using wavelet packet reconstruction algorithm for signal reconstruction can achieve signal filtering and feature extraction [5]. In this paper, the original signal is first split into different frequency bands using wavelet packet decomposition, and then,using the correlation function analyzes the correlation between the signal of each frequency band and the original signal, the signal,which contains important information could be effectively extracted.The interference signal could be eliminated.The specific calculation steps are as follows:

1）Decompose the outlet pressure signal with the wavelet packet; then,rebuild wavelet packet decomposition coefficient.

2）Analyze the correlation between the reconstruction signal of each frequency band and original signal. Then, obtain a signal correlation coefficient $\mathrm { \bf K }$ as the reference for frequency band selection.The correlation coefficient $\mathrm { \bf K }$ is O.1 in this paper.

$$
K = \frac { \sum _ { i = 0 } ^ { n } z \left( i \right) \cdot y \left( i \right) } { \sqrt { \sum _ { i = 0 } ^ { n } x ^ { 2 } \left( i \right) \cdot \sum _ { k = 0 } ^ { n } y ^ { 2 } \left( i \right) } }
$$

3)Extract the frequency band of $\mathrm { \ K { > } 0 . 1 }$ ，and reconstruct the pressure signal

4) Use wavelet packet to decompose the reconstructed pressure signal,and calculate the energy value of each frequency band.The energy value is calculated as shown in the following formula.

$$
E _ { j , i } = \sqrt { \sum _ { 1 } ^ { m } \left| d _ { 1 } ^ { \ j , i } \right| ^ { 2 } }
$$

Where is the wavelet packet coefficient for nodes $( \mathrm { j } , \mathrm { i } )$ $\mathrm { E _ { j , i } }$ is the energy value for nodes (j,i).

5)Use the energy value of each sub band as the element to construct the feature vector.

# Harmonicdistortionrate

The harmonic distortion rate (THD),which is a performance parameter in the electrical engineering discip line,represents the distortion degree of the actual output waveform compared with the sinusoidal waveform.In this paper,for the first time,it is used as an outlet pressure stability indicator of the gas pressure regulator. For a smaller waveform distortion rate,the outlet pressure is more stable.Thecalculation formulaisasfollows:

$$
T H D = \frac { \sqrt { \sum _ { n = 2 } ^ { \infty } { U _ { n } ^ { 2 } } } } { U _ { 1 } }
$$

Where THD is the total pressure distortion rate; $\mathrm { U } _ { \mathrm { n } }$ is the effective value of the outlet pressure harmonic component; and $\mathbf { U } _ { 1 }$ the set pressure value

To further quantify the influence of high or low frequency harmonic components on the outlet pressure fluctuation, the low frequency harmonic distortion rate $\left( \mathrm { T H D } _ { \mathrm { L } } \right)$ and high frequency harmonic distortion rate $\mathrm { ( T H D _ { H } ) }$ are defined, respectively. The calculation method is the same as above.

# Fault feature extraction and analysis ofa high-medium pressure gas regulator

Outlet pressure data of the high-medium pressure gas regulator operating in the SCADA system of Beijing Gas Group whose judgment cycle is from O0:0O to 23:55.The pressure regulator stations were recorded at 5-minute intervals to obtain 288 sets of pressure data every day. According to the Fourier transform and the improved Wavelet packet decomposition，the pressure harmonic distortion rate and energy values of different frequency bands were obtained as the basis for judging the running state of the gas pressure regulator.

In this paper, the operating states of the high-medium pressure gas regulator were divided into the following four categories:normal, surge,low-use gas peaks with high outlet pressure and high-use gas peaks with low outlet pressure.According to the levels of different fault types,there are two warninglevels,which are referred to asthe warning and alarm.The typical faults of gas pressure regulators were analyzed and described in the following section.

# Normal characteristics of the gas pressure regulator

To make a better comparison, the outlet pressure data of station A are first analyzed,and their operational pressures are stable from January 1st, 2015 to 31th, Figure 1 is a three-dimensional chart of the outlet pressure for station A,the $\mathbf { \boldsymbol { X } }$ -axis represents the date,Y-axis represents the 288 data points corresponding to the dates, and Z-axis is the outlet pressures.Fig.2 and Fig. 3,respectively show the trend line charts of the energy value of each frequency band and the pressure harmonic distortion rate.

As shown in Figure 1,the outlet pressure for station A nearly ranges from 97 to $9 9 \ \mathrm { k P a }$ ，and there is pressure fluctuation within $0 . 5 \mathrm { { k P a } }$ .The operating state of the gas pressure regulator is ideal, and the stabilizing precision of the outlet pressure is high.As observed from Figures 2 and 3,each component of the energy values is relatively small, E1 is not more than 7,and the remaining compo nents are not more than 1.The outlet pressure harmonic distortion rate remains within $0 . 5 \%$ ：

# Fault characteristics with the surge

Surge is a common fault for a gas pressure regulator. There are many reasons for surge,such as incorrect installation position of the signal pipe, low downstream gas consumption, the sensitive command device and more.A long-term surge will seriously reduce the lives of internal components of the gas pressure regulator, especially for the film and spring. The external performance of the surge involves violent fluctuation of the outlet pressure.

Figure 4 is a three-dimensional chart of the outlet pressure for station B,and their outlet pressures are obtained from February 1st to 28th.Fig.5 and Fig.6,respectively, show the trend line charts of energy value of each frequency band and the pressure harmonic distortion rate.

As shown in Figures 4 and 6,the outlet pressure for station B ranges from 116 to $1 2 0 \mathrm { k P a }$ ,the outlet pressure fluctuation is approximately $1 . 2 \ \mathrm { k P a }$ ，the total pressure harmonic distortion rate is approximately $1 \%$ ， $\mathrm { T H D } _ { \mathrm { H } }$ increases significantly,which is compared to station A. As observed from Figure 5,compared to station A,the over-all energy value increases significantly. Among them,E1 ranges between 16 and 23,E2 ranges between 5 and 10,E4 and E3 also increase significantly. The mean value of E2\~E4 is up to 12.

![](images/31be08c51450d1fb39914f12375244a4e790f4bd6d73760b67a99234984e43fb.jpg)  
Fig.1Three-dimensional outlet pressure chart

![](images/41da40bbc69e35621f0d1b1d1f7383310f4249034234bbd92813bdf95e9ddbd2.jpg)  
Fig.2Energy value trend line chart

![](images/dbfd8ad0a2704724bbc5f6dc96930ac1e91ef60ba92a682b4c61c0238abf26d3.jpg)  
Fig.3Waveform distortion rate trend line chart

![](images/d30a4c9b290ab37b6e0a71bd467165b96a840928aab1e577169a59b2ea3c9f1c.jpg)  
Fig.4Three-dimensional outlet pressure chart

# Fault characteristics with high outlet pressure

Due to the difference in gas quality, gas more or less contains some gas impurities. These impurities wear pressure regulator valve port pads or the valve barrel, and make regulator valve port have close lax problem.As a result, the outlet pressure will be higher than the set value especially it occurs during the low-use gas peaks.

Figure 7 is a three-dimensional chart of the outlet pressure for station C,and their outlet pressures are obtained from February 1st to 28th.Figs.8 and 9,respectively,show the trend line charts of energy value of each frequency band and the pressure harmonic distortion rate.

As shown in Figure 7,the outlet pressure for station D ranges from 97 to $1 0 4 ~ \mathrm { { k P a } }$ ，and the outlet pressure for low-use gas peaks which occurs in the early morning, reaches $1 0 3 \mathrm { \ k P a }$ 、The outlet pressure during low-use gas peaks is beyond the set pressure value by $3 \ \mathrm { k P a }$ ，and the fluctuation is more than average.As shown in Figs 8 and 9,E1 improves greatly,and the average value reaches 21. $\mathrm { T H D } _ { \mathrm { L } }$ have a great value and the low-frequency pressure fluctuating is the main reason for outlet pressure fluctuation.

![](images/681ae5be994de9bda208203421056f54223d85ca94aa3ccda41ec059d9bd53d3.jpg)  
Fig.5Energyvalue trendline chart

# Fault characteristics with low outlet pressure

The main reasons for the low outlet pressure are the overload operation of the gas pressure regulator and blockage of the conductor. During the high-use gas peaks. the outlet pressure will significantly decreased, if the pressure drop is beyond the limit,and affects the use of the downstream users,the gas pressure regulator should be repaired in time.

Figure 1O is a three-dimensional chart of the outlet pressure for station D,and their outlet pressures were obtained from February 1st to 28th. Fig.11 and Fig.12, respectively, show the trend line charts of energy value of each frequency band and the pressure harmonic distor tion rate.

![](images/2f979028e7a50203a87d2e113f4f480511e00bd751f318947610f724a07f6763.jpg)  
Fig.6Waveform distortion rate trend line chart

![](images/d861e4b6c59fc83c7309bafc5e18fe674856a799a9d311d5d2b9840e70286057.jpg)  
Fig.7Three-dimensional outlet pressure chart

![](images/1ed077c44dc0833c4c072f5847ba514437052018bea50fe4f9ead00be92b9267.jpg)  
Fig.8Energy value trend line chart

![](images/5d44bcc947365e0828a279789169515e2d601e791111ba930555d2b25af38f66.jpg)  
Fig.9Waveform distortion rate trend line chart

![](images/c9659ca50da4d087de29e2728219e74c8f72a1f5a4a6eb73ab78d902ae5723a7.jpg)  
Fig.10Three-dimensional outlet pressure chart

![](images/d7a1203cc8fc40db42b1bdc916252cceee1ecd3a63d5af3dc19041f9ef3149e6.jpg)  
Fig.11Energy value trend line chart

As shown in Figure 1O, the outlet pressure for station Drangesfrom95 to $9 9 \mathrm { k P a }$ ，and the outlet pressure value only reaches $9 6 ~ \mathrm { \ k P a }$ during high-use gas peaks.The pressure is not more than the set pressure by $2 \ \mathrm { k P a }$ However, the pressure fluctuating is much more than average.Asobserved fromFigures11 and12,E1 reaches 13,the remaining ones are in the low level. Compared to station A,THD has a greater improvement,especially $\mathrm { T H D } _ { \mathrm { L } }$ ,inahighlevel.

# Conclusions

Through the analysis of faultcharacteristics of different fault types,the main conclusions are as follows:

1） The four energy values are obtained by improved wavelet packet decomposition，and E1 represents the low-frequency fault of the system (high or low outlet pressure),the latter three items (E2\~E4) represent high frequency fault of the system (surge).

2）The pressure harmonic distortion rate (THD） reflects the stable performance of the gas pressure regulator. $\mathrm { T H D } _ { \mathrm { L } }$ represents the affection of the low-frequency fault on the outlet pressure fluctuation. $\mathrm { T H D } _ { \mathrm { H } }$ represents the affection of high-frequency fault on the outlet pressure

![](images/9a509b94cd53565f15d1593867878407d676f4dd90825455b7ae749b44bc371d.jpg)  
Fig.12Waveform distortion rate trend line chart

fluctuation.

3)When the data acquisition occurs at 5-minute intervals and the set outlet pressure is 1MPa,the safety pre caution model is shown as in the following Table 1.

As shown in Table 1, the safety precaution model of gas peaks with high or low outlet pressure is completely consistent. To further identify the low-frequency fault types，further judgments should be made by the daily pressure distribution.

4) This method is equally applicable to fault diagnosis and safety precautions of other level outlet pressures of the gas pressure regulator. However, according to the differences in the outlet pressure level, the safety precaution model should properly be adjusted.

Table1 Gas pressure regulator safety precaution model   

<html><body><table><tr><td>Gas regulator state</td><td>Warning</td><td>Alarm</td></tr><tr><td rowspan="3">Surge</td><td>5<∑E≤20</td><td>20<ME</td></tr><tr><td>i=2</td><td>i=2</td></tr><tr><td>0.8%<THDH≤1.4%</td><td>1.4%<THDH</td></tr><tr><td rowspan="3">High outlet pressure</td><td>12<E ≤25</td><td></td></tr><tr><td>0.7%<THD≤1.8%</td><td>25<E</td></tr><tr><td></td><td>1.8%<THDL</td></tr><tr><td>Low outlet pressure</td><td>12<E≤25 0.7%<THD≤1.8%</td><td>25<E 1.8% <THDL</td></tr></table></body></html>

# Acknowledgments

This paper was supported by Science and technology project of Beijing in 2O15 from Beijing Municipal Science & Technology Commission.

# References

[1]Hao Xuejun,Liu Qiang,Yang Guobin,Du Yi.Using the EMD Method to Determine Fault Criterion for Medium-low Pressure Gas Regulators [J]. Journal of Thermal Science,2015,24(6): 557-561.   
[2]Hosei Univ. Tokyo.Development of incipient fault diagnostic system for high pressure regulator[C]. SICE-ICASE International Joint Conference,2006   
[3]Gao Shunli,Yang Meng.Fault identification of gas pressure regulator based on wavelet packet and neural network [J].Gas and Heat,2013,33(10): 29-31.   
[4]Craigmile PF,Percival DB.Asymptotic deco-rrelation of between-scale wavelet coefficient-s [J].IEEE Transactions On Information Th-eory,2005,51(3):1039-1048.   
[5]Huang Qiang, Jiao Li,LI Yanze.Research on the measure locations of vibration signals for fault diagnosis in the diesel engines [J]. Journal of Huazhong University of Science and Technology (Nature Science Edition), 2007, 35(5):99-101.   
[6]Jing Shuangxi, Zhang Yingqi. Signal filtering based on wavelet transform [J].Journal of China University of Mining and Technology, 2000,29 (2): 190-193.