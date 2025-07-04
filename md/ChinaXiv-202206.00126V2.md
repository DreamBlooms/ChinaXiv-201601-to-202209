# Low-Noise Large-Bandwidth Transimpedance Amplifier for Measuring Scanning Tunneling Shot Noise Spectra in Cryogenic STM and its Applications

Ying-Xin Liang\* Anyang Normal Univ, Sch Phys & Elect Engn, No.436, Xiange Avenue, Anyang 455000,Henan,China

June 11,2022

# Abstract

Shot noise is a powerful tool to study quantum systems. In this work,a design of transimpedance amplifier (TIA) for a cryogenic scanning tunneling microscope (CryoSTM) is proposed to meet the requirements of the shot noise measurements for quantum systems. In the TIA, the preamplfier is made of the low-noise low-power cryogenic high electron mobility transistors.With the high transimpedance gain of 1 $\mathrm { G } \Omega$ ，the bandwidth of the proposed TIA is larger than $3 0 0 ~ \mathrm { k H z }$ .In the CryoSTM, the TIA with the tip-sample component is called as CryoSTM-TIA.The bandwidth of the proposed CryoSTM-TIA is still larger than $3 0 0 ~ \mathrm { k H z }$ . Its equivalent input noise current power spectral density is less than 3O (fA)²/Hz at $1 0 0 ~ \mathrm { k H z }$ .It is detailed, for quantum systems,by using the CryoSTM-TIA, how to measure scanning tunneling current spectra, scanning tunneling differential conductance spectra, and scanning tunneling noise current power spectra, in atomic scale, and then extract their scanning tunneling shot noise spectra. Thus, it is possible to study novel quantum phenomena in various quantum systems by measuring shot noise with the CryoSTM-TIA, such as the Andreev reflection in atomic scale,the Kondo effect in a single molecular magnet, and the existence of Majorana bound states, etc.

# 1Introduction

Shot noise is caused by the discreteness (quantization) of charge carriers and can be observed in non-equilibrium transports. As the non-equilibrium statistics of time-dependent fuctuations, shot noise measurements yield information in mesoscopic systems that is not present in the time-averaged transport characteristics [1]. Shot noise is a powerful tool to study quantum phenomena in mesoscopic systems. The cryogenic STM (CryoSTM) has been used to measure the shot noise in the quantum systems [2, 3,4, 5,6]. Applying DC bias $V$ on the tunnel junction(TJ) between the tip and sample in the CryoSTM, the tunneling current is generated, which contains the tunneling DC current $I$ and tunneling noise current $i$ . For the tunneling noise current $i$ ， its power spectral density (PSD) $S _ { \mathrm { I } }$ is the function of frequency $f$ ： $S _ { \mathrm { I } }$ contains two components: one is the flicker noise, usually （204号 $1 / \mathrm { f }$ noise,whose noise current PSD $S _ { \mathrm { I f } } ( f )$ decreases in the ratio of $1 / f ^ { \alpha }$ ( $0 . 8 < \alpha < 1 . 2$ [7]; the other is the white noise,whose noise current PSD $S _ { \mathrm { { I w } } }$ does not change with $f$ $S _ { \mathrm { I f } } ( f _ { \mathrm { c } } )$ equals $S _ { \mathrm { { I w } } }$ at the frequency $f _ { \mathrm { c } }$ ，where $f _ { \mathrm { c } }$ is called as the corner frequency of $S _ { \mathrm { I } }$ ： $S _ { \mathrm { I } }$ （204号 is also the function of $I$ ， so it is the function of $f$ and $I$ . For the flicker noise, $S _ { \mathrm { I f } } \propto I ^ { \beta }$ ， （204号 $0 . 5 \leq \beta \leq 2$ ,and $\beta$ is different in different systems and conditions [7]. For the white noise, when $| V | \gg k _ { \mathrm { B } } T / e$ ， $S _ { \mathrm { { I w } } }$ performs as the shot noise $S _ { \mathrm { { I s } } }$ in the non-equilibrium transports, and $S _ { \mathrm { { I s } } } ~ = ~ 2 F e | I |$ ，where $F$ is the Fano factor, $k _ { \mathrm { B } }$ is the Boltzmann constant, $e$ is the electron charge,and $T$ is the TJ temperature [1]. $S _ { \mathrm { { I s } } } ( I )$ ，as the function of $I$ ， is called as the scanning tunneling shot noise spectra (STSNS). By using the CryoSTM, to obtain the accurate Fano factor $F$ in a quantum system,we need amplify the white noise current PSD with high gain at high frequencies to avoid the large flicker noise at low frequencies. Measuring $S _ { \mathrm { { I w } } }$ as the function of $I$ at the frequency $f _ { \mathrm { m } }$ much larger than $f _ { \mathrm { c } }$ (usually $f _ { \mathrm { m } } \geq 1 0 f _ { \mathrm { c } }$ ）， $F$ can be obtained as the absolute value of the slope of $S _ { \mathrm { I w } } ( I ) / ( 2 e )$ when $| V | \gg k _ { \mathrm { B } } T / e$ ：

In 2018,a customized voltage amplifier used in the CryoSTM was reported to amplify the tunneling shot noise in the quantum system at a high frequency [2,3]. A low-noise low-power cryogenic high electron mobility transistor developed by CNRS/LPN in France (denoted as CNRS-HEMT)[8, 9] acts as the preamplifier (Pre-Amp), placed in the cryogenic region at $5 ~ \mathrm { K }$ . A resonator with the resonant frequency of 1 MHz is formed by the self-resonance of the superconducting inductor in combination with the cable capacitor between the inner line and the outer one [2]. The tip is connected to the gate of the CNRS-HEMT with the inner line of the cable,and its outer line is connected to ground. Therefore, only the signals at frequencies near the resonant one can be amplified with high voltage gain. By this means, the tunneling shot noise can be measured at 1 MHz by the CryoSTM. The amplifier with the LC-resonator and the tip-sample component described in Ref.[2, 3] is caled as STM-LC-Amp. The STM-LC-Amp has been used to measure the noise around the defects of the high-temperature superconductors (HTCS),and it is found that there are the shot noises with the huge Fano factors. It is believed that the electron correlations at the defects of the HTCS enhance the shot noise [4,5]. The STM-LC-Amp has also been used to measure the shot noise generated by the superconducting Josephson junction, and the Fano factor of 2 is observed in the superconducting energy gap domain, verifying the Andreev reflection in atomic scale [6].

However, there are some disadvantages for the shot noise measurements by using STM-LC-Amp. (1） The high magnetic field cannot be applied, since the $Q$ factor of the superconducting coil inductor is dramatically decreased due to the ruining of the pure superconducting state with perfect diamagnetism. (2) Only the noise current PSD near the resonance frequency can be observed. It is not sure whether the observed noise is white noise or not. (3) The equivalent input noise current PSD of the STM-LC-Amp, as its inherent noise current PSD, is about $\mathrm { 7 0 0 ~ ( f A ) ^ { 2 } / H z }$ [2], approximate to the Poisson shot noise of $I = 2$ nA.It is difficult to measure the shot noise current PSD of the small tunneling current (for example $I < 5 0$ pA）by using the STM-LC-Amp due to its high inherent noise.

In this work,I present a design of transimpedance amplifier (TIA） for the CryoSTM with high gain, large bandwidth,and low inherent noise. In the CryoSTM, the TIA with the tip-sample component is called as CryoSTM-TIA. And, its bandwidth is approximate to that of the TIA. By using the proposed CryoSTM-TIA,it is possible to measure the tunneling noise current PSD as the function of tunneling current $I$ and frequency $f$ with very high accuracy. The accurate white noise (shot noise) can be extracted from the measured tunneling noise current PSD.As using the CryoSTM-TIA, the high magnetic field can be used in the CryoSTM. Therefore, it is possible to measure the shot noise in various quantum systems at the extreme conditions. In recent years, people have attempted to verify the existence of the Majorana bound states (MBSs) in the condensed matters, since it can be used to realize the topological quantum computation [10]. The evidences of the single MBS are announced by detecting the differential conductance peaks at zero energy [11,12]. However,it is very difficult to verify the existence of the MBSs only by the conductance evidences, which often leads to the misjudgments [12]. Whether the MBSs really exist in condensed matters is still controversial. Some theoretical studies show the existence of the MBSs can be accurately told out by the evidences of the conductance results combined with the shot noise results [13,14,15,16,17,18]. Up to now, no attempt is tried to measure the shot noise in the quantum systems in which the MBSs may exist, since it is limited by the noise measurement accuracy. The proposed CryoSTM-TIA is expected to realize the accurate measurements of the above shot noise to tell out the existence of the MBSs.

In Section 2, the basic idea for the design of the proposed CryoSTM-TIA is introduced. In Section 3, the circuit of the CryoSTM-TIA is given. Its circuit stability is proved, and its amplification and transient response performance are demonstrated by the simulations with TINA-TI [19]. In Section 4, the inherent noise of the proposed CryoSTM-TIA is estimated and compared with that of the conventional one. In Section 5, the DC tunneling current measurements by the CryoSTM-TIA are discussed. In Section 6,the applications and outlooks of the CryoSTM-TIA are presented, and its usages in these applications are also detailed, especially for STSNS measurements.

# 2 Basic idea for the design of the proposed CryoSTM-TIA

There are serious disadvantages by using a voltage amplifier for the tunneling current measurements in STM [20]. Usually, the tip-sample tunneling current in the STM is amplified by the TIA [20]. The basic mode of the TIA used in the STM is shown in Fig.1. The dashed triangle represents an operational amplifier (OPA). $R _ { \mathrm { { A } } }$ is the input resistance of the OPA and $C _ { \mathrm { { A } } }$ is its input capacitance. $R _ { \mathrm { F } }$ is the feedback resistor. BMS represents a signal voltage source with the DC bias $V _ { \mathrm { i } }$ and the modulated signal voltage $\dot { V _ { \mathrm { i } } }$ . BMS is in series with the tip-sample TJ,and then connects to the OPA. The TJ differential resistance is $R _ { \mathrm { J } }$ and its capacitance in parallel is $C _ { \mathrm { { J } } }$ ： $C _ { \mathrm { I } }$ is the capacitance of the cable with which the tip is connected to the input of the TIA. Due to the virtual short efect of the OPA, the voltage $V _ { \mathrm { i } } + \dot { V _ { \mathrm { i } } }$ drops on TJ, generating the tunneling current,and the current is amplified to the output voltage $V _ { \mathrm { o } } + \dot { V } _ { \mathrm { o } }$ at the output terminal O.Transimpedance gain, bandwidth,and inherent noise are the most important characters for the CryoSTMTIA. For the DC and low frequency tunneling current, the transimpedance gain of the CryoSTM-TIA is approximately equal to $R _ { \mathrm { F } }$ . Excluding the tunneling noise current PSD, the inherent noise of the CryoSTM-TIA can be described by a virtual noise current source in parallel with TJ,whose noise current PSD is called the equivalent input noise current

![](images/6e1ec0bd5b4c38536c6df6b03d6003a374e7beecb656719cc2ce0c3d08f53ba9.jpg)  
Figure 1: Basic model of the CryoSTM-TIA. The TIA is shown in the dashed box. The dashed triangle is a OPA with the open loop voltage gain $a _ { \mathrm { A } }$ ， $R _ { \mathrm { { A } } }$ is its input resistance, and $C _ { \mathrm { { A } } }$ is its input capacitance. $R _ { \mathrm { F } }$ is the feedback resistor.TJ is the tip-sample tunnel junction with the differential resistance $R _ { \mathrm { J } }$ and capacitance $C _ { \mathrm { { J } } }$ . BMS is a signal voltage source with the DC bias $V _ { \mathrm { i } }$ and the modulated signal voltage $\dot { V _ { \mathrm { i } } }$ ，generating the output voltage with the DC output $V _ { \mathrm { o } }$ and the AC output $\dot { V } _ { \mathrm { o } }$

PSD of the CryoSTM-TIA, denoted as $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ or $\overline { { i _ { \mathrm { i n } } ^ { 2 } } } ( f )$ ： $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ can be easily compared with the signal current flowing through TJ, such as the tunneling shot noise current PSD.

For the conventional CryoSTM-TIA, its TIA is typically represented by DE-DLPCA200 (FEMTO)[21], which is only able to work at room temperatures,while the tip-sample TJ is placed in the cryogenic region. As the transimpedance gain of DE-DLPCA-200 is 1 $\mathrm { G } \Omega$ ,its bandwidth is only $1 . 1 \ \mathrm { k H z }$ . And, $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ of the conventional CryoSTM-TIA is about 4 $\mathrm { 1 1 ~ ( f A ) ^ { 2 } / H z }$ at $1 \ \mathrm { k H z }$ ，as listed in Table 6. The following goals should be achieved for the proposed CryoSTM-TIA. (1) The tip-sample TJ can be placed in the cryogenic region below 4.2 K.(2) The transimpedance gain is up to 1 GΩ. (3) The bandwidth is above 300 $\mathrm { k H z }$ (4) $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ is less than 3 (fA)²/Hz at $1 0 ~ \mathrm { k H z }$ , and less than 30 $\mathrm { ) \ ( f A ) ^ { 2 } / H z }$ at $1 0 0 ~ \mathrm { k H z }$ . Such performances are able to meet the requirements in accuracy of the STSNS measurements for various quantum systems.

# 2.1 Noise model of CryoSTM-TIA

The equivalent input noise voltage of the OPA is denoted as eA and its equivalent input noise current is $i _ { \mathrm { A } }$ .By Wiener-Khintchine theorem, $\left( \begin{array} { c c } { { \overline { { { e _ { \mathrm { A } } ^ { 2 } } } } } } & { { \overline { { { e _ { \mathrm { A } } i _ { \mathrm { A } } ^ { * } } } } } } \\ { { \overline { { { i _ { \mathrm { A } } e _ { \mathrm { A } } ^ { * } } } } } } & { { \overline { { { i _ { \mathrm { A } } ^ { 2 } } } } } } \end{array} \right)$ can be obtained [7,22, 23]. The two matrix elements on the main diagonal are the equivalent input noise voltage PSD of the OPA and its equivalent input noise current PSD. The two matrix elements on the sub-diagonal are its equivalent input noise voltage-current PSD and equivalent input noise current-voltage PSD.

The equivalent input noise voltage of the TIA is denoted as $e _ { \mathrm { T } }$ and its equivalent input noise current is $i _ { \mathrm { T } }$ . The noise current of the feedback resistor $R _ { \mathrm { F } }$ is denoted as $i _ { \mathrm { F } }$ .The temperature of $R _ { \mathrm { F } }$ is $T$ , and its noise current PSD is $\overline { { i _ { \mathrm { F } } ^ { 2 } } } = 4 k _ { \mathrm { B } } T / R _ { \mathrm { F } }$ . By the nodal analysis method and Wiener-Khintchine theorem [22, 23], $\left( \begin{array} { c c } { \overline { { { e _ { \mathrm { T } } ^ { 2 } } } } } & { \overline { { { e _ { \mathrm { T } } i _ { \mathrm { T } } ^ { * } } } } } \\ { \overline { { { i _ { \mathrm { T } } e _ { \mathrm { T } } ^ { * } } } } } & { \overline { { { i _ { \mathrm { T } } ^ { 2 } } } } } \end{array} \right)$ can be obtained (see

Supplemental file 1 [24]). The two matrix elements on the main diagonal are the equivalent input noise voltage PSD of the TIA and its equivalent input noise current PSD. The two matrix elements on the sub-diagonal are its equivalent input noise voltage-current PSD and equivalent input noise current-voltage PSD. $e _ { \mathrm { T } } ^ { 2 }$ ， $i _ { \mathrm { T } } ^ { 2 }$ ， $\overline { { e _ { \mathrm { T } } i _ { \mathrm { T } } ^ { * } } }$ ,and $\overline { { i _ { \mathrm { T } } e _ { \mathrm { T } } ^ { * } } }$ can be expressed as

$$
\overline { { e _ { \mathrm { T } } ^ { 2 } } } = \overline { { e _ { \mathrm { A } } ^ { 2 } } } ,
$$

$$
\overline { { i _ { \mathrm { T } } ^ { 2 } } } = \overline { { i _ { \mathrm { A } } ^ { 2 } } } + \overline { { e _ { \mathrm { A } } ^ { 2 } } } / R _ { \mathrm { F } } ^ { 2 } + 4 k _ { \mathrm { B } } T / R _ { \mathrm { F } } ,
$$

$$
\overline { { e _ { \mathrm { T } } i _ { \mathrm { T } } ^ { * } } } = ( \overline { { i _ { \mathrm { T } } e _ { \mathrm { T } } ^ { * } } } ) ^ { * } = \overline { { e _ { \mathrm { A } } i _ { \mathrm { A } } ^ { * } } } + \overline { { e _ { \mathrm { A } } ^ { 2 } } } / { R _ { \mathrm { F } } } .
$$

The equivalent input noise current PSD of the CryoSTM-TIA $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ can be obtained [7, 22, 23] by

$$
\overline { { i _ { \mathrm { i n } } ^ { 2 } } } = \overline { { i _ { \mathrm { T } } ^ { 2 } } } + ( \frac { 1 } { R _ { \mathrm { J } } ^ { 2 } } + ( 2 \pi f ) ^ { 2 } C _ { \mathrm { I J } } ^ { 2 } ) \overline { { e _ { \mathrm { T } } ^ { 2 } } } + ( \frac { 1 } { R _ { \mathrm { J } } } + j 2 \pi f C _ { \mathrm { I J } } ) \overline { { e _ { \mathrm { T } } i _ { \mathrm { T } } ^ { \ast } } } + ( \frac { 1 } { R _ { \mathrm { J } } } - j 2 \pi f C _ { \mathrm { I J } } ) \overline { { i _ { \mathrm { T } } e _ { \mathrm { T } } ^ { \ast } } } .
$$

In this work, $C _ { \mathrm { I J } } = C _ { \mathrm { I } } + C _ { \mathrm { J } }$ . Putting Eq.(2.1), (2.2),and (2.3) into Eq.(2.4),

$$
\begin{array} { r l } & { \overline { { i _ { \mathrm { i n } } ^ { 2 } } } = \overline { { i _ { \mathrm { A } } ^ { 2 } } } + \frac { 4 k _ { \mathrm { B } } T } { R _ { \mathrm { F } } } + [ \frac { 1 } { R _ { \mathrm { J } } ^ { 2 } } + \frac { 1 } { R _ { \mathrm { F } } ^ { 2 } } + ( 2 \pi f ) ^ { 2 } C _ { \mathrm { I J } } ^ { 2 } ] \overline { { e _ { \mathrm { A } } ^ { 2 } } } } \\ & { \quad + ( \frac { 1 } { R _ { \mathrm { J } } } + j 2 \pi f C _ { \mathrm { I J } } ) ( \overline { { e _ { \mathrm { A } } i _ { \mathrm { A } } ^ { * } } } + \frac { \overline { { e _ { \mathrm { A } } ^ { 2 } } } } { R _ { \mathrm { F } } } ) + ( \frac { 1 } { R _ { \mathrm { J } } } - j 2 \pi f C _ { \mathrm { I J } } ) ( \overline { { i _ { \mathrm { A } } e _ { \mathrm { A } } ^ { * } } } + \frac { \overline { { e _ { \mathrm { A } } ^ { 2 } } } } { R _ { \mathrm { F } } } ) , } \end{array}
$$

The means to reduce the inherent noise of the CryoSTM-TIA can be found in Eq.(2.5), such as reducing $\overline { { e _ { \mathrm { A } } ^ { 2 } } }$ , reducing $C _ { \mathrm { I } }$ , increasing $R _ { \mathrm { F } }$ , reducing $T$ ，etc.

# 2.2 Selection of transistors in Pre-Amp

In the conventional CryoSTM-TIA with DE-DLPCA-200 as the TIA, its input capacitance $C _ { \mathrm { { A } } }$ is about $5 ~ \mathrm { p F }$ ，and the TJ capacitance $C _ { \mathrm { { J } } }$ is estimated as several fF [2, 25]. TJ is connected to the TIA with a long cable of $1 . 5 \ \mathrm { m } { \sim } 2 \ \mathrm { m }$ ，whose capacitance $C _ { \mathrm { { I } } }$ is about 100 pF. $C _ { \mathrm { I } }$ converts the equivalent input noise voltage PSD of the TIA $e _ { \mathrm { T } } ^ { 2 }$ to a great component of $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ of the CryoSTM-TIA. The component of $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ related to $C _ { \mathrm { I } }$ is $i _ { \mathrm { C I } } ^ { 2 } \approx ( 2 \pi f ) ^ { 2 } C _ { \mathrm { I } } ^ { 2 } e _ { \mathrm { A } } ^ { 2 }$ ，where $\overline { { e _ { \mathrm { A } } ^ { 2 } } } = \overline { { e _ { \mathrm { T } } ^ { 2 } } }$ and $\overline { { e _ { \mathrm { T } } ^ { 2 } } } = 1 6 ~ ( \mathrm { n V ) ^ { 2 } / H z }$ [21]. $\overline { { i _ { \mathrm { C I } } ^ { 2 } } }$ is only about $6 . 3 ~ \mathrm { ( f A ) ^ { 2 } / H z }$ at $1 \ \mathrm { k H z }$ .However, it is about 6 $\mathrm { 3 0 ~ ( f A ) ^ { 2 } / H z }$ at $1 0 ~ \mathrm { k H z }$ , becoming the main component of $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ . Hence, Ref.[20] emphasizes that the length of the cable between the tip and the input of the TIA should be shortened as far as possible to reduce $C _ { \mathrm { I } }$ ，which requires the transistors in the PreAmp of the OPA to be placed in the cryogenic region [26, 27, 28]. A CryoSTM-TIA design has been proposed in Ref.[26],in which a differential amplifier as the Pre-Amp is made of JFETs. The minimum temperature at which JFETs can work normally is 50 K. If TJ is in the cryogenic region below $4 . 2 ~ \mathrm { K }$ , the cable is still long and $C _ { \mathrm { I } }$ is still large. Ref.[28] describes several methods to reduce the inherent noise of the CryoSTM-TIA,and one is shortening the cable between the tip and the input of the TIA. The advantages and disadvantages of four kinds of cryogenic transistors used in the CryoSTM-TIA are also discussed. A specific design of the CryoSTM-TIA with the bandwidth of $4 ~ \mathrm { k H z }$ is proposed, and its equivalent input noise current PSD $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ is about 100 (fA) $^ 2$ /Hz at $4 ~ \mathrm { k H z }$ ：

In the design of the proposed CryoSTM-TIA, the OPA consists of a Pre-Amp and a post-amplifier (Post-Amp), which is called as Macro-OPA.The CNRS-HEMTs are selected as the transistors in the pre-Amp [8, 9]. The CNRS-HEMT is capable of operating below 0.5 K,and its power at the ideal_operating point is only 0.1 mW. The CNRS-HEMT parameters are listed in Table 1. $e _ { \mathrm { H } } ^ { 2 }$ is its equivalent input noise voltage PSD,and $\overline { { i _ { \mathrm { H } } ^ { 2 } } }$ is its equivalent input noise current PSD.

Table 1:Parameters of CNRS-HEMT   

<html><body><table><tr><td>gate-source resistance RA transconductance 9m channel condactance gd</td><td>> 10 TΩ 40 mS 1 mS</td></tr><tr><td>gate-source capacitance Cgs gate-drain capacitance Cgd drain-source voltage Vds drain-source current Ids</td><td>5pF 1pF 100 mV 1 mA</td></tr><tr><td>(nV）2/Hz</td><td>10 kHz 0.25</td></tr><tr><td></td><td></td></tr><tr><td>（fA)²/Hz 10 kHz</td><td>0.1</td></tr></table></body></html>

Even if TJ is placed in the cryogenic region below $0 . 5 ~ \mathrm { K }$ , the CNRS-HEMTs can still be placed close to TJ due to their low power. Thus, $C _ { \mathrm { I } }$ can be reduced to below O.5 pF. As the result, the inherent noise of the CryoSTM-TIA is greatly reduced, even at high frequencies.

However, there are many diffculties in constructing the Pre-Amp with the CNRSHEMTs. For example, since the drain-source voltage for the ideal operating point of the CNRS-HEMT is only 10O mV, the voltage fluctuations of the circuit affct its normal operation seriously, and the voltage surges may destroy it. The design of the Pre-Amp, aiming to resolve these diffculties,is detailed in Section 3.1.

# 2.3 Frequency compensation in feedback loop

![](images/df246f93d87ff6b64d75d61d89a8bb88c8690f5279a5fd2e1c72591d1d02dcb3.jpg)  
Figure 2: Circuit diagram of the compensated feedback network [20, 26]

For the high feedback resistor $R _ { \mathrm { F } }$ ， its parasitic capacitance $C _ { \mathrm { F } }$ cannot be ignored at high frequencies. In order to increase the bandwidth of the CryoSTM-TIA with high $R _ { \mathrm { F } }$ ， frequency compensation must be used in the feedback loop. A very simple compensated

feedback network is proposed in Ref.[20, 26]. As shown in Fig.2, taking $C _ { \mathrm { c } }$ equal to $k C _ { \mathrm { F } }$ where $k$ is above $1 0 ^ { 3 }$ ， adjust $R _ { \mathrm { k } }$ equal to $R _ { \mathrm { F } } / k$ ， realizing $R _ { \mathrm { k } } C _ { \mathrm { c } } = R _ { \mathrm { F } } C _ { \mathrm { F } }$ . The output voltage of the OPA as $\dot { V } _ { \mathrm { o } }$ generates the current $\dot { I } _ { \mathrm { F } }$ flowing to the OPA input N, so

$$
Z _ { \mathrm { { F } } } ( f ) = { \frac { \dot { V } _ { \mathrm { o } } } { { \dot { I } } _ { \mathrm { { F } } } } } \approx { \frac { R _ { \mathrm { { k } } } + R _ { \mathrm { { F } } } } { 1 + j 2 \pi f R _ { \mathrm { { k } } } C _ { \mathrm { { k } } } } } \approx { \frac { R _ { \mathrm { { F } } } } { 1 + j 2 \pi f R _ { \mathrm { { k } } } C _ { \mathrm { { k } } } } } ,
$$

where $C _ { \mathrm { k } }$ is the parasitic capacitance of $R _ { \mathrm { k } }$ [26]. $Z _ { \mathrm { F } } ( f ) = \dot { V } _ { \mathrm { o } } / \dot { I } _ { \mathrm { F } }$ can be considered as the impedance of the feedback network. $f _ { \mathrm { F } } = 1 / ( 2 \pi R _ { \mathrm { k } } C _ { \mathrm { k } } )$ is called as the cut-off frequency of the compensated feedback network. The experimental results in Ref.[26] show that the feedback network is achieved to broaden the bandwidth to MHz.

In my design, $R _ { \mathrm { F } }$ is $1 \ G \Omega$ ， $C _ { \mathrm { F } }$ is about $0 . 3 \mathrm { p F }$ ， $R _ { \mathrm { k } }$ is about $1 0 0 ~ \mathrm { k } \Omega$ ，and $C _ { \mathrm { k } }$ is about 0.2 $\mathrm { p F }$ ，s0 $f _ { \mathrm { F } } = 1 / ( 2 \pi R _ { \mathrm { k } } C _ { \mathrm { k } } )$ is about 8 MHz. In $( 0 , 1 \ \mathrm { M H z } ]$ ， $| Z _ { \mathrm { F } } ( f ) | \approx R _ { \mathrm { F } } / | 1 + j 2 \pi f R _ { \mathrm { k } } C _ { \mathrm { k } } | >$ （204号 $R _ { \mathrm { F } } / 1 . 0 0 8$ and $| Z _ { \mathrm { F } } ( f ) | ~ \le ~ R _ { \mathrm { F } }$ ，so it can be considered that $Z _ { \mathrm { F } } ( f )$ is equal to $R _ { \mathrm { F } }$ in （204号 $( 0 , 1 \ \mathrm { M H z } ]$ ：

# 2.4Idea for realizing circuit stability of the proposed CryoSTM-TIA

To realize the large bandwidth of the proposed CryoSTM-TIA, the principles for the design of the conventional CryoSTM-TIA to realize circuit stability [21, 29] is inapplicable. In the following, a simple principle for the proposed CryoSTM-TIA to realize circuit stability is given.

In the proposed CryoSTM-TIA,for simplicity, it is assumed that there is no parasitic capacitance in parallel with $R _ { \mathrm { F } }$ and the TJ differential resistance $R _ { \mathrm { J } }$ varies from $1 0 ^ { - 3 } R _ { \mathrm { F } }$ （204号 to infinity. $a _ { \mathrm { A } } ( f )$ is the open loop voltage gain of the Macro-OPA. It is assumed that the modulus $\left| a _ { \mathrm { A } } ( f ) \right|$ and the argument $\angle ( a _ { \mathrm { A } } ( f ) )$ both decrease with the increase of $f$ [29]. A frequency $f _ { - 6 0 }$ can be found for $\angle ( a _ { \mathrm { A } } ( f _ { - 6 0 } ) ) = - 6 0 ^ { \circ }$ . In this work, $C _ { \mathrm { A I } } = C _ { \mathrm { A } } + C _ { \mathrm { I } }$ ， （204号 $C = C _ { \mathrm { A } } + C _ { \mathrm { I } } + C _ { \mathrm { J } } = C _ { \mathrm { A I } } + C _ { \mathrm { J } }$ ， $a _ { 1 } = | a _ { \mathrm { A } } ( f _ { - 6 0 } ) |$ ，and $f _ { \mathrm { y } } ~ { = } ~ 2 a _ { 1 } / ( 2 \pi R _ { \mathrm { F } } C )$ .As long as $f _ { \mathrm { y } } ~ < ~ f _ { - 6 0 }$ is realized by selecting proper $R _ { \mathrm { F } }$ ， $C$ and $a _ { 1 }$ ，the circuit stability of the CryoSTM-TIA is guaranteed, and the gain margin of the circuit stability is at least 6 dB and the phase margin is at least $3 0 ^ { \circ }$ . This conclusion will be proved in the following paragraphs. For an intuitive understanding of this proof, refer to the graphical method shown in Fig.4 in Section 3.3.

The loop gain $T _ { \mathrm { { L } } }$ of the CryoSTM-TIA [29] is

$$
T _ { \mathrm { L } } ( f ) = a _ { \mathrm { A } } ( f ) \beta ( f ) = a _ { \mathrm { A } } ( f ) / [ 1 / \beta ( f ) ] ,
$$

in which $\beta ( f )$ is the feedback factor,and its reciprocal is,

$$
1 / \beta ( f ) = 1 + R _ { \mathrm { F } } ( 1 / R _ { \mathrm { J } } + 1 / R _ { \mathrm { A } } + j 2 \pi f C ) .
$$

In $( 0 , f _ { - 6 0 } ]$ ，since $| 1 / \beta ( f ) |$ increases monotonically and $f _ { \mathrm { y } } < f _ { - 6 0 }$

$$
\begin{array} { r } { | 1 / \beta ( f _ { - 6 0 } ) | \ge | 1 / \beta ( f _ { \mathrm { y } } ) | = | 1 + R _ { \mathrm { F } } ( 1 / R _ { \mathrm { J } } + 1 / R _ { \mathrm { A } } + j 2 \pi f _ { \mathrm { y } } C ) | > 2 \pi f _ { \mathrm { y } } R _ { \mathrm { F } } C = 2 a _ { 1 } . } \end{array}
$$

Hence,

$$
| T _ { \mathrm { L } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } = | a _ { \mathrm { A } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } - | 1 / \beta ( f _ { - 6 0 } ) | _ { \mathrm { d B } } < ( a _ { 1 } ) _ { \mathrm { d B } } - ( 2 a _ { 1 } ) _ { \mathrm { d B } } = - 6 ~ \mathrm { d B } .
$$

In $[ f _ { - 6 0 } , + \infty )$ , considering $| 1 / \beta ( f ) | \ge | 1 / \beta ( f _ { - 6 0 } ) |$

$$
\begin{array} { r l } & { | T _ { \mathrm { L } } ( f ) | _ { \mathrm { d B } } = | a _ { \mathrm { A } } ( f ) | _ { \mathrm { d B } } - | 1 / \beta ( f ) | _ { \mathrm { d B } } } \\ & { \qquad \leq | a _ { \mathrm { A } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } - | 1 / \beta ( f _ { - 6 0 } ) | _ { \mathrm { d B } } = | T _ { \mathrm { L } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } < - 6 ~ \mathrm { d B } . } \end{array}
$$

On the other hand,in $( 0 , f _ { - 6 0 } ]$ ， $\angle ( a _ { \mathrm { A } } ( f ) ) \geq - 6 0 ^ { \circ }$ and $\angle ( 1 / \beta ( f ) ) < 9 0 ^ { \circ }$ ，S0

$$
\angle ( T _ { \mathrm { L } } ( f ) ) = \angle ( a _ { \mathrm { A } } ( f ) ) - \angle ( 1 / \beta ( f ) ) > - 6 0 ^ { \circ } - 9 0 ^ { \circ } = - 1 5 0 ^ { \circ } .
$$

According to Eq.(2.8) and (2.9), $\vert T _ { \mathrm { L } } ( f ) \vert _ { \mathrm { d B } } < - 6 ~ \mathrm { d B }$ in $[ f _ { - 6 0 } , + \infty )$ and $\angle ( T _ { \mathrm { L } } ( f ) ) >$ $- 1 5 0 ^ { \circ }$ in $( 0 , f _ { - 6 0 } ]$ , so the proposed CryoSTM-TIA is stable, and the gain margin is higher than 6 dB and the phase margin is higher than $3 0 ^ { \circ }$ ：

Considering a parasitic capacitor $C _ { \mathrm { F } }$ parallel to the feedback resistor $R _ { \mathrm { F } }$ ,the feedback loop can be compensated by the means described in Section 2.3,so Eq.(2.7) here should be changed to

$$
1 / \beta ( f ) = 1 + Z _ { \mathrm { F } } [ 1 / R _ { \mathrm { J } } + 1 / R _ { \mathrm { A } } + j 2 \pi f C ] ,
$$

where $Z _ { \mathrm { F } } = R _ { \mathrm { F } } / ( 1 + j 2 \pi f R _ { \mathrm { k } } C _ { \mathrm { k } } )$ . For the design of the Macro-OPA in the proposed CryoSTM-TIA, it is easily to realize $f _ { - 6 0 }$ is in $[ 5 0 0 ~ \mathrm { k H z } , 1 ~ \mathrm { M H z } ]$ . As mentioned ino Section 2.3, $C _ { \mathrm { k } }$ is approximately to $0 . 2 ~ \mathrm { p F }$ for $R _ { \mathrm { k } }$ of $1 0 0 ~ \mathrm { k } \Omega$ ，s0 $Z _ { \mathrm { F } }$ is almost equal to $R _ { \mathrm { F } }$ in $( 0 , 1 \ \mathrm { M H z } ]$ . Because $R _ { \mathrm { F } } C$ is at least 4 orders of magnitude greater than $R _ { \mathrm { k } } C _ { \mathrm { k } }$ ， $| 1 / \beta ( f ) | \geq$ $| 1 / \beta ( f _ { - 6 0 } ) |$ in $[ f _ { - 6 0 } , + \infty )$ ，and $\angle ( 1 / \beta ( f ) ) < 9 0 ^ { \circ }$ . Hence,the above proof for the circuit stability is still valid.

# 2.5 Voltage gain and transimpedance gain of CryoSTM-TIA

With the frequency compensation as mentioned in Section 2.3, it can be considered that $Z _ { \mathrm { F } }$ is equal to $R _ { \mathrm { F } }$ in $( 0 , 1 \ \mathrm { M H z } ]$ . Considering the TJ capacitance $C _ { \mathrm { { J } } }$ , the TJ impedance should be $Z _ { \mathrm { J } } = R _ { \mathrm { J } } / ( 1 + j 2 \pi f R _ { \mathrm { J } } C _ { \mathrm { J } } )$ .In this work, $C _ { \mathrm { { J } } }$ is at least two orders of magnitude less than $C _ { \mathrm { A I } }$ , so it can be ignored in $C$ and $C \approx C _ { \mathrm { A I } }$ . The voltage gain of the CryoSTM-TIA is $A _ { \mathrm { v } } = \dot { V } _ { \mathrm { o } } / \dot { V } _ { \mathrm { i } }$ .In $( 0 , 1 \ \mathrm { M H z } ]$ ， $A _ { \mathrm { v } }$ is

$$
A _ { \mathrm { v } } \approx - { \frac { R _ { \mathrm { F } } } { Z _ { \mathrm { J } } } } \cdot { \frac { 1 } { 1 + { \frac { 1 } { a _ { \mathrm { A } } } } + { \frac { R _ { \mathrm { F } } } { a _ { \mathrm { A } } R _ { \mathrm { J } } } } + { \frac { R _ { \mathrm { F } } } { a _ { \mathrm { A } } R _ { \mathrm { A } } } } + j 2 \pi f { \frac { R _ { \mathrm { F } } C _ { \mathrm { A I } } } { a _ { \mathrm { A } } } } } } .
$$

The TJ differential conductance $G _ { \mathrm { { J } } } = 1 / R _ { \mathrm { { J } } }$ can be solved out from Eq.(2.11)，and the measurement method is detailed in Section 6.

$\dot { V _ { \mathrm { i } } }$ is set to O and a sinusoidal current source $\dot { I _ { \mathrm { i } } }$ is added in parallel with TJ,and then the transimpedance gain of the CryoSTM-TIA is $A _ { \mathrm { i } } = \dot { V _ { \mathrm { o } } } / \dot { I _ { \mathrm { i } } }$ .In $( 0 , 1 \ \mathrm { M H z } ]$ ， $A _ { \mathrm { i } }$ is

$$
A _ { \mathrm { i } } \approx - { \frac { R _ { \mathrm { F } } } { 1 + { \frac { 1 } { a _ { \mathrm { A } } } } + { \frac { R _ { \mathrm { F } } } { a _ { \mathrm { A } } R _ { \mathrm { J } } } } + { \frac { R _ { \mathrm { F } } } { a _ { \mathrm { A } } R _ { \mathrm { A } } } } + j 2 \pi f { \frac { R _ { \mathrm { F } } C _ { \mathrm { A I } } } { a _ { \mathrm { A } } } } } } .
$$

How to obtain $| A _ { \mathrm { i } } ( f ) |$ in experiments is detailed in Section 6.

Without the circuit component outside the dashed box in Fig.1,a sinusoidal current source $\dot { I } _ { \mathrm { i T } }$ is added on the input N of the TIA，generating the output voltage $\dot { V } _ { \mathrm { o T } }$ at the output of the TIA. The transimpedance gain of the TIA $A _ { \mathrm { i T } }$ is $A _ { \mathrm { i T } } = \dot { V } _ { \mathrm { o T } } / \dot { I } _ { \mathrm { i T } }$ In $( 0 , 1 \ \mathrm { M H z } ]$ ， $A _ { \mathrm { i T } }$ is

$$
A _ { \mathrm { i T } } \approx - { \frac { R _ { \mathrm { F } } } { 1 + { \frac { 1 } { a _ { \mathrm { A } } } } + { \frac { R _ { \mathrm { F } } } { a _ { \mathrm { A } } R _ { \mathrm { A } } } } + j 2 \pi f { \frac { R _ { \mathrm { F } } C _ { \mathrm { A } } } { a _ { \mathrm { A } } } } } } ,
$$

And, $| A _ { \mathrm { i T } } ( f ) | \geq | A _ { \mathrm { i } } ( f ) |$ , so the bandwidth of the TIA is not less than that of the CryoSTMTIA.

# 3 Circuit of the proposed CryoSTM-TIA

![](images/688eced86bf2ed2a374127d57e9e5bac071cd83dc0de379cf10fc84d9609afc1.jpg)  
Figure 3: Circuit of the proposed CryoSTM-TIA. The Pre-Amp is shown in dashed box (al） and dashed box (a2),the Post-Amp in dashed box (b), the compensated feedback network in dashed box (c),and the signal source circuit in dashed box (d).

The circuit of the proposed CryoSTM-TIA is shown in Fig.3. It consists of four components: the Pre-Amp shown in dashed box (a1) and dashed box (a2) of Fig.3, the Post-Amp shown in dashed box (b), the compensated feedback network shown in dashed box (c),and the signal source circuit shown in dashed box (d). The two stage amplifier made of the Pre-Amp and the Post-Amp is called as Macro-OPA, acting as a OPA. The Macro-OPA is connected with the feedback network to form the TIA.

# 3.1 Design of Pre-Amp

# 3.1.1 Differential amplifier part of Pre-Amp

The differential amplifier part in the Pre-Amp is shown in dashed box (a1) of Fig.3. The transistors H1 and H2 are CNRS-HEMTs. Their sources are connected together and grounded via a variable resistor $R _ { \mathrm { s } }$ . The drains of the two transistors are connected to resistors $R _ { 1 }$ and $R _ { 2 }$ respectively,and $R _ { 1 } = R _ { 2 } = R _ { \mathrm { L } }$ ： $\mathrm { L _ { 1 } }$ and $\mathrm { L _ { 2 } }$ are connected to the two fixed terminals of the potentiometer $R _ { 1 2 }$ ，and the movable terminal of $R _ { 1 2 }$ is connected to the output of the constant-current source, where $R _ { 1 2 } ~ \leq ~ 0 . 0 1 R _ { \mathrm { L } }$ ： $R _ { \mathrm { L 1 } } = R _ { 1 } + \lambda R _ { 1 2 }$ （204号 and $R _ { \mathrm { L 2 } } = R _ { 2 } + ( 1 - \lambda ) R _ { 1 2 }$ ，and $\lambda$ can vary from O to 1. The drains of H1 and H2（O $^ { 1 }$ and O $_ 2$ in Fig.3) as the noninverting and inverting outputs of the Pre-Amp respectively are connected to the noninverting and inverting inputs of the Post-Amp respectively. The gate of H1 as the inverting input of the Pre-Amp is connected to the tip of the CryoSTM, and the gate of H2 as the noninverting input of the Pre-Amp is connected to ground. （204号 $C _ { \mathrm { { A } } }$ is the input capacitance of the Pre-Amp. The capacitors $C _ { \mathrm { s } }$ ， $C _ { 1 }$ and $C _ { 2 }$ as the AC short circuit capacitors are $0 . 1 ~ \mathrm { m F }$ . H1,H2, $R _ { 1 }$ and $R _ { 2 }$ in the Pre-Amp are placed in the cryogenic region. H1 is placed as close as possible to the tip of the CryoSTM, so $C _ { \mathrm { { I } } }$ is reduced to less than O.5 pF.

The voltage difference between the noninverting input of the Pre-Amp and its inverting input is called the differential input voltage of the Pre-Amp,and the voltage difference between the noninverting output of the Pre-Amp and its inverting output is called the differential output voltage of the Pre-Amp. The ratio between its AC differential output voltage and AC differential input voltage is the voltage gain of the Pre-Amp, denote as $A _ { \mathrm { v P } }$ . The gain-bandwidth product of the CNRS-HEMT is $g _ { \mathrm { m } } / [ 2 \pi ( C _ { \mathrm { g s } } + C _ { \mathrm { g d } } ) ] \approx 1$ GHz [9].Hence,the bandwidth of the differential amplifer made of the CNRS-HEMTs is no less than 30 MHz.In $[ 0 , 3 ~ \mathrm { M H z } ]$ ， $A _ { \mathrm { v P } }$ can be considered as a constant,

$$
A _ { \mathrm { v P } } = g _ { \mathrm { m } } R _ { \mathrm { L } } / ( 1 + g _ { \mathrm { d } } R _ { \mathrm { L } } ) .
$$

The input capacitance of the Pre-Amp $C _ { \mathrm { { A } } }$ is

$$
C _ { \mathrm { A } } = C _ { \mathrm { g s } } + ( 1 + A _ { \mathrm { v P } } ) C _ { \mathrm { g d } } .
$$

The output resistance of the Pre-Amp $R _ { \mathrm { d } }$ is

$$
R _ { \mathrm { d } } = R _ { \mathrm { L } } / ( 1 + g _ { \mathrm { d } } R _ { \mathrm { L } } ) .
$$

In this design, the parameters of the differential amplifier part and constant-current source part of the Pre-Amp are listed in Table 2.

Table 2: Parameters of Pre-Amp   

<html><body><table><tr><td>H1&H2</td><td>CNRS-HEMT，Table 1</td></tr><tr><td>RL (2)</td><td>1 k</td></tr><tr><td>R12 (S2)</td><td>10</td></tr><tr><td>Rs (2)</td><td>50</td></tr><tr><td>Cs, C1, C2 (mF)</td><td>0.1, 0.1, 0.1</td></tr><tr><td>BJTs T1 and T2</td><td>BFT93 [30]</td></tr><tr><td>Rb (2)</td><td>347</td></tr><tr><td>Rt (2)</td><td>20 k</td></tr><tr><td>VPp (V)</td><td>+12</td></tr></table></body></html>

According to the parameters listed in Table 1 and 2, $A _ { \mathrm { v P } } ~ = ~ 2 0$ ， $C _ { \mathrm { A } } = 2 6 ~ \mathrm { p F }$ ，and $R _ { \mathrm { d } } = 5 0 0 \Omega$ . The input resistance of the Pre-Amp $R _ { \mathrm { { A } } }$ is the gate-source resistance of the CNRS-HEMT,and $R _ { \mathrm { A } } > 1 0 ~ \mathrm { T } \Omega$ ，which is also the input resistance of the Macro-OPA. Therefore, $R _ { \mathrm { { A } } }$ can be considered as infinity and be ignored in this work.

# 3.1.2 Constant-current source part of Pre-Amp

For the conventional diferential amplifier, two power supplies are used [26, 27],and the schematic circuit is shown as Fig.25(d) in Ref.[27]. If two power supplies are used for the differential amplifier made of the CNRS-HEMTs,i.e. a positive voltage source is connected to the ends of the two load resistances $R _ { \mathrm { { L 1 } } }$ and $R _ { \mathrm { L 2 } }$ ，and the negative power supply is a constant-current source, the voltage fluctuations of the positive voltage source makes the fluctuations of the drain potential of the CNRS-HEMTs in the conventional differential amplifier almost as large as those of the positive voltage source. However, the drain-source voltage $V _ { \mathrm { d s } }$ for the ideal operating point of the CNRS-HEMT is only 100 mV. Therefore, the fluctuations of $V _ { \mathrm { d s } }$ induced by the positive voltage source may be too large to keep the CNRS-HEMTs operating around the ideal operating point. Furthermore, the DX centers (DX $^ -$ ), shallow donors,and channel electrons are not in statistical equilibrium in the CNRS-HEMTs after frozen out, and the large voltage surges dropping between its drain and source may activate the frozen DX $\mathit { \Pi } ^ { - }$ ， changing the DX $^ -$ to the shallow donors, and releasing the electrons [8]. Therefore, the CNRS-HEMTs in the Pre-Amp are easily damaged by the voltage surges from the positive voltage source. It is difficult to be solved by the additional regulator circuit or other protection circuit. For the Pre-Amp in this work, the schema of conventional differential amplifier with two power sources [27] is not suitable.

For the proposed Pre-Amp in this work, only a constant-current source as the power supply as shown in dashed box (a2) of Fig.3 is used. It allows the DC potentials at the drain and source of each CNRS-HEMT to remain constants,as the potential at both the noninverting and inverting inputs of the Pre-Amp remains constants. $C _ { 1 }$ and $C _ { 2 }$ as the short circuit capacitors filter out the noise of the positive voltage source in the constantcurrent source,and $C _ { \mathrm { s } }$ as the short circuit capacitor filters out the noise of $R _ { \mathrm { s } }$ . TINA-TI simulation results show that the $V _ { \mathrm { d s } }$ of the CNRS-HEMTs will fluctuate less than 2 mV, even if the voltage fluctuations of $V _ { \mathrm { P p } }$ is up to 10o mV,i.e. the voltage surges are “filtered out” by the constant-current source. The temperature of the bipolar junction transistors (BJTs) in the constant-current source can be controlled by the temperature controling device,such as TEC [31],with the fluctuations within $0 . 1 ~ ^ { \circ } \mathrm { C }$ ， so as to realize the more stable current. Using a constant-current source as the power supply for the Pre-Amp, the voltage regulation is simple, avoiding voltage surges on the CNRS-HEMTs and other drawbacks of the conventional differential amplifier with two power supplies.

# 3.2Design of Post-Amp and composition of Macro-OPA

The circuit of the Post-Amp is shown in dashed box (b) of Fig.3. The OPA in the Post-Amp is the selected commercial OPA with high gain-bandwidth-product, such as THS4021, OPA657, LMH6624, etc [32]. And, it is called as Rear-OPA in this work. The open-loop voltage gain of the Rear-OPA is $a _ { \mathrm { a } }$ .In a quite large frequency bandwidth (usually $>$ 30 MHz), $a _ { \mathrm { a } }$ can be approximately expressed as $a _ { \mathrm { a } } = a _ { \mathrm { a 0 } } / ( 1 + j f / f _ { \mathrm { b } } )$ ： $R _ { \mathrm { a } }$ and $C _ { \mathrm { a } }$ are the input resistance and capacitance of the Rear-OPA respectively. In the following,only THS4021 [33] as the Rear-OPA is discussed. The feedback resistor $R _ { \mathrm { f } }$ of the Post-Amp is the magnitude of M $\Omega$ . Considering the parasitic capacitance of $R _ { \mathrm { f } }$ as about $0 . 2 \ \mathrm { p F }$ , the frequency compensation in the feedback loop can be used by the same means described in Section 2.3. Since $R _ { \mathrm { f } }$ is quite small, even if there is no compensation, the feedback loop still works well. The noninverting and inverting inputs of Rear-OPA in the room temperature region are connected respectively to the noninverting output $\mathrm { O _ { 1 } }$ and inverting output O $_ 2$ of the Pre-Amp with two cables. The capacitance of the two cables is $C _ { \mathrm { i } 1 }$ and $C _ { \mathrm { i 2 } }$ respectively, and $C _ { \mathrm { i } 1 } = C _ { \mathrm { i } 2 } = C _ { \mathrm { i } } \approx 1 0 0 ~ \mathrm { p F }$ . The Post-Amp parameters are listed in Table 3.

Table 3: Parameters of Post-Amp   

<html><body><table><tr><td>Rear-OPA</td><td>THS4021</td></tr><tr><td>aao (dB)</td><td>97.5</td></tr><tr><td>fb (kHz)</td><td>14.5</td></tr><tr><td>Ca (pF)</td><td>1.5</td></tr><tr><td>Ra ()</td><td>1M</td></tr><tr><td>Rf (MΩ)</td><td>1</td></tr><tr><td>Rd (2)</td><td>500</td></tr><tr><td>Ci (pF)</td><td>100</td></tr><tr><td>Supply voltages VRp, VRn (V)</td><td>+15,-15</td></tr></table></body></html>

The open-loop voltage gain of the Macro-OPA $a \mathrm { A }$ can be expressed as

$$
a _ { \mathrm { { A } } } = A _ { \mathrm { { v P } } } A _ { \mathrm { { v R } } } .
$$

And, $A _ { \mathrm { v R } }$ can be solved out by the the nodal analysis for the Macro-OPA circuit in Fig.3 as

$$
A _ { \mathrm { v R } } \approx \frac { R _ { \mathrm { f } } } { R _ { \mathrm { d } } } \cdot \frac { 1 } { 1 + \frac { R _ { \mathrm { f } } } { a _ { \mathrm { a } } R _ { \mathrm { d } } } + j 2 \pi f \frac { R _ { \mathrm { f } } C _ { \mathrm { i } } } { a _ { \mathrm { a } } } } ,
$$

where $1 / a _ { \mathrm { a } }$ ， $2 R _ { \mathrm { f } } / ( a _ { \mathrm { a } } R _ { \mathrm { a } } )$ ，and $j 4 \pi f R _ { \mathrm { f } } C _ { \mathrm { a } } / a _ { \mathrm { a } }$ have been omitted in the denominator, since $R _ { \mathrm { a } } \gg R _ { \mathrm { d } }$ and $C _ { \mathrm { i } } \gg C _ { \mathrm { a } }$ . According to the parameters listed in Table 3, $R _ { \mathrm { f } } / ( a _ { \mathrm { a 0 } } R _ { \mathrm { d } } ) \ll 1$ ： Therefore, Eq.(3.5) can be expressed as

$$
A _ { \mathrm { v R } } \approx { \frac { R _ { \mathrm { f } } } { R _ { \mathrm { d } } } } \cdot { \frac { 1 } { 1 + j 2 \pi f ( { \frac { R _ { \mathrm { f } } / R _ { \mathrm { d } } } { 2 \pi f _ { \mathrm { b } } a _ { \mathrm { a 0 } } } } + { \frac { R _ { \mathrm { f } } C _ { \mathrm { i } } } { a _ { \mathrm { a 0 } } } } ) + ( j 2 \pi f ) ^ { 2 } { \frac { R _ { \mathrm { f } } C _ { \mathrm { i } } } { 2 \pi f _ { \mathrm { b } } a _ { \mathrm { a 0 } } } } } } .
$$

（204号 $\omega _ { \mathrm { b } } = 2 \pi f _ { \mathrm { b } }$ is denoted. The poles of $A _ { \mathrm { v R } }$ are the solutions of the equation

$$
\frac { R _ { \mathrm { f } } C _ { \mathrm { i } } } { \omega _ { \mathrm { b } } a _ { \mathrm { a 0 } } } s ^ { 2 } + ( \frac { R _ { \mathrm { f } } / R _ { \mathrm { d } } } { \omega _ { \mathrm { b } } a _ { \mathrm { a 0 } } } + \frac { R _ { \mathrm { f } } C _ { \mathrm { i } } } { a _ { \mathrm { a 0 } } } ) s + 1 = 0 .
$$

$s _ { 1 }$ and $s _ { 2 }$ as two poles of $A _ { \mathrm { v R } }$ are

$$
s = - \frac { \omega _ { \mathrm { b } } } { 2 } ( \frac { 1 } { \omega _ { \mathrm { b } } R _ { \mathrm { d } } C _ { \mathrm { i } } } + 1 ) \pm \frac { \omega _ { \mathrm { b } } } { 2 } \sqrt { ( \frac { 1 } { \omega _ { \mathrm { b } } R _ { \mathrm { d } } C _ { \mathrm { i } } } + 1 ) ^ { 2 } - \frac { 4 a _ { \mathrm { a 0 } } } { \omega _ { \mathrm { b } } R _ { \mathrm { f } } C _ { \mathrm { i } } } } ,
$$

It is easily found in Eq.(3.8) that $s _ { 1 }$ and $s _ { 2 }$ can be both negative real numbers, by adjusting the value of $R _ { \mathrm { f } }$ .Hence, $A _ { \mathrm { v R } }$ can be expressed as

$$
A _ { \mathrm { v R } } = \frac { R _ { \mathrm { f } } } { R _ { \mathrm { d } } } \cdot \frac { 1 } { ( 1 + j f / f _ { 1 } ) ( 1 + j f / f _ { 2 } ) } ,
$$

where $f _ { 1 } = - s _ { 1 } / ( 2 \pi )$ and $f _ { 2 } = - s _ { 2 } / ( 2 \pi )$ . According to Table 3, $f _ { 1 } = 6 9 4$ kHz and （204号 $f _ { 2 } = 2 . 4 6$ MHz.

Since $A _ { \mathrm { v P } }$ is regarded as a constant, the poles of $A _ { \mathrm { v R } }$ are also the poles of $a _ { \mathrm { A } }$ . As the poles of $a _ { \mathrm { A } }$ are both negative real numbers,the Macro-OPA is stable [29]. The calculated performances of the Macro-OPA are listed in Table 4.

Table 4: Calculated performances of Macro-OPA with the parameters in Table 2 and 3   

<html><body><table><tr><td>S1,f1 (MHz)</td><td>-1.388π，0.694</td></tr><tr><td>laA(fi)ldB (dB)</td><td>88.6</td></tr><tr><td>∠(aA(f1))</td><td>-59.7°</td></tr><tr><td>S2, f2 (MHz)</td><td>-4.92π，2.46</td></tr><tr><td>JaA(f2)ldB (dB)</td><td>77.8</td></tr><tr><td>∠(aA(f2))</td><td>-118.5°</td></tr></table></body></html>

# 3.3 Circuit stability and transimpedance gain of the proposed CryoSTMTIA

In Fig.3, the output O of the Macro-OPA is connected to its inverting input N with the feedback network shown in dashed box (c) of Fig.3 to form a TIA. The signal source circuit in dashed box (d) of Fig.3 is connected with the TIA to form the CryoSTM-TIA. As mentioned in Section 3.2, the poles of the open-loop voltage gain of the Macro-OPA $a _ { \mathrm { A } }$ （204号 are both negative real numbers and there is no zero for $a _ { \mathrm { A } }$ ，s0 $| a _ { \mathrm { A } } ( f ) |$ and $\angle ( a _ { \mathrm { A } } ( f ) )$ are both monotonic decreasing functions of $f$ ． The method described in Section 2.4 can be used for the proposed CryoSTM-TIA to realizing circuit stability. For the circuit in Fig.3, $f _ { \mathrm { y } } = 2 a _ { 1 } / ( 2 \pi R _ { \mathrm { F } } C ) < f _ { - 6 0 }$ can be easily realized by selecting $R _ { \mathrm { F } }$ and $C _ { \mathrm { I } }$ with the proper values,so the circuit stability is guaranteed, and the gain margin of the circuit stability is at least 6 dB and its phase margin is at least $3 0 ^ { \circ }$ ：

For the proposed CryoSTM-TIA, the parameters of the compensated feedback network and the signal source circuit,including the selected $R _ { \mathrm { F } }$ and $C _ { \mathrm { { I } } }$ ，are listed in Table 5.

Table 5: Parameters of the compensated fedback network and the signal source circuit   

<html><body><table><tr><td colspan="2">Feedback network</td></tr><tr><td>RF (GS)</td><td>1</td></tr><tr><td>CF (pF)</td><td>0.3</td></tr><tr><td>Rk (kS2)</td><td>100</td></tr><tr><td>Ck (pF)</td><td>0.2</td></tr><tr><td>Cc (nF)</td><td>3</td></tr><tr><td colspan="2">Signal source circuit</td></tr><tr><td>Rj (GS2)</td><td>0.001~1</td></tr><tr><td>C1 (pF)</td><td>0.5</td></tr></table></body></html>

By adjusting the SPICE model of a JFET in TINA-TI [19] according to the HEMT parameters listed in Table 1, the SPICE model of the CNRS-HEMT is established and it is applied for H1 and H2 in the Pre-Amp. The SPICE model of THS4021 in TINA-TI is used in the Macro-OPA. In the following, the performances of the proposed CryoSTM-TIA are simulated by TINA-TI with the parameters listed in the Table 1, 2,3, 5. As a function of the signal frequency $f$ ， $a _ { \mathrm { A } }$ can be simulated by TINA-TI, and it can be also calculated by Eq.(3.1)，(3.4), (3.6). The two results are consistent each other (see Supplemental file 2 [32]).

![](images/4c752d2ed172f9b3a38c6ba77c275cec3f07226e759b9aa0d41e839c4367ad0c.jpg)  
Figure 4: TINA-TI simulation results for the open-loop voltage gain of the Macro-OPA $a _ { \mathrm { A } }$ ， the calculated results for $1 / \beta$ of the proposed CryoSTM-TIA and $2 \pi f R _ { \mathrm { F } } C$ ： $\angle ( a _ { \mathrm { A } } ( f _ { - 6 0 } ) ) =$ （204号 $- 6 0 ^ { \circ }$ at $f _ { - 6 0 } = 6 7 1 ~ \mathrm { k H z }$ and $| a _ { \mathrm { A } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } = ( a _ { 1 } ) _ { \mathrm { d B } } = 8 8 . 4$ dB. $f _ { \mathrm { y } } = 2 a _ { 1 } / ( 2 \pi R _ { \mathrm { F } } C ) = 3 2 0$ （204号 $\mathrm { k H z }$ is less than $f _ { - 6 0 }$ ：

Fig.4 shows the TINA-TI simulation results for the open-loop voltage gain of the Macro-OPA $a _ { \mathrm { A } } ( f )$ ，the calculated results for the reciprocal of the feedback factor of the CryoSTM-TIA $1 / \beta ( f )$ ，and the calculated $2 \pi f R _ { \mathrm { F } } C$ . In the curves of $| a _ { \mathrm { A } } ( f ) | _ { \mathrm { d B } }$ and （204号 $\angle ( a _ { \mathrm { A } } ( f ) )$ ， $\angle ( a _ { \mathrm { A } } ( f _ { - 6 0 } ) ) = - 6 0 ^ { \circ }$ at $f _ { - 6 0 } = 6 7 1 ~ \mathrm { k H z }$ and $| a _ { \mathrm { A } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } = ( a _ { 1 } ) _ { \mathrm { d B } } = 8 8 . 4$ dB. The curves of $| 1 / \beta ( f ) | _ { \mathrm { d B } }$ and $\angle ( 1 / \beta ( f ) )$ are obtained by Eq.(2.10) in Section 2.4 with the parameters as $R _ { \mathrm { A } } > 1 0 ~ \mathrm { T } \Omega$ ， $R _ { \mathrm { F } } = 1$ GΩ, $C _ { \mathrm { F } } = 0 . 3 ~ \mathrm { p F }$ ， $R _ { \mathrm { k } } = 1 0 0 ~ \mathrm { k } \Omega$ ， $C _ { \mathrm { k } } = 0 . 2 ~ \mathrm { p F }$ ， （20 $C \approx C _ { \mathrm { A I } } = 2 6 . 5 ~ \mathrm { p F }$ ，and $R _ { \mathrm { J } } = 1$ MΩ. In Fig.4, it is found that $f _ { \mathrm { y } } = 2 a _ { 1 } / ( 2 \pi R _ { \mathrm { F } } C ) = 3 2 0$ （204号 kHz,much less than $f _ { - 6 0 } = 6 7 1 ~ \mathrm { k H z }$ . The conditions described in Section 2.4 for the circuit stability of CryoSTM-TIA are met for it. It is also found that the gain margin of the circuit stability for the CryoSTM-TIA is about 27 dB and its phase margin is about （204号 $7 0 ^ { \circ }$ , much larger than the usual requirements.

$A _ { \mathrm { i T } } ( f )$ is the transimpedance gain of the TIA,as expressed in Eq.(2.13). Fig.5 shows the $A _ { \mathrm { i T } } ( f ) / R _ { \mathrm { F } }$ of the TIA in the CryoSTM-TIA simulated by TINA-TI. It is found that $| A _ { \mathrm { i T } } ( f _ { \mathrm { y } } ) / R _ { \mathrm { F } } | _ { \mathrm { d B } } \approx - 3 ~ \mathrm { d B }$ and $\angle ( A _ { \mathrm { i } } ( f _ { \mathrm { y } } ) / R _ { \mathrm { F } } ) \approx 1 0 1 ^ { \circ }$ at $f _ { \mathrm { y } } = 3 2 0 ~ \mathrm { k H z }$ ，and $f _ { \mathrm { y } }$ is approximately equal to the upper cut-off frequency of the TIA $f _ { \mathrm { h T } }$ .In addition,it is found that $| A _ { \mathrm { i T } } ( f ) / R _ { \mathrm { F } } | _ { \mathrm { d B } }$ decreases monotonically, and there is no “gain peaking” on the curve, which also indicates the circuit is quite stable [29].

As the cable between the tip and the input of the proposed TIA is very short, $C _ { \mathrm { I } }$ is very small, so $C _ { \mathrm { { A } } }$ in Eq.(2.13) is approximate to $C _ { \mathrm { A I } }$ in Eq.(2.12). Thus,the transimpedance gain of the CryoSTM-TIA $A _ { \mathrm { i } }$ is approximate to $A _ { \mathrm { i T } }$ . The upper cut-off frequency of the CryoSTM-TIA $f _ { \mathrm { h C S T } }$ is approximately equal to $f _ { \mathrm { h T } } C _ { \mathrm { A } } / C _ { \mathrm { A I } }$ .According to Fig.5, （20 $f _ { \mathrm { h C S T } } \approx 3 2 0 ~ \mathrm { k H z }$ and $| A _ { \mathrm { i } } ( f _ { \mathrm { h C S T } } ) | \approx 0 . 7 \ \mathrm { G } \Omega$ , so the high-gain and large-bandwidth for the proposed CryoSTM-TIA are realized together.

In supplemental fle 2 [32], for the proposed CryoSTM-TIA with OPA657 or LMH6624 as the Rear-OPA, their performances are also simulated by TINA-TI,and the results are similar to Fig.4 and Fig.5.

![](images/1cc53af627892cc741e99f82e0f385122259d18527e2319033d31b3bba996075.jpg)  
Figure 5: TINA-TI simulation results for $A _ { \mathrm { i T } } ( f ) / R _ { \mathrm { F } }$ ： $A _ { \mathrm { i T } } ( f )$ is the transimpedance gain of the TIA in the proposed CryoSTM-TIA. $| A _ { \mathrm { i T } } ( f _ { \mathrm { y } } ) / R _ { \mathrm { F } } | _ { \mathrm { d B } } \approx - 3$ dB and $\angle ( A _ { \mathrm { i T } } ( f _ { \mathrm { y } } ) / R _ { \mathrm { F } } ) \approx$ $1 0 1 ^ { \circ }$ at $f _ { \mathrm { y } } = 3 2 0 ~ \mathrm { k H z }$

# 3.4 Transient response of the proposed CryoSTM-TIA

![](images/7f6341feb33e159e2d8d4c8c5558536603191762d17264c115c255f2a2a17c74.jpg)  
Figure 6: TINA-TI simulation results for the transient response of the proposed CryoSTMTIA. The dashed curve is the step input signal $V _ { \mathrm { i } }$ and solid curve is the output response $V _ { \mathrm { o } }$ Transient response time $t _ { \mathrm { r } } < 3 . 5$ $\mu \mathrm { s }$ . There is no“ringing” and “overshoot” characteristics in the output response curve, confirming the circuit stability.

In the case of $R _ { \mathrm { J } } = R _ { \mathrm { F } }$ ， the transient response performance of the CryoSTM-TIA simulated by TINA-TI is shown in Fig.6, in which the dashed curve is the step input signal $V _ { \mathrm { i } }$ and the solid curve is the output response $V _ { \mathrm { o } }$ . The time taken from adding the step input signal to the output response stably within $0 . 1 \%$ error is called the transient response time $t _ { \mathrm { r } }$ .Fig.6 shows $t _ { \mathrm { r } } ~ < ~ 3 . 5$ μs. In addition，there is no “ringing”and “overshoot” characteristics in the output response curve, confirming the circuit stability [29].

# 4Noises of the proposed CryoSTM-TIA

The differential equivalent circuit with all noise sources for the circuit of the proposed CryoSTM-TIA shown in Fig.3 is used to calculate its equivalent input noise. The details for the noise calculations are shown in Supplemental file 1 [24].

# 4.1Equivalent input voltage noise and equivalent input current noise of Macro-OPA in the proposed CryoSTM-TIA

The equivalent input noise voltage of CNRS-HEMT H1 and its equivalent input noise current are denoted as $e _ { 1 }$ and $i _ { 1 }$ respectively. Similarly, for CNRS-HEMT H2, there are （204号 $e _ { 2 }$ and $i _ { 2 }$ ： $R _ { 1 }$ and $R _ { 2 }$ are the resistors connected to the drains of H1 and H2 respectively (here $R _ { 1 } = R _ { 2 } = R _ { \mathrm { L } }$ ). $R _ { \mathrm { f } }$ is the feedback resistor.The noises of these resistors above 1 kHz are all thermal noise. The equivalent input noise voltage of the Rear-OPA and its equivalent input noise current are denoted as $e _ { \mathrm { a } }$ and $i _ { \mathrm { a } }$ respectively. All noise sources are independent.

By the nodal analysis method and Wiener-Khintchine_theorem,ignoring the small quantities, such as the thermal noise of $R _ { 1 }$ ， $R _ { 2 }$ and $R _ { \mathrm { f } }$ ， $\overline { { e _ { \mathrm { A } } ^ { 2 } } }$ ， $i _ { \mathrm { A } } ^ { 2 }$ ， $\overline { { e _ { \mathrm { A } } i _ { \mathrm { A } } ^ { * } } }$ ，and $\overline { { i _ { \mathrm { A } } e _ { \mathrm { A } } ^ { * } } }$ for the Macro-OPA of the proposed CryoSTM-TIA can be expressed approximately as

$$
\overline { { e _ { \mathrm { A } } ^ { 2 } } } = 2 \overline { { e _ { \mathrm { H } } ^ { 2 } } } + \overline { { e _ { \mathrm { a } } ^ { 2 } } } / A _ { \mathrm { v P } } ^ { 2 } + 4 \overline { { i _ { \mathrm { a } } ^ { 2 } } } / g _ { \mathrm { m } } ^ { 2 } ,
$$

$$
\overline { { i _ { \mathrm { A } } ^ { 2 } } } = \overline { { i _ { \mathrm { H } } ^ { 2 } } } + ( 2 \pi f ) ^ { 2 } C _ { \mathrm { A } } ^ { 2 } ( \overline { { e _ { \mathrm { H } } ^ { 2 } } } + \overline { { e _ { \mathrm { a } } ^ { 2 } } } / A _ { \mathrm { v P } } ^ { 2 } ) + ( 2 \pi f ) ^ { 2 } ( C _ { \mathrm { g s } } + C _ { \mathrm { g d } } + C _ { \mathrm { A } } ) ^ { 2 } \overline { { i _ { \mathrm { a } } ^ { 2 } } } / g _ { \mathrm { m } } ^ { 2 } ,
$$

$$
\overline { { e _ { \mathrm { A } } i _ { \mathrm { A } } ^ { * } } } = ( \overline { { i _ { \mathrm { A } } e _ { \mathrm { A } } ^ { * } } } ) ^ { * } = - j 2 \pi f C _ { \mathrm { A } } ( \overline { { e _ { \mathrm { H } } ^ { 2 } } } + \overline { { e _ { \mathrm { a } } ^ { 2 } } } / { A _ { \mathrm { v P } } ^ { 2 } } ) - j 4 \pi f ( C _ { \mathrm { g s } } + C _ { \mathrm { g d } } + C _ { \mathrm { A } } ) \overline { { i _ { \mathrm { a } } ^ { 2 } } } / { g _ { \mathrm { m } } ^ { 2 } } ,
$$

where $\overline { { e _ { \mathrm { H } } ^ { 2 } } } = \overline { { e _ { 1 } ^ { 2 } } } = \overline { { e _ { 2 } ^ { 2 } } }$ is the equivalent input noise voltage PSD of the CNRS-HEMTs (i.e. H1 and H2) and $\overline { { i _ { \mathrm { H } } ^ { 2 } } } = \overline { { i _ { 1 } ^ { 2 } } } = \overline { { i _ { 2 } ^ { 2 } } }$ is their equivalent input noise current PSD. The CNRSHEMT parameters are listed in Table 1. For THS4021 as the Rear-OPA, $\overline { { e _ { \mathrm { a } } ^ { 2 } } } \approx 2 ~ \mathrm { ( n V ) ^ { 2 } / H z }$ （20 and $\overline { { i _ { \mathrm { a } } ^ { 2 } } } \approx 4 ~ \mathrm { ( p A ) ^ { 2 } / H z }$ for $f \geq 1 0 ~ \mathrm { k H z }$ As $A _ { \mathrm { v P } } = 2 0$ and $g _ { \mathrm { m } } = 4 0 ~ \mathrm { m S }$ ， $e _ { \mathrm { a } } ^ { 2 } / A _ { \mathrm { v P } } ^ { 2 }$ and $i _ { \mathrm { a } } ^ { 2 } / g _ { \mathrm { m } } ^ { 2 }$ （204号 are less than $0 . 0 7 \overline { { e _ { \mathrm { H } } ^ { 2 } } }$ . Therefore,further omiting the minor terms, Eq.(4.1), (4.2), (4.3) can be expressed as

$$
\overline { { e _ { \mathrm { A } } ^ { 2 } } } = 2 \overline { { e _ { \mathrm { H } } ^ { 2 } } } ,
$$

$$
\overline { { i _ { \mathrm { A } } ^ { 2 } } } = \overline { { i _ { \mathrm { H } } ^ { 2 } } } + ( 2 \pi f ) ^ { 2 } C _ { \mathrm { A } } ^ { 2 } \overline { { e _ { \mathrm { H } } ^ { 2 } } } ,
$$

$$
\overline { { { e _ { \mathrm { A } } i _ { \mathrm { A } } ^ { * } } } } = ( \overline { { { i _ { \mathrm { A } } e _ { \mathrm { A } } ^ { * } } } } ) ^ { * } = - j 2 \pi f C _ { \mathrm { A } } \overline { { { e _ { \mathrm { H } } ^ { 2 } } } } ,
$$

in which $C _ { \mathrm { A } } = 2 6 ~ \mathrm { p F }$ . Thus, $e _ { \mathrm { A } } ^ { 2 } = 0 . 5 ~ \mathrm { ( n V ) ^ { 2 } / H z }$ and $\overline { { i _ { \mathrm { A } } ^ { 2 } } } = 0 . 8 ~ \mathrm { ( f A ) ^ { 2 } / H z }$ at $f = 1 0 ~ \mathrm { k H z }$ ， and $\overline { { e _ { \mathrm { A } } ^ { 2 } } } = 0 . 1 4 ~ \mathrm { ( n V ) ^ { 2 } / H z }$ and $i _ { \mathrm { A } } ^ { 2 } = 2 0 ~ \mathrm { ( f A ) ^ { 2 } / H z }$ at $f = 1 0 0 ~ \mathrm { k H z }$ , as listed in Table 6.

# 4.2Equivalent input current noise of the proposed CryoSTM-TIA

The Macro-OPA connected with the feedback resistor $R _ { \mathrm { F } }$ to form the TIA in the proposed CryoSTM-TIA. According to the noise models in Section 2.1, $\overline { { e _ { \mathrm { T } } ^ { 2 } } }$ ， $i _ { \mathrm { T } } ^ { 2 }$ ， $\overline { { e _ { \mathrm { T } } i _ { \mathrm { T } } ^ { * } } }$ ，and $\overline { { i _ { \mathrm { T } } e _ { \mathrm { T } } ^ { * } } }$ can be obtained by putting Eq.(4.4),(4.5), (4.6) into Eq.(2.1),(2.2), (2.3). With $R _ { \mathrm { F } } = 1$ $\mathrm { G } \Omega$ ， （204号 $C _ { \mathrm { A } } = 2 6 ~ \mathrm { p F }$ ， $\overline { { e _ { \mathrm { T } } ^ { 2 } } }$ is $0 . 5 ~ \mathrm { { ( n V ) ^ { 2 } / H z } }$ at $1 0 ~ \mathrm { k H z }$ and $0 . 1 4 ~ \mathrm { ( n V ) ^ { 2 } / H z }$ at $1 0 0 ~ \mathrm { k H z }$ ，and $\overline { { i _ { \mathrm { T } } ^ { 2 } } }$ is $\mathrm { 1 \ ( f A ) ^ { 2 } / H z }$ at $1 0 ~ \mathrm { k H z }$ and $\mathrm { 2 0 ~ ( f A ) ^ { 2 } / H z }$ at $1 0 0 ~ \mathrm { k H z }$ ：

For the proposed CryoSTM-TIA, putting Eq.(4.4), (4.5), (4.6) into Eq.(2.5), the equivalent input noise current PSD of the CryoSTM-TIA $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ can be obtained as

$$
\overline { { i _ { \mathrm { i n } } ^ { 2 } } } = \overline { { i _ { \mathrm { H } } ^ { 2 } } } + 4 k _ { \mathrm { B } } T / R _ { \mathrm { F } } + [ ( 2 \pi f ) ^ { 2 } ( C ^ { 2 } + C _ { \mathrm { I J } } ^ { 2 } ) + 2 ( 1 / R _ { \mathrm { F } } + 1 / R _ { \mathrm { J } } ) ^ { 2 } ] \overline { { e _ { \mathrm { H } } ^ { 2 } } } ,
$$

i.e.

$$
\overline { { i _ { \mathrm { i n } } ^ { 2 } } } = \overline { { i _ { \mathrm { A } } ^ { 2 } } } + 4 k _ { \mathrm { B } } T / R _ { \mathrm { F } } + ( 2 \pi f ) ^ { 2 } C C _ { \mathrm { I J } } \overline { { e _ { \mathrm { A } } ^ { 2 } } } + ( 1 / R _ { \mathrm { F } } + 1 / R _ { \mathrm { J } } ) ^ { 2 } \overline { { e _ { \mathrm { A } } ^ { 2 } } } .
$$

Eq.(4.8) shows the equivalent input noise current PSD of the CryoSTM-TIA has four components: the equivalent input noise current PSD of the Macro-OPA $\overline { { i _ { \mathrm { A } } ^ { 2 } } }$ , the thermal noise current PSD of $R _ { \mathrm { F } }$ as $4 k _ { \mathrm { B } } T / R _ { \mathrm { F } }$ , the noise component concerned with the capacitance （204号 $C _ { \mathrm { I } }$ as $\overline { { i _ { \mathrm { C I } } ^ { 2 } } } = ( 2 \pi f ) ^ { 2 } C C _ { \mathrm { I J } } \overline { { e _ { \mathrm { A } } ^ { 2 } } }$ ,the noise component concerned with $R _ { \mathrm { J } }$ as $( 1 / R _ { \mathrm { F } } + 1 / R _ { \mathrm { J } } ) ^ { 2 } { \overline { { e _ { \mathrm { A } } ^ { 2 } } } }$ Eq.(4.8） is also suitable for the conventional CryoSTM-TIA. For the conventional CryoSTM-TIA with the DE-DLPCA-20O as the TIA, the TIA and $R _ { \mathrm { F } }$ are both at room temperatures,and the tip-sample junction is at low temperatures. $R _ { \mathrm { F } } = 1$ $\mathrm { G } \Omega$ ， $C _ { \mathrm { { A } } } = 5$ （204号 pF， $C _ { \mathrm { I } } = 1 0 0 \ \mathrm { p F }$ ，and $C \approx C _ { \mathrm { I } }$ .For DE-DLPCA-200, $\overline { { e _ { \mathrm { T } } ^ { 2 } } } = 1 6 ~ ( \mathrm { n V } ) ^ { 2 } / \mathrm { H z }$ and $i _ { \mathrm { T } } ^ { 2 } =$ 1 $\mathrm { 3 . 6 ~ ( f A ) ^ { 2 } / H z }$ at $f = 1 ~ \mathrm { k H z }$ [21]. $e _ { \mathrm { A } } ^ { 2 } = 1 6 ~ \mathrm { ( n V ) ^ { 2 } / H z }$ and $i _ { \mathrm { A } } ^ { 2 } = 2 . 6 ~ \mathrm { ( f A ) ^ { 2 } / H z }$ at $f = 1 \ \mathrm { k H z }$ （204号 can be estimated. For the conventional CryoSTM-TIA with the DE-DLPCA-200 as the TIA, as $R _ { \mathrm { J } } = 1$ MΩ, $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ and its four components are listed in Table 6.

For the proposed CryoSTM-TIA, THS4021 is selected as the Rear-OPA in the TIA, $R _ { \mathrm { F } } = 1$ GΩ, $C _ { \mathrm { A } } = 2 6 ~ \mathrm { p F }$ ， $C _ { \mathrm { I } } = 0 . 5 ~ \mathrm { p F }$ ，and $C _ { \mathrm { J } } = 1 0$ fF[2,25]. $R _ { \mathrm { F } }$ and the tip-sample junction are at 4.2 K. As $R _ { \mathrm { J } } = 1 ~ \mathrm { M } \Omega$ ， $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ and its four components are listed in Table 6. The inherent noise of the proposed CryoSTM-TIA at $1 0 0 ~ \mathrm { k H z }$ is even much lower than that of the conventional CryoSTM-TIA at $1 \ \mathrm { k H z }$ . The design of the CryoSTM-TIA with high gain, large bandwidth,and low noise is achieved.

Table 6: Noise components of CryoSTM-TIAs   

<html><body><table><tr><td>TIA type</td><td colspan="2">The proposed TIA</td><td>DE-DLPCA-200</td></tr><tr><td>CA,C1,CJ (pF)</td><td colspan="2">26,0.5,0.01</td><td>5,100,0.01</td></tr><tr><td>RF (2)</td><td colspan="2">1G</td><td>1G</td></tr><tr><td>RJ (2)</td><td colspan="2"></td><td></td></tr><tr><td>Tof RF (K)</td><td colspan="2">1M</td><td>1M</td></tr><tr><td>f (kHz)</td><td colspan="2">4.2 100</td><td>300 1</td></tr><tr><td>e² ((nV)²/Hz)</td><td>10 0.5</td><td>0.14</td><td>16</td></tr><tr><td colspan="4">Unit for the following terms is (fA)²/Hz</td></tr><tr><td></td><td>0.8</td><td>20</td><td>2.6</td></tr><tr><td>4kBT/RF 记</td><td>0.2 0.03</td><td>0.2 0.7</td><td>16 6.3</td></tr><tr><td>(+）</td><td>0.5</td><td>0.14</td><td>16</td></tr><tr><td></td><td>1.5</td><td>21</td><td>41</td></tr></table></body></html>

# 5DC tunneling current Measurements by the proposed CryoSTMTIA

For the proposed CryoSTM-TIA in Fig.3, CNRS-HEMTs H1 and H2 with the same performances should be selected as far as possible in the Pre-Amp. The gate P of H2 is constantly grounded.

![](images/c682a75a165688075e30e2732c3867607dec5ff7f5581f661f597ece7cad878c.jpg)  
Figure 7: Scheme of DC circuit of the proposed CryoSTM-TIA. Vos is the input ofset voltage of the Macro-OPA.

Disconnect the Pre-Amp from the Post-Amp,and ground the signal input of the PreAmp,i.e. ground the gate N of H1. Adjust potentiometer $R _ { 1 2 }$ ，so that the two drain load resistors $R _ { \mathrm { { L 1 } } }$ and $R _ { \mathrm { L 2 } }$ are equal (i.e. $\lambda = 0 . 5$ ). Adjust the output current generated from the constant-current source in dashed box (a2) of Fig.3 to the differential amplifier in dashed box (al） of Fig.3 to $I _ { \mathrm { s o u r } } = 2$ mA.Adjust the resistance $R _ { \mathrm { s } }$ to achieve the gate-source voltage $V _ { \mathrm { g s } }$ of H1 and H2 for their operating points near the ideal one as far as possible.

Cascade the Pre-Amp and Post-Amp to form the Macro-OPA. Then, the DC voltage （204号 $V _ { \mathrm { o m } }$ at the output of the Macro-OPA is called as the output offset voltage of Macro-OPA. $V _ { \mathrm { o m } }$ is induced by the input offset voltage of the Rear-OPA in the Post-Amp,its input bias currents and input offset current,and the common-mode DC voltages output from the two outputs of the Pre-Amp to the Rear-OPA. Usually, $V _ { \mathrm { o m } }$ is not O. The DC parameters of THS4021 as the Rear-OPA are listed in Table 7 [33]. The ratio between the DC output voltage increment of the Macro-OPA and its differential DC input voltage increment is called as the DC voltage gain of the Macro-OPA, denoted as $a _ { \mathrm { A 0 } }$ . And, $a _ { \mathrm { A 0 } } \approx g _ { \mathrm { m } } R _ { \mathrm { f } }$ can be obtained by the nodal analysis for the circuit in Fig.3. The input offset voltage of the Macro-OPA is denoted as $V _ { \mathrm { O S } }$ ， as shown in Fig.7. And, $V _ { \mathrm { o m } } = a _ { \mathrm { A 0 } } V _ { \mathrm { O S } }$ . Since the input resistances of H1 and H2 can be considered as infinity, the input bias currents and input offset current of the Macro-OPA can be considered as O. According to the parameters in Table 7, Vos can be estimated to be about 31 $\mu$ V. How to estimate $V _ { \mathrm { O S } }$ is presented in Supplemental file 3 [34].

Table 7: DC parameters of THS4021 as Rear-OPA   

<html><body><table><tr><td>aao</td><td>97.5 dB</td></tr><tr><td>CMRR</td><td>95 dB</td></tr><tr><td>Input offset voltage</td><td>0.5 mV</td></tr><tr><td>Input bias current</td><td>3 μA</td></tr><tr><td>Input offset current</td><td>30 nA</td></tr></table></body></html>

Connect the gate N of H1 to the output end of the Macro-OPA with the feedback resistor $R _ { \mathrm { F } }$ ，and then disconnect it from ground,to form the TIA,as shown in Fig.7. Here,Switch K is off, i.e. the signal source circuit is disconnected. The output voltage of the TIA is $V _ { \mathrm { t i a } }$ , which is equal to the voltage at the TIA input N. For $V _ { \mathrm { t i a } }$ ，

$$
a _ { \mathrm { A 0 } } ( V _ { \mathrm { O S } } - V _ { \mathrm { t i a } } ) = V _ { \mathrm { t i a } } .
$$

$V _ { \mathrm { t i a } } = V _ { \mathrm { O S } } a _ { \mathrm { A 0 } } / ( 1 + a _ { \mathrm { A 0 } } )$ is approximately equal to $V _ { \mathrm { O S } }$ ： $V _ { \mathrm { t i a } }$ can be measured. And, $\vert V _ { \mathrm { t i a } } \vert$ can be lowered by adjusting $R _ { 1 2 }$ ， even to 0.

Switch on Switch K,i.e. the signal source circuit is connected to the TIA, to form the CryoSTM-TIA,as shown in Fig.7. Here, the TJ DC resistance is denoted as $R$ . As DC input signal $V _ { \mathrm { i } }$ is applied, $V _ { \mathrm { { N } } }$ is the voltage at point N, and $V _ { \mathrm { o } }$ is the output voltage of the CryoSTM-TIA. For the CryoSTM-TIA,

$$
a _ { \mathrm { A 0 } } ( V _ { \mathrm { O S } } - V _ { \mathrm { N } } ) = V _ { \mathrm { o } } ,
$$

$$
( V _ { \mathrm { i } } - V _ { \mathrm { N } } ) / R = ( V _ { \mathrm { N } } - V _ { \mathrm { o } } ) / R _ { \mathrm { F } } .
$$

The DC bias applied on TJ is

$$
V = V _ { \mathrm { i } } - V _ { \mathrm { N } } .
$$

The DC tunneling current is

$$
I = ( V _ { \mathrm { i } } - V _ { \mathrm { N } } ) / R .
$$

$V _ { \mathrm { o } }$ and $V _ { \mathrm { i } }$ can be obtained by measurements. $I _ { \mathrm { s } }$ is denoted as

$$
I _ { \mathrm { s } } = - ( V _ { \mathrm { o } } - V _ { \mathrm { t i a } } ) / R _ { \mathrm { F } } .
$$

By the above six equations, the relative error of $I _ { \mathrm { s } }$ as an approximation of $I$ is obtained as

$$
E r = | I _ { \mathrm { s } } - I | / | I | = 1 / ( 1 + a _ { \mathrm { A 0 } } ) ,
$$

and $V$ is

$$
V = { \frac { ( 1 + a _ { \mathrm { A 0 } } ) R } { ( 1 + a _ { \mathrm { A 0 } } ) R + R _ { \mathrm { F } } } } { ( V _ { \mathrm { i } } - V _ { \mathrm { t i a } } ) } .
$$

As $a _ { \mathrm { A 0 } } \approx g _ { \mathrm { m } } R _ { \mathrm { f } } = 4 0 , 0 0 0$ ， $E r < 0 . 0 0 3 \%$ . And,as the CryoSTM-TIA is used for the measurements in the condition of $R _ { \mathrm { J } } \geq 1 0 ^ { - 3 } R _ { \mathrm { F } }$ , Eq.(5.4) can be expressed approximately as

$$
V = V _ { \mathrm { i } } - V _ { \mathrm { t i a } } .
$$

![](images/3ea9fc0064b66392d6ccb73a9fa3f1278d52b9a2d13e5819320a748c75341bf4.jpg)  
Figure 8: For the proposed CryoSTM-TIA, $E r = | { \cal I } _ { \mathrm { s } } - { \cal I } | / | { \cal I } |$ vs. $R$ ( $R \in [ 1 \mathrm { ~ M } \Omega , 1 \mathrm { ~ G } \Omega ] )$ is simulated by TINA-TI with $V _ { \mathrm { i } } = 1 ~ \mathrm { m V }$ (Solid curve） and $V _ { \mathrm { i } } = 5 ~ \mathrm { m V }$ (Dashed curve). The simulation results show $E r < 3 0 ~ \mathrm { p p m }$ , consistent with the above calculated results.

For the CryoSTM-TIA with the circuit in Fig.3, assuming the performances of H1 are as same as those of H2 and $R _ { \mathrm { L 1 } } = R _ { 1 } + 0 . 5 R _ { 1 2 } = R _ { \mathrm { L 2 } } = R _ { 2 } + 0 . 5 R _ { 1 2 }$ ， $E r = | { \cal I } _ { \mathrm { s } } - I | / | I |$ vS. $R$ ( $R \in \left[ 1 \mathrm { ~ M ~ } \Omega , 1 \mathrm { ~ G ~ } \Omega \right] )$ simulated by TINA-TI are shown in Fig.8. The simulation results show $E r < 3 0 \mathrm { p p m }$ ， consistent with the above calculated results.

# 6Applications of spectra measurements by the proposed CryoSTM-TIA

In this section, I illustrate how the proposed CryoSTM-TIA is used for various spectra measurements. Especially, how to obtain the STSNS in experiments are illustrated and the measurement accuracy is estimated.

# 6.1Measurements of scanning tunneling current spectra by the proposed CryoSTM-TIA

The scanning tunneling current spectra measured with the CryoSTM is the function of $I \ = \ I ( V )$ ，where $V$ is the DC bias on the tip-sample TJ and $I$ is the DC tunneling current. For the measurements of $I = I ( V )$ ( $V \in [ V _ { \mathrm { L } } , V _ { \mathrm { H } } ] ,$ ),using the CryoSTM-TIA, only the DC bias $V _ { \mathrm { i } }$ is provided by BMS, i.e. $\dot { V _ { \mathrm { i } } } = 0$ ，and $V _ { \mathrm { i } } \in [ V _ { \mathrm { i L } } , V _ { \mathrm { i H } } ]$ ，where $V _ { \mathrm { i L } } = V _ { \mathrm { L } } + V _ { \mathrm { t i a } }$ （20 and $V _ { \mathrm { i H } } = V _ { \mathrm { H } } + V _ { \mathrm { t i a } }$ according to Eq.(5.5). The corresponding DC output voltage of the CryoSTM-TIA $V _ { \mathrm { o } }$ is measured. According to Eq.(5.2) and (5.5), the approximate value of （20 $I$ is $I _ { \mathrm { s } } = - ( V _ { \mathrm { o } } - V _ { \mathrm { t i a } } ) / R _ { \mathrm { F } }$ , and the approximate value of $V$ is $V _ { \mathrm { { s } } } = V _ { \mathrm { { i } } } - V _ { \mathrm { { t i a } } }$ . The function of $I _ { \mathrm { s } } = I _ { \mathrm { s } } ( V _ { \mathrm { s } } )$ ( $V _ { \mathrm { s } } \in [ V _ { \mathrm { L } } , V _ { \mathrm { H } } ]$ ） is the measured scanning tunneling current spectra.

# 6.2 Measurements of transimpedance gain of the proposed CryoSTMTIA

In the CryoSTM-TIA,only DC bias $V _ { \mathrm { i } }$ is provided by BMS,i.e. $\dot { V _ { \mathrm { i } } } = 0$ . A sinusoidal current signal is connected in paralel with TJ,and Eq.(2.12) gives a representation of the transimpedance gain. For the CryoSTM-TIA, in Eq.(2.12), $R _ { \mathrm { F } } = 1$ （2 $\mathrm { G } \Omega$ ， $R _ { \mathrm { A } } > 1 0 ~ \mathrm { T } \Omega$ ,and （20 $C \approx C _ { \mathrm { A I } } = 2 6 . 5 ~ \mathrm { p F }$ , as listed in Table 6. And, as shown in Fig.4, $| a _ { \mathrm { A } } ( f _ { - 6 0 } ) | _ { \mathrm { d B } } = 8 8 . 4 \ : \mathrm { d B }$ at $f _ { - 6 0 } = 6 7 1 \mathrm { ~ k H z }$ ,and $| a _ { \mathrm { A } } ( f ) | \geq 1 0 ^ { 9 1 / 2 0 } \approx 3 5 , 0 0 0 \$ in $[ 1 ~ \mathrm { k H z } , 3 0 0 ~ \mathrm { k H z } ]$ .When $R _ { \mathrm { J } } \geq 1 0 ^ { - 3 } R _ { \mathrm { F } }$ ， in $[ 1 ~ \mathrm { k H z } , 3 0 0 ~ \mathrm { k H z } ]$ ,Eq.(2.12) for $\lvert A _ { \mathrm { i } } \rvert$ can be approximately simplified as

$$
\left| A _ { \mathrm { i } } \right| = \frac { R _ { \mathrm { F } } } { | 1 + j 2 \pi f R _ { \mathrm { F } } C _ { \mathrm { A I } } / a _ { \mathrm { A } } ( f ) | } .
$$

![](images/4e54cfedd97ffae2ee9262d0c405ad079ceff658a4f0bfd5c6b62f89a8a76757.jpg)  
Figure 9: Accessory circuit for measuring transimpedance gain of the proposed CryoSTMTIA.

The accessory circuit shown in Fig.9 replaces TJ and BMS in the signal source circuit in dashed box (d) of Fig.3,connected to point A in Fig.3. The accessory circuit here is identical in structure with that of the compensated feedback network shown in Fig.2 (i.e. dashed box (c) in Fig.3),but with different parameters. Here, $R _ { \mathrm { j } } = 1 0 0$ MΩ, $R _ { \mathrm { k j } }$ is adjustable around $1 0 ~ \mathrm { k } \Omega$ ， $C _ { \mathrm { c j } } = 3 ~ \mathrm { n F }$ , the parasitic capacitance of $R _ { \mathrm { j } }$ and $R _ { \mathrm { k j } }$ is denoted as $C _ { \mathrm { j } }$ and $C _ { \mathrm { k j } }$ respectively. $C _ { \mathrm { j } }$ and $C _ { \mathrm { k j } }$ are about O.3 pF and 0.2 pF respectively. Adjust （20 $R _ { \mathrm { k j } }$ to realize $R _ { \mathrm { k j } } C _ { \mathrm { c j } } = R _ { \mathrm { j } } C _ { \mathrm { j } }$ . Here,BMS only provides the modulated signal voltage $\dot { V _ { \mathrm { i } } }$ Similar to the feedback network in Section 2.3, the impedance of the accessory circuit $Z _ { \mathrm { j } } = R _ { \mathrm { j } } / ( 1 + j 2 \pi f R _ { \mathrm { k j } } C _ { \mathrm { k j } } )$ . Since $R _ { \mathrm { k j } } C _ { \mathrm { k j } } < 2 \times 1 0 ^ { - 9 }$ , it can be considered that $Z _ { \mathrm { j } }$ is equal to $R _ { \mathrm { j } }$ in $[ 1 ~ \mathrm { k H z } , 3 0 0 ~ \mathrm { k H z } ]$ . Thus,the CryoSTM-TIA is modified by replacing TJ in the original circuit with a pure resistance $R _ { \mathrm { j } } = 1 0 0 ~ \mathrm { M } \Omega$ without parasitic capacitance. In $[ 1 ~ \mathrm { k H z } , 3 0 0 ~ \mathrm { k H z } ]$ , the voltage gain of the modified CryoSTM-TIA $| A _ { \mathrm { v j } } ( f ) | = | \dot { V } _ { \mathrm { o } } | / | \dot { V } _ { \mathrm { i } } |$ can be measured with $V _ { \mathrm { i } } = 0$ , and Eq.(2.11) for $| A _ { \mathrm { v j } } ( f ) |$ can be approximately modified as

$$
| A _ { \mathrm { v j } } ( f ) | = \frac { 1 } { R _ { \mathrm { j } } } \cdot \frac { R _ { \mathrm { F } } } { | 1 + j 2 \pi f R _ { \mathrm { F } } C _ { \mathrm { A I } } / a _ { \mathrm { A } } ( f ) | } .
$$

Comparing Eq.(6.1) and Eq.(6.2),

$$
| A _ { \mathrm { i } } ( f ) | = R _ { \mathrm { j } } | A _ { \mathrm { v j } } ( f ) | ,
$$

And, $| A _ { \mathrm { i } } ( f ) |$ is independent of $R _ { \mathrm { j } }$ . By this means,in $\left\lfloor 1 \mathrm { ~ k H z } , 3 0 0 \mathrm { ~ k H z } \right\rfloor$ ,the transimpedance gain $| A _ { \mathrm { i } } ( f ) |$ can be obtained in experiments with $R _ { \mathrm { j } }$ and the measured $| A _ { \mathrm { v j } } ( f ) |$

# 6.3 Measurements of the scanning tunneling differential conductance spectra by the proposed CryoSTM-TIA

The TJ differential resistance $R _ { \mathrm { J } }$ is a function of the bias $V$ on TJ, i.e. $R _ { \mathrm { J } } = R _ { \mathrm { J } } ( V )$ ，where $V \approx V _ { \mathrm { s } } = V _ { \mathrm { i } } - V _ { \mathrm { t i a } }$ according to Eq.(5.5). For $f < 1 \ \mathrm { k H z }$ ,the TJ impedance $| Z _ { \mathrm { J } } ( f ) | \approx R _ { \mathrm { J } }$ ， and $| a _ { \mathrm { A } } ( f ) |$ is about $a _ { \mathrm { A 0 } } = g _ { \mathrm { m } } R _ { \mathrm { f } } = 4 0 , 0 0 0$ . According to Eq.(2.11)，at low frequencies, such as $f < 1 \ \mathrm { k H z }$ ， $\lvert A _ { \mathrm { v } } \rvert$ is

$$
| A _ { \mathrm { v } } | \approx \frac { R _ { \mathrm { F } } } { R _ { \mathrm { J } } } \cdot \frac { 1 } { 1 + R _ { \mathrm { F } } / ( a _ { \mathrm { A 0 } } R _ { \mathrm { J } } ) } .
$$

$G _ { \mathrm { J } } ( V ) = 1 / R _ { \mathrm { J } } ( V )$ can be solved out from Eq.(6.4) with the measured $\vert A _ { \mathrm { v } } \vert$ .In fact，so long as $R _ { \mathrm { F } } / | A _ { \mathrm { v } } | \geq 1 0 ^ { - 3 } R _ { \mathrm { F } }$ ， $R _ { \mathrm { J } }$ obtained by $R _ { \mathrm { J } } \approx R _ { \mathrm { F } } / | A _ { \mathrm { v } } |$ is almost equal to that obtained with Eq.(6.4).

The measurement speed of the scanning tunneling differential conductance spectra （204号 $G _ { \mathrm { J } } = G _ { \mathrm { J } } ( V )$ （ $V \in [ V _ { \mathrm { L } } , V _ { \mathrm { H } } ] ,$ ） can be accelerated by increasing the modulation frequency. In the condition of $R _ { \mathrm { J } } \geq 1 0 ^ { - 3 } R _ { \mathrm { F } }$ ， so long as $f < 1 / ( 2 0 \pi R _ { \mathrm { J } } C _ { \mathrm { J } } )$ , by Eq.(2.11), $| A _ { \mathrm { v } } ( f ) |$ can be expressed as

$$
| A _ { \mathrm { v } } ( f ) | \approx \frac { 1 } { R _ { \mathrm { J } } } \cdot \frac { R _ { \mathrm { F } } } { | 1 + j 2 \pi f R _ { \mathrm { F } } C _ { \mathrm { A I } } / a _ { \mathrm { A } } ( f ) | } = \frac { 1 } { R _ { \mathrm { J } } } \cdot | A _ { \mathrm { i } } ( f ) | .
$$

And, the solution is

$$
R _ { \mathrm { J } } ( V ) \approx | A _ { \mathrm { i } } ( f ) | / | A _ { \mathrm { v } } ( f ) | .
$$

Here, $| A _ { \mathrm { v } } ( f ) |$ can be measured and $| A _ { \mathrm { i } } ( f ) |$ is obtained in advance as mentioned in Section 6.2. Thus, $G _ { \mathrm { J } } ( V ) = 1 / R _ { \mathrm { J } } ( V )$ can be obtained in experiments.

However, for the various systems, it is difficult to estimate the value of $R _ { \mathrm { J } } C _ { \mathrm { J } }$ .The experiments need doing to judge how high the modulation frequency $f$ is suitable for a specific system under test yet. Firstly, the accurate values of $R _ { \mathrm { J } }$ at a few TJ DC bias values of $V$ in $[ V _ { \mathrm { L } } , V _ { \mathrm { H } } ]$ (i.e. $V _ { \mathrm { i } } \in [ V _ { \mathrm { i L } } , V _ { \mathrm { i H } } ]$ mentioned in Section 6.1） are measured with the modulation signal $\dot { V _ { \mathrm { i } } }$ at a low frequency. And then, $R _ { \mathrm { J } }$ at the same TJ DC bias values are measured with $\dot { V _ { \mathrm { i } } }$ at a higher frequency. If the two series of results are within the allowable error range, the whole spectra of $G _ { \mathrm { { J } } } ( V )$ vs. $V$ in $[ V _ { \mathrm { L } } , V _ { \mathrm { H } } ]$ can be measured with $\dot { V _ { \mathrm { i } } }$ at the higher frequency thoroughly. For the conventional CryoSTM-TIA， the modulation frequency $f$ is usually less than $1 \ \mathrm { k H z }$ . For the proposed CryoSTM-TIA, the modulation frequency of $1 0 ~ \mathrm { k H z }$ is expected to be suitable for many systems under test.

# 6.4Measurements of scanning tunneling shot noise spectra by the proposed CryoSTM-TIA

![](images/a950618c12c8ca8e5ce0a5bb7e2fcae699c466438aeee6fa207ab711850896b7.jpg)  
Figure 1O: Schematic curve of the scanning tunneling differential conductance spectra of the SIS system. $D _ { \mathrm { { V } } }$ is noted with several thick lines on the $V$ axis.The line of $G _ { \mathrm { h } } = 1$ （204号 （204号 $\mu$ S is noted.

Firstly, an example is given to illustrate how to measure the scanning tunneling shot noise spectra (STSNS) by the CryoSTM-TIA in CryoSTM. In this example, the sample is “clean Pb(111) surface” as mentioned in Ref.[6],and the STM tip is coated with Pb. The tip and sample in the cryogenic region at $2 . 2 ~ \mathrm { K }$ is a superconductor-insulatorsuperconductor (SIS） system. The Fano factors of the SIS system have been predicted theoretically and verified by the experiments [6]. Same experiments can be done for calibrating the proposed CryoSTM-TIA. By using the CryoSTM-TIA, the STSNS measurements for the SIS system can be performed as follows.

Fig.2(a) in Ref.[6] shows several measured differential conductance curves $G _ { \mathrm { J } } = G _ { \mathrm { J } } ( V )$ corresponding to the different junction resistances of $R _ { \mathrm { N } }$ ，where $V$ is the voltage bias on TJ and $V \in [ - 5 \mathrm { ~ m V } , 5 \mathrm { ~ m V } ]$ . From these curves,one is selected whose minima are higher than $0 . 1 ~ \mu \mathrm { S }$ in $[ - V _ { \mathrm { m } } , V _ { \mathrm { m } } ]$ and $V _ { \mathrm { m } }$ is slightly larger than $2 \Delta / e$ ，where $\Delta$ is the superconducting gap energy of the sample. Fig.10 is the schematic curve of the scanning tunneling differential conductance spectra of the SIS system,in which $V _ { \mathrm { m } } = 4 . 8 ~ \mathrm { m V }$ . In $[ - V _ { \mathrm { m } } , V _ { \mathrm { m } } ]$ , the domain of $V$ where $G _ { \mathrm { J } } ( V ) < G _ { \mathrm { h } } = 1 ~ \mu \mathrm { S }$ is denoted as $D _ { \mathrm { { V } } }$ ,i.e.

$$
D _ { \mathrm { V } } = \{ V | - V _ { \mathrm { m } } \leq V \leq V _ { \mathrm { m } } , G _ { \mathrm { J } } ( V ) < G _ { \mathrm { h } } \} .
$$

Only the DC bias is applied by BMS,and the scanning tunneling current spectra $I = I ( V )$ $\mathbf { \nabla } V ~ \in ~ D _ { \mathrm { V } } ,$ ） can be obtained as mentioned in Section 6.1. The corresponding range of （20 $I = I ( V )$ is denoted as $D _ { \mathrm { I } }$ ： $\begin{array} { r } { I = \int _ { 0 } ^ { V } G _ { \mathrm { J } } ( V ) d V } \end{array}$ and $G _ { \mathrm { J } } ( V ) > 0 . 1 ~ \mu \mathrm { S }$ in $( 0 , V _ { \mathrm { m } } ]$ ，s0 $I > 1 0 0$ pA as $V > 1 ~ \mathrm { m V }$ ：

![](images/de69f28a71a921cf96bc4e3b2474407e06ade9b3a4351333ebde1f688a3d1e83.jpg)  
Figure 11: Schematic curve of a scanning tunneling noise current PSD $S _ { \mathrm { I } } = S _ { \mathrm { I } } ( f , V )$ ata fixed $V$ . Its corner frequency $f _ { \mathrm { c } }$ is noted. 1/f noise can be considered as zero at frequency $f _ { \mathrm { m } }$ ：

For the SIS system， the tunneling noise current PSD is denoted as $S _ { \mathrm { I } } = S _ { \mathrm { I } } ( f , V )$ （ $V \in D _ { \mathrm { V } }$ ， $f \in [ 1 0 \ \mathrm { H z } , 3 0 0 \ \mathrm { k H z } ] ,$ ).Fora fixed $V$ in $D _ { \mathrm { { V } } }$ , a schematic curve of $S _ { \mathrm { I } } = S _ { \mathrm { I } } ( f , V )$ 0 $f \in \left[ 1 0 \ \mathrm { H z } , 1 0 0 \ \mathrm { k H z } \right] \mathrm { \Omega }$ ） is shown in Fig.11, in which the corner frequency $f _ { \mathrm { c } }$ is noted. For the SIS system [6],if the wite noise $S _ { \mathrm { { I w } } } ( V )$ is much larger than the fliker noise at frequency $f _ { \mathrm { m } }$ and $f _ { \mathrm { m } } < 3 0 0 ~ \mathrm { k H z }$ ， $S _ { \mathrm { { I w } } } ( V )$ can be measured accurately by the proposed CryoSTMTIA at $f _ { \mathrm { m } }$ ： $S _ { \mathrm { { I w } } } ( V )$ performs as the shot noise when $| V | > 4 k _ { \mathrm { B } } T / e$ 0 $k _ { \mathrm { B } } T / e \approx 0 . 1 9 ~ \mathrm { m V }$ （204号 for $T = 2 . 2 \textrm { K }$ ).With the measured $I = I ( V )$ 0 $V \in D _ { \mathrm { V } }$ )，the STSNS $S _ { \mathrm { I s } } = S _ { \mathrm { I s } } ( I ) \approx$ （204号 $S _ { \mathrm { I w } } ( V ( I ) )$ （ ${ \cal I } \in { \cal D } _ { \mathrm { I } }$ ， $\vert V \vert > 4 k _ { \mathrm { B } } T / e )$ can be obtained. The Fano factor $F$ can be extracted by $F = S _ { \mathrm { I s } } / ( 2 e | I | )$ . For the SIS system in Ref.6], it should be obtained that $F = 2$ in $[ 4 k _ { \mathrm { B } } T / e , 2 \Delta / e ]$ and $F = 1$ in $[ 2 \Delta / e , V _ { \mathrm { m } } ]$

In the following,how to obtain the white noise current PSD is detailed.

For the CryoSTM-TIA,as Eq.(4.8), its equivalent input noise current PSD $\overline { { i _ { \mathrm { i n } } ^ { 2 } } } ( f , V )$ is əxpressed as the sum of four components,

$$
\overline { { \dot { \iota } _ { \mathrm { i n } } ^ { 2 } } } ( f , V ) = \overline { { \dot { \iota } _ { \mathrm { A } } ^ { 2 } } } ( f ) + 4 k _ { \mathrm { B } } T / R _ { \mathrm { F } } + ( 2 \pi f ) ^ { 2 } C C _ { \mathrm { I J } } \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) + \big [ 1 / R _ { \mathrm { F } } + 1 / R _ { \mathrm { J } } ( V ) \big ] ^ { 2 } \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) .
$$

Before approaching the tip to the sample in the CryoSTM, $R _ { \mathrm { J } }$ can be considered as infinity and $C _ { \mathrm { { J } } }$ as $0$ . The equivalent input noise current PSD of the CryoSTM-TIA with $R _ { \mathrm { J } } = \infty$ （204 and $C _ { \mathrm { { J } } } = 0$ is

$$
\overline { { i _ { \mathrm { i } } ^ { 2 } } } ( f ) = \overline { { i _ { \mathrm { A } } ^ { 2 } } } ( f ) + 4 k _ { \mathrm { B } } T / R _ { \mathrm { F } } + ( 2 \pi f ) ^ { 2 } C _ { \mathrm { A I } } C _ { \mathrm { I } } \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) + \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) / R _ { \mathrm { F } } ^ { 2 } .
$$

$\overline { { i _ { \mathrm { i } } ^ { 2 } } } ( f )$ is irrelevant to the tip-sample TJ junction. And,

$$
\begin{array} { r l } & { \delta ( f , V ) = \overline { { i _ { \mathrm { i n } } ^ { 2 } } } ( f , V ) - \overline { { i _ { \mathrm { i } } ^ { 2 } } } ( f ) } \\ & { \qquad = \{ [ 1 / R _ { \mathrm { F } } + 1 / R _ { \mathrm { J } } ( V ) ] ^ { 2 } - 1 / R _ { \mathrm { F } } ^ { 2 } \} \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) + ( 2 \pi f ) ^ { 2 } ( C + C _ { \mathrm { I } } ) C _ { \mathrm { J } } \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) . } \end{array}
$$

$\overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f ) = 2 \overline { { e _ { \mathrm { H } } ^ { 2 } } } ( f )$ as Eq.(4.4) mentioned in Section 4.1, and $\overline { { e _ { \mathrm { H } } ^ { 2 } } } ( f )$ decreases monotonically in $[ 1 0 \ \mathrm { H z } , 3 0 0 \ \mathrm { k H z } ]$ [8,9]. As listed in Table 6, $( 1 / R _ { \mathrm { F } } + 1 / R _ { \mathrm { J } } ) ^ { 2 } e _ { \mathrm { A } } ^ { 2 }$ is only $0 . 5 ~ \mathrm { ( f A ) ^ { 2 } / H z }$ at $1 0 ~ \mathrm { k H z }$ and $\mathrm { 0 . 1 4 ~ ( f A ) ^ { 2 } / H z }$ at $1 0 0 ~ \mathrm { k H z }$ ，for $R _ { \mathrm { F } } = 1$ G $\Omega$ and $R _ { \mathrm { J } } = 1 ~ \mathrm { M } \Omega$ According to the parameters listed in Table 6, it is estimated that $( 2 \pi f ) ^ { 2 } ( C + C _ { \mathrm { I } } ) C _ { \mathrm { J } } \overline { { e _ { \mathrm { A } } ^ { 2 } } } ( f )$ is less than 0.05 (fA)²/Hz in $[ 1 0 ~ \mathrm { k H z } , 1 0 0 ~ \mathrm { k H z } ]$ and less than 0.14 $\mathrm { \Omega ( f A ) ^ { 2 } / H z }$ in $[ 1 0 0 ~ \mathrm { k H z } , 3 0 0 ~ \mathrm { k H z } ]$ ： And, $R _ { \mathrm { J } } > 1 ~ \mathrm { M } \Omega$ for $V \in D _ { \mathrm { V } }$ discribed by Eq.(6.5). Therfore, in Eq.(6.8), $\delta ( f , V ) <$ （20 $\mathrm { 0 . 6 \ ( f A ) ^ { 2 } / H z }$ in $\lfloor 1 0 \ \mathrm { k H z } , 3 0 0 \ \mathrm { k H z } \rfloor$ ·

For $V \in D _ { \mathrm { V } }$ and $f \in [ 1 0 ~ \mathrm { k H z } , 3 0 0 ~ \mathrm { k H z } ]$ , the sum of the tunneling noise current PSD $S _ { \mathrm { I } } ( f , V )$ and the equivalent input noise current PSD of the CryoSTM-TIA $\overline { { i _ { \mathrm { i n } } ^ { 2 } } } ( f )$ is amplified to the output noise voltage PSD $S _ { \mathrm { s u m } } ( f , V )$ by the CryoSTM-TIA with the transimpedance gain $A _ { \mathrm { i } } ( f )$ expressed as Eq.(6.1). And $S _ { \mathrm { s u m } } ( f , V )$ can be measured with the spectrum analyzer. Before approaching the tip to the sample in the CryoSTM, the output noise voltage PSD with $R _ { \mathrm { J } } = \infty$ and $C \mathrm { { J } } = 0$ is $S _ { \mathrm { s u } } ( f )$ ： $S _ { \mathrm { s u } } ( f ) = | A _ { \mathrm { i } } ( f ) | ^ { 2 } i _ { \mathrm { i } } ^ { 2 } ( f )$ and it can be measured in advance by the spectrum analyzer. Hence,

$$
[ S _ { \mathrm { s u m } } ( f , V ) - S _ { \mathrm { s u } } ( f ) ] / | A _ { \mathrm { i } } ( f ) | ^ { 2 } = S _ { \mathrm { I } } ( f , V ) + \overline { { i _ { \mathrm { i n } } ^ { 2 } } } ( f , V ) - \overline { { i _ { \mathrm { i } } ^ { 2 } } } ( f ) = S _ { \mathrm { I } } ( f , V ) + \delta ( f , V ) .
$$

The noise measurements can be performed at $f _ { \mathrm { m } }$ ，where $S _ { \mathrm { I } } ( f _ { \mathrm { m } } , V ) = S _ { \mathrm { I w } } ( V )$ and $\delta ( f _ { \mathrm { m } } , V ) \ < \ 0 . 6 \ ( \mathrm { f A } ) ^ { 2 } / \mathrm { H z }$ In $D _ { \mathrm { { V } } }$ ，when $V \mathrm { ~ > ~ } 1 \mathrm { ~ m V }$ ， $I > 1 0 0$ pA and $| V | > 4 k _ { \mathrm { B } } T / e$ （204号 （ $T = 2 . 2 \textrm { K }$ [6])．Therefore, $S _ { \mathrm { I w } } ( V ) \approx S _ { \mathrm { I s } } ( V ) = S _ { \mathrm { I s } } ( V ( I ) ) = 2 F e | I | > F ( 3 2 ~ \mathrm { ( f A ) ^ { 2 } / H z } )$ ： Even if $F = 0 . 5$ , it is estimated $S _ { \mathrm { I s } } > 1 6 ~ \mathrm { ( f A ) ^ { 2 } / H z }$ ,which is 25 times higher than $\delta ( f _ { \mathrm { m } } , V )$ Therefore, from Eq.(6.9),

$$
S _ { \mathrm { I w } } ( V ) \approx \frac { S _ { \mathrm { s u m } } ( f _ { \mathrm { m } } , V ) - S _ { \mathrm { s u } } ( f _ { \mathrm { m } } ) } { | A _ { \mathrm { i } } ( f _ { \mathrm { m } } ) | ^ { 2 } } .
$$

By Eq.(6.1O)，with the scanning tunneling current spectra obtained in experiments as mentioned in Section 6.1, the STSNS $S _ { \mathrm { { I s } } } ( I )$ ( ${ \cal I } \in { \cal D } _ { \mathrm { I } }$ ）can be obtained in experiments.

If the frequency of $f _ { \mathrm { m } }$ cannot be determined in advance,at which the flicker noise component in the tunneling noise is far less than the white noise, the upper limit of the corner frequencies of the tunneling noises must be measured first. For the SIS system, as an example, selecting some typical values in $D _ { \mathrm { { V } } }$ ， such as $V = V _ { 1 }$ ， $V _ { 2 }$ (in Fig.10), and $V _ { \mathrm { m } }$ ， measure the tunneling noise current PSD $S _ { \mathrm { I } } ( f )$ at the selected $V$ as mentioned above,and then fit the curve of $S _ { \mathrm { I } } ( f )$ to find its corner frequency $f _ { \mathrm { c } }$ ,as illustrated in Fig.11. Taking （204号 $f _ { \mathrm { m } }$ is 10 times higher than the maximum of the above corner frequencies or more, the tunneling noises measured at $f _ { \mathrm { m } }$ can be considered as the obtained white noises.

For the shot noise measurements on a normal metal sample, the domain $[ - V _ { \mathrm { m } } , V _ { \mathrm { m } } ]$ can be selected with a large interval. For example,in Ref.[3], the shot noise measurements on Au(111) are performed,in which the maximum value of $R _ { \mathrm { J } }$ is adjusted to $\mathrm { ~ 1 ~ G } \Omega$ ，and （204号 $V _ { \mathrm { m } } = 5 0 0 ~ \mathrm { m V }$ ，so that $I$ can reach up to 5Oo pA.Therefore,it is more convenient to calibrate the CryoSTM-TIA by measuring the shot noise on Au(111).

In order to verify the existence of the Majorana bound states (MBSs) in condensed matters, the shot noise characteristics of the MBSs in the different device structures have been predicted in theroies [13,14,15,16,17,18]. However, such measurements have been never made, since there is no appropriate measuring equipment available up to now. Some of these predictions are made for multi-terminal device structures [16,17,18]. For the multi-terminal devices, if the shot noise is measured with a CryoSTM, the tunnel junction of the CryoSTM needs to be designed as a component of the device, which is not easy in experiments. For the 2-terminal device structures [14,15], it can be designed as a device with the tip as one end and sample as the other end. The corner frequency of the tunneling noise in this structure is usually quite small, and the shot noise measurements may be easily achieved. Recently, many evidences of the conductance measurements show the MBS may be generated in the flux vortex of the iron-based superconductors [35]. For that work, the existence of the MBS may be further verified by measuring the shot noise,which is obviously meaningful. The shot noise measurements with the proposed CryoSTM-TIA may be performed as follows. As the iron-based superconductor sample is placed at O.55 K with a magnetic field of 2.5 T, the topological energy gap is about $1 . 8 ~ \mathrm { m e V }$ . Several measured differential conductance spectral curves corresponding to the different tip-sample distances have been shown in Fig.3(A) of Ref.[35]. Select the curve whose minimum differential conductance is about $0 . 0 5 ~ \mu \mathrm { S }$ , take the interval $[ - V _ { \mathrm { m } } , V _ { \mathrm { m } } ]$ as $[ - 2 \ \mathrm { m V } , 2 \ \mathrm { m V } ]$ ,and find the domain $D _ { \mathrm { { V } } }$ by the method mentioned above with Eq.(6.5). The corner frequency $f _ { \mathrm { c } }$ of the tunneling noise can be found by the method mentioned above with Eq.(6.9),and the frequency $f _ { \mathrm { m } }$ can be determined. At $f _ { \mathrm { m } }$ , the STSNS can be obtained in experiments with Eq.(6.10). Because of the 2.5 T magnetic feld, the STMLC-Amp mentioned in Ref.[2, 3] cannot be used for the measurements in Ref.[35]. For the measurements in Ref.[35], the DC tunneling current $I$ is as small as 5O pA,and the corresponding shot noise for the MBS may be $e | I |$ of8 $\mathrm { ( f A ) ^ { 2 } / H z }$ ，while the inherent noise of STM-LC-Amp is as high as 7 $\mathrm { 0 0 ~ ( f A ) ^ { 2 } / H z }$ , so it is impossible to measure so low the shot noise for the tunneling current in Ref.[35].

Before 2Ol8, shot noise in mesoscopic systems are studied by the tunnel junction devices without STM involving. It is impossible to study shot noise in-situ in atomic scale, such as a single molecule, a single molecular magnet, a defect in atomic scale, etc. If CryoSTM is used to measure the noise in quantum systems, the impossible as mentioned above may become possible. By the CryoSTM, the shot noise in-situ measurements in atomic scale may be achieved with very high resolution in energy and space distributions,as well as with the excellent tunability of temperature, magnetic field and tunneling conditions. For the proposed CryoSTM-TIA, the simulation and calculation results show its inherent noise is very low, while its gain and bandwidth can be still quite large. Therefore, the accuracy of the tunneling shot noise measurements can be dramatically improved by using the CryoSTM-TIA. The proposed CryoSTM-TIA may become a universal tool to meet the measurement needs for various quantum systems, such as Dirac semi-metal, Weyl semimetal, topological superconductor, topological insulator, and other quantum materials with novel quantum phenomena.

# 7Conclusions and outlooks

During the non-equilibrium transports in mesoscopic systems,the statistical information can be obtained by measuring shot noise. In this work,a low-noise high-gain largebandwidth transreimpedance amplifier (TIA） has been proposed to meet the needs of the shot noise measurements in the CryoSTM. In the CryoSTM, the TIA with the tip-sample component is called as CryoSTM-TIA. The core component of the proposed CryoSTM-TIA is a cryogenic Pre-Amp made of the low-noise low-power cryogenic CNRS-HEMTs. And, a special single power supply is used to ensure the stability and robustness of CNRS-HEMTs at low temperatures. The CryoSTM-TIA has a transimpedance gain of the magnitude of

G $\Omega$ ，with a bandwidth above $3 0 0 ~ \mathrm { k H z }$ . The equivalent input noise current PSD of the proposed CryoSTM-TIA $\overline { { i _ { \mathrm { i n } } ^ { 2 } } }$ is only 21 $\mathrm { ( f A ) ^ { 2 } / H z }$ at $1 0 0 ~ \mathrm { k H z }$ . The scanning tunneling current spectra $I = I ( V )$ and scanning tunneling differential conductance spectra ${ \cal G } _ { \mathrm { J } } =$ （204号 $G _ { \mathrm { { J } } } ( V )$ can be measured with the cryoSTM-TIA. In this work, it is detailed, by using the CryoSTM-TIA,how to measure the scanning tunneling noise current PSD $S _ { \mathrm { I } } = S _ { \mathrm { I } } ( f , V )$ and extract the scanning tunneling shot noise spectra $S _ { \mathrm { { I s } } } = S _ { \mathrm { { I s } } } ( I )$ for quantum systems in atomic scale. And,all of these spectra can be measured with very high accuracy. This CryoSTM-TIA can be used to investigate the properties of various quantum materials, such as high-temperature superconductors [4, 5], topological superconductors, topological insulators, etc. It can also be used to study various quantum effects, such as the Andreev reflection in atomic scale [6], the Kondo effect in a single molecular magnet [36],etc. Especially, it may be used to verify the existence of Majorana bound states, related to the realization of topological quantum computing.

In the future, any kinds of collaborations are welcome, and the funding will be applied to realize the proposed CryoSTM-TIA,based on the design in this work.

# Acknowledgment

This research did not receive any specific grant from funding agencies in the public, commercial, or not-for-profit sectors. We acknowledge stimulating discussions with Prof. FangHao Liang of Math School in Shandong Univ and Prof. Xing Liang of Math School in USTC.

# Declaration of competing interest

The authors declare that they have no known competing financial interests or personal relationships that could have appeared to influence the work reported in this paper.

# References

[1] Y.M. Blanter and M. Büttiker, Shot noise in mesoscopic conductors, Phys. Rep., 336 (2000) 166.https://doi.0rg/10.1016/S0370-1573(99)00123-4.   
[2] F.Massee，Q. Dong，A. Cavanna, Y. Jin，and M. Aprili, Atomic scale shotnoise using cryogenic MHz circuitry, Rev. Sci. Instrum.， 89 (2018) 093708. https://doi.org/10.1063/1.5043261.   
[3] K.M. Bastiaans, T. Benschop, D. Chatzopoulos, D. Cho, Q. Dong, Y. Jin, and M.P. Allan，Amplifier for scanning tunneling microscopy at MHz frequencies,Rev. Sci. Instrum.,89 (2018) 093709. https://doi.0rg/10.1063/1.5043267.   
[4] F. Massee, Y.K. Huang， M. S. Golden， and M. Aprili， Noisy defects in the high- $T _ { \mathrm { c } }$ superconductor Bi2Sr2CaCu2O8 $+ x$ ，Nat.Commun.， 10 (2019） 544. https://doi.0rg/10.1038/s41467-019-08518-1. [5] K.M. Bastiaans，D. Cho，T.Benschop，I. Battisti，Y. Huang，M.S. Golden, Q. Dong， Y. Jin2014， J. Zaanen， and M.P. Allan， Charge trapping and superPoissonian noise centres in a cuprate superconductor, Nat. Phys., 14 (2018) 1183. https://doi.0rg/10.1038/s41567-018-0300-z. [6] K.M. Bastiaansa,D. Cho, D. Chatzopoulos,M. Leeuwenhoek,C. Koks,and M.P. Allan,Imaging doubled shot noise in a Josephson scanning tunneling microscope, Phys.Rev. B,100 (2019) 104506. https://doi.org/10.1103/PhysRevB.100.104506.   
[7] A. van der Ziel, Noise in solid state devices and circuits, Wiley-Inter-Science, New York, (1986).   
[8] Y.X. Liang，Q. Dong，M.C. Cheng，U. Gennser，A. Cavanna，and Y. Jin， Insight into low frequency noise induced by gate leakage current in AlGaAsGaAs high electron mobility transistors at 4.2 K，Appl.Phys. Lett.， 99 (201l） 113505. https://doi.0rg/10.1063/1.3637054.   
[9] Y. Jin, Q. Dong, A. Cavanna, U. Gennser, L. Couraud, and C. Ulysse, Ultra-low noise HEMTs for deep cryogenic low-frequency and highimpedance readout electronics, 12th IEEE International Conference on Solid-State and Integrated Circuit Technology (ICSICT) (2014).   
[10] Y. Oreg and F.V. Oppen， Majorana zero modes in networks of Cooper-pair boxes: topologically ordered states and topological quantum computation， Annu. Rev. Condens. Matter Phys.，11 (2020) 397. https://doi.org/10.1146/annurev-conmatphys031218-013618.   
[11] S. Nadj-Perge, I.K. Drozdov, J. Li， H. Chen， S.J. Jeon, J.P. Seo，A.H. MacDonald， B.A. Bernevig， and A. Yazdani， Observation of Majorana fermions in ferromagnetic atomic chains on a superconductor， Science， 346 (2014） 602. https://doi.org/10.1126/science.1259327.   
[12] H. Zhang， et al.， Quantized Majorana conductance， Nature， 556 (2018） 74. https://doi.org/doi:10.1038/nature26142. H. Zhang et al.， Large zero-bias peaks in InSb-Al hybrid semiconductor-superconductor nanowire devices， Preprint at https://arxiv.org/abs/2101.11456 (2021).   
[13] C.J. Bolech and E. Demler, Observing majorana bound states in $p$ -wave superconductors Using Noise Measurements in Tunneling Experiments, Phys. Rev. Lett., 98 (2007)237002. https://doi.0rg/10.1103/PhysRevLett.98.237002.   
[14] A.Golub and B. Horovitz, Shot noise in a Majorana fermion chain, Phys. Rev. B, 83 (2011) 153415. https://doi.org/10.1103/PhysRevB.83.153415.   
[15] H. Soller and A. Komnik, Charge transfer statistics of transport through Majorana bound states, Physica E, 63 (2014) 99. https://doi.org/10.1016/j.physe.2014.05.020.   
[16] H.F. Lü, Z. Guo, S.S. Ke, Y. Guo,and H.W. Zhang, Shot noise as a measure of the lifetime and energy splitting of Majorana bound states, J. Appl. Phys.117 (2015) 164312. http://dx.doi.org/10.1063/1.4919748.   
[17] D.E. Liu， M. Cheng， and R.M. Lutchyn， Probing Majorana physics in quantum dot shot noise experiments， Phys. Rev. B, 91 (2015) 081405. https://doi.org/10.1103/PhysRevB.91.081405.   
[18] J. Manousakis, C. Wille, A. Altland,R. Egger, K. Flensberg, and F. Hassler, Weak Measurement Protocols for Majorana Bound State Identification, Phys. Rev. Lett., 124 (2020) 096801. https://doi.org/10.1103/PhysRevLett.124.096801.   
[19] TINA-TI is SPICE-based analog simulation program produced by Texas Instruments Inc. https://www.ti.com/tool/TINA-TI.   
[20] C.J. Chen， Introduction to scanning tunneling microscopy， Oxford Univ. Press, (1994).   
[21] Data sheet of FEMTO DE-DLPCA-200 TIA https://www.femto.de/images/pdfdokumente/de-dlpca-200.pdf.   
[22] J.S. Xu, Y.S. Dai,and D.Abbott，A complete operational amplifier noise model: analysis and measurement of correlation coefficient, IEEE Trans. Circuits Syst. I, 47 (2000) 420. https://doi.0rg/10.1109/81.841928.   
[23] Z.H. Qian, Study on noise models algorithms and matrix descriptions for integrated circuits, J Northeast Norm.Univ, 35(2003) 41.   
[24] Supplimental file 1.   
[25] R.A. Christian， J. Berthold, S. Jacob,E. Matthias,E. Markus,A. Joachim，and K. Klaus, Sensing the quantum limit in scanning tunnelling spectroscopy, Nature Commun.7 (2016) 13009. https://doi.org/10.1038/ncomms13009.   
[26] B. Michel,L. Novotny, and U. Diirig, Low-temperature compatible I-V converter, Ultramicrosc0py, 42-44 (1992) 1647. https://doi.org/10.1016/0304-3991(92)90499-A.   
[27] Y.J. Song， A.F. Otte， V. Shvarts， Z.Y. Zhao, Y. Kuk, S.R. Blankenship, A. Band， F.M. Hess， and J.A. Stroscio， Invited Review Article:A 10 mK scanning probe microscopy facility， Rev. Sci. Instrum.， 81 (2010） 121101. https://doi.0rg/10.1063/1.3520482.   
[28] J.F. Ge， M. Ovadia， and J.E. Hoffman， Achieving low noise in scanningtunnelingspectroscopy，Rev.Sci. Instrum.，90(2019） 101401. https://doi.org/10.1063/1.5111989.   
[29] S. Franco, Design with Operational Amplifiers and Analog Integrated Circuits, McGraw-Hill Companies, Inc (2002).   
[30] Data sheet ofBFT93 BJT https://www.nxp.com.cn/docs/en/datasheet/BFT93_CNV.pdf.   
[31] A suitable TEC device https://www.analogtechnologies.com/document /Micro_TEC_C   
[32] Supplimental file 2.   
[34] Supplimental file 3.   
[35] D.F. Wang, L.Y. Kong, P. Fan, H. Chen, S.Y. Zhu, W.Y. Liu, L. Cao, Y.J. Sun, S.X. Du,J. Schneeloch,R.D. Zhong, G.D.Gu, L. Fu, H. Ding,and H.J. Gao,Evidence for Majorana bound states in an iron-based superconductor, Science, 362 (2018) 333. https://doi.org/10.1126/science.aao1797.   
[36] S.Cocklin and D.K. Morr, Scanning tunneling shot-noise spectroscopyinKondosystems, Phys. Rev. B, 100 (2019) 125146. https://doi.org/10.1103/PhysRevB.100.125146.