# Passive submillimeter-wave imaging demonstrated by two-element interferometer

Donghao Han1,², Hao Liu',Dehai zhang',Jin Meng', Xin Zhao', Ying Zhang1², Ji

Wu1, 1 National Space Science Center, Chinese Academy of Sciences, Beijing 100190, China 2 University of Chinese Academy of Sciences, Beijing 10o049, China $E$ -mail: liuhao@mirslab.cn

Abstract: Interferometric radiometer obtains passive brightness temperature images by correlation operation between different receivers,which would seriously increase hardware requirements and need high phase accuracy in submillimeter-wave (SMMW) spectral region. An interferometric radiometer based on two-element interferometer has been set up with specialized high accuracy SMMW devices in this paper. Point-source target calibration has been introduced to reduce instrumental error. Interference fringes and point target images are presented by this SMMW interferometer. The linear phase error of interference fringes is better than $2 ^ { \circ }$ . The angular resolution is $0 . 5 7 ^ { \circ }$ . System performance is in accord with theoretical analysis. This interferometer demonstrates a new way for passive SMMW remote sensing.

PACS: 07.57.Kp

Key words: submillimeter-wave (SMMW) imaging, point-source target calibration, SMMW Interference fringes, interferometric imaging.

# 干涉式被动亚毫米波成像系统研究

韩东浩1²，刘浩¹，张德海¹，孟进¹，赵鑫¹，张颖1²，吴季」，

1．中国科学院国家空间科学中心微波遥感重点实验室，北京100190;

2．中国科学院大学，北京 100190

Abstract：干涉式辐射计通过多通道间的相关运算得到被动亮温图像。对于亚毫米波段(submillimeter-wave,SMMW)相关运算对硬件系统的精度与相位稳定性提出了很高的要求。本文中，通过特殊设计的高精度SMMW器件，实现了一套基于二单元干涉仪的干涉式辐射计系统。针对该系统的自身特点，作者提出了点源目标响应定标方法来降低系统误差。系统完成后，分别进行了干涉条纹实验和点源目标成像实验。经测试，系统的线性相位误差小于 $2 ^ { \circ }$ ，角分辨率优于 $0 . 5 7 ^ { \circ }$ 。系统实测性能和理论分析结果一致。以上研究为今后设计高分辨率亚毫米波干涉式成像辐射计提供了重要的参考价值。

KeyWords：亚毫米波成像，点源目标响应定标，亚毫米波干涉条纹，干涉式成像

中图分类号：TN454 文献标识码：A

# Introduction

The submillimeter-wave (SMMW） spectral region， interval commonly from 300GHz to 3000GHz,is one of the most exciting and,at the same time,most frustrating sectors of the electromagnetic spectrum. Exciting because of the wealth of knowledge that can be gained from research at these frequencies; frustrating because techniques have lagged behind those at lower and higher frequencies[1]. With technology advancing recentlyl2]，SMMW detector is playing a more and more important role in remote sensing field[3], such as security detection[4], meteorological observation[5].

In geoscience applications[6]， many molecules have characteristic absorption lines in SMMW spectral region, of which 380GHz is water vapor absorption spectra, and 425GHz is oxygen absorption spectra, et al. Many attempts have been made around SMMW electromagnetic spectrum and several have succeeded with such fruits as Aura[7]，and SMILEs[8].Geostationary Interferometric Microwave Sounder (GIMS)9] is a millimeter-wave imaging sounder concept proposed for China's next-generation geostationary meteorological satellite (FY-4M). Some millimeter wave(MMW） bands，such as 50-56GHz and 183Ghz，have been developed for GIMS[10]. Because of short wavelength, SMMW spectra is also fascinatingly helpful for GIMS to increase the special resolution, which is crucial for geostationary remote sensing.

Most of existing SMMW sensors are based on spatial domain scanning imaging or focal plane array imaging. The spatial domain scanning imaging system has a simple hardware structure but a large antenna aperture and long imaging period, like Microwave Limb Sounder (MLS） in Aura[7]1]. On the other hand, the focal lane array could decrease the imaging time but the cost of its hardware structure is sharply increased,as is the case with Heterodyne Instrument for the Far-Infrared (HIFI) in Herschel[12l. Diferent from those instruments,large antenna aperture willbe synthetic by means of some small antennas in interferometric radiometers,thus also called synthetic aperture radiometer[13]l．Spatial frequency domain sampling will be accomplished by mobile receivers,so there is a flexible tradeoff between systematic complexity and the imaging period. Unlike traditional radiometers， correlation measurement in interferometric radiometer needs phase information between the receivers[14]5]l That means high hardware stability and phase accuracy should be achieved in SMMW spectral region, because the short wavelength is very sensitive to delay error. As far as we know in the public reporting， the highest frequency of existing interferometric imaging radiometers is 183GHz，which is realized by GeoSTAR project[16].

In this paper, a passive SMMW interferometric radiometer is set up with two-element interferometer working at 440GHz. Because of its similarities in system, this SMMW interferometric radiometer will be compatible with GIMS other spectra instruments.Related SMMW services with high stability are developed for this interferometric radiometer to insure the hardware stability and phase accuracy in SMMWspectral region[17]l8l.Furthermore,a new calibration method,namely point-source target calibration， is introduced to eliminate instrumental errors. In Section 1, the observation is formulated for interferometric radiometer. Then the two-element SMMW interferometer and the point-source target calibration are presented in Section 2. In Section 3, we demonstrate the Interference fringes and point target images by this SMMW interferometer, followed by the conclusion and outlook in Section 4.

# 1FORMULATIONFORINTERFEROMETRICIMAGING

An elementary interferometer of interferometric radiometerl13] is shown in Fig. 1.

The two antennas are separated by a distance $D$ ，which is defined as the baseline,and observe a point-source located in $\theta _ { 0 }$ ，which is in the far field of the interferometer. So the incident wavefront can be considered as a plane over the

distance $D$ . In order to simplify the discussion, the receivers are assumed to have narrow bandpass filters that pass only signal components very close to $f _ { 0 }$

Then the output $V _ { i }$ in Fig.1 can be described as:

$$
\begin{array} { l } { { V _ { i } = \langle A ( \theta _ { 0 } ) \sin ( 2 \pi f _ { 0 } t + \varphi ) \cdot A ( \theta _ { 0 } ) \sin ( 2 \pi f _ { 0 } ( t - \tau _ { g } ) + \varphi ) \rangle \ } } \\ { { \displaystyle \propto A ^ { 2 } ( \theta _ { 0 } ) \cos ( 2 \pi f _ { 0 } \tau _ { g } ) } } \\ { { \displaystyle = A ^ { 2 } ( \theta _ { 0 } ) \cos ( 2 \pi \frac { D } { \lambda } \sin \theta _ { 0 } ) } } \end{array}
$$

![](images/f736c13d3df3541df1fd10b49f1de4e7a470063e593e05f8c020602a32d7b502.jpg)  
Fig.1 elementary interferometer   
图1：单元干涉仪

In Eq. (1)， $A$ is the signal strength of point source, $\lambda$ is the wavelength corresponding to $f _ { 0 }$ ，and $\tau _ { g }$ is the time delay between the two receivers. $V _ { _ q }$ can be got in the same way. When the source becomes area target, which can be expressed as $T ( \xi , \eta )$ ，and practical bandwidths are considered in the receivers, the output of elementary interferometer, shown in Fig. 1, can be described as[19]:

$$
V ( u , { \bf v } ) = \iint _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } \frac { T ( \xi , \eta ) - T _ { r } } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } \cdot F _ { 1 , 2 ^ { * } } ( \xi , \eta ) \cdot \tilde { r } _ { 1 , 2 } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) \cdot e ^ { - j 2 \pi ( u \xi + \nu \eta ) } d \xi d \eta
$$

Here， $( u , \nu )$ are the projections over the X-Y axes of the baseline $D$ normalized to the wavelength. $T _ { r }$ is the instrument temperature. $F _ { _ { 1 , 2 ^ { * } } } ( \xi , \eta )$ is the conjugate product of the receiver antenna pattern and the two receivers are numbered as 1 and 2. （2 $\tilde { r } _ { 1 , 2 }$ is the fringe washing function about the receiver frequency responsel20l. $V _ { _ q }$ and $V _ { _ i }$ correspond to the real and imaginary part of $V ( u , \mathbf { v } )$ respectively.

By changing baseline $D$ ， the synthetic aperture interferometric radiometer could get $V ( u , \mathrm { v } )$ in an effective spatial frequency domain. Then $T ( \xi , \eta )$ can be inverted by appropriate inverse algorithm[1[2].

# 2SYSTEMARCHITECTURE

This SMMW interferometric radiometer is set up by two-element interferometer. Because the short wavelength is very sensitive to delay error, correlation for the interferometer requires not only high hardware stability but also high phase accuracy. So the SMMW devices should be elaborately designed in the front end,and a high speed digital correlator is employed in the back end. What's more, a new calibration method, namely point-source target calibration, is proposed to eliminate instrumental errors.

# A. Modular Composition

This SMMW interferometer mainly consists of three parts: an antenna part,an analog front-end part and a digital correlator. Furthermore,a two-dimensional moving platform is employed to complete spatial frequency domain scanning. The integrated system is shown in Fig.2.

![](images/ccfd7e8e4a4d100dfe3301b6a02b6881ed69ed45a36d080d39e5e3b744ac3af6.jpg)

![](images/51994ddbc05ac4298ae60a68ac6c6e0f77911958b484d5b0d41e5da7c344f7fd.jpg)  
Fig.2 SMMW interferometer. (a) functional block diagram, (b) production after machining and electrical installation

图2：亚毫米波干涉仪 (a) 原理框图， (b) 加工装配后的实物图

In Fig.2(a), the dash line with arrows means flexible waveguides connection. Two receivers are fixed respectively on two moving arms of the moving platform. One arm can move horizontally and the other can move vertically, so the trace of these two arms is T-shaped， which is so-called T-shaped scanning. SMMW interferometer and the moving platform are set up as shown in Fig.2(b).

Horn antennas are employed in this system, which have a mature technology and high reliability. The antenna gain is 25.6dB,3 dB beamwidth is $1 0 ^ { \circ }$ ,the sidelobe level is lower than -3OdB,and the cross polarization level is better than $3 0 \mathrm { d B }$

The analog part mainly includes three components: a local oscillator (LO),a tripler and a mixer. Considering the level of processing technology at present, a circuit structure of anti-parallel diodes with self-bias is proposed in the triplerl17]，which is shown in Fig. 3(a). With this structure, not only can the difficult problem of processing bias circuit be solved, but also the odd-order frequency multiplication can berealized efficiently. After machining and electrical installation， the highest measured output power is $3 . 1 \mathrm { m W }$ at $2 2 1 ~ \mathrm { G H z }$ and the output power is more than $2 \mathrm { m W }$ at frequencies ranging from 219\~227 GHz.

![](images/38c02572b69c0319c715f027d1e6904ba6aeedbf097f10f1d95d54a87d0d0544.jpg)  
Fig.3(a) tripler production,(b) mixer production图3（a）三倍频器实物图, (b）混频器实物图

Behind the tripler isa 440GHz sub-harmonic mixer[18], which is shown in Fig. 3(b). An anti-parallel pair of Schottky diodes is the key component in the mixer. The length of the diodes is 74 μm,and the cutoff frequency of diodes is up to 8O00GHz. The suspended microstrip matching circuit is built on quartz,and the metal block is cut into two halves. The diode package and the matching circuit are integrated in the mixer model. The measured results indicate that the loss is below 17.O dB in the band ranging from 433\~451 GHz, with a 3 dB bandwidth of $1 8 \ : \mathrm { G H z }$

The digital part is a high speed digital correlator. This correlator solves the phase synchronization problem by using a cross synchronization scheme,which is based on low hardware cost FPGA controller. After the digital quantization, quadrature digital down conversion is employed to eliminate the quadrature error. In this correlator, the sampling rate can reach as high as 5GHz, the effective number of ADC is greater than or equal to 6bit[23], and the integration time is adjustable.

# B. Point-source Target Calibration

This SMMW interferometric radiometer has only one elementary interferometer. So the errors originating in receivers can be regarded as a simple modulation of the source image,as long as the errors are steady during one imaging period, which is easy to guarantee by this system. The most crucial error comes from the flexible waveguides connection，which is employed to complete spatial frequency domain scanning. To solve this problem, a point-source target calibration method is presented in this paper.

During every imaging period, the system has the same moving trace. The error coming from the flexible waveguides can be described as a function of coordinates in spatial frequency domain. $A ( u , \nu )$ and $\varphi ( u , \nu )$ mean magnitude and phase errors respectively. Then, Eq. (2) becomes

$$
\begin{array} { r l } & { V ( u , \mathrm { v } ) = \displaystyle { \int _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } } \frac { T ( \xi , \eta ) - T _ { r } } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } { \cdot } F _ { 1 , 2 ^ { * } } ( \xi , \eta ) { \cdot } \tilde { r } _ { 1 , 2 } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) } \\ & { \quad \cdot e ^ { - j 2 \pi ( u \xi + \nu \eta ) } \cdot A ( u , \nu ) \varphi ( u , \nu ) d \xi d \eta } \end{array}
$$

When considering a point source target located on $( \xi _ { 0 } , \eta _ { 0 } )$ ,we have

$$
\begin{array} { r l } { V ( u , \mathrm { v } ; \xi _ { 0 } , \eta _ { 0 } ) = \displaystyle \int \displaystyle \int _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } \frac { \delta ( \xi - \xi _ { 0 } , \eta - \eta _ { 0 } ) + \Upsilon _ { p } - T _ { r } } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } \cdot F _ { 1 , { \tiny 2 ^ { * } } } ( \xi , \eta ) \cdot \tilde { r } _ { 1 , 2 } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) } & { } \\ { \cdot e ^ { - j 2 \pi ( u \xi + \nu \eta ) } \cdot A ( u , \nu ) \varphi ( u , \nu ) d \xi d \eta } & { } \end{array}
$$

in which, $\mathrm { T } _ { \mathfrak { p } }$ is the background brightness of the point source. A flat target response $V ( u , \mathrm { v } ; T _ { p } - T _ { r } ^ { \prime } )$ can be got by turning off the point-source

$$
\begin{array} { r l } & { V ( u , \mathrm { v } ; T _ { p } - T _ { r } ^ { \prime } ) = \displaystyle \iint _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } \frac { \mathrm { T } _ { p } - T _ { r } } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } \cdot F _ { 1 , 2 ^ { * } } ( \xi , \eta ) \cdot \tilde { r } _ { 1 , 2 } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) } \\ & { \quad \quad \cdot e ^ { - j 2 \pi ( u \xi + \nu \eta ) } \cdot A ( u , \nu ) \varphi ( u , \nu ) d \xi d \eta } \end{array}
$$

in which, $T _ { r } ^ { \prime }$ is th instrument temperature during flat target imaging[24], which may be different from other imaging. Flat target response will be used as flat target calibration for Eq. (4):

$$
\begin{array} { l } { { \displaystyle V ^ { \prime } ( u , { \mathrm { v } } ; { \xi } _ { 0 } , { \eta } _ { 0 } ) = V ( u , { \mathrm { v } } ; { \xi } _ { 0 } , { \eta } _ { 0 } ) - \frac { T _ { r } - \mathrm { T } _ { p } } { T _ { r } ^ { \prime } - \mathrm { T } _ { p } } V ( u , { \mathrm { v } } ; \mathrm { T } _ { p } - T ^ { \prime } ) } } \\ { ~ = ~ \displaystyle \iint _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } \frac { \delta ( \xi - \xi _ { 0 } , \eta - \eta _ { 0 } ) } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } \cdot \tilde { r } _ { 1 , 2 } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) }  \\ { ~ \cdot F _ { { 1 , 2 ^ { * } } } ( \xi , \eta ) \cdot e ^ { - j 2 \pi ( u \xi + \nu \eta ) } \cdot A ( u , \nu ) { \varphi } ( u , \nu ) d \xi d \eta } \end{array}
$$

When $( \xi _ { 0 } , \eta _ { 0 } ) \approx ( 0 , 0 )$ ， $\sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } \approx 1$ . Influence of fringe washing function $\tilde { r } _ { 1 , 2 }$ can be neglected. The weighting effect of antenna pattern becomes a constant approximate to 1, which can also be ignored. Then Eq. (6) can be used as point-source

target calibration for a common measuring as described in Eq. (3):

$$
\begin{array} { l } { { \displaystyle V ^ { \prime } ( u , \mathrm { v } ) = \frac { V ( u , \mathrm { v } ) } { V ^ { \prime } ( u , \mathrm { v } ; \xi _ { 0 } , \eta _ { 0 } ) } } \ ~ } \\ { { \displaystyle ~ = \ \iint _ { \xi ^ { 2 } + \eta ^ { 2 } \le 1 } \frac { T ( \xi , \eta ) - \mathrm { T } _ { r } } { \sqrt { 1 - \xi ^ { 2 } - \eta ^ { 2 } } } \cdot \tilde { r } _ { 1 , 2 } ( - \frac { u \xi + \nu \eta } { f _ { 0 } } ) \cdot F _ { 1 , 2 ^ { * } } ( \xi , \eta ) \cdot e ^ { - j 2 \pi \lvert u ( \xi - \xi _ { 0 } ) + \nu ( \eta - \eta _ { 0 } ) \rvert } d \xi d \eta } } \end{array}
$$

in which,the calibrated result $V ^ { \prime } ( u , \mathrm { v } )$ can be regard as a space shift of the raw $V ( u , { \bf v } ) .$ （204号

Furthermore, the relationship of flat target transformation and point-source target transformation is delicate.In theory, Dirac delta function and constant function are a Fourier transform pair in Fourier transform theory. So the visibility function of flat target is approximate to delta function， and the visibility function of point-source target is similar to constant function.

In practical application, flat target calibration is an additive operation,which is aimed at minimizing the impact of the antenna errors by minimizing $T ( \xi , \eta ) - T _ { r }$ ，as described in Eq. (2). Point-source target calibration is a multiply operation, which is used to eliminate multiplicative error. These two calibrations have no interference with each other. Indeed, flat target calibration will help point-source target calibration to eliminate the influence of instrument temperature, just as shown in Eq. (6).

Generally， flattarget calibration can work for all syntheticaperture interferometric radiometers,and point-source target calibration will take effect on the time-sharing system which has a scanning period. But when introduced to a complex system with more than one elementary interferometer, the inconsistency between the receivers should be considered in Eq. (6) and Eq. (7).

# 3 EXPERIMENT

# A.Interferometric Fringes experiment

Fixing the baseline of interferometer, and moving the point-source in the horizontal direction of the baseline, we can get interferometric fringes as shown in Fig. 4(a). The phase of interferometric fringes is shown in Fig. 4(b).

![](images/8f4f1c75d5cad0db9bba4037efab2f8605ee03e9d48d0d1376dd5ca6cd645208.jpg)  
Fig.4(a)interferometric fringes, (b)linear phase of interferometric fringes图4（a）干涉条纹（b）干涉条纹的线性相位

During the experiment, the SMMW interferometer is working at 440GHz and the length of baseline is $5 9 . 5 2 \mathrm { m m }$ ，vertical distance between interferometer and point-source is $1 1 0 0 \mathrm { m m }$ . By Eq.(1)， the displacement corresponding to one interferometric fringes period is $1 2 . 6 \mathrm { m m }$ ，and the measured value is $1 2 . 4 \mathrm { m m }$ The linear correlation coefficient of interferometric fringes is better than O.999,and the corresponding linear phase error is better than $2 ^ { \circ }$

# B. Point Source imaging

Fixing the location of the point source and scanning the spatial frequency domain can be completed by moving the arms of the two-dimension moving platform. The SMMW interferometric radiometer works at 440GHz,with the longest baseline $\lambda$ 70 in both directions of $\xi$ and $\eta$ . The primary retrieved image is shown in Fig. 5(a-b), and the point-source target calibrated image by Eq.(7) is shown in Fig. 5(c-d). For theoretical analysis, the normalized synthetic aperture array factor function for an even sampling grid in spatial frequency domain can be described as:

$$
D ( \xi , \eta ) = \frac { \sin [ ( 2 N - 1 ) \pi \Delta u \xi ] } { ( 2 N - 1 ) \sin [ \pi \Delta u \xi ] } \cdot \frac { \sin [ ( 2 M - 1 ) \pi \Delta \nu \eta ] } { ( 2 M - 1 ) \sin [ \pi \Delta \nu \eta ] }
$$

in which $\Delta u$ and $\Delta \nu$ are the minimum antenna spacing normalized to the wave length in the directions of $\xi$ and $\eta$ respectively. $N$ and $M$ are the number of antennas in the directions of $\xi$ and $\eta$ for no sparse array. Angle resolution can be defined as 3dB beamwidth of the synthetic aperture antenna pattern, with reference to the real aperture system, which is derived from Eq. (8):

$$
\theta _ { H P _ { - } \xi } \approx 1 . 2 0 7 \frac { 1 } { ( 2 N - 1 ) \Delta u }
$$

The similar result can be got in the direction of $\eta$

![](images/3ee2898fd05df2df9e0583731a86b12fd4cf88bbab3dc24f8b3cae7203de295f.jpg)  
Fig. 5 point source retrieved imaging (a) raw retrieved image, (b) cross section of raw retrieved image,(c) point source target calibrated image,(d) cross section of

calibrated image

图5点源反演图（a）原始数据反演图像（b）原始反演图像的横剖图（c）点源响应定标后数据的反演图像（d）点源响应定标后反演图像的横剖图

In this SMMW interferometric radiometer, comprised of a sparse mobile array, the equivalent antenna array correspondsto $N = M = 1 3$ and $\Delta u = \Delta \nu = 5$ ： Introducing this parameter to Eq. (8)，we can figure out the theoretical angle resolution is $0 . 5 5 ^ { \circ }$ ，and that ideal first side lobe level approaches -6.5dB. The practical angle resolution is $0 . 5 7 ^ { \circ }$ as shown in Fig.5(c), which has a good agreement with the theoretical results. In the raw retrieved image, first side lobe level is $- 2 . 8 \mathrm { d B }$ as shown in Fig. 5(a). After point-source target calibration, it decreases to $- 5 . 3 \mathrm { d B }$

Experiment results show that point-source target calibration plays a key role in reducing first side lobe，which reflects the system errors of synthetic aperture interferometric radiometer. Unfortunately， there is an obvious gap between the calibrated image and theoretical image, suggesting some considerable errors are still hidden in the point-source target calibrated results,which are yet to be solved in the next step work.

# 4 CONCLUSION

In this paper, a SMMW interferometric radiometer has been set up by means of two-element interferometer and point-source target calibration has been applied to improve the performance of this radiometer. Interferometric fringes and point source images have been presented,and the linear phase error of interference fringes is better than $2 ^ { \circ }$ . The angular resolution of imaging is $0 . 5 7 ^ { \circ }$ . System performance has a good agreement with theoretical results.

This interferometer demonstrates the technical feasibility of synthetic aperture imaging in its application to SMMW spectral region. The result provides important reference for the next stage of GIMS project.

As for future work, the calibration method should be improved to reduce the system errors.Additionally,a modified SMMW interferometric radiometer is now under breadboarding and area target will be imaged in expectation.

# References

[1] A.Maestrini, J. S. Ward, J. J. Gill, H. S. Javadi, E. Schlecht, C. T. Canseliet,A 540-64O-GHz High-Efficiency Four-Anode Frequency Tripler, IEEE Transactions on Microwave Theory and Techniques, vol. 53, no.9, pp.2835-2843, Sep. 2005.   
[2] K. Leong, X. B. Mei, W. Yoshida, M. Lange, A. Zamora, B. Gorospe,“Progress in InP HEMT Submillimeter Wave Circuits and Packaging”, in IEEE Compound Semiconductor Integrated Circuit Symposium, New Orleans,LA, 2015, pp1-4.   
[3] Y. D. Zhang, Y. S. Jiang, Y. T. He, H. Y. Wang, Passive millimeter-wave imaging using photonic processing technology, J. Infrared Millim. Waves, vol. 30, no. 6, Dec. 2011.   
[4] A.Luukanen，T. Kiuru，M. M.Leivo，A. Rautiainen，J. Varis,“Passive three-colour submillimetre-wave video camera", Proc. of SPIE, vol. 8715, 2015.   
[5] Y.Irimajiri, T. Manabe, S. Ochiai, H. Masuko, T. Yamagami, Y. Saito, N. Izutsu, T.Kawasaki， M. Namiki， BSMILES—A Balloon-Borne Superconducting Submillimeter-Wave Limb-Emission Sounder for Stratospheric Measurements, IEEE Geoscience and Remote Sensing Lettrs, vol. 3, no.1, Jan. 2006.   
[6] H.M. Pickett，R.L. Poynter，E.A. Cohen，Submillimeter，millimeter，and microwave spectral line catalog, J. Quant. Spectrosc. Radiat. Transf., vol. 6O, no. 5, pp. 883-890, 1998.   
[7] J.W. Waters,L. Froidevaux，R. S. Harwood, The Earth Observing System Microwave Limb Sounder (EOS MLS) on the Aura satellite, IEEE Trans. Geosci. Remote Sens., vol. 44, no. 5, pp.1075-1092,May. 2006.   
[8] K.Kikuchi， T. Nishibori， S. Ochiai， Overview and early results of the Superconducting Submillimeter-Wave Limb-Emission Sounder (SMILES)，J. Geophys.Res., vol. 115,no.D23, pp.D23306-1-D23306-12, Dec.2010.   
[9] H. Liu, J Wu, S. W. Zhang,“Conceptual design and breadboarding activities of geostationary interferometric microwave sounder (GIMS),” in Proc. IGARSS, Cape Town, South Africa, 2009,pp. 1039-1042.   
[10]C. Zhang, H. Liu, J. Wu, S.W. Zhang, J. Y. Yan, Imaging Analysis and First Results of the Geostationary Interferometric Microwave Sounder Demonstrator, IEEE Trans. Geosci. Remote Sens.,vol. 53, no.1, pp.207-218, Jan. 2015.   
[11] W. G. Read, Z. Shippony, M. J. Schwartz, N. J. Livesey,W. V. Snyder, The Clear-Sky Unpolarized Forward Model for the EOS Aura Microwave Limb Sounder (MLS), IEEE Trans. Geosci. Remote Sens., vol. 44, no.5, pp.1367-1379, May. 2006.   
[12] F. Rodriguez-Morales, K. S. Yngvesson，E. Gerecht,A terahertz focal plane array using HEB superconducting mixers and MMIC IF amplifiers, IEEE Microw. Compon. Lett., vol. 15, no. 4, pp. 199-201,   
[l5]し.S.KuI,C.1．Swit,A.B.Ianner,ana D.M. Le Vine,InterIerometric synthetic aperture microwave radiometry for the remote sensing of the Earth, IEEE Trans. Geosci. Remote Sens., vol. 26, no. 5, pp. 597-611, Sep. 1988.   
[14] M. A. Brown, F. Torres, I. Corbella, and A. Colliander,“ SMOS Calibration,” IEEE Trans. Geosci. Remote Sens., vol. 46, no.3, pp. 646-658,Mar. 2008.   
[15] I. Corbella, F. Torres,A. Camps，A. Colliander， M. M. Neira, S. Ribo，K. Rautiainen,MIRAS End-to-End Calibration: Application to SMOS L1 Processor, IEEE Trans. Geosci. Remote Sens., vol. 43, no. 5,pp.1126-1134,May. 2005.   
[16] A. B. Tanner，W. J. Wilson，B. H. Lambrigsten， Initial results of the geostationary synthetic thinned array radiometer (GeoSTAR） demonstrator instrument, IEEE Trans. Geosci. Remote Sens., vol. 45, no. 7, pp.1947-1957, Jul. 2007.   
[17] J. Meng, D. H. Zhang, C. H. Jiang, C. F. Yao, Research on the practical design method of 225 GHz tripler, J. Infrared Millim. Waves,Vol. 34, no. 2, pp.190-195, Apr. 2015.   
[18] X. Zhao,C.H. Jiang，D.H. Zhang,C. F. Yao,Design of the 45O GHz sub-harmonic mixer based on Schottky diode, J. Infrared Millim. Waves,Vol. 34, no. 3, pp.301-306, Jun. 2015.   
[19]I. Corbella, N. Duffo,M. Vall-llossera, The Visibility Function in Interferometric Aperture Synthesis Radiometry, IEEE Trans. Geosci. Remote Sens., vol. 42, no. 8, pp.1677-1682,Aug. 2004.   
[20] R. Butora, M. M. Neira, A. Luis, R. Antich, Fringe-washing function calibration in aperture synthesis microwave radiometry, RADIO SCIENCE, VOL. 38, NO. 2, 2003.   
[21] A. Camps,J. Bara, I. Corbella,F. Torres，The Processing of Hexagonally Sampled Signals with Standard Rectangular Techniques: Application to 2-D Large Aperture Synthesis Interferometric Radiometers， IEEE Trans. Geosci. Remote Sens., vol. 35, no.1, pp.183-190, Jan.1997.   
[22] C. Zhang, J. Wu,W. Y. Sun,Applications of Pseudo-polar FFT in Synthetic Aperture Radiometer Imaging, PIERS Online, vol. 3, no.1, 2007.   
[23] Q. Z. Wu, C. X. Cai, Y. C. Ding, C. L. Liao, Design and implementation of 5Gsps high-speed data acquisition system, Electronic Design Engineering, vol. 20, no. 1, Jan. 2012.   
[24] M. M. Neira,M. Suess, J.Kainulainen, The Flat Target Transformation, IEEE Trans. Geosci. Remote Sens., vol. 46, no. 3, pp. 613-620, Mar. 2008. areas of sub-millimeter waves applications， system design of synthetic aperture radiometer. E-mail: handonghao1124@163.com.   
Foundation items: Supported by National 863 Program(2013AA122701)，and Scientific Research Fund of Meteorological Public Welfare Profession (GYHY201506023)