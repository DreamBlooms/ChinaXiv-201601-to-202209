# Deep space communication channel characteristics under solar scintillation

Tong WU1.2.3, Yi YAN1,2, Yongcheng $\mathrm { L I } ^ { 1 }$ , Chunmei WANG², Xiujuan YAO², Xue LI2 1The State KeyLab.ofComplex Electromagnetic Environment Efects on Electronics and Information System,Luoyang, China 2Center for Space Science and Applied Research, Chinese Academy of Sciences, Beijing, China 3University of Chinese Academy of Sciences, Beijing, China wutong963852@163.com, yanyi $@$ nssc.ac.cn, lyncan $@$ 163.com, wangchm $@$ nssc.ac.cn, yaoxj@nssc.ac.cn, lixue @nssc.ac.cn

Abstract-Electromagnetic wavesused for deep space communications are mainlyaffected by the charged particles ejected by the sun.These effects may result in degradation of communication quality or communication interruption. This paper discusses the effects of solar scintillation on electromagnetic waves,including the scintillation index which isa measure of the intensity scintillation,the coherence bandwidth and the coherence time of deep space communication channel. The deep space communication channel under solar scintillation ismodeled by using Rician fading channel according to the scintillation index.The coherence bandwidth will determine whether the channel is flat fading or frequency selective fading and the coherence time will determine whether the channel is slowfading or fast fading.The approach of choosing signal bandwidth is determined by the coherence bandwidth and the coherence time with the change of the solar elongation angle.The simulationresultsshow thebit errorrate of the signal bandwidth chosen by the proposed approach is lower than a random choice.

Keywords-coherence bandwidth; coherence time; fading channel;solarscintillation

# I．INTRODUCTION

The effects of solar scintillation on radio waves may result in degradation of communication quality even communication interruption， such that data transmission， telemetryor telecommand would fail, when deep space probes suffer solar conjunction.In order to avoid the damage of deep space probes caused by solar corona, solar wind and cosmic ray, the data must be transmitted to the earth in time.So it is significant to ensure the reliability of the communication link under solar scintillation.

In terms of physical mechanism,solar corona and solar wind are considered as random media[1].Brown[2] studied the moment equations in random media.Lee et al.[3] studied the fourth-moment equation and obtained scintillation index. Woo et al.[4] analyzed the spectral broadening of monochromatic radio signal when the solar scintillation and solar event occurred. The reciprocal of spectral broadening is namely coherence time.Xu et al.[5] studied mutual coherence function and coherence parameters of random media and used the parameters to analyze the ionospheric irregularities.

In order to study the reliability of the communication link under solar scintillation,Feria et al.[6] modeled the amplitude scintillation effects on telemetry signals by means of the statistical characteristics of the telemetry data,but he did not consider the coherence time and the coherence bandwidth in the model.

The purpose of this paper is to model the deep space communication channel under solar scintillation by using Ricianfadingchannel according to the scintillation index,and to give an approach to choose the signal bandwidth by means of the coherence bandwidth and the coherence time.So,in Section II,we give the definitions of scintillation index coherence bandwidth and coherence time,respectively.And then we simulate the three parameters of characteristics versus solar elongation angle and so on.The results can be explained by the turbulence theory ofKolmogorov[7]. In Section III, we present the model of the deep space communication channel and briefly review the fading channel characteristics by comparing the coherence bandwidth and the coherence time to the signal bandwidth.Then in Section IV,we simulate the fading channel obtained in Section III with the characteristics obtained in Section II and propose an approach of choosing signal bandwidth.In Section V,we conclude the paper.

# II．INFLUENCE BY THE SOLAR WIND

The electromagnetic waves emitted by the deep-space satellites are affected by the sun. The continuous solar wind and occasional coronal mass ejections are main solar events which may affect the electromagnetic waves.The charged particles of interplanetary space are seen as plasma and will mayresult inthe intensityscintillation， thespectral broadening and phase scintillation[8,9]. The inverse of the spectral broadening is the coherence time[5].The signal is assumed as a monochromatic radio wave to elicit the intensity scintillation and the coherence time,and as a two-frequency radio wave to elicit the coherence bandwidth.

# A.Intensity Scintillation.

Intensity scintillation is the intensity fluctuation of the received electromagnetic wave,usually with the scintillation index to indicate the degree of the intensity scintillation. The scintillation index reflects the strength of small scale of the turbulent density fluctuations[8] and it is defined as[7]:

$$
m ^ { 2 } = \frac { \Bigl \langle ( I - \langle I \rangle ) ^ { 2 } \Bigr \rangle } { \langle I \rangle ^ { 2 } } { = } \sigma _ { I } ^ { 2 } = B _ { I } ( x , \pmb { \rho } = 0 )
$$

It is proved by [2] that for weak scintillation, $B _ { I } ( x , { \ \pmb \rho } ) =$ $4 B _ { \chi } ( x , \ \pmb { \rho } )$ ，and $B _ { \chi } ( x , \ \pmb { \mathsf { p } } )$ is the correlation function of the magnitude. So scintillation index can be expressed as[7,10]:

$$
m ^ { 2 } = 4 B _ { \chi } ( x , \mathbf { p } = 0 ) = 4 \sigma _ { \chi } ^ { 2 }
$$

Using Rytov's approximation， the amplitude fluctuation variance can be calculated and given by [9]:

$$
\sigma _ { \chi } ^ { 2 } = 0 . 5 6 3 k ^ { 7 / 6 } \pi ^ { 1 / 2 } a _ { 1 } R ( L _ { 1 } L _ { 2 } / L ) ^ { 5 / 6 } c _ { n 0 } ^ { 2 }
$$

where $a _ { 1 } { = } 0 . 8 5 [ 1 1 ]$ ： $\scriptstyle { k = 2 \pi / \lambda }$ is the wave number. $\lambda$ is the electromagnetic wavelength in the random media. $R , L , L _ { 1 } , L _ { 2 }$ are shown in Fig. 1. $c _ { \mathrm { n 0 } }$ is the structure constant at the closest approach point of the propagation pathand given by [3]:

$$
c _ { n 0 } \approx \frac { 5 5 . 5 9 \sigma _ { n e } } { f ^ { 2 } L _ { 0 } ^ { 1 / 3 } }
$$

where $\sigma _ { \mathrm { n e } }$ is the RMS electron density at the closest approach point of the propagation path and is directly proportional to the electron density of the solar wind. $f$ is the carrier signal frequencyand $L _ { 0 }$ is the outer scale of the solar wind turbulence. $c _ { \mathrm { n 0 } }$ is related to solar elongation angle.

Fig.2a shows that when the propagation path approaches to the sun， i.e. solar elongation angle decreases， the scintillation index will increases until saturation because of the increase of $c _ { \mathrm { n 0 } }$ at the closest approach point. And the higher the wave frequency is, the smaller the scintillation index is before saturation.Fig.2b shows that the scintillation index decreases with the outer scale increasing，which can be explainedbyKolmogorovturbulentenergy.spectrum theory[7].With the outer scale increasing,the probability of the turbulent scale falling into the inertial subrange increases, which means the property of the turbulence changes from anisotropy to isotropic,so the impact on the electromagnetic wave and the scintillation index decreases.

![](images/efd59091674fc4d078e606c1c6599cce3cc37d446a63714f3d5e3581a4aa8864.jpg)  
Figure 1．Propagation path geometry.

![](images/f3ea8b97d2b8d014927aef22078cc2c241ee83f8dc447e45e6f4c5bfa6162db3.jpg)  
Figure 2.a.The scintillation index versus solar elongation angle.b.The scintillation index versus the outer scale.

# B.Coherence Bandwidth.

The coherence bandwidth in random media is derived by two-frequency mutual coherencefunction, namelythe second-moment parabolic equation[5,12]. The coherence bandwidth represents the maximum frequency difference of the frequency response at two frequencies remaining strong correlation.Two sine waves with different frequency whose frequency difference is greater than the coherence bandwidth are differently affectedby the channel.

The definition of the coherence bandwidth is given by [4] for ionospheric irregularities:

$$
\omega _ { c o h } = - \frac { 1 2 \pi } { \lambda } \frac { A _ { 0 } } { \sigma _ { \phi } ^ { 2 } A _ { 2 } } \frac { z } { ( 3 z L - 2 L ^ { 2 } ) } \omega
$$

where $\omega$ is the center angular frequency of electromagnetic wave. $L$ is the thickness of the irregularity. $\sigma _ { \phi } ^ { 2 } = L k _ { p } ^ { 4 } A _ { 0 } \big / 4 k ^ { 2 }$ （20 is phase fluctuation variance.The electron plasma angular frequency and the wave number are:

$$
\omega _ { p } ^ { 2 } = \frac { e ^ { 2 } N _ { e } } { m \varepsilon _ { 0 } } , \mathrm { a n d } k _ { p } = \omega _ { p } / c
$$

where $N _ { \mathrm { e } }$ is the electron density $( 1 / \mathrm { m } ^ { 3 } )$ ： $e$ and $m$ are the charge and mass of the electron，respectively. $ { \varepsilon } _ { 0 }$ isthe dielectric constant in vacuum.When the angular frequency of electromagnetic wave is greater than $\omega _ { p }$ ，electromagnetic waves can propagate in the plasma,otherwise it will suffer total reflection or strong attenuation. The coefficient is also defined by [4]:

![](images/a8d6b153d80e5a5cbac87d2fd098150dbcca7e9ccf3b2d1daffe81d230f09d3e.jpg)  
Figure 3.a.The coherence bandwidth versus solar elongation angle.b.The coherence bandwidth versus the outer scale.c.The coherence bandwidth versus the inner scale.

$$
\begin{array} { r } { \left\{ A _ { 0 } = ( 2 \pi l _ { 0 } / \kappa _ { 0 } ) ^ { 1 / 2 } \sigma _ { \xi } ^ { 2 } \mathbf { K } _ { ( p - 2 ) / 2 } ( \kappa _ { 0 } l _ { 0 } ) / \mathbf { K } _ { ( p - 3 ) / 2 } ( \kappa _ { 0 } l _ { 0 } ) \right. } \\ { \left. \left[ A _ { 2 } = - ( \pi \kappa _ { 0 } / l _ { 0 } ) ^ { 1 / 2 } \sigma _ { \xi } ^ { 2 } \mathbf { K } _ { ( p - 4 ) / 2 } ( \kappa _ { 0 } l _ { 0 } ) / \mathbf { K } _ { ( p - 3 ) / 2 } ( \kappa _ { 0 } l _ { 0 } ) \right. \right. } \end{array}
$$

where $\mathrm { ~ K ~ }$ is a modified Bessel function of imaginary argument. $l _ { 0 }$ is the inner scale of the solar wind turbulence,which is $5 0 { - } 2 0 0 \mathrm { k m } [ 1 3 ]$ , and $\kappa _ { 0 } { = } 1 / L _ { 0 }$ ， $\sigma _ { \xi } ^ { 2 } = \left. \xi ^ { 2 } \right. \leq 1$ ， $\scriptstyle \xi = \Delta N _ { \mathrm { e } } / \langle N _ { \mathrm { e } } \rangle$ . When the spectral index $\scriptstyle { p = 1 1 / 3 }$ ，Shkarosfsky spectrum degenerates to Kolmogorov spectrum.

The coherence bandwidth of ionospheric irregularities is analyzed by [4],and we extended it into interplanetary space by making a little change of (5） for both weak and strong scintillation:

$$
\omega _ { c o h } = - \frac { 1 2 \pi } { \lambda } \frac { A _ { 0 } } { \sigma _ { \phi } ^ { 2 } A _ { 2 } } \frac { \omega } { L } , f _ { c o h } = \frac { \omega _ { c o h } } { 2 \pi } = - \frac { 6 } { \lambda } \frac { A _ { 0 } } { \sigma _ { \phi } ^ { 2 } A _ { 2 } } \frac { \omega } { L }
$$

Fig.3a shows the coherence bandwidth decreases with solar elongation angle decreasing,especially within $1 ^ { \circ }$ of the angle.And increasing the center frequency helps to increase the coherence bandwidth of the channel.Fig.3b shows that the coherent bandwidth increases with the outer scale of the turbulence.It can also be explained by Kolmogorov turbulent energy spectrum theory[7] resembling the explanation of the scintillation index. Fig. 3c showsthat the coherence bandwidth increases with the inner scale of the turbulence, because the probability of the turbulent scale falling into the dissipation range increases.

# C.Coherence Time.

The coherence time in random media is derived by temporal mutual coherence function which is namely the temporalsecond-momentparabolicequation[4].The coherence time represents the maximum time difference of the impulse response at two temporal channels remaining strong correlation. When the time difference is less than the coherence time,the channel characteristics are substantially the same.

The spectral broadening is given by [3]:

$$
B = 0 . 5 4 2 ( c _ { n 0 } k ) ^ { 6 / 5 } ( a _ { 1 } R ) ^ { 3 / 5 } \nu
$$

where $\nu$ is the average velocity of the solar wind at the closest approach point and perpendicular to the propagation path.

So the coherence time of the channel is:

$$
T _ { \scriptscriptstyle c o h } \approx 1 / B = 1 . 8 4 5 ( c _ { \scriptscriptstyle n 0 } k ) ^ { - 6 / 5 } ( a _ { \scriptscriptstyle 1 } R ) ^ { - 3 / 5 } \nu ^ { - 1 }
$$

![](images/f05d7d6e967456ab3e0f65a4b90c9c8b352fd57fd5291b666eaabde75f0509a7.jpg)  
Figure 4.a.The coherence time versus solar elongation angle.b.The coherence time versus the outer scale.

Fig.4a shows the coherence time decreases with the solar elongation angle decreasing,which is similar to the coherence bandwidth.And increasing the center frequency helps to increase the coherence time of the channel.Fig.4b shows that the coherence time increases with the outer scale of the turbulence resembling the coherence bandwidth.

# III.CHANNELMODEL

The deep space communication channel model would be presented in this section based on the factors obtained above. The propagation factor caused by the solar scintillation is seen asmultiplicative noise,while the noise and interference are seen as additive noise.

![](images/484169839b4de3adb79562b792f3fc5f3c7dfb62cf13db1fa40ac348ee255ade.jpg)  
Figure 5.The deep space communication channel model.

Assume that the multiplicative noise factor is $\boldsymbol { a } _ { \mathrm { s c } } ( t )$ ，the noise and interference are $n ( t )$ and $J ( t )$ ，respectively. So the deep space communication channel model is shown in Fig.5.

The relationship between the scintillation index $m$ and the Rician factor $\gamma$ of Rician distribution is derived by Shaft[14]:

$$
\gamma = { \frac { \left( 1 - m ^ { 2 } \right) ^ { 1 / 2 } } { 1 - \left( 1 - m ^ { 2 } \right) ^ { 1 / 2 } } }
$$

Therefore,the probability density function(PDF）of the envelope $R { = } | a _ { \mathrm { s c } } ( t ) |$ can be considered as Rician distribution:

$$
P ( R ) = \frac { R } { \sigma ^ { 2 } } \exp \left( - \frac { R ^ { 2 } + R _ { 0 } ^ { 2 } } { 2 \sigma ^ { 2 } } \right) I _ { 0 } \left( \frac { R R _ { 0 } } { \sigma ^ { 2 } } \right)
$$

where $R _ { 0 }$ is the amplitude of the specular component. $\scriptstyle { \mathcal { O } } ^ { 2 }$ is the variance of Gaussian noise component. $I _ { 0 }$ iszero-order modified Bessel function of the first kind. $\gamma = R _ { 0 } ^ { 2 } \big / 2 \sigma ^ { 2 }$ is the Rician factor. The PDF of the envelope of the additive noise factor $n ( t )$ and $J ( t )$ can be simplified by Gaussian distribution， which means an AWGN (Additional White Gaussian Noise) channel.

The coherence bandwidth and the coherence time will limit the bandwidth of the transmitted signal to some extent. Assume that the bandwidth of the transmitted signal is $W _ { ; }$ and the duration of each symbol is $T { \approx } 1 / W .$ ，So if the deep space communication channel shows the flat and slow fading channel,the bandwidth and the duration of each symbol should satisfy:

$$
W \perp \ f _ { c o h } , \ T \perp \ T _ { c o h } \
$$

Equation(13) can be rewritten by means of $T { \approx } 1 / W$ as:

$$
T _ { c o h } ^ { - 1 } < W < f _ { c o h }
$$

So the scintillation index determines the amplitude of the signal,and the coherence bandwidth and the coherence time which are limitative factors determine the signal bandwidth.

# IV.SIMULATIONRESULTS

Wecalculate the theoretical Bit Error Rate (BER) performance with different scintillation indices in Fig.6.It shows that with the decrease of the scintillation index,the BER performance is getting better and is close to no scintillation channel （AWGN） at weak scintillation. The modulation is DBPSK and there is no channel code.

Assume that the signal bandwidth is W,and the duration of each symbol is $\mathrm { T } { \approx } 1 / \mathrm { W } ,$ ，so the coherent bandwidth and the inverse of the coherent time can divide the two dimensions of the solar elongation angle and the signal bandwidth into four regions,which is illustrated in Fig.7. The flat and slow fading channelis the easiestto be dealtwith.So in orderto determine the signal bandwidth,we should guarantee the channel is mostly flat and slow at different solar elongation angles. So the proposed approach is that choosing the intersection of the two curves,which is optimal.

![](images/f87684645f697bc10f5b69f26063373085281ccbed9c8f9649830639e3e008b7.jpg)  
Figure 6.Theoretical BER performance with different scintillation indices.

Fig.7 shows that the intersection of the two curves is about $4 0 \mathrm { { H z } }$ at 8.43GHz and $2 5 { \mathrm { - } } 6 0 \mathrm { H z }$ at 32GHz. So we choose $4 0 \mathrm { { H z } }$ to be the signal bandwidth and simulate BER performance versus solar elongation angle in Fig.8 and Fig.9. We also take $1 0 ~ \mathrm { { H z } }$ and $4 0 0 \mathrm { { H z } }$ asa comparison．The modulation is DBPSK and the SNR of AWGN channel is 12dB.Fig.8 shows that for strong scintillation the BER performance of $4 0 ~ \mathrm { H z }$ bandwidth is much better than $4 0 0 \mathrm { { H z } }$ but a little worse than $4 0 0 \mathrm { { H z } }$ when $\mathrm { \Delta } \mathrm { a } { \approx } 0 . 4 ^ { \circ }$ .This is because with the increase of solar elongation angle,the channel of 400 Hz signal bandwidth comes into slow fading channel a

![](images/60b96383ce8114d6b106a6cf2c4cfebdd8dd503fb58692a057867109fbef0b9b.jpg)  
Figure 7.Different areas of the property of the fading channel

little earlier than $4 0 \mathrm { { H z } }$ ．The channel of $^ { 4 0 } \ \mathrm { \ H z }$ signal bandwidth is better than $1 0 \ : \mathrm { H z }$ .For the region between strong and weak scintillation, the BER performance of $4 0 ~ \mathrm { H z }$ is also better than $1 0 \ : \mathrm { H z }$ .And for weak scintillation,the three curves are adjacent.In Fig.9, the carrier frequency is $3 2 \mathrm { G H z }$ and the BER performance of $4 0 ~ \mathrm { H z }$ is the best among three curves with solar elongation angle increasing.

# V.CONCLUSION

This paper studies the effects of the sun on electromagneticwavesindeepspacecommunications, including dissemination of factors and the noise and the interference. Deep space communication channel model is derived by using Rician fading channel model with additive white Gaussian noise channel model. The coherence time and coherence bandwidth are calculated to determine the characteristics of deep space channel and the signal bandwidth,which lays the foundation for the future conduct related to exploration activities.

![](images/4439cc056258a1019169ba6bda4016478bcb9ffbfe00daa3d3b9e0c93534cb0e.jpg)  
Figure 8．BER performance versus solar elongation angle (8.43GHz).

![](images/2150162011e89a4af2d29704f09eac9ec3915a332f8587a6e4671b3d24c56beb.jpg)  
Figure 9.BER performance versus solar elongation angle (32GHz).

# ACKNOWLEDGMENT

This work was supported by grant CEMEE2014K0105B from the State Key Lab. of Complex Electromagnetic Environment Effects on Electronics and Information System.

[10]R.Woo,"Radial dependence of solar wind properties deduced from HELIOS 1/2 and Pioneer 1O/11 radio scattering observations,"The Astrophysical Journal,vol.219,pp.727-739.1978.   
[11]R.Woo,"Multifrequency techniquesforstudying interplanetary scintillations,"The Astrophysical Journal,vol.201,pp.238-248.1975.   
[12]K.C.Yeh and C.H.Liu,"An investigation of temporal moments of stochastic waves,"Radio Science,vol.12,pp.671-680.1977.   
[13] Steven R.Spanglerand Carl R.Gwinn,"Evidence for an inner scale to the density turbulence in the interstellar medium,"The Astrophysical Journal, vol.353,pp.L29-L32.1990.   
[14]Paul D. Shaft,"On the relationship between scintillation index and Rician fading,”Communications,IEEE Transactions，vol.22，pp.731-732. 1974.

# REFERENCES

[1]L.C.Lee,"Wave propagation in a random medium:A complete set of the moment equations with different wavenumbers," Journal of Mathematical physics,vol.15,pp.1431-1435.2003.   
[2] J.R.Brown and P.Wilbur,"Moment equations for waves propagated in random media,"JOSA,vol.62,pp.45-54.1972.   
[3] L. C.Lee and J.R. Jokipii,"Strong scintillations in astrophysics. III - The fluctuations in intensity,"The Astrophysical Journal,vol.202,pp. 439-453.1975.   
[4] R.Woo,F.C.Yang and A.Ishimaru,"Structure of density fluctuations nearthesundeducedfromPioneer-6spectralbroadening measurements," The Astrophysical Journal,vol. 210,pp.593-602.1976.   
[5] Zhengwen Xu,Jian Wu and Zhensen Wu,"Second-order statistics of radio wave propagation through the structured ionosphere," Journal Of Atmospheric And Solar-Terrestrial Physics,vol.66,pp.971-980.2004.   
[6] Y.Feria,M.Belongie,T.McPheeters and H. Tan,"Solar scintillation effects on telecommunication links at Ka-band and X-band," The Telecommunications and Data Acquisition Progress Report, vol.129, pp. 1-11. 1997.   
[7] A.Ishimaru,Wave propagation and scattering in random media.IEEE Press and Oxford University Press,New York.1997.   
[8] C.M.Ho,M.K.Sue,A.Bedrossian and R.W.Sniffin,"Scintillation effects on radio wave propagation through solar corona," 27th URSZ General Meeting.2002.   
[9] D.D.Morabito,S.Shambayati,S.Finley and D.Fort,"The Cassini May 2000 solar conjunction,"Antennas and Propagation,IEEE Transactions, vol.51,pp.201-219.2003.