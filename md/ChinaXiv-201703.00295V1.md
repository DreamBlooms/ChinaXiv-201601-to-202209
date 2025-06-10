# A Broadband Reflectarray Using Patch With Slot Ring On Ground Plane Elements

Fei Xue1, ², Hongjian Wang',Min ${ \bf { \cal Y } _ { i } ^ { \bullet } }$ , and Xingchao Dong1, 2 'CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academyof Sciences,Beijing,100190, China ²University of Chinese Academy of Sciences, Beijing,100049, China

ABSTRACT—A broadband center-fed reflectarray antenna is presented in this paper. Patch with slot ring on ground plane elements are used for bandwidth improvement. It is shown that quasi-linear phase responses with broad frequency band can be achieved by such a phasing element.An $1 1 \times 1 1$ elements reflectarray is designed and simulated. The results show that the simulated gain is $2 3 . 9 2 \mathrm { d B }$ at the center frequency of 13.58GHz with 3-dB bandwidth of $52 \%$ ， which demonstrate significant broadband operation compared with that of conventional reflectarray.

# 1.INTRODUCTION

For most radar and long distance communications,the need for high gain antennas is inevitable. Parabolic reflectors and arrays are playing an important role in this application. However, due to its specificaly curved surface,the disadvantages of the parabolic reflector are also apparent, such as heavy,bulky and nonplanar. On the other hand,the high gain array antenna which equipped with controllable phase shifters generally becomes very expensive because of its complicated beamformer and high cost amplifier modules.In order to avoid the above mentioned disadvantages,reflectarray antenna emerged with the advantages of high gain,low profile and mass,low cost, flatness and so on. It is usually an antenna that consists of an illminating feed antenna and a flat reflecting surface with many microstrip elements.

The main limitation of reflectarray antennas is their narrow bandwidth，generally lower than 5 percent and even less for large reflectarrays [1]. Its bandwidth is mainly limited by two factors of the element bandwidth and spatial phase delay dispersion.However，for small or moderate size reflectarray antennas,the factor of element bandwidth plays a dominant role in reflectarray bandwidth. In the previous papers，several methods have been presented to improve the bandwidth of the reflectarray [2-7]. In [2],a novel single-layer cell consists of three coupled circular rings where four quasi-spiral delay lines are connected to the outer ring is presented. An $1 8 \times 1 8$ elements reflectarray is designed based on the element and 1-dB gain bandwidth about $1 6 . 5 \%$ is achieved.In [3],a significant improvement in the bandwidth of large reflectarrays is demonstrated using elements which allow true time delay.In [4],an optimization method to enhance the bandwidth is proposed and two single layer large printed reflectarrays with multi cross loop elements of variable loop length are designed. The results show a significant improvement in the radiation pattern and gain bandwidth. The multilayer approach combined with the subwavelength element technique is presented in [5],and 1-dB gain bandwidth of $1 9 . 1 \%$ has been demonstrated for a double-layer reflectarray using elements with a periodicity of $\lambda / 4$ . In [6] and [7], multi-resonant structures are used for broadband operation.

In this paper, a novel element structure using a circular patch with slot ring on the ground plane is presented,which offers enough variation phase range with quasi-linear phase responses. An $1 1 \times 1 1$ elements reflectarray is designed and simulated based on the suggested element, and 3-dB gain bandwidth about $52 \%$ is achieved, which demonstrates wideband operation for the present reflectarray antenna.

# 2. ELEMENTDESIGN

The configuration of the proposed reflectarray element is composed of a circular patch with slot ring on the ground plane,as shown in Figure 1. The elements are etched on a Rogers 588O substrate with relative permitivity of 2.2 and thickness of h1. The layer between the two ground planes is an air layer whose relative permitivity is 1 and thickness is h $2 . { \mathrm { L } } { = } 1 3 { \mathrm { m m } }$ is the lattice period of the element and equivalent to O.59 wavelengths at13.58GHz.

![](images/f9c0b0b94fc3b7c4b7d9eaaa631a419b73e991146b6f16cae6acc7739cdf1747.jpg)  
Figure 1: The element structure.

The phase response is obtained by adjusting the patch radius $r$ . The relationships between patch radius $r$ ,the outer slot ring radius $r _ { I }$ and the width of the slot ring $g$ is $\scriptstyle r _ { I } = k \times r$ and $g { = } k _ { I } { \times } r$ ,respectively. After optimizing the dimension parameters,the final design parameters are as follows: $h _ { I } { = } 1 . 5 \mathrm { m m }$ $h _ { 2 } { = } 1 \mathrm { m m } , k { = } 1 . 7 , k _ { I } { = } 0 . 1 7 .$

The equivalent unit cell waveguide approach [8] is used to get the phase responses for the normal incidence of plane wave. The analysis of elements'reflection phase was carred out using HFSS,and the periodic boundary conditions are used to give consideration to the interactions with identical neighbor elements.Reflection phase versus patch radius $r$ for different frequencies( $1 1 . 5 8 \mathrm { - } 1 5 . 5 8 \mathrm { G H z } )$ are shown in Figure 2.The quasi-linear phase responses at diferent frequencies indicate the wideband property of the proposed element.

![](images/1412521f27e659c47018a3612adf1c0315bc4d7e73d995e1b976a2c655aa0471.jpg)  
Figure 2: Reflection phase versus patch radius $r$ for different frequencies.

# 3.REFLECTARRAYDESIGNANDPERFORMANCE

In order to validate wideband property of the proposed element, an $1 1 \times 1 1$ elements reflectarray is designed using the proposed element and the performances of the reflectarray are simulated.The reflectarray is center fed by a linearly polarized pyramidal horn antenna.Figure 3 shows the radiation pattern of the pyramidal horn antenna at $1 3 . 5 8 \mathrm { G H z }$ . The distance between the phase center of the horn antenna and the reflectarray is $1 4 3 \mathrm { m m }$ ，which is equivalent an $\mathrm { F / D }$ ratio of 1.All the elements' reflection phase are adjusted to generate a beam in the direction of $Z$ axis (the reflectarray is in the XY-plane). Figure 4 presents the structure of the proposed antenna. Figure 5 shows the simulated radiation patterns of the reflectarray antenna in E-plane and H-plane at the center frequency of 13.58 $\mathrm { G H z }$ ,it can be concluded that the simulated gain is $2 3 . 9 2 \mathrm { d B }$ at the center frequency of $1 3 . 5 8 ~ \mathrm { G H z }$ The simulated gains against frequencies from $1 1 . 0 8 \ : \mathrm { G H z }$ to $1 9 . 5 8 \ : \mathrm { G H z }$ are shown in Figure 6,which exhibits 3-dB gain bandwidth about $52 \%$ (11.58-18.58 GHz).

![](images/2c7c0f788f8b144412f265206d6844545f45705678091d687c378f8a2bc509b1.jpg)  
Figure 3:Radiation pattern of the feed at center frequency (13.58GHz).

![](images/c5cdc06677c82cd4dfb34fe11fb6db0c3bf32d132b5e332d8fbd2920d9fcec9f.jpg)  
Figure 4: The structure of the proposed reflectarray antenna.

![](images/656b5917016e40f32784315ada20b9635f5ba43b87e59747f666cb7c3fb147e7.jpg)  
Figure 5: The simulated radiation pattern of the reflectarray antenna.

# 4.CONCLUSION

A novel element structure using a patch with slot ring on the ground plane is proposed in this paper. A quasi-linear phase responses with broad frequency band have been achieved by changing the sizes of the patch and slot ring on the ground plane.A reflectarray with $1 1 \times 1 1$ elements is designed and simulated based on the mentioned element. The simulated results show the 3-dB gain bandwidth is $52 \%$ . An experimental verification will be performed in the next step.

![](images/03d2d39e0259adbe614f4ec24b5c52b466eaa1568af62908f066b982e630f1ad.jpg)  
Figure 6: Simulated gain of the reflectarray antenna.

# REFERENCES

1.J.Huang and J.A.Encinar,Reflectarray Antennas. John Wiley & Sons, Institute of Electrical and Electronics Engineers,2008.   
2.I. Derafshi， N. Komjani and M. Mohammadirad,“A Single-Layer Broadband Reflectarray Antenna by Using Quasi-spiral Phase Delay Line,” IEEE Antennas and Wireless Propagation Letters, Vol. 14, 84-87,2015.   
3. E. Carrasco, J. A. Encinar and M. Barba, “Bandwidth improvement in large reflectarrays by using true-time delay,” IEEE Transactions on Antennas and Propagation, Vol. 56, No.8, 2496-2503, 2008.   
4. M. R. Chaharmir, J. Shaker and H. Legay,“Broadband design of a single layer large reflectarray using multi cross loop elements,” IEEE Transactions on Antennas and Propagation, Vol. 57,No. 10,3363-3366,2009.   
5.P. Nayeri, F. Yang and A. Z. Elsherbeni,“Broadband reflectarray antennas using double-layer subwavelength patch elements,” IEEE Antennas and Wireless Propagation Letters，Vol. 9, 1139-1142,2010.   
6.J. H. Yoon, Y. J. Yoon, W. Lee and J. So,“Broadband microstrip reflectarray with five parallel dipole elements,” IEEE Antennas and Wireless Propagation Letters, Vol.14,1109-1112,2015.   
7.K.H. Sayidmarie and M.E. Bialkowski,“Fractal unit cells of increased phasing range and low slopes for single-layer microstrip reflectarrays,” IET Microwaves,Antennas & Propagation, Vol. 5, No. 11, 1371-1379,2011.   
8.F.E. Tsai and M. E. Bialkowski,“An equivalent waveguide approach to designing of reflect arrays with the use of variable-size microstrip patches,” Microwave and Optical Technology Letters,Vol.34,No.3,172-175,2002.