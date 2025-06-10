# Analysis and mitigation ofthe carrier phase delay effect of the digital phase generated carrier algorithm

LI SHUWANG,12 SHAO SHIYONG,1\* MEI HAIPING,1HAO QILONG1,²AND RAO RUIZHONG1,2

KeyLaboratoryfAtmosphericCompositionandOpticalRadiationAnuiIstituteofOpticsandFineMechanics,Chnesecademyof   
Sciences,Hefei,Anhui230031,China   
2Science IslandBranchofraduatehool,Universityofienceandechnologyofina,Hefeio6,hinaubictio   
\*Corresponding author: shaoshiyong@aiofm.ac.cn

ReceivedXMthXX;vdXthX;ceethX;podXthX(c.);s

We present an improved digital phase generated carrier (PGC)algorithm based on the synchronous carrier restoration(SCR) methodto mitigate thecarrier phase delay effects.The most distinguishing feature of this method is that it picks up the carrier signal information (frequency and phase) from the interference signal directly and accomplishes the processing of carrier signal restoration synchronically. In comparison with the traditional one which adopts the initial carrier signal, the total-harmonic-distortions of the SCR method is only $\mathbf { 0 . 0 9 1 \% }$ ,lower than the traditional one's $\mathbf { 1 8 . 3 8 \% }$ ，and the signal-to-noise-ratio increases 29 dB.Further，we derive the analytic expression of distortion component and verify it by experiments.Thistechnique may be potentially applied in a long distance large-scale distributed fiber-optic interferometer sensors array. $\circledcirc$ 2016 Optical Society of America

OCIS codes:(060.5060) Phase modulation;(060.2300) Fiber measurement; (120.3180) interferometry

http://dx.doi.0rg/10.1364/AO.99.099999

# 1.Introduction

Fiber-optic interferometer sensor (FOIS) such as Mach-Zehnder, Michelson and Sagnac interferometers is the most sensitive class in all kinds of fiber sensors.It can output a linearly signal and give much higher performance than conventional electronic sensors [1,2]. FOISalsohas the features of compact size,light weight, wide responsive bandwidth and immunitytoelectromagnetic interference [3]. Additionally,itisverysuitable forlongdistance large-scaledistributed sensing due to the very small propagation loss of in fiber andease of multiplexing[4].Hence,FOIS iswidelyusedin fields ofweak signal detection (i.e sound pressure,magnetic,accelerationand vibration) [1]. Generally,PGCalgorithmis the mostwidely used signal demodulatorof FOIS[5],due to it'sadvantagesof high resolution,highsensitivity,wide dynamic range,good linearity and the multi-channels demodulated capability[6].In PGCalgorithm,a high-frequencysinusoidal phase modulation signal is applied to the FOI to generate aphase carrier, thiswill up-convert the sensing signalonto the sidebands of carrier frequency.Then,a pair of quadrature components containing the sensing signal are obtained by mixing the interference signal with the carriersignals [7].Accordingly,if phase difference exists between the interference signaland the carrier mixing signals, the demodulated sensing signal will be distorted [4]. Moreover,this will be more serious for the long distance large-scale distributed sensing array because the phasedifferencemaybe inducedbythe lasertransmissiontimein leadingand sensing fiber or the conversion time between analogand digital.

To mitigate above effects and improve the performance of FOIS, in this paper，we will analyze the distortion component of the demodulated signals induced by the carrier phase delay effect theoretically and experimentally.Then，an improved digitalPGC algorithm based on the synchronous carrier restoration (ScR) method will be presented to mitigate this effect. The most distinguishing feature of this method is that it picksup the carrier signal information (frequency and phase) from the interference signal directly and accomplishestheprocessingofcarriersignalrestoration synchronically.Furthermore,an experimental systemwill be to verify the validity of the improved digital PGC algorithm.Results show that thismethodwill eliminate the phase difference between the carrier signaland the interference signal andmitigate the phase delay effect.

The structure of this paper is as follows:In Section 2,we introduce the basic theory of PGC algorithmand analyze the effect of phase delay inPGC-Arctanalgorithm.In Section 3,principle of the improved digital PGC algorithm based on the synchronous carrier restorationmethod is reported.In Section 4,we describe the experiments andresults to evaluate the performance of this method and validate the previous theoreticallyanalysis.Finally,we summarize our conclusion in Section 5.

# 2. Analysis of the carrier phase delay effect

Forthe dual beam interferometer,afterthe carrierterm isadded, the output light intensity ofinterferometer can be shown as [7]

whereAis the average interference intensity,Bis the interference intensity,C is the PGC carrier phase modulation depth,is the angular frequency of carrier,,is the sensing signal,and is the initial phase of interferometer.

In PGC algorithm，to recover the sensing signal from the interference signal in Eq. (1),a pair of quadrature components containing the sensing signal is obtained by mixing the interference signal with the carrier fundamental and second-harmonic signal respectively.Inactual, if considering the existence of conversion time delay fromanalog to digital and laser transmission time delay in fiber (leading fiberand sensing fiber),Eq.(1) should be modified as

here,is the time delay，is the phase delay between the interference signal and initial carrier signal. Consequently, Eq. (3) can be obtained after using the Bessel function to expand Eq.(2) as follows

where is the orders of Bessel function. Then, if multiply Eq. (3) with the initial carrier fundamental signaland second-harmonic signal,respectively,Eq.(4) andEq. (5) can yield

After filtered by two low-pass filters to remove the termsabove the highest frequency of interest, the quadrature componentsEq. (6) and Eq.(7) are got

Obviously, two additional factors of and appears in and .In fact, theyare the attenuation coefficient induced by phase delay.For the PGC-Arctan algorithm,after dividing Eq.(6) with Eq.(7) and arc tangent function processing, the result can be written as [8]

Here,the carrier phase modulation depth is just under $2 . 6 3 \mathrm { r a d } ,$ accordingly,Eq.(8) can be modified to

In order to analyze effects of carrier phase delayofPGC-Arctan demodulation,we expand Eq.(9) into the fundamental component and the distortion component Therefore,the can be writtenas

The first term on the right-hand side (r.h.s.) is the desired signal of the fundamental component. The second term is the initial phase of interferometerwhich can easily be removed by high-pass-filter. The third term is the distortion component, which is concerned with the carrier phase delay,the sensing phase signal and the initial phase of interferometer. If,the third termwill disappearand the distortion will no longer exist Moreover,if,the demodulated signal will be zero.

To investigate the harmonic distortion due to the phase delay, we assume that the sensing signal，and are the amplitude and the frequency of the sensing signal, respectively. Substituting the singlefrequency sensing signal to Eq.(1O) and using Bessel expansion, Eq. (10) can be written as [5]

The first term on the r.h.s.of Eq.(11) is DC component which can easilybe removedbya high-pass-filter.Thesecond term is the desired sensing signalat the fundamental frequency.The third termand fourth termare even and odd harmonics,respectively.

Here,we adopt the total-harmonic-distortions (THD) to evaluate thecarrier phase delayeffect of PGC-Arctan algorithm which can represent the degree of harmonic distortion of demodulation signals. In this paper, THD is defined as the ratio of equivalent root-meansquare (RMS) amplitude of all harmonics to the amplitude of the fundamental component [5].The analytic expression of the THD of the PGC-Arctan algorithm can be expressed as

This indicates that the THD depends on the carrier phase delay, the sensing phase signal and the initial phase of interferometer. Further，we also adopt signal-to-noise-and-distortion (SINAD） to evaluate the carrier phase delay effectof PGC-Arctanalgorithm.In this

TherelationshipsofTHD,SINAD and withdifferent are plotted in Fig.1.,andof,,,，and,and ranges from O to are chosen.If the initial phase of interferometer，we can see that when the phase delay approaches to (isodd number),THD increases rapaidly,and when the phase delayis around（is even number)，THD approaches to zero.Further, if the initial phase of interferometer，THD presents a different tendency.When the phase delay approching to (is2,6), THD increases sharply,and when the phase delay is around（is $1 , 3 , 4 , 5 ,$ 7),THD approaches to zero.It should be stated that whenis (is1,2,3, 5,6,7),the THD will get its maximum value of,and the SINAD will approach to．Specifically, the demodulation process will be failed. Here,in order to present more detailsof THD,these points are not shown. As a whole, THD is non-zero except for several special points, it paper,SINAD is defined as the ratio of the power of the fundamental frequency to the sum of the powers of all noise and harmonics [5]. Sinceis periodic,the fundamental component and the distortion component are periodic, too.Hence,the SINAD can be expressed as [8]

means that the distortion of demodulation signal is always existence.   
The relevant SINAD proofs the conclusion.

![](images/ee23502f400e2685bbd0dc67acd1597e094018aa3dd7b6fba517bae49e66919b.jpg)  
Fig.1.Therelationshipsof THD,SIANDand phasedelaywith different initial phase of interferometer.

Distortions of PGC-Arctandemodulated signals under and are shown in Fig.2.,andof,,,,,and.We can find that when the phase delay，the THD is $0 \% ,$ the SINAD is，and the demodulated signal present a standard sinusoidalsignal which is well coincided with the sensing signal.When the phase delay，the THD is $0 . 4 7 \%$ ，but the SINAD is onlywhich decreased，obviously，theamplitudeof demodulated signal increased.When the phase delay，the THD sharply increases to $1 7 . 0 1 \% ,$ the SINAD is only. It is clearly that the demodulated signals presentaserious distortionboth theamplitude and thewaveform.

![](images/9e96d8d016c46af2197c3309371b68c04c9ca6571d90ecb3c2a30bcb570bd42b.jpg)  
Fig.2.Distortion of PGC-Arctan demodulation signalsunder different phase delay when the initial phase of interferometer.

# 3.Principle of the improved digital PGCalgorithm based on the ScR method

Obviously,the existence of phase delay will cause serious effects of PGC algorithm.It is indispensableto eliminate the carrier phase delay. Here,we present a novel method based on synchronouscarrier restoration which can eliminate the phase difference between the interference signal and the carrier mixing signal.

The frequency-domain interference signal is shown in Fig. 3, which is acquired from the experimental instrument shown in Fig.6. The frequency of the carrier signal is and the sample rate is .

![](images/40988db49a8298474aeb9e47466e28fc6e4a1a7c226edfe6463cfac74ec43459.jpg)  
Fig.3.Frequency-domain interference signal acquired from the experimental instrument.

From Fig.3,we can see that the interference signal has the frequency components of zero,fundamental, second-harmonic and high-harmonic,et.al.This is well coincided with the Bessel functionof interference signal inEq. (3).Consequently,if the Eq.(3) is filtered by two band-pass filters whose center frequency is fundamental and second-harmonic,respectively，the residual components can be written as

If ignore the effectof,Eq.(14) and Eq.(15) are the ideal source of carrier mixing signal. Because they are directly filtered from the interference signal,and the phase delay in the interference signal will transfer to the carrier mixing signal. This can ensure the carrier mixing signals synchronous with the interference signal. Unfortunately, the effect of is inevitable and in mostly times the frequency components of is lower than the carrier signal. Consequently,this will lead lowfrequency disturbance to the carrier mixing signals and trigger a negative effect on the demodulation process.

Based on this,we present a novel method which picks up the information of frequency and phasefrom Eq. (14） and Eq.(15) directly,and then restore the carrier mixing signalssynchronously.The whole process of the improved PGC algorithm based on the synchronous carrier restoration method is shownin Fig.4.Firstly, the interference signal isdivided into two channels.Onechannel isdirectly transported to the PGC demodulatorand another is transported to the synchronous carrier restoration module. The later will go across a band-pass filter,and then transfer to frequencydomain from time domain by windowed Fast Fourier Transform (FFT). In the frequency spectrum，the carrier signal occupies the absolute advantage. Consequently,we can easily pick up the carrier information (frequency and phase）with the extraction module of single frequency signal and input the frequency and phase to the signal restoration module. Finally, the carrier mixing signals of fundamental signal and secondharmonic signal are restored. Obviously,if multiply Eq. (3) with the restored ones,the two additional factors of and in Eq.(6) and Eq. (7) are no longer existence.

![](images/4b59353f7077e84c27598d57b55a52d58f4f2274fc7cde1ef3595e9ab794c5c8.jpg)

Fig.4.Schematic of improved digital PGC algorithmbased on the synchronous carrier restoration method.

The feasibility of this algorithm is proved by the simulated demodulation without any noise.But, there is no doubt that phase noise always exists in an actual interferometer and appears along with the sensing signal.So,itis indispensable to test the capability of the SCR method under different SNR and verify whether the phase noise will trigger an extra error on demodulated signal.

Here,we define the signal-to-noise-ratio (SNR) as (16)

assuming that，is uniform white noise,and SNRis from 0.1 to 10 by changing amplitude of.Further, we set,,,and the sample rate is .Simulative demodulation results based on the SCR method are shown in Fig.5.From Fig.5(a),we can see that when the SNR is greater than 5, the absolute error of equals zero which is picked up by the SCR method. When the SNR approaches to 0.1，the absolute error increased. Evenso, the maximumabsolute erroris less than and the maximum standard deviation is only.Further,we evaluate the influence of this small error,and result is shown in Fig.5(b).The dot represents the THD of demodulated signals with theoretical predication,and the star represents THD of demodulated signals with the SCR method.We can find that the results under two circumstances are coincided well. The correlation coeffcient is up to O.999. This means that the SCR method can work well under low $\mathsf { S N R } ,$ and only triggersa verysmall error.Itisclear that this errorhas little effect on demodulated signal.

The SCR method directly picks up the carrier information (frequencyand phase) from interference signal andaccomplishes the carrier restorationprocessing synchronically.It means that the time delayof conversion time between analog and digital or the transmission time of laser in the leading fiber and sensing fiber has no effect on demodulation process. Because of the carrier mixing signalis originated from the interference signal.All the phase delay contains in the interference signal will transfer to the carrier mixing signal, too. Therefore,this methodcan ensure that the carrier mixing signalis completely matching with the interference signal.

![](images/ec28443b1752b2eb0dc95514605ea5e3796c87f20718ae80dafbff175094462c.jpg)  
Fig. 5.Results of the synchronous carrier restoration method underdifferentSNR.

frequency ofis applied to the interferometer by directly current modulating the semiconductor laser to get the carrier phase signal. The carrier signal is generated by a signal generator (NI PXI-5406). The lightis propagation in the single mode fiber.A fiber splitter is employed to separate the light passing through the fiber isolator into reference beamand several interference beams.Thereference beamis directly detected by low-noisepositive intrinsic-negative photodiode (PIN1),and this signal will be used to eliminate the laser intensity modulation (LIM)of interference signal[11,12];A custom-made fiber collimator is employed to separate the interference beam passing through the fiber circulatorinto reference armand signal arm.The light-emittingsurfaceof collimatorisplatteda $3 0 \%$ reflecting film. So a partof lightisreflected into the fiberagainby the collimatorreflecting film and back-propagation as the reference arm of interferometer. Others transmitted from the collimator and then penetrate into the collimator again after transferring the sensing area twice,due to the existence of reflector mirror which is handled bya piezoelectric transducer (PZT).This part is as the signal arm of interferometer. Consequently,the signal armand reference arm are collinearactually and the arm path difference isnearly $2 0 \ \mathrm { c m } .$ ，Therefore,interference pattern is created after they are combined,and then detected by photodiode (PIN2). The outputs ofthe photodiode are then sampled to simultaneously at the sampling rate ofusing a multifunction data acquisitioncard (NI PXIe-6366),and thentransmitted into a computer toperform improved digital PGC demodulation algorithm with thesynchronous carrier restoration method. The sample period is . This card has two digital-to-analog output channels,and the PZT control signal can output byit. The entire experiment instrumentsare placed on an optical bench supported by four air suspension legs.

![](images/ca9d4247d62d9401bb927251abab77a606037c8453e2dace3e0e06552262197e.jpg)  
Fig. 6.Schematic of experimental instruments.

# 4.Experimentsand results

![](images/98bed68a4e369f6a41699ff74ceae89af23170198e1d475d0c7300eb714c2705.jpg)  
Fig.7.Picture of experimentalinstruments.

In order to verify the feasibilityof synchronous carrier restoration method, the experiment instruments is set up as shown in Fig.6 and Fig.7.AmodifiedFizeau interferometer is employed in the experiment. A distributed-feedback semiconductor laser (NLK1B5EAAA,）is chosen as the light source.A sinusoidal phase carrier signal at the

# 4.1 Contrast of different carrier mixing signals

In experiment, we apply a stable sinusoidal voltage signal to the PZT which frequency is and amplitude is.This signal willbe converted into a stable vibration signal and detected by the interferometer as shown in Fig.6.The phase shift coefficient of the PZT is.Further, two kinds of carrier mixing signals are got to demodulate the vibration signal.Theyare theinitialcarriersignalfromthePGCalgorithmand therestoration carriersignal from the SCR method,respectively.From Fig.9,we can see that the carrier mixing signal generated by the SCR methodiscompletelymatchingwiththe interferencesignal.Different from this,the initial carrier signal hasan obvious time delay with the interference signal.The time delayis major triggered by the conversion timeofDAC andADC.More concretely,the initial carrier signalisconvertedtoanaloguesignalbyaDACandamplifiedbefore added into the FOI. Then, the interference light intensity of the FOI is converted to analogue signal bya photodiode,and furtherconverted to digital signal by an ADC.After that, the interference signal will be combined with the initial carrier signal in digital PGC algorithm. It is obviously that,due to the existance of conversion time， the interference signal will hasa time delay relative to the initial carrier signal,and this efect will be gradually accumulated.The carrier modulating period is,so the correspondence phase delay is,this will trigger a distortion component accorrding to the former theoretical analysisin Eq.(1O).Additionally, the laser transmission time can be ingored in our experiment, due to the length of the fiber (leading and sensing) isonlyabout.This mustbe considered and willbe more complex fora long distancelarge-scale distributed fiber-optic interferometer sensors array.

![](images/ccde42209aa857a0d6679cd68ad7f72498e3acca402ccc2660cf79b82ba6bcb3.jpg)  
Fig.9.Interference signal and carrier mixing signal which is oroduced by different methods.

Additionally,from Fig.10,we can see that the corresponding demodulated signalwith the initial carrier signal and the SCR method are different The former present a good performance and is well coincided with the desired sinusoidal signal, the THD is only $0 . 0 9 1 \%$ and the SINAD is .In contrast, the demodulated signalwith the initial carriersignal isseriouslyaffected bythephase delayand presentsan obvious distortion not only the amplitude but also the waveform. The THD is up to $1 8 . 3 8 3 6 \%$ and the SINAD is only.More seriously, the symbol is opposite with the desired sinusoidal signal.

![](images/b5753cd0c2d1ad73886a40870e573975557dfafd9f3f7a9149aa8e039d06c3c0.jpg)  
Fig.10.Demodulated results with different method.

# 4.2 linearity of the improved PGC algorithm based on SCR method

Furthermore,we linearly change the amplitude of sinusoidal voltage whichis applied to the PZT to generatea linearly increase vibration signal.This vibration will be detected bythe interferometer and demodulated by the improved PGC algorithmshown inFig.4.The details resultsare shown in Fig.11,the demodulated signals present a good linearityperformance,and the linear fittingcorrelation coefficient is up to 0.999.Results indicate that the system has a good linearity.

![](images/13fc0ba1d95d132e3efa97d5f9a0d4c81c1bdb5e315f7273641305042d0f4ec5.jpg)  
Fig.11.Voltageapplied to PZTand demodulated phase signals.

# 4.3Demodulated signals of PGC-Arctan under different phase delay

Moreover,in order to evaluate the performance of the SCR method and verify the theoretical analysis of distortion components, we assume the carrier mixing signal from the SCR methodas the benchmark,and continue activelyadd phase delay step-by-step from 0 to into the interference signal,here,one step is.A stable single frequency sinusoidal signal at the frequencyof isapplied to the PZT, and other parameters are same just like above.With this method, we can get the experimental measured distortion component of PGCArctanalgorithm induced by the carrier phase delay effects.At the same time,we also calculate the theoretical predicted ones by Eq.(14). The measured and theoretical predicted results are shown in Fig.12. We can see that the measured distortion component is in good agreement with the theoretical predicted ones,and the correlation coefficient is up to 0.99231 in the gray core area which includes the 90 percent of data.

![](images/803d1edfddc10709a779cc595eb0bdc148deb541e0af14ad9cb4a8cd4f442c98.jpg)  
Fig.12.Distortion component of measured andtheoretical predicted one.

According to the results of the above experiments,the improved PGC algorithm based on the synchronous carrierrestoration method can work well in an actual system,and the synchronous carrier restoration method can valid eliminate the phase delay effects and improve the performance of the FOIS system.

# 5.Conclusion

In this paper,an improved digital PGC algorithm based on the synchronous carrier restoration (SCR) method has been reported. Both the theoretical analysis and corresponding experiments have beencarried out to investigate the carrier phase delay effect and the performance of SCR method.The carrier phase delay effect has been analyzed and the analytic expression of distortion component has been derived.The improved PGC algorithm based on the SCR method has demonstrated with the vibration measurement Compared with the traditional PGC algorithmwith initial carriersignal, ithasamuch lower THDaswell asa better SINAD.Alow THDof below $0 . 1 \%$ andahigh SINAD of have been got fora small sinusoidal vibration signal induced byPZT.The demodulated signals with SCR method present a good linearity performance,and the linear fiting correlation coefficient is up to 0.999.With the improved digital PGC algorithm based on the synchronous carrier restoration (ScR) method, the performance of FOIS can be improved significantly.

Funding Information. National Science Foundation of China (NSFC) (41205022,41475024,41205010)

Acknowledgment. We thank Dr. Wenyue Zhu and Honghua Huang for their help and encouragements.

# References

1.G.G.Thomas,A.B.Joseph,A. Dandridge,et.al."Optical fiber sensor technology,"Transactions on Microwave and Techniques MTT-30(4), 472-499 (1982).   
2.Y. Liu, L.W.Wang, C.D.Tian,et.al."Analysis and optimization of the PGC method inall digital demodulation systems,"J. Lightw.   
Technol.26(18),3225-3233 (2008).   
3.H. Xiao,F.Li,Y.L.Liu.“Crostalk analysis of a fiber laser sensorarray system based on digital phase generated carrier scheme,"J.Lightw. Technol.26(10),1249-1255 (2008).   
4.S.C. Huang and H. Lin,"Modified phase-generated   
carrierdemodulation compensated for the propagation delay of thefiber," Appl.Opt.46(31),7594-7603 (2007).   
5.J.He,L.Wang,F.Li,et.al.“Anameliorated phase generatedcarrier demodulation algorithm with low harmonic distortion and highstability," J. Lightw.Technol.28(22),3258-3265 (2010).   
6.A.D. Kersey,A. Dandridge,A.B.Tveten."Time-division multiplexing of interferometricfiber sensors using passive phase-generated carier interrogation,",Opt. Lett.12(10),775-777(1987).   
7.A. Dandridge,A. B.Tveten,T.G.Giallorenzi, et.al.“Homodyne   
demodulation scheme for fiber optic sensors using phase generated carrier,"IEEE J.Quantum.Electron.QE-8(1O),1647-1653(1982).   
8.Y.W.Tong, H.L. Zeng, L.Y.L,and Y.Zhou.“Improved phase generated carrier demodulationalgorithm for eliminating light intensity disturbance and phase modulation amplitude variation,"Appl. Opt.51(29),6962- 6967 (2012).   
9. Q.P.Shi, Q.Tian."Performance improvement of phase generated carrier method is eliminating the laser intensity of seismometer," Optical Engineering.49(2):024402 (2010).   
10. G.Q.Wang,T.W.Xu,F.Li. "PGC demodulation technique with high stability and low harmonic distortion,"IEEE Photonic T.L.24(23), 2093-2096 (2012).   
11. S.Kobayashi,Y.Yamamoto,T. Kimura.“Modulation frequency characteristics of directly modulated optical frequency modulated   
AlGaAssemiconductor lasers," Electron.Lett.17(1O),350-351(1981). 12. K.Kirkendall,A.Dandridge.“Overview of high performance fiberoptic sensing,"J.Phys.D.Appl.Phys.37 (04),197-216 (2004).