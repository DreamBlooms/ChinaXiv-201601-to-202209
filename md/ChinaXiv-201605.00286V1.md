# DEVELOPMENT OF THE RECONSTRUCTIVE TRANSPONDER FOR IN-ORBITCALIBRATIONOFHY-2 ALTIMETER

Caiyun Wangl,Wei Guo1,Fei Zhaol\*,Junzhi Wan²,Ke $\mathrm { X u ^ { 1 } }$ lThe Key Laboratory of Microwave Remote Sensing Center for Space Science and Applied Research, Chinese Academy of Sciences,Beijing,100190, China 2The Graduate University of the Chinese Academy of Sciences, Beijing,10oo49,P.R. China Corresponding Author Email: zhaofei@mirslab.cn

# ABSTRACT

HY-2 satellite, the first ocean dynamic satellite of China, was launched in August 2O11,carrying a dual frequency ( $\mathrm { \ K u }$ band and C band) altimeter, to measure the global mean sea level [1]. To provide truly sea level measurements,in-orbit calibration is essential.This paper concerns the transponder in-orbitcalibration method. A signalreconstructive transponder for HY-2 altimeter in-orbit calibrationis presented.Different from the existing bent-pipe ones,this kind of transponder can capture and track altimeter pulses, record them,and reconstruct the chirp pulses,transmit them back to the altimeter.It is carried on a SUV，reduces requirement for a permanent installation site.With the characteristics of capture and record altimeter signals,the HY-2 altimeter inner path delay and clock drift could be derived fromthe calibrationdata.

Keywords: HY-2 altimeter, in-orbit calibration, transponder, signal reconstructive, clock drift

system,in-orbit calibration is essential. There exist some in-orbit calibration methods, such asthe conventional method with offshore sensors or indirectly using coastal tide gauges. In contrast, the microwave transponder allows performing directly range measurement, does not involve any errors induced by the ocean dynamics.

# 2.SIGNALRECONSTRUCTIVE TRANSPONDER

The existing transponders used for altimeter calibration, such as the GAVDOS transponder for JASON-2 [2]are bent-pipe ones,which receive the altimeter signals,amplify them and retransmit them back to the altimeter. Bent-pipe transponders are simple, economical，and stable.They provide a fixed electrical delay and require the accurate knowledge of the installation site altitude.Therefore the experiments success rate is not high.

# 1. INTRODUCTION

The transponder for HY-2 altimeter calibration,different from the existing bent-pipe one,is a signal reconstructive transponder.It can capture and track altimeter pulses,record them， and retransmit the reconstructed signals to the altimeter [3]. It provides flexible time delay and could be set on any site of the ground tracks,and furthermore,as a result of the capture and tracking feature,the altimeter clock drift could be derived from the calibration data.

HY-2 satellite,Chinese first ocean dynamic environment satellite, was launched in August, 2011. One of the primary payloads,a dual frequency (Ku band and C band) altimeter, issophisticated radar designed to measure the key parameters of global oceans [1]. The altimeter is developed by the Key Laboratory of Microwave Remote Sensing, Chinese Academy of Sciences.The altimeter can measure the range from the satellite to the sea surface with a precision of 4cm at high sea state,and provide accurate wave height and wind speed products. The system is very similar to the Jason series altimeters.In order to provide truly global sea level measurements within a geodetic

The transponder system block diagram is shown in Fig.1. It consists of mainly five units: antenna,receiver,data processing unit (DPU), transmitter, and power unit.

The antenna is a dual frequency (Ku band and C band) offset-fed parabolic with a circularpolarization feeder. For the altimeter signal is linear polarization，the circular polarization reduces the aligning requirement between the transponder antenna and the altimeter antenna.The 3dB main lobe is not more than 1.5 degree to gain a high gain of greater than 4OdB.The feeder is share by two band signals. The picture of the antenna and the feeder is shown in Fig.2.

![](images/018ba2d9ad42285c80100a7454c2a21536cecb72df3bc62bde699aae8a43766e.jpg)  
Fig1Block diagram of the reconstructive transponder

The parabolic antenna is 1.2 meter in diameter, with the feeder off the focus point. The RF power amplifier is mounted on the feeder bracket to reduce the RF signal transmission loss.During the satellite passing over, the antenna is unfolded and pointed zenith，as the HY-2 altimeter isnadir looking.In other time,itis folded in safe state.The antenna unitis mounted on the top ofa SUV,as shown in Fig.3,and the other four units are installed inside, as shown in Fig.4.Therefore,the entire transponder is carried on a SUV. It can move to any site on the satellite ground tracks,more flexible and efficient compared to the permanent mounted transponders.

The receiver,DPU, transmitter are the key kernels of the transponder,implementing signal capture， tracking and reconstruction.The receiver is composed of a low noise amplifier (LNA） with AGC function and a quadrature down-converter,which receives altimeter RF signals and produces demodulated baseband I/Q.The DPU samples I/Q signals and records them.The signal capture, tracking and reconstruction are performed in this unit by a FPGA,which also generates reconstructed baseband I/Q chirp to the transmitter.The transmitter consists of an up converter and RF power amplifier that outputs RF signals to the antenna. The track error, expressed as FFT of the received I/Q data, is recorded and compensated in reconstructed signals. Some modulation, such as time modulation (delay or advance) or frequency modulation could be added to the reconstructed chirp pulses to ensure the transponder signal being visible in the altimeter receive window.

The entire system is powered by an independent AC/DC unit, which supplies the other units separate DC powers.

![](images/42224a345aa5b576a950f4e00a9156944a32ee67d69a64d22a15e73eb941ecae.jpg)  
Fig2Picture of antenna and feeder

![](images/7bd82eb00027115349402b9c1e564211d39df2c79b0db85679fa27e55d1bdf1f.jpg)  
Fig 3 Picture of antenna mounted on the SUV top

![](images/0d9937f6e9734dc01df448192060bad89acddcdbbd9dbf5afa1cd894c7c39997.jpg)  
Fig4Picturesofdevices installed inside

After a long trip of atmosphere, the transmitted pulses of the altimeter are received by the transponder,and then are de-ramped.The trigger time is controlled by the DPU.The demodulated I/Q signals are sampled and recorded.After a programmed time delay,depending on the orbit prediction andcalibrationsitealtitude(therecould besome modulation), the reconstructed $\mathrm { I } / \mathrm { Q }$ signals are injected into up converter,then are amplified and retransmitted to the altimeter [3].

During experiment, some ancillary devices are needed, a set of static GPS receivers for precise positioning,a timer GPS to provide the receiver precise UTC time and PPS, two hydraulic jacks to lift and level the SUV,and a portable computer to control and record calibration data. Ancillary devices are shown in Fig.5.

![](images/a45f20ec84af253a21f41324d2f02ffe83e12d20a7b647df2edd5e14622a9539.jpg)  
Fig5Ancillaries: hydraulic jack and GPS receiver

The system time delay of the transponder is determined by an overall measurement on a test range,relative to a disk reflector. An inner calibration loop is designed to monitor the variation of the time delay,so the accuracy of the transponder is guaranteed [4].The overall measurement of the system time delay is shown in schematic diagram Fig.6.

![](images/82752e76a9983dc5e8f1b040a8f598404e7b5bf143f42a4a543d44044b169d6f.jpg)  
Fig 6Overall measurement of the system time delay

A burst of RF chirp pulses are generated from the DPU, amplified and transmitted, thetransmitted pulsesare reflected by the disk reflector which faces directly to the antenna at the testing range of R,the reflected pulses are received by the receiver,and the time delay of the overall round path are obtained from FFT analysis of the received data.The testing range,illustrated in Fig.6 as R,is obtained through a laser ranging device installed at the disk center. Subtracting the testing range R from the overall path delay, the transponder system time delay is obtained.Accurate pointing between the transponder antenna and disk reflector is crucial, small deviation leads to large measurement error. Once overall measurement is enough provided no hardware alteration to the transponder before it is applied to the in-orbit calibration.The inner calibration loop,illustrated in Fig.6,the dotted line，records the inner calibration data value as a standard.Any changes of the data value in the future would be compensated for the transponder system time delay. The overall experiment should be done in an open field to reduce the background clutter and the disk reflector should be selected to provide an appropriate radar Cross-Section.

The transponder system parameter is tabulated in Table 1.

Table1SystemParameter   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Antenna Gain</td><td>More than 40dB</td></tr><tr><td>AntennaPolarization</td><td>Circular polarization</td></tr><tr><td>Receiver Power Dynamic</td><td>-60dBm~-30dBm</td></tr><tr><td>Transmitter Power Dynamic</td><td>-22dBm~38dBm</td></tr><tr><td>System Time Delay</td><td>23.85m</td></tr><tr><td>AntennaPointingPrecision</td><td>Better than O.1degree</td></tr><tr><td>Range Calibration Precision</td><td>Better than 4cm</td></tr><tr><td>RCS Calibration Precision</td><td>Better than 0.5dB</td></tr><tr><td>Time Delay Step</td><td>12.5nS</td></tr><tr><td>Time Delay Precision</td><td>0.1nS</td></tr></table></body></html>

# 3.IN-ORBIT CALIBRATION OF HY-2 ALTIMETERUSING SIGNAL RECONSTRUCTIVETRANSPONDER

This signal reconstructive transponder was used in HY-2 altimeter in-orbit calibration from March 2O12. The experiments are implemented once every two weeks (HY-2 orbit cycle). By virtue of the mobility of the transponder, several calibration sites are used to increase experiment numbers.

During HY-2 passing，2 to 3 seconds,a number of transponder waveforms are obtained,and the uncorrected slant ranges can be derived. Some corrections,including altimeter phase center offset from the satellite gravity center, atmosphere propagation delay, transponder system delay, etc. are applied to convert these uncorrected rangesto measurements of the true slant ranges. These are then compared with the ranges calculated from the satellite precise orbit determination and the position of the transponder,and the residual is obtained.There are two elements in the residual: one is the altimeter inner path delay which is considered constant throughout the lifetime; the other is the error arising from the altimeter clock drift, which varies with time [5]. Use the signal reconstructive transponder,the altimeter clock drift could be determined accurately.Subtracting the clock drift from the residual, the altimeter inner path delay is obtained.

Until now, there have been more than 6O experiments in different calibration sites. Among them $3 5 \%$ of the campaign is successful, unfortunately,the remaining $6 5 \%$ because of different kind of problems (orbit prediction deviation,power failures and bad weathers) did not provide

useful data.

In April 2013, Side-A ofHY-2 altimeter shut down due to failures of the crystal oscillator, and Side-B was switched on. The oscillator abnormity during the failure time was monitored by the transponder.

From all the successful experiments,the altimeter Side-A and Side-B inner path delay is shown in Fig.7.The Side-A mean is 5.4635 meters,and the standard is O.0091 meters. There are some outliers in Side-B indicated as blue point, which are due to the loss of inner calibration data and heavy rains during the passing time.Eliminating the outliers,the mean of the Side-B inner path delay is 6.2742 meters and the standard is 0.0449 meters.

The altimeter clock drift (frequency bias） could be converted to range bias [5],and the clock drift has been monitored since August,2012.HY-2 altimeter clock drift is illustrated in Fig.8 [5]. The anomalous behavior of the oscillator is monitored, marked black cross.

![](images/0932c56282a44e113ae164b37cb2e28b0af50e969a8f345e80d31e86ad1bc894.jpg)  
Fig7Altimeter Side-A and Side-B inner path delay   
Fig 8 HY-2 altimeter clock drift and corresponding range bias   
Fig 9Clock drift validation between Jason-2 and HY-2

0.9 米Side A, part I 70   
0.8 Side A, part II Side A,USO anomalous bhavour epred. 米 \*\* ouonba 中 菜   
0.3 X 20   
0.2 米 10   
0.1 300 400 500 600 700 800900 1000 Number of days from August 16, 2011

The clock drift is validated by cross calibration between Jason-2 altimeter and HY-2 altimeter [5],and the clock corrections are used to correct mean sea level (MSL). Fig.9 (a) shows the MSL bias between Jason-2 and HY-2 without clock drift corrected.Fig.9 (b) is the MSL bias corrected. Relative biases are removed in Fig.9. The transponder calibration campaign starts from day 359 relative to August 16,201l，and the red part of (b） (before day 359） is uncorrected.

1.5 PartI slope:1.28e-03±1.20e-04m/day ×Part II slope:-4.42e-04±1.09e-03 m/day \*Part II slope:1.35e-03±6.69e-05m/day   
WST sss 0.5 0 -0.5 −1 -1.5 0 200 400 600 800 1000 Number of days from August 16,2011 Jason-2 MSL minus HY-2A MSL (USO Corrected) 1.5 \*PartI slope:1.63e-03±2.52e-04m/day ×Part II slope:2.42e-04±2.92e-04m/day \*Part III slope:2.04e-05±6.69e-05m/day   
W/ST ass 0.5 0 -0.5 - -1.5 0 200 400 600 800 1000 Number of days from August 16, 2011

# 4. CONCLUSION

Since the launch of HY-2, the technique of using a signal reconstructive transponder has demonstrated significant meaning for the satellite altimeter. It makes an independent contribution to the calibration of the altimeter range bias. Furthermore,this kind of transponder provides an effective means for long-term monitoring of the altimeter clock drift.

# 5. REFERENCE

[1] X.L.Dong, K.Xu, H.G. Liu, J. S. Jiang,“ The radar altimeter and scatterometer of China's HY-2 satellite",   
IGARSS proceeding, vol.3, pp.1703-1706,2004   
[2]E.Cristea,P.Moore,“Altimeter range determination and application using a transponder", SPIE Proceedings   
Vol.6360,D01: 10.1117/12.691041, 2006   
[3] Guo Wei, Gong Xiao-Yan, Xu Xi-Yu, Liu He-Guang,Xu Chuan-Dong， Du Yue-Heng， “A transpondersystem dedicatingforthein-orbitcalibrationofChina's new-generationsatellitealtimeterandscatterometer", CIE-Radar, vol.1, pp.22-25,2011   
[4] Wang Caiyun,Guo Wei, Zhao Fei,Wan Junzhi, ‘20 In-orbit Calibration of HY-2 altimeter using a signal reconstructive transponder”， IGARSSproceeding，DIO: 10.1109,pp.5119-5122,2014   
[5] Wan, J.；Guo,W. ；Zhao,F. ；Wang, C. ；Liu, P. “HY-2A Radar Altimeter Ultrastable Oscillator Drift Estimation Using Reconstructive Transponder With Its Validation ByMultimissionCrossCalibration”，IEEE transactions,DIO:10.1109/TGRS.2015.2419670,Issue: 99, pp.1-8.