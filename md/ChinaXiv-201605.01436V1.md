# In vivo sensitivity estimation and imaging acceleration with rotating RF coil arrays at 7 Tesla

Mingyan Lia\*, Jin Jinä, Zhentao Zuob\*,Feng Liua, Adnan Trakica, Ewald Webera, Yan Zhuob,Rong Xueb stuart Croziera

aSchoolof IformationTechnologyndElectricalEngineering,TeUiversityfQueensland,Brisbane,QLDustralia tateKe

# ARTICLE INFO

Article history:   
Received 8 July 2014   
Revised 11 December 2014   
Available online 26December 2014   
Keywords:   
Human brain imaging   
In vivo sensitivity estimation   
Rotating RF coil array (RRFCA)   
Phased array coils   
Parallel imaging   
7 Tesla   
Rotating SENSitivity Encoding (rotating  
SENSE)   
Signal-to-noise ratio (SNR)

# ABSTRACT

Usinga new rotating SENSitivity Encoding (rotating-SENSE）algorithm,we have successfully demonstrated that the rotating radiofrequency coil array(RRFCA) was capable of achieving a significant reduction in scan time and auniform image reconstruction fora homogeneous phantom at7Tesla.However,at 7 Tesla the invivo sensitivity profiles $\left( B _ { 1 } ^ { - } \right)$ become distinct at various angular positions.Therefore,sensitivity maps at other angular positions cannot be obtained by numerically rotating the acquired ones.In this work,a novelsensitivity estimation method for the RRFCA was developed and validated with human brain imaging.This method employed alibrary database and registration techniques to estimate coil sensitivity at an arbitrary angular position.The estimated sensitivity maps were then compared to the acquired sensitivity maps.The results indicate thatthe proposed method is capable of accurately estimating both magnitude and phase of sensitivityatanarbitrary angular position,which enablesus to employ the rotating-SENSE algorithm to accelerate acquisition and reconstruct image.Compared to a stationary coil array with the same number of coil elements,the RRFCA was able to reconstruct images with better quality at a high reduction factor.It is hoped that the proposed rotation-dependent sensitivity estimation algorithm and the accelerationabilityof the RRFCA willbe particularly useful for ultra high field MRI.

$\circledcirc$ 2014 Elsevier Inc.All rights reserved.

# 1. Introduction

Reducing the scan time of magnetic resonance imaging(MRl) is important for both clinical diagnosis and scientific research.Clinically,acquiring high resolution images normally requires long scan duration,which may discomfort patients and generate motionrelated artifacts thataffect diagnostic accuracy.In research,especially in functional MRI (fMRI)，shorter scan time facilitates improving quantification of the brain activity.The fast full $k$ -space acquisition schemes have been developed for modern MRl systems to shorten scan time,such as echo planer imaging(EPI)[1],fast spin echo [2]and fast gradient echo imaging[3].More recently, phased arraycoils(PACs）[4,5]have facilitated partial $k$ -space acquisition to further reduce the scan time. Images can then be reconstructed with different algorithms,such as simultaneous acquisition of spatial harmonics (SMASH)[6], SENSitivity Encoding (SENSE)[7,8],generalized autocalibratingpartiallyparallel acquisitions (GRAPPA) [9].

As an alternative method,we have introduced the rotating radiofrequency coil (RRFC)[10,11] and the rotating radiofrequency coil array （RRFCA）[12-14] to reduce scan duration by using SENSE-like reconstruction methods.Both rotating RF systems are capable of encoding $k$ -space data with varying sensitivity profiles $\left( B _ { 1 } ^ { - } \right)$ ,which benefit the signal encoding process and reconstruction algorithms.Byadopting the time-division multiplexing sensitivity encoding(TDM-SENSE), the RRFC demonstrateda2-fold scan time reduction for human brain imaging[11]. The RRFCA used the rotating-SENSE algorithm that featured time-varying sensitivityprofiles foracquisition acceleration and image reconstruction.A4-element RRFCA was prototyped and tested with a homogeneous phantom at 7Tesla,which exhibited improved $g _ { \ l }$ -maps[7] and uniform signal-to-noise ratio (SNR) distributions compared with a traditional stationary 8-element coil array[12,14].

In this work,the feasibility of using the RRFCA for human brain imaging was tested. Since the rotating-SENSE algorithm needs sensitivity information for image reconstruction,in our previous studies[11,14],a small number of sensitivity maps acquired at several angular positions were numerically rotated to estimate sensitivity at other positions.This technique was used for human brain imagingat2 Tesla[1O,11] owing to the negligible coil-tissue interaction [15-19] (dielectric resonance [20-22],or constructive and destructive interference [23,24]). This approach was also used for imaging a homogeneous phantomat7 Tesla,provided the phantom and the RRFCA system are both symmetrical [14].However,this method is notapplicable forinvivo sensitivityestimationat7Tesla,because the in vivo sensitivity maps at different angular positions vary significantly. Since measuring sensitivity at every angular position is impractical and compromises the fast imaging purpose,a practical and robust sensitivity estimation method is needed for in vivo applications of the RRFCAat ultra high felds.

Here we investigate a novel sensitivity estimation method specially designed forinvivo applications of the RRFCA.Instead of simply rotating the acquired sensitivity to new angular positions,the in vivo sensitivity maps will be deformed in a non-linear fashion. These deformations can be calculated with image registration techniques by registering in vivo sensitivity to sensitivity in the library which was acquired from scans of volunteers or numerical calculations.This approach is based on the observation that the $B _ { 1 } ^ { - }$ map is not particularly sensitive to small local changes,in terms of dielectric properties and structures of tissues.Instead, $B _ { 1 } ^ { - }$ maps are typicallyrelated to the global dielectric property distribution relative to the RF system[24-26],with lower spatial frequencies.This sensitivity deformation can be modelled numerically using image registration techniques [27-29],as these techniques are commonly used in finding the spatial correspondence between two images. Importantly,imageregistration hasrecently found application in modelling the magnetic field variations due to changes in dielectric distributions between different subjects [30].

In this work,the proposed numerical method will be applied to estimate the rotated sensitivity maps,which will then be used to optimise the rotating technique and reconstruct the images.The optimisation of the rotating scheme is achieved by minimising the maximum $g \mathrm { . }$ -factor,which suppresses the noise amplification in the imaging acceleration. The $g \mathrm { . }$ -maps,reconstructed images and SNR maps of the RRFCA and stationary coil array will then be compared.

# 2.Methods and materials

Asdescribed in previous work[14],the RRFCA moves to various angular positions during acquisition,so that different $k$ -space phase-encoding lines are associated with distinct coil sensitivity profiles which improve encoding capability.In order to reduce the overall scan time,sensitivity maps at most angular positions are estimated froma small number of measured in vivo sensitivity maps,by employing the proposed algorithm.The linear superposition of individual sensitivity maps with global coverage of the sample can benefit the registration algorithm [31] (detailsare discussed in later sections).However,four physical elements with $9 0 ^ { \circ }$ intervals of the RRFCA prototype are insufficient to provide a complete coverage.Consequently,two sets of sensitivity maps, with angular separation of $4 5 ^ { \circ }$ (e.g. position $1 \colon 0 ^ { \circ } + 4 5 ^ { \circ }$ in Fig. 1), areused together to simulate a rotating array with 8 elements equidistantly distributed in angular direction.Considering that all elements are identical, the range of angular displacement that theRRFCA needs to travel is from $- 2 2 . 5 ^ { \circ }$ to $+ 2 2 . 5 ^ { \circ }$ .In orderto test the robustness of the estimation algorithm at the maximum angular rotation,sensitivity with $2 2 ^ { \circ }$ displacement（position 3） from position1is estimated.In addition,the intermediate angular position displacement ( $1 0 ^ { \circ }$ at position 2)is also estimated.(as shown in Fig.1,estimate $B _ { 1 } ^ { - }$ at positions 2 and 3 from acquired $B _ { 1 } ^ { - }$ at position1).To verify the robustness of the proposed algorithm,two volunteers of different gendersand distinctly different head sizes were imaged.

![](images/4330ffc5505c1d6b85adb3de6f8fb4bcab2130eace94af348c2c2ce78bfed85e.jpg)  
Fig.1.The sensitivity profiles of the 4-element RRFCA were acquired at angular positions at 0o,10,22, $4 5 ^ { \circ }$ $5 5 ^ { \circ }$ and $6 7 ^ { \circ }$ ,denoted with red,yellow,green,dashed red,dashed yellow and dashed green. Sensitivity maps acquired at these positions were recombined as three positions for better registration performance: position 1 $( 0 ^ { \circ } + 4 5 ^ { \circ } )$ ，position 2 $( 1 0 ^ { \circ } + 5 5 ^ { \circ } )$ ，position 3 $( 2 2 ^ { \circ } + 6 7 ^ { \circ } )$ .(For interpretation of the references to color in this figure legend,the reader is referred to the web version of this article.)

# 2.1.Registration based in vivo sensitivity estimation

In this work,the new sensitivity estimation method uses the acquired sensitivityat the initial position to estimate the sensitivityatother positions by employinga sensitivity libraryand registration techniques.The library provides source images,which are made up of sensitivity maps at all angular positions acquired during scans of volunteers.The registration techniques are employed to find the spatial transformation that aligns the source image (library sensitivity) to the target image (actual acquired sensitivity) from its initial position,and this transformation is applied to other angular positions for estimating corresponding sensitivity maps. The rotational sensitivityat arbitraryangular positions is acquired by following four steps:

(1) Create a library by acquiring sensitivity maps at all angular positions from the scans of the volunteers.During the actual patient scanning,sensitivity maps at an initial position (i.e., position1 in Fig.1) are acquired. Image processing is applied to both groups of sensitivity maps to smooth profiles and correct singular values.   
(2）Instead of registering individual coil sensitivity maps,they are linearly combined before being registered,to improve accuracy and efficiency.The combination coefficients are determined with a condition number of1 to achieve the optimal sensitivity estimation when individual sensitivity profiles are later extracted (see Step (4)).   
(3） As illustrated using a flow chart in Fig.2,the source profile $S _ { 1 } ^ { 8 }$ (combined 8 library $B _ { 1 } ^ { - }$ maps at position 1) is registered to the target profile $\stackrel { \_ } { T _ { 1 } ^ { 8 } }$ (combined 8 in vivo $B _ { 1 } ^ { - }$ maps at position 1). The corresponding transformation $\psi _ { 1 } ^ { 8 }$ is extracted and applied to the combined library sensitivity map at arbitrary angularposition $( \boldsymbol { \alpha } ^ { \circ } )$ to obtain the estimated combined sensitivity map $\stackrel {  } { E _ { \alpha } ^ { 8 } }$ ，

![](images/b4805c837484372f7d074ff218455b63396773f9e6a4a0cdc3aadb49e97b9f1c.jpg)  
Fig.2.Flow chart of the registration based rotation-dependent sensitivity estimation.

(4)Repeat step(3）8 times for all the linear combinations to estimate all the combined sensitivity maps.The individual $\underset { - 1 } { \longrightarrow }$ sensitivity map $E _ { \alpha } ^ { 1 }$ at $\alpha ^ { \circ }$ angular position (i.e., positions 2, 3 in Fig.1) is calculated by multiplying the inverse of the coefficient matrix. $N ^ { 2 }$ in Fig.2 denotes the number of pixels.

# 2.1.1.In vivo sensitivity mapping and singular value correction

The most common sensitivity mapping method for a stationary coil array is to derive relative coil sensitivity by dividing the individual coil image using a predominantly uniform reference image. Both the coil image and the reference image can be obtained from either full $k$ -space sampling[7,32] or fully sampled central $k$ -space [33,34].Without a uniform volume transmit coil,the reference image is typically approximated as the root sum of square(RSS) image:

$$
{ \begin{array} { r l } & { { \mathsf { R S S } } = \left| { \sqrt { \sum _ { j = 1 } ^ { J } { \vec { ( I _ { j } ) } } ^ { 2 } } } \right| } \\ & { } \\ & { { \vec { S } } _ { j } = { \frac { \vec { I _ { j } } } { { \mathsf { R S S } } } } } \end{array} }
$$

where $J$ is the total number of coil elements in an array; $\stackrel {  } { I _ { j } }$ is the fullFOV image obtained with the $j .$ -th coil; $S _ { j }$ is the sensitivity map of the individual coil.

The direct division in Eq.(1b) can easily generate singular values.The different singular value distributions of each coil can cause inaccurate reconstructions which,particularly in this work,can misinform the registration process.

Singular values are commonly seen at the interfaces (i.e.skin and skull,skin and air) for both magnitude and phase of the sensitivity maps.In addition,the phase of sensitivity is often unpredictably wrapped for the ultra high field MRI. To prepare sensitivity profiles for registration,a multi-level singular value removal algorithm was developed.Similarto methods employed in [35],the map was first divided into reliable and unreliable regions.The unreliable regions consist of singular values of the magnitude map,sensitivity voidsand phase discontinuities[36].An interpolation/extrapolation procedure [35],based on polynomial fitting,was then performed to correct the sensitivity profiles in the unreliable regions.

# 2.1.2.Optimal sensitivity combination

Due to the complex coil-tissue interactions at ultra high fields, after loading a heterogeneous subject like the human brain,the sensitivity of each coil becomes distinct[25].For this reason,single coil sensitivity based estimation is compromised by insufficient coil-tissue information.In addition,the registration algorithm works less efficiently with signal voids that are commonly seen in single-channel sensitivity maps.For better estimation,sensitivityprofiles are linearly combined before applying registration.A similar method has been reported for optimal $B _ { 1 }$ mapping [31]. This process is expressed as:

$$
C _ { \mathrm { c o e f } } S _ { \mathrm { s i n g l e } } = S _ { \mathrm { c o m b i n e d } }
$$

where $C _ { \mathrm { c o e f } }$ denotes an $8 \times 8$ coefficient matrix; $S _ { \mathrm { s i n g l e } }$ is the sensitivity matrix resized to $8 \times N ^ { 2 }$ (resolution is $N \times N )$ and each row is a single coil sensitivity. $S _ { \mathrm { c o m b i n e d } }$ contains the linearly combined sensitivity maps.

During rotating,the coil-tissue interaction is fully transformed from one angular position to another and Eq.(2) is applied accordingly.As shown in Fig.2,to decompose the estimated individual $$ coil sensitivity $E _ { \alpha } ^ { 1 }$ from estimated combined sensitivity maps $E _ { \alpha } ^ { 8 }$ the inversion of $C _ { \mathrm { c o e f } }$ is multiplied to both sides of equation.With the method described in [31], the matrix $C _ { \mathrm { c o e f } }$ is determined with condition number 1 to minimise error.

# 2.1.3.The registration technique for sensitivity estimation

The goal of registration is to find the spatial correspondence between the source and target images.Registration techniques are widely used in medical imaging[27,28,37,38], such as when information from multiple modalities are combined (computed tomography (CT)，MRI，positron emission tomography (PET)), intra-subject motion correction,distortion correction,dynamic imaging reconstruction and high-field MRl safety assessment [30].A typical registration algorithm includes two components:a similarity metric and geometric deformation.The registration algorithmemployed here followed,in part,previously published works [29,39],while various components were adapted to suit the current application.For example,a similarity metric was modified to cope with complex-valued sensitivity maps.

2.1.3.1.Similarity metric. The similarity metric measures how well the source image aligns to the target image.Various metrics have been developed for image registration,suchas squared difference (SD),mutual information (MI) [4O,41] and pattern intensity(PI) [42].

Sensitivity maps are complex images.Both magnitude and phase of $B _ { 1 } ^ { + }$ and $B _ { 1 } ^ { - }$ exhibita rotational property [25]which offers opportunities to apply image registration techniques for estimating sensitivity maps.Magnitude imagesare relatively easy to be registered because the features are clear;however,registering phase images is problematic due to phase-wrapping. Even when the phase images are unwrapped, the unwrapping quality and phase ranges are difcult to control which can undermine the registration performance.To avoid this problem,the registration process in this work was not solely performed on phase images,but on the complex sensitivity maps.The PI metric was modified to cope with complex numbers.The SD metric was chosen for registering magnitude images due to its fast processing speed.Two registration processes were set to different convergence parameters for optimal performance.

For a source image $I _ { s } ( x , y )$ and a target image $I _ { t } ( x , y )$ ,a twodimensional SD and PI are defined as:

$$
\mathrm { S D } = \frac { \sum _ { x = 1 } ^ { X } \sum _ { y = 1 } ^ { Y } \left( I _ { s } ( x , y ) - I _ { t } ( x , y ) \right) ^ { 2 } } { X Y }
$$

$$
\begin{array} { l } { \displaystyle \mathsf { P I } _ { r , \sigma } = \sum _ { x , y } \sum _ { \left( x - u \right) ^ { 2 } + \left( y - v \right) ^ { 2 } \leqslant r ^ { 2 } } \frac { \sigma ^ { 2 } } { \sigma ^ { 2 } + \left( I _ { d i f f } \left( x , y \right) - I _ { d i f f } \left( u , \nu \right) \right) ^ { 2 } } } \\ { \displaystyle I _ { d i f f } = I _ { t } - I _ { s } } \end{array}
$$

where $x$ and $y$ are the voxel coordinates in the image, $X$ and Yare the numbers of the voxels along each dimension.In Eq.(3b), $I _ { \mathrm { d i f f } }$ is the difference image.The parameter $r$ defines the size of the neighbourhood,in which the variations are taken into account. The parameter $\sigma$ isa sensitivity controller to decide whether the variation is a structure or not.

2.1.3.2.Geometric deformation. Two types of geometric deformation,affine transformation and non-rigid transformation,were employed in this work.The affine transformation included translations and rotations,making it best suited for global transformations.The non-rigid transformation was applied to compensate the inefficiency of the affine transformation in local areas.In the non-rigid transformation,a deformation field recorded all displacement vectors at each voxel from an aligned source image to the target image.In this work,a free-from deformation (FFD) based on B-splines [43]was adopted for non-rigid transformations.The FFD worked by deforminga source image by manipulating a mesh of control grids [44].To improve its efficiency,a coarse-to-fine multilevel B-spline approximation was adopted to generate a series of B-spline functions incorporating bicubic interpolation functions for calculation of the deformed pixel values.

# 2.2.Image reconstruction and encoding optimisation

The rotating coil array emulates a large amount of coils with only four physical RF elements,thereby improving the condition of the encoding matrix to facilitate a higher reduction factor.However,the encoding ability of RRFCA can be further improved by strategically choosing the rotating degree for each stepping,which is determined by the $g .$ -map based optimisation algorithm[14].

# 2.2.1.Image reconstruction with rotating-SENSE

The number of sensitivity profiles limits the sensitivity encodingability ofa stationary coil array;therefore,the sensitivity profiles in the encoding matrix remain unchanged from row to row for each coil. However,the encoding matrix $\left( A _ { R } \right)$ of the RRFCA has more variations in its rows by taking rotational sensitivity into account:

$$
A _ { R } = { \left[ \begin{array} { l } { E S _ { 1 } } \\ { E S _ { 2 } } \\ { \vdots } \\ { E S _ { 4 } } \end{array} \right] }
$$

where $E = e ^ { i K _ { \kappa } r _ { \rho } }$ and $S _ { j } = S _ { j } ( r _ { \rho } , t )$

$\kappa \in [ 1 , M \times N / R ]$ = $t \in [ 1 , M / R ]$ ,Nis the length ofa $k$ -space line, $M$ is the number of $k$ -space lines and $R$ is the reduction factor.E and $S _ { j }$ denote the Fourier encoding and sensitivity encoding matrices, respectively. $K _ { \kappa }$ denotes the $\kappa$ -th $k$ -space sampling position; $r _ { \rho }$ and t in $S _ { j }$ denote the sensitivity at the position of $\rho$ -th voxel of the step t.

The Fourier encoding kernel is consistent between the stationaryand rotating array;however,sensitivity maps for individual coils $j$ at each steptare different as the coil rotates.Thisvariation improves the condition of encoding matrix and can be exploited for further scan time reduction [14].

The noise behaviour analysis of the rotating-SENSE is similar to that of the traditional stationary array.However,to employ $g$ -maps [7] for noise analysis,the sensitivity matrix S needs to be delineated from encoding matrix $A _ { R }$ ：

$$
A _ { R } = F S
$$

where $F$ and S represent the Fourier encoding matrix and sensitivity matrix,respectively.The sensitivity matrix S consists of the

![](images/f81ddfa91df29d97ad02ba83761546486a30c55192828f48c22ef90c1caa3ab2.jpg)  
Fig.3.(a)Top view of the RRFCA setup.The outside layer is the stationary 8-element transmit coil aray with $4 0 0 \mathrm { m m }$ diameter,inner layer is the 4-element RRFCA with （204号 $2 8 0 \mathrm { m m }$ diaeter(i ia transmit and receive coils.

acquired sensitivityand estimated sensitivityprofiles.See[14] for the process of separating $F$ and S.

# 2.2.2.Sensitivity encoding optimisation

The proposed method of estimating in vivo sensitivity maps enables us to investigate the optimal rotating scheme using numerical simulations.By optimally choosing the sampling position of each step,the sensitivity encoding capability can be maximised. At each angular position,the coil sampled one phase-encoding line. The angular displacement $\theta$ between adjacent acquisitions was determined by achieving the best imaging acceleration performance as follows:

$$
\arg \operatorname* { m i n } _ { \theta } \left\{ \sqrt { \frac { \sum _ { x = 1 } ^ { M } \sum _ { y = 1 } ^ { N } \left( g _ { x , y } ( \theta ) - 1 \right) ^ { 2 } } { M \times N } } \right\}
$$

where $\theta$ denotes the angular displacement between two $k$ -space lines, $g _ { x , y } ( \theta )$ is the $g \mathrm { . }$ -factor calculation[7] at voxel $( x , y )$ in an image with $M \times N$ pixels.

# 2.3.Experimental validation

The 4-channel RRFCA was used to scan two subjects,A and B,at 6 angular positions $( 0 ^ { \circ } , 1 0 ^ { \circ } , 2 2 ^ { \circ } , 4 5 ^ { \circ } , 5 5 ^ { \circ }$ and $6 7 ^ { \circ }$ in Fig.1). These data were firstly combined to simulate an 8-channel RRFCA(for reasons described previously).To test the proposed algorithm in an intra-subject case,images of subject A were acquired at two slices with $1 2 \mathrm { m m }$ spacing.Sensitivity maps of one slice were used asthe library.In the inter-subject case,sensitivity maps of subject A were used as the library to estimate sensitivity maps of subject B. The image registration techniques were then applied to both datasets for the estimation of the rotation-dependent sensitivity profilesat desired positions.

To study the rotating coil array in the reception mode independently without the complication from changing transmission profiles,a 4-element RRFCA[14] was used as a receive-only coil array. An additional transmit coil array was built to provide an unchanged and relativelyuniform transmission.The experimental setup is shown in Fig.3(b) with one healthy volunteer ona wholebody7T MRI scanner(Magnetom 7T MRI, Siemens Medical Solutions,Erlangen,Germany).All imaging protocols were approved byinstitutional review board of Institute of Biophysics of Chinese Academy of Sciences (Beijing),and signed consent forms were collected.Small-flip-angle $\mathrm { F A } = 3 0 ^ { \circ }$ )GREimages of two sliceswere acquiredwith $\mathrm { T E } / \mathrm { T R } = 4 / 1 0 0 0 \ : \mathrm { m s }$ (inplanevoxelsize $\mathbf { \sigma } = \mathbf { \sigma }$ $2 \ : \mathrm { m m } \times 2 \ : \mathrm { m m }$ ）

The RRFCA system consisted of three layers.The stationary inner layer was isolated from the rotating coils and provided support to a patient's head.The receive coils were attached to a rotatablemiddle layer and the transmit coils were attached to a stationary outer layer.The radius of the inner layer was set to $1 2 5 \mathrm { m m }$ to comfortably accommodate the human head.As shown in Fig.3(a) and (c),the transmit coil array consisted of eight loop coils,each of which was $1 6 0 \mathrm { m m }$ in length and $1 3 0 \mathrm { m m }$ in width. They were attached equidistantly to a coil former.A capacitance decoupling method was used to keep the coupling at a reasonably low level of $- 1 2 { \mathrm { ~ d B } } \sim - 1 4 { \mathrm { ~ d B } }$ when loaded.To reduce the interactionand parasitic capacitance between the transmit and receive coils,besides employing active detuning circuits,a transmit coil former with a large radius should be used.However,in order to minimise the signal drop caused by the increased distance and to guarantee consistent rotation,the radius of the middle layer was set to $1 4 0 \mathrm { m m }$ to provide a $1 5 \mathrm { m m }$ separation from the inner layer. (Fig. 3(a), $\varnothing$ transmit: $4 0 0 \mathrm { m m }$ 1 $\mathcal { O } _ { \mathrm { r e c e i v e } }$ ： $2 8 0 \mathrm { m m }$ )

Anextended shaft [14] was used to adjust the rotation angle outside of the MRl tunnel without repositioning the coil-subject set for acquisition at each angular(stepping） position.However, unlike the experiment setup using phantoms [14],the rotation indicatorand the extended shaft were installed at the rear of the magnet bore (Fig.3(b)) to allow enough space for the patient.

# 3. Results

Fig.4(a)and (b) shows the gradient recalled echo (GRE) images of two slices from subject A.The GRE image of subject B (same slice locationas Fig.4(b)) is shown in Fig.4(c).Their corresponding sensitivity maps are shown in (d)-(f).Since there isa large difference in head size and thus in global dielectric properties between subjects,large sensitivity variations are found even at the same slice location.As seen from Fig.4(a) and (b), the anatomical structure and dielectric property of the two slices (subject A) from one subject are very different,but their sensitivity maps have minor changes shown in Fig.4(d) and (e).This correlates with the observation that the sensitivity is more related to global dielectric changes rather than local changes.

![](images/f9dd92a23ece73223ab52d56a64cce15a748b68101c29df943da6b6f49bf555b.jpg)  
Fig.4.(a) and(b) are GRE images of two slices ( $1 2 \mathrm { m m }$ separation) from subject A at position 1 $( 0 ^ { \circ } ) .$ (c) Image from subject B of the same slice position in(b)at position 1 $( 0 ^ { \circ } )$ Their corresponding sensitivity maps are shown in (d)-(f) respectively.

![](images/60bc92f03cb4d879d09e429b465b64f84c0af22d25e7c596faa9da8cd096de56.jpg)  
Fig5.(ai sit ii the web version of this article.)

Theraw magnitude and phase maps of sensitivity derived from Eq.(1a,b) are shown in Fig.5(a)and (c),respectively.As predicted, coil sensitivity maps should be smooth with a small local gradient. However,in Fig.5(b) and(d),we can see that the coil sensitivity maps had abrupt changes which were associated with high gradients (markedasred dots).Magnified regions in the red boxes show the singular values.In addition,the phase map in Fig.5(c) also exhibits the phase wrapping at the skin/air and the skull/tissue interface.

With the developed multi-level fiting algorithm,both the magnitude and phase images were smooth with the singular values corrected.In Fig.6(a),the signal voids were also extrapolated for image registration purposes.Compared to Fig.5(b） and(d),the high gradient and undulating errors were corrected. Both the magnitude and phase plots of sensitivity were smooth and natural.

The experimentally acquired and numerically estimated sensitivity maps for the intra-subject case are compared in Fig.7.With a $1 0 ^ { \circ }$ angular displacement (p2 in Fig.7(a)), the estimated magnitude maps in the second row of Fig.7(a) were very similar to the measured sensitivity maps in the first row.Both the global features and the local details were estimated accurately.Estimated phase maps in the fourth row only showed small local variations compared to the acquired maps.Combining the magnitude and phase plots into a complex-numbered sensitivity,the root-mean-square error(RMSE) of the estimated sensitivity is O.048.In Fig.7(b), the angulardisplacement increased to $2 2 ^ { \circ }$ (position 3),which was also thelargest displacement for the rotational sensitivity estimation under the current configuration. From the comparisons between the estimated and measured sensitivity maps in Fig.7(b),we note that the minor local discrepancies started to present,although the global features of sensitivity maps were well captured by the registration based algorithm.The RMSE increased to O.O68 at p3, which suggested a slightly decreased accuracy of estimating sensitivity with a larger angular displacement.

For the inter-subject case,the experimentally acquired and numerically estimated sensitivity maps at position 2 (p2 in Fig. 8(a)) and position 3 (p3 in Fig. 8(b)) are compared in Fig. 8.

![](images/39da434976d8dc67087e87f05888c05b67b92cf847a33d9c7aa05a9eca0d7c07.jpg)  
Fig.6.(a) magnitude (top row) and phase (bottom row) plots of refined sensitivity map at $0 ^ { \circ }$ .(b) 3D magnitude (top row) and phase (bottom row) plots of refined sensitivity map for single coil.

The female subject hada noticeably smaller head than that of the male subject, therefore the sensitivity maps of two subjects have more differences compared to the intra-subject case.However,as shown in Fig.8(a),the registration based algorithm was able to estimate the magnitude and phase maps of sensitivityaccurately,both globallyand locally.TheRMSEwas O.054,whichisslightly higher than that of the same position in the intra-subject case $( \mathrm { R M S E } = 0 . 0 4 8 )$ ).Different from the intra-subject case,the RMSE reduced to O.O45 when the angle was then increased to $2 2 ^ { \circ }$ for position 3.

To illustrate the imaging acceleration and reconstruction ability of the RRFCA, the $g$ -maps,reconstructed images and the SNR maps are shown in Fig.9 when the reduction factor was four $\left( R = 4 \right)$ . The measurements with 4-element RRFCA sampled at two angular positions(position $1 \colon 0 ^ { \circ } + 4 5 ^ { \circ } ,$ ）wereused togetherto emulatean 8-element stationary coil array.In the first and second rows, results reconstructed from the experimental data for 4-and 8-element stationary arrays are shown,respectively.However,the coil elements of the RRFCA were naturally decoupled $( - 1 8 \mathrm { d B } S _ { x y } )$ which would be more difficult to realise with an 8-element coil arrayinthe same size.Therefore the max $g _ { \ l }$ -factorinthe second row may be higher than 1.7 and the averaged relative-SNR may be lower than 2.35 in practice.

Since the SNRis hardto calculateaccurately forultra high field MRI, the SNR maps in this work were calculated relative to that of a singlerotating coil withoutundersampling $( R = 1 )$ .Aswe can see in Fig.9,with a high reduction factor $\left( R = 4 \right)$ ,the 4-element stationary coilarrayhadavery high $g _ { \ l }$ -factor $\mathrm { ( m a x - } g = 3 . 7 \mathrm { ) } .$ anda0.95averaged relative-SNR,which corresponded to a very noisy image with strongaliasingartifact.In contrast,under the rotating scheme of visiting 32 positions,the max $g$ -factor(the fourth row）of 4-element RRFCA decreased to 1.6,which was comparable to the stationary coil arraywith twiceas many elements (max $g = 1 . 7$ ）in the second row.The reconstructed image was better with lower RMSEandartifactpower[45] $( \mathrm { R M S E } = 0 . 0 2 3$ ，artifact power $\mathbf { \tau } = 0 . 0 0 8 2$ ）compared to the 4-element stationary array （20 $( \mathrm { R M S E } = 0 . 0 3 9$ ，artifactpower $= 0 . 0 2 3 1$ ).However,fewer sensitivityprofiles were available when visiting fewerangular positions, leading to higher $g \mathrm { . }$ -factorsand less capability in imagingacceleration.As shown in the third row,the maximum $g .$ -factor increased to 2.5by only visiting six positions,and aliasing artifacts started to emerge in the reconstructed image.It is well known that the SNR is proportional to the square root of the number of channels [4,46].To providea fair comparison,an 8-channel RRFCA was simulated by combining two sets of sensitivity profiles of the 4-channel RRFCA with a $4 5 ^ { \circ }$ rotation. The $g \mathrm { . }$ -map,reconstructed images

# Subject A,Slice1,p1→ Slice2,p2

![](images/b73e79919aad0328e614284c9654f230de3c2472b71a5540ce81eef4652e667c.jpg)

![](images/172a15ab9279f968a4a55f60dc1e2fff1292db55340e2d60044587b7906d5a9c.jpg)  
Subject A, Slice1,p1 → Slice2,p3   
row,experimentallyacquiredmagnitudema ps atp2;econdrow,numericallestimated magnitudemapsatp2;thirdrow: experimentallyacquiredphasemapsatp;fourth row, numerically estimated phase maps at p3.

and the SNR maps were shown in the fifth row for such a coil array. Compared to the second row,we can see that with the same number of coils,not only was the relative-SNR of RRFCA(relative$\mathsf { S N R } = 2 . 8 3 \AA$ ）higher than that of the stationary array (relative$\mathsf { S N R } = 2 . 3 5$ ),but also the global SNR map was more uniform.

# 4. Discussion

# 4.1.The library data

The library data was used to provide sensitivity maps at all angular degrees,and the registrationalgorithm was used to bridge the discrepancy between the library and actual sensitivity maps. Theoretically,the library data can be either experimentally measured or numerically calculated.The experimentally acquired sensitivity maps may be more realistic,but obtaining 3-dimensional maps at multiple positions can be time-consuming.Acquisition speed may be further restricted due to the potential heating problem forultra high field MRI.

Commercially available electromagnetic(EM) software can be employed to calculate sensitivity maps and avoid such problems. With differentalgorithms,EM field distributionsand related coil sensitivity can be calculated by solving Maxwell's equations.The Method of Moments (MOM) [13,18,47-50],used for calculating the EM field,is efficient for homogeneous loads,but it is not feasible to calculate heterogeneous dielectric loads due to the complexity of calculating the Green function [51]. The Finite Element Method (FEM) [52],discretising heterogeneous subjects into tetrahedral or hexahedral elements,is capable of representing complex heterogeneous subjects smoothly and providing a more accurate solution.However,the FEM requires very large computational resources for discretising the subjects and would have taken substantialamount of time to accurately evaluate $B _ { 1 }$ .The Finite-Difference Time-Domain (FDTD）method [53-59] has advantages over theFEMas it simplifies the discretisation into regular boxes,and the iterative solution saves on computational resources.Working in conjunction with a graphical processing unit (GPU),the calculation time can be dramatically reduced [60].

![](images/a3cdefcf651e6c7ad61091f3405d0fe68c80ba63100db8dc953e61717af6d8a7.jpg)  
Slice 2:Subject A,p1→ SubjectB,p2

![](images/af8afe8f53eb53d054177d237ff4bb24914d4db88726418be3d6fbf48122b390.jpg)  
Slice 2: Subject A,p1→ Subject B, p3   
t oxll row, numerically estimated phase maps at p3.

# 4.2. Transmit $B _ { \imath } ^ { + }$

A signal intensity image is determined by both transmit profile $B _ { 1 } ^ { + }$ and receive sensitivity $B _ { 1 } ^ { - }$ as illustrated in Eq.(7).At low field, the $\big | B _ { 1 } ^ { + } \big |$ is uniform and thus can be excluded from the sensitivity encoding matrix in the SENSE reconstruction.However,to include the $| B _ { 1 } ^ { + } |$ influence in the SENSE reconstruction at ultra high fields, the actual sensitivity map in the encoding matrix should be in the form of Eq. (8) [14,61].

$$
\begin{array} { r l } & { \mathrm { S I } = M _ { 0 } | B _ { 1 } ^ { - * } | \sin \left( V \gamma \tau | B _ { 1 } ^ { + } | \right) } \\ & { \mathrm { s e n s i t i v i t y } _ { \mathrm { a c t u a l } } = \sin \left( V \gamma \tau | B _ { 1 } ^ { + } | _ { \mathrm { s h i m } } \right) B _ { 1 } ^ { - } } \end{array}
$$

where γ is the gyromagnetic ratio and $M _ { 0 }$ is proportional to the proton density distribution. $\tau$ and $V$ denotes the RF pulse duration and coil driving voltage.The asterisk denotes the complex conjugate operation.

In this work,an 8-element coil array was manufactured and actively detuned to provide an unchanged $B _ { 1 } ^ { + }$ in the course of rotation.However,the $\lvert B _ { 1 } ^ { + } \rvert$ inevitably changed as the array rotated, which may have introduced a small bias into the reconstruction when this changing field was not considered in the encoding

Imaging performance comparisonsat reduction factor 4 $( \mathsf { R } = 4 )$ g-map Reconstruction SNR 4-coil stationary S max g= 3.7 relative-SNR=0.95 8-coil O O   
stationary max g=1.7 relative-SNR=2.35 RRFCA O   
6 positions max g= 2.5 relative-SNR=1.02   
4-element O RRFCA   
32 positions max g=1.6 ga   
8-element RRFCA   
32 positions max $\mathfrak { g } = 1 . 3 5$ relative-SNR=2.83

matrix.To further improve the sensitivity encodingability of the RRFCA and faithfully reconstruct the image,it may be advantageous to adopt a composite sensitivity concept [14].Our future work will involve the development of the sensitivity estimation algorithm for the RRFCA working in transceive mode.

# 4.3.SNR calculation

As an important metric to quantitatively evaluate image quality,the SNR calculation for MRI has been extensively studied [4,62-65]. At ultra high field $( > 3 T )$ ,the SNR can be expressed as [62,66]:

$$
\mathsf { S N R } = \frac { V _ { \mathrm { s i g n a l } } } { V _ { \mathrm { n o i s e } } } \propto \frac { B _ { 0 } ^ { 2 } \int _ { \mathsf { V O I } } W \sin { \left( V \gamma \tau | B _ { 1 } ^ { + } | \right) } | B _ { 1 } ^ { - } | d \nu } { \sqrt { P _ { \mathrm { s a m p l e } } } }
$$

where the integration is performed over the volume of interest (VOI)and $W$ isaweighting factor related to tissue and sequence.

The $P _ { \mathrm { s a m p l e } }$ is the power dissipated in the sample,which is too complex to be efficiently calculated for rotating array coils at ultra high fields.Thus the relative SNR was reported.In this work,to simplify the comparison, the $P _ { \mathrm { s a m p l e } }$ for different arrays were considered the same [67],since transmission power remained approximately the same for different arrays.

In parallel imaging,the reduced $k$ -space dataare recovered by employing the coil sensitivity profiles.However,the noise is inevitably amplified in the reconstruction process,especially with a high reduction factor. The SNR calculation when employing parallelimaging algorithms,such as SENSE,can be calculated as below [7],provided that the channel number does not change:

$$
\frac { S \mathrm { N R } _ { \mathrm { P I } } } { S \mathrm { N R } _ { \mathrm { f u l l } } } = \frac { 1 } { g \sqrt { R } }
$$

where $g$ and $R$ denotes the $g$ -mapand reduction factor,respectively. The SNR is also proportional to the square root of the number of channels [4,46].In order to provide a fair SNR comparison,we

simulated the 8-channel RRFCA by combining data obtained with a $4 5 ^ { \circ }$ separation.

# 4.4. RRFCA structure and data sampling

# 4.4.1. Coil geometry

Using a large number of RF coils can increase the SNR and significantly accelerate the imaging process [68-71]. However,placinga large number of coils in a constrained space will decrease the coil size,leading toa shallower $B _ { 1 }$ penetration.Namely,smaller coils receive less signal from the centre compared to larger coils. In addition,a coil array with higher density can increase the difculty of decoupling. Coil coupling undermines the parallel imaging performance and reduces the SNR.By employing the rotating scheme, the RRFCA not only provides a large number of sensitivity profiles without additional RF channels,but also allows bigger coils to be used with less decoupling complexity.

# 4.4.2. Data sampling

The RRFCA is designed to sample one $k$ -space line at each stepping position,and then move to the next angular position for the following sampling. In this preliminary in vivo study, the stepping angle was manually adjusted and a full $k$ -space matrix was sampled at each angular position.The accelerated acquisition was numerically modelled by extracting and combining the corresponding $k$ -space lines.

# 4.4.3.Rotating speed and acoustic noise

In this proof-of-concept work,the RRFCA was manually rotated to sample dataat several angularpositions in order to validate the proposed in vivo sensitivity estimation algorithm.In our previous works[1O,11]，the rotating coil was pneumatically driven to achieve up to $8 7 0 \mathrm { r p m }$ for human head imaging with negligible acoustic noise,compared with noise generated by the gradient system.For animal imaging,the rotating speed can easily exceed $1 0 , 0 0 0 \mathrm { r p m }$ .Our recent experiments on a 9.4T pre-clinical system have shown that the rotating coil can faithfully reconstruct the images at speeds of,or exceeding, $5 5 0 0 \mathrm { r p m }$

# 5.Conclusion

In this paper,an in vivo rotational sensitivity estimation algorithm for the RRFCA was proposed and verified using human head imaging.By taking advantage of registration techniques and a library data,the algorithm was able to estimate sensitivity maps with arbitrary angular displacement.The estimated sensitivity maps were then fed into the rotating-SENSE algorithm to improve theimaging acceleration ability of the 4-element RRFCA.The 4- channel RRFCA outperformed the 4-element stationary array and was comparable to 8-element stationary PACs in terms of $g$ -map and reconstruction quality.The 8-element RRFCA has been shown to significantly improve image quality compared to a stationary 8- element coil array.In the future,a sensitivity estimation algorithm foratransceive RRFCAwith“composite sensitivity"will be developed.Bytaking $B _ { 1 } ^ { + }$ intoaccount in sensitivity encoding,the imagingacceleration ability of the RRFCA can be further improved. Additionally,an automatic rotation control system for the RRFCA will be developed by means of,for example,a non-magnetic piezo-electric or ceramic motor.

# Acknowledgments

This work was supported by Australian Research Council, the MinistryofScienceandTechnologyofChinaGrant (2012CB8255oO), the Chinese National Major Scientific Equipment

R&D Project (Grant No. ZDYZ201O-2), the National Nature Science Foundation of China Grant (91132302） and the Chinese Academy of Sciences Grants (XDB02010001 and XDB02050001).

# References

[1] P.Mansfield, Multi-planar image formation using NMR spin echoes,J. Phys. C: Solid State Phys. 10(1977) L55. [2] J. Listerud, S. Einstein,E. Outwater,H.Y. Kressel, First principles of fast spin echo,Magn. Res0n. Q. 8 (1992) 199-244. [3] P.van der Meulen,J.P. Groen,J.J. Cuppen, Very fast MR imaging by field echoes and smallangle excitation, Magn. Reson. Imaging 3 (1985) 297-299.   
[4] P.B. Roemer, W.A. Edelstein, C.E. Hayes, S.P. Souza, O.M. Mueller, The NMR phased array, Magn. Reson. Med. 16 (1990) 192-225. [5] S.M. Wright,L.L. Wald，Theory and application of array coils in MR spectroscopy, NMR Biomed. 10 (1997) 394-410. [6] D.K. Sodickson, W.J. Manning, Simultaneous acquisition of spatial harmonics (SMASH): fast imaging with radiofrequency coil arrays, Magn. Reson. Med. 38 (1997) 591-603.   
[7] K.P. Pruessmann, M. Weiger, M.B. Scheidegger, P. Boesiger, SENSE: sensitivity encoding for fast MRI, Magn. Reson. Med. 42 (1999) 952-962.   
[8] K.P. Pruessmann,M. Weiger, P. Bornert, P. Boesiger, Advances in sensitivity encoding with arbitrary $k$ -space trajectories，Magn. Reson. Med. 46(2001) 638-651.   
[9]M.A. Griswold, P.M. Jakob, R.M. Heidemann, M. Nittka, V. Jellus,J. Wang, et al., Generalized autocalibrating partially parallel acquisitions (GRAPPA)， Magn. Reson. Med.47 (2002) 1202-1210.   
[10] A. Trakic, B.K. Li, E. Weber, H. Wang, S. Wilson, S. Crozier, A rapidly rotating RF coil for MRI, Concepts Magn. Reson. Part B: Magn. Reson. Eng.35B (2009) 59- 66.   
[11] A. Trakic, H. Wang,E. Weber,_B.K. Li, M. Poole,F. Liu, et_al.， Image reconstructions with the rotating RF coil,J. Magn. Reson. 201 (2009) 186-198.   
[12] M.Li, Jin Jin,Feng Liu,Ewald Weber, Adnan Trakic,Stuart Crozier,Highly accelerated parallel MRI using rotating radiofrequency coil array at7T,in: 21st Annual Meeting and Exhibition of ISMRM, Salt Lake City, Utah,USA,2013.   
[13]M.Li,J. Jin,A. Trakic,F.Liu,E.Weber,Y.Li,et al.,High acceleration with rotating radiofrequency coil array (RRFCA） in parallel magnetic resonance imaging (MRI),in:Presented at the 34th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC'12),San Diego, 2012.   
[14]M. Li, Z. Zuo, J. Jin,R. Xue,A. Trakic,E.Weber,et al.,Highly accelerated acquisition and homogeneous image reconstruction with rotating RF coil array at 7T- A phantom based study, J. Magn. Reson. 240 (2014) 102-112.   
[15] S. Crozier, LM. Brereton, F.O. Zelaya, W.U. Roffmann, D.M. Doddrell, Sampleinduced RF perturbations in high-feld, high-resolution NMR spectroscopy,J. Magn. Res0n. 126 (1997) 39-47.   
[16] P.S. Tofts, Standing wave in uniform water phantoms, J. Magn. Reson. 104 (B) (1994) 143-147.   
[17]F.Liu, S. Crozier, Electromagnetic fields inside a lossy, multilayered spherical head phantom excited by MRl coils: models and methods, Phys. Med. Biol. 49 (2004) 1835-1851.   
[18]F.Liu, B.L. Beck, B. Xu, J.R. Fitzsimmons, S.J. Blackband, S. Crozier, Numerical modeling of 11.1T MRl of a human head using a MoM/FDTD method, Concepts Magn. Reson. Part B: Magn. Reson. Eng. 24B (2005) 28-38.   
[19] G.McLaughlin,T.Ji,D.Napolitano,Material probing method for medical application,involves receiving echoes generated by interactions between ultrasound beam and material,and converting received echoes to generate echolocation data, United States Patent US2004147841-A1,2004.   
[20] L.B. Pierre-Marie, Robitalle, Ultra High Field Magnetic Resonance Imaging, Springer Science $^ +$ Business, Media, New York, USA, 2006.   
[21] T.S. Ibrahim,R. Lee,A.M. Abduljalil, B.A. Baertlein,P.M. Robitaille,Dielectric resonances and B(1) field inhomogeneity in UHFMRl: computational analysis and experimental findings, Magn. Reson. Imaging 19 (2001) 219-226.   
[22] A. Kangarlu, B.A. Baertlein, R. Lee, T. Ibrahim, L. Yang, A.M. Abduljalil, et al., Dielectric resonance_phenomena in ultra high field MRI, J. Comput. Assist. Tomogr.23(1999) 821-831.   
[23] C.M. Collins, W. Liu, W.Schreiber, Q.X. Yang, M.B.Smith, Central brightening due to constructive interference with，without， and despite dielectric resonance, J. Magn. Reson. Imaging 21 (2005) 192-196.   
[24] Q.X. Yang, J. Wang, X. Zhang, C.M. Collins, M.B. Smith, H. Liu, et al., Analysis of wave behavior in lossy dielectric samples at high field, Magn. Reson. Med. 47 (2002) 982-989.   
[25] P.F. Van de Moortele, C. Akgun, G. Adriany, S. Moeller, J. Ritter, C.M. Collins, etal., B(1) destructive interferences and spatial phase patterns at 7T with a head transceiver array coil, Magn. Reson. Med. 54 (2005) 1503-1518.   
[26] T.S. Ibrahim, R. Lee, B.A. Baertlein, A.M. Abduljalil, H. Zhu, P.M.L. Robitaille, Effect of RF coil excitation on field inhomogeneity at ultra high fields: a field optimized TEM resonator, Magn. Reson. Imaging 19 (2001) 1339-1347.   
[27] D.L. Hill, P.G. Batchelor, M. Holden, D.J. Hawkes, Medical image registration, Phys. Med. Biol.46 (2001) R1-R45.   
[28]M. Holden, A_review of geometric_transformations for nonrigid body registratinn IFFF Trans Med Imaging 27(2008)111-128   
[29] D. Rueckert, L.I. Sonoda, C. Hayes, D.L. Hill, M.O. Leach, D.J. Hawkes, Nonrigid registration using free-form deformations: application to breast MR images, IEEE Trans. Med. Imaging 18(1999) 712-721.   
[30] J. Jin,F. Liu,E. Weber, S. Crozier, Improving SAR estimations in MRI using subject-specific models, Phys. Med. Biol. 57 (2012) 8153-8171.   
[31] S.J. Malik,D.J. Larkman, J.V. Hajnal, Optimal linear combinations of array elements for B1 mapping, Magn. Reson. Med. 62 (2009) 902-909.   
[32] L. Ying, J. Sheng, Joint_image reconstruction and sensitivity estimation in SENSE (JSENSE), Magn. Res0n.Med.57 (2007) 1196-1202.   
[33] C.A. McKenzie,E.N. Yeh，M.A. Ohliger，M.D. Price，D.K. Sodickson，Selfcalibrating parallel imaging with automatic coil sensitivity extraction, Magn. Reson. Med. 47 (2002) 529-538.   
[34] F. Huang, Y. Chen, W. Yin, W. Lin, X. Ye, W. Guo,et al.,A rapid and robust numerical algorithm for sensitivity encoding with sparsity constraints: selffeeding sparse SENSE, Magn. Reson. Med. 64 (2010) 1078-1088.   
[35] J. Jin,F. Liu, E.Weber, Y. Li, S. Crozier,An electromagnetic reverse method of coil sensitivity mapping for parallel MRl - theoretical framework, J. Magn. Reson. 207 (2010) 59-68.   
[36] M.D.P.Dennis, C. Ghiglia, Two-Dimensional Phase_ Unwrapping: Theory, Algorithms,and Software, John Wiley and Sons Inc., 1998.   
[37] J.B. Maintz, M.A. Viergever, A survey of medical image registration, Med. Image Anal. 2 (1998) 1-36.   
[38]R.Wan,M.Li，An overview of medical image registration，in:Fifth International Conference on Computational Intelligence and Multimedia Applications,ICCIMA,Proceedings,2003,pp.385-390.   
[39] J. Jin,F. Liu， S. Crozier, Image registration guided, sparsity constrained reconstructions for dynamic MRI, Magn. Reson. Imaging 32 (2014) 1403-1417.   
[40] F.Maes,A. Collignon, D. Vandermeulen, G.Marchal, P. Suetens,Multimodality image registration by maximization of mutual information, IEEE Trans. Med. Imaging 16(1997) 187-198.   
[41] J.P.W. Pluim， J.B.A. Maintz, M.A. Viergever， Mutual-information-based registration of medical images: a survey, IEEE Trans. Med. Imaging 22 (2003) 986-1004.   
[42] T.M.B.J. Weese, C. Lorenz, C. Fassnacht, An approach to 2D/3D registration of a vertebra in 2D X-ray fluoroscopy, CVRMed/MRCAS (1997) 119-128.   
[43]D.Rueckert，P. Aljabar，R.A. Heckemann， J.V. Hajnal，A. Hammers, Diffeomorphic registration using B-splines，Med. Image Comput. Comput. Assist. Interv.9 (2006) 702-709.   
[44] L. Seungyong, G. Wolberg, S. Sung-Yong, Scattered data interpolation with multilevel B-splines, IEEE Trans. Visual. Comput. Graphics 3(1997) 228-244.   
[45] C.A. McKenzie, E.N. Yeh, D.K. Sodickson, Improved spatial harmonic selection for SMASH image reconstructions,Magn. Reson. Med.46 (2001) 831-836.   
[46] D. Liang, H.T. Hui, T.S. Yeo, Increasing the signal-to-noise ratio by using vertically stacked phased array coils for low-field magnetic resonance imaging, IEEE Trans. Inf. Technol. Biomed.16 (2012) 1150-1156.   
[47] R.F. Harrington, Field Computation by Moment Methods,John Wiley and Sons, New York, 1996.   
[48] H. Ochi, E. Yamamoto,K. Sawaya,S. Adachi, Analysis of a magnetic-resonanceimaging antenna inside an RF shield, Electron. Commun. Jpn. Part I-Commun. 77 (1994) 37-45.   
[49] S.Wright,M. Lee,Full-wave moment of method analysis of RF coils on lossy media,in:Proceeding of the 6th Annual Meeting of 1Oth ISMRM,San Francisco,USA,1991.   
[50] J. Jin,F. Liu, E. Weber, Y. Li, S. Crozier, An electromagnetic reverse method of coil sensitivity mapping for parallel MRl - theoretical framework, J. Magn. Reson. 207 (2010) 59-68.   
[51] B.K. Li,F. Liu, E. Weber, S. Crozier, Hybrid numerical techniques for the modelling of radiofrequency coils in MRI, NMR Biomed. 22 (2009) 937-951.   
[52] J.M. Jin, J. Chen, On the SAR and field inhomogeneity of birdcage coils loaded with the human head, Magn. Reson. Med. 38 (1997) 953-963.   
[53] K. Yee, Numerical solution of initial boundary value problems involving Maxwel's equations in isotropic media, IEEE Trans. Antennas Propagation 14 (1966)302-307.   
[54] K. Ugurbil,M. Garwood,J. Ellermann,K. Hendrich,R. Hinke, X.P. Hu, et al., Imaging at high magnetic-fields - initial experiences at 4-T,Magn. Reson. Q. 9 (1993) 259-277.   
[55] C.M. Collins, M.B.Smith,Signal-to-noise ratio and absorbed power as functions of main magnetic field strength, and definition of ${ } ^ { \mathfrak { a } } \mathfrak { g } 0$ degrees" RF pulse for the head in the birdcage coil, Magn. Reson. Med. 45 (2001) 684-691.   
[56] T.S. Ibrahim, A numerical analysis of radio-frequency power requirements in magnetic resonance imaging experiment, IEEE Trans. Microwave Theory Tech. 52 (2004) 1999-2003.   
[57] F. Liu, S. Crozier,An FDTD model for calculation of gradient-induced eddy currents in MRI system,IEEE Trans. Appl. Supercond.14(3)(2004) 1983-1989.   
[58] F. Liu, S. Crozier, H Zhao, iwrence, Finite-difference time-domain-based studies of MRl pulsed field gradient-induced eddy currents inside the human body, Concepts Magi   
[59] A. Trakic, J. Jin, M.Y. Li,I . Weber,F. Liu, etal., A comparative numerical study of rotating RF coils in terms of flip angle and specific absorption r lagn. Res0n.236 (2013) 70-82.   
[60]J. Chi,F.Liu,E.Weber,Y.Li,( Stuart J-accelerated FDTD modeling of radiofrequency field-tissue interactions in high-field MRI, IEEE Trans. Biomed. Eng. 58 (2011) 1789-1796.   
[61] C.M. Collins, Q.X. Yang, J.H. Wang, X. Zhang,H. Liu, S. Michaeli, et al., Different excitation and reception distributions with a single-loop transmit-receive surface coil near a head-sized spherical phantom at 3oo MHz, Magn. Reson. Med.47 (2002)1026-1028.   
[62] C.M. Collins,M.B.Smith, Signal-to-noise ratio and absorbed power as functions of main magnetic field strength,and definition of “9Oo" RF pulse for the head in the birdcage coil, Magn. Reson. Med. 45 (2001) 684-691.   
[63] W.A. Edelstein, G H.Glover, Hardy,R.W.Redington,The intrinsic signal-tonoiseratioinNMRimaging Magn. Res0n. Med.3(1986) 604-618.   
[64]D.I. Hoult, R.E. Richards signal-to-noise ratio of the nuclear magnetic resonance experiment Magn Reson. (1969) 24(1976) 71-85.   
[65] J.T. Vaughan, M. Garwood, Collins,W. Liu,L. DelaBarre, G. Adriany, et al., 7T vs. 4T: RF power, homogeneity,and signal-to-noise comparison in head images,Magn. Reson.Med. 46 (2001) 24-30.   
[66] D.I. Hoult, D. Phil, Sensitivity and power deposition in a high-field imaging experiment, J. Magn. Reson. Imaging 12 (2000) 46-67.   
[67] A.Trakic,J. Jin, M.Y. Li, D. McClymont, E.Weber, F. Liu, et al., A comparative numerical study of rotating and stationary RF coils in terms of flip angle and specific absorption rate for 7T MRl, J. Magn. Reson. 236 (2013) 70-82.   
[68] G.C. Wiggins,j.R. Polimeni, A. Potthast, M.Schmitt, V. Alagappan, L.L. Wald,96- Channel receive-only head coil for 3 Tesla: design optimization and evaluation, Magn. Reson. Med. 62 (2009) 754-762.   
[69] M. Schmitt,A. Potthast, D.E. Sosnovik, JR. Polimeni， G.C. Wiggins，C. Triantafyllou,et al.，A 128-channel receive-only cardiac coil for highly accelerated cardiac MRl at3 Tesla, Magn. Reson. Med. 59 (2008) 1431-1439.   
[70] C.J. Hardy,R.O. Giaquinto,J.E. Piel, K.W. Rohling,L. Marineli, D.J. Blezek, et al., 128-Channel body MRI with a flexible high-density receiver-coil array, J. Magn. Reson. Imaging 28 (2008) 1219-1225.   
[71] G.C. Wiggins, C. Triantafyllou, A. Potthast, A. Reykowski, M. Nittka, L.L. Wald, 32-Channel 3 Tesla receive-only phased-array head coil with soccer-ball element geometry, Magn. Reson. Med.56 (2006) 216-223.