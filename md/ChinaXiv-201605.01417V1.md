# Improved adaptive reconstruction of multichannel MR images

Ya-Jun Ma, Wentao Liu, Xuna Zhao,and Weinan Tang   
Beijing CityKeyLab forMedicalPhysicsand Engineering,InstituteofHeavyIonPhysics,SchoolofPhysics,   
Peking University, Beijing 1O0871,China and Center for MRI Research,Academy for Advanced   
Interdisciplinary Studies,PekingUniversity,BeijinglOo871,China Zihao Zhang   
State Key Laboratory of Brainand Cognitive Science,Beijing MRI Center for Brain Research,Institute ofBiophysics,Chinese Academy ofSciences,BeijinglOolol,Chinaand Graduate University,Chinese Academy of Sciences,Beijing,China   
Xin Tang, Yang Fan, and Huanjie Li   
Beijing CityKeyLab forMedicalPhysicsand Engineering,InstituteofHeavy IonPhysics,SchoolofPhysics,   
Peking University, Beijing 1Oo871,China and Center for MRI Research,Academy for Advanced   
InterdisciplinaryStudies,PekingUniversity,Beijing1Oo87l,China   
Jia-Hong Gaoa)   
Beijing City Key Lab for Medical Physicsand Engineering,Institute of Heavy Ion Physics,Schoolof Physics,   
Peking University,Beijing 1Oo871,China; Center for MRlResearch,Academy forAdvanced Interdisciplinary   
Studies,Peking UniversityBeijing O0871,China;andMcGovern Institute for BrainResearch,Peking   
University,Beijing100871,China

(Received 1 August 2014; revised 16 November 2014; accepted for publication 14 December 2014; published 12 January 2015)

Purpose: To improve adaptive reconstruction of multichannel MR images by simultaneously removing nonsmooth phase and signal-loss imaging artifacts.

Methods: The improved adaptive reconstruction consists of three steps: (1) modified multichannel images are first derived by dividing raw multichannel images by a reference image (i.e.,a normalized single-channel image); (2) the modified multichannel images are smoothed by a low-pass filter; (3)adaptive spatial matched filters determined from the smoothed multichannel images are utilized to obtain multichannel combined images.Numerical simulations,as well as MRI experiments,on phantoms and human subjects are performed to evaluate and compare the effectiveness of this improved adaptive reconstruction approach against traditional coil combination methods.

Results: Both simulation and MRI experimental results demonstrated that the proposed improved adaptive reconstruction method is able to obtain combined images with reduced nonsmooth phase and signal-loss imaging artifacts.

Conclusions:A novel multichannel image reconstruction method is developed that produces high quality multichannel combined images. $\circledcirc$ 2015American Association of Physicists in Medicine. [http://dx.doi.org/10.1118/1.4905163]

Key words: adaptive reconstruction, nonsmooth, signal-loss, MRI

# 1.INTRODUCTION

Multichannel receiver coils have been widely used for MRI since 199Os.1 Due to the inhomogeneous coil sensitivity map of surface coils,the object signal intensity rapidly decreases with increased distance from the coil location. Thus,a proper multichannel image reconstruction method is needed to generate a combined image with a uniform intensity.

For multichannel magnitude image reconstruction, the commonly practiced method is the sum-of-squares (SOS) approach.1 However, the SOS method is known to reduce imaging signal-to-noise ratio (SNR) and introduce signal bias: signal appears larger than it should be,especially in regions with low SNR.² To address these problems, various coil sensitivity based methods for multichannel image combination have been developed, such as electromagnetic field calculation methods,’ reference scan methods,4.5 and multichannel images based methods.6.7 On the other hand, for multichannel phase image reconstruction,both the weighted mean (WM) methods8-1l and the coil sensitivity based methods4,6.7 are commonly used. The SNR of the phase images produced by the coil sensitivity based methods are higher than that of the WM methods,especially when the SNR is low.9 This work focuses on improving one of the coil sensitivity based methods,the adaptive reconstruction（AR) method proposed by Walsh et al., for both the multichannel magnitude and phase image reconstruction.AR is the default multichannel image combination method used in Siemens scanners.

The AR method uses a statistical description of the expected signal and noise covariances to derive estimates of the optimal spatial matched filters (SMF,i.e.,coil sensitivity weights). The SNR of both combined magnitude and phase images produced by AR method is improved compared to conventional SOS and WM methods, respectively. However, SMF of AR tend to result in inconsistencies and sometimes failure in phase determination (nonsmooth phase artifacts), particularly at points where the phases between the channels vary substantially to cause signal cancelation.12 In practice, nonsmooth phase artifacts often occur in the combined image when multichannel images are in regions with low SNR.

Walsh et al.7 mentioned that SMF computed from low-pass filtered multichannel images may eliminate/reduce their noise correlation with raw multichannel images.This modified AR (MAR) method could further reduce background noise in the combined magnitude image and increase the SNR of the combined phase image.Besides, the nonsmooth phase artifacts in the combined image could be significantly reduced because of the increased phase consistencies of the low resolution SMF with improved SNR.However,in practice,low-pass filtered multichannel images may lose regional coil sensitivity information when the underlying regional MR signals suffer rapid phase variation due to the strong susceptibility inhomogeneity, such as in the air-tissue interfaces.7,13,14 Then, the combined imageusing SMFdeterminedfromthe filtered multichannel images will suffer signal-loss artifacts both in magnitude and phase images.

In terms of physical nature,the phase map of each multichannel image represents mixtures of RF offset phase and inhomogeneous susceptibility components.15 Except the RF offset phases induced by the different receive coils,the other phase components including static field inhomogeneity(due to imperfect shimming) and time varying inhomogeneity(due to eddy currents and object motion) are exactly the same in all the multichannel images.In this note,we develop a robust modified adaptive reconstruction(ROMAR) method to eliminate the signal-loss artifacts in the MAR combined image due to the existence of large inhomogeneous susceptibility components in the raw multichannel phase images.The key steps of ROMAR are as follows:(1) the large inhomogeneous susceptibility components in the raw multichannel phase images are removed by dividing raw multichannel images by a reference image (i.e.,a normalized single-channel image); (2) the obtained new multichannel images without rapid phase variation patterns are smoothed by a low-pass filter,and the filtered multichannel images contain sufficient coil sensitivity information for adaptive constructing the SMF,which have a low noise correlation with raw multichannel images;(3) both the magnitude and phase components of the combined image using the above SMF are SNR-optimal and free of both nonsmooth phase and signal-loss imaging artifacts.

# 2. THEORY

Complex channel image $C _ { j } ( \boldsymbol { r } )$ acquired by $j$ -th receive coil can be described as a pixel by pixel product of native MR signal $\rho ( r )$ multiplied by corresponding coil sensitivity $S _ { j } ( \boldsymbol { r } )$ with additive noise $n _ { j } ( r )$

$$
C _ { j } ( r ) = \rho ( r ) S _ { j } ( r ) + n _ { j } ( r ) , \quad j = 1 , 2 , . . . , N ,
$$

where $N$ is the total number of receive channels and $r$ is the pixel location. The combined image is the linear superposition of weighted multichannel images1

$$
I ( \boldsymbol { r } ) = \boldsymbol { W } ( \boldsymbol { r } ) ^ { H } \boldsymbol { C } ( \boldsymbol { r } ) ,
$$

MedicalPhysics,Vol.42,No.2,February2015 where $I ( \boldsymbol { r } )$ 0 $\dot { \boldsymbol { r } }$ is indexing the pixel) is the combined image. $W ( r )$ is a vector of $N$ channel components and vector cell is the coil sensitivity weight $W _ { j } ( r )$ ： $H$ denotes the Hermitian transpose operation. $C ( \boldsymbol r )$ is also a vector of $N$ channel components and vector cell is the channel image $C _ { j } ( \boldsymbol { r } )$ ：

AR method demonstrates that the optimal spatial matched filter is obtained by maximizing imaging SNR,and the SNR formulation is expressed as follows:7

$$
\mathrm { S N R } = \frac { W ^ { H } R _ { s } W } { W ^ { H } R _ { n } W } ,
$$

where $R _ { s }$ and $R _ { n }$ are the second order array correlation matrices of the MR signal and noise,respectively. The matrix cells of $R _ { s }$ and $R _ { n }$ are expressed as follows:7

$$
\begin{array} { r l } & { R _ { s } ( j , k ) = \underset { ( r \in \mathrm { S R O I } ) } { \underline { { E } } } ( C _ { j } ( r ) C _ { k } ( r ) ^ { * } ) , \quad j = 1 , . . . , N , k = 1 , . . . , N , } \\ & { R _ { n } ( j , k ) = \underset { ( r \in \mathrm { S R O I } ) } { \underline { { E } } } ( n _ { j } ( r ) n _ { k } ( r ) ^ { * } ) , \quad j = 1 , . . . , N , k = 1 , . . . , N , } \end{array}
$$

where SROI is a specified setof pixel coordinates and $*$ represents the Hermitian conjugate operator. Operator $E ( \cdot )$ is the signal’s expectation.Then, the optimal spatial matched filter $W ( r )$ can be generated from the eigenvector corresponding to the maximum eigenvalue of the matrix product

$$
\begin{array} { r } { P = { \cal R } _ { n } ^ { - 1 } { \cal R } _ { s } . } \end{array}
$$

The noise correlation matrices $R _ { n }$ can be derived from a prescan noise calibration or can be simply assumed to be an identity matrix.Then,the obtained $W ( r )$ is used pixel by pixel or block by block basis to combine multichannel images.7

Further SNR improvement can be obtained by MAR which utilizes smoothed (i.e.,low-pass filtered) multichannel images to compute SMF.7 Commonly, low-pass filtering is applied in the image domain by windowing the $k$ -space data.15.16 The native MR signal $( \rho ( r ) )$ may have both low and high spatial frequency components $( \rho ( r ) ^ { \mathrm { l o w - f r e q } }$ and $\rho ( r ) ^ { \mathrm { h i g h - f r e q } } )$ and coil sensitivity profile $S ( \boldsymbol r )$ only has a low frequency character. Then, both original and smoothed multichannel images can be expressedas follows:

$$
\begin{array} { r l r } & { } & { C _ { j } ( r ) = \rho ( r ) ^ { \mathrm { l o w - f r e q } } S _ { j } ( r ) + \rho ( r ) ^ { \mathrm { h i g h - f r e q } } S _ { j } ( r ) + n _ { j } ( r ) , } \\ & { } & { j = 1 , . . . , N , } \\ & { } & { \left. C _ { j } ( r ) \right. = \rho ( r ) ^ { \mathrm { l o w - f r e q } } S _ { j } ( r ) + \left. n _ { j } ( r ) \right. , \quad j = 1 , . . . , N , } \end{array}
$$

where $\langle \rangle$ indicates that the image has been smoothedbyalowpass filter and it is not the signal's expectation. If the native MR signal has enough low frequency components $( \rho ( r ) ^ { \mathrm { l o w - f r e q } } )$ （20 in each pixel location,coil sensitivity information is still remained in $\langle C _ { j } ( \boldsymbol { r } ) \rangle$ . The corresponding signal and noise array correlation matrix $R _ { s }$ and $R _ { n }$ can be expressed as

$$
\begin{array} { r l } & { R _ { s } ( j , k ) = \underset { ( r \in \mathrm { S R O I } ) } { E } { ( \langle C _ { j } ( r ) \rangle \langle C _ { k } ( r ) \rangle ^ { * } ) } , } \\ & { \quad j = 1 , . . . , N , k = 1 , . . . , N , } \\ & { R _ { n } ( j , k ) = \underset { ( r \in \mathrm { ( S R O I ) } ) } { E } { ( \langle n _ { j } ( r ) \rangle \langle n _ { k } ( r ) \rangle ^ { * } ) } , } \\ & { \quad j = 1 , . . . , N , k = 1 , . . . , N . } \end{array}
$$

Most noise energy in original multichannel images is removed by the smoothing operation.Thus,the derived SMF

![](images/7625be9a56fa10f1da4ff0488441851d3f8d083144af761239e5b0ac6959631f.jpg)  
FIG.1ecosruciulsfsulticalaagshOaissoefsteotourthsede andpaseesuels filtedso artifacts are shown in the red circles in the above images.

determined from matrix $R _ { s }$ exhibit almost no correlation with the original multichannel images in the nonsignal regions. So the combined image hasafurtherreduced noise floor.

# 2.A.ROMAR of multichannel MR images

The image combined by MAR method always produces an optimized SNR. However, some regional MR signals may exhibit rapid phase variation due to the strong susceptibility inhomogeneity,and these regions almost do not contain the low frequency native MR signal components.Thus, the lowpass fltered coil image will lose coil sensitivity information in these rapid phase variation regions and consequently the combined image will suffer signal-loss artifacts.

Inlightof the problem in MAR,ROMARis introduced to avoid the signal-loss artifacts and simultaneously optimize

SNR of the combined image.ROMAR removes the large inhomogeneous susceptibility components in raw multichannel phase images through dividing multichannel images by a reference image. Then, the new channel image $C _ { i } ^ { R } ( r )$ does not contain rapid phase variation patterns and itis expressed as follows:

$$
C _ { i } ^ { R } ( r ) = C _ { i } ( r ) / \mathrm { n o r m a l i z e } ( C _ { R } ( r ) ) , \quad i = 1 , . . . , N , R \in [ 1 , N ] ,
$$

where the reference image (normalize $( C _ { R } ( r ) ) )$ can be derived bya normalized single-channel image $C _ { R } ( r )$ (i.e.,normalize $( C _ { R } ( r ) ) = \exp ( i \varphi ( C _ { R } ( r ) ) )$ ，where $\varphi ( C _ { R } ( r ) )$ is the phase of $C _ { R } ( r ) )$ . The phase components remained in the new channel image $C _ { i } ^ { R } ( \boldsymbol { r } )$ are only RF offset phase induced by the receive coil,and the RF offset phases are always globally smooth.Then, $C _ { i } ^ { R } ( r )$ is smoothed by a low-pass filter. The coil sensitivity information is well preserved in the filtered image $\langle C _ { i } ^ { R } ( r ) \rangle$ . The correlation matrix $R _ { s }$ is similarly calculated by Eq.(9).In addition,a constant divisor (normalize $( C _ { R } ( \boldsymbol { r } ) ) )$ does not change the physical content of the matrix cells of $R _ { s }$ . Finally, the SMF determined from $R _ { s }$ are used for multichannel image combination.For ROMAR,since the smoothing procedure has been employed to the multichannel images without rapid phase variation, signal-loss artifacts are effectivelyavoided.

![](images/8ecc98f8d4c6edb7906fdfee9e0432841a6bbdce82008bf34debc55b9444febe.jpg)  
FIG.2.Recorcslsuleadsgoindtotssotd paseresultil pasepsl are shown in the red circles in the above images.

# 3.MATERIALSANDMETHODS

To validate the proposed method, both phantom and in vivo experiments were performed. The multichannel images were combined,and the results were compared to those of SOS,AR, and MAR techniques.In addition, the proposed method is also compared with the WM method in phase reconstruction.

# 3.A.MR experiments

A group of ACR phantom and human brain data were acquired on a Siemens 3T scanner using a 12-channel head coil with a 2D gradient echo sequence $( \mathrm { T R } / \mathrm { T E } / \theta = 6 2 0 ~ \mathrm { m s } /$ $2 0 ~ \mathrm { m s } / 3 ^ { \circ }$ ， $\mathrm { F O V } = 2 2 0 \times 2 2 0 ~ \mathrm { m m } ^ { 2 }$ ，matrix $= 2 5 6 \times 2 5 6$ ，slice thickness $= 3 ~ \mathrm { m m }$ ，slice number $= 1 8$ ）toproduce noisy data The low SNR data were used to test AR,MAR,and ROMAR methods.The second head data were acquired with a 3D full flow-compensated SPGR sequence $\mathrm { ( T R / T E / } \theta = 4 0 \ \mathrm { m s } / 3 2$ $\mathrm { m s } / 1 5 ^ { \circ }$ ， $\mathrm { F O V } = 2 3 0 \times 2 3 0 \times 4 0 \mathrm { m m } ^ { 3 }$ ，matrix $= 2 5 6 \times 2 5 6 \times 4 0 \rangle$ ！ The high SNR SPGR data were used to compare MAR and ROMAR methods.Written informed consent was obtained from all subjects prior to the examination.In addition,human brain data in low SNR were also acquired with a 2D dual echo SPGR sequence $\mathrm { ( T R / T E _ { 1 } / T E _ { 2 } / \theta = 4 0 m s / 2 1 . 8 m s / 2 4 . 9 m s / 5 ^ { \circ } }$ $\mathrm { F O V } = 2 4 0 \times 2 4 0 ~ \mathrm { m m } ^ { 2 }$ ，matrix $= 2 5 6 \times 2 5 6$ ，slice thickness ${ \bf \omega } = 2 { \bf m m }$ ，slice number $= 1 8$ ）to compare the proposed method with the WM method in phase difference reconstruction.8.9

TABLE I. The noise level of the top left regions (size: $4 0 \times 4 0$ )in both phantom and head images.   

<html><body><table><tr><td colspan="2"></td><td>SOS</td><td>AR</td><td>MAR</td><td>ROMAR</td></tr><tr><td rowspan="2">Phantom</td><td>Mean values</td><td>0.153</td><td>0.088</td><td>0.075</td><td>0.063</td></tr><tr><td>SD values</td><td>0.041</td><td>0.046</td><td>0.040</td><td>0.032</td></tr><tr><td rowspan="2">Head</td><td>Mean values</td><td>0.165</td><td>0.096</td><td>0.081</td><td>0.076</td></tr><tr><td>SD values</td><td>0.044</td><td>0.050</td><td>0.042</td><td>0.036</td></tr></table></body></html>

![](images/7b0bcf75135567641fdf7e2a2b8da7ecd642c3fb6848f1e91a40e0d28c43b470.jpg)  
FIG.3.ReconstructioesulsfulticaelDGmagsA(frstdtdo)OA(codndfourtho)etodaste fitooutsodaspiso rows are two diffrent slices acquired with same sequence. High-passfiltered phase maps are shown in the range of $[ - 1 , 1 ]$ (the unit is radian). Imaging artifacts are shown in the red circles in the above images.

# 3.B. Data processing

All methods were implemented in MATLAB 2O13a (64-bit; Mathworks,Natick,MA).In the data processing of both phantom and in vivo data, SMF of AR was applied by a pixelwise combination with a size of $1 6 \times 1 6$ SROI correlation matrices. The smoothing procedure of MAR and ROMAR was carried out by $k$ -space truncation followed by applying a Hanning window and zero-filling.Truncation factor(TF) was defined by dividing original encoding steps by the remained encoding steps after truncation.All the data dimensions had the same TF. TFs of both MAR and ROMAR methods were typically 8.15,17 An $8 \times 8$ SROI correlation matrix was employed for SMFcalculationofbothMARandROMAR.

For ROMAR,any given single-channel image (choose channel #1 here) of both phantom and in vivo data processed in this note can be employed as the reference image. Though SOS is not a SNR optimized coil combine method, it can still serve as a useful guide for object signal detection.Difference maps were calculated to investigate signal difference between SOS images and magnitude components of AR,MAR, and ROMAR combined images. High-pass filtered phase images (using typical Gaussian window with $\sigma = 4 2$ ）ofAR,MAR, and ROMAR results were also computed to identify the phase image quality.18 For 3D SPGR data, susceptibility maps are determined from the above combined phase images by recently developed quantitative susceptibility mapping (QSM) method to test the combined phase quality.19

For phase difference reconstruction，two groups of the multichannel images (the dual echo data) with different echo times were reconstructed, respectively, by the proposed ROMAR method.Then, the phase difference image was obtained by Eq. (4) of Ref.9. The WM method using Eq. (3) of Ref.9 was employed for comparison.

# 4.RESULTS

The reconstruction results of noisy phantom and head data were shown in Figs.1and 2,respectively. The mean and standard deviations (SDs) values of the top left noise regions (size: $4 0 \times 4 0 )$ in magnitude maps of SOS,AR,MAR,and ROMAR were shown in TableI.Both the mean and SD valuesof the noise regions in ROMAR magnitude maps were minimum when comparing with those obtained from the other methods. In addition, the SDs of AR signal were larger than those results of SOS,MAR,and ROMAR methods.This occurs because of the unstable correlation matrix averaging procedure of AR. As can be seen in Figs.1 and 2,both phase and high-pass phase images by AR suffered some nonsmooth phase artifacts (seen in the circle regions).The results of MAR incurred in some signal-loss artifacts,both in magnitude and phase images,due to the rapid phase variation of the data.In contrast,both the magnitude and phase images of ROMAR combined image were free of artifacts and showed high image quality.

MAR combined images of 3D SPGR data still presented signal-loss artifacts (see the circle regions in Fig.3).Figure 4 shows the susceptibility maps which correspond to the combined phase images in Fig.3.The small artifacts in the MAR phase images caused extremely large errors in susceptibility maps determination.

As can be seen from the results of both noisy phantom and head data, nonsmooth and signal-loss artifacts were appeared in AR and MAR combined images,respectively.Besides, signal-loss artifacts still damaged the MAR combined image of high SNR SPGR data. In contrast,whatever images reconstructedfromnoisyorhighSNRdata,ROMARmethod always showed SNR-optimized and artifacts-freed combined magnitude and phase images.

The results of phase difference reconstruction were shown in Fig.5.It is seen that signal variance within the circular region of the WM phase image is larger than that of the ROMAR phase image,which shows that the phase difference image reconstructed by ROMAR possesses a higher SNR than that of the WM method.

![](images/0cc901ce8f77827c58995638bcd9693e167c14e10f30e64394ab07579438fb47.jpg)  
FI.4Rcobloitssso imagesin Fig.3.The susceptibility results of ROMAR are shown in the second column.

Medical Physics,Vol. 42, No.2, February 2015

![](images/5ba3a1d9c93ecd94c630aac31ac4c42abf6cce1f3182bdf2503c085cea19fba7.jpg)  
FG.5Recostrofseatdtiaesiecosededod ROMARethdsspectivelyTgnalranceiticeregisoftendOARpaseimagsareO.57dO.45sctiely

# 5.DISCUSSION

Both phantom and in vivo studies have demonstrated that our proposed image combination method, relative to conventional image reconstruction methods,yields more accurate and robust performance,in particular when multichannel images are noisy or oscillating. The developed ROMAR method always showed SNR-optimized and artifacts-freed combined magnitude and phase images.

SMF of the proposed ROMAR were applied by pixelwise combination with $8 \times 8$ SROI correlation matrices.Signal averaging of pixels in SROI box is beneficial for the continuity of combined phase image.Similar to the original AR method, the size of SROI can be selected adaptively.However, a small size of SROI should be sufficient because the majority of the noise has been removed by the smoothing method.In our tests,TF values from 4 to 2O can be used in practice.A large TF value $_ { ( \geq 8 ) }$ is recommended for full elimination of noise energy and increased phase consistency between channel images. Besides,because of the elimination of susceptibility components from raw multichannel phase images, the new channel images contain sufficient low frequency components.Thus, coil sensitivity information is well preserved in the filtered multichannel images [seen in Eq. (8)] even with a large TF.

The data processed by the proposed ROMAR method in this note are fully sampled, which have a higher SNR,and do not contain aliasing artifacts compared with undersampled data.In practice,when the acquired data have a low SNR such as diffusion weighted imaging (DWI) with a high $b$ -value,or when the imaging contrast is sensitive to both aliasing artifacts and noise level such as functional MRI,or when the high resolution images which contain small tissue details are needed such as whole brain $T _ { 1 }$ weighted imaging for voxel-based morphometric (VBM) analyzing or QSM, we recommend these data be fully sampled and combined by the proposed ROMAR method to obtain images with high quality.

The ROMAR method can also be combined with parallel imaging techniques such as SENSE(Refs.4,15,and 2O) and GRAPPA.21,22 For combination with SENSE, the SMF (i.e., coil sensitivity weights) of ROMAR is derived from the fully sampled center $k$ -space lines.20 Then,Eq. (16) of Ref.20 may be employed for optimal magnitude and phase reconstruction.To combine with GRAPPA,undersampled data should be reconstructed by GRAPPA algorithm first to derive the full resolution multichannel data.Then,optimal multichannel image combination can be derived by the proposed ROMAR method.

In addition, the proposed ROMAR method inherits the capability of suppressing motion-related artifacts in the original AR implementation.Besides QSM,the developed ROMAR method is potentially useful for phase contrast (PC) flow imaging.8 The image reconstruction procedure for PC flow imaging is the same as the phase difference reconstruction described above.Hence, it is advantageous to use the proposed ROMAR method than the WM method9 in PC flow imaging, especially when the SNR is low.

# 6.CONCLUSION

An improved adaptive reconstruction method is proposed in this work to obtain accurate coil sensitivity estimations for SNR-optimized and artifacts-freed multichannel image combination. Compared to the conventional AR,MAR,and WM methods,more robust and reliable results can be obtained from the proposed ROMAR method.

# ACKNOWLEDGMENTS

This work was supported by the China's National Strategic Basic Research Program (973) (2012CB720700) and the Natural Science Foundation of China(81227003 and 81430037).

experiment involving human samples,”J.Magn.Reson.34,425-433 (1979).   
$^ 4 \mathrm { K }$ P.Pruessmann,M.Weiger,M.B.Scheidegger,andP.Boesiger,“SENSE: Sensitivity encoding for fast MRI,”Magn.Reson.Med.42,952-962 (1999).   
$^ { 5 } \mathrm { { S } }$ .N. Sotiropoulos,S.Moeller, S. Jbabdi, J. Xu,J.L. Andersson, E.J. Auerbach,E.Yacoub,D.Feinberg,K.Setsompop,L.L.Wald,T.E.J. Behrens,K.Ugurbil,and C.Lenglet,“Effects of image reconstruction on fiber orientation mapping from multichannel diffusion MRI:Reducing the noise floor using SENSE,Magn.Reson.Med.70,1682-1689 (2013).   
$^ 6 \mathrm { M }$ Bydder,D.J.Larkman,and J.V.Hajnal,“Combination of signals from array coils using image-based estimation of coil sensitivity profiles,"Magn. Reson.Med.47,539-548 (2002).   
$\mathrm { { ^ 7 D } }$ O.Walsh,A.F. Gmitro,and M. W. Marcellin,“Adaptive reconstruction of phased array MR imagery,"Magn.Reson.Med.43,682-690 (2000).   
$^ 8 { \bf M }$ A.Bernstein,M. Grgic,T.J.Brosnan,and N.J. Pelc,“Reconstructions of phase contrast,phased array multicoil data,”Magn.Reson.Med.32, 330-334 (1994).   
$^ { 9 } \mathrm { K }$ Lua,T.T.Liua,andM. Bydder,“Optimal phase difference reconstruction: Comparison of two methods,Magn.Reson.Imaging 26,142-145 (2008).   
$^ { 1 0 } \mathrm { S }$ .Robinson,G. Grabner, S.Witoszynskyj,and S. Trattig，“Combiningphase images from multi-channel RF coils using 3D phase offset maps derived froma dual-echo scan,"Magn.Reson.Med.65,1638-1648 (2011).   
$^ { 1 1 } \mathrm { K }$ E.Hammond,J.M.Lupo,D.Xu,M.Metcalf,D.A.C.Kelley,D.Pelletier, S.M.Chang,P.Mukherjee,D.B.Vigneron,and S.J.Nelson,"Development ofa robust method for generating $7 . 0 \mathrm { T }$ multichannel phase images of the brain with application to normal volunteers and patients with neurological diseases," NeuroImage 39,1682-1692 (2008).   
${ } ^ { 1 2 } \mathrm { D }$ L.Parker,A. Payne,N. Todd,and J. R. Hadley,“Phase reconstruction from multiple coil data using a virtual reference coil,”Magn.Reson.Med. 72,563-569 (2014).   
$^ { 1 3 } \mathrm { C }$ Ros,S.Witoszynsky,K.H. Herrmann,and J.R.Reichenbach,“Reconstruction of phase images for GRAPPA accelerated magnetic resonance   
imaging,”in Proceedingsofthe4th European Conferenceof IFMBE,   
Antwerp,Belgium (Springer,Berlin,2008),pp.803-806.   
$^ { 1 4 } \mathrm { C }$ Ros,S. Witoszynsky, K. H. Herrmann,andJ. R.Reichenbach,"Recon  
struction of phase images for GRAPPA based susceptiblity weighted imaging(SWI),inProceedingsoftheInternationalSocietyofMagneticReso  
nanceinMedicine,2lst ScientificMeeting,ISMRM,Toronto,Canada (International Society forMagnetic Resonance in Medicine,2Oo8),p.1265.   
15Y. J. Ma, W.Liu, X. Tang,andJ. H. Gao,“Improved SENSE imaging using   
accurate coil sensitivity maps generated by a global magnitude-phase fitting method,"Magn.Reson.Med.(2014) (E-pub ahead of print).   
$^ { 1 6 } \mathrm { { M } }$ A.Griswold,F.Breuer,M.Blaimer,S.Kannengiesser,R.M.Heidemann,   
M.Mueller,M.Nittka,and V.Jellus,"Autocalibrated coil sensitivity estima  
tion for parallel imaging,"NMR Biomed.19,316-324 (2006).   
$^ { 1 7 } \mathrm { L }$ Ying and J.Sheng,“Jointimage reconstruction and sensitivity estimation   
in SENSE(JSENSE),"Magn.Reson.Med.57,1196-1202 (2007).   
$^ { 1 8 } \mathrm { E }$ .M.Haacke,Y.B. Xu,Y.C.Cheng,and J. R. Reichenbach,"Susceptibility weighted imaging (SWI),Magn.Reson.Med.52,612-618 (2004).   
${ } ^ { 1 9 } \mathbf { B }$ Bilgic,I. Chatnuntawech,A. P.Fan, K. Setsompop,S.F.Cauley,L.L. Wald,and E.Adalsteinsson,“Fast image reconstruction with L2-regular  
ization,"J.Magn. Reson.Imaging 40,181-191 (2014).   
$^ { 2 0 } { \cal Z }$ Chen,L. A. Johnston,D.H. Kwon,S.H. Oh,Z. H. Cho,and G.F.Egan,   
“An optimized framework for reconstructing and processing MR phase   
images,NeuroImage 49,1289-1300 (2010).   
$^ { 2 1 } \mathbf { M }$ 、A.Griswold,P. M.Jakob,R.M.Heidemann,M. Nitka,V. Jellus,   
J.Wang,B.Kiefer,and A.Haase,“Generalized autocalibrating partially   
parallel acquisitions (GRAPPA),”Magn.Reson.Med.47，1202-1210 (2002).   
$^ { 2 2 } \mathrm { W } .$ Liu,X. Tang,Y.J.Ma,andJ. H. Gao,“Improved paralel MR imaging usinga coefficient penalized regularization for GRAPPA reconstruction," Magn.Res0n.Med.69,1109-1114 (2013).