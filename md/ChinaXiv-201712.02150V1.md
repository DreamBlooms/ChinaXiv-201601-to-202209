# FEASIBILITY ANALYSIS OF 1D CARBON

# MATERIALINAPPLICATIONOFNEGATIVE

# PARTICLEBEAMDIAGNOSTICS

YONGJIAN XU ,LI ZHANG,LING YU, YAHONG XIE,CAICHAO JIANG,LIZHEN LIANG,JIANGLONGWEI，YUANLAIXIE,CHUNDONG HU

# ABSTRACT

An important feature of China Fusion Engineering Test Reactor (CFETR) project is represented by the additional heating obtained from the injection of neutral beams based on accelerated negative ions. For the neutral beams based on negative ions, the most important measurements are beam uniformity, beamlet divergence and stripping losses. According to the CFETR requirement， the maximum allowed beam divergence angle and beam non-uniformity are 6 mrad and $\pm I O \%$ respectively. As 1D carbon tiles have large ratio between perpendicular conductivity and parallel conductivity and high stability, they can be used for beam uniformity and beamlet divergence measurement. This paper presents the investigation of the influence on the response of 1D carbon tile having the thermal characteristics and features of some dedicated diagnostics. Simulations show that it will be possible to verify experimentally whether the beam meets the requirement about the maximum allowed value. This work lays a foundation for design and application of high precision beam diagnostic targets.

KEYWORDS: neutral beam injection; beam divergence angle; beam uniformity; negative ion source; 1D carbon material

# I.INTRODUCTION

The China Fusion Engineering Test Reactor (CFETR） will require additional heating by means of injection of high energy， high power neutral beam injector in order to fulfillits mission.1-3 Beam uniformity and divergence angle,as the key parameters for ion beam， should be measured during beam extraction.4-12 To study and optimize the negative ion production,a lot of novel calorimeters have been developed.13-17 Supported by ITER project, G. Serianni (Consorzio RFX, Italy) develops aShort-TimeRetractableInstrumented KalorimeterExperiment (STRIKE） based on one-direction carbon-fiber-carbon-composite （1DCFC) tiles.18.19 STRIKE can produce 2D beam intensity profile with a spatial resolution of $2 ~ \mathrm { m m }$ and $5 0 ~ \mathrm { H z }$ frame rate by measuring with IR thermo-cameras. As the key component, the 1D-CFC guarantees a ratio up to 2O of thermal conductivity along/across the fibers. Since a qualified manufacturer of suitable 1D-CFC has not been identified yet, an alternative carbon material， which has much larger ratio of thermal conductivity than that of 1D-CFC，is investigated.In this paper， the thermal performance of carbon material is analyzed using FEM and the results show that the carbon material can meet this diagnosis requirement of key beam parameter.

# II.ASSESSMENT OF ONE DIMENSION CARBONMATERIAL

To study the beam properties,it is important that heat transmission from the front to the rear side of the tiles occurs with a small systematic error and the thermal profile of rear side can reflect the real beam profile as closely as possible.The carbon material is produced by the institute of coal chemistry, CAS.20,21 The physics properties of carbon material are given in TABLE I.

TABLE I. The physics properties of one-dimension carbon material   

<html><body><table><tr><td rowspan="2">Mass density</td><td rowspan="2">Specific heat</td><td colspan="2">thermaldiffusioncoefficient</td><td colspan="2">thermal conductivity</td></tr><tr><td>perpendicular</td><td>parallel</td><td>perpendicular</td><td>parallel</td></tr><tr><td>1.910kg/cm³</td><td>704J/(kg·K)</td><td>319.7mm²/s</td><td>9.3mm²/s</td><td>429.9W/m·K</td><td>12.4W/m·K</td></tr></table></body></html>

The ratio of the thermal conductivity of perpendicular and parallel to the graphite layers is up to 34. As the specific heat and thermal conductivity are regarded as a constant in this simulation, actually, these two thermal parameters will change with the rise of temperature, so there is some divergences between the simulation results and actual case. 22

An important issue that shall be taken into account is the temperature profile of front and rear side of the tile. Comparing the temperature profiles, the thermal feature of tile can be obtained. Simulation consists of two parts, one is thermal properties of one-dimension carbon material, and the other is assessment simulation of beam key parameters based on one-dimension carbon material.

# II.A. THERMAL PROPERTIES OF ONE-DIMENSION

# CARBONMATERIAL

Theprototype of CFETR neutral beam injector(NBI） isin the planning process. The primary parameters is: negative beam energy is 200keV,current density is no less than $3 0 0 \mathrm { A } / \mathrm { m } ^ { 2 }$ ， and the extraction area of ion source is $0 . 3 2 \mathrm { m } { \times } 1 . 6 \mathrm { m }$ . The grids of prototype plan to adopt similar design of ITER NBI.

The incidence angle of the beam on the tile is supposed to be $9 0 ^ { \circ }$ .The simulations have been performed with thickness $2 0 \mathrm { m m }$ ， pulse length 2s with peak heat flux $1 0 \mathrm { M W } / \mathrm { m } ^ { 2 }$ . The beam energy distribution $P g ( x , y )$ （204号 meets Gaussian distribution in two dimensions and it is represented as follows16:

$$
P _ { _ g } ( x , y ) = A _ { _ g } \exp \Biggl ( - \frac { ( x - x _ { _ 0 g } ) ^ { 2 } } { 2 \sigma _ { _ { x g } } ^ { 2 } } - \frac { ( y - y _ { _ 0 g } ) ^ { 2 } } { 2 \sigma _ { _ { y g } } ^ { 2 } } \Biggr )
$$

Where $\sigma _ { \mathrm { x g } }$ and $\sigma _ { \mathrm { y g } }$ are the beamlet half-widths in the X and y directions and $\mathrm { A _ { g } } = 1 0 \mathrm { M W / m } ^ { 2 }$ is the amplitude of the energy flux at the maximum position $( \mathrm { x _ { 0 g } , y _ { 0 g } } )$ . In this simulation, the size of modeled tile is $1 0 0 \mathrm { m m } \times$

$1 0 0 \mathrm { m m } \times 2 0 \mathrm { m m }$ and the tile is adiabatic except for the front and rear side and the thermal radiation of the front and rear side is considered. The initial temperature is 293.15K. In order to research the temperature varying with time, transient thermal modeling is used in this simulation. The heat load is applied on the tile with a circle of radius $2 0 \mathrm { m m }$

Fig.1 gives the layout of ground grid aperture. According to the Fig.1, the beam width is assumed as ${ \sigma } _ { \mathrm { { x g } } } { = } { \sigma } _ { \mathrm { { y g } } } { = } 1 1 \mathrm { { m m } }$ , the duration of heat load is 2s, Fig.2 gives the temperature curve for front and rear side of 1D-carbon tile from O to 3s. Fig.2 shows that the temperature of front side reached the maximum at the end of the heat load, and the temperature of rear side almost reached the maximum at the same time because of heat propagation time from the front side to rear side. So the thermal profiles of carbon tile are taken at 2s,which is the end of heat load (shown in Fig.3). In order to investigate the thermal properties， the normalized temperature curves along the diameter for front and rear side, with a comparison with the Gaussian curve given in Eqn.1 are shown in Fig.4. Fig.4 shows that(1) the temperature curve of front side is similar to the Gaussian curve, showing that the temperature profile on the front side can be a measurement of the applied heat load; (2) the temperature curve of the front side is similar to which of rear side, showing that heat transfer to the rear side occurs with negligible lateral loses. It means that the carbon tile， which has anisotropy of thermal conductivity， can meet the requirement of beam characteristics testing.

Ground Grid d=6mm aperture dbq9o R=8mm

![](images/fafd5fb030ab081d497f4a8cc06834058605147ed96d0012903fbb31daa8a2df.jpg)  
Fig.1. the layout of the ground grid aperture   
Fig.2. the temperature curve for front and rear side of 1D-carbon tile

![](images/a7554ce82f403b1b5d0b0abe10d5fe165c8ef5acbd500d119d9f35d003f64baf.jpg)  
Fig.3. the surface thermal profile of 1D carbon tile at 2s

![](images/112af1b61fdcc8728bb3b173b69895aafbc076f11468cab5fde306e8ebd30985.jpg)  
Fig.4. the normalized temperature curve along the diameter (at 2s)

# I1.B. Investigation of beam divergence angle

The estimation of beamlet divergence calls for the measurement of the beamlet width in different positions along the beam. Generally， the beamlet width can be written as the superposition of an intrinsic width ${ \sigma } _ { \mathrm { 0 g } }$ (which is assumed as $3 \mathrm { m m }$ in this simulation） and the increase of the beamlet width $\delta _ { z }$ due to the increase of the angular aperture of the beamlet as a function of the distance along beam direction from the ground grid. It means that ${ \sigma } _ { \mathrm { x g } }$ and ${ \sigma } _ { \mathrm { y g } }$ in Eqn.1 include two parts

$$
\sigma _ { \mathrm { g } } = \sigma _ { \mathrm { 0 g } } + \delta _ { z }
$$

where $\delta _ { z }$ is determined by the beamlet divergence. In order to deduce the value of $\delta _ { z }$ ，the beamlet width of two positions ( $( \pmb { \sigma } _ { \mathrm { x g } } { = } \pmb { \sigma } _ { \mathrm { y g } } { = } \pmb { \sigma }$ $\scriptstyle = 1 1 { \mathrm { m m } }$ and $1 7 \mathrm { m m }$ ,respectively） are reconstructed on the 1D carbon tile. The heat flux with distribution given in Eqn.1 is applied on the tile. Fig.5 gives the thermal pattern of rear side at different O. The temperature peak stands out less clearly. For assessing the beam width conveniently, the temperature profile along the diameter is shown in Fig.6. Fig.6 presents that the 1/e half width increases from $1 6 . 3 \mathrm { m m }$ to $1 9 \mathrm { m m }$ as O changes from $1 1 \mathrm { m m }$ to $1 7 \mathrm { m m }$ . The increase of beam width is due to the beam angular aperture along the beam transmission direction. The beamlet divergence angle $\alpha$ can be obtained

$$
\alpha = \arctan { \frac { r _ { 1 } - r _ { 2 } } { D } }
$$

where $\mathbf { r } _ { 1 }$ and $\mathbf { r } _ { 2 }$ are the $1 / \mathrm { e }$ half width of beam profile at two measurement

sites,respectively, and D is the distance between the two measurement sites.

![](images/71ccd0e6fdb901862d6e2dccc884b347c5e7a08fb8628fc5597bcdfe540b7315.jpg)  
Fig.5. The thermal pattern of rear side at different O

![](images/ac7e19ec7e8ad8d0e4633f92d4dbf2745b31cb33e6e7550c34a6c750a7982a2e.jpg)  
Fig.6. the temperature profile along the diameter at different O

# II.C.INVESTIGATIONOFBEAMUNIFORMITY

The beam uniformity can be assessed through the difference of temperature rise after the beam impinges on the 1D carbon tile. The surface temperature rise of the tile is related with the beam power density deposited on the tile surface. In this simulation,a set of data is given in TABLE II. In this table,a reference case $( 1 0 \mathrm { M W } / \mathrm { m } ^ { 2 } )$ ）is compared with other two cases，in which the heat load has been raised by $1 5 \%$ $\mathrm { 1 1 . 5 M W / m } ^ { 2 } \mathrm { \cdot }$ ）or reduced by $5 \%$ $( 9 . 5 \mathrm { M W } / \mathrm { m } ^ { 2 } )$ ）with respect to the reference case. The temperature of the front and rear sides are recorded, so the temperature difference $\Delta$ T per $1 \%$ of power density can be got. As the beam impinges on the tiles, the nonuniformity of beam inevitably leads to the nonuniformity of temperature rise. So, combining with the data listed in TABLE II, the beam uniformity can be obtained through the analysis of the data of surface temperature rise at different position with respect to the grid aperture.A set of simulation results is given in Fig.7 (a), the peak of heat loads from left to right on each line of the tile are （20 $9 \mathrm { M W } / \mathrm { m } ^ { 2 }$ 9.5MW $/ \mathrm { m } ^ { 2 }$ ，10MW $/ \mathrm { m } ^ { 2 }$ ，9.5MW $/ \mathrm { m } ^ { 2 }$ ， $9 \mathrm { M W / m } ^ { 2 }$ ，respectively. The peak temperature of rear side，which is corresponding to each beamlet, presents major difference (see Fig.7(b)). According to the table 1, assume the $1 0 \mathrm { M W } / \mathrm { m } ^ { 2 }$ as the reference case, the beam uniformity is （204号 $10 \%$ and $5 \%$ for $9 \mathrm { M W } / \mathrm { m } ^ { 2 }$ ， $9 . 5 \mathrm { M W } / \mathrm { m } ^ { 2 }$ respectively. This means that the 1D carbon tile is a viable option for the assessment of the beam uniformity.

TABLE II.Comparison between reference case, case with $+ 1 5 \%$ heat loading and case with $- 5 \%$ heat loading.

<html><body><table><tr><td></td><td>Reference case (10MW/m²)</td><td>+15% (11.5MW/m²)</td><td>-5% (9.5MW/m²)</td></tr><tr><td>Front side</td><td>1062K</td><td>1177K</td><td>1024K</td></tr><tr><td>Rear side</td><td>889K</td><td>978K</td><td>859K</td></tr><tr><td>△ T/1%</td><td>一</td><td>Front: 7.7K/1% Rear: 5.9K/1%</td><td>Front: 7.6K/1% Rear: 6.0K/1%</td></tr></table></body></html>

![](images/9e213b88f049d1d1b730e880491b31562c83b1512d5364af72a10290ba14ebe1.jpg)

Fig.7. Simulation of measurements performed with different peak of heat load: (a) thermal pattern of rear side,(b) temperature profile along the white line

# III.CONCLUSION

Beamlet divergence and beam uniformity are important parameters for negative neutral beam injectors. Comparing with 1D CFC, 1D carbon material is easy to obtain and has similar or more superior performance in thermal properties. In this paper, the thermal characteristics are analysed in the application of negative particle beam diagnostics. The results of the simulations show that 1D carbon material is a viable option for the evaluation of the beamlet divergence and the beam uniformity. In addition， the assessment need to be further improved and refined, considering also the halo effect and the corrections to compensate for the image distortion due to view angle.In conclusion, as 1D carbon material has excellent thermal character，it is to be considered as a suitable alternative material in negative particle beam diagnosis.

# ACKNOWLEDGEMENTS

This work has been supported by Key Program of Research and Development of Hefei Science Center, CAS (No. 2O16HSC-KPRD002), National Natural Science Foundation of China (No.11505225） and Institute of Plasma Physics Foundation of Chinese Academy of Sciences (No.DSJJ-15-GC03).

# REFERENCES

1. Y. WAN et al., “Overview of the present progress and activities on the CFETR", Nucl. Fusion,57,102009(2017)

2. Y. SONG et al.， “Concept Design of CFETR Tokamak Machine,”, IEEE T. Plasma Sci.,42,3. 503(2014).

3 B.WANet al.，“Physics Design of CFETR: Determination of the Device Engineering Parameters,” IEEE T.Plasma Sci.,42,3, 495(2014).

4.D.CIRIC et al.,“Beam profiles measurement using a unidirectional CFC-target and infrared imaging,” , Fusion Technol.,2,827(1994).

5.R. MAURIZIO et al.， “Characterisation of the properties of a negative hydrogen ion beam by several beam diagnostic techniques", Nucl. Fusion, 56, 066012(2016).

6.G. SERIANNI et al., “First negative ion beam measurement by the Short-Time Retractable Instrumented Kalorimeter Experiment (STRIKE) ", Rev. Sci. Instrum. 85 ,02A736(2014).

7. M. DE MURI et al.，“Characterization， test and interpretative simulations of one-dimensional Carbon Fiber Composite prototype for SPIDER experiment," Fusion Eng. Des., 88,1758(2013).

8.R.NOCENTINI et al.，“Beam diagnostic tools for the negative hydrogen ion source test facility ELISE,’ Fusion Eng. Des.， 88, 913(2013).

9.P.VELTRI et al., “Optics of the NIFS negative ion source test stand by infrared calorimetry and numerical modeling,’ Rev. Sci. Instrum. ， 87, 02B908(2016).

10.K.TSUMORI et al.， “Beamlet characteristics in the accelerator with multislot grounded grid,", Rev. Sci. Instrum. 81, O2B117 (2010).

11. C.FUENTES et al.,“Thermographic calorimetry of the neutral beam injectors heating beams at TJ-II," Rev. Sci. Instrum. 77, 10E519 (2006).

12.M. CAVENAGO et al.，“Installation of a versatile multiaperture negative ion source," Rev. Sci. Instrum., 85, 02A704(2014).

13.L. SVENSSON et al.， “Latest results from the Cadarache 1 MV SINGAP experiment,", Fusion Eng. Des. 66-68, 627 (2003).

14.R.PASQUALOTTO et al.,“A wire calorimeter for the SPIDER beam: Experimental tests and feasibility study,’ AIP Conf. Proc. 1655, 060008(2015).

15.A. RIZZOLO et al., “Design and analyses of a one-dimensional CFC calorimeter for SPIDER beam characterization,” Fusion Eng. Des., 85, 2268(2010).

16.M.LINIERS et al., “Beam transmission dependence on beam parameters for TJ-II Neutral Beam Injectors,’ Fusion Eng. Des., (to be published).

17. R. PASQUALOTTO et al.， “Diagnostics of the ITER neutral beam test facility," Rev. Sci. Instrum., 83, 02B103(2012).

18. G. SERIANNI et al., “Thermal simulations of STRIKE tiles for the assessment of the CFC prototypes and of the configuration for SPIDER," AIP Conf. Pr0c. 1515, 579(2013).

19.G. SERIANNI et al.，“Negative ion beam characterisation in BATMAN by mini-STRIKE: Improved design and new measurements," AIP Conf. Pr0c. 1655, 060007(2015).

20. Z. LIU. et al., “Preparation of doped graphite with high thermal conductivity y a liquid mixing process," Carbon ,45, 1911(2007).

21. Z. LIU et al., “Graphite blocks with high thermal conductivity derived from natural graphite flake," Carbon, 46, 414(2008).

22. M. DALLA PALMA et al., “Numerical Assessment of the Diagnostic Capabilities of the Instrumented Calorimeter for SPIDER (STRIKE)," AIP Conf. Pr0c. 1390, 584(2011).