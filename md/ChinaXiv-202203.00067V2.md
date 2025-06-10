# Study on laser shocking of melt pool in Laser Additive Manufacturing of FeCoCrNi High-Entropy Alloys

Heng Lu ä, Xiaohan Zhanga, Jian Liua, Shusen Zhaob, Xuechun Linb, Hui Li ä, Yaowu Hu äa \* äThe Institute of Technological Sciences, Wuhan University, Wuhan,430072,China b The Institute of Semiconductors,Chinese Academy of Sciences,Beijing,10o083, China

# Abstract:

The growing interest in Laser Additive Manufacturing (LAM) High-entropy alloys (HEAs） during most recent years,the design of elements and scanning strategies are primary methods to overcome the defects such as porosity, pores, and segregation etc. Here we propose a new approach,a novel real-time Laser Shocking of Melt Pool (LSMP),to obtain melt pool modifications to yield beter HEAs.LSMP moves a pulsed laser into a liquid melt pool caused by a continuous wave laser, enabling non-destructive and real-time fabrication of high-performance HEAs. The numerical simulation reveals the convection mechanism of the melt pool in the LSMP process,and the intervention of the pulsed laser promotes melt pool flow type to convert the Marangoni eect into a multi-convective ring, which accelerates melt pool flow and the columnar crystal growth is significantly inhibited. Experimental results show the evolution law of the microstructure in the LSMP process. CrFeCoNi HEAs forms a stable FCC structure without segregation and other defects. Meanwhile,the microstructure undergoes a Columnar-Equiaxed Transition (CET),and CrFeCoNi HEAs with higher nano-hardness are obtained. Furthermore,the reduction in the (111) interplanar spacing demonstrates laser shock induces beneficial compressive stress. Therefore,it is necessary to consider introducing laser shock at appropriate conditions to control the melt pool online.

Keywords: Laser shock; High-entropy alloys; Melt pool; Laser Additive Manufacturing

# 1. Introduction

As a new type of material, Yeh et al.[1] broke the traditional design concept of a single metal as the main element and created High-Entropy Alloys (HEAs) with excellent performance.It has brought a new dawn for the development of new alloy systems,which have received extensive attention in many fields of basic research and engineering manufacturing. But, typical metallurgical defects such as porosity,pores,and segregation in conventional as-cast HEAs affect the final properties,which limit the potential application of HEAs.Fortunately, Brief et al.[2] firstly used Laser Additive Manufacturing (LAM） technology to obtain HEAs with beter mechanical properties than as-cast samples, demonstrating the feasibility of LAMed HEAs. It not only shortens the process cycle but also provides a faster and more effcient method for manufacturing complex HEAs parts. Besides,Moghaddam et al.[3] presented a conclusion of current state and future prospects of additive manufacturing (AM) of HEAs.

Among many HEAs systems,laser additive manufacturing FeCoCrNi-based HEAs is the earliest and most extensive. Zhou et al. [4] fabricated carbon-containing FeCoCrNiC $0 . 0 5$ HEAs by Selective Laser Melting (SLM). The aloy structure is a single face-centered cubic (FCC) without carbide phases, and the carbon distribution in the samples prepared under optimal parameters is uniform. Zhu et al.[5] prepared the CoCrFeNiMn HEAs by SLM,the distribution of each element is uniform,and Mn is slightly segregated at the melt pool boundary. Besides, Peyrouzet et al.[6] used SLM process to obtain $\mathrm { A l } _ { 0 . 3 }$ CoCrFeNi HEAs with a tensile strength of up to 896 MPa and a yield strength of $7 3 0 \mathrm { M P a }$ ，which is also a single FCC structure. Obviously, more and more scholars such as Li et al.[7] have transferred the research focus on HEAs to the performance of materials.

However,the high thermal stress caused by the thermal cycle of the melt pool during the LAM process also brings many hazards. Zhang et al.[8]observed cracks in the CoCrFeNiMn HEAs samples obtained under different scanning strategies,resulting in low densities.Niu et al.[9] also found the same result. And many scholars have joined the ranks to solve this problem. For example, Jiang et al. [10] shows the presence of FCC phase significantly reduces the internal stress of the specimen by the addition of Fe-based amorphous.In addition,the indeterminate cooling rate of the melt pool,a critical factor, also directly affects the recrystallization species,leading to various types of HEAs with different properties. Li et al.[11] reveals the formation mechanism of microstructures in HEAs rapidly cooled to room temperature at nanoscale through Molecular dynamics (MD) simulation. At present, most HEAs prepared by Laser Melting Deposition (LMD) exhibit a typical dendritic structure, because the scan rate of LMD is significantly lower than that of the SLM process, causing a low cooling rate so that equiaxed crystals cannot be achieved. Therefore, Tong et al.[12] found the microstructure of the CoCrFeNiMn HEAs fabricated by LAM is mainly columnar crystals inside the melt pool, while the outside of the melt pool is equiaxed grains. After heat treatment at $1 1 0 0 ^ { \circ } \mathrm { C }$ , the structure is completely equiaxed grains. Certainly,subsequent heat treatments such as Knowles et al.[13] used a range of annealing processes after Direct Metal Laser Sintering (DMLS） and Li et al.[7] applied the Hot isostatic pressng (HIP) after SLMed HEAs are detrimental to the continuity and production efficiency of the AM proces However, Tong et al.[14] shows different process parameters such as laser power and scanning speed in the LAM process can directly obtain different microstructures because the ratio of the thermal gradient and solidification rate inside melt pool is the dominant factor in Columnar-Equiaxed Transition (CET).

Thence,the online regulation of the melt pool to get the better structure in the LAM process is particularly important. The Laser Shock Peening (LSP) as a advanced technology which not only induced high compressive stress on the surface of metal components and structures but also achieved to control at the micro-nano level.For example,Hu et al.[15,16] realized ultrafast direct fabrication of plasmonic nanoarrays by LSP. A novel synchronous Laser Shocking of Melt Pool (LSMP) method is proposed to suppress thermal stress,enhance melt pool convections and inhibit columnar crystal growth.Not only that, it extends the efort that Tong et al.[14] used the LSP as a post-processing treatment to in-situ modification to improve the LAMed HEAs. Although the pulsed laser is widely used in material properties strengthening，to our knowledge there had not been any research on synchronous hybrid additive manufacturing processes with laser shocking of melt pool to overcome the surface tension of liquid metal. In this paper, the action mechanism of LSMP by combining experiments and numerical simulations is studied. We reveal the convection mechanism inside the melt pool with the assistance of pulsed laser. As a result,the microstructure evolution law of HEAs produced by LSMP is obtained,achieving non-destructive real-time production of higher-performance CoCrFeNi HEAs.

# 2.Material and Methods

# 2.1.Materials and Experiment

The LSMP method moves the pulsed laser into a melt pool of liquid high-entropy alloy produced by a continuous wave (CW) laser,as shown in Fig. 1(a).A size of $3 0 \ \mathrm { m m } \times 3 0 \ \mathrm { m m } \times 1 \ \mathrm { m m } \ 4 5$ steel, cleaned with ethanol solution after polishing to ensure cleanliness,was used as the substrate.The experimental material adopts the equiatomic CrFeCoNi powder prepared by vacuum atomization. The particle size is $1 5 { \sim } 4 5 { \mu } \mathrm { m }$ . It has good fluidity and sphericity. The powder morphology and composition analysis are shown in Fig.1(b) and (c). The thickness is 1mm. The experimental equipment includes a 1kW continuous wave (CW) fiber laser (Shenzhen Chuangxin Laser Co.,Ltd.） and a pulsed laser. The

Selective Laser Melting (SLM) process is carried out in a high-purity argon atmosphere with a gas supply rate of 3L/min. The process parameters are laser power 8OoW，platform moving speed $1 0 0 0 \mathrm { r / m i n }$ ，and spot diameter $3 \ \mathrm { m m }$ .The pulsed laser process parameters are laser energy 3J, pulse width 1Ons,repetition frequency $1 0 \mathrm { { H z } }$ ,and spot diameter $1 \mathrm { m m }$ . The CW laser beam is perpendicular to the substrate,and the pulsed laser beam deviates from the vertical by $- 1 0 ^ { \circ }$

![](images/8c17f4cebc6a947076445b6dbe7efdaf7b6a7a975e93f8a6c69a39983eedf80f.jpg)  
Fig.1.(a)Experimentalschematicdiagram,(b)theSEMimageof CreCoNipowder,(c)theEDSanalysisofCrFeCoNi powder.

# 2.2.TestMethods

Different samples were tested from three perspectives: molding process, microstructure and phase composition to mechanical properties. First of all， the Chronos1.4 high-speed camera (Kron Technologies, Canada） was used to monitor the manufacturing process,and the NewViewTM 9000 Series white light interference 3D profiler (ZYGO,The United States) was used to measure the profile of the sample. Secondly, the sample was moved along the normal direction,then it was corroded by aqua regia (hydrochloric acid: nitric acid $\scriptstyle = 3 : 1$ ）for 6O seconds after polishing and cleaning the cross-section. The microstructure and the Energy-dispersive Spectroscopy (EDS) tests passed the BX51 optical microscope (OLYMPUS, Japan) and the MIRA3 scan electron microscope (SEM) (Tescan, The Czech Republic). To understand the phase composition of the original CoCrFeNi powder and the samples, the D8 ADVANCE X-ray difractometer (XRD) (Bruker, The German) was used for detection. The target material was copper and the scanning angle was $2 0 { - } 9 0 ^ { \circ }$ ,， the scanning speed is $5 ^ { \circ } / \mathrm { m i n }$ Finally,the iNano nanoindenter (KLA-Tencor, The United States） with a load of $5 0 \mathrm { m N }$ was used to obtain the mechanical properties of the samples along the upper, middle,and bottom of the section.

# 2.3. Calculation

Molecular dynamics (MD) simulation: An radius $1 5 \mathrm { \AA }$ iron sphere with an initial velocity apply an initial velocity $( V _ { O } )$ to the LSMP based on the following equations:[17,18]

$$
P ^ { 2 } ( \tau ) = m I _ { 0 } \alpha / 2 \tau ( \alpha + 1 )
$$

$$
V _ { \mathrm { 0 } } { = } 2 P ( \tau ) \tau / m
$$

where $I _ { O }$ is the nominal laser intensity, $\tau$ is the pulse duration,m is the mass of iron sphere, $P$ is the pressure generated during laser irradiation,and $\scriptstyle a$ is the factor to account for the increase of plasma thermal energy by the absorbing laser irradiation.A typical velocity of $1 \mathrm { k m s } ^ { - 1 }$ is applied,which yields a peak pressure of O.33Gpa based on the formula (1O) in the present case.CoCrFeNi HEAs y and iron sphere are single crystals with FCC and Body-centered cubic (BCC) structures,respectively, their lattice constants are $3 . 5 6 \mathrm { ~ \AA ~ }$ and 2.863 A. The modified embedded atom method (MEAM) in C style was used in the calculation,Mi et al.[19] calculated the potential function suitable for HEAs,which was used in this simulation. And the NVT ensemble was applied, warming up to $2 0 0 0 \mathrm { ~ K ~ }$ with a 0.001 ps time step.

Based on the finite element idea,a three-dimensional numerical model of the interaction between the laser and the melt pool is established to predict the temperature field during SLM process.In order to not afect the calculation quality,the following assumptions are put forward: 1. The plasma and metal vapor are ideal gases; 2. The effect of the shielding gas on the welding process is ignored. 3.

Computational fluids are laminar and Newtonian incompressible fluids.

Conservation equations: The fluid flow and heat transfer process in the LAM process mainly include the conservation equations of mass,momentum,and energy: [20, 21].

Conservation of mass:

$$
\frac { \partial } { \partial t } ( \rho ) + \nabla ( \rho \vec { V } ) = 0
$$

Conservation of momentum :

$$
\frac { \partial } { \partial t } ( \rho \vec { V } ) + \nabla ( \rho \vec { V } \vec { V } ) = \nabla ( \mu \nabla \vec { V } ) - \nabla P - \frac { \mu } { K } \vec { V } + \rho g
$$

Conservation of energy :

$$
\frac { \partial } { \partial t } ( \rho h ) + \nabla ( \rho \vec { V } h ) = \nabla ( k \nabla T )
$$

where $\rho$ is the fluid density, $V$ is the fluid velocity, $t$ is the time; $\mu$ is the fluid viscosity, $P$ is the pressure, $K$ is the isotropic permeability, $g$ is the gravity; $T$ is the temperature, $h$ is the material enthalpy, and $k$ is the thermal conductivity.

Laser heat source is seted as Gauss volume heat source model:[22]

$$
{ \bf q } _ { l a s e r } = { \frac { 9 \alpha _ { a b s } { \cal Q } } { \pi { \cal R } _ { 0 } ^ { 2 } H ( 1 - e ^ { - 3 } ) } } \exp \biggl [ { \frac { - 9 ( x ^ { 2 } + y ^ { 2 } ) } { { \cal R } _ { 0 } ^ { \ 2 } \log ( H / z ) } } \biggr ]
$$

where $\boldsymbol { Q }$ is laser power, $H$ is the height of the laser heat source, $a _ { a b s }$ is the absorption rate of the

material to the laser heat source,and $R _ { O }$ is the effective radius of the laser beam.In theory,more than $9 5 \%$ of the total energy of the laser beam is concentrated in the area with $R _ { O }$ as the radius.

Driving force: For recoil pressure,a widely accepted model is expressed by:[23]

$$
P _ { r } \cong 0 . 5 4 P _ { \scriptscriptstyle 0 } \exp \left( \Delta H _ { \scriptscriptstyle L V } \frac { T - T _ { \scriptscriptstyle L V } } { R T T _ { \scriptscriptstyle L V } } \right)
$$

where $P _ { 0 }$ is the atmospheric pressure, $R$ is the universal gas constant, $\varDelta H _ { L V }$ is the vaporization enthalpy of the liquid metal, $\mathrm { T } _ { \mathrm { L V } }$ is the liquid-gas equilibrium temperature of the material under a certain

pressure, $\varDelta V _ { L V }$ is the difference between the specific volumes of liquid and gas,and $V _ { L V }$ is the specific volume of the gas.The surface tension can be expressed as a function of temperature:[20]

$$
\gamma = \gamma _ { \mathrm { { 0 } } } + { \frac { \mathrm { { d } } \gamma } { \mathrm { { d } } T } } { \left( T - T _ { \mathrm { { 0 } } } \right) }
$$

Marangoni force formed on the surface of fluid which can be expressed by:[20]

$$
F _ { \gamma - i } = - \frac { \partial \gamma } { \partial T } \frac { \partial T } { \partial x _ { i } }
$$

where $T$ is the liquid surface temperature, $T _ { 0 }$ is the reference temperature,and $\gamma _ { 0 }$ is the surface tension at $T _ { 0 }$ temperature,Fy-i is the Marangoni force formed by the surface tension gradient in the i direction, $\boldsymbol { \gamma }$ is the surface tension,and“-” indicates that the direction of the force is opposite to the gradient direction of the surface tension.

Pulse pressure: The pulse pressure is the force formed by accelerating the impact on the surface of the molten pool in the vertical direction，and its direction is vertically downward.According to theoretical analysis and experimental verification, the pulse pressure formula is as follows:[24]

$$
P _ { \mathrm { m a x } } ( \mathrm { G P a } ) = 0 . 0 1 \sqrt { \frac { \alpha } { 2 \alpha + 3 } } \sqrt { Z } \sqrt { I _ { 0 } }
$$

where $P _ { \mathrm { m a x } }$ is the pulse pressure, $ { \boldsymbol { a } }$ is the efficiency of the interaction, $Z$ is the reduced shock impedance, $I _ { 0 }$ is the laser power density.

Geometric model and boundary conditions: As shown in Fig.2, the computational domain is 30 $\mathrm { m m } \times 7 ~ \mathrm { m m } \times 1 0 ~ \mathrm { m m }$ with the grid resolution of $0 . 1 5 ~ \mathrm { m m }$ ， $5 ~ \mathrm { m m }$ fluid region represents the HEAs powder, and $5 ~ \mathrm { m m }$ void region represents the atmospheric environment and serves to observe the free surface.For each boundary,the energy and pressure boundary balance conditions are required. The implicit SOR and VOF algorithms are used to obtain and update free surfaces through self-defined functions,and boundary conditions are imposed on all meshes until the end of the calculation.

![](images/9357f044792f9c51da72c21898cae787420bb63235aa09ac1f8bcd172ee60fce.jpg)  
Fig.2.The schematic diagram of computational domain.

# 3.Results and discussion

# 3.1. Surface topography

To explore the evolution of LSMP,real-time images of the melt pool under the two processes were collected as shown in Fig.3 and Video 1 (Supplementary material).Fig.3(a) records the real-time process of the melt pool in the SLM process. CW laser input fully melts the CoCrFeNi powder and gradually converges into a plump melt pool in the front of the solidification zone. In the LSMP process, the melt pool exhibits different characteristics.In Fig.3(b), the plasma clusters induced by the pulsed laser can be observed.The most important thing is that the pulsed laser drives and changes convection in the melt pool through the shock wave.In the transient process of $3 . 8 7 \mathrm { m s }$ , the surface area of the melt pool expands firstly after each laser shock,

![](images/11889942b165961bdf9e67c138fc99c10501dd822523a73357ef269d6745a2d6.jpg)  
Fig.3.Real-time images of melt pool evolution: (a) SLM treatment; (b) LSMP treatment

which is beneficial for the escape of heat in the melt pool and increases the cooling rate.Then,the surface tension makes the melt pool return to its original state to wait for the next pulsed laser. The melt pool cools faster throughout the manufacturing process.

3D profile data also confirmed this result, CW laser input full melts the CoCrFeNi powder and results in an arc-shaped melt pool as shown in Fig. 4(b),but this will cause the heat in the melt pool to fail escape quickly. Combined with Fig. 4(c),the most striking feature of the LSMP processis that the profile of the melt pool has changed,and the size of the melt pool has become wide and flat.The height of the melt pool has decreased and the width of the botom has increased,but this has not damaged the molding process.On the contrary,this phenomenon indirectly indicates that the cooling rate of the being shaken melt pool is increased,and it has solidified before returning to its original arc-shaped state. Owing to the conventional cooling method the heat source exists in the center of the chill layer is broken in the LAM process.

![](images/5ca0e3f793fe0fe89c7fca9df624f701eaeb2cb86177ac4294a7bc2fb56bc538.jpg)  
Fig.4.3Dtopographyandsectionprofileof melt poolunderdiffrent processes: (b)SLMtreatment; (c)LSMPtreatment.

# 3.2.Evolution of cooling rate

Changes in melt pool morphology are atributed to cooling rate.As a result, The CoCrFeNi HEAs model was established in MDas shown in Fig. 5(a).Fig. 5(c) shows the liquid melt pool oscilltes after being stressed, obvious deformation occurs at the top and spreads around. The shock wave propagates in three-dimensional directions and the melt pool quickly recovers to its original state.Apparently, similar results also appeared. After cooling,the size of the melt pool is different to that of SLM model, and becomes wide and flat.The changes in the melt pool profile also agree with the 3D profile data.

More cooling process under different time steps as shown in Fig. A1 (Supplementary material).

![](images/a4bcf68061acbcfb9ab3b58735faa05e59d5df30dd9f0fa147ab0382bbb26ced.jpg)  
Fig.5.Melt poolevolutionbasedonMolecularDynamics: (a)melt pool model; (b)SLM treatment;(c)LSMPtreatment.

The evolution of cooling rate is divided into two parts. From a microscopic perspective, the atoms inside the melt pool willaccelerate after being forced,which is one of the reasons for the increased cooling rate.Liu et al.[25] often used the Mean Square Displacement (MSD) to study the motion of atoms ina system:

$$
M S D = \frac { 1 } { N } { \sum _ { \mathrm { i } } ^ { N } } { \left[ r _ { i } \left( t + { \triangle } t \right) - r _ { i } \left( t \right) \right] ^ { 2 } }
$$

where $r i ( t )$ represents the position of atom $i$ at time $t$ ， $N$ is the number of atoms in the system,and $\varDelta t$ represents the change in time step. Fig.6 shows The MSD curves of atoms in the melt pool region under the two processes. A MSD vector of three quantities involve dx, dy and $\mathrm { d } \mathrm { z }$ in the LSMP are much larger than SLM as shown in Fig.6 (a),atoms inside liquid melt pool oscilates after being stressed and spreads around. In addition, there is another feature. The MSD hasan obvious jump and a linear relationship with time when the pulsed laser acts on the melt pool as shown in Fig.6 (b),indicating the movement ability of the atoms is particularly strong at this time,which will accelerate the heat dissipation. As the temperature decreases, the atoms in the melt pool area begin to arrange in a regular and orderly manner. When the solidification temperature is reached, the MSD curves tend to be horizontal,because they have formed a regular arrangement,only a slight relaxation at their equilibrium position. More results of MSD under diferent shock cases as shown in Fig. A2. (Supplementary material).

![](images/ebbba7050d5d529a38835260520c114d679638d8f62f71aa87b69dd1de1ec7cd.jpg)

Fig.6.TheMSDofatomsinthemeltpool,(a)thesquareddxdydzdirectionsdisplacements,(b)thetotalsquareddisplacement

From a macro perspective,the melt pool is driven and accelerated to flow, which is another reason for the increased cooling rate.The internal melt pool model is built to understand as shown in Fig.7,the CW laser energy input forms a beam of force,which moved down to the botom along the vertical centerline of the melt pool, and a symmetrical convection ring appears inside the plump liquid melt pool. Then it surges from both sides of the melt pool to the surface,forming the typical Marangoni effect. Khairrallah et al.[26] demonstrates the significant effect of the recoil pressure and Marangoni convection in laser powder bed fusion (L-PBF). However,the heat source stays in the middle and lower region and cannot escape as shown in Fig.7(a), which is the reason why high thermal stress is always present.Happily,this problem has been solved due to the asistance of pulsed lasers. It can be observed from Fig.7(b) the depresson appears in the top region because of the applied force,the original symmetrical convective ring is changed,and forming multiple convective loops at the top and bottom regions,respectively, which accelerates the flow, and prompting the heat source to move and dissipate quickly.

![](images/414849d58611a10924dee6240a27d68f1cfbfeb056e18c7e668a5d15a42e4b0a.jpg)  
Fig.7.Computed temperatureand vectors distributionunder diferent processes: (a)SLMtreatment; (b)LSMPtreatment

The temperature-time relationship of the internal melt pool model is extracted as shown in Fig.8. Clearly, different temperature profiles appeared under the two processes. The cooling rate $\scriptstyle { C = \boldsymbol { A } T / \boldsymbol { S } ^ { I } }$ per unit time is calculated, $_ { A T }$ is the temperature change, $S ^ { - l }$ is the unit time 1s. After reaching the temperature peak,LSMP solidifies rapidly with a cooling rate of $\boldsymbol { - 4 . 8 4 \times } 1 0 ^ { 2 } \mathrm { K / s } ^ { - 1 }$ ，which is better than SLM. Therefore,LSMP is beneficial to increase the cooling rate.

![](images/e025b24df8686d1be6e2313c70f56a59a96366251f262ba6ee251edccac05e95.jpg)  
Fig.8.The computed curve of melt pool between temperature and time.

# 3.3.Microstructure analysis

Based on the layer-by-layer manufacturing principle of LAM, CoCrFeNi powder is remelted and solidified due to heating,resulting in material structure changes,and the growth morphology of grains is closely related to the cooling rate. Under the SLM process,the cross-section of the melt pool shows a non-equilibrium structure composed of columnar dendrites and equiaxed dendrites as shown in Fig.9(a). From the local bottom boundary enlarged view of the melt pool, there is a good bond between the HEA and the substrate,indicating the formed sample has a good tensile ability. Columnar dendrites were observed at the bottom of the melt pool, growing upward perpendicular to the substrate boundaries.In the LAM process,the laser irradiation area is the center of the heat source,and the processed area belongs to the cooling layer, then a high-temperature gradient is formed between them,which driven the columnar dendrites to grow upward along the temperature gradient from the bottom of the melt pool as shown in Fig.9(b). Further, the solid and liquid lines inside the melt pool are promoted to show a directional solidification trend from the inside to the outside and the bottom to the top.When reaching the middle and upper region of the melt pool,a lower temperature gradient due to the distance from the heat source cannot drive the epitaxial growth of columnar dendrites.At the same time, the EDS results of the columnar dendrites in Fig.9(b)area show that Cr,Fe,Co,and Ni elements are uniformly distributed in the sample as shown in Fig.9(c),and no segregation defects appear. Lin et al.[27] also found columnar dendrites are one of the typical features of LAMed HEAs.

![](images/47deff2854d1fa57b14db5f60e1984133d545cf3a7b6a6e0e1e581355e121239.jpg)  
Fig.9.SamplesunderSLMtreatment:(a)The microstructureofthemelt polsection,(b)Thelocal SEMimageofcolumnar crystals,(c)TheEDSresultof in(b);SamplesunderLSMPtreatment:(d)Themicrostructureof themeltpoolsection,(e)The local SEMimage of equiaxed crystal,(f) The EDS result of points Aand B in (e).

In Fig.9(d) and (e),it is found the melt pool is an equilibrium structure composed of equiaxed dendrites. Apparently,a Columnar-Equiaxed Transition (CET) occurs. Hunt[28] proposed a model that when the volume fraction of equiaxed grains is $\phi { > } 0 . 4 9$ ,complete equiaxed dendrite growth occurs, and when the volume fraction of equiaxed grains is $\phi { < } 0 . 0 0 6 6$ ，the structure is considered to be completely columnar dendrites. More interestingly, Gaumann et al.,[29] proposed a revised model:

$$
\frac { G ^ { \mathrm { n } } } { V } { = } \mathrm { a } \left\{ \sqrt { \frac { - 4 \pi N _ { \mathrm { 0 } } } { 3 \ln ^ { [ 1 - \Phi ] } } } \frac { 1 } { n + 1 } \right\} ^ { n }
$$

where $G$ is the temperature gradient, $V$ is the solidification rate,nucleation number $\mathit { N O } { = } 2 { \times } 1 0 ^ { 1 5 } / \mathrm { m } ^ { 3 }$ equiaxed grain volume fraction $\phi , \ a$ and $n$ are constants related to materials, $\scriptstyle n = 3 . 4$ and $a$ （20 $= 1 . 2 5 { \times } 1 0 ^ { 6 } ( \mathrm { K } ^ { 3 . 4 } / \mathrm { m } \mathrm { ~ s } )$ ，set $\phi$ to a lower critical value $\scriptstyle { \phi { c = } 0 . 0 0 6 6 }$ ，Gan et al.[30]also obtained a judgment based on the $G ^ { n } / V$ ratio,that is,when the inside of the melt pool meets the following conditions, completely columnar dendrites occur:

$$
\frac { G ^ { \mathfrak { n } } } { V } { > } K
$$

where $K { = } 2 . 7 { \times } 1 0 ^ { 2 4 } ( \mathrm { K } ^ { 3 . 4 } / \mathrm { m } ^ { 4 . 4 } \mathrm { s } )$ ，thismicrostructure relationship is crucial between the limited solidification speed and temperature gradient as shown in Fig.1O (a). Obviously, LSMP has changed the directional solidification mode under the same G condition.As Fig.1O (b) shows the liquid melt pool Oscillates from top to bottom after being stressed,and spreads out to form multiple convective loops inside melt pool. Besides,the expansion of the surface area leads to an increased cooling rate together as shown in Fig.8, which directly accelerated the solidification rate V. As a result,the nucleation rate of the grains increases, and the growth rate decreases. Therefore, $\mathrm { G ^ { n } / V { < } K }$ occurs in the LSMP process, the recrystallization mode changes to completely equiaxed dendrite growth,replacing the original mode.In Fig.9(f),the dendrite point A and the interdendritic point B exhibit equal elemental compositions ofCr,Fe, Co,and Ni. Abolkassem et al.[31] shows the formation of Cr phase clusters and $\mathrm { C r } _ { 2 } \mathrm { O } _ { 3 }$ will lead to the reduction of Cr elements during the forming process, while other Cr, Co,and Ni elements are likely to form solid solutions with Fe,so the Fe element composition wil be high.

![](images/d4ccb031645621d672bde77d28453f78dfc18917a267f5b7944998c893782f43.jpg)  
Fig.10.(a)MicrostructureselectionmapforsolidificationmorphologyasafunctionofGandV[29](b)Columnar-Equiaxed

Transition (CET) occurs in LSMP treatment.

# 3.4.Phase composition

Figure 11 shows the XRD patterns of CrFeCoNi powder and CrFeCoNi HEAs under different processing.The three typical peaks of the FCC structure, namely (111),(20O),and (22O),dominate in the range from $2 0 ^ { \circ }$ to $9 0 ^ { \circ }$ ，and the results show a stable FCC structure is achieved through all processing conditions.Besides,Ni, Cr also forms a BCC solid solution with Fe, Abolkassem et al.[31] also obtained the same results. Under the LSMP processthe (111) peak shifts slightly to high angles as shown in Fig.11(a),which is caused by the decrease in interplanar spacing. In the orthorhombic crystal system,the crystal plane spacing $\mathrm { d } _ { \mathrm { h k l } }$ is determined by the crystal plane index $( \mathrm { ~ h ~ k ~ l ~ } )$ ,and the formula for calculating the crystal plane spacing is:

$$
d _ { \scriptscriptstyle { h k l } } = \frac { 1 } { \sqrt { \left( \frac { h } { a } \right) ^ { 2 } + \left( \frac { k } { b } \right) ^ { 2 } + \left( \frac { l } { c } \right) ^ { 2 } } }
$$

For the cubic crystal system, since $\scriptstyle \mathtt { a = b = c }$ , the above formula can be simplified to:

$$
{ \bf d } _ { \mathrm { h k l } } { = } \frac { \mathrm { ~ a ~ } } { \sqrt { { \bf h } ^ { 2 } + k ^ { 2 } + l ^ { 2 } } }
$$

After peak matching,it is obtained that the latice constants a of the HEA under the two conditions are $3 . 5 5 \mathrm { ~ \AA ~ }$ and $2 . 8 7 \mathring { \mathrm { A } }$ , respectively,and the interplanar spacing corresponding to the (111)crystal plane is calculated from the formula (15) to be $2 . 0 5 \mathrm { ~ \AA ~ }$ ,respectively.and $1 . 6 6 \mathring \mathrm { A }$ ,as shown in Fig.11(b),at the macroscopic stress level in multiple crystal scales,the compressive stress brought by LSMP leads to a smaler interplanar spacing,which is shifted to a higher angle in the XRD patern. Gonzalez et al.[32] shows the appearance of residual compressive stress can also effectively inhibit the propagation rate of hot cracks,which is beneficial.

![](images/3d2b9f65e0eaac9b9cda13090445c04e3b0447c5d2541008168995f7b9fc9510.jpg)  
Fig.l1.(a)X-RayDiffractionpattrnsand (b)interplanarspacingand laticeconstantofsamplesunderdiferenttreatments.

# 3.5.Nano-indentation analysis

Changes in microstructure will directly affect the mechanical properties of materials. Under the same experimental loading conditions,the nanoindentation results show different positions inside the melt pool also exhibit different displacements.In Fig.12 (a)and (b), the displacements of the upper and middle region of the melt pool after LSMP treatment are $8 7 9 ~ \mathrm { n m }$ and $9 0 9 ~ \mathrm { n m }$ ,respectively,which are better than those of SLM, indicating the deformation resistance of the material is improved. Because it is located in the strong influence area of the laser shock wave,the grain structure inside the melt pool under LSMP is an equiaxed dendrite, while those of SLM are columnar dendrites. Under the same load, the isotropic characteristics of equiaxed dendrites are significantly stronger than that of columnar dendrites in terms of deformation resistance.At the bottom of the melt pool,the opposite trend occurs due to the distance from the laser shock wave as shown in Fig.12(c). Since the columnar dendrites are tightly bound to the substrate,they willexhibit better combined tensile strength when hard objects are pressed in. However,the results of nano hardness show the upper, middle,and botom of the melt pool after LSMP treatment are 3.09GPa,2.83GPa,and 4.67GPa,respectively,as shown in Fig.12 (d), which are all better than those of SLM, indicating the CET under LSMP brings beneficial improvements to material properties.

![](images/32297820852e28baa93892a2c3d2d3d01724223b3010cef842a92ff9024d391e.jpg)  
Fig.12.Nanoindentationload-displacementindiferentareas:(a)Top,(b)Midle,and(c)Bottomareaofthemeltpool;(d) Hardness in different areas

# 4. Conclusions

In the process of LAMed high-entropy alloys,the online regulation of the melt pool is particularly important. A new LSMP method moves the LSP from the solid surface to the liquid melt pool is studied. Combined with numerical simulation to understand the action mechanism between laser shock and melt pool, the new process is systematically verified from the three perspectives of forming process, microstructures,and mechanical properties.The results show the necessity of introducing laser shock, and some important conclusions are summarized as follows:

1. Revealing the convection mechanism of the melt pool.The plasma induced by the pulsed laser acts on the melt pool,which promoted the transformation of melt pool flow mode from Marangoni effect to multi-convective loop, and successfully increased cooling rate by accelerating melt pool flow.

2. The microstructure evolution law of CrFeCoNi HEAs was obtained.After the action of the pulsed laser, the solidification rate of the melt pool was increased,the microstructure undergoes CET transformation，and macroscopically,the nano hardness of the top,middle and bottom regions is improved, and no segregation defects occur.

3. Realizing non-destructive real-time fabrication of CrFeCoNi HEAs with stable FCC structures, and the reduction of (111) interplanar spacing proves that laser shock introduces beneficial compressive stress.

# CRediT authorship contribution statement

Heng Lu: Investigation， Visualization, Integration, Writing-Original draft. Xiaohan Zhang: Resources. Jian Liu: Resources. Shusen Zhao: Resources and supervision. Xuechun Lin: Resources and supervision. Hui Li: Resources and supervision. Yaowu Hu: Conceptualization, Methodology, supervision, Funding acquisition.

# Acknowledgments

This work was supported by the National Natural Science Foundation of China (Grant No. 51901162). The authors thank the support of the National Talent Program of China.

# Declaration of Competing Interest

The authors declare that they have no known competing financial interests or personal relationships that could have influenced the work reported in this paper.

# Appendix A. Supplementary material

This document provides supplementary information to “Study on laser shocking of melt pool in Laser Additive Manufacturing of FeCoCrNi High-Entropy Alloys"

# 1. Cooling process

The Molecular Dynamics(MD） simulation of the Laser Shocking of Melt Pool (LSMP） goes through five stages:relax，heating (2OooK)，constant temperature，shocking and cooling. Before entering the cooling stage,the shocking module is removed to observe the liquid surface oscillation process. The total step of the cooling is 40ps as shown in Fig.A1,and the SLM process has no shock module. Clearly,the liquid melt pool oscillates after being stressed, the shock wave propagates in three-dimensional directions as shown in Fig.A1(b).At 4ps,the oscilated molten pool diffused to the solid phase and the substrate respectively. Until 2Ops,the temperature of the melt pool decreased and began to gradually solidify. After cooling,the shape of SLM model has no significant changes. But ， the shape of LSMP model does not recovers to similar state and becomes flat.The changes in the melt pool profile also agree with the 3D profile data.This phenomenon indirectly indicates that the cooling rate of the being shaken melt pool is increased,and it has solidified before returning to similar state of SLM model .

![](images/0153eadad80c1b19501864b5ee199d05d6bb8a17a4338a386b00d2b8f512f565.jpg)  
Fig.A1.Thecooling process of melt poolbased on Molecular Dynamics: (a)SLMtreatment; (c)LSMP treatment.

# 2.Different shock cases.

More shock cases including 1.5,2 and $2 . 5 \ \mathrm { k m / s }$ were simulated as shown in Fig.A2 (a). The results show there is not more benefits when the larger the shock wave acts on the melt pool. Too small will not work,too large will destroy the melt pool. In our previous experiments,the laser energy 3J wil produce beneficial oscillations effect,that is,the case of 1km in MD.At this time,the MSD of the atoms in the melt pool is the largest, indicating that the atomic movement ability is particularly strong, which will accelerate the escape of the heating source. However, others MSD curve is obviously less than the case of 1km. A MSD vector of three quantities involve dx,dy and dz are also displayed respectively as shown in Fig.A2.

![](images/b82b48169a0623294c88be50c8017c1431e6c8dd89dbc8aefeb8d27498fd4057.jpg)  
Fig.A2.TheMSDofatoms inthemeltpool,(a)totalsquareddisplacementunderdifferentshockconditions;thesquared

dx,dy,dz directions displacements: (b) $1 . 5 \mathrm { k m / s }$ (c） $2 \mathrm { k m / s }$ ,and (d) $2 . 5 \mathrm { k m / s }$

# References

[1] J.W.Yeh，S.K. Chen，S.J. Lin, J.Y.Gan, T.S.Chin, T.T. Shun,C.H. Tsau, S.Y.Chang, Nanostructured High-Entropy Alloys with Multiple Principal Elements: Novel Alloy Design Concepts and Outcomes, Advanced Engineering Materials 6(5) (2004) 299-303.https://doi.0rg/10.1002/adem.200300567.   
[2] Y.Brif, M. Thomas,I. Todd, The use of high-entropy alloys in additive manufacturing,Scripta Materialia 99 (2015) 93-96.https://doi.org/10.1016/j.scriptamat.2014.11.037.   
[3] A. Ostovari Moghaddam, N.A. Shaburova, M.N. Samodurova, A. Abdollahzadeh, E.A. Trofimov,

Additive manufacturing of high entropy alloys: A practical review, Journal of Materials Science & Technology 77 (2021) 131-162.https://doi.0rg/10.1016/j.jmst.2020.11.029.

[4] R. Zhou, Y. Liu, C. Zhou, S.Li, W. Wu, M. Song,B. Liu, X. Liang,P.K.Liaw, Microstructures and mechanical properties of C-containing FeCoCrNi high-entropy aloy fabricated by selective laser melting, Intermetallics 94 (2018) 165-171.https://doi.org/10.1016/j.intermet.2018.01.002.

[5] Z.G. Zhu, Q.B. Nguyen, F.L. Ng, X.H. An, X.Z. Liao, P.K. Liaw, S.M.L. Nai, J. Wei, Hierarchical microstructure and strengthening mechanisms of a CoCrFeNiMn high entropy alloy additively manufactured by selective laser melting, Scripta Materialia 154 (2018) 20-24.https://doi.org/10.1016/j.scriptamat.2018.05.015.

[6] F.Peyrouzet, D. Hachet, R. Soulas, C. Navone, S. Godet, S. Gorsse, Correction to: Selective Laser Melting of Al0.3CoCrFeNi High Entropy Alloy: Printability，Microstructure,and Mechanical Properties,Jom 72(10) (2020) 3705-3705.10.1007/s11837-020-04149-w.

[7] R.Li,P. Niu,T. Yuan,P. Cao, C. Chen,K. Zhou, Selective laser melting of an equiatomic CoCrFeMnNi high-entropy alloy: Processability, non-equilibrium microstructure and mechanical property, Journal of Alloys and Compounds 746 (2018) 125-134.10.1016/j.jallcom.2018.02.298.

[8] C. Zhang, K. Feng,H. Kokawa,B.Han, Z.Li, Cracking mechanism and mechanical properties of selective laser melted CoCrFeMnNi high entropy alloy using different scanning strategies, Materials Science and Engineering: A 789 (2020) 139672.https://doi.org/10.1016/j.msea.2020.139672.

[9] P.Niu,R.Li,S. Zhu,M. Wang,C. Chen,T. Yuan, Hotcracking,crystal orientation and compressive strength of an equimolar CoCrFeMnNi high-entropy alloy printed by selective laser melting, Optics & Laser Technology 127 (2020).10.1016/j.optlastec.2020.106147.

[10] Q. Jiang, P. Zhang, Z. Yu, Y. Tian, S. Ma, AlCoCrFeNi high entropy alloy fabricated via selective laser melting reinforced by Fe-based metallic glass, Materials Letters 307 (2022).10.1016/j.matlet.2021.130994.

[11] J.Li, H. Chen, S.Li, Q.Fang, Y. Liu,L. Liang, H. Wu, P.K. Liaw, Tuning the mechanical behavior of high-entropy alloys via controlling cooling rates,Materials Science and Engineering: A 760 (2019) 359-365.https://doi.0rg/10.1016/j.msea.2019.06.017.

[12] Z.Tong, X. Ren, J. Jiao, W. Zhou, Y. Ren, Y. Ye,E.A. Larson, J. Gu, Laser additive manufacturing of FeCrCoMnNi high-entropy alloy: Effect of heat treatment on microstructure, residual stress and mechanical property, Journal of Alloys and Compounds 785 (2019) 1144-1159.https://doi.org/10.1016/j.jallcom.2019.01.213.

[13] C.Knowles,T. Becker,R.Tait,The efect of heat treatment on the residual stress levels within direct metal laser sintered Ti-6Al-4V as measured using the hole-drilling strain gauge method, 2012.

[14] Z.Tong, H.Liu, J. Jiao,W. Zhou, Y. Yang, X. Ren, Improving the strength and ductility of laser directed energy deposited CrMnFeCoNi high-entropy alloy by laser shock peening，Additive Manufacturing 35 (2020) 101417.https://doi.org/10.1016/j.addma.2020.101417.

[15] Y. Hu, Y. Xuan, X. Wang, B. Deng,M. Saei, S. Jin,J. Irudayaraj, G.J. Cheng, Superplastic Formation of Metal Nanostructure Arrays with Ultrafine Gaps，Adv. Mater. 28(41) (2016) 9152-9162.https://doi.org/10.1002/adma.201602497.

[16]Y.Hu,P. Kumar,R.Xu,K.Zhao,G.J.Cheng，Ultrafast direct fabrication of flexible substrate-supported designer plasmonic nanoarrays, Nanoscale 8(1) (2016) 172-182.10.1039/C5NR06899A.

[17] Y.Hu, Y. Xuan, X. Wang, B. Deng,M. Saei, S.Jin, J. Irudayaraj,G.J. Cheng, Superplastic Formation of Metal Nanostructure Arrays with Ultrafine Gaps，Adv Mater 28(41）(2016) 9152-9162.10.1002/adma.201602497.

[18]R.Fabbro，J.Fournier，P. Ballard，D.Devaux，J. Virmont，PHYSICAL STUDY OF LASER-PRODUCED PLASMA IN CONFINED GEOMETRY，JOURNAL OF APPLIED PHYSICS 68(2) (1990) 775-784.10.1063/1.346783.

[19] W.-M. Choi, Y.H. Jo, S.S. Sohn, S. Lee, B.-J. Lee, Understanding the physical metalurgy of the CoCrFeMnNi high-entropy alloy: an atomistic simulation study, npj Computational Materials 4(1) (2018).10.1038/s41524-017-0060-9.

[20] L. Shi, X. Li,L. Jiang，M. Gao,Numerical study of keyhole-induced porosity suppression mechanism in laser welding with beam oscillation， Science and Technology of Welding and Joining 26(5) (2021) 349-355.10.1080/13621718.2021.1913562.

[21] W.Huang, H. Wang,T.Rinker, W. Tan, Investigation of metal mixing in laser keyhole welding of dissimilar metals,Materials & Design 195 (2020).10.1016/j.matdes.2020.109056.

[22] H. Wang,Y. Shi, S. Gong,Numerical simulation of laser keyhole welding processes based on control volume methods, J. Phys. D: Appl. Phys. 39(21) (2006) 4722-4730.10.1088/0022-3727/39/21/032.

[23] J.Y.Lee,S.H.Ko,D.F.Farson,C.D.Yoo,Mechanism of keyhole formation and stability in stationary laser welding, J. Phys. D: Appl. Phys. 35(13) (2002) 1570-1576.10.1088/0022-3727/35/13/320.

[24] P.Peyre,R.Fabbro,P.Merrien,H.P.Lieurade,Laser shock processing of aluminium alloys. Application to high cycle fatigue behaviour, Materials Science and Engineering: A 210(1) (1996)

102-113.https://doi.0rg/10.1016/0921-5093(95)10084-9.

[25]P.Liu,E.Harder,B.J.Berne,On the Calculation of Difusion Coeficients in Confined Fluids and Interfaces with an Application to the Liquid-Vapor Interface of Water, The Journal of Physical Chemistry B 108(21) (2004) 6595-6602.10.1021/jp0375057.

[26] S.A. Khairallah,A.T. Anderson,A. Rubenchik,W.E. King,Laser powder-bed fusion additive manufacturing: Physics of complex melt flow and formation mechanisms of pores,spatter, and denudation zones, Acta Materialia 108 (2016) 36-45.https://doi.0rg/10.1016/j.actamat.2016.02.014.

[27] D. Lin, X. Xi, X.Li,J. Hu, L. Xu, Y. Han, Y. Zhang,L. Zhao,High-temperature mechanical properties of FeCoCrNi high-entropy alloys fabricated via selective laser melting，Materials Science and Engineering: A (2021).10.1016/j.msea.2021.142354.

[28] J.D. Hunt, Steady state columnar and equiaxed growth of dendrites and eutectic, Materials Science and Engineering 65(1) (1984) 75-83.https://doi.0rg/10.1016/0025-5416(84)90201-5.

[29] M. Gäumann, C.Bezencon, P. Canalis,W. Kurz, Single-crystal laser deposition of superalloys: processing-microstructure maps, Acta Materialia 49(6) (2001) 1051-1062.https://doi.0rg/10.1016/S1359-6454(00)00367-0.

[30] Z. Gan, G. Yu, X. He,S.Li, Numerical simulation of thermal behavior and multicomponent mass transfer in direct laser deposition of Co-base alloy on steel,International Journal of Heat and Mass Transfer 104(2017) 28-38.10.1016/j.ijheatmasstransfer.2016.08.049.

[31] S.A.Abolkassem,L.Z. Mohamed,G.A.Gaber, O.A.Elkady，Microstructure and corrosion behavior of FeNiCoCrCu and FeNiCoCrMn high entropy alloys manufactured by powder metallurgy in different acid media, Journal of Materials Research and Technology 1O (2021)

1122-1142.10.1016/j.jmrt.2020.12.016.

[32] C.Rubio-Gonzalez,J.L.Ocana,G.Gomez-Rosas,C.Molpeceres,M.Paredes,A.Banderas,J.

Porro,M.Morales，Effect of laser shock processing on fatigue crack growth and fracture toughness of 6061-T6 aluminum alloy, Materials Science and Engineering:A 386(1) (2004)

291-295.https://doi.0rg/10.1016/j.msea.2004.07.025.