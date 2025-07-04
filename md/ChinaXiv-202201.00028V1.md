# Precise calibration of cavity forward and reflected signals using low-level radio-frequency system

Jin-Ying Ma,1Feng Qiu,1,2,十 Long-Bo Shi,1 Zheng-Long Zhu,1 Tian-Cai Jiang,1 Zong-Heng Xue,1Ke-An Jin,1 Qi Chen,1 Cheng-Ye Xu,1 Xing-Hao Ding,² Zheng Gao, Lie-Peng Sun,1,2 Gui-Rong Huang,1,² and Yuan $\mathrm { H e } ^ { 1 , 2 }$ （204号 1Institute of Modern Physics, Chinese Academy of Sciences, Lanzhou 730oo0, China 2School of Nuclear Science and Technology, University of Chinese Academy of Sciences, Beijing 10049,China

Precise measurements of the cavity forward $( V _ { \mathrm { f } } )$ and reflected signals $( V _ { \mathrm { r } } )$ are essential for characterizing other key parameters such as the cavity detuning and forward power. In practice,it is challenging to measure $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ precisely because of crosstalk between the forward and reflected channels (e.g.,coupling between the cavity reflectedand forward signals inadirectional coupler with limited directivity).ForDESY,amethod based on the cavity differential equation was proposed to precisely calibrate the actual $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ . In this study,we verified he validity and practicability of this approach for the Chinese ADS front-end demo superconducting linac (CAFe) facility at the Institute of Modern Physics and a compact energy recovery linac (cERL) test machineatKEK.At the CAFe facility,we successfully calibrated the actual $V _ { \mathrm { f } }$ signal using this method.The result demonstrated that the directivity of directional couplers might seriously affect the accuracy of $V _ { \mathrm { f } }$ measurement. At the cERL facility, we calibrated the Lorentz force detuning (LFD) using the actual $V _ { \mathrm { f } }$ . Our study confirmed that the precise calibration of $V _ { \mathrm { f } }$ significantly improves the accuracy of the cavity LFD measurement.

Keywords:Forward and reflected signals,Measurement, Calibration

# 1.INTRODUCTION

The Chinese ADS front-end demo superconducting linac (CAFe)was constructed at the Institute of Modern Physics to develop the key technologies for a superconducting(SC) front-end linac.It was used to demonstrate the possibility of a $1 0 \mathrm { m A }$ high-power continuous-wave (CW) proton beam for the China Initiative Accelerator-Driven System project [1-3]. The CAFe facility is a 162.5 MHz SC radio frequency (RF) facility operating in CW mode and consists of a normal conducting section and an SC section.As shown in Fig.1,the normal conducting section is composed of an ion source,lowenergy beam transport line (LEBT),RF quadrupole accelerator, and medium-energy beam transport line (MEBT). The SC section is composed of SC accelerating units,which consist of $2 3 { \mathrm { ~ S C ~ } }$ half-wave resonator cavities and are assembled in four cryomodules (CM1 to CM4).

The cavity forward and reflected signals ( $\mathrm { V _ { f } }$ and $V _ { \mathrm { r } }$ ）are typically used to control other key parameters such as the cavity voltage signal $( V _ { \mathrm { c } } )$ , cavity detuning $( \Delta f )$ , and forward power.For example,at the SC test facility (STF) at KEK[4], because there is no pickup antenna in the STF RF gun cavity, $V _ { \mathrm { c } }$ is reconstructed by computing the superposition of $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ 1 $( V _ { \mathrm { c } } = V _ { \mathrm { f } } + V _ { \mathrm { r } } )$ [5].Note that in this paper, $V _ { \mathrm { c } } , \ V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ referto baseband signals,which can be represented by their amplitude and phase (e.g., $V _ { \mathrm { c } } = | V _ { \mathrm { c } } | e ^ { j \angle V _ { \mathrm { c } } } )$ . The cavity pickup signal at the Paul Scherrer Institute Was found to be corrupted by noise [6]. Therefore, $V _ { \mathrm { c } }$ was recalculated using the actual $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ ,and the noise was successfully removed. In addition, $V _ { \mathrm { f } }$ measurement can affect the accuracy of the cavity dynamical detuning. For instance,at the compact energy recovery linac (cERL) test facility at KEK,we compared the cavity Lorentz force detuning (LFD, $\Delta f _ { \mathrm { L F D } } ^ { \ }$ ）calculated using the cavity differential equation with that calibrated using the square of the accelerating gradient. We found that the results of these two methods do not agree at the beginning ofcavity filling.This discrepancy was attributed to the inaccuracy of $V _ { \mathrm { f } }$ measurement,which was caused by the limited directivity of the RF directional coupler [7].

At CAFe,we measured the $V _ { \mathrm { c } } , V _ { \mathrm { f } }$ ，and $V _ { \mathrm { r } }$ signals and the low-level RF (LLRF) output in cavity $\mathrm { C M _ { 3 - 5 } }$ (see Fig. 2). The location of the LLRF output signal is marked in Fig.3. The cavity amplitude loop was operated in closed-loop mode, whereas the phase loop was operated in open-loop mode.As shown in Fig.2, the cavity amplitude error was well compensatedby the feedbackloop.By contrast,because the phase loop was open,the cavity phase fluctuated greatly owing to perturbations such as microphonics and $\Delta f _ { \mathrm { L F D } }$ .Moreover, Fig.2 shows that there is a significant difference between the $V _ { \mathrm { f } }$ phase and LLRF output phase.One possible reason for the phase difference is the nonlinearity of the solid-state amplifier (SSA).Another possible reason involves the inaccurate measurement of $V _ { \mathrm { f } }$ owing to crosstalk between the forward and reflected channels,for example,coupling between the cavity reflected and forward signals in the directional coupler. Later sections of this article demonstrate that the nonlinearity of the SSA is not the primary reason for this phase difference.

Because of crosstalk between the measurement channels, the measured $V _ { \mathrm { f } }$ signal is mixed with the $V _ { \mathrm { r } }$ signal, resultingin inaccurate $V _ { \mathrm { f } }$ measurement.To address this problem, Brandt proposed a method of eliminating the effect of $V _ { \mathrm { r } }$ on the $V _ { \mathrm { f } }$ signal [8]. We calibrated the actual value of $V _ { \mathrm { f } }$ in $\mathrm { C M _ { 3 - 5 } }$ at CAFe and in an SC cavity at KEK-cERL using this method.Themeasurement results confirmed that thismethod is effective.

The remainder of this paper is organized as follows. SectionII briefly describes the CAFe LLRF system.Section III reviews the algorithms used to calibrate the actual values of $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ .In addition, the actual $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ values are estimated with higher precision. SectionIV demonstrates the validity of the method using the experimental results for CAFe

and cERL.Section V presents a discussion of our future work.   
Finally, we summarize our study in Sec. VI.

# I.LLRF SYSTEM

At CAFe, the LLRF data acquisition system is used to measure the amplitude,phase,and frequency and then use various signal processing methods to monitor and control the RF fields.Figure 3 shows a simplified illustration of the layout of thedigitalLLRF systematCAFe.The frequenciesof theRF signals and the intermediate frequency (IF) signal are 162.5 and $2 5 ~ \mathrm { M H z }$ ,respectively. A field-programmable gate array (FPGA) module is used for real-time signal processing and high-speed data acquisition.RF signals such as $V _ { \mathrm { c } } , V _ { \mathrm { f } }$ ,and $V _ { \mathrm { r } }$ are first converted to IF signals.The IF signals are sampled at $1 0 0 ~ \mathrm { { M H z } }$ via a 16-bit analog-to-digital converter (ADC) and are fed to the FPGA.Then,the amplitude and phase of $V _ { \mathrm { c } }$ are extracted from the IF signals. Subsequently, the amplitude and phase signals are compared with their setpoints,and their errors are calculated.These error signals are controlled bya proportional and integral (PI) controller. The controlled amplitude and phase signals are used to rebuild the IF signal. Next, the IF signal is up-converted,and the up-converted signal is used to drive the SSA and ultimately power the cavity. An ARMchip is integrated into the FPGA.An experimental physics and industrial control system(EPICS)is installed on the ARMchip as an embeddedLinux system for data acquisition.The amplitude and phase waveforms of $V _ { \mathrm { c } } , \ V _ { \mathrm { f } }$ ，and $V _ { \mathrm { r } }$ are saved to the hard drive of the CPU controller during measurement,and the measurement data are analyzed offline.

# III. CALIBRATIONOFREALCAVITYFORWARD SIGNAL

To calibrate the real $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ signals (see Fig.2), we review the method of Brandt and present an example for cavity $\mathrm { C M _ { 3 - 5 } }$ at CAFe. $\mathrm { C M _ { 3 - 5 } }$ is mounted in the third cryomodule $\mathrm { ( C M _ { 3 } ) }$ .It is the fifth cavity in $\mathrm { C M _ { 3 } }$ , and the loaded quality factor is $3 . 8 \times 1 0 ^ { 5 }$ , as illustrated in Fig. 1.

Figure 4 shows the $V _ { \mathrm { c } } , V _ { \mathrm { f } }$ ,and $V _ { \mathrm { r } }$ signals measured by the LLRF system during the pulse conditioning of cavity $\mathrm { C M _ { 3 - 5 } }$ According to these results, the cavity signal cannot be obtained by computing the measured signal between the $V _ { \mathrm { f } } ^ { * }$ and $V _ { \mathrm { r } } ^ { * }$ vectors if the two signals are uncalibrated. The actual cavity signal $V _ { \mathrm { c } }$ is a superposition of the actual $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ signals, and it can be reconstructed using the formula [8-10]

$$
V _ { \mathrm { c } } = V _ { \mathrm { f } } + V _ { \mathrm { r } } .
$$

The actual $V _ { \mathrm { f } }$ and $V _ { \mathrm { r } }$ signals can be calibrated using the measured cavity forward and reflected signals according to [5,8]

$$
{ \left[ \begin{array} { l } { V _ { \mathrm { f } } } \\ { V _ { \mathrm { r } } } \end{array} \right] } = { \left[ \begin{array} { l l } { a } & { b } \\ { c } & { d } \end{array} \right] } { \left[ \begin{array} { l } { V _ { \mathrm { f } } ^ { * } } \\ { V _ { \mathrm { r } } ^ { * } } \end{array} \right] } ,
$$

where $V _ { \mathrm { f } } ^ { * }$ and $V _ { \mathrm { r } } ^ { * }$ are the measured values. In this equation, $a , b , c$ ，and $d$ are complex constants related to the actual and measured values.Then,Eq.(1) can be written as

$$
V _ { \mathrm { c } } = X V _ { \mathrm { f } } ^ { * } + Y V _ { \mathrm { r } } ^ { * } ,
$$

where $X = a + c$ and $Y = b + d$ .The complex constants $X$ and $Y$ can be estimated by the multiple linear regression method. The specific calculation methods are as follows.

The complex signals $V , X$ ，and $Y$ can be written as $V =$ $R ( V ) + j I ( V )$ ， $X = C _ { 1 } + j C _ { 2 }$ ,and $Y = C _ { 3 } + j C _ { 4 }$ ,respectively. $R ( V )$ ， $C _ { 1 }$ ，and $C _ { 3 }$ represent the real parts,whereas $I ( V ) , C _ { 2 }$ ,and $C _ { 4 }$ represent the imaginary parts. Then,Eq.(3) can be written as

$$
\begin{array} { r } { R ( V _ { \mathrm { c } } ) + j I ( V _ { \mathrm { c } } ) = ( C _ { 1 } + j C _ { 2 } ) [ R ( V _ { \mathrm { f } } ^ { \ast } ) + j I ( V _ { \mathrm { f } } ^ { \ast } ) ] } \\ { + ( C _ { 3 } + j C _ { 4 } ) [ R ( V _ { \mathrm { r } } ^ { \ast } ) + j I ( V _ { \mathrm { r } } ^ { \ast } ) ] . } \end{array}
$$

For a single pulse with sampled data points $V _ { \mathrm { c } k } , V _ { \mathrm { f } k } ^ { * }$ ，and $V _ { \mathrm { r } k } ^ { \ast }$ ，where $k$ runs from 1 to $n$ ，this method can be used to obtain a linear,overdetermined system of equations.Let $V _ { \mathrm { c } }$ be the response variable; then

$$
\mathbf { y } = \left[ R ( V _ { C 1 } ) \ \cdots \ R ( V _ { C n } ) \ I ( V _ { C 1 } ) \ \cdots \ I ( V _ { C n } ) \right] ^ { \mathrm { T } } .
$$

In addition, let the measured values $V _ { f } ^ { \ast }$ and $V _ { r } ^ { * }$ form the regressormatrix

$$
\mathbf { A } = { \left[ \begin{array} { c c } { R ( V _ { \mathrm { f f } } ^ { * } ) } & { - I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } \\ { R ( V _ { \mathrm { f f } } ^ { * } ) } & { - I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } \\ { \vdots } & { \vdots } & { \vdots } \\ { R ( V _ { \mathrm { f f } } ^ { * } ) } & { - I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } & { - I ( V _ { \mathrm { f f } } ^ { * } ) } \\ { I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } & { I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } \\ { I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } & { I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } \\ { \vdots } & { \vdots } & { \vdots } \\ { I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } & { I ( V _ { \mathrm { f f } } ^ { * } ) } & { R ( V _ { \mathrm { f f } } ^ { * } ) } \end{array} \right] } .
$$

Then the relation

$$
\mathbf { y } = \mathbf { A } \mathbf { C }
$$

is approximately satisfied for some parameter vector

$$
\mathbf { C } = \left[ C _ { 1 } C _ { 2 } C _ { 3 } C _ { 4 } \right] ^ { \mathrm { T } } ,
$$

where $\mathbf { C }$ represents the values of interest.The best estimates of $C _ { 1 } , C _ { 2 } , C _ { 3 }$ ,and $C _ { 4 }$ can be determined using multiple linear regression.The complex constants $X$ and $Y$ can be obtained using these C values.The crosstalk elements $b$ can be taken into account using the information from the RF decay time (after $3 . 5 \mathrm { m s }$ in Fig. 4).During decay, the actual $\mathrm { V _ { f } }$ should be O,and the factors $a$ and $b$ are then limited by another complex factor $Z$ as

$$
Z = a / b = - V _ { \mathrm { r } } ^ { \ast } / V _ { \mathrm { f } } ^ { \ast } ( t > 3 . 5 \mathrm { m s } ) .
$$

Then the complex factors can be expressed in terms of $X$ $Y$ ,and $Z$ according to

$$
\left\{ \begin{array} { l l } { a = a } \\ { b = a / Z } \\ { c = X - a } \\ { d = Y - a / Z . } \end{array} \right.
$$

# ChinaXiv合作期刊

![](images/1ec35c260c7c81d122d5c5ca04f9b548d775363b28c6fce6c5e706cac9fdf4cc.jpg)  
Fig.1.(Color online)LayoutofCAFefacility.The half-wave SCcavities are mounted in four cryomodules (CM1 toCM4).Cavity $\mathrm { C M _ { 3 - 5 } }$ ismarkedbyared triangle

![](images/67ecf5f5df474a2059c845641c4dab57d7f2f6801c39130311b3f89743169ca9.jpg)  
Fig. 2. (Color online) Comparison of amplitude and phase of cavity voltage signal $( V _ { \mathrm { c } } )$ ,cavity forward signal $( V _ { \mathrm { f } } )$ ,cavity reflected signal $( V _ { \mathrm { r } } )$ andLLRFoutputsignal.Thecavityamplitudeloopwasoperatedinclosed-loopmode,whereasthephaselopwas operatedinpen-loop mode.Figure shows that the phase of $V _ { \mathrm { f } }$ differs from that of the LLRF output.

The final unknown complex factor $a$ can be extracted numerically from the cavity differential equation assuming a constant cavity half-bandwidth $\omega _ { 0 . 5 }$ ,which can be estimated in terms of the field decay curve $( t > 3 . 5 \mathrm { m s } )$ ）

The cavity equation can be written in polar coordinates as

$$
\frac { \mathrm { d } | V _ { \mathrm { c } } | } { \mathrm { d } t } + | V _ { \mathrm { c } } | \omega _ { 0 . 5 } = \omega _ { 0 . 5 } \cdot ( 2 | V _ { \mathrm { f } } | ) \mathrm { c o s } ( \theta - \phi ) .
$$

Consequently, the differential of $| \mathrm { V } _ { \mathrm { c } } |$ can be computed using the formula

$$
y ( a , t _ { k } ) = \omega _ { 0 . 5 } \left[ ( 2 | V _ { \mathrm { f } } | ) \mathrm { c o s } ( \theta - \phi ) - | V _ { \mathrm { c } } | \right] ,
$$

where $\theta$ and $\phi$ represent the phases of $V _ { \mathrm { c } }$ and $V _ { \mathrm { f } }$ ,respectively. The variable $y ( a )$ represents the calibrated $\frac { \mathrm { d } | V _ { \mathrm { c } } | } { \mathrm { d } t }$ as a function of the factor $a$ according to Eq. (13). By contrast, $\frac { \mathrm { d } | V _ { \mathrm { c } } | } { \mathrm { d } t }$ can be directly calibrated from the amplitude of $V _ { \mathrm { c } }$ ,which is independent of $a$ . The difference between these two calculations should be minimized by optimizing $a$ . Therefore,we denote the difference as $\lambda ^ { 2 } ( a )$ ：

$$
\lambda ^ { 2 } ( a ) = \sum _ { t _ { k } } \left[ { \frac { \mathrm { d } | V _ { \mathrm { c } } | } { \mathrm { d } t } } - y ( a ) \right] ^ { 2 }
$$

![](images/afc5ac75501beb5ba42f98212c2f8ef18f2964af99ca1a26cb610886f1692aa6.jpg)  
Fig.3.Schematic of digitalLLRF system at CAFe.The location of the LLRF output signal is marked.

![](images/968f9826527d4e29851948f3d2e04483933106c6449f0ce38c2fa223878f95d0.jpg)  
Fig.4.(Coloronline）Measured cavityvoltage,forward,and reflected signals in $\mathrm { C M _ { 3 - 5 } }$ during RF commissioning.

Note that $a$ is a complex number with two components.A two-dimensional map can be obtained by sweeping the real and imaginary components of $a$ ，as shown in Fig. 5. Here, the color axis represents the value of $\lambda ^ { 2 } ( a )$ . The $X$ and $Y$ axes represent the real and imaginary components of $( a / X )$ respectively. The optimal value of $( a / X )$ is clearly $0 . 9 9 \ + \$ $0 . 0 7 i$ . To better illustrate this result,Figs.6 and 7 compare the waveforms of $V _ { \mathrm { f } }$ and $y ( a )$ ,respectively, for $a / X = 1$ and $a / X = 0 . 9 9 + 0 . 0 7 i$ .The difference between dVland y is minimized when the optimal value of $a$ is used.

![](images/9441f859299fd7f829ad7b5e759f09454e4a28f3fd9d8a112470bddd62d66417.jpg)  
Fig.5．(Color online） Scanning result of the parameter $\lambda ^ { 2 }$ .The optimized factor $a / X$ is $0 . 9 9 + 0 . 0 7 i$ . The $X$ and $Y$ axes represent the real and imaginaryparts of $a / X$ ,respectively.

![](images/1b7208f9fde7f61032e582890b40dd0458e79fcafe6db757df9ffd4abbf75b39.jpg)  
Fig.6.(Color online) Comparison of cavity forward voltage $V _ { \mathrm { f } }$ for $a / X = 1$ and $a / X = 0 . 9 9 + 0 . 0 7 i$ .The waveforms of $X V _ { \mathrm { f } } ^ { * }$ and $V _ { \mathrm { c } }$ are also presented for comparison.

# IV. EXPERIMENTALVERIFICATION

To demonstrate the method described in the previous section, the $V _ { \mathrm { f } }$ measurement data were processed and analyzed at the CAFe andcERL facilities.

![](images/32cf9d25bc7bde876c5887f03ca4a1c8fa4e429f10a786b90613b1bdbadecd93.jpg)  
Fig.7.(Color online） Comparison of parameter $y$ for $a / X = 1$ and $a / X = 0 . 9 9 + 0 . 0 7 i$ .The quantity $\frac { \operatorname { d } | V _ { \mathrm { c } } | } { \operatorname { d } t }$ is also plotted as a reference.

# A.Experimental resultatCAFe

During the RF commissioning at CAFe,the LLRF output, SSA output, and $V _ { \mathrm { f } } ^ { * }$ and $V _ { \mathrm { r } } ^ { * }$ signals of $\mathrm { C M _ { 3 - 5 } }$ were downconverted and sent to the ADCs of the LLRF system. The positions of the four signals (points A,B,C,and D,respectively)，are shown in Fig.8. As mentioned in Sect.I, the phase of $V _ { \mathrm { f } } ^ { * }$ differs from the LLRF output phase according to the measurement (see Figs.2 and 9). In theory, the LLRF output phase and $V _ { \mathrm { f } }$ phase should be in agreement,whereas the phases at points A and C differ greatly, according to Fig. 9. As shown in Fig.8,in the ideal case, the phases of the LLRF output (point A) and $V _ { \mathrm { f } }$ (point C) should be in agreement. The discrepancy has two possible causes: the nonlinearity of the SSA and crosstalk between the measurement channels (that is,the unwanted coupling of some components of $V _ { \mathrm { r } }$ with $V _ { \mathrm { f } } ^ { } .$ ).Weanalyze the effects of these two causesas follows.

To eliminate the impact of the nonlinearity of the SSA, we measured the output characteristics of the SSA,as shown in Fig.1O.The amplitude and phase characteristics of the SSA output were measured using a network analyzer. The operating point for Fig.2(and Fig.9) is marked on Fig.1O as $P ( x , y )$ . The amplitude nonlinearity curve can be fitted using the polynomial formula [11]

$$
f _ { \mathrm { A } } ( x ) = h _ { n } x ^ { n } + h _ { n - 1 } x ^ { n - 1 } + \cdot \cdot \cdot + h x + h _ { 0 } .
$$

The phase characteristic curves can be fitted by

$$
f _ { \theta } ( x ) = q _ { m } x ^ { m } + q _ { m - 1 } x ^ { m - 1 } + \cdot \cdot \cdot + q x + q _ { 0 } .
$$

The amplitude $( f _ { \mathrm { A } } ( | V _ { \mathrm { L L R F } } | ) )$ and phase $( f _ { \theta } ( | V _ { \mathrm { L L R F } } | ) )$ of the SSA output can be calibrated using Eqs.(14) and(15),as shown in Fig. 9.

Furthermore, $f _ { \mathrm { A } } ( | V _ { \mathrm { L L R F } } | )$ and $f _ { \theta } ( | V _ { \mathrm { L L R F } } | )$ can also be estimated using the differential near the operating point. If the SSA is linear, its output amplitude increases linearly as the input amplitude increases,and the linear gain is $K = y / x$ . In fact, the output amplitude of the SSA is often nonlinear with respect to the input amplitude;thus,the differential at point $P$ is approximately $G \ : = \ : \Delta y / \Delta x$ ，as illustrated in Fig.9 [11-13]. The amplitude variation of the SSA output signal depends on the value of $G / K$ .For $G / K > 1$ ,the amplitude fluctuation of the LLRF output will be $G / K$ times larger than that of the SSA.By contrast, for $G / K < 1$ ， the amplitude fluctuation of the LLRF output will be $G / K$ times smaller than that of the SSA.We can see from Fig.1O that the value of $G / K$ is approximately 1.8； thus,a $1 \%$ fluctuation in the LLRF output amplitude near the operating point corresponds to a $1 . 8 \%$ fluctuation in the SSA output amplitude. It is easy to see that the ratio of the LLRF output amplitude and $f _ { \mathrm { A } }$ is in good agreement with the value of $G / K$ in Fig. 9. In addition, a $1 \%$ fluctuation in the LLRF output amplitude near the operating point will result in an error of $0 . 0 1 5 ^ { \circ }$ in the SSA output phase,according to the phase curves in Fig.9. Noise from various sources also contributes to the error,which is difficult to determine from the LLRF output phase,as shown in Fig.9. Thus far,we have estimated the amplitude and phase at point B( $f _ { \mathrm { A } }$ and $f _ { \theta . }$ ）successfully.Figure9 shows that $f _ { \mathrm { A } }$ and $f _ { \theta }$ differ greatly in amplitude and phase(especiallyin phase) from $V _ { \mathrm { f } } ^ { * }$ . Thus,we deduce that the nonlinearity of the SSA is not the main reason for the disagreement in phase by comparing the phase curves of $f _ { \theta } { \big ( } | V _ { \mathrm { L L R F } } | { \big ) }$ and $f _ { \mathrm { A } }$

To determine whether the $V _ { \mathrm { r } }$ signal is coupled with the $V _ { \mathrm { f } }$ signal,it is necessary to calculate the actual $V _ { \mathrm { f } }$ value of $\mathrm { C M _ { 3 - 5 } }$ . The values of the complex constants $a$ and $b$ must be known before this calculation can be performed. The exact value of $a$ for $\mathrm { C M _ { 3 - 5 } }$ was obtained by theoretical analysis andderivation in Sect.III.The exactvalue of $b$ can then be calculated using Eq. (9). From the known $a$ and $b$ values, the actual cavity forward signal can be calibrated using the measured signals $V _ { \mathrm { r } } ^ { * }$ and $V _ { \mathrm { f } } ^ { * }$ . Figure 11 shows the actual $V _ { \mathrm { f } }$ signal,measured $V _ { \mathrm { f } }$ signal,and SSA output signal considering the effects of the nonlinearity of the SSA.Panels (a), (b), and(c) represent the measurement results using the same calibration factors (i.e., $a$ and $b$ )but for differentdates.The red lines represent the amplitude and phase of the SSA output signal considering the effectof the nonlinearity of the SSA.The blue lines show the calibrated actual forward signal,which represents $V _ { \mathrm { f 2 } }$ in the figure.The aqua lines represent the measured forward signal,as in the previous section,which repre sents $V _ { \mathrm { f 1 } }$ . Figure 11(a) shows good phase agreement between the blue and red lines.The LLRF output phase is in agreement with the phase of the $V _ { \mathrm { f } }$ signal in theory. This result confirms that the $V _ { \mathrm { r } }$ signal is coupled with the $V _ { \mathrm { f } }$ signal in the signal measurement. It is demonstrated that crosstalk in the measurement channels (e.g.,crosstalk caused by the limited directivity of the directional coupler) is the major reason for the inaccurate measurement of $V _ { \mathrm { f } }$ ,and thus the phase discrepancy.

To further confirm the results of $V _ { \mathrm { f } }$ signal calibration, we used the same calibration array (that is,the same values of

# ChinaXiv合作期刊

![](images/cb257df0375af1fb9e6aa56d73ec5250dd3b1e3bc64dc09c2a3915994242472a.jpg)  
Fig.8.Diagramofsignalmeasurement.PointsAandBrepresenteLRFandAoutputsignals,espectivelyPontsCandeprset the measured values of the cavity forward and reflected signals $( V _ { \mathrm { f } } ^ { * }$ and $V _ { \mathrm { r } } ^ { * }$ ),respectively.

![](images/6bcfcc392974ae0efe31606d8afa83668b5346f9055926baed6abcf5f2cd7a05.jpg)  
Fig.9.(Color online) Amplitude and phase ofLLRF output signal, which corresponds to point AinFig.8(green, $V _ { \mathrm { L L R F } } { \mathrm { . } }$ ),SSAoutput signal considering the effect of SSA nonlinearity,which corresponds to pointB in in Fig.8 (red),and forward signal of measured corresponds to $V _ { \mathrm { f } } ^ { \ast }$ (aqua).When the nonlinearity of the SSAis taken into account, the phases at point B $( f _ { \theta } { \big ( } | V _ { \mathrm { L L R F } } | { \big ) } ) ,$ and point A $( \angle V _ { \mathrm { f } } ^ { * } )$ still differ greatly.

$a , b , c .$ ,and $d$ ）to calibrate the measurement results for other cases.In these cases,the working point of the SSA is the same as the working point in Fig.1O.The blue and red lines show good agreement [see Fig.11(b) and 11(c)] in all cases, indicating that the calibration array has high universality.

# B.Experimental result at KEK-cERL

The cERL facility was constructed at KEK to accommodate industrial applications of SC technology. It is a $1 . 3 \mathrm { G H z }$ SC machine operated in CW mode [14-16]. At cERL,two nine-cell cavities (ML1 and ML2) with high $Q _ { \mathrm { L } }$ values of up to $1 \times 1 0 ^ { 7 }$ were installed in the main linac.

![](images/d4d8ff3c62c1905f8325fc7c74189b424c599478a4c8403c44e4e22300ef417e.jpg)  
Fig.1O.(Color online) Schematic of amplitude and phase characteristics of SSA.The SSA and LLRF output amplitudes are normalized to the saturation point of the SSA.

At cERL,we observed that the LFD calculated using $V _ { \mathrm { f } }$ differs from the theoretical value at the beginning of cavity filling in ML2.The discrepancy was assumed to be related to the inaccuracy of the $V _ { \mathrm { f } }$ measurement due to signal crosstalk between the measurement channels.To verify the correctness of this assumption, the experimental data were re-analyzed. The cavity detuning $( \Delta \omega )$ during the RF pulse without the beam can be estimated using the cavity differential equation

![](images/84eb5482a153dbbae5b790e3cbd3ac3269b99dc6a26edc09dc9f542538539b3d.jpg)  
Fig.11.(Coloronline)Amplitudeand phaseofSSAoutput signalconsideringtheeffects of thenonlinearityofthe SSA (red), $V _ { \mathrm { f 2 } }$ (the actual forward signal,blue), $V _ { \mathrm { f 1 } }$ (the measured forward signal,aqua).Panels (a), (b)and(c)show the measurement results obtained using the same calibration factors $a$ and $b$ but for different dates.These cases show good phase consistency between the blue and red lines.

# [7, 8, 12]

$$
\Delta \omega = \frac { \mathrm { d } \phi } { \mathrm { d } t } - \frac { \omega _ { 0 . 5 } ( | 2 V _ { \mathrm { f } } | ) \mathrm { s i n } ( \theta - \phi ) } { | V _ { \mathrm { c } } | } ,
$$

where $\phi$ and $\theta$ represent the phases of $V _ { \mathrm { c } }$ and $V _ { \mathrm { f } }$ ,respectively. The quantity $\omega _ { 0 . 5 }$ represents the cavity half-bandwidth. The detuning calculated using Eq.(16) includes other sources of detuning in addition to the LFD,although the LFD plays a major role in the overall detuning when the SC cavity is operated in pulse mode.

Moreover,for a given pulse pattern, the LFD can be calibrated using the LFD transfer function model $K ( s )$ [7, 17- 19] as

$$
\Delta \omega _ { \mathrm { L F D } } = - 2 \pi K ( s ) E _ { \mathrm { a c c } } ^ { 2 } ,
$$

where $K ( s )$ is the LFD transfer function,and $\scriptstyle { E _ { \mathrm { a c c } } }$ is the accelerating gradient. The detuning at the beginning of the filling time can be estimated using the above equation [see $\Delta f _ { \mathrm { m o d e l } }$ in Fig. 12(b)].

According to Eq.(16),the amplitude and phase $( | V _ { \mathrm { f } } |$ and $\theta$ ,respectively）of $V _ { \mathrm { f } }$ are required to calculate the cavity detuning $\Delta \omega$ ．When the crosstalk components $b$ and $c$ are not considered, the calibrated cavity forward signal $V _ { \mathrm { f } }$ is equal to $X V _ { \mathrm { f } } ^ { * }$ [Cali1 in Fig.12(a)]. Under this assumption, the detuning $\Delta f _ { \mathrm { C a i l 1 } }$ is calibrated as shownin Fig.12(b).Note that in Fig.12(a), the amplitude of the Calil curve does not decrease to zero immediately when the RF power is switched off.As shown in Fig. 12(b), the waveforms of $\Delta f _ { \mathrm { C a i l 1 } }$ and $\Delta f _ { \mathrm { m o d e l } }$ (red curve) are slightly different at the beginning of the filling time.

Next, the crosstalk coefficients $b$ and $c$ in Eq.(2) are considered,and the coefficients $a , b , c ,$ and $d$ are recalculated using the method described in Sec. III. Then, the actual cavity forward signal $V _ { \mathrm { f } }$ is calibrated by $V _ { \mathrm { f } } = a V _ { \mathrm { f } } ^ { * } + b V _ { \mathrm { r } } ^ { * }$ [Cali2 in Fig.12(a)]. As shown in Fig.12(a), the amplitude of the Cali2 curve decreases to zero immediately when the RF power is turned off. Using the waveform of $V _ { \mathrm { f } }$ in the cali2 curve, the LFD $( \Delta f _ { \mathrm { C a i l 2 } } )$ is obtained,as shown in Fig. 12(b). As expected, the trends of $\Delta f _ { \mathrm { C a i l 2 } }$ and $\Delta f _ { \mathrm { m o d e l } }$ are in good agreement at the beginning of the filling time.

From the analysis above,we conclude that the inaccurate measurement of $V _ { \mathrm { f } }$ can result in the miscalculation of the LFD.In addition,the analysis demonstrates the validity of the method of Brandt.

# V. FUTUREWORK

In the future,after estimating the values of $a , b , c ,$ and $d$ in the offline state,we will implement Eq.(2) in the FPGA. The actual cavity forward signal $V _ { \mathrm { f } }$ and the actual reflected signal $V _ { \mathrm { r } }$ are expected to be calibrated in real time.In the next stage,the calibrated $V _ { \mathrm { f } }$ can be used to calibrate other parameters such as the cavity detuning and beam current.

In addition, the directivity of the directional coupler is related to its input power (the output of the RF source); there fore, the value of $a / X$ may also depend on the location of the nonlinear operating point of the SSA.In the next step,we will attempt to determine the dependence of the parameter $a / X$ on the operation point of the RF source.This research will be based on many measurements and calculations at CAFe at various SSA powers accordingto the research purpose.

![](images/441b15ab1ff5ec9f73cca113ff5a3f7075f5f5feedce0ac0c59dd0e8a8dda628.jpg)  
Fig.12.(Color online)(a) Two methods of calibrating the actual cavity forward signal.Green line,Calil:calibration of $V _ { \mathrm { f } }$ without considering signal crosstalk.Blue line,Cali2:calibration of $V _ { \mathrm { f } }$ considering signal crosstalk.(b) Comparison ofLFD calculated using Eq.(16) without considering signal crosstalk (green),using Eq.(16) considering signal crosstalk (blue),and using Eq.(17) (red).

Finally,this paper assumes that crosstalk exists only between the measured forward and reflected waves.However, RF components could also contribute to the crosstalk signal. We will study these crosstalk relationships further in future work.

# VI.SUMMARY

In this study, the actual $V _ { \mathrm { f } }$ was successfully calibrated using the method proposed by Brandt. We verified the validity of this method for the CAFe and cERL facilities.The study atCAFeindicatedthatinaccurate $V _ { \mathrm { f } }$ measurementis caused mainly by the directivity of the couplers.We confirmed that at cERL,the calibration accuracy of the cavity detuning can be significantly improved by considering the crosstalk components resulting from,for example, the limited directivity of the directional coupler.

# ACKNOWLEDGMENTS

We thank all members of the CAFe and cERL commissioning teams for providing stable beam operation. We also thank all the operation staff for their cooperation and help during the machine study.

# AUTHORCONTRIBUTIONS

All authors contributed to the study conception and de sign.Material preparation,data collection and analysis were performed by Feng Qiu, Jin-Ying Ma and Gui-Rong Huang.The first draft of the manuscript was written by JinYing Ma and all authors commented on previous versions of the manuscript. All authors read and approved the final manuscript.

based calibration method for the llrf systems at KEK STF. inProceedings of the 9th Annual Meeting of ParticleAccelerator Society ofJapan (PASJ2015),Osaka,Japan,2012. Available at https://www.pasj.jp/web_publish/ pasj9/proceedings/PDF/FRLR/FRLR09.pdf   
[6]R.Kalt，Z.Q.Geng，RF and beam stability at SwissFEL，in Oral presentation of the LLRF Workshop 2019, Chicago，USA September 29-October3，2019.Available at https://indico.fnal.gov/event/21836/ contributions/64989/attachments/40775/ 49374/RF_and_beam_stability_at_SwissFEL. pdf   
[7]F.Qiu,T. Miura,D.Arakawa et al.，RF commissioning of the compact energy recovery linac superconducting cavities in pulse mode.Nucl.Instrum.Meth.A.985,164660 (2021). $\mathsf { d o i } : 1 0 . 1 0 1 6 / \mathsf { j }$ .nima.2020.164660   
[8]B.Alexander,Development of a finite state machine for the automated operation of the LLRF control atFLASH.Ph.D.thesis, Universitt Hamburg,2007. [9] M. Grecki, S.Pfeiffer, Resonance control of superconducting cavities at heavy beam loading conditions.in Proceeding of IPAC2012, New Orleans,Louisiana, USA.doi :1O .1103 / PhysRevAccelBeams.21.032003   
[10]F.Qiu,S.Michizono,T. Matsumoto et al.,Real-time cavitysimulator-based low-level radio-frequency test bench and applications for accelerators.Phys.Rev.Accel.Beams 21, 032003 (2018). doi:10.1103/PhysRevAccelBeams. 21.032003   
[11]M.omet, S.Michizono,T.Miura et al.,FPGA-based klystron linearization implementations in scope of ILC.Nucl.Instrum. Meth. A. 768,69-76 (2014). d0i:10.1016/j.nima. 2014.09.007   
[12]F.Qiu,Z.L.Zhu,J,Y.Ma et al.,An approach to characterize Lorentz force transfer function for superconducting cavities.Nucl. Instrum. Meth.A. 1012,165633 (2021).doi: 10.1016/j.nima.2021.165633   
[13] L.P. Sun，Z.Y. Yuan,C. Zhang et al.，New thermal optimization scheme of power module in solid-state amplifier. Nucl. Sci. Tech. 30(4),68 (2019). doi:10.1007/ s41365-019-0585-3   
[14]MAkemoto D.Arakawaet,S.Asaokaal et al.,Construction and commissioning of the compact energy-recovery linac at KEK.Nucl.Instrum.Meth.A. 877,197-219 (2018).doi :   
10.1016/j.nima.2017.08.051 [15] Y.Morikawa,K.Haga,M.Hagiwara et al.,New Industrial ap plication beam-line for the cERL inKEK,in Proceedings of thelOthInternationalParticleAcceleratorConference,Melbourne,Australia,2019.https://doi.org/10.18429/ JACoW-IPAC2019-THPMP012 [16]F.Qiu,T. Miura,D.Arakawa et al.,Application of disturbance observer-based control on pulsed superconducting radio frequency cavities.Phys.Rev. Accel.Beams 24(1),   
012804 (2021). doi:10 .1103/PhysRevAccelBeams.   
24.012804 [17]R.R.Mitchell,K.Y.Matsumoto，G.Ciovati et al.，Lorentz Force Detuning analysis of the spallation neutron source (SNS）accelerating cavities,in 1OthWorkshoponRF Superconductivity,Tsukuba City, Japan,2OO1.Available at ht tp S : //digital.library.unt.edu/ark:/67531/ metadc723708/m2/1/high_res_d/786098.pdf [18]T.Schilcher,Ph.D.thesis,UniversityHamburg,1998. [19] J.Y. Ma,G.R.Huang,Z.Gao et al.,The resonant frequency measurement method for superconducting cavity with Lorentz force detuning.Nucl.Instrum.Meth.A.993(5),165085 (2021). doi:10.1016/j.nima.2021.165085