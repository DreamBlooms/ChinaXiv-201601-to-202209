# Design of A W-Band Four-Channel DualPolarization Waveguide Slot Antenna

Xi Guo Key Laboratory of Microwave Remote Sensing National Space Science Center, CAS Beijing, China whatnoyeah@163.com

Hao Luo, Hou-jun Sun School of Information and Electronics Beijing Institute of Technology Beijing, China 552190410@qq.com

Abstract—The W-band full-polarization radar detection system is in need of a new type of antenna feed with good performance.The waveguide slot array antenna,has the advantages of low profile,high radiation efficiency,easy access to high gain.It has been become the research emphasis in the field of millimeter wave detection.In ordertosatisfy theneed ofdeveloping complete polarization radar detection system,a W-band fourchannel dual-polarization waveguide slot antenna is designed.The results of the simulation and optimization tests show that,the antenna has outstanding technical characteristics in double polarization.The antenna gain is higher than 13dB,and the cross-polarization level lower than -34dB.The bandwidth below VSWR 1.5is better than 2.8GHz.High isolation ofover 50dB is achieved between different polarization input ports. (Abstract)

Keywords- W-band;dual-polarization antenna; fourchannel feeding structure; waveguide slot array(key words)

# I. INTRODUCTION

Due to significant dielectric losses in millimeterWave band, inevitable electromagnetic wave attenuation alongtransmissionlines, andlowefficiencyof conventional array antenna fed by microstrip in high frequency region [1]，which can no longer meet the technical requirements of high gain and wide band in millimeter-wave band. The millimeter-wave detection system is in urgent need of a new type of antenna in the application of millimeter-wave band.

The waveguide slot antenna has high radiation efficiency，because it does not suffer from dielectric losses.It also has the advantages of low profile,low transmission losses，and easy access to high gain.The Waveguide slot antenna is widely used in radar antenna system thanks to its features of narrow beam and low side lobe.In recent years,Ando & Hirokawa Lab in Tokyo Institute of Technology has been studying ways to improve the performance of waveguide slot antenna [2]-[8].By using full cooperate-feeding structure and cross-shaped radiating slots,researchers have been able to operate waveguide slot array antenna in the dualpolarization mode in the 6O-GHz band and as antenna it is quite eligible [8].

Beijing key laboratory of millimeter wave and terahertz technology has been working on W-band fullpolarization radar detection system.We already used horn antenna as the feed of W-band dual-polarization Cassegrain antenna. The horn antenna feed has four mutually independent apertures, which are linearly polarized subarrays of rotational symmetry.It has the ability of synthesizing any kind of polarization wave instantaneously.Due to the test results,the Cassegrain antenna gain is higher than 36dB in $9 3 ~ \mathrm { G H z }$ band. To improve the system performance further,we use the waveguide slot antenna as the feed of Cassegrain antenna. We hope that we could take advantage of the high performance of the waveguide slot antenna.

Inorder to realize the instantaneousfullpolarization operation and effective extraction of the target's multi-polarization information,we propose a four-channel feeding structure,and combine it with $2 { \times } 2$ radiating element as the entire structure of the antenna. HFSS simulation results show that this type of dualpolarization antenna has outstanding characteristics,and it could satisfy the feed demand of Cassegrain antenna.

# II. ANTENNACONFIGURATION

![](images/854ab3d09b2eb20608c618e76ee2c22013af828fd5c83bccb3677bf590b9b890.jpg)  
Figure 1．Antenna structure

Horizontalpolarizationwaveandvertical polarization wave are fed into antenna structure by their feeding waveguide respectively.Due to the special set of feeding structure,two polarization waves form a pair of orthogonal magnetic fields in cross-shaped coupling slot. The waves are then transmitted into the radiating element located above. $\mathrm { T E } _ { 1 0 }$ and $\mathrm { T E } _ { 0 1 }$ mode are excited by the two polarization waves in radiating element, which eventually radiate into the free space through the cross-shaped radiating slot.

![](images/fc6e6a9c79d2da1fcf38761ba920030cb241174c1fb9a021ca87d6ac7500d185.jpg)  
Fig.1 shows the antenna structure,which can be divided into two parts: four-channel feeding structure and radiating element.   
Figure 2. Four-channel feeding structure

Fig. 2 shows the four-channel feeding structure. The size of standard rectangular waveguide is WR-10. The four-channel feeding structure consists of two horizontal polarization feeding waveguides,two vertical polarization feeding waveguides,four feeding coupling slots,two waveguide transmission layers and a crossshaped coupling slot.

Thefeedingstructuresetstwokindsof polarization ports on the different layers.Two horizontal polarization feeding ports are placed in the first layer, and two vertical polarization feeding ports are placed in the second layer. Two kinds of polarization feeding ports only transmit dominatemode, $\mathrm { T E } _ { 1 0 }$ mode. Horizontal polarization wave is fed by horizontal polarization waveguide,and transmitted into horizontal polarization waveguidetransmission layer through feeding coupling slot. Then it's coupled into vertical polarizationwaveguidetransmission layerbythe horizontal polarization coupling slot above horizontal waveguidetransmissionlayer.Similarly，vertical polarization wave is coupled into vertical polarization waveguide transmission layer. Two polarization waves form a pair of orthogonal magnetic field components in vertical polarization waveguide layer, under crossshaped feeding slot.

Based onthe $\mathrm { T E } _ { 1 0 }$ mode magneticfield distribution, the longitudinal magnetic field is very weak on the center of rectangular waveguide.Therefore,the vertical polarization wave wouldn't be coupled into horizontal feeding waveguide beneath through feeding coupling slot. The high isolation between two kinds of polarization feedingports is achieved.Finally,two kinds of polarization waves are transmitted into radiating element through cross-shaped coupling slot.

#

#+

Fig.3 shows the radiating element structure.It consists of a cross-shaped radiating slot,a quadrupleridged waveguide and four cross-shaped coupling slots. The cross-shaped radiating slot and the quadruple-ridged waveguide share the same structural shape, which ensure the maximum radiation efficiency.Rotationally symmetry structure is adopted on the quadruple-ridged waveguide.This special structure makes sure that the electromagnetic energy could be distributed equally to four cross-shaped radiating slots， and the feeding amplitude could be kept consistent. Therefore, two types of polarization could have the same characteristics.

The cross-shaped coupling slot couples the two types of orthogonal polarization waves into quadruple-ridged waveguide,in which $\mathrm { T E } _ { 1 0 }$ and $\mathrm { T E } _ { 0 1 }$ mode are exited. The direction of the electric and magnetic fields of these two modes are both orthogonal,as is shown in Fig. 4. To realize the dual-polarization mode， the cross-shaped radiating slot is formed by a pair of orthogonal rectangular slots,each of which chooses its respective mode, $\mathrm { T E } _ { 1 0 }$ or $\mathrm { T E } _ { 0 1 }$ mode.Due to the orthogonality of two modes,low cross-polarization level is achieved.

![](images/0525ad84937be5bff543bd0ad04c3318ecfffec0df68bf8ac85d210a94521224.jpg)  
A．Four-channel feeding structure   
Figure 4.Magnetic field distribution of $\mathrm { T E } _ { 1 0 }$ and $\mathrm { T E } _ { 0 1 }$ mode

The radiating element structure has already given outstanding performance in the $6 0 – \mathrm { G H z }$ band [8].Due to the principle of frequency scaling used in frequencyindependent antennas,as we change the model size and workingfrequencyin thesameproportion， the performance of antenna would not change.This means that we can reduce the antenna model size from 6OGHz to 94GHz in the same proportion,in order to determine the initial parameters.Thus，furthersimulation and optimization of the antenna could be carried out.

# III. SIMULATION AND OPTIMIZATION

# A.Simulation steps

The simulation and optimization of antenna could be divided into the following steps:

(1) Optimize the radiating element structure; (2) Optimize the four-channel feeding structure; (3） Combine optimized radiating element and four-channel feeding structure asthe entire antenna structure; (4)Adjust the antenna structure parameter's values according to laws of simulation and optimization.

# B.Optimization methods

The key method of optimization is parameter sweep analysis providedby the stimulation software ofHFSS: by sweeping the parameters one at a time while the others remain unchanged,we are able to observe and record their respective influence on the antenna's performance and thus adjust certain structures to optimize the antenna's performance.

To realize a uniform excitation in neighboring radiatingslots, theelectromagneticfield inthe quadruple-ridged waveguide has to be symmetric.Itcan be achieved by propagating the dominant mode and cutting off the higher-order modes generated by the coupling slots.When the quadruple-ridged waveguide under the radiating slots is sufficiently high or low,the higher-order modes could be cut off[8]. The attenuation of $\mathrm { ~ E ~ }$ and its constant $\mathfrak { a }$ of the TEmn modes through the coupling slots are expressed by(1) and (2):

$$
E = E _ { \mathrm { { 0 } } } \exp ( - \alpha t _ { c } )
$$

![](images/36630f0b18c207591ea190d1d4c904f648f038aa379b473198da9dc7424faed0.jpg)  
Figure 5.Return losses of feeding ports

$$
\alpha = \sqrt { \left( \frac { m \pi } { l _ { c } } \right) ^ { 2 } + \left( \frac { n \pi } { w _ { c } } \right) ^ { 2 } - k ^ { 2 } }
$$

where,tc,lc,and wc are the height,length and width of the quadruple-ridged waveguide,respectively.k is the wave number in free space.In fact, the length and width of the quadruple-ridged waveguide are the same, because rotationally symmetry structure is adopted.

We choose the length and height of the quadrupleridged waveguide,and the spacing between radiating slots as the main optimization parameters.Then sweep analyses of each parameters are finished by HFSS. Based on the effects of parameters sweep on the characteristics of the antenna,the final structure is determined.

![](images/8406e0750d8e3f638e10db5165467cd681d3df2065a0a5a77d106fa319d761c5.jpg)  
Figure 6.Isolation between different polarization feeding ports

![](images/295527ecb08f66094d9ca2ee15e11592e9a797e1124b6657f41954cca053fc43.jpg)  
Figure 7．Radiation pattern

The results of the simulation and optimization tests are as follows: the peak of horizontal polarization gain is $1 3 . 5 4 \mathrm { d B }$ ，the width of 3dB beam is $4 2 . 3 ^ { \circ }$ ，and crosspolarization level lower than -34dB;the peak of vertical polarization gain is 13.55dB,the width of 3dB beam is $4 2 . 2 ^ { \circ }$ ，cross-polarization level lower than -35dB. The average level of the two polarization's side lobe islower than -14dB.The bandwidth of horizontal polarization is 2.89GHz below VSWR1.5,and 3.5GHzbelow VSWR 2.The bandwidth of vertical polarization is 3.35GHz below VSWR 1.5,and 4.14GHz below VSWR 2. High isolation above 5OdB is achieved between different polarization feeding ports. When the two kinds of polarization feeding ports work together, the antenna has the ability of synthesizing any kind of polarization wave

Main parameters of optimized antenna,as are showed in Table 1.

TABLEI. MAINPARAMETERSOFANTENNA   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Length of cross-shaped radiating slot</td><td>1.9mm</td></tr><tr><td>Width of cross-shaped radiating slot</td><td>0.96mm</td></tr><tr><td>Length of cross-shaped coupling slot 1</td><td>2mm</td></tr><tr><td>Width of cross-shaped coupling slot 1</td><td>0.5mm</td></tr><tr><td>Length of cross-shaped coupling slot 2</td><td>1.9mm</td></tr><tr><td>Width of cross-shaped coupling slot 2</td><td>0.4mm</td></tr><tr><td>Height of cross-shaped coupling slot</td><td>1.2mm</td></tr><tr><td>Length of horizontal polarization coupling slot</td><td>1.72mm</td></tr><tr><td>Width of horizontal polarization coupling slot</td><td>0.8mm</td></tr><tr><td>Length of vertical polarization coupling slot</td><td>1.74mm</td></tr><tr><td>Width of vertical polarization coupling slot</td><td>0.8mm</td></tr><tr><td>Length of horizontal polarization transmission waveguide</td><td>7mm</td></tr><tr><td>Length of vertical polarization transmission waveguide</td><td>6.96mm</td></tr><tr><td>Height of the quadruple-ridged waveguide</td><td>1.5mm</td></tr><tr><td>Spacing between radiating slots</td><td>2.44mm</td></tr></table></body></html>

# V. CONCLUSION

In our design，we propose a W-band four-channel dual-polarization waveguide slot antenna,which will be employed as the feed of Cassegrain antenna in the Wband full-polarization radar detection system. The antennamakespossibleaninstantaneousfullpolarization operation and effective extraction of the target's multi-polarization information.The results of the simulation and optimization tests show that, the peaks of two kinds of polarization gain are higher than 13dB, cross-polarizationlevelslowerthan $\mathbf { - } 3 2 \mathrm { d } \mathbf { B }$ .The bandwidth of two kinds of polarization is larger than $2 . 8 \mathrm { G H z }$ below VSWR 1.5.High isolation of above 5OdB is achieved between different polarization feeding ports.

# REFERENCES

[1] E.Levine,G.Malamud,S.Shtrikman,and D.Treves.A study of microstrip array antennas with the feed network [J].IEEE Trans.Antennas Propag.,vol.37,no.4,pp.426-434,Apr.1989.   
[2] Y.Kimura,Y.Miura,T.Shirosaki,T.Taniguchi,Y.Kazama,J. Hirokawa,M.Ando,and T.Shirouzu．A low-cost and very compact wireless terminal integrated on the back ofa waveguide planar array for $2 6 ~ \mathrm { G H z }$ band fixed wireless access (FWA) systems [J].IEEE Trans.Antennas Propag.,vol.53,no. 8,pt.1,pp.2456-2463,Aug.2005.   
[3] S.Park,Y.Tsunemitsu,J.Hirokawa,andM.Ando.Centerfeed single layer slotted waveguide array [J].IEEE Trans.Antennas Propag.,vol.54,no.5,pp.1474-1480,May 2006.   
[4] S.Fujii,Y.Tsunemitsu,G.Yoshida,N.Goto,J.Hirokawa,and M.Ando.Partially corporate feed using E-plane coupler in a single-layer slotted waveguide array [R].IEICE Tech.Rep., AP2007-150,Jan.2008.pp.163-168.   
[5] Y.Miura,J.Hirokawa,M.Ando.Bandwidth of a four-aperture element for a double-layer corporate-feed hollow-waveguide slot array [C].Antennas and Propagation Society International Symposium,2009.   
[6]M.Ando,Y.Tsunemitsu,M.Zhang,J.Hirokawa,and S.Fujii. Reduction of long line effects in single-layer slotted waveguide arrays with an embedded partially corporate feed[J].IEEE Trans. Antennas Propag.,vol.58,no.7,pp.2275-2280,Jul.2010.   
[7] Y.Miura,J.Hirokawa,M.Ando,Y. Shibuya,and G.Yoshida. Double-layer full-corporate-feed hollow waveguide slot array

antenna in the 6O-GHz band [J]. IEEE Trans.Antennas Propag., vol.59,no.8,pp.2844-2851,Aug.2011. [8]D.Kim,M.Zhang,J.Hirokawa,and M.Ando.Design and fabrication of a dual-polarization waveguide slot array antenna with high isolation and high antenna efficiency for the $6 0 ~ \mathrm { G H z }$ band [J]. IEEE Trans.Antennas Propag.，vol. 62,no.6,pp. 3019-3027,Jun.2014.