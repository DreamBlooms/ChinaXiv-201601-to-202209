# ADAPTIVE REGULARIZATION METHOD FOR FORWARD LOOKING AZIMUTH SUPERRESOLUTION OF A DUAL-FREQUENCY POLARIZED SCATTEROMETER

Liling Liul ² Xiaolong Dong' Jintai Zhu³ Di Zhu'

1. The CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Science,Beijing 100190, China 2. University of Chinese Academy of Science, Beijing 1Ooo49, China 3.DFH Satellite co., Ltd, Beijing, 100094, China

# ABSTRACT

Dual-Frequency Polarized Scatterometer(DFPSCAT） is a pencil-beam rotating scatterometer which is used to measure snow water equivalence (SWE).Respecting the low azimuth resolution of itsforward-lookingregion，an adaptive regularization deconvolution super-resolution method, based on the scatterometer echo signal model，is proposed. Compared with the classical SIR and MAP algorithms, the proposed method can better reconstruct the original signal, and has less noise amplification. The algorithm processing accuracy with different $K _ { \mathrm { p c } }$ is also studied,and the results show that when the value of $K _ { \mathrm { p c } }$ isless than O.1,nearly the entire restored data can satisfy the requirement of O.5dB accuracy.

Index Terms—DFPSCAT,azimuth super-resolution, adaptive regularization method, accuracy

# 1.INTRODUCTION

The radar scatterometer has been widely used in ocean surface wind vector measurement,with surface resolution of tensofkilometers， usually $2 0 { - } 5 0 \mathrm { k m }$ ：Super-resolution techniques have been used to enhance the resolution of radar scatterometric data for some specific applications such as iceberg tracking，where the radiometric precision is not the essentialrequirement.Recently，theWaterCycle Observation Mission (WCOM) is proposed to improve the capability of synergetic observation of key water cycle parameters [1].DFPSCAT is one of three payloads proposed for WCOM along with other two payloads， the Full Polarization Interferometric Radiometer (FPIR） and the Polarimetric Microwave Imager (PMI).DFPSCAT is mainly used to retrieve the SWE by simultaneous measurement of both surface and volume scattering from snow coverage [2, 3].According to requirement of the retrieval,the surface resolution ofnormalized radarbackscattercoefficient (sigmaO） measured by DFPSCAT should be about approximate $2 \mathrm { k m }$ ，and with high radiometric precision. Subjected to restriction of scanning coverage and rotation speed, the beamwidth and antenna dimension of DFPSCAT are about $1 ^ { \circ }$ and $1 . 5 \mathrm { m }$ ,respectively. To achieve the desired spatial resolution，pulse compression is adopted along the elevation direction; while along the azimuth direction, Doppler Beam Sharpening(DBS）can be used at sidelooking region within the swath.

For the forward-looking region, the azimuth resolution is still limited by its antenna beamwidth.Plenty of superresolution methods，including wiener filtering，iterative deconvolution， generalized inverse filtering and MAP methods, have been investigated tosettle this issue. However, these methods have the disadvantage of declining capabilityand low efficiency especially at low SNR. Considering the characteristics of scatterometer signal,a suitable choice is the regularization method.

The paper first establishes DFPSCAT echo signal model, and then details the adaptive regularization method to enhance the azimuth resolution.Two simulations are carried out to evaluate the algorithm performance. The resultsshowthattheproposed method hasbetter performance.

# 2.DFPSCATECHOSIGNALMODEL

DFPSCAT is a pencil-beam rotating scatterometer,whose observation geometry is shown in Fig.1. Assuming the transmit signal is a rectangular pulse signal, the echo signal after pulse compression can be expressed as

$$
y ( R , \varphi ) = C _ { R } \sigma ^ { 0 } ( R , \varphi ) \bigotimes _ { R , \varphi } \left[ h ( R , \varphi ) \delta ( \frac { 2 R } { c } ) \right] \bigotimes _ { R } \left[ \mathrm { s i n c } ( \frac { 2 R } { c } ) \mathrm { e } ^ { j ( \frac { 4 \pi } { \lambda } - \phi ( \frac { 2 R } { c } ) } \right] + n .
$$

where $R$ is the slant range, $\varphi$ is the azimuth angle, $C _ { _ R }$ indicates the radar system constant, $\boldsymbol { \sigma } ^ { 0 }$ is the target backscatter coefficient, $h$ represents antenna pattern, $\lambda$ is the electromagnetic wave length, ${ \mathrm { c } } { = } 3 { \times } 1 0 ^ { 8 } ~ { \mathrm { m / s } }$ ， $\phi$ is phase factor of the transmit signal, $n$ is the receiver thermal noise, $\otimes$ represents convolution.

![](images/9a8b61e3b2e19577e819574b46150c4b3604c7711f61d6b4cca64546fed34f7c.jpg)  
Fig.1 The observation geometry of DFPSCAT

For the same slant range $R { = } R _ { 0 }$ ，Eq.（1）can be simplified as

$$
y ( \varphi ) = \sigma ^ { 0 } ( \varphi ) \otimes h ( \varphi ) + n
$$

For the scatterometer case,the observed data is one section of the above continuous convolution process,which is a partial convolution. The actual sampling operation can be written as

$$
\begin{array} { r } { y = \left[ \begin{array} { l } { y _ { 0 } } \\ { y _ { 1 } } \\ { y _ { 2 } } \\ { \vdots } \\ { y _ { N - 1 } } \end{array} \right] = \left[ \begin{array} { l l l l l l l } { h _ { M - 1 } } & { h _ { M - 2 } } & { \cdots } & { h _ { 0 } } & & & \\ & { h _ { M - 1 } } & & & { \ddots } & & \\ & & & { \ddots } & & & { \ddots } & \\ & & & { \ddots } & & & & { h _ { 0 } } \\ & & & & { h _ { M - 1 } } & { \cdots } & { h _ { 1 } } & { h _ { 0 } } \end{array} \right] \left[ \begin{array} { l } { \sigma _ { - u _ { 1 } } ^ { 0 } } \\ { \vdots } \\ { \sigma _ { - 1 } ^ { 0 } } \\ { \sigma _ { 0 } ^ { 0 } } \\ { \sigma _ { 1 } ^ { 0 } } \\ { \vdots } \\ { \sigma _ { - 1 } ^ { 0 } } \end{array} \right] + n } \end{array}
$$

where $\boldsymbol { y }$ is the vector of samples of the continuous signal $y$ of Eq. (2), $N$ is its total number of samples,and $M$ is the sampling number of $h$

Noted that Eq.(3） does not have definite solution because the number of unknown $\boldsymbol { \sigma } ^ { 0 }$ is greater than the number of equations.To settle the problem,one approach is toutilize a circulant matrix model; the otheristo modify the partial convolution into a complete convolution，namely aperiodic matrix model. These two approaches will achieve similar results as long as $M$ is much smaller than $N$ [4]. To facilitate calculation,we choose the approximate circulant matrix model, i.e.

$$
\begin{array} { r } { y = \left[ \begin{array} { l l l l l l } { h _ { 0 } } & & & & { h _ { M - 1 } } & { \cdots } & { h _ { 1 } } \\ { h _ { 1 } } & { h _ { 0 } } & & & & { \ddots } & { h _ { 2 } } \\ { \vdots } & & { \ddots } & & & & { \vdots } \\ { h _ { M - 1 } } & & & & & & { \vdots } \\ & { \ddots } & & & & & \\ & & { h _ { M - 1 } } & & & & & \\ & & & { \ddots } & & & & \\ & & & { h _ { M - 1 } } & { \cdots } & & & { h _ { 1 } } & { h _ { 0 } } \end{array} \right] \left[ \begin{array} { l } { \sigma _ { 0 } ^ { 0 } } \\ { \sigma _ { 1 } ^ { 0 } } \\ { \sigma _ { 1 } ^ { 0 } } \\ { \sigma _ { 2 } ^ { 0 } } \\ { \vdots } \\ { \sigma _ { n - 1 } ^ { 0 } } \end{array} \right] + n } \end{array}
$$

which can be expressed as a matrix-vector form

$$
\pmb { y } = \pmb { H } \pmb { \sigma } ^ { 0 } + \pmb { n }
$$

where ${ \textbf {  { y } } } , \sigma ^ { \mathrm { { 0 } } }$ and $\pmb { n }$ have the same dimension of $N { \times } 1$ ， $\pmb { H }$ represents a $N { \times } N$ circulant matrix.

# 3.ADAPTIVEREGULARIZATIONMETHOD

# 3.1.Tikhonov regularization method

Due to the ill-poseness of Eq.(5),Tikhonov put forward the regularization method by introducing a regularization operator to make the equation solutions continuously depend on observed data. Tikhonov regularization algorithm is equivalent to minimize the following expression

$$
\arg \operatorname* { m i n } _ { \boldsymbol { \sigma } ^ { 0 } } \biggl [ \left\| \pmb { H } \boldsymbol { \sigma } ^ { 0 } - \pmb { y } \right\| _ { L ^ { 2 } } ^ { 2 } + \alpha \left\| \pmb { \sigma } ^ { 0 } \right\| _ { L ^ { 2 } } ^ { 2 } \biggr ] , \alpha > 0
$$

where $\alpha$ is the regularization parameter which plays a key role to solve the problem. There are two criteria to make an optimal selection of $\alpha$ :prior and posterior criteria.The priori one depends mainly on experience,but it is often infeasible especially for some actual problems.Therefore, Morozov method,a commonly used posteriori criterion,is chosen to determine $\alpha$ ：

Calculating Eq. (6) is equivalent to solve the following linear equation

$$
{ \Big ( } H ^ { T } H + \alpha I { \Big ) } \sigma ^ { 0 } = H ^ { T } y
$$

# 3.2.Adaptive regularization method

The adaptive regularization method was first proposed by Ryzhikov andBiryulina in 1998 to solve inverse problem of linear equations [5].We apply the method to achieve superresolution of the scatterometer in the azimuth direction. With the prerequisite that ${ \pmb { H } } ^ { T } { \pmb { H } }$ is reversible,the specific form of the algorithm is

$$
{ \Big ( } ( H ^ { T } H ) ^ { 2 } + \alpha I { \Big ) } { \pmb { \sigma } } ^ { 0 } = H ^ { T } H H ^ { T } y
$$

Let $\boldsymbol { s } = \boldsymbol { H } ^ { T } \boldsymbol { y } , \eta = \boldsymbol { H } ^ { T } \boldsymbol { H }$ ，then the Eqs. (5), (7)， can be expressed as

$$
\begin{array} { c } { { { \pmb { R \sigma } } ^ { 0 } = s } } \\ { { { \pmb { R } } _ { \alpha } ^ { T } { \pmb { \sigma } } ^ { 0 } = s } } \\ { { { \pmb { R } } _ { \alpha } ^ { A } { \pmb { \sigma } } ^ { 0 } = s } } \end{array}
$$

where R= n, R =n+aI and R△ =η²+aI

Comparing the above formulae,itis not difficult to find that when $\alpha \to 0$ ， $\pmb { R } _ { \alpha } ^ { A }$ and $\pmb { R } _ { \alpha } ^ { T }$ are approximate to $\pmb { R }$ ， while when $\pmb { \eta }$ contains zero eigenvalue, $\pmb { R } \circledast 0 , \pmb { R } _ { \alpha } ^ { A } \to 0$ （204 and ${ \pmb R } _ { \alpha } ^ { T }  \alpha ^ { - 1 }$ .The results show that Eq.(11） can better approximate to the original Eq. (9). Therefore, the optimal approximation solution of the echo model can be obtained by using the adaptive regularization method.

# 4.ALGORITHMPERFORMANCE

To evaluate the algorithmperformance,one-dimensional（1- D） signal reconstruction simulation is first conducted. Furthermore，a quantitative analysis of the processing accuracy of the algorithms is carried out.

In 1-D signal reconstruction simulation, the test signal is a narrow sinc function with a bandlimited spectrum, while the antenna function is a wide rect function whose frequency response attenuated the high frequency components of the signal spectrum,as shown inFig.2.The antenna beamwidth is set as $1 . 0 8 ^ { \circ }$ . The azimuth super resolution region is $\pm 1 0 ^ { \circ }$ off nadir. The test signal is sampled per $0 . 1 4 ^ { \circ }$

where $N ( 0 , 1 )$ is a zero mean unit variance Gaussian random variable, $K _ { \mathrm { p c } }$ represents measurement error.

Figure 3 compares the reconstructed signals and the spectrum without noise.It is obvious that the four algorithms are able to provide good reconstruction of the original signal, as illustrated in Fig.3(a).From Fig.3(b),we note that the SIR and MAP methods cannot recover the lost spectrum information caused by the nulls of antenna pattern spectrum, while both TR and AR algorithms could completely restore the original spectrum.

![](images/72f1561c96fcc2d719a0f232adc26bfe9d50e362b33e21f582bd23486171060f.jpg)  
Fig.3 Algorithm Performance comparison for noiseless measurements (a) Reconstructed signals (b) Spectrum of the reconstructed signals

![](images/55343e23a2fb7460dfd299eaa1324eef80014da176d3fed9c08efe6d5121be6c.jpg)  
Fig.2(a) Test signal and antenna pattern used in the simulation.(b) Schematicillustration(vertical scale is compressed for clarity) of spectrum of the test signal and antenna pattern.

Thereconstructed signal and itscorresponding spectrum are investigated toevaluate the Tikhonov regularization (TR） andAdaptiveregularization(AR) algorithms performance.To further verify the deconvolution methods，they are also compared with classical SIR and MAP algorithms.In addition,both noise-free and noisy measurements are studied in the paper. The noisy measurements satisfy the following relationship

$$
\begin{array} { r } { \mathbf { y } _ { n o i s y } = ( 1 + K _ { \mathrm { p c } } N ( 0 , 1 ) ) \mathbf { y } _ { n o i s e - f r e e } } \end{array}
$$

To evaluate the performance with consideration of noise, Fig.4 demonstrates the output of resolution enhancement methods and their spectrum. $K _ { \mathrm { p c } }$ is set as O.01. There are two significant observations from these results:First,MAP and AR algorithms could reconstruct the original signal with less bias compared with SIR and TR algorithms.Second，the spectrum of AR algorithm has less noise amplification than MAP, SIR and TR.

![](images/57cdb1de692b81ee166b5cb02514e7eed5f280a65d5ddeb562ea28d701749a08.jpg)  
Fig. 4 Algorithm Performance comparison for noisy measurements (a) Reconstructed signals (b) Spectrum of the reconstructed signals

Based on the above 1-D signal reconstruction simulation,a conclusion is drawn that the AR method has bestreconstructionperformanceamongthesefour algorithms. The paper will quantitatively analyze the processing accuracy of these algorithms to verify their validation when conducting SWE retrieval. To satisfy the requirement of SWE retrieval, sigmaO accuracy need to be better than $0 . 5 \mathrm { d B }$ [6].Assuming the actual backscatter coefficient continuously varies with the azimuth super resolution region， we will calculate the percentage of reconstructed sigmaO whose accuracy is better than $0 . 5 \mathrm { d B }$ and take it as an index to evaluate algorithm performance.

Figure 5 shows the algorithm processing accuracy with $K _ { \mathrm { p c } }$ varies from O.05 to O.15. It is noted that the reconstructed sigmaO after AR method processing has higher accuracy than the others for the same $K _ { \mathrm { p c } }$ ，Additionally, compared with SIR,MAP and TR algorithms, the processing accuracy of the AR algorithm degrades more slowly with increased $K _ { \mathrm { p c } }$ .When the value of $K _ { \mathrm { p c } }$ is less than O.1,nearly the entire restored data satisfy the accuracy requirement.

![](images/ac8c9f1567827de7de2b92a27845801bf6561283e64b43083894545b0d846910.jpg)  
Fig. 5 Algorithm processing accuracy with varied $K _ { \mathrm { p c } }$

# 5.CONCLUSION

The paper introduces the regularization method to enhance azimuth resolution and successfully applies it to the DFPSCAT forward looking case.Tikhonov and adaptive regularization methods are described and compared by theoretical analysis,which shows that both of them can be usedin azimuth super resolution ofDFPSCAT,whereas the proposed adaptive regularization method adapts noise better and has better performance.Compared with classical SIR and MAP algorithms,simulation results turn out that the proposed method has higher accuracy,and almost the entire restored data accuracy are better than $0 . 5 \mathrm { d B }$ when $K _ { \mathrm { p c } }$ is less than 0.1.

# 6.REFERENCES

[1] J.C Shi, X.L. Dong, et al, Proposal Report of the Water Cycle Observation Mission (WCOM).National Space Science Center, Chinese Academy of Science,Beijing, China,2013.   
[2]J.C. Shi,X.L.Dong,et al,"WCOM:the science scenario and objective of a global water cycle observation mission,"IGARSS 2014,Quebec City, Canada, pp.3646-3649,2014.   
[3] X.L.Dong,J.C. Shi,et al,"WCOM: the mission concept and payloads of a global water cycle observation mission,"IGARSS 2014,Quebec City, Canada, pp.3338-3341,2014.   
[4] Zou M.Y.，Deconvolution and Signal Recovery，National Defense Industry Press,Beijing,2001.   
[5]WangY.F.,Computationalmethodsforinverseproblemsand their applications,Higher Education Press,Beijing,2007.   
[6] Clissold P.,Coreh2o-cold regions hydrology high resolution observation，ESACommunication ProductOffice, The Netherlands,2008.