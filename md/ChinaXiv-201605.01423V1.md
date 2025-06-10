# Theoretical Analysis of Magnetic Wall Decoupling Method for Radiative Antenna Arrays in Ultrahigh Magnetic Field MRI

XINQIANG YAN,1,2.3 ZHENTIAN XIE,4 JAN OLE PEDERSEN, XIAOLIANG ZHANG4,6

State Key Laboratory of Brain and Cognitive Science, Beijing MRl Center for Brain Research, Institute of Biophysics Chinese Academyof Sciences,Beijingloo1O1,China   
2Key Laboratoryof Nuclear Radiation andNuclear Energy Technology，Instituteof High Energy Physics，Chinese Academy of Sciences,Beijing 100049, China   
3 Beijing Engineering Research Center of Radiographic Techniques and Equipment, Beijing 10o049, China   
4 Department of Radiology and Biomedical Imaging, University of California San Francisco,San Francisco, CA 94158 5Sino-Danish Center forEducation andResearchUniversityof Chinese AcademyofSiences,Beijing1o19oChina 6 UCSF/UC Berkeley Joint Graduate Group in Bioengineering, San Francisco, CA 94158

ABSTRACT: Radiative antenna techniques,e.g.，dipole and monopole，have been proposed for radiofrequency (RF) coil array designs in ultrahigh field MRI to obtain stronger $\mathsf { B } _ { 1 }$ field and higher signal-to-noise ratio (SNR) gain in the areas deep inside human head or body. It is known that element decoupling performance is crucial to SNR and parallel imagingability of array coil and has been a challenging issue in radiative antenna array designs for MR imaging. Magnetic wall or induced current elimination (ICE) technique has proven to bea simple and effective way of achieving sufficient decoupling for radiative array coils expermentally.In this study,this decoupling technique for radiative coil array was analyzed theoretically and verified by a simulation study.The decoupling conditions were derived and obtained from the theory.By applying the predicated decoupling conditions,the isolationof two radiative elements couldbe improved fromabout $^ { - 8 }$ dB to better than $- 3 5$ dB. The decoupling performance has also been validated by current distribution along the radiative elements and magnetic field profiles in a water phantom. $\circledcirc$ 2015 Wiley Periodicals, Inc. Concepts Magn Reson Part B (Magn Reson Engineering) 45B:183-l90,2015

KEY WORDS:monopole;dipole;RF coil array;magnetic wall; ICE;decouple; simulation; ultrahigh field;MRI

# I.INTRODUCTION

Ultrahigh field (i.e., $7 \mathrm { ~ T ~ }$ and higher） magnetic resonance imaging (MRI)，has demonstrated remarking benefits for human imaging,including higher signalto-noise ratio (SNR)，higher spatial resolution,and better image contrast (1-5).The high static magnetic fields result in the increase in the Larmor frequency which is usually in radiofrequency(RF） range.At the high frequency of $3 0 0 ~ \mathrm { M H z }$ (Larmor frequency of proton at $7 \mathrm { T }$ ）and beyond,the wavelength is significantly shortened,especially in high dielectric biological samples,such as human body.The traditional near-field coils,e.g., lumped element $L / C$ loop resonators and microstrip transmission line resonators (6,7),face challenges to provide high SNR gain in the deep areas of human body.To address this problem,far-field coils or radiative antennas,e.g.,dipole (8,9）and monopole $( I O )$ ，have been applied and demonstrated stronger $B _ { 1 }$ field and higher SNR gain over the conventional near-field coils in the areas deep inside human head and body (8,10).

When the monopole or dipole techniques are employed for densely-spaced arrays,e.g.，8-channel or 16-channle arrays for human head imaging，the distance of two adjacent coil elements is smaller than $1 0 \ \mathrm { c m }$ (1/10 of the wavelength at $3 0 0 ~ \mathrm { M H z } )$ 二 Therefore the close arrangement of coil elements might lead to non-ignorable electromagnetic (EM) coupling，which could decrease the SNR and parallel imaging ability. Several decoupling methods have been successfully applied for traditional loop and microstrip line coil,e.g.，element overlapping $( l I )$ ,transformers(I2),and interconnecting $L / C$ networks (l3).However, these methods face challenges and not readily feasible for monopole or dipole arrays due to their unique structures.To attain sufficient isolation among the radiative coil elements, the magnetic wall (MW） or induced current elimination (ICE）decoupling technique（l4） has been proposed and successfully applied for monopole arrays(l5） and dipole arrays $( I 6 )$ ：

In this study,we aim to theoretically analyze the MW decoupling for radiative coil arrays in ultrahigh field MRI and derive the conditions required for achieving sufficient decoupling between radiative elements. Several theoretical methods,includingthe eigenvalue/eigenvector method, mutual impendence method,and odd/even mode method were employed in the analysis.Decoupling of a coil array isa process of modifying itsimpedance matrix and reducing all the off-diagonal elements to zero. For eigenvalue/eigenvector method，this can be regarded as a process of equalizing the eigenmode impedances.Mutual impedance method directly rearranges the impedance matrix to a diagonal matrix. Compared with eigenvalue/eigenvector method, mutual impedance method is more straightforward and easier to understand.However,it is limited by the complexity of the impedance matrix and is not suitable for analyzing arrays with highcount channels. Odd-even mode is another widelyused method for analyzing two-element arrays. This analysis assumes that any coupling between two coils can be decomposed into two basic modes, termed even and odd.In the even mode,the currents on both coils have the same direction and amplitude.In the odd mode,the currents on the two coils have the same amplitude but opposite direction.The coupling was totally reduced when the impedances in odd and even modes are the same. To validate the analytical results,transmission coefficient $( S _ { 2 1 } )$ ,current distribution, and magnetic field profile of MW decoupled radiative arrays were numerically studied and compared with those of radiative arrays without decoupling treatments.

![](images/62c2a342af1bb7aeac79f18b6086addaa859b2a845a85927f7e836bccf91e63c.jpg)  
Figure 1 Illustration of two radiative elements and a decoupling element. $V _ { i }$ and $I _ { i }$ are voltage and current across the ports. $Z _ { i j }$ are the mutual impedances of the ports. $Z _ { L }$ is the self impendence of the series circuit of the decoupling element.

# II.THEORY

Figure 1 shows a coil array consisting of two identical radiative elements and a decoupling element which is placed symmetrically between the two radiative elements.The self and mutual impedances of the two radiative elements (Element 1 and Element 2) and the decoupling element (Element d) are represented by $Z _ { i i }$ and $Z _ { i j }$ ，respectively，where $i \neq j$ $\{ i , j \} = 1 , 2 , d . V$ $V _ { i }$ and $I _ { i }$ are the voltage and current across the ports of the radiative elements and the decouplingelement. Thedecouplingelement includes a decoupling antenna and a series circuit. The self-impedances of the decoupling antenna and the series circuit are $Z _ { d ^ { \prime } , d ^ { \prime } }$ and $Z _ { L } .$ ，respectively.

The current of the decoupling element is totally passive.Therefore,the voltage of the decoupling element is zero and the matrix notation of voltage and current is

$$
\left[ \begin{array} { l l l } { Z _ { 1 1 } } & { Z _ { 1 2 } } & { Z _ { 1 d } } \\ { Z _ { 2 1 } } & { Z _ { 2 2 } } & { Z _ { 2 d } } \\ { Z _ { d 1 } } & { Z _ { d 2 } } & { Z _ { d d } } \end{array} \right] \left[ \begin{array} { l } { I _ { 1 } } \\ { I _ { 2 } } \\ { I _ { d } } \\ { I _ { d } } \end{array} \right] = \left[ \begin{array} { l } { V _ { 1 } } \\ { V _ { 2 } } \\ { 0 } \end{array} \right]
$$

Due to the reciprocity and the symmetry of Element 1 and Element 2,we can get

$$
\left\{ \begin{array} { c } { { Z _ { d 1 } = Z _ { 1 d } = Z _ { d 2 } = Z _ { 2 d } } } \\ { { { { } } } } \\ { { Z _ { 1 1 } = Z _ { 2 2 } } } \end{array} \right.
$$

# Eigenvalue/Eigenvector Method

In our previous study $( l 4 )$ ，the two coil elements are decoupled when one of the eigenvalues of impedance matrix $Z$ is equal to O. It is worth noting that although the eigenvalue/eigenvector method is used for reactance matrix $X$ ,it could be used for the impedance matrix $Z$ .The requirement of the decoupling element from Ref.(14) is

$$
{ \begin{array} { r } { \left[ { \begin{array} { c c c } { Z _ { 1 1 } } & { Z _ { 1 2 } } & { Z _ { 1 d } } \\ { Z _ { 2 1 } } & { Z _ { 2 2 } } & { Z _ { 2 d } } \\ { Z _ { d 1 } } & { Z _ { d 2 } } & { Z _ { d d } } \end{array} } \right] } { \left[ \begin{array} { c } { I } \\ { I } \\ { I } \\ { I _ { d } } \end{array} \right] } = { \left[ \begin{array} { l } { V } \\ { V } \\ { 0 } \end{array} \right] } } \end{array} 
$$

From Eqs.[6] and [7],the impedances of the odd-mode(referredtoas $Z _ { \mathrm { o } , \mathrm { \ell } }$ ）and even-mode (referred to as $Z _ { \mathrm { e } }$ ）can be derived as follows:

$$
\begin{array} { c } { { Z _ { \mathrm { { o } } } = \displaystyle \frac { V } { I } = Z _ { 1 1 } - Z _ { 1 2 } } } \\ { { Z _ { \mathrm { { e } } } = \displaystyle \frac { V } { I } = Z _ { 1 1 } + Z _ { 1 2 } - 2 \displaystyle \frac { z _ { 1 d } ^ { 2 } } { z _ { d d } } } } \end{array}
$$

If $Z _ { \mathrm { o } } = Z _ { \mathrm { e } }$ ，the elements are decoupled. Thus, based on Eqs.[8] and [9],the decoupling condition can be derived as

$$
Z _ { d d } = \frac { z _ { 1 d } ^ { 2 } } { z _ { 1 2 } }
$$

# Mutual Impendence Method

From Eqs.[1] and [2],the matrix notation of the voltage and current of Element 1 and Element 2 can simplified as $( I 7 )$

$$
\begin{array} { r l } { \left[ Z _ { 1 1 } - \frac { z _ { 1 d } ^ { 2 } } { z _ { d d } } } & { Z _ { 1 2 } - \frac { z _ { 1 d } ^ { 2 } } { z _ { d d } } \right] } \\ { \left[ Z _ { 1 2 } - \frac { z _ { 1 d } ^ { 2 } } { z _ { d d } } } & { Z _ { 1 1 } - \frac { z _ { 1 d } ^ { 2 } } { z _ { d d } } \right] } & { \left[ I _ { 1 } \right] = \left[ \begin{array} { l } { V _ { 1 } } \\ { V _ { 2 } } \end{array} \right] . } \end{array}
$$

The two coil elements were decoupled when the new mutual impendence matrix $Z$ could be simplified as a diagonal matrix.In other words，we require $\begin{array} { r } { Z _ { 1 2 } - \frac { z _ { 1 d } ^ { 2 } } { z _ { d d } } = 0 } \end{array}$ Thus the requirement of the decoupling element is

$$
Z _ { d d } = \frac { z _ { 1 d } ^ { 2 } } { z _ { 1 2 } }
$$

$$
Z _ { d d } = \frac { z _ { 1 d } ^ { 2 } } { z _ { 1 2 } } .
$$

# Odd/Even Mode Method

For the odd mode,the voltages and currents of the two ports are: $V _ { 1 } = - V _ { 2 } = V$ ， $I _ { 1 } = - I _ { 2 } = I $ Thus Eq. [1] can be written as:

$$
{ \left[ \begin{array} { l l l } { Z _ { 1 1 } } & { Z _ { 1 2 } } & { Z _ { 1 d } } \\ { Z _ { 2 1 } } & { Z _ { 2 2 } } & { Z _ { 2 d } } \\ { Z _ { d 1 } } & { Z _ { d 2 } } & { Z _ { d d } } \end{array} \right] } { \left[ \begin{array} { l } { I } \\ { - I } \\ { I _ { d } } \end{array} \right] } = { \left[ \begin{array} { l } { V } \\ { - V } \\ { 0 } \end{array} \right] }
$$

For the even mode,the voltages and currents of the two ports are: $V _ { 1 } = V _ { 2 } = V$ ： $I _ { 1 } = I _ { 2 } = I$ Thus Eq. [1] can be written as:

It is clear from Eqs.[3],[5],and [1O] that the three theoretical methods gave the same requirement of the decoupling element.Given that the decoupling element includes a decoupling antenna $( Z _ { d ^ { \prime } d ^ { \prime } } )$ and a series circuit $( Z _ { L } )$ ，the required impedance of $Z _ { L }$ ：

$$
Z _ { L } = \frac { z _ { 1 d } ^ { 2 } } { z _ { 1 2 } } - Z _ { d ^ { \prime } d ^ { \prime } }
$$

# III.SIMULATION

A set of EM simulations using a full-wave EM solver (HFSS,ANSYS,Canonsburg,PA） were employed to validate the theoretical analysis described above (2). In this article,we only use monopoles as an example to demonstrate this concept. However, the basic principle will work for any coil,e.g.，dipole array，since the method only relies on self and mutual impedances.Two monopole elements with and without the decoupling element were modeled in simulation,as shown in Fig.2(A,B).In the simulations,the length of the decoupling element was chosen the same as the monopole elements.Monopole elementswere mounted on a cylindrical former with a diameter of $2 5 \mathrm { \ c m }$ ．The angle of two monopole elements was varied from 25 to 5O degree with a step of 5 degree [Fig.2(C)],which means the distance between the two monopoles was varied from $4 . 3 \ \mathrm { c m }$ to $1 0 . 6 ~ \mathrm { c m }$ The operating frequency is $2 9 7 . 2 ~ \mathrm { M H z }$ ，which corresponds to the Larmor frequency of our $7 \mathrm { T }$ MRI system.A cylindrical water phantom with an outer diameter of $1 6 ~ \mathrm { c m }$ and a length of $3 7 \ \mathrm { c m }$ was placed

![](images/e402e4fc0d2d2de913ee7db4b99126b77dd258ecd8a0292d438c1921606e0381.jpg)  
Figure2Three-dimensional (3-D)modelsof 2-channel monopole arrays without (A）and with (B)thedecoupling element.C:Crossviewof the two monopolesand the water phantom.Monopole elements were mounted ona cylindrical former with a diameter of $2 5 \ \mathrm { c m }$ .The angle of two monopole elements was varied from 25 to 5O degree with a step of 5 degree.

$4 . 5 ~ \mathrm { \ c m }$ below the monopole elements. The EM parameters of the water phantom were set as: conductivity $\sigma = 0 . 5 9 ~ \mathrm { S / m }$ ；relative permittivity $\varepsilon _ { \mathrm { r } } = 7 8$ . The distance between the boundary and models was larger than $\lambda / 2$ .Manual mesh was used to accelerate simulation convergence and the convergence condition $\Delta S$ Was set to O.OO2 to achieve more reliable results.

Asshown in Fig.3, the procedure of the validation is:

1.The series circuit of the decoupling element is replaced with a port. Then we get self impedance of the decoupling monopole $( Z _ { d ^ { \prime } d ^ { \prime } } )$ and the mutual impedances of monopole-monopole $( Z _ { 1 2 } )$ and monopole-decoupling element $( Z _ { 1 d } )$ ：   
2.Secondly, the impedance of the serious circuit of decoupling element $( Z _ { L } )$ is obtained by solving Eq. [11].   
3.Finally,the equivalent lump component of $Z _ { L }$ is employed in new simulation. $S _ { 2 1 }$ of the two monopoles,current distribution along the conductors,and the magnetic field on the phantom were obtained and compared with the 2-channel array without decoupling treatments.

# IV.RESULTS

# Validation of S-Parameter

$Z _ { 1 2 } , \ Z _ { 1 d } .$ and $Z _ { d ^ { \prime } d ^ { \prime } }$ obtained from Step 1 of Fig.3 were listed in Table 1,from the second row to fourth row. The desired $Z _ { L }$ calculated from Eq. [11] was listed in the fifth column.The required resistances of the decoupling elements(referred to as $R ( Z _ { L } ) )$ are assumed to be neglectable because their values are very small. Thus only the imaginary parts of $Z _ { L }$ (referred to as $\mathrm { I m } ( Z _ { L } ) )$ ）werereplaced by lump components (capacitors or inductors),as listed in the sixth column.In order to validate the analysis described above，the equivalent lump components (sixth column of Table 1） were employed in the new simulation (Step 3 of Fig. 3).

Figure 4 shows $S _ { 2 1 }$ of the two monopole elements with and without decoupling elements.It can be observed that the coupling was reduced from about $- 8 \ \mathrm { d B }$ to a sufficiently small value $( < - 3 5$ dB）when the predicated decoupling elements were employed.This indicates that the theory described above was reliable and can accurately estimate the circuit of the decoupling element. These results have also demonstrated that the assumptionof neglectable $R ( Z _ { L } )$ is reasonable.Thus only reactance (capacitance or inductance） is needed and no Ohm loss is induced in the decoupling element.

# Validation of Current Distribution and $\pmb { H }$ Field

Figure 5(A） shows the current density distribution of two coupled monopoles when the left monopole was excited with $1 \mathrm { \Delta W }$ while the right monopole was not excited.Due to the mutual coupling,the signal power was obviously coupled to the right monopole,especially when the angle equals to 2O or 25. By using the predicated decoupling elements,however， the coupled signal became neglectable,as shown in Fig.5(B). This comparison results were in agreement with the $S _ { 2 1 }$ results as described above. The current directions were indicated by black arrows in Fig. 5(A,B). The current of right monopole using MW decoupling was very small and thus its direction was not shown.

Setp1: Get Z1d, Z12,Zd'd'

![](images/cf1edc38a65b94de75c2da1b9da258a8573047cbf8d96faf9ffb9507b62020a4.jpg)

Setp3: Comparison of monopole arrays with (right) and without decoupling treatments (left)

![](images/3cbc1643ea545b759ccf665c76055a99ed4c69623ac20583449732455b29aa1f.jpg)  
Figure 3The procedure of validating the theoretical analysis with a EM simulation study.

Figure 5(C,D） shows the normalized $H$ field on the water phantom in the transverse planeof monopole arrays without and with MW decoupling method. Clearly， the decoupling elements have shielding effect,making $H$ field profiles more independent and weaker at the neighborhood of the two elements.As shown in previous studies (I8), the shielding effect could benefit the MR imaging in terms of

Table 1 Self and Mutual Impedances of the Monopole Elements and Decoupling Elements   

<html><body><table><tr><td>Angle (degree)</td><td>Z12 (Ω)</td><td>Z1d (Ω)</td><td>Zdd(Ω)</td><td>Zz[11] (Ω)</td><td>Equivalent of Im (ZL)</td></tr><tr><td>20</td><td>29.637 + j5.438</td><td>31.769 + j11.39</td><td>32.9 + j18.673</td><td>0.145- j0.2816</td><td>1.9017 nF</td></tr><tr><td>25</td><td>27.848 + j2.2095</td><td>31.087 + j9.3953</td><td>32.686 + j18.399</td><td>0.3036- j0.0403</td><td>13.288 nF</td></tr><tr><td>30</td><td>25.8 - j0.63357</td><td>30.271 + j7.5383</td><td>32.409 + j18.177</td><td>0.451 + j0.3192</td><td>0.171 nH</td></tr><tr><td>35</td><td>23.551- j3.0622</td><td>29.9362 + j5.8832</td><td>32.071 + j17.979</td><td>1.9913 + j1.4065</td><td>0.7536 nH</td></tr><tr><td>40</td><td>21.215 - j5.0843</td><td>28.402 + j4.386</td><td>31.728 + j17.91</td><td>0.7114 + j1.6080</td><td>0.8615 nH</td></tr><tr><td>45</td><td>18.86 - j6.7665</td><td>27.462 + j2.9963</td><td>31.507 + j18.248</td><td>0.7249 + j2.0418</td><td>1.094 nH</td></tr><tr><td>50</td><td>16.437 - j8.0404</td><td>26.338 + j1.689</td><td>31.061 + j17.975</td><td>0.7168 + j2.9824</td><td>1.5979 nH</td></tr></table></body></html>

Concepts inMagnetic Resonance PartB(Magnetic Resonance Engineering) DOI10.1O02/cmr.b

![](images/82808de174a27b4d228893189ed6bbcd2a093cabbdbe60e08720289b9d7e3b15.jpg)  
Figure 4 $\mathbf { S } _ { 2 1 }$ plots vs. frequency of the two monopole elements with and without the magnetic wall decoupling method. The series circuitsofthedecoupling elements used in simulation werecalculated fromEq.[11].It isclearthatthe strong coupling could be reduced from $^ { - 6 }$ to $- 1 0 ~ \mathrm { d B }$ to a sufficiently small value (better than $- 3 5 ~ \mathrm { d B } ,$ ).These results indicate that the theory described above was reliable and itcanaccurately estimate the requirement of the decoupling element.

![](images/ab2c34a7b68b0511c0291c0db32ba52935f537f9336ae41849d3b42ca4bc9f73.jpg)  
Figure 5Surface current distributions of monopole arrays and magnetic field profiles on the water phantom.During the simulation,onlythe leftport was excited with1W.A:Current distributionof the monopole array without decoupling treatments.B: Current distribution of the MWdecoupled monopole array.Byusing the predicated decoupling element,the coupled currenton theright monopolescanbewellsuppressed.Black arrows in(A)and(B)indicate thecurrent directions along theconductors.C: Magnetic feld profileof monopole arrywithout decoupling treatments.D:Magnetic field profile of the MW decoupled monopole array.The magnetic fields near the right monopole become weaker when MW decoupling was employed,which is probably because the decoupling elements act as“magnetic wall’and show shielding effect.

SNR and parallel imaging performance.It can be understood that the shielding effect was generated by the induced current of the decoupling element.

# V.DISCUSSIONS AND CONCLUSION

Magnetic wall/ICE decoupling method uses an independent resonator/antenna which has no physical connection to array elements to compensate for the current induced by EM coupling in array elements. In this study,this decoupling method applied for radiative coil array in ultrahigh field MRI was analyzed by using the eigenvalue/eigenvector method, mutual impendence method,and odd/even mode method. The derived conclusions on decoupling conditions from all the three theoretical methods are consistent. Thesetheoretical methodsandthe decoupling conditions were validated by a set of comparative EM simulations.

The results of numerical analysis on transmission coefficient $( S _ { 2 1 } )$ between array elements and the induced current distribution have demonstrated that the strong coupling $\left( \sim - 8 ~ \mathrm { d B } \right)$ could be reduced to a sufficiently small value (better than $- 3 5 \mathrm { d B } )$ byusing the decoupling condition obtained from the theoretical analysis. The induced current of the decoupling element caused shielding effect and focused the magnetic field of monopole element (Fig. 5). This focusing generates locally stronger and spatially diverse $B _ { 1 }$ fields of antenna array elements,which might be advantageous for MR imaging in terms of SNR and parallel imaging performance.

From Fig.4,we can find that the decoupling performance still could be better than $- 3 0$ dB even when the distance between monopoles is only about $5 \mathrm { c m }$ .This indicates that the ICE decoupling method is potential to design radiative coil arrays with high-count channels,e.g.，16 channels.Since the above derivation is purely based on self and mutual impedances,the decoupling element can be arbitrary and need not be of the same type.In other words，the decoupling element could be loop or microstrip line resonators as long as it meets the decoupling condition in Eq.[3].

# ACKNOWLEDGMENT

The authors appreciate the invaluable advices from anonymous reviewers of this paper.This study was supported in part by the National Natural Science FoundationofChinaGrant(51228702)， and National Institutes of Health (NIH) RO1EBo08699.

# REFERENCES

1.Yacoub E,Shmuel A,Pfeuffer J,Van de Moortele PF,Adriany G,Andersen P,Vaughan JT,Merkle H, Ugurbil K,Hu XP.20O1.“Imaging brain function in humans at 7 Tesla".Magn Reson Med 45:588-594.   
2.Vaughan JT,Garwood M，Collins CM,Liu W, DelaBarre L，Adriany G,Andersen P，Merkle H, Goebel R,Smith MB,Ugurbil K.2001.“7T vs.4T: RF power, homogeneity,and signal-to-noise comparison in head images".Magn Reson Med 24:24-30.   
3.Lei H, Zhu X,Zhang X,Ugurbil K,Chen W.2003. “In vivo $^ { 3 1 } \mathrm { P }$ magnetic resonance spectroscopy of human brain at 7 T".Magn Reson Med 49:199-205.   
4.Ibrahim TS,Mitchell C，Schmalbrock P,Lee R, Chakeres DW. 2005.“Electromagnetic perspective on the operation of RF coils at 1.5-11.7 Tesla". Magn Reson Med 54:683-690.   
5．Thomas BP,Welch EB,Niederhauser BD,Whetsell WO Jr.,Anderson AW,Gore JC,Avison MJ, Creasy JL. 2008.“High-resolution 7T MRI of the human hippocampus in vivo". JMagn Reson Imaging 28:1266-1272.   
6.Adriany G,Van de Moortele PF,Wiesinger F,Moeller S, Strupp JP,Andersen P, Snyder C, Zhang X, Chen W, Pruessmann KP,Boesiger P,Vaughan T,Ugurbil K. 2005.“Transmit and receive transmission line arrays for 7 Tesla parallel imaging". Magn Reson Med 53:434445.   
7.Zhang X,Ugurbil K,Chen W.2001.“Microstrip RF surface coil design for extremely high-field MRI and spectroscopy". Magn Reson Med 46:443-450.   
8.Raaijmakers AJ,Ipek O,Klomp DW,Possanzini C, Harvey PR,Lagendijk JJ,van den Berg CA.2011. “Design of a radiative surface coil array element at 7 T: the single-side adapted dipole antenna". Magn Reson Med 66:1488-1497.   
9.Wiggins GC， Zhang B，Lattanzi R， Chen G, Sodickson D. 2012.“The Electric Dipole Array: An Attempt to Match the Ideal Current Pattern for Central SNR at 7 Tesla". In Proceedings 2Oth Scientific Meeting，International Society for Magnetic Resonance in Medicine. Melbourne,Australia. p 541.   
l0.Hong SM,Park JH,Woo MK,Kim YB,Cho ZH. 2014.“New design concept of monopole antenna array for UHF 7T MRI".Magn Reson Med.71:1944-1952.   
[1.Roemer PB,Edelstein WA,Hayes CE,Souza SP, Mueller OM. 1990.“The NMR phased array". Magn Reson Med 16:192-335.   
l2．Avdievich NI. 2O11.“Transceiver-phased arraysfor human brain studies at 7 T". Appl Magn Reson 41:483- 506.   
l3.Wu B,Qu P,Wang C,Yuan J,Shen GX.2007. “InterconnectingL/C components for decoupling and itsapplication to low-field open MRI array".Concepts Magn Reson B Magn Reson Eng 31:116-126.   
l4. Li Y, Xie Z, Pang Y, Vigneron D, Zhang X. 2011. “ICEdecouplingtechniqueforRFcoilarray designs". Med Phys 38:4086-4093.   
15．Yan X,Zhang X,Wei L,Xue R.2014.“Magnetic wall decoupling method for monopole coil array in ultrahigh field MRI: a feasibility test". Quant Imaging Med Surg 4:79-86.   
16.Yan X,Zhang X,WeiL,Xue R.2015.“Design and test of magnetic wall decoupling for dipole transmit/ receive array for MR imaging at the ultrahigh field of 7T".Appl Magn Reson 46:59-66.   
17．Avdievich NI,Pan JW,Hetherington HP.2O13."Resonant inductive decoupling (RID) for transceiver arrays to compensate for both reactive and resistive components of the mutual impedance".NMRBiomed 26:1547-1554.   
18.Yan X,Zhang X,Feng B,Ma C,Wei L,Xue R.   
2014.“7T transmit/receive arrays using ICE decoupling for human head MR imaging".IEEE Trans Med Imaging 33:1781-1787.