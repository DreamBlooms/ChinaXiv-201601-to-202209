# Design and Test of Magnetic Wall Decoupling for Dipole Transmit/Receive Array for MR Imaging at the Ultrahigh Field of 7T

Xinqiang Yan $\cdot$ Xiaoliang Zhang‘ Long Wei $\cdot$ Rong Xue

Received:11July 2014/Revised:26 September 2014/Published online:27 November 2014   
$\circledcirc$ Springer-Verlag Wien 2014

AbstractRadio-frequency coil arrays using dipole antenna technique have been recently applied for ultrahigh field magnetic resonance (MR) imaging to obtain the better signal-noise-ratio (SNR) gain at the deep area of human tissues.However, the unique structure of dipole antennas makes it challenging to achieve sufficient electromagnetic decoupling among the dipole antenna elements. Currently, there is no decoupling methods proposed for dipole antenna arrays in MR imaging. The recently developed magnetic wall (MW) or induced current elimination decoupling technique has demonstrated its feasibility and robustness in designing microstrip transmission line arrays,L/C loop arrays and monopole arrays.In this study,we aim to investigate the possibility and performance of MW decoupling technique in dipole arrays for MR imaging at the ultrahigh field of 7T.To achieve this goal, a two-channel MW decoupled dipole array was designed, constructed and analyzed experimentally through bench test and MR imaging. Electromagnetic isolation between the two dipole elements was improved from about $- 3 . 6$ dB(without any decoupling treatments） to $- 1 6 . 5 ~ \mathrm { d B }$ by using the MW decoupling method. MR images acquired from a water phantom using the MW decoupled dipole array and the geometry factor maps were measured,calculated and compared with those acquired using the dipole array without decoupling treatments. The MW decoupled dipole array demonstrated well-defined image profiles from each element and had better geometry factor over the array without decoupling treatments. The experimental results indicate that the MW decoupling technique might be a promising solution to reducing the electromagnetic coupling of dipole arrays in ultrahigh field MRI, consequently improving their performance in SNR and parallel imaging.

# 1 Introduction

Ultrahigh magnetic resonance imaging (MRI) could provide a high signal-noiseratio（SNR） and a high contrast in human imaging [1-1O].Dipole arrays,which have a simple structure,have been proposed to increase the $B _ { 1 }$ field penetration and SNR gain in the deep area of human head or body and have demonstrated promising capability in human imaging at ultrahigh magnetic fields [11,12]. It is known that the electromagnetic (EM) coupling among coil elements is critical to SNR and parallel imaging performance [13-19] of coil arrays. Due to the unique structure of the dipole antennas,the traditional decoupling methods,such as element overlapping[20] and L/C decoupling network [21-28],face challenges and are not readily feasible for dipole transmit/receive (transceiver） arrays. Insufficient decoupling among dipole array elements in current dipole array designs has negatively impacted the imaging performance. The recently developed magnetic wall (MW) or induced current elimination (ICE） decoupling technique has demonstrated its superior capability of decoupling resonant elements in various coil arrays, including microstrip transmission line(MTL)arrays [29-32],traditional $\mathrm { L } / \mathrm { C }$ looparrays [33- 35],and monopole arrays [36]. For the MW decoupling method,an independent resonator/antenna was used to eliminate the current induced in the resonant elements by EM coupling.This method does not need physical connection between coil elements and should be promising for dipole transceiver arrays.

In this study,we aim to test the feasibility and investigate the performance of the MW decoupling method in the dipole array.A two-channel MW decoupled dipole array was designed and constructed for 7T MR imaging.As a comparison, we also constructed a 7T dipole array without any decoupling treatments.Bench test, MR imaging and geometry factor results obtained from the two dipole arrays demonstrate that MW decoupling method is capable of obtaining a high degree of EM decoupling between dipole elements and provides enhanced imaging performance at the ultrahigh field of 7T.

# 2MaterialsandMethods

2.1 Design and Construction of the Two-Channel Dipole Array Without and With Magnetic Wall Decoupling Method

Figure 1 shows the photographs and sketches of the constructed two-channel dipole arrays without decoupling treatments and with the MW decoupling method.A simple dipole antenna is equal to 1/2 wavelength of the electromagnetic wave in the free space [37]. At $2 9 7 . 2 ~ \mathrm { M H z }$ ,the Larmor frequency of our 7T MRI scanner,the corresponding length of a simple dipole antenna is about $5 0 \ \mathrm { c m }$ ，which isa little longer and not suitable for most MRI applications.In this study,the length of each dipole was shortened by two series inductors (Ls,as shown in Fig.1c,d) to $2 6 ~ \mathrm { c m }$ which is suitable for human head MR imaging.Each series inductor was wound with a copper wire of four turns and $4 . 0 \ \mathrm { m m }$ in diameter.The distance between two dipole elements of each array is $7 \mathrm { c m }$ .Each dipole element was matched to $5 0 \ \Omega$ with a trimmer capacitor $\mathrm { { C m } }$ [12],and was tuned to $2 9 7 . 2 ~ \mathrm { M H z }$ by slightly changing the gap between the turns ofLs.Traditional $\mathrm { L } / \mathrm { C }$ trap circuits were applied to remove the possible “cable resonance” of each dipole element at the high frequency of $2 9 7 . 2 ~ \mathrm { M H z }$ ：

For the magnetic wall decoupled two-channel dipole array, an independent dipole antenna, referred to as the decoupling element, was symmetrically placed between the two dipole elements to reduce the EM coupling. The decoupling element had the same length as the dipole element and was shorted by a series inductor Ld, referred to as the decoupling inductor (Fig. 1d). The decoupling inductor was wound with a copper wire of three turns and $4 . 0 \ \mathrm { m m }$ in diameter. The resonance frequency of the decoupling element is about $4 0 0 ~ \mathrm { { M H z } }$ . All conductor strips described above were made of the $1 0 ~ \mathrm { m m }$ -wide copper tape (3 M, St,Paul, MN).

Figure 2 shows the position of the water phantom vs.dipole arrays.A cylindrical water phantom with an outer diameter of $1 6 ~ \mathrm { c m }$ and a length of $3 7 \ \mathrm { c m }$ was placed $2 . 5 \ \mathrm { c m }$ below the dipole arrays.The EM parameters of the water phantom were measured by a dielectric probe (DAK-12， Speag，Switzerland): conductivity $\sigma = 0 . 5 9 ~ \mathrm { S / m }$ ； relative permittivity $\varepsilon _ { \mathrm { r } } = 7 8$ ：

# 2.2 Bench Tests and MR Imaging Experiments

Scattering(S-）parameters,including reflection coefficient $( \mathbf { S } _ { 1 1 } )$ and transmission coefficient $( \mathsf { S } _ { 2 1 } )$ ，of the dipole elements with and without the MW decoupling method were measured with an Agilent E5O71C network analyzer.The reflection coefficient measurements were also used to calculate the coil's $\boldsymbol { Q }$ value.

To demonstrate the decoupling performance of the MW decoupling method for dipole arrays,gradient recalled echo (GRE) images and geometry factor maps on the water phantom using the two dipole elements with and without the decoupling element were measured, calculated and compared.The slice chosen for MR imaging was in the central transverse plane of the dipole elements. The imaging acquisition parameters were: flip angle $( \mathrm { F A } ) = 2 5 ^ { \circ }$ ， $\mathrm { T R } = \ 1 0 0 \ \mathrm { m s }$ $\mathrm { T E } = 1 0 ~ \mathrm { m s }$ ,field of view $\mathrm { ( F O V ) } = 2 5 0 \times 1 7 1 ~ \mathrm { m m } ^ { 2 }$ ,matrix $= 2 5 6 \times 1 7 6$ ，slice thicknes $\mathrm { \Delta } _ { \mathrm { { s s } } } = 5 ~ \mathrm { { m m } }$ ,bandwidth $= 3 2 0 ~ \mathrm { H z } /$ pixel, number of excitation $( \mathrm { N E X } ) = 1$ The MRI experiments were performed on a whole-body MRI scanner（7T MAGNETOM, Siemens Healthcare,Erlangen，Germany).During the experiments,one dipole element was used for both transmission and reception with the other one terminated with $5 0 { - } \Omega$ load. The geometry factor maps were calculated using an radio-frequency coil array design and analysis software Musaik (Speag, Switzerland).

![](images/63d122dd3ee70c440fa4649306b91146aa69d2a0a706f14aac3c326dff915e10.jpg)  
Fig.1Photographs and sketches of the two-channel dipole arrays without decoupling treatments (a and c)and with magnetic wall decoupling (b and $\mathbf { d }$ ）

![](images/5d2cfe4926a9367bede6874706bfc0df5681ac18ec2b5d85850d91e31fbda551.jpg)  
Fig.2Position of the dipole arraysvs.thewaterphantom

# 3 Results

# 3.1 Bench Test Results

The reflection coefficient $( \mathbf { S } _ { 1 1 } )$ of each dipole element is better than $- 2 0 ~ \mathrm { d B }$ ，as shown in Fig.3.For the dipole array without decoupling treatments， the transmission coefficient $\mathbf { S } _ { 2 1 }$ between two dipole elements was only about $- 3 . 6$ dB(Fig.3a). It is worth noting that no obvious peak split was observed even when the coupling achieved $- 3 . 6$ dB,which is unlike near-field coil such as loop or MTL coil. The average unloaded $\boldsymbol { Q }$ value $( Q _ { \mathrm { U L } } )$ and $\boldsymbol { Q }$ value loaded with water phantom $( Q _ { \mathrm { L } } )$ of a single element were about 13.3 and 9.5,respectively.

For the MW decoupled two-channel dipole array,the length of the decoupling element was chosen the same as the dipole elements $( 2 6 ~ \mathrm { c m } )$ .The transmission coefficient $\mathbf { S } _ { 2 1 }$ between the dipole elements could be reduced from $- 3 . 6$ to $- 1 6 . 5 ~ \mathrm { d B }$ ,as shown in Fig. 3b. The average $Q _ { \mathrm { U L } }$ and $\varrho _ { \mathrm { L } }$ of a single element were 48.1 and 29.2, respectively.Like the results of our previous work [36], the MW decoupled array exhibits higher $\boldsymbol { Q }$ value which might be due to the better decoupling performance and shielding effect of the decoupling element.

# 3.2 MR Images and Geometry Factor Maps

GRE images from each dipole element of the two-channel arrays were shown in Fig. 4.Figure 4a,b show the images from two coupled dipoles and the 1D profiles of the images.Figure 4c, d show the images from two MW decoupled dipoles and the 1D profile of the images. This significant decoupling effect,as obtained from the $\mathbf { S } _ { 2 1 }$ plots,could also be clearly observed in MR images.Well-defined image profiles of MW decoupled dipole array were obtained,indicating sufficient electromagnetic decoupling between the two elements.

![](images/92ffdcad7c337d85025d2e366e5fa7262d5103036558bbbc32c10d426c6df3a8.jpg)  
Fig.3Measured $\mathbf { S } _ { 1 1 }$ and $\mathbf { S } _ { 2 1 }$ plots vs.frequency of two dipole elements loaded with the water phantom. a Without decoupling treatments.b With the MW decoupling method.The isolation between the two dipole elements could be reduced from about $- 3 . 6 ~ \mathrm { d B }$ to about $- 1 6 . 5 { \mathrm { ~ d B } }$ ，indicating the strong decoupling capability of the MW decoupling method for the dipole array

![](images/84016c77ffa6d2fc2b69196c272581a0a78ce10c8685c09318b21c8ef816be00.jpg)  
Fig.4GRE images from each dipole element of the two-channel array without and with the magnetic wall decoupling.a Images from two coupled dipole elements.b Profile of the red dotted line of the images ina. The $\mathbf { S } _ { 2 1 }$ between the two dipole antennas was about $- 3 . 6$ dB,which indicates that about half of the signal power was coupled to the other element.The strong coupling between the two dipoles could also be observed from figures a andb.c Images from two MW decoupled dipole elements.dProfiles of the red dotted line of the images inc.Figures cand $\mathbf { d }$ show the strong decoupling performance between the two dipoles

Geometry factor maps with reduced factor (R) of two were shown in Fig.5.The average and maximum geometry factors of the coupled dipole array are 1.14 and 3.2,respectively; whereas the average and maximum geometry factor of the MW decoupled dipole array are 1.O8 and 2.4, respectively.Both average and maximum geometry factor results reveal that the MW decoupled array exhibits better parallel imaging ability,which can also be verified by the comparison of S-parameter results

2 88 1.5 as described above.In parallel imaging, the SNR of accelerated images is inversely proportional to the geometry factor [14]. Therefore,the results of the geometry factor measurements suggest that better quality-accelerated images can be achieved using MW decoupled transceiver dipole array over the array without decoupling treatments.

# 4 Discussions and Conclusions

The feasibility of magnetic wall decoupling technique for dipole coil arrays has been validated through bench tests and MR imaging experiments at the ultrahigh field of 7T in this study. The experimental results demonstrate that the transmission coefficient $\mathbf { S } _ { 2 1 }$ of the strongly coupled dipole elements is reduced from $- 3 . 6$ to $- 1 6 . 5$ dB using the MW decoupling technique. The EM isolation between the dipole elements might be further improved by optimizing the length of the MW decoupling element. Due to improved decoupling performance, the MW decoupled dipole elements demonstrate well-defined image profiles and improved geometry factors, indicating that better parallel imaging capability over the dipole array without decoupling treatments can be expected.This study has paved the way for designing MW decoupled multi-channel volume-typed dipole array for human MR imaging at ultrahigh fields.

AcknowledgmentsWe thank Mr.Lei Shi and Mr. Zihao Zhang from Institute of Biophysics, Chinese Academy of Sciences for their assistance on MR experiments.This work was supported in part by Chinese National Major Scientific Equipment R&D Project (grant number ZDYZ20l0-2),the Ministry of Scienceand Technology(MOST) of China (grant number 2012CB8255O0),the Chinese Academy of Sciences Strategic Priority Research Program (grant numbers XDB0201001,XDB02050001),National Natural Science Foundation of China Grant 512287O2 and National Institutes of Health (NIH) Grants RO1EB008699 andP41EB013598.

# References

1.E.Yacoub,A.Shmuel,J.Pfeufer,P.F.Van de Moortele,G.Adriany,P.Andersen,J.T.Vaughan,H. Merkle,K.Ugurbil,X.P.Hu,Magn.Reson.Med.45,588-594 (2001) 2.X.Zhang,K.Ugurbil,W.Chen,Magn.Reson.Med. 46,443-450 (2001)

4. X. Zhu, Y. Zhang,R. Tian,H.Lei,N. Zhang,X. Zhang,H. Merkle,K. Ugurbil,W. Cheng,Proc. Natl.Acad. Sci.USA100,4352 (2003)   
5.X. Zhang,K. Ugurbil,R. Sainati,W.Chen,IEEE Trans.Biomed. Eng.52,495-504 (2005)   
6. X. Zhang,X.H. Zhu,W.Chen, Magn. Reson.Med.53,1234-1239 (2005)   
7.G.C.Wiggins，A.Potthast,C.Triantafyllou,C.J.Wiggins,L.L.Wald,Magn.Reson.Med.54, 235-240 (2005)   
8.T.S.Ibrahim, C.MitchellP.Schmalbrock,R.Lee,D.W.Chakeres,Magn.Reson.Med.54,683-690 (2005)   
9.B.P.Thomas,E.B.Welch,B.D.Niederhauser,W.O.Whetsell Jr,A.W.Anderson,J.C.Gore,M.J. Avison,J.L.Creasy,J.Magn. Reson. Imaging 28,1266-1272 (2008)   
10. G.Chang, C.M.Deniz,S.Honig,K.Egol,R.R.Regatte,Y. Zhu,D.K. Sodickson,R. Brown,J. Magn. Reson. Imaging 39,1384-1393 (2014)   
11.A.J.Raaijmakers,O.Ipek,D.W.Klomp,C.Possanzini,P.R.Harvey,J.J.Lagendijk,C.A.van den Berg,Magn. Reson.Med.66,1488-1497 (2011)   
12.G.C.Wiggins,B. Zhang,R.Latanzi, G.Chen,D. Sodickson,in Proceedings of the 20th annual meeting of ISMRM,Melbourne,2012,p.541   
13.D.K. Sodickson,W.J. Manning,Magn.Reson.Med.38,591-603(1997)   
14.K.P.Pruessmann,M. Weiger, M.B. Scheidegger,P.Boesiger,Magn. Reson. Med. 42,952-962 (1999)   
15.M.A. Griswold,P.M.Jakob,R.M. Heidemann,M. Nittka,V. Jellus,J. Wang,B. Kiefer,A. Haase, Magn. Reson. Med.47,1202-1210 (2002)   
16. D.K.Sodickson,C.A.McKenzie,M.A. Ohliger,E.N.Yeh,M.D.Price,MAGMA13,158-163 (2002)   
17.Y.Pang,D.B.Vigneron, X. Zhang,Magn. Reson. Med.67,965-978 (2012)   
18. B.Wu,C.Wang,J.Lu,Y.Pang,S.J.Nelson,D.B.Vigneron, X. Zhang,IEEE Trans. Med. Imaging 31,183-191 (2012)   
19.B.Wu, X. Zhang,C.Wang,Y.Li,Y.Pang,J.Lu,D.Xu, S.Majumdar, S.J.Nelson,D.B.Vigneron, Magn.Reson.Med.68,1332-1338 (2012)   
20.P.B.Roemer,W.A.Edelstein,C.E.Hayes,S.P.Souza, O.M.Muellr,Magn.Reson.Med.16, 192-335 (1990)   
21.X.Z. Zhang,A.Webb, J.Magn. Reson.170,149-155 (2004)   
22.R.G.Pinkerton,E.A. Barberi,R.S. Menon, Magn. Reson. Med.54,499-503 (2005)   
23.B.Wu,P. Qu, C.Wang,J. Yuan,G.X. Shen,Magn. Reson. Eng.31B,116-126 (2007)   
24.B.Wu,C.Wang,R.Krug,D.A. Kelley,D.Xu,Y.Pang,S.Banerjee,D.B.Vigneron,S.J.Nelson,S. Majumdar,X. Zhang,IEEE Trans.Biomed.Eng.57,397-403 (2010)   
25.B.Wu,X. Zhang,P.Qu,G.X. Shen,J.Magn.Reson.182,126-132 (2006)   
26.B.Wu,X. Zhang,P.Qu, G.X. Shen,Magn. Reson. Imaging 25,418-424 (2007)   
27. Z. Zuo,J.Park,Y.Li,Z.Li, X. Yan, Z. Zhang,Y.Zhuo,Z.H. Cho,X.J. Zhou,R. Xue,in Proceedings of the 20th annual meeting of ISMRM,Melbourne,2012,p.2804   
28.X.Yan, C.Ma,L. Shi,Y. Zhuo,X. Zhou,L.Wei,R. Xue,Appl.Magn.Reson.45,437-449 (2014)   
29.Y.Li,Z.Xie,Y.Pang,D.Vigneron,X. Zhang,Med.Phys.38,4086-4093(2011)   
30.Z. Xie,X. Zhang,in Proceedings of the 16th annual meeting of ISMRM,Toronto,2008,p. 2972   
31.Z Xie,X Zhang,in Proceedings of the l6th annual meeting of ISMRM,Toronto,2008,p.1068   
32.X Yan,X Zhang,CMa,L Wei,R Xue,in Proceedings of the 22nd annual meeting of ISMRM,Milan, 2014,p. 1309   
33.X.Yan,X. Zhang,B.Feng,C.Ma,L.Wei,R.Xue,IEEE Trans.Med.Imaging (2014: doi:10.1109/ TMI.2014.2313879,[Epub ahead of print])   
34. X.Yan, X. Zhang, C. Ma,L. Wei,R. Xue,in Proceedings of the 22nd annual meeting of ISMRM, Milan,2014,p.1306   
35.X.Yan,X.Zhang,C.Ma,L.Wei,R.Xue,in Proceedings of the 22nd annual meeting of ISMRM, Milan,2014,p.1322   
36.X.Yan,X. Zhang,L.Wei,R.Xue,Quant.Imaging Mag.Surg.4(2),79-86 (2014)   
37.J.D.Kraus,R.J.Marhefka,Antennas: For All Applications,Third Edition (McGraw-HillPublishers, New York,2001)