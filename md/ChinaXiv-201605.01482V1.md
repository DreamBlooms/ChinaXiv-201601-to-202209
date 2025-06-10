# Hybrid Monopole/Loop Coil Array for Human Head MR Imaging at 7 T

Xinqiang Yan $\cdot \cdot$ Long Wei $\cdot \cdot$ Rong Xue · Xiaoliang Zhang

Received:31 December 2014/Published online:4March 2015   
$\circleddash$ Springer-Verlag Wien 2015

AbstractThe monopole coil and loop coil have orthogonal radiofrequency (RF) fields and thus are intrinsically decoupled electromagnetically if they are laid out appropriately. In this study,we proposed a hybrid monopole/loop technique which could combine the advantages of both loop arrays and monopole arrays. To investigate this technique,a hybrid RF coil array containing four monopole channels and four loop channels was developed for human head magnetic resonance (MR) imaging at $7 \mathrm { T }$ .In vivo MR imaging and $\mathrm { \bf g }$ -factor results using monopole-only channels,loop-only channels and all channels of the hybrid array were acquired and evaluated. Compared with the monopole-only and loop-only channels,the proposed hybrid array has the higher signal-to-noise ratio (SNR) and better parallel imaging performance. Sufficient electromagnetic decoupling and diverse RF magnetic field $( \mathbf { B } _ { 1 } )$ distributions of monopole channels and loop channels may contribute to this performance improvement.From experimental results, the hybrid monopole/loop array has low g-factor and excellent SNR at both periphery and center of the brain, which is valuable for human head imaging at ultrahigh fields.

# 1 Introduction

Ultrahigh field (i.e., $7 \mathrm { T }$ and higher） magnetic resonance imaging(MRI) offers significant advantages of the higher signal-to-noise ratio (SNR)， better imaging contrast and higher spatial resolution [1-3]. However, radiofrequency (RF) design challenges associated with ultrahigh fields,such as enlarged electromagnetic coupling among the resonant elements and limited field diversity of array channel, are augmented. A variety of RF coil arrays for ultrahigh field MR applications, e.g., $L / C$ loop array [4-8],microstrip transmission line (MTL） array [9-14],monopole array[15] and dipole array [16],have been proposed and applied for human head imaging at the ultrahigh field of $7 \mathrm { T }$

The previous work of hybrid monopole/loop dual-tuned coil designs has demonstrated that monopole and loop have two orthogonal and intrinsically decoupled RF fields [17] at two different frequencies.If this decoupling property still holds at the same frequency,it will be much useful to build a mono-nuclear array with both monopole channels and loop channels for proton MR imaging. Owing to the increased number of independent receive channels,the hybrid array should promise better coil performance over monopole-only and loop-only arrays in terms of SNR and parallel imaging capability [18-21]. In designing parallel imaging arrays, it is desirable that each element has a unique $\mathbf { B } _ { 1 }$ field. It has been demonstrated that the monopole and loop have different $\mathbf { B } _ { 1 }$ profiles owing to different coil structures and current distributions,which might further improve the $\mathbf { g } .$ -factors and thus the parallel imaging performance of the hybrid monopole/loop array.

In this work,we proposed a hybrid monopole/loop array design technique for proton parallel MR imaging applications. This technique was validated by implementing an RF array containing four hybrid coil elements for human head imaging at $7 \mathrm { T }$ .Each hybrid coil element or block has a monopole channel and a loop channel, which are intrinsically decoupled.Bench tests and in vivo MR images of the hybrid monopole/loop array were obtained to demonstrate its feasibility and performance in ultrahigh field MRI. To investigate the benefits of the proposed technique,MR imaging，SNR and $\mathbf { g }$ -factor results of the hybrid array were also compared with those from monopole-only channels and loop-only channels.

# 2MaterialsandMethods

# 2.1 Construction of the Eight-Channel Monopole/Loop Hybrid Array

A volume-typed monopole/loop hybrid array containing four independent blocks was designed and constructed for human head imaging at $7 \mathrm { T }$ ，as shown in Fig.1.

Fig.1 Diagram of the monopole/loop array containing four hybrid elements. Monopoles were placed across the center of the loops,resulting in intrinsic decoupling performance between them. $M _ { i }$ and $L _ { i }$ 1 $\overset { \cdot } { \iota } = 1$ ,2,3 and4) represent the element numbering of monopoles and loops, respectively

Fig.2 Equivalent circuit of one hybrid element which consists of a monopole and a loop. $\mathbf { C _ { m _ { - } m } }$ （20 and $\mathbf { C _ { \mathrm { t \_ m } } }$ were used for the matching and tuning of the monopole；while $\mathbf { C } _ { \mathrm { m } \_ \mathrm { L } }$ and $\mathbf { C } _ { \mathrm { t } _ { - } \mathrm { L } }$ were used for the matching and tuning of theloop.Three fixed capacitors $( 3 . 3 ~ \mathrm { p F } )$ were distributed along the loop conductor to avoid the value of tuning capacitor $( \mathbf { C } _ { \mathrm { t } \_ \mathrm { L } } )$ being too small

![](images/13dba32935d57203e1b5c8c36dd948cc8c4f08e42ab7f07c7ef0d1c91970fff7.jpg)

Each block consists of a monopole channel and a loop channel, and the total channel number of this volume array is 8.The monopole was positioned across the center of the loop to ensure that the two have orthogonal RF fields and thus are intrinsically decoupled. $M _ { i }$ and $L _ { i }$ $( i = 1 , 2 , 3$ and 4) in Fig.1 represent the element numbering of monopoles and loops,respectively.

An acrylic tube with dimensions of $2 4 ~ \mathrm { c m }$ ID, $2 5 ~ \mathrm { c m }$ OD and $2 6 ~ \mathrm { c m }$ in length was used as the mechanical support for this coil array.Four monopoles ( $2 5 \ \mathrm { c m }$ in length)and four loops $( 9 \ \mathrm { c m } \ \times \ 9 \ \mathrm { c m }$ in dimension） were equally spaced along the circumference of the acyclic tube.An acrylic plate $( 4 0 \ \mathrm { c m } \times 4 0 \ \mathrm { c m }$ in dimension) with upper corners cut was used as the former for the ground, which is perpendicular to the acrylic tube. As shown in Fig. 2, trimmer capacitors $\mathrm { C _ { t \_ m } , C _ { m \_ m } , C _ { t \_ L } }$ and $\mathbf { C } _ { \mathrm { m } _ { - } \mathrm { L } }$ (Voltronics Corp.,Denville,NJ,USA) were used for tuning and matching for the monopole channel and loop channel [22]. Each loop has three fixed capacitors $( 3 . 3 \mathrm { p F }$ ，American Technical Ceramics Corp.，Huntington Station，NY，USA) distributed along the conductors.The chosen dimensions of loops ensure that the coupling between neighboring blocks can be ignored while keeping the imaging coverage acceptable.Monopoles and loops were made of $1 0 \mathrm { - m m }$ -wide and $5 \mathrm { - m m } \mathrm { - }$ wide copper tapes，respectively. The ground was made from adhesive-backed copper foil (3 M, St.Paul, MN,USA).

All coil elements or channels were matched to $5 0 \ \Omega$ and tuned to $2 9 7 . 2 ~ \mathrm { M H z }$ which is the Larmor frequency of the utilized $7 \mathrm { T }$ MRI system.RF traps were placed between cables and loop channels to avoid possible “cable resonance”at the high frequency of $2 9 7 . 2 ~ \mathrm { M H z }$ . It is worth noting that RF traps are not necessary for monopoles due to their instinct unbalanced structure.

# 2.2Bench Measurement and MR Imaging Experiment

Scattering (S-） parameters including reflection coefficient $( S _ { 1 1 } )$ and transmission coefficient $( S _ { 2 1 } )$ of the hybrid coil array were measured with a calibrated network analyzer (5O71C,Agilent Technologies Inc., CA,USA). The S-parameter results were recorded when the coils were loaded with human head. $S _ { 1 1 }$ measurement was also used to calculate the $\boldsymbol { Q }$ values.

In vivo human head MR images were obtained from a healthy human volunteer using the eight-channel hybrid coil array. The human MRI experimental protocol was approved by the local institutional review board (IRB),and the volunteer signed an informed consent form before the experiment. In the experiment, scans were conducted two times using four loop channels and four monopole channels separately. In each scan,four channels (monopole or loop) were operated by using an RF interface box and all unused channels were terminated with $5 0 { - } \Omega$ loads. The RF interface box is composed of a four-way power splitter,phase shifters,T/R switches and $5 0 – \Omega$ preamplifiers.The phase difference between adjacent coil elements was $9 0 ^ { \circ }$ .During the two scans,the positioning of the subject was carefully kept unchanged via the line markers made on the patient table.

The sequence used for MR imaging is gradient recalled echo (GRE). The imaging parameters were: flip angle $( \mathrm { F A } ) = 2 5 ^ { \circ }$ ， $\mathrm { T R } = 1 0 0 ~ \mathrm { m s }$ ， $\mathrm { T E } = 1 0 ~ \mathrm { m s }$ $\mathrm { F O V } = 2 0 0 \times 2 0 0 \mathrm { \ m m } ^ { 2 }$ ，matrix $= 2 5 6 \times 2 5 6 .$ ，slice thicknes $\mathrm { s } = 2 ~ \mathrm { m m }$ ，bandwidth $= 3 2 0 \ \mathrm { H z / p i }$ xel,number of excitation $( \mathrm { N E X } ) = 1$ . All imaging data were acquired on a $7 \mathrm { T }$ whole-body MRI scanner(MAGNETOM,Siemens Healthcare, Erlangen, Germany). To demonstrate the parallel imaging capability, $\mathbf { g }$ -factor maps and average $\mathbf { g }$ -factors in the sagittal plane were measured and calculated with a reduction factor $( R )$ of 2,3 and 4. The $\mathbf { g }$ -factor maps and average $\mathbf { g }$ -factorswere calculated using an RF coil array design and the analysis software Musaik(Speag, Switzerland).

# 3 Results

# 3.1Bench Test Results

Figure 3 shows the S-parameter matrix of the eight-channel hybrid array loaded with human head.Reflection coefficient $( S _ { 1 1 } )$ of each coil element was better than $- 2 5 { \mathrm { ~ d B } }$ ，indicating excellent matching performance. An average isolation between a loop and a monopole from the same block is $- 2 0 . 1$ dB,which verifies their intrinsic decoupling performance.Average isolation between a loop and a monopole from neighboring blocks is $- 1 5 . 2 ~ \mathrm { d B }$ ，and average isolations of neighboring loops and neighboring monopoles are $- 1 3 . 7$ and $- 1 3 . 4 ~ \mathrm { d B }$ ， respectively.These results demonstrate that the isolation between adjacent blocks is still acceptable even when no decoupling methods are employed. The average unloaded and loaded $\boldsymbol { Q }$ values of loop channels are 124 and 34,respectively, whereas the average unloaded and loaded Q values of the monopole channels are 9.4 and 3.1, respectively.

![](images/5835f63c912491f35109133e2ec0a89aa8e647dc9080978118b7850d88c28ea7.jpg)  
Fig.3 S-parameter matrix of the eight-channel hybrid monopole/loop array loaded with a healthy human head. The worst-case isolation between any two elements is -13.1 dB, as shown by the red arrow.The element numbering here corresponds to that shown in Fig.1 (color figure online)

# 3.2 MR Imaging Results

Figure 4 shows the combined images in different axial planes from all loop channels,all monopole channels and their combination. These imageswere reconstructed from raw data without using any image processing method and were shown with the same signal intensity scale.The combined method is rooted sum of squares (RSS).Axial images from loop channels have high signal intensities at the periphery,but these intensities decrease fast with depth.Thus,loops face difficulty when imaging the area located deeply in human tissues, e.g., the center of the brain. On the contrary, the intensities of images from monopole channels had higher signal intensity at the central area,which is consistent with previous work [15]. These results indicated that a combination of the loop channels and monopole channels, i.e.,the hybrid coil array，could provide high signal sensitivities at both the peripheral and central areas.Local SNR at the four peripheral areas and the central area of human brain were calculated and marked in red color in Fig.4. Compared with the loop-only array, the hybrid array had overall SNR gains of $2 4 - 2 6 ~ \%$ and central SNR gains of $8 9 - 1 0 8 ~ \%$ for different slices.

![](images/9cd4d088e05e1d34c4aab147121906bbc62ff3cbfed29b8d6b98f96494f7c7a3.jpg)  
Fig.4 Combined axial images from all loop channels (left column),all monopole channels (middle column)and their combination (right column).These images were combined with the RSS method and shown in the same signal intensity scale.Local SNR at peripheral and central areas of the brain were marked inred color in these images.As expected,loop channels have high SNR at the periphery,but quite low SNR at the center.With the help of monopole channels,the hybrid aray has almost double SNR at the center of the brain compared with the loop-only array

G-factor maps with $R$ of 2, 3,and 4 were calculated using the images from loop channels，monopole channels and all channels,as shown in Fig.5.Average $\mathbf { g }$ -factors were also calculated and marked in white color in Fig.5.At the high accelerate factor of 4,the average g-factor using monopole channels,loop channels and all channels were 1.52,1.65 and 1.23,respectively. These results demonstrated that the parallel imaging performance could be largely improved when using the hybrid design,i.e.，both the monopole channels and loop channels were utilized. Figure 6 shows the original and rate-4 accelerated images of human head in the sagittal plane. The accelerated images were reconstructed with generalized autocalibrating partially parallel acquisitions(GRAPPA） using the PULSAR toolbox [23]. In the reconstruction，32 autocalibration signal (ACS） lines were used.As shown in Fig.6,excellent quality images could still be obtained when reduction factoris as high as 4.

![](images/b823c9256793bf8e3959c4fbd18f0cba4f8a3af1368aaca85c5b25153a33f3f7.jpg)  
Fig.5 G-factor maps $\boldsymbol { R } = 2$ ，3and 4) calculated using the images from loop channels,monopole channels and allchannels in thesagittal plane.Averageg-factorsare marked inwhite color in theg-factor maps.The average g-factors of loop channels,monopole channels and all channels with $R$ of 4 are 1.52, 1.65,and 1.23,respectively.These results demonstrate that parallel imaging performance could be highly improved by using the hybrid monopole/loop array

![](images/eef36921f517c09682f2a41f5fc41d86f222101795e58106e025c3478eaa8b97.jpg)  
Fig.6 GRE images of human head in the sagital plane using the eight-channel hybrid array:a fully encoded image without acceleration;b accelerated image with rate-4 GRAPPA acquisition

# 4 Discussions and Conclusion

Both $L / C$ loop and monopole techniques have been successfully applied for human head RF coil array designs at ultrahigh fields.When the monopole was placed across the center of the loop,the two coils have orthogonal RF fields and thus were instinct EM decoupled. Based on this feature,we proposed a hybrid monopole/loop array concept in the study. This concept was realized by designing and implementing a head coil array containing four hybrid monopole/loop blocks at $7 \mathrm { T } .$ 、As expected,the coupling between the monopole and loop in the same block was better than $- 1 9 \ \mathrm { d B }$ at the frequency of $2 9 7 . 2 ~ \mathrm { M H z }$ ，indicating their instinct decoupling performance.

Compared with the monopole-only and loop-only arrays，the hybrid array provides improved SNR gain and better parallel imaging performance. As demonstrated in previous work [15] and this study，the loop array has higher SNR at the peripheral area, while the monopole array has higher SNR at the central area.Hence, the hybrid array promises complementary advantage to provide excellent SNR at the entire brain.With the hybrid technique,coil element numbers or channel numbers could be doubled without adding additional decoupling treatments,leading to reduced g-factors (Fig. 5) and thus superior imaging quality in fast imaging. Sufficient electromagnetic decoupling and different $\mathbf { B } _ { 1 }$ distribution between monopole element and loop elements should be another important factor to contribute to the improvement of SNR and parallel imaging performance.Besides the benefits of SNR and parallel imaging,the hybrid monopole/loop technique is also possible for building phased array coils with quadrature capability,which could potentially increase the transmit eficiency by reducing the excitation power [24, 25]. Furthermore,if the proposed hybrid array technique is used for RF shimming and parallel transmit (pTx） applications,the hybrid arrays promise additional degrees of freedom for the RF shimming or pTx due to increased independent transmit elements [26,27]，which could be advantageous to provide more homogeneous transmit field.

Due to the limitation of our RF interface,monopole channels and loop channels of the hybrid array were driven separately for imaging acquisition in this study, but they can be used simultaneously given that the coupling among any two channels was low.Note that the transmit field using only monopole channels or loop channels is not the same as that using all channels simultaneously. Therefore,images obtained in the study might be different from those acquired using all channels simultaneously. In addition, the proposed hybrid array could be operated in other ways that, for example, loop-only or monopole-only channels are used to transmit, while all channels are used to receive.Although the hybrid monopole/loop array in this study only contains four blocks,the number of block numbers could be extended to 8 or even more if appropriate decoupling schemes,e.g.,individual shielding [28] and magnetic wall decoupling [22,29-33],are applied to ensure sufficient decoupling between the blocks. It has been demonstrated that magnetic wall decoupling is capable of decoupling both loop and monopole arrays [22,32] and thus should be a promising approach to address the coupling issue of the proposed hybrid arrays.

AcknowledgmentsThis work was supported in part by the Chinese National Major Scientific Equipment R&D Project (Grant No.ZDYZ2010-2),the Ministry of Science and Technology of China Grant (2012CB82550O),the National Natural Science Foundation of China Grant (51228702)，the Chinese Academy of Sciences Grants (XDB02010001,XDB02050001) and National Institutes of Health (NIH) RO1EB008699.

# References

1.E.Yacoub,A.Shmuel,J.Pfeuffer,P.F.Van De Moortele,G.Adriany,P.Andersen,J.T.Vaughan,H. Merkle,K.Ugurbil,X.Hu,Magn.Reson.Med.45,588-594(2001) 2.J.T.Vaughan,M. Garwood,C.M.Collins,W.Liu,L.DelaBarre,G.Adriany,P.Andersen,H. Merkle,R.Goebel,M.B.Smith,K.Ugurbil,Magn.Reson.Med.24,24-30 (2001)   
3.X.Zhang,K.Ugurbil,W.Chen,Magn.Reson.Med.46,443-450 (2001)   
4.R.G.Pinkerton,E.A.Barberi,R.S.Menon,Magn.Reson.Med.54,499-503(2005)   
5.G.C.Wiggins,A. Potthast,C. Triantafyllou,C.J.Wiggins,L.L.Wald,Magn.Reson. Med.54, 235-240 (2005)   
6.V.Alagappan,J. Nistler,E.Adalsteinsson,K. Setsompop,U. Fontius,A. Zelinski, M. Vester, G.C. Wiggins,F.Hebrank,W.Renz,F.Schmitt,L.L.Wald,Magn.Reson.Med.57,1148-1158 (2007)   
7.N.I. Avdievich,Appl.Magn. Reson. 41,483-506 (2011)   
8.X.Yan,C.Ma,L.Shi,Y.Zhuo,X.J. Zhou,L.Wei,R.Xue,Appl.Magn.Reson.45,437-449 (2014)   
9.R.F.Lee,C.R.Westgate,R.G.Weiss,D.C.Newman,P.A.Bottomley,Magn. Reson.Med.45, 673-683 (2001)   
10.G.Adriany,P.F.Van de Moortele,F.Wiesinger,S.Moeller,J.P.Strupp,P.Andersen,C.Snyder,X. Zhang,W.Chen,K.P.Pruessmann,P.Boesiger,T.Vaughan,K.Ugurbil,Magn.Reson.Med.53, 434-445 (2005)   
11.B.Wu,X.Zhang,P.Qu,G.X. Shen,J.Magn.Reson.182,126-132 (2006)   
12.B.Wu,X. Zhang,P.Qu,G.X. Shen,Magn. Reson. Imaging 25,418-424 (2007)   
13.G.Adriany,P.F.V.De Moortele,J.Ritter,S.Moeller,E.J.Auerbach,C.Akgun,C.J.Snyder,T. Vaughan,K.Ugurbill,Magn. Reson.Med.59,590-597 (2008)   
14.G.Adriany,E.J.Auerbach,C.J.Snyder,A. Gozubuyuk,S.Moeller,J.Ritter,P.F.Van de Moortele, T.Vaughan,K.Ugurbil, Magn. Reson.Med.63,1478-1485 (2010)   
15.S.M. Hong,J.H.Park,M.K.Woo,Y.B.Kim,Z.H. Cho,Magn.Reson.Med.71,1944-1952 (2014)   
16.A.J.Raaijmakers,O.Ipek,D.W.Klomp,C.Possanzini,P.R.Harvey,J.J.Lagendijk,C.A.van den Berg,Magn.Reson.Med.66,1488-1497 (2011)   
17. X.Yan,R. Xue,X. Zhang,Quantum Imaging Med. Surg.4(4),225-231 (2014)   
18.D.K.Sodickson,W.J.Manning,Magn.Reson.Med.38,591-603(1997)   
19.K.P.Pruessmann,M. Weiger,M.B. Scheidegger,P.Boesiger,Magn. Reson.Med. 42,952-962 (1999)   
20.M.A.Griswold,P.M.Jakob,R.M. Heidemann,M.Nittka,V.Jellus,J.Wang,B.Kiefer,A.Hase, Magn.Res0n.Med.47,1202-1210 (2002)   
21.D.K.Sodickson,C.A.McKenzie,M.A.Ohliger,E.N.Yeh,M.D.Price,Magma 13,158-163 (2002)   
22.X.Yan,X. Zhang,L.Wei,R.Xue, Quant Imaging Med. Surg. 4(2),79-86 (2014)   
23.J.X.Ji, J.B.Son, S.D.Rane,Concept Magn.Reson.B 31B,24-36 (2007)   
24.G.H. Glover,C.E.Hayes,N.J.Pelc,W.A.Edelstein,O.M.Mueller,H.R.Hart, C.J.Hardy，M. Odonnell,W.D.Barber,J.Magn.Reson. 64,255-270(1985)   
25.Y.Li,B.Y.Yu,Y.Pang,D.B.Vigneron,X.L. Zhang,PLoS ONE 8(11),e80428 (2013)   
26.K.Lakshmanan,R.L.M.Cloos,D. Sodickson,G.Wiggins,in Proceedings of the 22nd Annual Meeting of ISMRM,Milan (2014),p.397   
27.J.Paska1,C.Leussler,in Proceedings of the 16th Annual Meeting of ISMRM,Toronto (2008),p.149   
28.K.M.Gilbert,A.T.Curtis,J.S.Gati,L.M.Klassen,L.E.Villemaire,R.S.Menon,Magn.Reson.Med. 64,1640-1651 (2010)   
29.Z.Xie,X.Zhang,in Proceedings of the 16th Annual Meeting of ISMRM,Toronto (2008),p.1068   
30.Z.Xie,X.Zhang,in Proceedings of thel6th Annual Meeting of ISMRM,Toronto (20O8),p.2972   
31.Y.Li, Z. Xie,Y.Pang,D.Vigneron,X. Zhang,Med.Phys.38,4086-4093 (2011)   
32. X.Yan,X. Zhang,B.Feng,C.Ma,L.Wei,R. Xue,IEEE Trans.Med.Imaging 33,1981-1987 (2014)   
33. X.Yan, X. Zhang,L.Wei,R. Xue,Appl. Magn.Reson. (2014). doi:10.1007/s00723-014-0612-9