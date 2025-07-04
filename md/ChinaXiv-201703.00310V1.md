# A broadband Ku-Band microstrip reflectarray antenna using single-Layer fractal elements

Fei Xue12, Hong-Jian Wang², Min $\boldsymbol { \mathsf { Y } } \boldsymbol { \mathsf { i } } ^ { 2 }$ , and Guang Liu²

1University of Chinese Academy of Sciences，Beijing, 100049.China   
²The Key Laboratory of Microwave Remote Sensing, National Space Science Center， Chinese Academy of Sciences,Beijing100190, China   
E-mail: 07083003xuefei@163.com   
ABSTRACT:A novel single-layer microstrip reflectarray element with fractal structureisproposed.AnsoftHFSSisused to analyze the reflect phase for the fractal elementin honeycomblattice.A 469-element prime focus microstrip reflectarray antenna composed ofthe proposed fractal elements is designed,manufactured and measured.The measured gainlevel of29.8dBisobtained at the centerfrequencyof13.58GHz with1-dB gainbandwidth of $1 5 . 3 \%$

Keywords: Reflectarray; fractal structure; single-layer; honeycomb lattice; broadband

# 1. INTRODUCTION

The conventional parabolic reflector antenna has been widely used in both military and civil field.Due to the increasingly high requirements for flexible communication system, the disadvantages of the traditional parabolic reflector antenna have become increasingly apparent, such as heavy, bulky and nonplanar. In order to avoid the disadvantages, efforts have been made to replace a parabolic reflector by its equivalent such as a microstrip reflectarray [1].A Reflectarray antenna consists of an array of microstrip patch elements,each one imparting an appropriate phase delay to the incident wave to produce a collimated beam in front of the antenna aperture plane.

The main limitation to reflectarray performance isthe narrow bandwidth,generally lower than5 percent and even less for large reflectarrays [2]. The element bandwidth and spatial phase delay dispersion are the two factors limiting the reflectarray bandwidth. However， for the moderategain antennas, the element bandwidth seems to be the main reason of bandwidth limitation [3]. The bandwidth of the radiating element can be improved by an appropriate design of the phase-shifter element.The F/D ratio must be large enough so that the incident field is locally a plane wave and the effect of the spatial phase delaycan be decreased.However,alargerF/D ratios will affect the illumination efficiency.Much effort has been made to improve the bandwidth [4-9]. In [4],a reflectarray element made up of double crossed loops of variable lengths printed on a conductor backed substrate has been demonstrated. A single-layer reflectarray was fabricated and measured, which showeda1 dB gain-bandwidth of $10 \%$ ,centered at 22GHz.In [5]，a significant improvement in bandwidth has been demonstrated using elements which allow true-time delay.

In [6],a novel bandwidth improvement method is proposed, whichcombinesthemultilayerapproachwiththe subwavelength element technique.A method is proposed to design three-layer printed reflectarrays with patches of variable size for broadband operation in [7],and significant bandwidth and gain stability improvements were obtained.In [8] and [9], multiresonant elements are used for broadband operation.

Inconventional microstrip patch antennas, dual-or multi-frequency operation can be obtained by employing multiple radiating elements or reactivelyloaded patch antennas or multi-frequency dielectric resonator antennas [1O].However thesemethodshaveincreasedthecomplexityand manufacturing cost of the antenna.Fractal-shaped antennas which combine the antenna design theory and fractal geometry have already been proved to have some unique characteristics that are linked to the geometrical properties of fractals.The microstrip reflectarray combines microstrip antenna design with the fractal technology to make full use of their advantages. The space-filling characteristic of fractal antenna makes the antenna miniaturization. The self-similarity of the antenna structure results in multi-frequency operation,which increases the bandwidth of the antenna. The self-loading property also broadens the useful bandwidth [11]. The miniaturization feature of fractal antenna is used in [12] to design a miniaturized reflectarrayunitcellofferingwide-angle scanning capabilities.The designed X-band fractal reflectarray cell givesan improved maximum scan angleof $5 0 ^ { \circ }$ Fractal-shaped patch-slot configurations have been studied as reflectarray unit cells in [13]. Variable-length slots on the ground plane have been used to adjusting the phase.It has been shown that fractal configurations can reduce the size of the reflectarray unit cell and increase the maximum phase swing.

A novel fractal microstrip element on a single layer substrate is presented in this paper.In order to achieve a larger reflection phase variation range with less slope than conventional single layer element,an air layeris inserted between the substrate and the ground plane.The novel fractal microstrip element can meet the requirements of reflection phase curve linearity and variation range,so it has a broad bandwidth characteristic.

![](images/a6024fdae17d273f485a0f8ae4eb1c6ef40eb9734bc65ae6ae23c1edf423253b.jpg)  
Figure 1Top view and side view of the fractal element with honeycomb lattice.

# I. ELEMENTDESIGNANDPHASECHARACTERISTICS

The reflectarray presented in this paper is composed of fractal microstrip elements on a grounded substrate. The impedance characteristics of the element vary with the size of the element, so it can be used to adjust the phase of the reflected electromagnetic wave. The configuration of the proposed fractal element is shown in Figure 1.The fractal element is a multi-resonant structure that demonstrates a larger phase range and a more linear phase variation than the conventional square or circular patch.It consists of two concentric hexagon rings and a hexagon where each side of the inner hexagon is equal to the adjacent outer hexagon multiplied by the factor of $k$ Each patch was etched on Rogers RT/duroid 588O laminates with relative permittivity of 2.2 and thickness of h1.The layer between the substrate and ground plane is an air layer whose relative permittivity is1 and thickness is h2 $? . \mathrm { ~ L ~ } = 1 3 ~ \mathrm { m m }$ is the lattice period of the element and equivalent to O.59 wavelengths at $1 3 . 5 8 ~ \mathrm { G H z }$ .To derive reflection coefficient of the element, simulations are analyzed using Ansoft HFSS that uses master-slave boundaries and Floquet ports to model periodic structures.Figure 2 shows the honeycomb lattice model of the fractal elementin AnsoftHFSS.

![](images/fe7efcfd8f251916cce7ce2caa22cdbf2df4eccda48e40d83f6560adfa6a7981.jpg)  
Figure2 honeycomb lattice model of the fractal element.

The phase of the reflection coefficient is dependent not only on elements size but also on the incident angle of the plane wave.When the incident angle is less than $4 0 ^ { \circ }$ ， the reflection phase difference between normal incidence and oblique incidence can be neglected [14]. Figure 3 shows reflection magnitude and phase of element at $1 3 . 5 8 \mathrm { G H z }$ for different $\theta$ (from $0 ^ { \circ }$ to $3 0 ^ { \circ }$ ）and $\varphi$ （ $0 ^ { \circ }$ and $9 0 ^ { \circ }$ ）with $_ { \mathrm { h 1 = 0 . 5 m m } }$ $\scriptstyle \mathtt { h } 2 = 3 \mathrm { m m }$ and $\mathrm { k } { = } 0 . 7 5$ ： $( \theta , \varphi )$ is the direction of incident wave.It can be concluded that $\theta$ and $\varphi$ have little influence on reflection magnitude and phase.Furthermore，the incident angles of elements close to the edge of reflectarray are around $3 0 ^ { \circ }$ Thus， the assumption that the elements are excited by a normal incident plane wave is qualified in this paper.

![](images/eec1b819f7f14dc8d6438c3c388da4ee2886894da7543f3a9567244f3dbb6984.jpg)  
Figure 3 Reflect phase and magnitude curve of element at $1 3 . 5 8 \mathrm { G H z }$ for different $\theta$ with $_ { \mathrm { h 1 = 0 . 5 m m } }$ $\scriptstyle \mathtt { h } 2 = 3 \mathrm { m m }$ and $\mathrm { k } { = } 0 . 7 5$ (a) $\scriptstyle \varphi = 0$ deg. (b) $\scriptstyle \varphi = 9 0$ deg.

A parametric study is carried out to optimize element structure in order to obtain a smoother reflection phase curve and improve the bandwidth.Figure 4 shows the influence of $k$ factor on phase variations.It can be concluded that a factor of 0.75 leads to a better linear reflection phase and enough phase variation range.Figure 5 and Figure 6 show the effect of variations in the thicknessofsubstrate and air layer, respectively.

![](images/b73f9fb186b06d7af5a9ba7acb97b74f518387beb9825bf76803686c846180bf.jpg)  
Figure 4 Phase-size characteristics of the proposed fractal element for different $k$ at $1 3 . 5 8 \mathrm { G H z }$ for normal incidence.( $_ { \mathrm { h 1 = 0 . 5 m m } }$ $\scriptstyle \mathtt { h } 2 = 3 \mathrm { m m } ,$ ！

![](images/bad349d52ad7f7f539c8ceb4799132a0dee04e88d972c19ed74ddf27e848e062.jpg)  
Figure 5Phase-size characteristics of the proposed fractal element fordifferenth1at $1 3 . 5 8 \mathrm { G H z }$ fornormal incidence.( $k { = } 0 . 7 5$ ${ \mathrm { h } } 2 { = } 3 { \mathrm { m m } } )$ 1

![](images/43dc75c2cb73e228c2af5f834b5e429b23be608a2b5df1554ec14d1592356289.jpg)  
Figure 6 Phase-size characteristics of the proposed fractal element fordifferent h2at $1 3 . 5 8 \mathrm { G H z }$ fornormal incidence. $k { = } 0 . 7 5$ $_ { \mathrm { h 1 = 0 . 5 m m } }$ ！

<html><body><table><tr><td>a1</td><td>a2</td><td>a3</td><td>a4</td><td>k</td><td>h</td><td>h2</td><td></td><td>L</td></tr><tr><td>ka</td><td>ka1</td><td>ka2</td><td>ka3</td><td>0.75</td><td></td><td>0.5mm</td><td>3mm</td><td>13mm</td></tr></table></body></html>

![](images/eab78e790a119989c252a1371564725d66a3b2acbacecd4ac356b83a4e6b207b.jpg)  
Figure 7 Phase-size characteristics for different frequencies (12.5-17GHz) for normal incidence with $k { = } 0 . 7 5$ ， $_ { \mathrm { h 1 = 0 . 5 m m } }$ and $\scriptstyle \mathtt { h } 2 = 3 \mathrm { m m }$

It can be concluded from Figure 5 that the substrate thickness has little influence on the reflection phase curse. Taking into account the manufacture factor, the thickness of the substrate is $0 . 5 \mathrm { m m }$ .It can be drawn from Figure 6 that the thickness of the air layer has great influence on the reflection phase curse,so the thickness of the air layer is $3 \mathrm { m m }$ for better linear reflection phase and large phase variation range.

With the result of parametric study, the fractal element with $k { = } 0 . 7 5$ $_ { \mathrm { h 1 = 0 . 5 m m } }$ and $\scriptstyle \mathtt { h 2 } = 3 \mathrm { m m }$ , is the results of optimization, as depicted in Table I. The reflection phase variation range is in excess of $4 3 0 ^ { \circ }$ with the element size changes within the range of $1 . 5 \mathrm { m m }$ to $6 \mathrm { m m }$ .Reflection phase curses versus element size for different frequencies (12.5-17GHz) are shown in Figure 7. The reflection phase curses almost parallel to each other that indicates the wideband property of the novel fractal element.

# 三. DESIGNREFLECTARRAYANDPERFORMANCE

In order to validate the proposed fractal structure，a prime-focus 469-element reflectarray is designed using the proposed fractal structure as phase-shift elements and the performances of the reflectarray are simulated and measured. The size D and focal distance F of the reflectarray are $3 2 5 \mathrm { m m } ( 1 4 . 5 \lambda _ { O } )$ and $2 6 0 \mathrm { m m }$ separately.A pyramidal antenna is used as the feed of the reflectarray. The phase center of the pyramidal antenna is placed at the focal point (F） of the reflectarray and the illumination level at the reflectarray edges is about 11 dB below the level at the aperture center. Figure 8 presents the photograph of the reflectarray prototype.Foam and bracket are used to fix the feed horn. The radiation pattern of the antenna is tested in the near-field anechoic chamber. Figure 9 shows the simulated and measured radiation patterns of the reflectarray antenna for copolar and cross-polar components both in E-plane and H-plane at the center frequency of $1 3 . 5 8 \mathrm { G H z }$ ：

As shown in Figure 9, the simulated antenna gain is 3O.O4 dB at the center frequency of 13.58GHz with the 3-dB beamwidth of $4 . 9 5 ^ { \circ }$ in both E-plane and H-plane.The simulated results of side lobe levels are below -18.8 dB with regard to the peak level. The measured gain levels $2 9 . 8 { \mathrm { ~ d B } }$ is obtained at 13.58GHz with the 3-dB beamwidth of E-plane and H-plane both are $4 . 9 6 ^ { \circ }$ .The measured side lobe levels are below -18dB with regard to the peak level of both the H-plane and E-plane. The measured cross-polarization levels are below -35dB for the E-plane and -28dB for the H-plane.The simulation results are performed using the real material in order to coincide with the measurement condition.In practice,the air layeris substituted bya cellular board.Besides,clear epoxy adhesive is used to bind the cellular board and substrate layer.

![](images/2ab5f56ae33596e23fdd7323f1e9d87b0d3c538b85714a29ffe7a3705b6c0eab.jpg)  
Figure 8 Photograph of the designed reflectarray.

![](images/f9baa90a8c120e4c9d380118749a729fa3a0c576103e442a3cc45adba8191403.jpg)

![](images/c677fe3b860409b51604c27f9471776182b8f40060f6e7ebb5c276087e99fb32.jpg)  
Figure 9 Normalized simulated and measured radiation pattern of the reflectarray antenna for copolar and cross-polar components at 13.58GHz.(a) E-plane.(b)H-plane.

![](images/460f4d2f4ecc99502580f94c11f0276a14c5231825e6189547fd79a5716afc83.jpg)  
Figure 1o Measured radiation gain of the reflectarray antenna with frequency varying from $1 2 . 5 8 \mathrm { G H z }$ to $1 6 . 5 8 \mathrm { G H z }$ ：

The measured peak gainsagainst frequenciesfrom $1 2 . 5 8 \mathrm { G H z }$ to $1 6 . 5 8 \mathrm { G H z }$ are shown in Figure 1O.It can be concluded that the measured bandwidth, defined from the gain variation with frequency(1 dB drop in peak gain is considered), reaches $1 5 . 3 \%$ . The small difference between simulation and measured results are due to the fabrication and the measurement errors.The blockage of the foam and bracket and the feed misalignment are the reasons for the disagreement between simulations and measurements as well.

# IV.CONCLUSIONS

A novel fractal microstrip reflectarray element with a single-layer substrate has been proposed and studied. The analysis of the fractal element shows that the proposed element can provide sufficient phase variation range with good linear reflection phase and gentle slope.The reflection phase curses of different frequencies indicate that the fractal element has broadband property.A concentric circle reflectarray which is composed of lots of the proposed fractal elements is designed, fabricated and measured. The measured 1-dB gain bandwidth reaches $1 5 . 3 \%$ ·

# REFERENCES

1．F.E.Tsai and M.E.Bialkowski,Designing a 16l-element Ku-band microstrip reflectarray of variable size patches using an equivalent unit cell waveguide approach,IEEE Trans Antennas Propag 51(2003),2953-2962.   
2．D. Cadoret,A.Laisne,R.Gillard,L.Le Coq and H.Legay,Design and measurement of new reflectarray antenna using microstrip patches loaded with slot,ElectronicsLetters 41(2005),623-624.   
3．J.Huang and J.A.Encinar,Reflectarray Antennas.Hoboken,NJ,USA: Wiley,2008.   
4．M.R.Chaharmir,J. Shaker,M.Cuhaci,and A.Ittipiboon,Broadband reflectarray antenna with double cross loops,ElectronicsLetters 42 (2006), 65-66.   
5．E.Carrasco,J.A. Encinar and M.Barba,Bandwidth improvement in large reflectarrays by using true-time delay,IEEE Trans Antennas Propag 56 (2008),2496-2503.   
6．P.Nayeri,F.Yang,and A.Z.Elsherbeni,Broadband reflectarray antennas using double-layer sub-wavelength patch elements,IEEE Antennas Wireless Propag Lett9 (2010),1139-1142.   
7．J.A.Encinar,J.A. Zornoza,Broadband design of three-layer printed reflectarrays,IEEE Trans on Antennas and Propag 51 (2O03),l662-1664.   
8. Qin-Yi Li，Yong-Chang Jiao and Gang Zhao,A Novel Microstrip Rectangular-Patch/Ring-Combination Reflectarray Element andIts Application,IEEE Antennas Wireless Propag Lett 8 (2009),l119-1122.   
9.K.H. Sayidmarie and M.E.Bialkowski,Fractal unit cells of increased phasing range and low slopes for single-layer microstrip reflectarays, Microw,Antennas Propag 5 (2011),1371-1379.   
10.Hara PrasadRV,Purushottam Y,Misra VC,Microstrip fractal patch antenna for multiband communication,Electronics Letters 36 (2000), 1179-1180.   
11.Carles P.B.,Jordi R.,Angel C.,The Koch Monopole:A Small Fractal Antenna,IEEE Trans Antennas Propag 48 (200O),1773-1781.   
12.S.Costanzo and F.Venneri,Fractal shaped reflectarray element for wide angle scanning capabilities,2O13 IEEE AP-S International Symposium, Orlando,July 2013,pp.1554-1555.   
13.D.Oloumi et al.,Miniaturized reflectarray unit cell using fractal-shaped patch-slot con figuration,IEEE Antennas Wireless Propag Lett 11(2012), 10-13.   
14.S.D.Targonski and D.M.Pozar,Analysis and design of a microstrip reflectarray using patches of variable size,1994 IEEE AP-S/URSI International Symposium,Seattle,June 1994,pp.182O-1823.