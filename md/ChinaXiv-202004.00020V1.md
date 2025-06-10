# Printed Organic Transistors-based Impedance Biosensor

Qi Huang 1†, Kai Jin $^ { 1 , \dag }$ , Yukun Huang ², Zhe Liu ³, Linrun Feng ³, Xiaojun Guo ² and Hanbin Ma 1,\*

1 CAS Key Laboratory of Bio-Medical Diagnostics, Suzhou Institute of Biomedical Engineering and Technology, Chinese Academy of Sciences,Suzhou, 215163,China; E-mail: huangqi@sibet.ac.cn (Q.H.); kj902@acxel.com.cn (K.J.)   
2 Department of Electronic Engineering, Shanghai Jiao Tong University, Shanghai, China; x.guo@sjtu.edu.cn (X.G.); wjh1056@sjtu.edu.cn (Y.H.)   
3 Hangzhou LinkZill Technology Co., Ltd., Hangzhou, China; linrun.feng@linkzill.com (L.F.); zhe.liu@linkzill.com (Z.L.)

† These authors contributed equally to this work.

\*Author to whom correspondence should be addressed; E-mail: mahb@sibet.ac.cn; Tel.: +86-512-6958-8081; Fax: +86-512-6958-8081.

Abstract: Electrochemical impedance biosensors measure the impedance varies of the solution during the biochemical process，so it can realize label-free biological detection.However， the biological signal to be detected is very weak, thus requiring signal amplification circuit. Printed organic thin film transistor(OTFT) has many advantages such as low cost, flexible bending, biocompatibility, which is suitable for biological detection.This work built up amplification circuit for electrochemical impedance test based on OTFT,different concentrations of phosphate buffer solution (PBS) used as test samples were measured with the above circuit. The results show that OTFT-based circuit has a good implementation of signal amplification, which lay a foundation for the application of printed OTFT in the electrochemical impedance biosensors.

Keywords: electrochemical impedance biosensors; OTFT; impedance test; signal amplification circuit

# 1.Introduction

With the development of biological detection technology, biosensors like bioluminescent sensor are towards the trend of high sensitivity，selective and stability[1],and this fluorescent-based biosensors can be specifically designed to accommodate various applications like clinical medicine, food safety and environmental testing.However, in the fast diagnostic and point of care (PoC) applications, the low cost and user-friendly control characteristics of the sensors may take more into consideration as long as they meet the basic detection requirement.Meanwhile,due to the complexity and cumbersome operation of the existing optical immunosensor system, it is difficult to meet the convenient and rapid detection demand in the daily detection field (food bacteria, pesticide residues, etc. to achieve specific applications[2]. It is an urgent problem to reduce the volume and operation complicity of the sensing system.

Electrochemical impedance testing is a method to analyze the electrode process dynamics, double layer and diffusion by measuring the impedance changes with the sine wave frequency. When applied as a biosensor, the characteristics of biological sample can be directly judged by the change trend and degree of the interface structure between biological electrodes and biological samples[3]. Electrochemical biosensor has the features of simple structure and label-free analysis, thus receiving more and more atention in the biological detection field worldwide[4-7]. The researchers respectively proposed and realized the application of impedance test in the major biological detection fields such as cell[8], protein[9,10],and nucleic acid[11]. However, mainstream bioimpedance test work is done by large desktop electrochemical analyzers or impedance test board with metal electrodes.The measured signal needs to go through a long wire and different types of connection interfaces before it can be imported into the signal amplifier and the back-end impedance analysis circuit. The parasitic noise brought by this transmission line greatly afects the accuracy and repeatability of biological test. Therefore, more and more teams are focusing on the miniaturization and integration of impedance biosensors.The Andreas Demosthenous team of University College London realized the design of programmable wide-band impedance sensor chip with the high integration of complementary metal oxide semiconductor (CMOS)[12], Arjang Hassbi's team of the University of Texas at Austin integrated a biological functionalization electrode array into a CMOS impedance chip and realized DNA sequencing using an impedance test array[13]. However, CMOS integrated biochip is unable to meet the market expectations for the manufacturing cost and detection throughput of biosensors like immunosensor.As the metal suitable for traditional CMOS process are mainly non-biological materials such as aluminum and copper,and it needs to be reprocessed to integrate gold and other biological functionalization electrodes into CMOS chips,the process is complex and the cost is greatly increased. Meanwhile, the main advantage of CMOS technology is high integration, which can save chip size and cost.However, the electrochemical electrode needs to meet a certain size to ensure the success and fault tolerance rate of electrode biological functionalization. In practical application, it is often hoped to increase the number of electrodes to carry out multi-channel, high-throughput array detection. These are contrary to the traditional concept of making CMOS integrated circuit (IC) smaller and more precise.

Thin film electronic devices have been widely used in large area flat panel display, photovoltaic[14],flexible and wearable electronics[15,16] and other fields.Printing film electronic is a method of making different materials on substrate and forming electronic devices by using printing technology.As an important branch of large area electronic circuits,it has attracted atention in various fields due to itsultra-low preparation threshold and low cost.In recent years，the performance of printed electronic devices has developed rapidly，especially the stability and functionalityof inkjet thin film transistors[17].They have the ability to further integrate and realize the system functions.In 2016,the team of TSE Nga Ng at the University of California, San Diego successfully prepared the reading circuit of memory capacitance by using the printed organic thin film transistor[18]. Also in 2016, the Sungjune Jung team of POSCO University of Science and Technology in South Korea and the Shizuo Tokito team of Yamagata University in Japan jointly reported the circuit composed of nine 3D NAND gates integrated by inkjet printing film electronic devices[19]. And specific sensors and systems based on printed OTFT have been reported in recent years[20-22].

To sum up, with the purpose of achieving portable test for the biosensor, this work applied the printed OTFT in the electrochemical impedance biosensor, considering that the complexity of the structure of fluorescent-based biosensor is greatly reduced by the unmarked electrochemical impedance method,and the preparation dificulty of impedance sensor can be reduced at the same time by combining the manufacturing technology of large area electronic circuit based on printed film device.Amplification circuit was built for electrochemical impedance test based on OTFT, PBS solution was used as test samples,the results show that OTFT-based amplification circuit could hence the detection sensitivity.Meanwhile,the impedance inferred from the circuit was compared with the electrochemical workstation,the consistence between them proved the stability of the sensor. This work lays a foundation for the application of printed OTFT in the electrochemical impedance biosensors.

# 2.Materialsand Methods

# 2.1.Impedance biosensor

A system diagram of the reported impedance biosensing system is shown in Figure la. The impedance sensor is composed of thin electrode electrodes and printed OTFT-based circuit. The biological sample under test was placed on the electrodes, and sensing signal was amplified by the

OTFT-based circuit directly. A function generator is used here to generate sinusoidal signal at various frequencies, and the amplified sensing output was recorded by an oscilloscope.

![](images/87f809196dc70a089a4e46e713197e884d8b7ce91101cf035ba86eacae5c144d.jpg)  
Figure 1. Composition of the impedance sensor: (a) System schematic; (b) Photo of electrode chip; (c) Photo of the OTFTs chip; (d) Dimension of the electrode chip; (e) Microscopic photo of an OTFT.

Electrodes were designed for test.Figure 1b shows a real photo of the electrode chip.The electrode chip consists of gold electrodes and a polymethylmethacrylate (PMMA) reservoir.After the slide was passed the standard cleaning procedure, a $5 0 \mathrm { n m }$ layer of gold was grown on the surface of the slide using magnetron sputtering. PMMA sheet whose thickness is $2 \mathrm { m m }$ was purchased from Mitsubishi of Japan. In this paper, we used a carbon dioxide laser to cut gold-plated glass slide to prepare electrodes, and cut PMMA to prepare a reservoir. Electrode size and acrylic shape size were designed through AutoCAD software, as shown in Figure 1d.The completed drawing was imported into the carbon dioxide laser control software. In order to process the metal electrodes, following parameters were adjusted: the distance between the laser head and the sample was $7 \mathrm { m m }$ ; the power of the laser was 8 W; the speed of the laser was set to $1 5 \mathrm { m m / s }$ 、After that, in order to cut the PMMA to obtain the reservoir, only the power needs to be changed to $2 0 ~ W$ . After the laser processing was completed, the gold electrodes and the cut PMMA were bonded together by ultraviolet (UV) glue.

Figure 1c shows the OTFTs used in the OTFT amplifier. The gate, source and drain are led out by contact pads respectively,so that extern electronic component can be connected to the OTFT to form an amplifier. Figure 1e is a microscopic enlargement photo of the OTFT.

OTFTs were prepared on large area by high throughput coating techniques. The fabricated OFET dies were cut from the large area of substrate.Since the cost per unit area of OFET technology is much lower,a relatively large contact pads can be designed in order to facilitate external connection. The OFET die and sensing electrodes can then be connected to the carrer substrate through prefabricated contacts and interconnects. Blend solution of small molecule organic semiconductor and polymer binder was deposited on photolith patterned fine resolution electrodes by a soft contact coating technique at a fast rate of $2 0 \mathrm { m m } / \mathrm { s }$ .Highly uniform crystalline channels were obtained with low sub-gap density of states over large area with well controlled contact induced crystallization. The OTFT device exhibits low voltage electrical characteristics,excellent bias stress stability and good uniformity for more than 1o0 devices[23].

# 2.2OTFT device and circuit parameters

The transfer and output characteristics curves of the printed OTFT used in the amplification circuit are presented in Figure 2a,b,respectively.It can be seen that the OTFT can be operated at a low operation voltage $( < 3 \mathrm { V } )$ with an ON/OFF ratio over six orders of magnitude.

A printed OTFT-based common source amplifier is shown in Figure2c. $C _ { 1 }$ is used for filtering the direct current (DC) bias from the input signal.The input is biased by a DC pre-set stage which is composed of two resistors, naming $R _ { 1 }$ and $R _ { 2 }$ . It is used to define the DC working points of the amplifier. The resistor $R _ { 3 }$ is used as the load of the common source amplifier for achieving a better gain. The capacitor $C _ { 2 }$ is used to remove the DC component of the output signal, thus extracting the alternating current (AC) signal. The resistor $R _ { 4 }$ is a divider resistance. The parameters of the componentused in the amplifierare listed in Table1.

Figure 2d shows the frequency response of the amplification circuit. At lower frequencies, the gain of the circuit is around 13 dB,which can be further increased by setting the quiescent DC operating point. The gain decreases at higher frequencies, which is caused by the parasitic overlap capacitance between drain, source and gate of the OTFT.The 3 dB bandwidth of the printed OTFT based amplification circuit is $1 \mathrm { K H z }$ ：

![](images/3098fcbdb8b8224c002aabd68288623810ebfcc307d401aac9a5ece36c9e2b50.jpg)  
Figure 2. Characteristics of tested OTFT and circuit: (a) Transfer characteristics curve of the OTFT; (b) Output characteristics curve of the OTFT;(c)OTFT amplification circuit; (d) Frequency characteristics curve of the OTFT based amplification circuit.

Table1.Parameters of components used in the amplification circuit on Figure2b.   

<html><body><table><tr><td>Component</td><td>R1</td><td>R2</td><td>R3</td><td>C1</td><td>C2</td><td>Vcc</td><td>VDD</td></tr><tr><td>Value</td><td>200KΩ</td><td>200KΩ</td><td>3000KΩ</td><td>10 μF</td><td>10 μF</td><td>-10V</td><td>-30V</td></tr></table></body></html>

# 3.Results and Discussion

# 3.1.OTFT sensor sensitivity curve and measured results

![](images/a2322ab540c74e761bb414066c959e39b75d6e5fe75d7fa67814e6f7a25ccb0f.jpg)  
Figure 3. Characteristics of PBS impedance sensor: (a) Bode plot of different PBS samples using electrochemical workstation; (b） Nyquist plot of different PBS samples using electrochemical workstation; (c) The sensitivity histogram of OTFT impedance sensor to diferent concentrations of PBS solution; (d) The output voltage signal of measured samples, with and without amplification.

The electrodes were tested with five diferent concentrations of PBS solution. Figure 3a shows the bode plot of different concentration PBS samples,Figure 3b shows the Nyquist plot of the measurement result.The impedance value of PBS solution decreases with frequency in the lower band, while retain constant in high frequency band. It indicates that the solution impedance shows capacitor characteristic in low frequency band,and pure electrical resistance characteristic in high frequency band.The tested samples show high impedance recognition in the high frequency region (10 KHz-1 MHz),however, the gain of amplifier in the above frequency region is relatively low. The frequency of excitation signal by the function generator should be selected considering both amplifier gain and impedance discrimination degree.This willbe further discussed in the following paragraph.

As mentioned above,the signal frequency selection of the function generator is vital in the system design. Sensitivity should combine gain of the circuit and impedance difference of the PBS solution under different frequencies. The voltage generated by the signal generator divided by the PBS impedance is defined as the unamplified coefficient, while the unamplified coefficient multiply by the gain of the amplifier is defined as the amplified coefficient.The difference of the slope between the amplified coeficient and the unamplified coefficient curves under different concentrations at the specific measured frequency is calculated as the sensitivity difference. The sensitivity difference at the five measured frequencies are calculated therefore.Figure 3c shows the sensitivity difference value with and without amplification.1 KHz was chosen as the measured frequency for its maximum sensitivity difference,meanwhile,itfellinto the3dB bandwidth ofthe amplifier.The value of divider resistance $R _ { 4 }$ is chosen as the average value between the maximum and minimum of tested samples impedance at $1 \mathrm { K H z }$

Figure3d compares the unamplified output voltage signal with amplified signal. It indicates the amplifier can boost the sensitivity for PBS concentration measurement.

# 3.2Calculationof tested samples impedance

The samples impedance can be obtained by electrochemical workstation. It can be regarded as a standard value for the accuracy guarantee of the instrument. The solution impedance can also be deduced from the circuit and data in the experiment.The calculation of tested samples impedance based on the experiment circuit and data is illustrated in this part.

Figure 4 shows the smal-signal equivalent circuit of the common source amplifier in this work. The symbol $Z _ { t }$ represents the tested samples impedance, $g _ { m }$ is the transconductance, $R _ { d s }$ is channel-length modulation resistor. Actually,the AC impedance between gate and source should be considered,as the capacitance efect becomes obvious in the high frequency region. The impedance between gate and source is represented by $Z _ { g s }$ in the circuit. Frequency characteristics of $Z _ { g s }$ by using electrochemical workstation were measured，while the bias voltage of $V _ { g s }$ is $- 5 \mathrm { ~ V ~ }$ .The corresponding AC impedance of $Z _ { g s }$ at different frequencies can be obtained as a result (see Figure S1 in the Supplementary).

![](images/bcc27eef3727f4d7dd2c1c302ecac89ccb89adc0ce6ab58fb95a06a473735f0f.jpg)  
Figure 4. Smal-signal equivalent circuit of the experimental circuit.

The tested samples impedance calculation process is as follows:

$$
\dot { V } _ { \iota } = \dot { V } _ { Z t } + \dot { V _ { g s } } ,
$$

where $\dot { V } _ { \iota }$ is the voltage of the signal by the function generator, $\dot { V _ { Z t } }$ is the voltage across the electrodes contained with PBS solution, $\dot { V _ { g s } }$ is the voltage across the parallel resistances of $R _ { 4 } , R _ { 1 } ,$ $R _ { 2 } , Z _ { g s } . \dot { V _ { g s } }$ can be obtained by:

$$
\dot { V _ { g s } } = \dot { V } _ { o } / \dot { A _ { v } } ,
$$

where $\dot { V _ { o } }$ is the output voltage recorded by the oscilloscope, $\dot { A _ { v } }$ is the gain of the amplifier. The current through $Z _ { t }$ is equal to the total current through $R _ { 4 } , R _ { 1 } , R _ { 2 }$ and $Z _ { g s } ,$ then the following equation is established:

$$
\dot { V _ { Z t } } / Z _ { t } = \dot { V _ { g s } } / \big ( R _ { 4 } / / R _ { 1 } / / R _ { 2 } / / Z _ { g s } \big ) ,
$$

by simultaneous Eq.(1), (2) and (3), the tested samples impedance can be deduced:

$$
| Z _ { t } | = \left| \dot { V } _ { i } - V _ { o } ^ { \cdot } / \dot { A } _ { v } \right| / \left| V _ { o } ^ { \cdot } / \dot { A } _ { v } \right| \ast \big ( R _ { 4 } / / R _ { 1 } / / R _ { 2 } / / Z _ { g s } \big ) .
$$

Meanwhile, the voltage on the resistance of $R _ { 4 }$ under different tested sample was directly recorded by the oscilloscope on the condition that the amplification circuit was not used.The impedance of $Z _ { t }$ can be deduced as Eq. (5) based on that the current through $Z _ { t }$ is equal to the current through $R _ { 4 }$ ：

$$
\left| Z _ { t } \right| = \left| \dot { V } _ { \imath } - \dot { V } _ { o } \right| / \left| \dot { V } _ { o } \right| \ast R _ { 4 } ,
$$

where $\dot { V _ { o } }$ is the voltage on the resistance of $R _ { 4 }$ recorded by the oscilloscope.

The impedance of the tested samples with and without amplification circuit was obtained based on the experimental data and the above equations. Figure 5 shows the impedance measurement results with, without amplification circuit and using electrochemical workstation. Itcan be sen there are relatively good consistency measurement results by these three methods, which indicate a good stability of the PBS solution impedance system.

![](images/0a59bbcec754e7a93d039d2a686d6ea10080928421157b57f9a5ff85fbfab4dd.jpg)  
Figure 5.Impedance measurement results with,without amplification and using electrochemical workstation.

# 4. Conclusions

Aprinted organic transistors-based impedance biosensor using printed OTFT-based amplification circuit was established in this work.Different concentrations of PBS solution used as tested samples were measured using the amplifier, the results show that OTFT-based amplification circuit can enhance the sensitivity of tested samples concentration measurement.Calculation of tested samples impedance with experiment circuit and data was conducted in the following work, the result indicates the system has a good impedance measurement stability. A common source amplifier based on printed OTFT was built in this work,further work needs to be done to apply the OTFT amplification impedance sensor in biological applications like electrochemical impedance immunosensors, considering the good features of printed OTFT.

Supplementary Materials: The following is available online, Figure S1: Frequency characteristics of $Z _ { g s }$ by using electrochemical workstation, while the bias voltage of $| \dot { V _ { g s } } |$ is $- 5 \mathrm { V }$

Author Contributions: Designed and performed the experiments, Q.H.andK.J.;Fabrication of OTFTs,X.G. Y.H.,Z.L.and L.F.; writing-review and editing,all authors; supervisor, H.M. Allauthors have read and agreed to the published version of the manuscript.

Acknowledgments: This research was funded by National Natural Science Foundation of China, grant number 61701493.

Conflictsof Interest: The authors declare no conflict of interest.

# References

sensing platform for hyaluronidase activity detection based on Si QDs/HA-δ-FeOOH nanoassembly. Biosens.Bioelectron. 2020,150,111928.   
2. Ma, H.; Li, J.; Cheng, X.; Nathan, A. Heterogeneously integrated impedance measuring system with disposable thin-film electrodes. Sens. Actuator B-Chem. 2015,211, 77-82.   
3. Jang, B.; Hassibi, A.J. Biosensor systems in standard CMOS processes: Fact or fiction? IEEE Trans. Ind. Electron. 2009,56, 979-985.   
4. Cimafonte,M.; Fulgione,A.; Gaglione,R.; Papaianni, M.; Capparelli, R.; Arciello,A.; Bolleti Censi, S.; Borriello, G.; Velotta,R.; Dell Ventura, B. Screen Printed Based Impedimetric Immunosensor for Rapid Detection of Escherichia coli in Drinking Water. Sensors 2020,20, 274.   
5. Malvano,F.; Pilloton, R.; Albanese,D.Label-free impedimetric biosensors for thecontrol of food safety-a review.Int. J. Environ. Anal. Chem. 2019,1-24.   
6. Shaikh，M.O.； Srikanth，B.； Zhu，P.-Y.； Chuang，C.-H. Impedimetric Immunosensor Utilizing Polyaniline/Gold Nanocomposite-Modified Screen-Printed Electrodes for Early Detection of Chronic Kidney Disease. Sensors 2019,19,3990.   
7. Jin, K.; Hu,S.; Su,Y.; Yang C.; Li,J;Ma,H.Disposableimpedance-based immunosensor array with directlaser writing platform. Anal. Chim. Acta 2019,1067, 48-55.   
8. Swisher, S.L.; Lin, M.C.; Liao,A.; Leeflang E.J.; Khan,Y.; Pavinatto,F.J.; Mann, K.; Naujokas,A.; Young, D.; Roy,S.Impedance sensing device enables early detection of pressure ulcers in vivo. Nat. Commun. 2015, 6, 6575.   
9. Peng, Y.; Zhang, D.; Li, Y.; Qi, H.; Gao,Q.; Zhang, C.Label-free and sensitive faradic impedance aptasensor for the determination of lysozyme based on target-induced aptamer displacement. Biosens.Bioelectron.2009, 25, 94-99.   
10.Sun,K.;Xia,N.; ZhaoL.;Liu,K.;Hou,W.;Liu,L.Aptasensors fortheselective detectionofalpha-syuclein oligomer by colorimetry, surface plasmon resonance and electrochemical impedance spectroscopy. Sens. Actuator B-Chem. 2017,245,87-94.   
11.Tang, D.; Yuan, R.; Chai, Y.; Dai,J.; Zhong, X.; Liu, Y. A novel immunosensor based on immobilization of hepatitis B surface antibody on platinum electrode modified coloidal gold and polyvinyl butyral as matrices via electrochemical impedance spectroscopy. Bioelectrochemistry 2004, 65,15-22.   
12.Valente, V.; Demosthenous, A. Wideband fuly-programmable dual-mode CMOS analogue front-end for electrical impedance spectroscopy. Sensors 2016,16,1159.   
13.Hassibi, B.; Vikalo,H.;Hassibi,A.Methodandapparatus fordetection,identification and quantificationof single-and multi-analytes in affinity-based sensor arrays. Google Patents: 2015.   
14.Hamakawa, Y.Thin-film solar cels: next generation photovoltaics and its applications; Springer Science & Business Media: 2013; Vol. 13.   
15.Nathan,A.; Ahnood,A.; Cole,MT; Lee, S. Suzuki,Y.; Hiralal,P.; Bonaccorso,F.; Hasan,T.; GarciaGancedo,L.; Dyadyusha,A.Flexible electronics: the next ubiquitous platform.Proc. IEEE 100.Special Centennial Issue 2012, 100,1486-1517.   
16.Dai, Y.; Chen, J.; Tian, W.; Xu,L.; Gao,S.A PVDF/Au/PEN Multifunctional Flexible Human-Machine Interface for Multidimensional Sensing and Energy Harvesting for the Internetof Things.IEEE Sens.J. 2020, 10.1109/JSEN.2020.2974096,1-1,doi:10.1109/JSEN.2020.2974096.   
17.Feng,L.;Jiang, C.;Ma, H.; Guo,X.; Nathan,A.Allink-jetprintedlow-voltageorganic field-eect transistors on flexible substrate. Org. Electron. 2016,38,186-192.   
18.Ng,T.N.; Schwartz, D.E.; Mei,P.; Kor, S.; Veres,J.; Broms,P.; Karlsson, C.Printed organic circuits for reading ferroelectric rewritable memory capacitors. IEEE Trans. Electron Devices 2016, 64,1981-1984.   
19.Kwon,J.; Takeda,Y.; Fukuda,K.;Cho,K.; Tokito,S.; Jung,S.Three-dimensional, inkjet-printedorganic transistors and integrated circuits with $1 0 0 \%$ yield,high uniformity,and long-term stability. ACs Nano 2016, 10, 10324-10330.   
20.Takeda,Y.; Hayasaka,K.; Shiwaku, R.; Yokosawa, K.; Shiba,T.; Mamada,M.; Kumaki, D.; Fukuda, K.; Tokito,S. Fabrication of ultra-thin printed organic TFT CMOS logic circuits optimized for low-voltage wearable sensor applications. Sci Rep 2016,6,1-9.   
21.Nketia-Yawson,B.; Jung, A.-R.; Noh, Y.; Ryu, G.-S.; Tabi G.D.; Lee, K.-K.; Kim,B.; Noh, Y.-Y. Highly sensitive flexible NH3 sensors based on printed organic transistors with fluorinated conjugated polymers. ACS Appl.Mater.Interfaces 2017,9,7322-7330.   
22. Shiwaku, R.; Matsui, H.; Nagamine, K.; Uematsu, M.; Mano,T.; Maruyama, Y.; Nomura,A.; Tsuchiya, K.; Hayasaka，K.； Takeda，Y. A printed organic amplification system for wearable potentiometric electrochemical sensors. Sci Rep 2018,8, 1-8.   
23. Huang, Y.; Song, Y.; Tang, Y.; Liu, Z.; Han,L.; Zhang, Q.; Ouyang, B.; Tang W.; Feng,L.; Guo, X. Solution Processed Highly Uniform and Reliable Low Voltage Organic FETsand Facile Packaging for Handheld Multi-ion Sensing. In Proceedings of 2019 IEEE International Electron Devices Meeting (IEDM); pp.18.15.11- 18.15. 14.