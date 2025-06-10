# RESEARCH ARTICLE

# Bayesian localization microscopy based on intensity distribution of fluorophores

Fan $\mathsf { X } \mathsf { u } ^ { 1 , 2 }$ ,Mingshu Zhang³, Zhiyong Liu1, Pingyong $\mathsf { \pmb { x } } \mathsf { \pmb { u } } ^ { 3 \boxtimes }$ ,Fa Zhang1

1 KeyLabof Inteligent Information Processing,Instituteof Computing Technology，Chinese Academyof Sciences,Beijing 100190,China   
2 Universityof Chinese Academy of Sciences,Beijing 10o049,China   
3 Laboratory of Non Coding RNA, Institute of Biophysics,Chinese Academy of Sciences,Bejing 100101,China   
区Correspondence: pyxu@ibp.ac.cn (P. Xu), zhangfa@ict.ac.cn (F. Zhang)   
Received December 3,2014 Accepted December 31,2014

# ABSTRACT

Super-resolution microscopy techniques have overcome the limit of optical diffraction. Recently，the Bayesian analysis of Bleaching and Blinking data (3B) method has emerged as an important tool to obtain super-resolution fluorescence images.3B uses the change in information caused by adding or removing fluorophores in the cell to fit the data. When adding a newfluorophore,3B selectsa random initial position, optimizes this position and then determines its reliability.However, the fluorophoresare not evenlydistributed in the entire image region,and the fluorescence intensity at a given position positively correlates with the probability of observing a fluorophore at this position. In this paper, we present a Bayesian analysis of Bleaching and Blinking microscopy method based on fluorescence intensity distribution (FID3B). We utilize the intensity distribution to select more reliable positions as the initial positions of fluorophores. This approach can improve the reconstruction results and significantly reduce the computational time. We validate the performance of our method using both simulated data and experimental data from cellular structures.The results confirm the effectiveness of our method.

KEYWORDS super-resolution,fluorescence image,3B, intensity distribution

# INTRODUCTION

Fluorescence microscopy,which enables the observation of living cell structures,organelles and even small molecules, playsan indispensable role in life science.However， the spatialresolution ofconventional lightmicroscopyis restricted to approximately half the emission wavelength due to optical diffraction (Hell, 20o7).To overcome this limitation, severalsuper-resolutionfluorescencemicroscopytechniques based on single-molecule localization have been developed in recent years，such as stochastic optical reconstruction microscopy (STORM) (Rust et al.，2006), photo-activated localization microscopy(PALM）(Betzig et al.,2OO6) and fluorescence PALM (fPALM) (Hess et al., 2006).These techniques utilize the on-off switching of fluorescent probes to ensure that each active fluorophore is isolated beyond the range of diffraction-limitation and ultimately build a high-resolution image from the precise and accurate positions of many single fluorophores (Deschout et al.，2014). However, single-molecule localization techniques require that the density of fluorophores in each frame remains sufficiently low to prevent individual fluorophores from overlapping，which leads to long imaging times and increases the damage to live samples (Lippincot-Schwartz andManley,20o8).Thus,low temporal resolutions limit the application of super-resolution microscopy techniquesin live-cell imaging.Although several methods have been developed based on simultaneous fittingwith multiple fluorophores to deal with relatively dense fluorescent data (DAOSTORM,2011; Huang et al., 2011; Quan et al., 2011), the localization accuracy of fluorophoresdramatically decreases as the density of emitters increases.

Recently，a localization microscopy analysismethod named the Bayesian analysis of bleaching and blinking (3B)

method was developed to address the high-density fluoro phore data extracted from live cells with standard fluorescent proteins (Cox et al.,2012). In the analysis of 3B, the entire image sequences are modeled as a set of blinking and bleaching fluorophores，and the properties of blinking and bleaching are utilized by hybridizing two hidden Markov model inference methods to improve the obtained accuracy of fluorophore positions.

During the analysis,3B uses the changed information by adding or removing fluorophores in the cell to adjust the model and further fit the data.When addinganew fluorophore,the initial selected position is random,and the positionprior is assumed to be uniform in the optimization iteration of 3B.3B optimizes this random position to determine whether to keep this position as a true single molecule in the model.In fact, the fluorophores are not evenly distributed in the entire image region,and the fluorescence intensity positively correlates with the probability of observing a fluorophore at this position. If a presumed initial positionis far away from the real biological structure，reoptimizing this position is a waste of time and leads to inaccurate results.Thus,assuming that the position prior of fluorophores is uniform in 3B is not appropriate.

In this article，we propose a Bayesian analysis of Bleaching and Blinking microscopy method based on the fluorescence intensity distribution (FID3B） to improve the reconstruction results and accelerate computation. The key techniques include two aspects:an intensity distribution calculation to obtain the probability distribution of fluorophores and a modified model to add a procedure that selects the initial positions of fluorophores based on the intensitydistribution．In 3B，each fluorophore transitions between the emittingstate， non-emitting state andbleached state according toa Markov process,and each transition is associated witha transition probability.The transition probabilities, togetherwiththe fluorophore's previous state,are used to determine thestate ofafluorophoreata certain time.The fluorescence intensity represents the probability of observing a fluorophore at this position.We calculated the intensity distribution of fluorophores at each pixel by combining transition probabilities and fluorescence intensity. Instead of choosing randomly，we then selected a position with more confidence for each newly added fluorophore according to previous knowledge.As a consequence，the results of our method are much more consistent with the real structure,and the computational time can be significantly reduced.Both simulated data and real cellular structures were tested to validate the performance of ourmethod.The results provide convincing evidence of the effectiveness of our method.

# RESULTS

# Experimental validation using simulated dataset

Wepresent twodifferentsimulateddatasetstodemonstrate the performance of FID3B (Figs.1 and 2).One is a grid structure composed of 6 intersecting lines with evenly distributed brightness,named the grid dataset (Fig. 1A); the other is also a grid structure composed of 6 intersecting lines，but with gradually decaying brightness from left to right,named the gradient grid dataset (Fig.2A). Both datasets consist of2oo image frames,and the size of each frame is $4 0 \times 4 0$ pixels ( $1 \ \mathsf { p i x e l } = 1 0 0 \ \mathsf { n m } ,$ .Here,the fullwidthat half maximum (FWHM) of the optical point spread function (PSF) was set to $2 4 0 ~ \mathsf { n m }$ ：

Figure1depicts the reconstruction results of 3B and FID3B withthe grid dataset.Accordingto the characteristics of the state transition of fluorophore in 3B,we generated the grid dataset of 20o frames from the original image (Fig.1A).The fluorescence density of each frame was very high,and the fluorescent molecules were overlapped.The superimposed fluorescence data from 200 frames are shown in Fig.1B.Both 3B and FlD3B were run with a fixed number of iterations,320, and the reconstruction results are shown in Fig.1C and 1D. The brightness of the image that resulted from 3B is relatively low,and the lines in the grid are discontinuous in many areas. In contrast, the reconstruction result of FlD3B retains more details and thus is much more similar to the original image.

To validate the ability to process images with unevenly distributed brightness，the reconstruction results of 3B and FID3B with the gradient grid dataset are shown in Fig.2.As for the previous grid dataset, the gradient grid dataset of 200 frames was generated from the original image (Fig.2A).The brightness of the original image gradually decays from left to right.The superimposed fluorescence data from 2oo frames are shown in Fig.2B.Both 3B and FID3B were run with a fixed number of iterations,240,and the reconstruction resultsare shown in Fig.2C and 2D.In contrast to the reconstruction resultof 3B, thereconstruction resultofFlD3Brevealsmore details.Moreover, the reconstruction result of FlD3B exhibits the same brightness gradientas the original image and thus is much more similar to the real image.

To validate the capability of FID3B in resolving fine structures,we generated simulated images with concentric rings structures,where the distance between two neighboring rings is $2 0 0 \mathsf { n m }$ (Fig. S1).Although it is difficult to see the concentric rings structures from the superimposed fluorescencedata, the reconstruction results ofboth3BandFID3B are consistent with the original image.Moreover， the reconstruction result of FID3B has better continuity.

# Quantitative analysis of image reconstruction quality

Inprevious studies,quantitative measurements have been used to evaluate the performance and quality of localization microscopy algorithms (Ram et al.， 2006;Small, 2009;Huanget al.,2011;Wolter et al., 2011).These measurements assess the detection and localization accuracy of single ormulti emitters ineach frame.Because 3Banalyzes the entire image sequences to obtain a probability map of the positions of fluorophores，which does not reflect the real localization of fluorophores (Lidke，2012)，we sought to 耕 拼 255 0 Max 0

measure the quality of the overall reconstructed image instead of the location of single or multi emitters.The similaritybetween the original image and reconstructed image is a good indicator of the reconstruction quality. In this work, the structural similarity (SSiM) (Wang et al.,2004),which is widely used in the digital image process field,was used to measure the similarity.

SSIM assesses the visual impact of three aspects of an image:luminance,contrastand structure,which are also the main concern of 3B andFID3B.A large SSIMvalue represents high similarity.The measurement between the original image $x$ and reconstructed image $y$ is defined as follows:

$$
\mathsf { S S I M } ( x , y ) = \frac { ( 2 \mu _ { x } \mu _ { y } + C _ { 1 } ) ( 2 \sigma _ { x y } + C _ { 2 } ) } { ( \mu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } + C _ { 1 } ) ( \sigma _ { x } ^ { 2 } + \sigma _ { y } ^ { 2 } + C _ { 2 } ) }
$$

where $\mu _ { x }$ and $\mu _ { y }$ are the mean values of $x$ and y, $\sigma _ { x } ^ { 2 }$ and $\sigma _ { y } ^ { 2 }$ are the variances of $x$ and y, $\sigma _ { x y }$ is the covariance of $x$ and y, and $C _ { 1 }$ and $C _ { 2 }$ are two variables to stabilizeadivision with a weak denominator.

Figure 3 illustrates the quantitative comparison between 3B and FID3B with the grid dataset and the gradient grid dataset.The experimental output data of both 3B and FID3B were recorded at an interval of 40 iterations.For every intermediate output, their similarity with the original image was measuredby SSlM.The similarity curve shown in Fig.3 indicates thatFID3B is superiorto 3B.The grid dataset and gradient grid dataset mentioned above were used to evaluate thereconstructed image.For the grid dataset (Fig.3A),3B no longer improved the reconstructed image qualityafter 200 iterations,but FID3B continued to improve the reconstructed image qualityafter 2oo iterations.When convergencewas reached，the similarity value of 3B was 0.679,which was 0.728 of FID3B. For the gradient grid dataset (Fig.3B), the image quality of 3B essentially stopped improvingafter 320 iterations.When convergence was reached， the similarity value of 3B was 0.683,and the similarity value of FID3Bwas 0.757.The similarity value of FID3B is clearly higher than that of 3B for the same number of iterations.

Inorder to demonstrate the acceleration effect of our method，experiments of both 3B and FID3B with the grid dataset mentioned above were carried out on a platform with an Intel E7500 (2.93 GHz) CPU.We used SSIM to measure 井 B 拼 255 0 Max 0

![](images/70df1c0e2618258caf4b7501cd67e08167ee882e220862bb375dca60c34fef1b.jpg)  
Figure 2.Comparisonofthereconstructionresultsof3BandFID3Bforthe gradient griddataset.(A)Theoriginalimageofthe gradientgriddata (Brightnessgraduallydecaysfromlefttoright).(B)Superimposedfluorescencedatafrom2Ooframesrepresenting thedifraction-limitedimage.(C)Reconstructionresultof3B(240iterations).(D)ReconstructionresultofFD3B(240iterations). (Scale bar: $2 0 0 \mathsf { n m }$ ).Notethatthe resultofFID3B exhibits the same brightness gradientasthe originalimageand thusis much more similar to the real image.   
Figure3.Quantitativecomparisonofthereconstructionresultsofthegridandgradientgriddatasetswith 3BandFID3E (A)Measuring imagequalityof thegriddataset with SSIM.(B)Measuring imagequalityofthe gradient griddataset with SSIM.

![](images/371d8dd20ed3ca3f92abf94ca13d2221134b7add9b5affdd3a8f0d259a7fd21c.jpg)  
Figure 4.Comparisonof thereconstructionresultsof thetwo methods basedonreal experimentaldata.(A)Superimposed fluorescencedatafrom20framesdatashowingdifraction-limitedresolution.(B)Reconstructionresultof3B(160iterations). (C)ReconstructionresultofFID3B(160terations).(D)MagnificationofsolidboxinBandC,showingthedistibutionofluorescence intensityalong thesolidline.Theblackcyclesshowsomepointsofwhichthedensityisnearlydownto0.Thescalebarsare $2 0 0 \mathsf { n m }$ (A-C)and $1 0 0 \mathsf { n m }$ (D). Note that the image continuity obtained with FID3Bis betterand much more consistent with thereal structure.

the similarity between the original and reconstructed images and recorded the computational time of 3B and FID3B.We ran both 3B and FID3B in parallel for2 days.3B required nearly $3 8 . 5 \ h$ to converge to its best similarity value (0.679),while FID3B required only $2 5 . 2 \ h$ to achieve the same similarity valueand continued to improve the result toa large extent.

# Evaluating the performance by experimental data of cellular structure

To evaluate the performance of our method in biological samples,COS7 cells expressingmEos3.2-labeled Lifeact,an actin binding peptide,were illuminated at $4 8 8 \mathsf { n m }$ and imaged with the total internal reflection fluorescence microscope (Fig.4). The experimental data consisted of 200 image frames,and the size of each framewas $3 8 \times 5 0$ pixels(1pixel $\mathbf { \sigma } = \mathbf { \sigma }$ $1 0 0 \ \mathsf { n m } ,$ .The superimposed fluorescence data from 200 frames show the diffraction-limited image (Fig. 4A).Two methods,3B and FID3B,were used to process the experimental data and reconstruct the final super-resolution images (Fig.4B and 4C).Both methods were run with 160 iterations. The reconstruction result of 3B shows many inconsecutive point structures,while the reconstruction result of FID3B shows improved image continuity and is much more consistent with the real structure.Furthermore，some missing structures marked by solid box in Fig.4B are clearly visualized inFig.4C. The magnification of the solid boxesis shown in Fig.4D.We calculated the distribution of fluorescence intensity along the solid line.In this distribution of fluorescence intensity, FlD3B is denser than 3B at all points of the curve.At some points,the densityof 3B is almost0 (as shown by the black cycles in Fig.4D).These points correspond to inconsecutive structures in the magnified area.

# DISCUSSION

We propose a Bayesian analysis of Bleaching and Blinking microscopy method based on fluorescence intensity distribution (FID3B). Our method introduces statistical analysis to estimate the distribution probabilityof fluorescently labeled biological structures in images,and these data are utilized to further guide the selection of the initial positions of fluorophores.We validated our method with both simulated fluorescencedataandexperimentaldatafromcellular structures.These experiments show that our method better addresses both images with even and uneven brightness. Compared with 3B，our method selects a better starting position when adding a new fluorophore and involves more positions in computation at the same number of iterations. As a result, the reconstruction results can be improved,and the computational time can be significantly reduced.

![](images/3c100c43e27904d8696c1a3d501577c4e95ff3fa76db600e623feac47c65e7e1.jpg)

We explain how our method affects the reconstruction results based on two aspects:the selection of the initial positions of fluorophores and the number of retained and discarded positions of fluorophores.

# Comparison of the distribution of initial positions of fluorophores

To illustrate the selection of the initial positions of fluorophores，we compared the distribution of these generated positions using 3B and FID3B.Both 3B and FID3B experiments were carried out with the grid dataset and gradient grid dataset mentionedabove for the same 320 iterations.We recorded the initial positions selected byeach method and calculated the distance from each initial position to the nearest real molecule in the structure in each dataset.For the grid dataset (Fig. 5A-D)，the number of initial positions of fluorophores was 407 for 3B and 562 for FID3B.Comparing the geometry distributions of initial positions in Fig.5A and 5B to the corresponding original images mentioned above indicated that the positions of the selected initial fluorophores of FID3B are much closer to the real structures.The histograms of the distances from initial positions to the nearest structure provide solid support for our findings (Fig. 5C and 5D).The number of selected initial positionswith distances less than 1 is 100 in 3B，which consisted of only $2 4 . 6 \%$ of total initial positions.In contrast, 367 initial positions with distances less than 1 are observed in FID3B,comprising up to $6 5 . 3 \%$ of total initial positions.For the gradient grid dataset (Fig.5E-H), the initial positions of FlD3B are also much closer to the structure of the original image (Fig.5E and 5F). The results from 3B and FID3B include 427 and 518 initial positions,respectively. The histograms of distances are shown in Fig. 5G and 5H. The number of selected positions with distances less than 1 inFID3Bis331( $6 3 . 9 \%$ in total),while in 3B this number is 90 $( 2 1 . 1 \% )$ .The above comparison confirms the advantage of FID3B in selecting initial positions.

# Comparison of the number of retained and discarded positions of fluorophores

3B uses the change in information caused by adding or removing fluorophores in the cellto fit the data.When adding a newfluorophore,3Bselectsan initial position,optimizes this position,and then determines whether it isa reliable position ofafluorophore.If the position is reliable, itwill be retained and referred to as aretained position;otherwise,it will be discarded and referred toas a discarded position.We ran both 3B and FlD3B with the two datasets mentioned above for the same 320 iterations and recorded the numbers of retained and discarded positions (Fig.6). For the grid dataset (Fig.6A),3B yielded 36,756 discarded positions and 36,311 retained positions,resulting ina total of73,067 positionswitha discard rate of $5 0 . 3 \%$ . In contrast，FID3B yielded 28,036 discarded positions and 61,248 retained positions,resulting in 89,284 positions in total with a much lower discard rate of $3 1 . 4 \%$ .For the gradient grid dataset (Fig.6B)，3B yielded 40,792 discarded positionsand 31,938 retained positions,resulting in a total of72,730 positionswitha discard rate of $56 . 1 \%$ .In contrast,FlD3Byielded28,736discarded positionsand53,872 retained positions,resulting in 82,6o8 positions in total with a much lower discard rate of $3 4 . 8 \%$ .Fig.6 shows thatFID3B clearly involves more positions in computation for the same number of iterations,asaresult, the reconstruction result of FID3B is much closer to the real structure than that of 3B.

![](images/8db324cd242b2eb07bc84b24105d6a16d2706c0ea55eab13de726b447f423234.jpg)  
Figure5.Comparisonofthedistributionof initial positions for the grid dataset (A-D) and the gradient grid dataset (E-H). (A) Distribution of initial positions using 3B. (B) Distribution of initial positions using FID3B.(C) Distances from initial positions to image contour in 3B.(D) Distances from initial positions to image contour in FID3B.(E-H) are interpreted as the same as (A-D).   
Figure 6.Comparisonof the number of retained and discarded positions fortwo datasets. (A)Grid dataset (B)Gradient gric dataset.

# MATERIALSANDMETHODS

# Plasmids construction

Toexpress Lifeact-mEos3.2in mammalian cells,mEos3.2 containing BamHland Notl sites was firstPCR-amplified and inserted into the pmEos3.2-N1 (Clonetech) plasmid to replace EGFP.The Lifeact sequence was then cloned into pmEos3.2-N1 with EcoRl and BamHl.The synthetic DNA primers used for cloning were purchased fromInvitrogen.All plasmids were sequenced(The Beijing Genomics Institute) before furtheranalysis.

# Cellculture,transfectionandfixation

COS-7 cells were cultured in DMEM complete medium (Gibco) supplemented with $10 \%$ fetal bovine serum and maintained at $3 7 ^ { \circ } \mathsf { C }$ in a humidified incubator(Thermo).Theywere then transiently transfected using LipofectamineTM 20oo (Invitrogen） in accordance with the manufacturer's protocol when they reached $8 0 \%$ confluence.Before fixation,the cells were grown in DMEM complete medium (Gibco) for $2 4 \mathsf { h }$ The cells were then sub-cultured on coverslips (Fisher Scientific) foranother $2 4 \mathsf { h }$ and fixed with $3 \%$ (w/v) paraformaldehydeand $0 . 5 \%$ glutaraldehyde inPBS for15 minat $3 7 ^ { \circ } \mathsf { C }$ ,washed 3 times with filtered PBS and stored in PBS until imaging.

# Optical setup and imaging

The 3B imaging of Lifeact-mEos3.2 was performed as previously described (Cox et al.,2012).We used an Olympus IX71 inverted microscope equipped with a $1 0 0 \times 1 . 4 5$ numerical aperture (NA) oil objective (Olympus PLANAPO).An internal $1 . 6 \times$ magnification was used to yielda pixel size of $1 0 0 ~ \mathsf { n m }$ .Anacousto-optic tunable filter (AA Optoelectronic) was used to control the 488-nm laser (Sapphire).The fluorescence signals were acquired using an electronmultiplying charge-coupled device (EMCCD) camera (Andor iXon DU-897 BV).For 3B imaging，Lifeact-mEos3.2 constructs were imaged by a $4 8 8 \mathrm { - } \mathsf { n m }$ laser with $5 0 ~ \mathsf { m s }$ integration times.The 3B datasets consisted of 2oo frames and were corrected fordrift.

# Simulateddataset generation

We generated two diferent simulated datasets with overlapping fluorophores ineach frame.One was the griddataset,whose brightness was uniform in the grid region; the other was the gradient grid dataset,whose brightness gradually decayed from left to right. Both datasets consisted of 2oo image frames,and the size of each frame was $4 0 \times 4 0$ pixels( $1 \ \mathsf { p i x e l } = 1 0 0 \ \mathsf { n m } ,$ .Inall of our simulations,the optical point spread function (PSF）was represented asa 2D Gaussian shape with a width parameter of $1 0 0 ~ \mathsf { n m }$ .In 3B, the entire datasetwas generated from large numbers of fluorophores that had blinking and bleaching properties.All of these fluorophores were modeledaftera Factorial Hidden MarkovModel (FHMM) (Ghahramaniand Jordan,1997),each of whichwas modeledaftera Hidden Markov Model (HMM) (MacKay,2003)and had three possible states: emitting (light),not emittingand bleached.The fluorophore can transition between the emitting and not emitting state as well as from the not emiting to the bleach state.Once it has transferred to the bleach state,the fluorophore can no longer transfer to the other states.We assumed that the states of all fluorophores were statistically independent.These characteristics of state transition proposed in 3B were usedto generate simulated datasets.In the first frame of the simulation, half of the fluorophores were in the emiting state and half were in the not emiting state.Subsequently,we created an image for each frame that consisted of fluorophores whose states were randomly decidedbya state transition diagram.The stack of image frames was degraded by both shot (Poisson) noise and read out (Gaussian) noise.

# Bayesian analysis of bleaching and blinking (3B) method

3Butilizesa Bayesian model to generate fluorescence imageswith aspatial resolution approaching 5O nanometers.It can handle the high-density fluorophore image data extracted from live cells with standard fluorescent proteins.In this Bayesian technique,3B models the entire image sequences as a set of blinking and bleaching fluorophores and generates a probability map of positions using a maximuma posteriori (MAP) calculation.

The complete procedures for 3B are summarized as follows:

Step1. Select the initial spot positions fora model. Step2. Optimize the entire model: re-optimizing each fluorophore in turn to obtain a new position in the model. Step3.Model selection: incrementally adjusting the model to fit the data，one fluorophore at a time.3B either adds a new fluorophore at a random position or selects a fluorophore in the model for removal.

Repeating Step2and Step3 generatesasuper-resolution fluorescence image.The algorithm is terminated when the adjacent reconstructed images no longer significantly differ.

The basic operation of Step 3 is adjusting the model to fit the data.In this model selectionstep,3B makes many local decisions to incrementallyadjust the model.It onlyallows one fluorophore to be eitheradded or removedata time:eitheranew fluorophore isadded at arandom position ora fluorophore in the model is selected for removal.3B optimizes this spot to search fora new position and then decides whetherto keep it in the model.After a series of such decisions have been made,3B re-optimizes the entire model (Step 2)and then repeats the model selection step (Step 3).

During the analysis,3B selectsa random position asan initial position of the fluorophore when adding a new fluorophore.3B considers that the position prior is uniform in all image areas.Intuitively，the distribution of fluorophores is uneven,and the fluorescence intensity at a given position positively correlates with the probabilityof observinga fluorophore at this position.If the presumed initial position of the fluorophore is far away from the real biological structure,finding the correct position of the fluorophore is difficult.Thus,re-optimizing this position is a waste of time and leads to inaccurate results.

# 3B method based on fluorescence intensity distribution (FID3B)

To improve the reconstruction results and accelerate the calculation, we propose a Bayesian analysis of Bleaching and Blinking microscopy method based on fluorescence intensity distribution (FID3B). In 3B,each fluorophore transfers among an emitting state,non-emitting state and bleached state according to a Markov process,and each transferis associated witha transition probability.The transition probabilities,togetherwith the fluorophore's previous state,are used to determine the stateofa fluorophoreatacertain time.The fluorescence intensity represents the probability of observinga fluorophore at this position.By combining transition probabilities and fluorescence intensity，we calculated the intensity distribution of fluorophores at each pixel. Instead of choosing randomly，we then selected a position with more confidence for each newly added fluorophore.

The key techniques include two aspects:an intensity distribution calculation to obtain the probabilitydistributionof fluorophoresand a modified model selection to adda procedure that selects the initial positions of fluorophores based on the intensity distribution.

# Intensitydistribution calculation

According to the state transition diagram of the fluorophore in 3B, each fluorophore has three possible states，emiting (light)，not emittingand bleached,and transfersamong the three states.The transitionprobabilities,i.e.,theprobabilityofafluorophore transferring from emitting toemitting or fromnot emitting to emitting,are $\pmb { a }$ and $\beta$ ，respectively，as shown in Fig.7.We assumed that each fluorophore's transitions are statistically independent of other fluorophore's states.This state transition characteristic was used to calculate the probability of the fluorophore at each pixel in the images.We then used these probabilities as an intensity distribution to guide the selection of the initial positions of fluorophores.

Figure 7 shows that two situations cause a fluorophore to emit light:transferring from emitting to emitting and transferring fromnot emitting to emitting.For convenience，we only considered two states:emitting and not emitting.Like deconSTORM (Mukamel et al.，2012)，we assigned an exponential prior distribution to parameter, $\gamma _ { k } ( \boldsymbol { x } )$ ,which represents the estimated intensityat location $x$ in frame $k$ $\gamma _ { k } ( \boldsymbol { x } )$ isbased onaweighted average of the fluorescence intensity at location $x$ in all $\boldsymbol { \kappa }$ frames.The weight increases as the distance to the current frame $k$ decreases.

![](images/3da6f4dabd69fb17748f0f81603c10752de44ccc37f0a813f8e62a5a9953593e.jpg)  
Figure 7. State transition diagram of fluorophore.

$$
\gamma _ { k } ( x ) = \sum _ { t = 1 } ^ { K } \left( \frac { \alpha ^ { | k - t | } } { \tau } + \frac { \beta } { K } \right) i _ { t } ( x )
$$

where $\begin{array} { r } { T = \sum _ { t = 1 } ^ { K } \alpha ^ { | k - t | } } \end{array}$ is the normalization factor. $\boldsymbol { \kappa }$ is the total number of image frames. ${ i _ { k } ( x ) }$ represents the fluorescence intensity at location $x$ in frame $k$ The first term in Eq.2 indicates that the observation of image intensity at a particular location in one image frame is generated byaseries of image frames.This process calculatesaweighted average based onall of image frames,and the current frame is assigned the maximum weight.The weight decreasesas thedistance from the current frame increases,which decays exponentially.The second term in Eq.2 indicates that an emittingstate detected inany image frame is due toa transition from not emittng to emitting in any earlier or later image frame with probabilityβ.We considered the average impact of re-emitting, βi(xadcbedefistdcodtetainth estimated intensity, $\gamma _ { k } ( \boldsymbol { x } )$ ，at each location in each image frame.

The total intensity at a certain location $x$ $\gamma ( \boldsymbol { x } )$ ,is then obtained by adding the estimated intensity, $\gamma _ { k } ( \boldsymbol { x } )$ ，inall $\boldsymbol { \kappa }$ frames as shown in equation 3.

$$
\gamma ( \boldsymbol { x } ) = \sum _ { k = 1 } ^ { K } \gamma _ { k } ( \boldsymbol { x } )
$$

Finally, $\boldsymbol { \gamma } ( \boldsymbol { x } )$ is normalized to obtain probability map of the image at a certain location $x$ $P ( x )$ (Eq.4).We utilized this probability map as the intensity distribution of fluorophores to evaluate the selection of initial positions.The intensity distribution interval ranges from O to 1.A large value represents a high probability of the selected positions of fluorophores.

$$
P ( x ) = \frac { \gamma ( x ) } { \mathsf { m a x } _ { x } \gamma ( x ) }
$$

# Modifiedmodelselection

The model selection in 3B(Step 3 in subsection “Bayesian analysis of bleaching and blinking (3B) method") is modified to improve the initial positions of fluorophores.When adding a new fluorophore,we used theintensitydistributionto selectamorereliable initial position.The modified procedures are summarized as follows:

Step1. Select the initial spot positions fora model. Step2. Optimize the entire model: re-optimizing each fluorophore in turn to obtain a new position in the model. Step3.Model selection: incrementally adjusting the model to fit the data,one fluorophore at a time.The operation details are shown below:

a）Adding a new fluorophore at a random position $( O p _ { - } a )$   
b）Adding a new fluorophore based on intensity distribution $( O p \_ b )$ ：   
c）Randomly selecting a fluorophore in the model for removal $( O p _ { - } c )$ ：

When model selection (Step 3) is executed to adjust the model to fit thedata，we take one fluorophore under consideration from three operations:addinga new fluorophore at a random position $( O p \_ a )$ addinganew fluorophore based on intensity distribution $( O p \_ b )$ and randomlyselecting a fluorophore in the model for removal $( O p \_ c )$ These three operationsare randomlyselectedwithacertain probability. If the probability of Op_a is high,FlD3B tends to selectmore random positions asnew fluorophores.In contrast, if the probability of $O p \_ b$ is high,FID3B tends to select more fluorophores based on intensity distribution.In particular, if the probability of $O p \_ b$ is set to 0,FID3B is converted to the 3B.In our experiment, the probabilities of the three operations, $O p _ { - } a$ $\mathsf { O } p \_ b$ and $\begin{array} { r } { O p \_ c , } \end{array}$ were set to 0.2,0.5 and 0.3,respectively.

# ACKNOWLEDGEMENTS

This project was supported by the National Natural Science Foundation of China(Grants No．61232001，61202210，61472397, 31170818 and 31370851), the National Basic Research Program (973 Program)(Nos.2010CB912303 and 2013CB910103) and a Project of the Chinese Academy of Sciences (XDB08030202).

# ABBREVIATIONS

3B，Bayesian analysis of theblinking andbleaching; FID3B, Bayesian analysis of Bleachingand Blinking microscopy method based on fluorescence intensity distribution；PSF，point spread function;FWHM，full width athalfmaximum； CPU，central processing unit;SSIM,structural similarity;HMM，Hidden Markov Model; FHMM,Factorial Hidden Markov Model;MAP,maximum a posteriori.

# COMPLIANCEWITHETHICSGUIDELINES

Fan Xu,Mingshu Zhang,Zhiyong Liu,Pingyong Xu and Fa Zhang declare that they have no conflict of interest.This article does not contain any studies with human or animal subjects performed by the any of the authors.

# OPENACCESS

This article is distributed under the terms of the Creative Commons Attribution License which permits any use， distribution，and reproduction in any medium，provided the original author(s)and the source are credited.

# REFERENCES

Betzig E,Patterson GH,Sougrat R,Lindwasser OW,Olenych S, Bonifacino JS，Davidson MW,Lippincott-Schwartz J,Hess HF

(2006）Imaging intracellular fluorescent proteins at nanometer resolution. Science 313:1642-1645   
Cox S,Rosten E,Monypenny J,Jovanovic-Talisman T, Burnette DT, Lippincot-Schwartz J, Jones GE,Heintzmann R (2012) Bayesian localization microscopy reveals nanoscale podosome dynamics. Nat Methods 9:195-200   
Daostorm SS (2011） DAOSTORM:an algorithm for high-density super-resolution microscopy. Nat methods 8:279   
Deschout H，Cella Zanacchi F，Mlodzianoski M，Diaspro A, Bewersdorf J，Hess ST，Braeckmans K(2014) Precisely and accurately localizing single emiters in fluorescence microscopy. Nat Methods 11:253-266   
Ghahramani Z,Jordan Ml (1997) Factorial hidden Markov models. Mach Learn 29:245-273   
Hell SW (2007) Far-field optical nanoscopy. Science 316:1153-1158   
Hess ST，Girirajan TP，Mason MD (2O06) UItra-high resolution imaging by fluorescence photoactivation localization microscopy. Biophys J91:4258-4272   
Huang F, Schwartz SL，Byars JM,Lidke KA (2011) Simultaneous multiple-emitter fiting for single molecule super-resolution imaging.Biomed Opt Express 2:1377-1393   
Lidke KA (2012) Super resolution for common probes and common microscopes.Nat Methods 9(139):141   
Lippincott-Schwartz J，Manley S (20o8）Putting super-resolution fluorescence microscopy to work. Nat Methods 6:21-23   
MacKay DJ (20o3) Information theory,inference,and learning algorithms,vol 7(Citeseer). Cambridge university press, Cambridge   
Mukamel EA, Babcock H, Zhuang X (2012) Statistical deconvolution for superresolution fluorescence microscopy. Biophys J 102: 2391-2400   
Quan T, Zhu H,Liu X, Liu Y, Ding J, Zeng S, Huang Z-L (2011) Highdensity localization of active molecules using structured sparse model and Bayesian information criterion.Opt Express 19: 16963-16974   
Ram S,Ward ES,Ober RJ (2006) Beyond Rayleigh's criterion:a resolution measure with application to single-molecule microscopy.Proc Natl Acad Sci USA 103:4457-4462   
Rust MJ, Bates M, Zhuang X (2006) Sub-diffraction-limit imaging by stochastic optical reconstruction microscopy (STORM). Nat Methods 3:793-795   
Small AR (2oo9) Theoretical limits on errors and acquisition rates in localizing switchable fluorophores.Biophys J 96:L16-L18   
Wang Z, Bovik AC,Sheikh HR, Simoncelli EP (2004) Image quality assessment: from error visibility to structural similarity.IEEE Trans Image Process 13:600-612   
Wolter S,Endesfelder U,van de Linde S,Heilemann M,Sauer M (2011） Measuringlocalizationperformanceofsuperresolution algorithms on very active samples.Opt Express 19: 7020-7033