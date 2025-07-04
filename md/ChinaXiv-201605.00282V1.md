# IMAGING SIMULATION OF THE MICROWAVE RADIOMETER ABOARD THE MICAP FORSEASURFACESALINITYMEASUREMENT

Cheng Zhang, Hao Liu, Lin Wu, & Ji Wu

Key Laboratory of Microwave Remote Sensing, Chinese Academy of Sciences, National Space Science Center, Chinese Academy of Sciences,Beijing, 100190, China

# ABSTRACT

Sea surface salinity as an ocean variable plays an important role in various components of the water and energy cycle. Recently a Chinese space mission using a new concept of Microwave Imager Combined Active and Passive (MICAP) at L-band is proposed for the ocean salinity measurement. MICAP uses interferometric techniques for both the radiometer and the scatterometer,which adopt two kinds of linear array feeds sharing one $3 { \times } 4 . 5 \mathrm { ~ m ~ }$ parabolic cylinder reflector. Thispaper isfocused onthe microwave interferometric radiometer(MIR)aboard the MICAP,and discusses the imaging simulation, imaging algorithm,and instrument performance.

Index Terms- Sea surface salinity， microwave radiometer,synthetic aperture,L-band, parabolic cylinder reflector.

# 1.INTRODUCTION

Sea surface salinity as an ocean variable plays an important role in various components of the water and energy cycle.Lband passive microwave radiometer is considered as the mostappropriate technique forsea surfacesalinity measurement in terms of its high sensitivity to this variable [1].Currently two L-band radiometer satellite missions for sea surface salinity measurement are running in orbit. One is the Soil Moisture and Ocean Salinity (SMOS) satellite launched in 20o9 by the ESA [2],which implements a Y shaped array 2-D synthetic aperture radiometer.The other is the Aquarius satellite launched in 2O11 by NASA[3],which implements three real aperture radiometers sharing one 2.5 meter reflector in diameter.It is noted that Aquarius embarked an active L-band scatterometer to correct the impact of sea surface roughness on brightness temperature TB.The strategy of using coincident radar measurement for direct measurements of surface roughness to mitigate the wind impact on TB shows a significant potential for accurate sea surface salinity measurement [4].

![](images/f9c75fb40a0c47db1c49ef95f421155594b79330c73d5f07981d3f345f9ba697.jpg)  
Fig.1. MICAP Antenna configuration (a) and the linear feeds array distribution (b). The antenna is composed by a parabolic cylinder reflector and a linear patch feeds array located at the focus line.The patch feeds categorize by blue and red ones are used for radiometer and radar, respectively. Two different sized antenna feeds are adopted for the radiometer. The three small feeds are used for sampling the short baselines to ensure a wide alias free field of view(AFFOV), the other four big feeds with higher antenna gain are helpful for achieving higher radiometric sensitivity.

Recently a new concept of Microwave Imager Combined Active and Passive (MICAP) for ocean salinity mission is proposed by NSSC/CAS [5], [6]. Different to Aquarius,MICAP applies interferometric techniques for both the radiometer and the scatterometer.It utilizes a $3 { \times } 4 . 5$ m parabolic cylinder reflector antenna with a linear array feedslocated at the focus line,as shown in Fig.1 (a),to form fan beams for each feed. The placement of the linear feeds arrayis shown in Fig.1(b),where 8 patch antennas illustrated in blue are used for the microwave interferometric radiometer (MIR) to achieve a synthetic aperture in crosstrack direction ，and 7 phased patch antennas illustrated in red are used for scatterometer to form a pencil beam that electrically scanning in cross-track direction.

![](images/dfcebe4105ad52369d3409fbf913692ac87843345b85ae7a02ec64558b765a71.jpg)  
Fig.2. Simulation architecture for the MIR aboard the MICAP.

Developing a software platform for the system simulation of MICAP is necessary for the engineers and scientists to evaluate the system performance, test the design parameters and evaluate the processing methods. This paper is focused on the imaging simulation of the MIR aboard the MICAP.

# 2.SIMULATIONARCHITECTURE

The simulation of the MIR aboard the MICAP is mainly composed by four parts,as shown in Fig.2.The first part is scene simulation. The available databases of the geophysical variables are used to simulate the brightness temperature $( T _ { \mathrm { B } } )$ of the Sea and the land. Then, the atmosphere influence and Faraday rotation are taken into account by using the atmosphere models to generate the brightness temperature at the top of atmosphere.

The second part is $T _ { \mathrm { B } }$ image generation，which isthe conjunction between the $\mathrm { { T _ { B } } }$ image of the atmosphere in geographic coordinates and the $T _ { \mathrm { B } }$ image in front of the antenna in coordinates of cosine direction.The generator is not only for the simulated $T _ { \mathrm { B } }$ image in the forward simulation,but also for the reconstructed image in the backward simulation.In the forward process,The Tb image viewing from the antenna is composed by all the unnegligible radiations incident to the antenna,including the sources outside the earth,such as the Galaxy, the Sun and even the Moon. The satellite parameters such as the position, tilting angle and steering angle must be used to make the transformation between the $T _ { \mathrm { B } }$ image at the top of atmosphere defined in geographic coordinates and the image in front of the antenna defined in cosine direction coordinates. The polarization rotation for each pixel should also be taken into account.

The third part is the measurement simulation,which is the most important part for testing the instrument performance. All the available information of the instrument including the array placement, antenna pattern,Fringe washing function and other characteristics should be taken into account to simulating the direct visibility measurement and the indirect brightness temperature image measurement. The calibration and the imaging reconstruction are combined together and play the critical role in the measurement process. A submodule of performance evaluation is used to characterize the instrument performance in terms of spatial resolution, radiometric resolution and also the imaging accuracy. The calibration method and imaging algorithm can be further tested by this submodule through making comparison between the simulated image and the reconstructed image.

The forth part is the geophysical variables retrieval, which is mainly for the scientist to demonstrate the scientific goals reached by the system and also test the applied variableretrievalmethods.

A preliminary simulation of the $T _ { \mathrm { B } }$ image at antenna port is shown in Fig.3,where the Klein and Swift's empirical Model [7] is used to compute the dielectric constant of sea water and generate the ocean brightness temperature.The brightness temperature image of the sky background including the galaxy is generated by using the model provided by [8].

![](images/077dc619093322c4dbc3769a75416ecc809998ae54394dbb7c59ce97dde5b197.jpg)  
Fig. 3. Scene simulation for the MIR aboard the MICAP.(a) H-pol $\mathrm { { T _ { B } } }$ image in the forward FOV, (b) V-pol $\mathrm { { T _ { B } } }$ image in the forward FOV,(c) Sky background including the Galaxy in the backward FOV.

![](images/8d054539f9ecfb5ab515607e4d3ab5508b3ed9593b036f3629e0c5226d787ce5.jpg)  
Fig. 4.Antenna powerpatern. (a)3-Dviewofoneantenna patern,1-Dcutsof the H-polpaters (b)and V-polpaterns (c) of the 8 antenna elements in the cross-track direction.

# 3.IMAGERECONSTRUCTION

The imaging algorithm used to reconstruct the brightness temperatureimagesfromthe visibilityfunction measurements is the key part of the imaging simulation. For the 1-D MIR, the numerical G matrix resolve method is the exclusive choice for the image reconstruction due to the large diversity of antenna patterns.As shown in Fig.4,the antenna pattern of each antenna element differs much from each other especially for two different sized antenna feeds. The G matrix characterizing the relation between the measured polarimetric visibility functions and the polarized brightness temperature images includes all the information of the antenna patterns, so the G matrix inverse method would mitigate the impact of inconsistent antenna patterns. However,pseudo-inverse of G still causes big errors because of the bad condition of G,as shown in Fig.5.Regularization method,such as the SVD method [9],is required to deal with this ill-posed problem.However,for high accuracy sea surface salinity measurement, the image noise error caused by the reconstruction method itself should be controlled in levelof O.1K. EventheGmatrixinversionwith regularization method will cause unacceptable errors for such case.An efficient solution is recovering the differential image instead of direct reconstructing the original image [10].Then the image reconstruction is to solve the minimum problem

$$
\left\{ \begin{array} { l l } { \displaystyle \operatorname* { m i n } _ { T \in \cal E } \left\| \Delta V - G \Delta T \right\| _ { F } ^ { 2 } } \\ { \displaystyle \big ( I - P _ { \check { H } } \big ) \Delta T = 0 } \end{array} \right.
$$

Where the differential image $\Delta T$ is computed by the inversion of differential visibility function $\Delta V _ { ; }$ ，which is generated by subtracting the reference visibilities from the measured visibilities.The reference visibilities are computed from an artificial scene image by using the databases of the geophysical parameters to ensure the simulation is as close as possible to the real observed scene. $P _ { \mathrm { H } }$ is the projector to the H bandlimited function. Then, the image reconstruction process can be expressed as

$$
\hat { T } _ { r } = U ^ { H } Z \left( { A ^ { ' } A } \right) ^ { - 1 } A ^ { * } \left( V - G \tilde { T } \right) + \tilde { T }
$$

![](images/9ae46880d84587af574c9194873eb445fe84257ad871a6e60acb7657810a51bd.jpg)  
Fig.5.The full polarimetric G matrix image in unit of dB (a) and its singular values distribution (b).

where $\mathrm { ~ U ~ }$ is the Fourier transform operator, $Z$ is the zero padding operator, $\mathbf { A } { = } \mathbf { G } \mathbf { U } ^ { * } Z$ . This approach can greatly reduce the reconstruction bias error.

In order to filter out the Gibbs effects due to the sharp frequency truncation by the finite array sampling,other than the traditional window tapering function applied to the visibility function,a spatial smooth filter is directlyapplied to the reconstructed image. This approach can effectively suppress the oscillations in the reconstructed image,and at the same time broaden the maim beam width of the system point spread function (PSF).The PSFs of the MIR aboard the MICAP and their beam width variation along the cross track directionareshowninFig.6, which clearly demonstrate the side-lobe suppression and beam width extension caused by the smooth filter.

# 4. CONCLUSIONS

The framework of the imaging simulation for the MIR aboard MICAP is briefly described in this paper. Some initial results are present. This simulator is still under development.Lots of submodules need to be accomplished and added in the simulator.More emphasis should be put on the instrument measurement part, especially the calibrating and imaging processing，which affect the system final imaging performance and consequently the capability of achieving the application goals.

# 5.REFERENCES

[1] S.H.Yueh，et al.，“Error sources and feasibility for microwave remote sensing of ocean surface salinity,”IEEE Trans. Geosci. Remote Sens.,vol.39,no.5,pp.1049-1059, May 2001.   
[2] H.Barré,B.Duesmann,and Y.Kerr,“SMOS:The mission and the system,”IEEE Trans.Geosci.Remote Sens.,vol.46, no.3,pp.587-593,March2008.   
[3] D.M.Le Vine,et al.“Aquarius:an instrument to monitor Sea Surface Salinity from space”,IEEE Trans.Geosci. Remote Sens.,vol.45,no.7,pp.2040-50,2007.   
[4] S.H.Yueh,J.Chaubell,"Sea Surface Salinity and Wind Retrieval Using Combined Passive and Active L-Band Microwave Observations"，IEEE Trans.Geosci.Remote Sens.,vol.50,no.4,pp.1022-1032,April 2012.   
[5] H.Liu,et al.,“A Combined L band Synthetic Aperture Radiometer and Fan-Beam Scatterometer for Soil Moisture and Ocean Salinity Measurement"，In Proc.IGARSS, pp.4644-4647,2012.   
[6] H.Liu,L.Niu, C. Zhang,X. Zhang,J.Yan, J.Wu,“System study and development of an L-band 1-D synthetic aperture radiometer forocean salinitymeasurement,”In Proc. IGARSS,pp.1916-1919,2013.   
[7] L.A.Klein and C.T.Swift,"An improved model for the dielectric constant of sea water at microwave frequencies," IEEETransactions on Antennas and Propagation,vol.AP25, no.1, pp. 104-111, Jan. 1977.   
[8] E.P.Dinnat,D.M.Le Vine,S.Abraham and N. Flury, “Map of Sky background brightness temperature atL-band," http://oceancolor.gsfc.nasa.gov/AQUARIUS/DinnatEtAl201 0/   
[9] B.Picard and E.Anterrieu,“Comparison of regularized inversion methods in synthetic aperture imaging radiometry," IEEE Trans. Geosci. Remote Sens.,vol. 43,no.2,pp. 218- 224,Feb.2005.   
[10]E.Anterrieu,“On the Reduction of the Reconstruction Bias in Synthetic Aperture Imaging Radiometry,” IEEE Trans. Geosci.Remote Sens.,vol.45,no.4,pp.1084-1093,Apr. 2007.

![](images/fd39ed8f10afdbfb015850f26ab2ac14f66aff643d89b9dde433c80104748715.jpg)  
Fig.6.PSFs of the MIR inHand $\mathrm { v }$ polarizations (a) and the variations of the angular resolutions (-3dB beam width) in crosstrack direction (b)