# Learning an Adaptive Model for Extreme Low-light Raw Image Processing

Qingxu $F \pmb { U } ^ { 1 }$ , Xiaoguang $D _ { \ L } ^ { \ L _ { 1 * } }$ ， Yu Zhang²   
1ControlandSimulation Center,Harbin Instituteof Technology,Harbin,150080,People'sRepublicof China   
2NationalKeyboatoryofableLserhologyHarbinstituteofcnologyHarbinoeople'sepublcfa   
\*E-mail:dixiaoguang@hit.edu.cn

Abstract:Lowlight images sufer from severenoiseand lowilumination.Current deep learning models thatare trained with real-worldimages have excelent noisereduction,butaratioparametermustbechosen manualy tocomplete theenhancement pipeline.Inthis work,we proposeanadaptive low-lightrawimageenhancement network toavoid parameter-handcratigand to improve imagequaity.The proposed method canbedivided into two sub-models:Brightness Prediction (BP)and Exposure Shifting (ES).Theformer isdesignedtocontrolthe brightness oftheresulting image byestimatingaguideline exposure time $t _ { 1 }$ ： The latter learns to approximate an exposure-shifting operator $E S$ ， converting a low-light image with real exposure time $t _ { 0 }$ to a noise-free image with guideline exposure time $t _ { 1 }$ . Additionally, structural similarity (SSIM) loss and Image Enhancement Vector (IEV)are introduced topromoteimagequaliyandanew Campus Image Dataset (CID)isproposedtoovercomethelimitations of theexistingdatasetsandtosupervisethetrainingof theproposedmodel.Inquantitivetests,itisshownthat theproposed methodhas thelowestNoiseLevelEstimation(NLE)scorecomparedwithBM3D-basedlow-lightalgorithms,suggestingasuperior denoisingperformance.Furthermore,thosetestsilustratethateproposedmethodisabletoadaptivelycontroltegobalimage brightnessaccording tothecontentoftheimagescene.Lastlythepotentialaplicationinvideoprocessingisbrieflydiscued.

# 1 Introduction

Images playan irreplaceable role in industry,militaryand entertainment.As the art of light,how to obtain betterimages inthe low-light environment has been extensively studied in the literature.Some advanced photography equipment can help but at an expensive cost. On the other hand,there are few limitations to post-process low-light images.However,it is challenging due to problems such as noise, color distortion et al.

Exposure time,ISO (which measures the sensitivity of the image sensor) and aperture are known as three pillars of photography.With extended exposure time,the low-light problemcan be easily solved, but itis not realistic because if the camera is not fixed or the scene contains moving objects.Higher ISO introduces more noise and is not always available for mobile devices.Asa flexible solution,lowlight image enhancement provides an alternative for imaging in the low-light environment.

In general, current low-light image enhancement method can be classifiedas follows:

Classic low-light image enhancement methods,with no application of convolutional neural networks.Histogram equalization (HE)[1] and gamma correction[2] provide simple solution for lowlight image processing. Based on Retinex theory[3], Single-scale Retinex (SSR)[4]，Multi-scale Retinex (MSR)[5]，SRIE[6]and LIME[7] were proposed,enhancing low-light image by estimating the illumination map and reflectance map.Dehazing[8] methods can also be applied to this subject,regarding low-light images as inversed hazed image.

With the rapid development of the deep neural network, researchers have combined classic low-light image enhancement methods with Convolutional Neural Networks (CNNs).Chen et al.proposed Retinex-Net[9] to decompose low-light image into illumination and reflectance and use BM3D[1O] for denoising.

Those methods assume low-light images are free of noise or noise isalready removed by additional denoising process.Therefore,when applying those methods on real-world low-light images,an additional denoising process is required.However,most low-light images suffer from severe noise,traditional denoising methods like BM3D are not able to provide satisfactory results.To be rid of image noise, researchers also explored the method of deep learning[11-14] in denoising topics.

![](images/033d0ab9a45c5acc066d982d3db91ce970934290976d89b29650fad7144c32c9.jpg)  
Fig.1: Several scenes in CID datasets.

There are some low-light images which are barely visible before post-processing，as they are captured in extremely dark environments or with very short exposure time.In this work,those images arenamed as extreme low-light images.While the classic methods are unable to tackle the severe noise and serious color distortion in those images,itis then discovered that with the help of deep learning and raw-format image datasets,we can still obtain satisfactory results.Chen et al.proposed an end-to-end solution for raw lowlight image enhancement[15],dealing with the low-light problem and denoising in a single model.However,extra brightness amplification ratio is needed and requires manual parameter tuning for different scenes,gaining excellent denoising effects but losing the flexibilityand adaptability ofclassic methods.

Currently,all datasetsavailable forlow-light enhancementmodels chose a longer-exposed image as the ground-truth image in training, which was heavily dependent on the dataset collector's experience to select exposure parameters such as exposure time,ISO and white balance mode.Thus these parameters were usually not optimal,considering the content of the scene,illumination of the environment et al.,which can lead to an undesired trained model.

It is hard for deep CNNs to learn how we determine the best exposure parameters for the ground-truth images because this can bevery subjective and lacks specific standards.It canlead to more problems if there is more than one dataset collector.On the other hand,making a baseline for ground-truth selection is equally difficult.Nevertheless,it is possible to predict how an image varies when exposure parameters change.We name this process Exposure Shifting(ES).Witha learnedES model,itbecomespossible to reversely study what good exposure parameters (e.g.exposure time) should be for each low-light image,utilizing the characteristics of the back-propagation algorithm.

![](images/581eedf313e3bd2dda6bb7fb5baa4b8794b3c5240000457d38e2e40a6e788ce4.jpg)  
Fig. 2: The proposed framework.For a underexposed low-light raw image with guideline exposure time $t _ { 1 }$ already known,the Exposure ShiftingNetwok(E)ispledtoompletetestiatioofthGesultiageIorgeneacase,righessrdictioetok (BPN) is utilized to give a proper estimation for the uncertain parameter $t _ { 1 }$ with raw image array and available Exif metadata.

The contributions of our work are summarized as follows:

1） We presented Campus Image Dataset (CID),which contains a variety of scenes captured by multi-level exposure.CID provides powerful support for the training of our data-driven low-light enhancementmodel.

2)We proposed an adaptive two-stage low-light image enhancement model,which provides state-of-the-art low-light noise suppression as well as adaptive global brightness control effect:

In stage one,a Brightness Prediction Network(BPN) was introduced to estimate a proper exposure time based on the content of images as well as Exif (Exchangeable image file) metadata.BPN was trained to provide adaptive image brightness control during image enhancement and to get ridof the external parameters required in the Exposure Shifting stage.

In stage two,an Exposure Shifting Network(ESN) was proposed to estimate a longer-exposed version of the image with target exposure time estimated by BPN.Moreover,ESN also completes image denoising and ends up with the final resulting RGB image.

The rest of the article is organized as follows.In section Related Works,previousresearch works are provided.The Dataset section demonstrates the importance and advantages of our CID (CampusImage Dataset) dataset.In the Method section,our model and its training details are provided,as well as the design concept of the model. The proposed model is compared with other state-ofthe-art methods in Experiments section,from multiple perspectives including denoising，adaptive brightness control performance and computational cost. The possible extension in video processing is brieflydiscussed here.In the Conclusion and Discussion section,the advantages and the limitations of our model are concluded.We also present the future expectations of this work.

# 2 Related Works

The method we proposed was inspired not only but the application of deep neural networks,but also by classic methods based on the Histogram Equalization model, dehazing model and Retinex model.

# 2.1 Histogram EqualizationMethods

Histogram Equalization (HE） method is used extensively to process digital images.The basic idea is to improve image visibility by changing the image histogram into a uniform distribution,which effectively increases image entropy for low-light images.In [16] it isargued that a color-invariant representation can be obtained by applying HE.However,HE tends to cause noise amplification,details disappearance and color distortion in low-light image enhancement.

On account of the drawbacks of HE,a number of improvements have been put forward. Adaptive Histogram Equalization (AHE)[17] and its variation Contrast-limited Adaptive Histogram Equalization(CLAHE)[18] perform the histogram equalization in a region surrounding each pixel, instead of across the whole image. Hue-preserving color image enhancement [19] works on contrastenhanceing and hue-preserving,[2O] and [21] on preserving the original image luminance.

# 2.2 DehazingandRetinexModel-BasedMethods

A number of low-light enhancement methods are based on the dehazingand Retinex model.It is observed that low-light images and inversed haze images share many similarities.For this reason,[8] presented a method in which low-light image is inversed,dehazed and then inversed back again.This method was studied further by [22] and [23].

On the other hand,the Retinex model[3] revealed thata natural image is made up of the illumination map and the reflectance map.With Retinex decomposition and the assumption that the illumination map is smooth,researchers have proposed single-scale Retinex [24] and multi-scale Retinex [4].Based on image fusion, adjustments can be applied to the illumination map to improve the performance [25].[26] focused on preserving natural characteristics witha Bright-Pass filter.In [27],a variational Retinex model was proposed and the illumination estimation problem was formulated as a Quadratic Programming optimization problem.In [28] illumination map is estimated considering local structure and [29] focused on revealing the structure details from the reflectance map.A recent study shows that the Retinex model can combine with the atmospheric scattering model[3O].More refined models were presented by[31,32] based on variational Retinex theory.

However,noise modeling is not well established in those algorithms.In [8] it is assumed that noise is insignificant and can be removed before or after the Dehazing stage.And the Retinex based models rely on classic noise reduction algorithms(e.g.BM3D） to reduce noise found in the reflectance map.Therefore it can achieve good results in mild low-light images but tends to amplify noise when processing severe or extreme low-light images.Besides,the variational Retinex model is very time-consuming as it takes many iterations to solve the optimization objectives and so are many denoising algorithms,thus it is hard to achieve real-time processing.

# 2.3 Data-driven Methods

Image-denoising and low-light enhancement can be realized with the data-driven approach,separately or integrated.

Noise reduction has been the subject of extensive studies.[11] has discovered that convolutional neural networks can compete with the state-of-the-art classic denoising algorithm BM3D.The works on date-driven denoising have been extended by[14,33,34].Although these works were not targeted at low-light image processing,they provide some references for the research of other image processing studies.

The first application of the data-driven method is LLNET [12], which utilizes a deep auto-encoder to learn from synthetic low-light image datasets and the object of denoisingis integrated into the lowlight enhancement process.Also,it was demonstrated that Retinex based methods can be further improved by deep learning [9,35],but those works still have undesirable denoising performance because synthetic datasets are used and they cannot reflect the characteristics of real low-light images.

To solve the drawbacks of synthetic datasets,a large multiexposure image dataset was proposed in [36],but it was found by [15] that models that utilize raw-format images can provide much better results in low-light enhancement.In [15],it suggested that the state-of-the-art results can be achieved by using raw-format paired images and training in an end-to-end way.However,since the paired two images have different exposure time,a ratio was introduced as an additional input to bridge the gap.Thus after the model is trained and with no reference to indicate the ratio,[15] requires manual adjustment for every different image to be enhanced,resulting in many drawbacks in practical applications.

# 3 Dataset

For extreme low-light image enhancement, there are few optional datasets.The Google $\mathrm { H D R + }$ dataset[37] and Darmstadt Noise Dataset[38] avoid the disadvantages of synthetic datasets,but they were mainly collected in environments with sufficient illumination.The RENOIR[39] and learning-to-See-In-the-Dark dataset (SID)[15] provides real low-light image pairs,which is captured by carefully selecting the ISO and exposure time for each scene.The Exclusively Dark Dataset (EDD) [4O] is another low-light dataset with object-level annotations,which is targeting at object recognition.But these datasets cannot satisfy the need of our study.In our work,in order to adaptively enhance images with different noise levels,it is needed to consider how the exposure parameters have an impact on low-light images.More specifically,as the environment illumination grows lower, low-light images are gradually overwhelmed by noise and invalid pixels.Although itis not flexible to manipulate the environment illumination,the camera exposure time setting can be easily changed to simulate this illumination shift. Therefore,it is expected that there is a dataset containing,instead of just some image pairs,a number of multi-exposed image series,in each of which there are low-light images of different levels and one reference image captured in the same scene.

Overall, there are three conditions need to be met for a satisfying dataset:

· Real scenes.Unlike synthetic images,photos captured in real scenes reflect much more diverse noise and distortion pattern   
· Multiple exposure levels. Using a number of multi-exposed image series to train an adaptive model capable of enhancing low-light imagesofdifferentlevels.   
·Raw-format images.Most data captured by the camera sensor islost in format convertion,those lost infomation is essential for extreme low-light image enhancement. ISO 300   
Invalid Noise Image t=0.001 (XR,1, YR)   
Extreme Low-light Image 三 t=0.010 (to=0.01,tg= 0.30) ： 一 to= 0.020 (XR,2,YR)   
Mild Low-light Image t=0.050 (to =0.02,tg = 0.30) … t= 0.10 公 (XR,3,YR)   
Ground-truth Image tg 二 0.30 (to =0.05,tg = 0.30) … t= 0.50 (XR4,YR)   
Over-exposed Image to 二 1.0 (to =0.10,tg=0.30) CID Image Group

Based on the above description,we proposed our Campus Image Dataset (CID). There are about 2OO image groups in CID,each of which consists of 8 raw images with different exposure time,shot continuously in the same scene using a tripod (Fig.3). To be specific,for every group,an upper limit of exposure time was selected to make sure that the first image in the sequence was slightly overexposed,then a lower limit was chosen to capture an extreme low-light image as the last image in the sequence,and the gap between the limits was filled up by another6 images.Finally,the ground-truth image for each group was manually selected,and invalid images that had nothing but noise due to extreme short exposure were tagged and excluded.A demonstration of scenes in CID is presented in Fig.1.

# 4 Method

# 4.1 Method Overview

Most of the existing methods are unable to suppress the severe noise present in extreme low-light images.On the other hand, recent studies e.g.[15] have concentrated on the extreme low-light enhancement with raw-format images and real-scene datasets in an end-to-end way,but unlike the classic methods,the brightness of the enhanced image cannot be automatically controlled in this framework,more specifically,an external ratio has to be manually adjusted when the input image has no paired image as the reference.

It is our aim to find a solution to enhance extreme low-light images,combining the advantages of adaptive brightness control and superior denoising performance.It is found that the problem of lowlight enhancement can be considered as a special case of changing the time of exposure.With $t _ { 0 }$ and $t _ { 1 }$ representing exposure time, the low-light image $\mathcal { X } _ { t _ { 0 } }$ can be interpreted as a normal image $\boldsymbol { \mathcal { { y } } } _ { t _ { 1 } }$ corrupted by a hypothetical exposure-shifting operator $E S$ ,which only alters the exposure time but keeps the aperture and ISO unchanged:

$$
B \mathcal { X } _ { t _ { 0 } } = E S ( \mathcal { V } _ { t _ { 1 } } , t _ { 0 } )
$$

In this process,more stochastic noise $\mathcal { N }$ is generated by operator $E S$ because $t _ { 0 } < t _ { 1 }$ ,corresponding to the low PSNR(Peak Signal to Noise Ratio) value in low-light images.Contrariwise,the corrupted

![](images/2f867a0f89971bd4593515bea21a604bf125577b7bd878a0a31f5cec3c2068e6.jpg)  
Fig. 4: The components of BPN.

low-light image can also be restored by the same operator $E S$

$$
\hat { \mathcal { N } } _ { t _ { 1 } } = E S ( \mathcal { X } _ { t _ { 0 } } , t _ { 1 } )
$$

The noise $\mathcal { N }$ is reduced because $t _ { 1 } > t _ { 0 }$ . Thus the normal image $\hat { \mathcal { V } } _ { t _ { 1 } }$ is reconstructed.

The latter process,named as Exposure Shifting (ES),can enhance low-light images as well as suppress image noise.More importantly, it can be learned in a data-driven and end-to-end way,thus itis expected to have superior denoising performance.However,a proper guideline exposure time $t _ { 1 }$ always has to be provided in the reconstruction $\hat { \mathcal { V } } _ { t _ { 1 } } ^ { \phantom { \dagger } }$ .To make our model adaptive,aBrightnessPrediction (BP) procedure is introduced to achieve guideline time estimation.

In brief,the extreme low-light enhancement process is split into two procedures.Firstly,for a raw-format low-light image(with real exposure time $t _ { 0 }$ ),an optimal guideline exposure time $t _ { 1 }$ is estimated via a sub-model called Brightness Prediction Network (BPN).Secondly, the final RGB-format enhanced image is obtained byanother sub-model,namely Exposure Shifting Network (ESN), using estimated guideline time $t _ { 1 }$ to control result brightness.

Inaddition,besides the image itself,some extra data are involved in both BPN and ESN,such as white balance index,ISO, $t _ { 0 }$ and $t _ { 1 }$ .The Image Enhancing Vector (IEV) is put forward to encode the involved extra data.

# 4.2 ImageEnhancingVector

Rawimage array is the original data captured by the camera. Other keyparameters,such as camera white balance,ISO,exposure time, time and date,are stored together with the raw image array as Exif metadata.In researches of HDR imaging[41],exposure time and ISO information have played an essential role in calculating the response curve and LDR to HDR conversion. Although it is not necessary to explicitly train the network to learn the camera response curve, feeding these additional parameters into the network as input avoids underfitting caused by insufficient features.

Image Enhancing Vector(IEV）is proposed to introduce extra features into the convolution neural networks.In this paper,IEV consists of ISO $u _ { s }$ ，white balance indices for 4 raw image channels $( w r , w _ { g } , w _ { b } , w _ { g 2 } )$ ，exposure time of the low-light image $t _ { 0 }$ and guideline exposure time $t _ { 1 }$ .Moreover,it is possible to append other Exif metadata into IEV to improve network performance when necessary,e.g.aperture and focal length.

The IEV is used as network input in both BPN(for $t _ { 1 }$ estimation)and ESN(for exposure shifting),but a difference exists.As it is shown in Fig.2,in ES procedure the IEV can be written as:

$$
\mathcal { V } ^ { t _ { 0 }  t _ { 1 } } = \mathcal { V } ( t _ { 0 } , t _ { 1 } ) = ( w _ { r } , w _ { g } , w _ { b } , w _ { g 2 } , u _ { s } , . . . , t _ { 0 } , t _ { 1 } )
$$

Where $( w r , w _ { g } , w _ { b } , w _ { g 2 } )$ are the white balace indices of 4 raw image channels and $u _ { s }$ is the ISO value (controlling the camera sensitivity).

In BP procedure the $t _ { 1 }$ in IEV is removed.It is renamed as partial IEV(pIEV) to indicate the difference:

$$
\mathcal { V } _ { p } ^ { t _ { 0 } } = \mathcal { V } _ { p } ( t _ { 0 } ) = ( w _ { r } , w _ { g } , w _ { b } , w _ { g 2 } , u _ { s } , . . . , t _ { 0 } )
$$

IEVand pIEV are fed into the convolutional neural network as additional channels of the raw image array.For example,the first

extra channel provided by IEV is a uniform image filled up with pixel value $w _ { r }$ ：

# 4.3 Exposure Shifting

Exposure Shifting (ES) is the second procedure in our model but istrained first.The U-NET[42] is selected as the structure of the Exposure Shifting Network(ESN),Compared with the fully convolutional network, the U-NET architecture reduced the usage of GPU memory, thus it can easily process images with high resolution.

Recall that the basic unit of our Campus Image Dataset(CID) is animage group,which consists of 8 raw-format images with different exposure time but captured in the same scene. Let $( \boldsymbol { \mathcal { X } } _ { R } , \boldsymbol { \mathcal { Y } } _ { R } )$ be the paired raw image extracted from one group,in which ${ \mathcal { V } } _ { R }$ is the pre-selected ground-truth image and $\scriptstyle { \mathcal { X } } _ { R }$ isarandom-selected lowlight image.More specifically, $\scriptstyle \mathcal { X } _ { R }$ is randomly chosen within this image group,with $y _ { R }$ and over-exposed images excluded (Fig.3). Moreover, the exposure time of $\scriptstyle { \mathcal { X } } _ { R }$ is denoted as $t _ { 0 }$ . The corresponding RGB-format image of $y _ { R }$ is denoted as $y$ and its exposure time as tg.

It is expected for the ESN to learn the exposure-shifting operator $E S$ froma large number of paired images.Specifically, the ESN is required to estimate an image $\hat { \mathcal { Y } }$ that resembles the $y$ as closely as possible.In this way ESN successfully changes the raw-format lowlight image $\scriptstyle \mathcal { X } _ { R }$ into an RGB-format longer-exposed version of itself. More importantly, the serious noise of $\scriptstyle { \mathcal { X } } _ { R }$ can also be removed.This procedure can be written as:

$$
\begin{array} { r l } & { \hat { \mathcal { Y } } _ { t _ { g } } ^ { \Theta _ { 1 } } = F _ { E S } \left( \chi _ { R } , \nu ^ { t _ { 0 } \to t _ { g } } \Big | \Theta _ { 1 } \right) } \\ & { \nu ^ { t _ { 0 } \to t _ { g } } = \mathcal { V } ( t _ { 0 } , t _ { 1 } = t _ { g } ) } \end{array}
$$

Where ESN is denoted as $F _ { E S }$ ,its parameters as $\Theta _ { 1 }$ . Note that since the BP procedure has not yet involved, the guideline exposure time $t _ { 1 }$ is replace by $t _ { g }$ in IEV $\gamma ^ { t _ { 0 }  t _ { g } }$ . The enhanced result image is represented by 1.

Two metrics to guide the training process of the ESN model are Mean Square Error (MAE)and multi-scale Structural Similarity(SSIM)[43].The formeris consideredasa simple but effective indicator,evaluating the general similarity of the estimated image and the groud-truth image.And the later is a perceptual metric that is more sensitive to visible structures.Both of them are full-reference metrics. Let $L _ { M A E }$ be the MAE loss and $L _ { S S I M }$ be the SSIM loss. The width and length of the image are denoted as $m$ and $n$ respectively.With subscript $t _ { g }$ omitted, the MAE loss $L _ { M A E }$ and SSIM loss $L _ { S S I M }$ are defined as:

$$
\begin{array} { l } { { { \cal L } _ { M A E } \left( \hat { y } ^ { \Theta _ { 1 } } , y \right) = \displaystyle M A E \left( \hat { y } ^ { \Theta _ { 1 } } , y \right) = \displaystyle \frac { 1 } { m n } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \left| \hat { y } _ { i j } ^ { \Theta _ { 1 } } - \mathcal { Y } _ { i j } \right| } } \\ { { { \cal L } _ { S S I M } \left( \hat { y } ^ { \Theta _ { 1 } } , y \right) = 1 - S S I M \left( \hat { y } ^ { \Theta _ { 1 } } , y \right) } } \end{array} 
$$

The final MAE loss is the average of the channel MAE loss,for simplicity,the image channel is not presented in the equation. The calculation of the multi-scale structural similarity (SSIM) can be refered in [43].With subscript $t _ { g }$ omitted,the loss function is defined as the linear combination of $L _ { M A E }$ and $L _ { S S I M }$ ：

$$
\begin{array} { r l } & { L _ { E S } = L _ { E S } \left( \hat { \mathcal { V } } ^ { \Theta _ { 1 } } , \mathcal { V } \right) } \\ & { \qquad = \left( 1 - \alpha \right) L _ { M A E } \left( \hat { \mathcal { V } } ^ { \Theta _ { 1 } } , \mathcal { V } \right) + \alpha L _ { S S I M } \left( \hat { \mathcal { V } } ^ { \Theta _ { 1 } } , \mathcal { V } \right) } \end{array}
$$

Where $\alpha$ is a constant and $0 \leqslant \alpha < 1$ .The influce of $\alpha$ will be discussed in the Experiments section.

The parameters of the ESN network $\Theta _ { 1 }$ are learned by minimizing $L _ { E S }$ over $K$ pairs of images in the training set:

$$
\Theta _ { 1 } ^ { * } = \underset { \Theta _ { 1 } } { \mathrm { a r g m i n } } \sum _ { k = 1 } ^ { K } L _ { E S } \left( \hat { y } _ { k } ^ { \Theta _ { 1 } } , y _ { k } \right)
$$

![](images/2b61a86b704f1bbb9bafcd148d17e021d592fae80f97bdc9bc4e39a0c182760a.jpg)  
Fig.5:Theresultsofusingourmethodtoehancemultipleimagesinasamesenebutcapturedwithdiverseexposuretime.Forthesecond image group, The exposure time $t _ { 0 }$ of the last image in the sequence is only $8 \%$ of that of the first,yet the network compensates for this difference, keeping the brightness of each image in the scene approximately uniform.

$\Theta _ { 1 } ^ { * }$ represents the optimized ESN parameters.

The obtained sub-model $F _ { E S }$ is an approximation to the exposure-shifting operator $E S$ .However,for a low-light image outside the training set,a ground-truth counterpart does not exist, thus the guideline time $t _ { 1 }$ in IEV $\gamma ^ { t _ { 0 }  t _ { 1 } }$ is absent, which leads to the Brightness Prediction (BP) sub-model and guideline time estimation.

# 4.4 BrightnessPrediction

The Brightness Prediction (BP) procedure provides the estimation of guideline exposure time $t _ { 1 }$ ：

$$
t _ { 1 } ^ { \Theta _ { 2 } } = F _ { B P } \left( \chi _ { R } , \nu _ { p } ^ { t _ { 0 } } \Big | \Theta _ { 2 } \right)
$$

Where $F _ { B P }$ and $\Theta _ { 2 }$ is BPN and its parameters respectively. The pIEV is represented by $\mathcal { V } _ { p } ^ { t _ { 0 } } = \mathcal { V } _ { p } ( t _ { 0 } ) ^ { ' }$ . It is the first enhancement procedure in our model but trained after the ESN.As it is illustrated inFig.4,TheBrightnessPredictionNetwork(BPN) isarelatively small network,which consists of multiple convolution layers and then ends up with several fully connected layers.Because of the existence of fully connected layers,the width and length of the input image $\scriptstyle { \mathcal { X } } _ { R }$ should be uniformly changed into $5 1 2 \times 5 1 2$ ：

With the estimated $t _ { 1 } ^ { \Theta _ { 2 } }$ obtained in this BP procedure, the $t _ { g }$ item in IEV in the ES procedure can be replaced by $t _ { 1 } ^ { \Theta _ { 2 } }$ . Different from $\hat { \mathcal { V } } _ { t _ { g } } ^ { \Theta _ { 1 } }$ derived in(5), te newfinalresult imagecanbeformuatedas:

$$
\hat { y } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } } = F _ { E S } (  \chi _ { R } , \mathcal { V } ^ { t _ { 0 }  t _ { 1 } ^ { \Theta _ { 2 } } } | \Theta _ { 1 } ^ { * } )
$$

Then an approach to train the BPN is required. To begin with, the purpose of BPN is to control the brightness of the final result image, which is achieved by adjusting the guiding exposure time $t _ { 1 }$ in the ES procedure. Since there are image pairs $( \mathcal { X } _ { R } , \mathcal { Y } _ { R } )$ and their exposure time $( t _ { 0 } , t _ { g } )$ available,intuitively it seems that the BPN can simply learnt from $( \mathcal { X } _ { R } , t _ { g } )$ in an end-to-end way,with $\scriptstyle { \mathcal { X } } _ { R }$ as the input as $t _ { g }$ as the label.However it cannot be achieved, the reason for which will be discussed later in the next subsection.

The proposed BPN training approach and the loss function $L _ { B P }$ are as follows.We define the brightness of a single pixel ${ B r }$ as the average pixel value of all color channels.Given a certain dark scene for image capturing and with ISO,aperture setings and the scene all fixed,then the brightness of a pixel is only determined by exposure time. Let $\mathcal { R }$ be the pixel irradiance in this scene,when the exposure time $t$ in camera settings increases,the pixel Exposure $\mathcal { E } ( \mathcal { R } , t )$ increases as well [44]:

$$
\mathcal { E } ( \mathcal { R } , t ) = \mathcal { R } t
$$

Thus the pixel becomes brighter.As an inspiration,it is feasible to design loss function $L _ { B P }$ based on pixel brightness.

It should be noted that the relationship between pixel brightness $B r ( \mathcal { E } )$ and Exposure $\mathcal { E } = \mathcal { R } t$ is not linear,instead, it can be typically described by an S-shaped curve because the pixel brightness is limited within [O,1] (or $[ 0 , 2 5 5 ]$ for 8-bit image storage) and the camera sensor is less sensitive to the change of $t$ when the pixel value is close to O or 1.In other words,as the exposure time $t$ setting changes,some pixels are not sensitive and there are little changes in the pixel brightness compared with some other pixels. For example,when photographing a street at night,pixels revealing the lamp bulbs are always saturated unless the $t$ is extremely small, and pixels representing the dark sky are always close to zero unless it is affected by noise.If those pixels are involved in BPN training, they can cause gradient vanishingin the back propagation algorithm because $\begin{array} { r } { \frac { \partial B r ( \boldsymbol { \mathcal { E } } ) } { \partial t } = \frac { \partial B r ( \boldsymbol { \mathcal { E } } ) } { \partial \boldsymbol { \mathcal { E } } } \cdot \boldsymbol { \mathcal { R } } } \end{array}$ OBr(). R and as it is revealed in the S-shaped ${ B r } _ { }$ ve rond0.5the aBr(ε) is close toO.Ontheotherhand,whenpixel brightness $\textstyle { \frac { \partial B r } { \partial t } }$ ing this condition can be collected into an Area of Interest (AoI), which identifies pixels that are sensitive to the process of Exposure Shifting.

![](images/2b88fa6cd65e81eec42a572506b6a2913460769ae7cecfef82859dc670f303c8.jpg)  
Fig. 6: The results using different methods on CID test images.From (a) to $\mathbf { \tau } ( \mathbf { g } )$ ,they are the original low-light images and the results of multiscale Retinex (MSR),MSRwithBMD,iluminationmapestimationbased(IME),LIMEwithD,deepRetinexdecooio (R-net), R-net with BM3D,learning-to-see-in-the-dark (SID) model and ours respectively.

First,in the ground-truth image $y$ ，an AoI weight map $\boldsymbol { \mathcal { W } }$ can be obtained by filtering out pixels with brightness near O.5.More specifically, the ground-truth image $y$ is converted into a single channel grayscale image $\scriptstyle { \mathcal { D } } _ { G }$ ，then a Gaussian culve with mean $\mu _ { w } = 0 . 5$ and variance $\sigma _ { w } ^ { 2 } = 0 . 0 1$ is applied on each pixel of $\scriptstyle { \mathcal { D } } _ { G }$

$$
\mathcal { W } _ { G } = \exp \left( - \frac { ( \mathcal { V } _ { G } - \mu _ { w } ) ^ { 2 } } { 2 \sigma _ { w } ^ { 2 } } \right)
$$

Then $\ w _ { G }$ is normalized, the result is the AoI weight map $\boldsymbol { \mathcal { W } }$ .The value at position $( i , j )$ is denoted as subscripts,namely $\mathcal { W } _ { G , i j }$ and $\mathcal { W } _ { i j }$

$$
\mathcal { W } _ { i j } = \frac { \mathcal { W } _ { G , i j } } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \mathcal { W } _ { G , i j } } , \forall 1 \leqslant i \leqslant m , 1 \leqslant j \leqslant n
$$

Combining the Equation 12 and 13,they can be simplified by the softmax function:

$$
\mathcal { W } = s o f t m a x \left( - \frac { ( \mathcal { V } _ { G } - \mu _ { w } ) ^ { 2 } } { 2 \sigma _ { w } ^ { 2 } } \right)
$$

Lastly, the loss function $L _ { B P }$ is designed to check if the final result image $\hat { \mathcal { V } } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } }$ has the same AoI. Having the same AoI means that in this AoI area $\hat { \mathcal { V } } ^ { \boldsymbol { \Theta } _ { 2 } | \boldsymbol { \Theta } _ { 1 } ^ { * } }$ and $y$ share similar brightness. Moreover, recall that pixels outside AoI are not sensitive to the change of exposure time $t$ or the ES process,thus it can be derived that the overall image brightness of $\mathcal { \hat { V } } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } }$ resembles that of $y$ . In this way,BPN completed the adaptive Brightness Prediction objective.

Then enhanced image $\mathcal { \hat { V } } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } }$ is converted into a grayscale image $\hat { \mathcal { V } } _ { G } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } }$ . When the AoI of $\hat { \mathcal { V } } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } }$ and $y$ overlaps exactly, the following loss function reaches its minimum:

$$
\begin{array} { c } { { { \cal L } _ { B P } = { \cal L } _ { B P } \left( \hat { y } _ { G } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } } , { \mathcal W } \Big | \Theta _ { 2 } ; \Theta _ { 1 } ^ { * } \right) } } \\ { { = - \displaystyle \frac { 1 } { m n } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \exp \left( - \frac { \left( \hat { y } _ { G , i j } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } } - \mu _ { w } \right) ^ { 2 } } { 2 \sigma _ { v } ^ { 2 } } \right) { \mathcal W } _ { i j } } } \end{array}
$$

Where $\sigma _ { v } ^ { 2 } = 0 . 0 4$ is another variance constant. The image value at position $( i , j )$ is represented by $i , j$ subscripts.Finally,BPN is trained by optimizing $\Theta _ { 2 }$ over $K$ pairs of images in the training set:

$$
\Theta _ { 2 } ^ { * } = \underset { \Theta _ { 2 } } { \operatorname { a r g m i n } } \sum _ { k = 1 } ^ { K } L _ { B P } \left( \hat { y } _ { G , k } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } } , \mathcal { W } _ { k } \Big | \Theta _ { 2 } ; \Theta _ { 1 } ^ { * } \right)
$$

In Algorithm 1, the training process of our model is summarized, together with the method to evaluate and apply this model.

1:Initialize ESN,BPN parameters $\Theta _ { 1 }$ and $\Theta _ { 2 }$ （204号   
2:Prepare CID dataset   
3:function TRAIN(Dataset)   
4: forEpochTrainl $\ E S N = 1  E _ { 1 }$ do   
5: for Image Pair $k = 1  K$ do   
6: Read rawimage pairs (XRk,VR,k)and Vtotg   
7: Convert to RGB format.Vk ←VR,k   
8: Compute $\hat { \mathcal { V } } _ { k } ^ { \Theta _ { 1 } }$ via Equation 5   
9: （2 $\begin{array} { r } { \Theta _ { 1 } \gets \mathrm { a r g m i n } _ { \Theta _ { 1 } } \sum _ { k = 1 } ^ { K } L _ { E S } \left( \hat { \mathcal { V } } _ { k } ^ { \Theta _ { 1 } } , { \mathcal { V } _ { k } } \right) } \end{array}$   
10: end for   
11: end for   
12: $\Theta _ { 1 } ^ { * }  \Theta _ { 1 }$   
13: for $E p o c h T r a i n B P N = 1  E _ { 2 }$ do   
14: for Image Pair $k = 1  K$ do   
15: Read raw image pair $( x _ { R , k } , y _ { R , k } )$ and $\gamma _ { p , k } ^ { t _ { 0 } }$   
16: Compute $t _ { 1 , k } ^ { \Theta _ { 2 } }$ and $\hat { \mathcal { V } } _ { k } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } }$ via Equation 9 and 10   
17: Convert to grayscale image. $y _ { G , k } \gets y _ { R , k }$   
18: Convert to grayscale image. $\hat { \mathcal { V } } _ { G , k } ^ { \ominus _ { 2 } | \ominus _ { 1 } ^ { * } } \gets \hat { \mathcal { V } } _ { k } ^ { \ominus _ { 2 } | \ominus _ { 1 } ^ { * } }$   
120 （2 $\begin{array} { r } { \Theta _ { 2 } \stackrel { \cdot } {  } \operatorname { a r g m i n } _ { \Theta _ { 2 } } \hat { \sum _ { k = 1 } ^ { K } } L _ { B P } ( \hat { y } _ { G , k } ^ { \Theta _ { 2 } | \Theta _ { 1 } ^ { * } } , \mathcal { W } _ { k } \Big | \Theta _ { 2 } ; \Theta _ { 1 } ^ { * } ) } \end{array}$ $\boldsymbol { \mathcal { W } _ { k } }$   
21: end for   
22: end for   
23: $\Theta _ { 2 } ^ { * }  \Theta _ { 2 }$ （204号   
24: return $\Theta _ { 1 } ^ { * }$ ， $\Theta _ { 2 } ^ { * }$   
25:end function   
26:   
27:function EVALUATE(Image)   
28: Read raw-format image $\scriptstyle { \mathcal { X } } _ { R }$   
29: Read all elements in $\bar { \mathcal { V } } _ { p } ^ { t _ { 0 } }$ from raw-image file   
30: BPN: Compute $t _ { 1 } ^ { \Theta _ { 2 } ^ { * } } \gets F _ { B P } \left( \left. \mathcal { X } _ { R } , \mathcal { V } _ { p } ^ { t _ { 0 } } \right| \Theta _ { 2 } ^ { * } \right)$   
31: ESN: Compute $\hat { \mathcal { V } } ^ { \Theta _ { 2 } ^ { * } | \Theta _ { 1 } ^ { * } } \gets F _ { E S } \left( \chi _ { R } , \mathcal { V } ^ { t _ { 0 } \to t _ { 1 } ^ { \Theta _ { 2 } ^ { * } } } \bigg | \Theta _ { 1 } ^ { * } \right)$   
32: return \*|0\*   
33:end function

Asmentioned earlierin the last section,training BPNwith input $\scriptstyle { \mathcal { X } } _ { R }$ and label $t _ { g }$ is straightforward but not feasible. First let $F _ { B P } ^ { * }$ be the hypothetical optimal BPN model, then $t _ { 1 } ^ { * } ( { \mathcal { X } } _ { R } ) = F _ { B P } ^ { * } ( { \bar { \mathcal { X } } } _ { R } )$ is the optimal estimation of guideline exposure time.For a pair of image and time label $( \mathcal { X } _ { R } , t _ { g } )$ ,the $t _ { g }$ can be considered as one sampling from a Gaussian distribution: $\dot { t } _ { g } \sim \mathcal { N } \left( t _ { 1 } ^ { * } , \sigma _ { c } ^ { 2 } \right)$ . The variance $\sigma _ { c } ^ { 2 }$ in this process is too large because:

·In every CID image group,the ground-truth image is chosen manually and is dominated by subjective human judgments. $\cdot$ The ground-truth image is selected from only 8 candidate images, but the optimal $t _ { 1 } ^ { * }$ exists somewhere in the time continuum $( 0 , \operatorname { i n f } )$

Furthermore,the number of samples is very limited since each image group can only provide one $t _ { g }$ sample.As a result,this straightforward approach cannot be applied in the training of BPN due to the high variance of the label $t _ { g }$ and the limited number of samples.

# 5 Experiments

# 5.1 Training

Limited by the GPU memory,we did not adopt the Batch Normalization [45] technique.To accelerate model training,before the training process started,each channel of the input image,as well as each element of IEV,was normalized along the sample dimension.Then the means and variances used in the normalization became invariant constants.Additionally, images for training were randomly cropped into $5 1 2 \times 5 1 2$ patches.

Algorithm1Model training and evaluation   
Table 1 Comparison results with non-reference image quality metrics.MSR, LIME,R-Net methods are combined with BM3D to make a fair comparison.Noreference quality metrics,including Statistical Noise Level Estimation (SNLE), NLE(Noise Level Estimation)，NV(Noise Variance) and image entropy，are applied to evaluate model denoising and brightness control performance.   

<html><body><table><tr><td>Methods</td><td>SNLE</td><td>NLE</td><td>NV</td><td>Entropy</td></tr><tr><td>Original</td><td></td><td></td><td></td><td>4.0689</td></tr><tr><td>MSR+BM3D</td><td>0.0014</td><td>1.3792</td><td>0.8998</td><td>7.0068</td></tr><tr><td>LIME+BM3D</td><td>0.0086</td><td>4.2437</td><td>10.1789</td><td>7.1084</td></tr><tr><td>R-Net+BM3D</td><td>0.0017</td><td>0.2467</td><td>0.4491</td><td>6.1503</td></tr><tr><td>Ours</td><td>0.0015</td><td>0.1061</td><td>0.4554</td><td>6.6112</td></tr></table></body></html>

Both ESN and BPN were trained with Adam optimizer[46], following the procedures shown in Algorithm1.The ESN was trained first with the learning rate slowly descending from $2 \times 1 0 ^ { - 4 }$ to $1 \times 1 0 ^ { - 5 }$ . After about 30O epochs, when the loss on training sets became stable.Then the parameters inESNwere made untrainable. Then BPN was appended to the training graph and trained with the same learning rate. Considering BPN may require global information to decide the proper exposure time,we used bigger patches but avoid training with the whole image to prevent overfitting.Although the loss must propagate through the deep ESN before reaching BPN, the training process went smoothly and completed after 1OO epochs.

# 5.2 Content-Based Brightness Control

Firstly,we highlight the adaptive brightness control feature of our method.Here we explicitly define the brightness as the mean value of an image $y$ ,denoted as $B r ( \mathscr { V } )$ .We expect a dynamic adjustment of the image brightness based on the image content.More specifically, while extreme low-light images suffer from severe noise along with color distortion and are barely visible before post-processing,other mildlow-light images only have moderate noise and relativelylower brightness compared with normal images.Thus,the enhancement algorithmneeds to make adjustments adaptivelyfor different input images.Currently the classic methods,such as algorithms based on Retinex and Dehazing,have poor performance on the extreme lowlight images,on the other hand,learning-based methods targeting at end-to-end denoising can process all kinds of low-light images, but they lack the flexibility and adaptability because they either need brightness amplification hand-tuning,or simply serve as a denoising procedure in other low-light methods.The proposed model is of the advantages of both and is able to process low-light images of differentlevels.

In order to evaluate the adaptability,we apply the trained model to enhance all images in the test set. Recall that the image group is the basic unit of our CID dataset,accordingly,instead of evaluating single images,the collaborative characteristics across different images are investigated within each image group.Note that the group identity of an imageis NOT involvedin model trainingand only serves asatag to gatherresulting images forfurther analysis.

For a sequence of multi-exposed images $( \mathcal { X } _ { R , 1 } , \mathcal { X } _ { R , 2 } , . . . )$ with increasing exposure time,it is expected that after enhancement the resulting images possess similar image brightness，namely $B r ( \hat { \mathcal { Y } } _ { 1 } ) \approx \breve { B } r ( \hat { \mathcal { Y } } _ { 2 } ) \approx \breve { \dots }$ ，where $\hat { \mathcal { V } }$ denotes the enhanced image. Fig.5(a) illustratesa busy-road scene,the first row displays theRGB images produced by the camera,the second displays the enhanced results by utilizing our method on individual raw images.Note that the first image in this group is exposed for 1/2O seconds,causing motion blur to the truck,while the last image is exposed for only 1/100 seconds.It is shown that all four images have approximately uniform brightness after enhancement,despite the changing $t _ { 0 }$ and the moving vehicle headlight.Fig.5(b) presents the performance of our method on extreme low-light conditions.The last image in the sequence suffers from both low environment illumination and short exposure and the color and shape of objects in the image are drowned out by noise.However, the resulting image has the noise reduced and still maintain acceptable global brightness.

![](images/aaecdcd515a055da78bf4cba0169a2bc60e6c997da0bab8f9aa0fe53c29aac6c.jpg)  
Fig.7: Controlled experiments on the impact of SSIMloss.

![](images/027a09a8798a8326b22a59a85d076b6c510e5152e5320593f69b4ef6b019c3c8.jpg)

Fig. 8: The shift of average brightness and brightness coefficient of variation(CV) within each group.Each Group contain 3-6 images captured ina brust with different exposure time,e.g.Fig.5.In both test set and training set,an increase in brightness and reduction in CV is observed.Note that the CV decreased considerably, indicating the highly uniformed brightness for images within each group after enhancement.

Asmentioned above,for quantitative analysis，we gathered images that belong to the same groups and calculated the brightness of all images in order to observe the shift of brightness.Let $( B r _ { 1 } , B r _ { 2 } , . . . ) _ { k }$ be the image brightness of each unenhanced lowlight image in $k$ -th image group and let $( B r _ { 1 } ^ { \prime } , B r _ { 2 } ^ { \prime } , . . . ) _ { k }$ be that of the enhanced ones.Then,the mean value and the CV(coefficient of variation) of $( B r _ { 1 } , B r _ { 2 } , . . . )$ is computed and denoted as $( \mu , c _ { v } ) _ { k }$ correspondingly, $( \mu ^ { \prime } , c _ { v } ^ { \prime } ) _ { k }$ is calculated from $( B r _ { 1 } ^ { \prime } , B r _ { 2 } ^ { \prime } , \cdots ) _ { k }$ .In Fig.8,we plotted $( \mu , c _ { v } )$ and $( \mu ^ { \prime } , c _ { v } ^ { \prime } )$ for all groups.To illustrate the change after enhancement, for each group $( \mu , c _ { v } )$ (marked with star)and $( \mu ^ { \prime } , c _ { v } ^ { \prime } )$ (marked with circle) are linked with a dotted line. It can be observed from Fig.8 that for different groups that captured from diverse scenes,the enhanced images all end up with increased image brightness and significantlyreduced CV.And yet the brightness growth between groups can be very different, ranging from around $60 \%$ to over $1 , 0 0 0 \%$ . Considering together with Fig.exp,Fig.8 indicates that the BP sub-modelis able to adaptively control the global image brightness according to not only the brightness of the original image,but also the content of the scene.On the other hand,the dramatic reduction of CV suggests that the enhanced images within each group share almost identical brightness in spite of the varying exposure time $t _ { 0 }$ .To be precise,our model can control group brightness CV under O.29 on $7 6 . 3 \%$ test set groups and $9 8 . 5 \%$ training set groups considering the influence of the diverse scenes, illumination conditions,capture ISO,etc.

![](images/2d8d54385a8d30d022c223eab24cc3950d0a6159f51fd711d6b06b9c2f3fe174.jpg)  
Fig. 9: The comparison of image original exposure time $t _ { 0 }$ and BPN assigned time $t _ { 1 }$ .BPN infers $t _ { 1 }$ based on not only the original time $t _ { 0 }$ but also the content of the scene.The color indicates the mean global brightness value of enhanced images within each group.

![](images/a430560846fd51c6ad8b1a3251aca35a4cf5e3514b120096fc9051076557decc.jpg)  
Fig.10: Applying our method to dynamic low-light video enhancement.

When designing our model, we expect the BPN to extract features of the scene content and then estimates a reasonable $t _ { 1 }$ accordingly. In order to see through clearly how this black box works,Fig.9 is plotted to illustrate the relationship between the real exposure time $t _ { 0 }$ ,the BPN-estimated guideline exposure time $t _ { 1 }$ and the brightness of enhanced images $\boldsymbol { B \ddot { r } } ( \boldsymbol { \hat { y } } )$ . Similar to Fig.8,we use group average to simplify the figure,in which each point corresponds to an image group.As shown in Fig.9,the network tends to estimate $t _ { 1 }$ positively associated with $t _ { 0 }$ .Furthermore,for groups with identical average $t _ { 0 }$ ,the contents of the scenes have an impact on $t _ { 1 }$ prediction. To be specific,if the scene of a group has more relatively bright areas, a smaller $t _ { 1 }$ is more likely to be adopted to prevent overexposure and vice versa. And yet a few exceptions exist, suggesting the BPN sub-model has learned some more sophisticated rules in the neural network black box.

# 5.3 Denoising Evaluation

We compare our method with four classic and state-of-art methods, including multiscale Retinex (MSR)[5],illumination map estimation based (LIME)[7],deep Retinex decomposition (Retinex-Net, R-Net)[9] and learning-to-see-in-the-dark (SID)[15].For fair comparison,3D transform-domain filtering (BM3D)[1O]is applied on MSR,LIME,R-Net,since those methods do not model noise and require extra denoising process.Additionally,we train the SID model on the CID dataset and manually select ratio $\gamma$ for the SID model since it does not provide automatic brightness estimation.

Recall that the BPNutilizesareduced reference evaluation index as the loss in its training.In this way,the exposure parameters of the ground-truth image,which is chosen by highly subjective human judgment, will have much less influence on BPN model training.As aresult of this novel technique,however,PSNR and SSIM evaluation cannot be adopted because there is no reference image.We provide perceptual comparisons in Fig.6 and evaluate our method with noreference quality metrics.

In Table.1,we compare the proposed method with MSR,LIME and R-Net(Retinex-Net),using several no-reference quality metrics including Statistical Noise Level Estimation (SNLE)[47],Noise Level Estimation (NLE) [48],Noise Variance (NV) [49] and image entropy.SNLE,NLE and NV metrics can estimate noise level from a single image,and clean images have relatively smaller values than noisy ones.The SNLE estimates noise variance by observing the eigenvalues of images and the NLE by applying the principal component analysis (PCA) on special image patches.The NV metric is motivated by the fact thatcleanand noisy imageshave different sensitivity to the Laplacian operation.The image entropy reflects the average amount of information in an image,itis the most simple image evaluation metric and images with proper overall brightness have larger image entropy.We run evaluations on about 4OO CID test images and the SID method is excluded because it requires an external manually-selected amplification ratio for every image. As it is shown in Table.1,our method has superior performance on Noise Level Estimation.Moreover, the no-reference metrics use very different standards to assess image quality.MSR $^ +$ BM3D,RNet+BM3D and $\mathbf { L I M E + B M 3 D }$ methods all have undesired scores on one or multiple indices,while our method has good performance on all metrics.

It is illustrated in Fig.6 that our method and SID method provide more significant improvements in noise removal than classic method BM3D and can adaptively denoise images with diverse noise levels.Furthermore,our results benefit from the white balance index introduced in IEV and avoid abnormal color in extreme low-light images.

However, the CNN-based method tends to blur the object with sharp edges (e.g. text).By introducing SSIM into loss function,our method shows more promising results in images with text and has advantages over SID in keeping more edge information,e.g. the images in the first row of Fig.6.But on the other hand,in controlled experiments shown in Fig.7,it is revealed that the ratio of SSIM component $\alpha$ in loss function $L _ { E S }$ has to be contained to avoid the noise being interpreted into texture and edge by ESN.

# 5.4 Low-light Video Processing

The advantage of our work lays in getting rid of the brightness control ratio while achieving state-of-the-art low-light noise suppression. Without any handcrafting parameters as network input, we can directly apply our method to raw low-light video processing.

A raw-format video can occupy a very large amount of storage space.Limited by devices,we only developed a relatively simple way to verify our method on raw low-light videos.In Fig.1O,we experiment on 21 continuous raw images captured in a burst session, shot with short exposure time and identical ISO,to discuss the potential applications in raw video processing.In this scene,the camera starts from a bridge with lighting decoration, then turns to the dark riverbank,and finally to the dimlyilluminated sidewalk.As is shown in Fig.1O,though the enhancement process of each frame is completely independentof other frames,neither the estimated $t _ { 1 }$ nor the resulting images show any sudden fluctuation.However,for practical considerations,it is also convenient to implement guideline time filters between ESN and BPN,which allows the value of $t _ { 1 }$ to be dynamically filtered or amplified according to different demands.

# 5.5 Computational Cost

The proposed algorithm is evaluated on the ModelArts cloud service,which is equipped with 8 vCPUs and an Nvidia-P1OO GPU (16GB GPU memory).The execution time for a high-resolution image $( 3 9 6 8 \times 2 9 7 6 )$ is O.27 seconds on average,which only shows a minor increase compared with the SID algorithm(O.21 seconds). More specifically, the execution time of BPN and ESN sub-model is 0.05 and O.22 respectively.For comparison,it takes 4.32 seconds for BM3D(GPU implementation [5O]) to complete the denoising process,therefore other low-light methods that depend on BM3D for denoising, including MSR,LIME,R-Net et.al.,are much less efficient on devices with GPUs.

# 6 Conclusion and Discussion

# 6.1 Conclusion

In this paper,an adaptive raw image enhancement model is proposed for extreme low-light image processing. The two-stage framework provides adaptability to images with different scenes and exposure parameters.We also presented the CID dataset for model training and evaluation.The experimental test shows that our model can provide the state-of-the-art low-light image denoising as well as adaptive global brightness control.

The proposed method has many advantages over existing approaches.In the first place,no external parameters are needed after model training,a single raw image and its Exif metadata (e.g.white balance,ISO and exposure time) are sufficient to complete the process.Therefore,our model is able to process a large batch of raw images without parameter-handcrafting. Secondly,our model significantly outperforms other methods in which denoising works as a separable step.because instead of simply implementing noise-suppression algorithms (e.g.BM3D) before or after the main low-light enhancement procedure,we make denoising procedure an integrated part in our model,allowing the ESN module to learn exposure shifting and denoising simultaneously in an end-to-end way. In quantitative experiments,we adopted no-reference image quality metrics including SNLE,NLE,NV and image entropy to test the denoising performance.Our model has the smallest noise variance on NLE metric compared to BM3D-based low-light methods and obtains approximate optimal scores on the other three indices.We also reveal the potential application in low-light video processing. The BPN module makes it possible for our model to process images with diverse exposure levels,from extreme low-light images to mild ones.But to be applied in video processing,it should face more challenges,e.g.the brightness of frames should change continuously and avoid fluctuation.We experiment on continuous raw image series, despite that no information of adjacent frames is used,the output of BPN changes continuously with the illumination condition and shows no fluctuation.

# 6.2 Limitationsand Future Works

The model proposed is limited by dataset,which is a common problem in data-driven methods.On the one hand, the model is trained by raw-format and multi-exposed images,which significantlyimproved image quality.But on the other hand,all reference ground-truth images are captured in the real scenes,as a result, they sometimes have minor defects such as noise,halos around the light source,local over-exposure and white balance deviation.The denoising performance may be further elevatedif those drawbacks canbe avoided. Then the image groups in CID have not covered enough nature scenes.For example,it is found that green grass and trees tend to havelow color saturation in the resulting images,that is because most images in the training set are collected in winter when there is hardly any green plants in scenes.For future study, the raw-format CID dataset can be extended by unprocessing[14] technique and generating raw-format images from other available online datasets.

Another limitation is algorithm memory consumption.The batch size is constrained because it takes too much GPU memory to train the proposed model. Therefore training the model can be time-consuming on GPUs with small memory. We are planning to improve network architecture and investigate the possibility of application on mobile devices.

Asa future expectation,the model can be further modified by introducing HDRI (High Dynamic Range Imaging). Since our CID dataset is composed of multi-exposed images,we can calculate an HDR image of each scene.Finally,the HDR images can be used as ground truth to participate in the ESN training.

# 7 References

1 Pizer, S.M.,Amburn,E.P.,Austin, J.D.,Cromartie,R.,Geselowitz,A.,Greer, T.,et al.:‘Adaptive histogram equalization and its variations',Computervision, graphics,and image processing,1987,39,(3),pp.355-368   
2 Huang，S.C.,Cheng,F.C.,Chiu,Y.S.:‘Efficient contrast enhancement using adaptive gamma correction with weighting distribution',IEEE Trans.on image processing,2012,22,(3),pp.1032-1041   
3 Land,E.H.: The retinex',American Scientist,1964,52,(2),pp.247-264   
4 Jobson,D.J.,Rahman,Z.,Woodell,G.A.:‘Properties and performance of a center/surround retinex',IEEETrans.on ImageProcessing,1997,6,(3),pp.451-462   
5 Jobson,D.J.,Rahman,Z.u.,Woodell,G.A.:‘A multiscale retinex for bridging the gap between color images and the human observation of scenes',IEEE Trans.on Image processing,1997,6,(7),pp.965-976   
6 Fu,X.,Zeng,D.,Huang,Y.,Liao,Y.,Ding,X.,Paisley,J.:‘A fusion-based enhancingmethod forweakly illuminated images',Signal Processing,2O16,129, pp.82-96 Guo,X,Li,Y.,Ling,H.:‘Lime:Low-light image enhancement via illumination mapestimation.',EEETrans.ImageProcessing,2017,26,(2),p.982-993   
8 Dong,X.,Wang,G.,Pang,Y.,LiW.,Wen,J.,Meng,W.,etal.:‘Fast efficient algorithm for enhancement of low lighting video'.IEEE Int.Conf.on Multimedia andExpo,Belo 9 Wei,C.,WangWang,W,LiuJDeepetiexdecopositioforloht enhancement,arXiv preprint arXiv:180804560,2018   
10 Kostadin,D.,Alessandro,F.,Vladimir,K.,Karen,E.: Image denoising by sparse 3-dtransfolbisg 2007,16,(8),pp.2080-2095   
11 Burger,H.C.,Schuler,C.J.,Harmeling,S.‘Imagedenoising:Can plain neural networks compete with bm3d?.IEEE Conf.on computer vision and patern recognition,Providence,RI,USA,2012.pp.2392-2399   
12 Lore,K.G.，Akintayo,A., Sarkar,S.:LInet:A deep_autoencoder approach to naturalow-lightigeeancement,ateecogitio17,61,pp6   
13 Zhang,K.,ZuoW,Chen,Y,eng,D.,Zhang,Leyondagauianeoiser Residual learningof deepcnn forimage denoising',IEEE Trans.onImage Processing,2017,26,(7),p.3142-155   
14 Brooks,T.,ildenhall,Xue,,Chen,harlet,D,Barron,J.T‘Ur cessing images for learned raw denoising'.Proc.of the IEEE Conf.on Computer Visionand PattmRecognition,LongBeach,CA,USA,2019.pp.103611045   
15 Chen,C.,Chen,Q.,Xu,J.,Koltun,V.:‘Learning to see in the dark'.Proc.of the IEEEConf.onComputerVisionandateRecogtionSaltLakeCityU USA,2018.pp.3291-3300   
16 Finlayson,G.,Hordley,S.,Schaefer,G.Iluminantanddeviceinvariantcolour using histogramequalistion’,aenRecognition,o5,38,pp.79190   
17 Pizer,S.MmbuE.PstinJDomartieRGselowizAre T.,etal.:Adaptive histogramequalizationand itsvariations',，GraphicalModels graphical ModelsndImageProcessngcomputer VisionGrapicsdge Processing,19879,(3),p.568   
18 Zuiderveld,K.J.:Contrast limited adaptive histogram equalization’,Graphics gems,1994   
19 Naik,S.K.,Murthy，C.A.:‘Hue-preserving color image enhancement without gamut problem',IEEETrans.onImageProcessing,200,12,(12),pp.591-1598   
20 Wang,Y.,Chen,Q.,Zhang,B.Imageenhancementbased onequalareadualistic sub-image histogramequalizationmethod,IEEETrans.onConsumerElectrois, 1999,45, (1),pp. 68-75   
21 Kim,Y.:Contrast enhancement using brightness preserving bi-histogram equalization’Esro9   
22 Li,L.,Wang,R.,Wang,W.,Gao,W.:A low-light image enhancement method for both denoising andcontrast enlarging',,2015   
23 Malm,H.as,,atE.J,bg,P,eenJ ‘Adaptive enhancement and noise reduction in very low light-level video,,2007   
24 Jobson,D.J.nZWoodell,GAropertiedpeorane ter/surroundretinex’,EEETrans.onImageProcessing,1997,6,(3),.45462   
25 Fu,X.,Zeng,D.,Huang，Y.,Liao,Y.,Ding,X.,Paisley,J.:‘A fusion-based enhancing method for weakly illuminated images',Signal Processing,2O16,129, pp. 82-96   
26 Wang,S.,Zheng,J.,Hu,H.,Li,B.Naturalness preservedenhancementalgoithm for non-uniformillminationimages',IEEETrans.onImageProcessing,2013,22, (9), pp.3538-3548   
27 Kimmel,R,d,ke,Dehetobe,:tilfr forretinex',nt.JouralofomputerVision,,52,(1),.   
28 Hao,S.,Feng,Z.,Guo,YLow-light image enhancement witharefined illumnation map',ultimediaToolsandApplications,2018,77,(22),pp.29639-29650   
29 Li, M.,Liu,JYang,W,Sun, X，GuoZStructure-revealing low-lightimage enhancementvibusreieoelEEasactioonge 2018,27, (6), pp.28282841   
30 Gu,Z.,Chen,C.,Zhang,D.y.‘Alow-light image enhancement methodbasedon image degradation model and pure pixel ratioprior',Mathematical Problems in Engineering0188   
31 Park,S.oo,,oSuSikJ:ightimageeaetin variational optimization-based retinex model',,2017   
32 Fu,G.,Duan,L.,Xiao,C.Ahybridl-lpvariationalmodelforsinglelow-light imageenhancement with brightchannel prior',2019.pp.1925-1929   
33 Zhang,K., Zuo,W.,Chen,Y.,Meng,D.,Zhang,L.: ‘Beyond a gaussian denoiser: Residual learningof deep cnn forimage denoising'，IEEE Trans.on Image Processing7(7),15   
34 Guo,S.,Yan,.,Zhang,K.,Zuo,W.,Zhang,L.:‘Toward convolutional blind denoising of real photographs',,2019   
35 Shen,L.,Yue,Z.,Feng,F.,Chen,Q.,Liu,S.,Ma,J.:Msr-net:Low-lightimage enhancement using deepconvolutional network',arXiv preprint arXiv:171102488, 2017   
36 Cai,J.,Gu,S.，Zhang,L.:‘Learning a deep_singleimagecontrast enhancer from multi-exposure images',IEEE Trans.on Image Processing,2018,27,(4), pp.2049-2062   
37 Hasinoff,S.W.,Sharlet,D.,Geiss,R.,Adams,A.,Barron,J.T.,Kainz,F.,et al.: Burst photography for high dynamic rangeandlow-light imaging onmobile cameras’,ACMTrans.on Graphics (TOG),2016,35,(6),pp.92   
38 Xu,J.,Li,H,Liang,Z,Zhang,D,Zhang,L:Real-worldnoisyimagedenoising: A new benchmark',arXiv preprint arXiv:180402603,2018   
39 Anaya,J.,BrbuAenoir-dtasetforaloghtiseagereucti, arXiv preprint arXiv:14098230,2014   
40 Loh,Y.P.,Chan,C.S.: Geting to know low-light images with the exclusively dark dataset',ComputerVisionandImage Understanding,2019,178,pp.042   
41 Reinhard,E.,Ward,G.,Patanaik,S.,Debevec,P.ighdynamicrangeimaging: acquisition,display,and image-based lighting'.(Morgan Kaufmann,2005)   
42 Ronneberger, O.,Fischer,P.,Brox,T.:‘U-net:Convolutional networks for biomedical image segmentation'.Int. Conf.on Medical image computing and computerassisted intervention,Munich,Germany: Springer,2O15.pp.234-241   
43 Wang,Z., Simoncelli,E.P.,Bovik,A.C.: ‘Multiscale structural similarity for image quality assessment'.The Thrity-Seventh Asilomar Conf.on Signals, Systems & Computers,2003,vol.2.Pacific Grove,CA,USA:Ieee,2003.pp.1398-1402   
44 Fu,L.,Qi,Y.:Camera response function estimation and application with a single image'.Yang,D.,editor.Informatics in Control,Automation and Robotics,Berlin, Heidelberg: Springer Berlin Heidelberg,2012.pp.149-156   
45 Ioffe,S., Szegedy,C.Batch normalization: Accelerating deep network training byreducing internal covariate shift',arXiv preprint arXiv:l50203167,2015   
46 Kingma,D.P.,Ba,J.:‘Adam:A method for stochastic optimization',arXiv preprint arXiv:14126980,2014   
47 Chen,G.,Zhu,F.,Heng,P.A.: ‘An efficient statistical method for image noise level estimation'.2015 IEEE Int.Conf.on Computer Vision (ICCV),,2015.pp.477- 485   
48 Liu,X.,Tanaka,M., Okutomi,M.:‘Single-image noise level estimation for blind denoising',IEEE Trans.onimageprocessing,2013,22,(12),pp.5226-5237   
49 Immerkaer,J.:‘Fast noise variance estimation',Computer vision and image understanding,1996,64,(2),pp.300-302   
50 Honzatko,D.,Krulis,M.:‘Accelerating block-matching and 3d filtering method forimage denoising on gpus',Journal of Real-Time Image Processing,2017