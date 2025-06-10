# A Novel Single-Layer Unit Structure for Broadband Reflectarray Antenna

Chunhui Han, Student Member, IEEE, Yunhua Zhang,Member, IEEE and Qingshan Yang, Member, IEEE

Abstract—A novel X-band single-layerunit cell structure with enhancedbandwidthforlinearlypolarizedmicrostrip reflectarray antenna is proposed.The unit-cell structure is composed of two circular rings,each with a pair of gaps which are orthogonallyplaced,and two identical phase-delay lines attached to the outercircularring.With this novel structure,a linear phase response ranging about $\pmb { 5 5 0 } ^ { \circ }$ isachievedby varying the length of the phase delay line.An offset-fed reflectarray antenna composed of 277 elements forming an octagon-shape aperture is designed, fabricated,and measuredto verifythebroadbandcharacteristic of the proposed unit cell.Measurement results show that $20 \%$ 1-dB gainbandwidth isrealized.Besides, the maximum gain at10 GHz is about 26.38 dBi,which means about $51 . 3 \ \%$ efficiency is achieved.At the same time，the side lobe level and cross polarizationforE-planearealsomeasuredwhicharebelow $\mathbf { - 1 7 . 5 }$ dB and $- 2 6 \ : \mathbf { d B }$ ,respectively.

Index Terms—Reflectarray antenna,single-layer unit cell, bandwidth enhancement,phase delay lines.

# I．INTRODUCTION

MCROe hsi and radar, due to its alluring advantages [1].However, there are also some disadvantages for microstrip reflectarray antennas, especially the narrow bandwidth.There are two main factors which restrict the gain bandwidth of microstrip reflectarray antennas: first, the nature of narrow bandwidth for microstrip antenna unit cells,second, the differential spatial phase delay between the feed source and unit cells on the reflectarray plane. The first is more significant to the bandwidth limitation for small and medium-size reflectarray antennas [2].

Numerous methodswere presented to enhance the bandwidth performance of radiating unit cells for reflectarray antennas in recent years,among which by applying unit cells with wide-range linear phase responses is a very effective one [3].There are several approaches to achieve linear phase responses, such as using multi-layer structures [4], thickening substrate,and attaching phase-delay lines [5]. In order to reduce the fabrication errors and the cost,single-layer broadband reflectarrays have been proposed by using multi-resonant elements and $24 \%$ 1-dB gain bandwidth was achieved [6]. However,this approach needs thick substrate to obtain linear phase responses,so the increases of mass as well as cost are unavoidable.Besides,thick substrate also leads to smaller linear phase range.So the dimension sizes of the elements have to belargelyvaried in order to achieve wide enough range of linear phase responses，and thus potential phase error is unavoidable due to the mutual couplings become much complicated as well as the fabrication errors are hard to control.

In recent years,a lot of researchers have been focused on the approach of using phase-delay lines because large linear phase range can be easily achieved with thin substrate with no need to use elements of largely varied size [5], [7], [8],[9].However, the bandwidth performance mentioned in these works was still limited, since the parallelism of the phase response curves versus the phase-delay-line length for the presented elements Was not so well which unavoidably restricted the expanding of working frequency band.

In this letter,a linear polarized single-layer unit-cell structure isproposed to enhance the bandwidth performance of reflectarray antennas. The proposed element structureis constructed by an inner resonant structure which is composed of double split ringsand two phase-delay lines.The double split rings were first proposed for dual-band circularly polarized reflectarrays[1O] which rotates independently to obtain different reflecting phases.In our work, the double split rings are fixed with dimensions optimized to provide linear phase responses versus frequency.In thisway，parallel phase response curves versus the phase-delay-line length are obtained A277-elementoffset-fedreflectarrayformingan octagon-shape aperture operating at $\mathrm { \Delta } \mathrm { X }$ band is designed, manufactured， and measured to validate the broadband characteristic of the proposed unit-cell structure.Measurement results show that 1-dB gain bandwidth reaches over $20 \%$ .The measured peak gain at $1 0 \mathrm { G H z }$ is about 26.38 dBi, which equals to about $5 1 . 3 \%$ efficiency.

# II.UNIT CELLDESIGN

Fig.1 depicts the designed single-layer unit-cell structure, which was proposed in our previous work [11]. The proposed unit cell consists of two circular rings,each with a pair of gaps orthogonally placed and two identical phase-delay lines are attaching to the outer circular ring for phase shifts. $w _ { i }$ and $w _ { o }$ are the width of the inner ring and outer ring,and the corresponding gaps are $g _ { i }$ and $g _ { o }$ $w _ { s }$ and $L _ { s }$ represent the width and the length of the stubs which connect the phase delay line to the outer circular ring. The length of the identical phase-delay lines is represented by its rotation angle $\theta$ in degree. The unit-cell size is designed to be $L = 1 5 \ \mathrm { m m }$ ( $0 . 5 \lambda$ for 10 GHz, $\lambda$ is the wavelength in free space).Unitcells are etched ona dielectric substrate $( d _ { t } )$ of $1 . 5 \mathrm { m m }$ thickness with relative permittivity $\varepsilon _ { r } =$ 3.48 and $2 \mathrm { - m m }$ -thickair layer $( d _ { s } )$ separates the substrate layer and the metallic ground for more smooth phase response.

![](images/b931a6ed69e60fc60373f6c909b3c4b9eb67339189d001bb75190e5be19df227.jpg)  
Fig.1.Unit cell structure for reflectarray antenna.

TABLEI REFLECTARRAYELEMENTGEOMETRYPARAMETERS   

<html><body><table><tr><td>Quantity</td><td>Value</td></tr><tr><td>0</td><td>5°:2.5°:180°</td></tr><tr><td>Ws</td><td>0.4 mm</td></tr><tr><td>Ls</td><td>0.4 mm</td></tr><tr><td>gi</td><td>0.6 mm</td></tr><tr><td>g0</td><td>0.6 mm</td></tr><tr><td>Wi</td><td>0.88 mm</td></tr><tr><td>Wo</td><td>0.8 mm</td></tr><tr><td>Ri</td><td>1.8 mm</td></tr><tr><td>R</td><td>4.0 mm</td></tr><tr><td>dt</td><td>1.5 mm</td></tr><tr><td>d</td><td>2.0 mm</td></tr></table></body></html>

To investigate the phase response of the unit cell and perform optimization for structure geometry parameters,an infinite array model is built in the simulation software of HFSS,in which Floquet port excitation and master-slave boundary condition are adopted. The operating principle of our proposed element can be described as follows.To obtain linear phase responses versus frequency,the geometric parameters of the double split-ring structure are optimized,which is designed to resonate at $1 0 \mathrm { G H z }$ Besides,the width $( w _ { s } )$ and the length $( L _ { s } )$ of the stub should also be optimized to realize good matching between phase-delay lines and the double split-ring structure. In this way, the reflecting phase curves versus the lengths of the phase-delay lines at different frequencies will have a great chance to maintain parallel and thus wide-band performance can be achieved.TABLE I lists the final designed element

![](images/a4b0fcb9d15184362c4b9f17c35881f2a0d0f70655a5666d92c1b04d3d409584.jpg)  
Fig.2.Reflection phase curves versus the length of phase-delay line

![](images/78cdf4d96c769bf6805aef2f9359256850cd91cf3c02bedf1b3335672b4aaf7a.jpg)  
Fig.3.Reflection phases versus frequency for element of $0 ^ { \circ }$ phase shift for different unit cells.

parameters for the elements.

The phase response curves against the length of the phase-delayline at different frequenciesof 9,1O,11,and 12 GHz are plotted in Fig.2,in which the value of $\theta$ is the length of the phase-delay lines.As one can see,a linear and smooth reflecting phase curve ranging about $5 5 0 ^ { \circ }$ is achieved at frequency of $1 0 ~ \mathrm { G H z }$ .Parallel phase curves among different frequencies are also obtained.It is worth noting that the reflecting phases vary linearly with smaller slopes and in parallel with each other when the lengths of the phase-delay line $\mathbf { \eta } ( \theta )$ range from $6 0 ^ { \circ }$ to $1 8 0 ^ { \circ }$ ，which demonstrates a better broadband performance compared with the unit cells in [5], [7], [8], [9].

To further explore the broadband property of the proposed unit cell,different unit cells with orthogonal gaps, parallel gaps, and without gaps are investigated with results presented in Fig.3,which shows how the reflection phases for elements of $0 ^ { \circ }$ phase shift vary with frequency [12]. The lengths $\mathbf { \eta } ^ { ( \theta ) }$ of phase-delay lines for these three unit cells of $0 ^ { \circ }$ phase shift should be $\theta = 3 5 ^ { \circ }$ $4 0 ^ { \circ }$ ,and $7 0 ^ { \circ }$ ,respectively.It is observed that, these three unit cells behave differently on frequency performance for reflection phases.When frequency changes, unit cell with orthogonal gaps shows smallest phase variation among the working frequency band $8 { \sim } 1 2 ~ \mathrm { G H z }$ ，Therefore, bandwidth performance of the reflectarray elements can be obviously enhanced by adding orthogonal gaps.

![](images/b61b4be6e3a22665819cbb5e4504dbb4ed0f3251561f12a130154ce2e302a9e1.jpg)  
Fig.4.Phase distribution of the designed reflectarray aperture.

![](images/169778c45770f2a0bd81f25d844a06894b4a2d1bafdfef12d4213c05abe3e06f.jpg)  
Fig.5.Layout and element arrangement of the designed reflectarray.

# III.REFLECTARRAY ANTENNAWITHPROPOSED UNIT CELL

In this section，an X-band offset-fed reflectarray with diameter $D = 2 8 5 \mathrm { \ m m }$ is designed,manufactured,and tested to validate the broadband feature of the novel unit-cell structure.

The required reflecting phases for all unit cells on the reflectarray plane are calculated at $1 0 \mathrm { G H z }$ ,according to(1)

$$
\phi _ { R } = k _ { \scriptscriptstyle 0 } \cdot \big ( d _ { \scriptscriptstyle i } - \big ( x _ { \scriptscriptstyle i } \cos \varphi _ { \scriptscriptstyle 0 } + y _ { \scriptscriptstyle i } \sin \varphi _ { \scriptscriptstyle 0 } \big ) \sin \theta _ { \scriptscriptstyle 0 } \big )
$$

where $k _ { 0 }$ represents the propagation constant in free space, $d _ { i }$ is the distance between the phase center of the feed source and the center of the ith unit cell on the reflectarray plane, $( \theta _ { 0 } , \varphi _ { 0 } )$ is the designed main beam radiation direction.Here,to avoid feed blockage, a $1 0 ^ { \circ }$ offset-fed design is selected for the reflectarray antenna to produce a main beam in the specular reflecting direction,which means $( \theta _ { 0 } , \varphi _ { 0 } )$ is set to be $( 1 0 ^ { \circ } , 0 ^ { \circ } )$ . An X-band pyramid horn of linear polarization is utilized to be the feed source and the path between the feed source and the reflectarray center is designed to be $2 2 5 ~ \mathrm { \ m m }$ ，which equals to a focus/diameter(F/D） ratio of O.79.The unit cell phase responses are designed to compensate for the spatial phase delays between the feed source and reflectarray unit cells.

![](images/7c010d98cdfee1641c2f0c2d451892e32684e414c2a478eef7313de9b4e7d674.jpg)  
Fig.6.Measurement setup of the designed reflectarray antenna.

Fig.4 shows the designed phase distribution on the aperture at $1 0 \ \mathrm { G H z }$ ，and Fig.5 shows the photo of the fabricated reflectarray which is composed of 277 unit cells forming an octagon-shape aperture.One can further see fromFig.5 that the unit cells are placed in a mirror symmetric arrangement in order to decrease the cross polarization[7].Fig.6 shows the setup for the measurement where a fiberglass is utilized to support the feed horn while minimize the feed blockage.

Fig.7 and Fig.8 show the measurement radiation patterns of co-polarization and cross-polarization (X-pol) at frequencies among 1-dB gain band in E-plane and $\mathrm { H }$ -plane,respectively.As can be seen, a gain of about 26.38 dBi at $1 0 \mathrm { G H z }$ is achieved, which means about $5 1 . 3 \%$ efficiencyis realized.The measured cross-polarization levels of both principal planes (E-plane and H-plane） are suppressed below $^ { - 2 6 }$ dB among the working frequencybandbenefitedfrom thespecial elements arrangement design.Besides,the realized side lobe levels for both principal planes are $- 1 7 . 5 { \mathrm { ~ d B } }$ and $- 1 5 { \mathrm { ~ d B } }$ at $1 0 ~ \mathrm { { G H z } }$ respectively.BothFig.7 andFig.8 demonstrate the broadband performance well because the measured radiation patterns within the 1-dB bandwidth remain stable.

Fig.9 plots the measured gain curve against frequency, from which one can see that the 1-dB bandwidth is about $20 \%$ $( 9 . 7 4 \mathrm { - } 1 1 . 8 ~ \mathrm { G H z } )$ ）while the 3-dB bandwidth is about $28 \%$ $( 9 . 5 5 { - } 1 2 . 3 5 ~ \mathrm { G H z } )$ . One can observe that a drastic gain drop occurs when the frequency is below $9 . 8 ~ \mathrm { G H z }$ ，and the main reason is due to the narrow operating band of the feed horn.In fact,the phase center of the feed horn can deviate when the frequency is lower than $9 . 8 ~ \mathrm { G H z }$ ，which results in significant phase errors.Besides,the widerbeamwidth of the feed hornat lower frequency also decrease the efficiency of the antenna, especially for the offset-fed reflectarray antenna of our case. This is these two major reasons to lead to the actual central frequencydeviated from $1 0 \ : \mathrm { G H z }$ to about $1 0 . 8 ~ \mathrm { G H z }$ .We can further observe some ripples exist on the measured gain curves and this is the result of the multiple reflections between feed horn,reflectarray plane and the probe.Besides,the system measurement errors can also lead to this kind of phenomenon.

![](images/b85376f4be6bb323c28e5eb04f9a00cb962bbd00a0ef329af5235f12dbe3d3c4.jpg)  
Fig.7.Measured co-polar and cross-polar radiation patterns of E-plane.

![](images/06307bb60e3e2382c9da58c9a4fadd0702301b4a05911687e22cf434a0c2ca09.jpg)  
Fig.8.Measured co-polar and cross-polar radiation patterns of H-plane

![](images/97a2f1c58b05525f2812f25363655c76c2357e371184d0573e3f4cbd8b51bf48.jpg)  
Fig. 9.Measured gain versus frequency.

TABLE IICOMPARISON OFTHEBANDWIDTHPERFORMANCEWITHPREVIOUSWORKSONANTENNASUSING PHASE-DELAYLINES  

<html><body><table><tr><td>Reference</td><td>Our work</td><td>[5]/[7]</td><td>[8]</td><td>[9]</td></tr><tr><td>Center Frequency (GHz)</td><td>10</td><td>11.7</td><td>10.3</td><td>8.5</td></tr><tr><td>1-dB Gain Bandwidth (%)</td><td>20</td><td>-</td><td>10</td><td>16.5</td></tr><tr><td>3-dB Gain Bandwidth (%)</td><td>28</td><td>18</td><td>15.5</td><td>-</td></tr><tr><td>Polarization</td><td>Linear</td><td>Linear</td><td>Circular</td><td>Linear</td></tr></table></body></html>

The measurement results of Fig.9 demonstrate that an obvious improvement on the gain bandwidth performance is achieved compared to the previous works[5],[7],[8],[9],as describedin TABLEII.

# IV．CONCLUSION

A novel single-layer unit cell with phase-delay lines is proposed for reflectarray antennas with enhanced bandwidth performance achieved. The geometry dimensions of double split rings as well as the lengths of phase-delay lines are optimized to realize parallel phase responses in a wide frequency range.A 277-element offset-fed reflectarray with octagon-shape aperture operating at $\mathrm { \Delta } \mathrm { X }$ band is designed, fabricated,and measured. The measurement results of $20 \%$ 1-dB gain bandwidth demonstrate that an obvious improved bandwidth performance is achieved compared with the previous reflectarrays using phase-delay-lines.We should address that although our current 1-dB gain bandwidth is smaller than that of [6],our approach can be easily extended to further enhance the bandwidth by adding one more gapped ring into the resonant structure.In fact, $3 6 . 3 \%$ 1-dB gain bandwidth has been achieved in this way and the brand new results have been addressed by another paper.

# REFERENCES

[1] J.Huang,J.A.Encinar,“Reflectarray antennas,"(Wiley,2007).   
[2] D.M.Pozar,"Bandwidth of reflectarrays,”Electronics Letters,vol.39, no.21,pp.1490-1491,Oct.2003.   
[3] E.Carrasco,M.Barba,andJ.A.Encinar,“Reflectarray element based on aperture-coupled phases with slots and lines of variable length,”IEEE Trans.Antennas Propag.,vol.55,no.3,pp.820-825,Mar.2007.   
[4] J.A.Encinar and J.A. Zornoza,“Broadband design of three-layer printed reflectarrays,”IEEE Trans.Antennas Propag.,vol.51,no.7,pp.1662- 1664, Jul. 2003.   
[5] H.Hasani,M.Kamyab,and A.Mirkamali,“Broadband reflectarray antenna incorporating disk elements with attached phase-delay lines,' IEEE AntennasWireless Propag.Lett.,vol.9,pp.156-158,2010.   
[6] M.R.Chaharmir and J.Shaker，“Broadband reflectarraywith combination of cross and rectangle loop elements,”Electronics Letters, vol.44,no.11,pp.658-659,May.2008.   
[7] H.Hasani,M.Kamyab,and A.Mirkamali,“Low cross-polarization reflectarray antenna,”IEEE Trans. Antennas Propag.,vol.59,no.5, pp. 1752-1756,May 2011.   
[8] R.Shamsaee and Z.Atlasbaf,“Design and implementation of a broadband single layer circularly polarized reflectarray antenna,”IEEE Antennas Wireless Propag.Lett.,vol.11,pp.973-976,2012.   
[9] I.Derafshi，N.Komjani，and M.Mohammadirad,"Single-Layer Broadband Reflectarray Antenna by Using Quasi-spiral Phase Delay Line,"IEEE Antennas Wireless Propag.Lett.,vol.14,pp.84-87,2015.   
[10] T.Smith,U.V.Gothelf,O.S.Kim,and O.Breinbjerg，“Design, manufacturing,and testing of a 2O/3O GHz dual-band circularly polarized reflectarray antenna,”IEEE Antennas Wireless Propag.Lett, vol. 12,pp. 1480-1483,2013.   
[11] C.H. Han,Y.H. Zhang,and Q. S. Yang,“Single-Layer Reflectarray Antennas with Improved Bandwidth by Attaching Phase-Delay Lines,” presented at European Conference on Antenna and Propagation (EuCAP), Davos, Switzerland,April 10-15,2016.   
[12]P.Nayeri,F.Yang and A.Z.Elsherbeni,“A Broadband Microstrip ReflectarrayUsingSub-WavelengthPatchElements",IEEE International Symposium on Antennas and Propagation,Charleston,SC, June 1-5,2009.