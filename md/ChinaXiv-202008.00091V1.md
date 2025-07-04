# Better Than Reference In Low Light Image Enhancement: Conditional Re-Enhancement Networks

Yu Zhang, Xiaoguang Di, Bin Zhang, Ruihang Ji, and Chunhui Wang

Abstract—Lowlightimagessufer fromsevere noise,lowbrightnesslowcontrast，etc.Inpreviousresearches，manyimage enhancementmethods havebeenproposed,butfewmethodscandealwiththeseproblemssimultaneously.Inthispaper,tosolve theseproblemssimultaneouslyweproposealowlightimageenancementmethodthatcancombinedwithsupervisedlearningand previousHSV(Hue,Saturation,Value)orRetinexmodelbasedimageenhancementmethods.First,weanalysetherelationshipbetween theHSVcolorspaceandtheRetinextheoryandshowthattheVchannel(VchanelinHSVcolorspace,equals themaximumcanel inRGBcolorspace)ofthenancedimagecanellepresentthecontrastandbrightnesseancementprocessTenadata-driven conditionalre-enhancementnetwork(denotedasCRENet)isproposed.Thenetworktakesowlightimagesasinputandtheenhanced Vchanelascondition,thenitcanre-enhancethecontrastandbrightnessofthelowlightimageandatthesametimereducenoise andcolordistortion.Ishouldbnotedthatduringthetrainingprocess,nypairedimageswithiferentexposuretimecanbeusedfor training,andthereisnoneedtocarefullyselectthesupervisedimageswhichwillsavealot.Inadition,ittakesless than $2 0 ~ \mathsf { m s }$ to process a color image with the resolution $4 0 0 ^ { \star } 6 0 0$ on a 208oTi GPU. Finally, some comparative experiments are implemented to prove theefectivenessofthe method.Theresultsshowthatthe method proposedinthispapercansignificantlyimprovethequalityof the enhancedimage,andbycombiningwithotherimagecontrastenhancementmethods,thefinalenhancementresultcanevenbebeter thatherefereneimageincontrastandbrightness.(Codewillbeavailableathtps:/gitubcom/hitzhangu/image-enhancement-with denoise)

Index Terms—Low Light, Image Enhancement,Denoising,Color correction

# 1 INTRODUCTION

Wtetiticiig light images. This kind of images always suffer from low contrast,low brightness,serious noise,and so on. Low light image enhancement method is used to solve these problems before high-level tasks.In the past decades,researchers have proposed lots of non-learning based image enhancement methods,such as [1],[2],[3],etc.Recently,with the development of deep learning,many supervised and unsupervisedlearning based image enhancement methods have beenproposed,such as [4], [5], [6], [7], etc.，and achieve promising results.However, whether these methods are based on learning or not, they have not been able to solve all these problems in low light images well simultaneously.

For non-learning based methods [3],[8], [9],most of them can significantly improve the image contrast and brightness.However, it is difficult for these methods to reduce or suppress noise directly,and they may even amplify noise or cause color distortion during the enhancement process.The later denoising operation often brings problems such as blur, disappearance of details, etc. For unsupervised image enhancement works,since it is difficult to introduce some prior knowledge to the learning pipeline,especially noise and color terms,there is always a problem of noise and color distortion [7]. For most supervised works [5], [10], there must be a hyperparameter which can be used to connect the input and reference image during training,and this iscaused by non-one-to-one correspondence between input and reference images.The hyperparameter can be used to adjust the contrast and brightness of the whole image during test, however, itis hard to obtain the hyperparameter automatically,and the brightness and contrast of some local areas may not be satisfactory even if the hyperparameter is adjustedcarefully.

In this paper, we provide a low-light image enhancement framework that can integrate unsupervised learning or non-learning methods with supervised learning methods to solve the low contrast,low brightness,noise and color distortion in low light images simultaneously.

The effectiveness of supervised methods often depends on the quality of the data. However, in low-level image processing tasks,it is difficult to get input/label pairs like high-level tasks,especially in image enhancement tasks. Although we can get some images with different illumination from the same scene by changing the lighting or modifying the camera parameters, we cannot guarantee that the reference image has good contrast and brightness on each image block (e.g.Fig.1(e)-(f)).At the same time,as one low light image can correspond to many high light images, it is hard to ensure consistency in the selected data (similar input image blocks should correspond to similar reference image blocks inlight).In fact,it can be considered that there is no ground-truth image here. Then the problem can be summarized as how we can train the networks without the unique or the best ground-truth image and how we can connect the input image and reference image when they do not meet the consistency condition during training. Different from the way of introducing a single hyperparameter such as time ratio [10] into the enhancement process in previous supervised works,we propose a new framework which can use point-wise parameters related to contrast to achieve training and the parameters can be automatically obtained through other contrast enhancement methods during test. It can be seen in Fig.1,combining our method with some contrast enhancement methods,like gamma correction, we can adjust the contrast of the enhanced image and reduce the noise simultaneously. And contrast in some local areas of the enhanced images are even better than those in the reference images, such as bookcase,seats in the dark part of stadium.

![](images/de959614c384f6303937e884533cb300824e3046b4a2293c26328b032615ff38.jpg)  
Fig.1.VisualComparsonwithReference.TopRow:low-lightimags.MiddleRow:Referenceimages.BotomRow:Teresultsehancedby our method combined with Gamma correction.

As with some previous works [11],we divided the low light enhancement problem into two sub-problems,one is the contrast and brightness enhancement problem,and the other is the denoising and color restoration problem. Different from the previous method to solve the two subproblems separately,weuse contrast enhancement methods to generate point-wise contrast and brightness proposals and use them as a condition to re-enhance the low light image,and at the same time reduce the noise and color distortion. The method in this paper can be combined with any image contrast and brightness enhancement method based on HSV color space or Retinex model. And the network can be trained without the need of carefully selecting reference images,and any paired images with different light can be used for training.

Our contributions can be summarized as follows:

A conditional re-enhancement network(denoted as CRENet) for low light image enhancement is proposed,which can solve the low contrast,low brightness,noise and color distortion simultaneously. The CRENet can be combined with existing image enhancementmethodandusetheenhancedVchannel as a condition to achieve re-enhancement of low-light images.In this process,the CRENet can maintain the contrast and brightness of other enhancement method,while reducing noise and color distortion at the same time.   
Compared with other learning-based methods,the hyperparameters included in our method are pointwise and are directly related to image contrast and brightness，which makes it possible that the enhanced image has better contrast than the reference image through adjusting the brightness and contrast of the local area of the image,and that is hard for other learning-based methods with only one hyperparameters.   
By combining with other contrast and brightness enhancement methods,the proposed method does not need to carefully select the reference images with

good exposure,and any paired images with different brightness can be used for training.

![](images/a92479bc1a8ead25491cb029331bad78f0d8dfaa917a0f4e1df10dc763f9219c.jpg)  
Fig.2.Visual Comparison with BM3D.(Best viewed on high-resolution displays with zoom-in.)

# 2 RELATED WORKS

# A.Non-learning based image enhancement methods

For non-learning based single low light image enhancement methods,there are mainly histogram equalization methods based on dehazing or Retinex model and other improved methods based on those methods.

Histogram Equalization(HE) is one of the most wildly used methods,however,it cannot avoid the problems of detail disappearance，poor color restoration,noise amplification and so on. Although many improved methods have been proposed to solve those problems [8], [9], [12], [13],[14], [15], there are still many problems in applying histogram equalization directly to image enhancement.

Dong et al. [16] proposed the method based on dehazing model firstly and then some studies extended these works [17],although these methods have achieved some good effect, they lack corresponding physical model,which limits the application of the method in various scenes.

Some works based on Retinex model are proposed to maintain image details and naturalness [3], [18],[19],however, the denoising process before or after the enhancement process will still cause blur or loss of details.To solve the noise and hole effect, and preserve more details, many algorithms based on the variational Retinex model are proposed and achieved good results,such as [2], [20], [21], [22], however, most of them will cost too much time due to the need of multiple iterations to solve the variational equation.

Most of the non learning methods focus on contrast and brightness enhancement, and then use general denoising methods (like BM3D [23]) and white balance to remove noise and correct the color, however, those methods always bring blur and cannot solve the problem of color distortion. As shown in Fig.2,although Gamma correction improves the contrast and brightness of the image,after the denoising operation of BM3D,some details disappeared.

B.Learning based image enhancement methods

As we know, LLNET [37] is the first work to use deep neural networks to solve image enhancement problem, and it proposes to train the networks with synthetic noisy and dark images separately, but it does not consider the characteristics of the natural images.Some other methods also use synthetic data sets,such as [24], [25], [26],although the data obtained by these methods seems to look like low light images,itis difficult to trulyreflect some characteristics of low light images,such as noise,color distortion,overexposed and underexposed areas existed in the same image, etc.

Chen et al.[1O] introduce a dataset which contains real raw low light images and corresponding raw high light images for training,and they introduce an amplification ratio to connect the input and reference images and multiply the ratio to a certain layer in the network.The ratio is set to be the exposure time difference between the input and reference images during training. This method can solve the problem of noise and color distortion well, however, the ratio must be chosen by user during test which limit the widely use of this method,and it can not solve the inappropriate contrast problem well. It can be seen that this algorithm provides an exposure time adjustment method instead of physically adjusting the exposure time,it is obvious that only by adjusting the exposure time cannot work well in the night scene, there will still be some over-enhanced (saturated) areas or under-enhanced areas in the image. In our previous work [27],we provide a way to automatically learn the expected exposure time,but still can not solved the problem of contrast. Because we can never provide the ground-truth reference images with proper contrast in every local area,and without other constraints,it is difficult to solve this problem.

In [4],it is proposed to introduce the Retinex model into the training process to connect the reflection images of input and reference.However,due to the lackof constraints on the noise of the reflection image,additional denoising methods(like BM3D [23]) still need to be introduced.The method proposed in [5] looks like the combination of [10] and[4]. Compared to [4], [5] provides an extra brightness ratio to connect the illuminantion images of input and reference and adds a subnet called restoration-net to achieve denoising.However, during the test,it need to manually adjust the ratio parameter to obtain better enhancement results.Although these methods use real low light data for training, they do not constrain the contrast of the enhanced image，which caused the problem of over-enhancement (saturation) or under-enhancement in the enhanced image.

In our previous work [6], we provide a max entropy Retinex model to achieve self-supervised learning and at the same time constrain the contrast during training.However, due to the lack of strong constrains on color and noise, the enhanced image still looks like a night one in color and the noise cannot be removed well,and during test, we cannot guarantee the well contrast on every local area.

Xiong et al. [7] decompose the low light image enhancement task into two stages: contrast enhancement and noise removal, and propose an unsupervised framework.However,in the absence of constraints on the image contrast, the contrast and brightness after image enhancement may be still unsatisfactory, and in this paper we also prove that the Retinex model used in their first stage cannot ensure the color information close to the real day image.

Although these deep learning based methods have achieved good visual effects in low light image enhancement,they still cannot solve the low contrast,low brightness, noise and color distortion simultaneously.

# 3 METHOD

# 3.1Relationship between HSV color space and Retinex model

Recently,a lot of low-light image enhancement works are based on the following Retinex model:

$$
\mathbf { F } = \mathbf { R } \circ \mathbf { I }
$$

where $\mathbf { F }$ and I represent the captured image and the illumination image respectively, $\mathbf { R }$ represents the reflection or the desired image,o represents the element-wise multiplication. Most of the works assume that the three color channels of the image have the same illumination in order to simplify the model [4],[5],and the maximum value of the three color channels is generally used as the initial estimate of the illumination map [3]. In the following description,we referto this simplified Retinex model as the Retinex model. Through a simple transformation,it can be proven that image enhancement methods based on this simplified Retinex model are equivalent to make enhancement operation on V channel in HSV color space and remain the H and S channels unchanged.

The color image can be divided into three channels according to the value of each pixel in RGB color space:

$$
\left\{ \begin{array} { l l } { \displaystyle \mathbf { L } \left( x \right) = \underset { c \in \{ R , G , B \} } { \operatorname* { m a x } } \mathbf { F } ^ { c } \left( x \right) } \\ { \displaystyle \mathbf { M } \left( x \right) = \underset { c \in \{ R , G , B \} } { m e d i a n } \mathbf { F } ^ { c } \left( x \right) } \\ { \displaystyle \mathbf { N } \left( x \right) = \underset { c \in \{ R , G , B \} } { \operatorname* { m i n } } \mathbf { F } ^ { c } \left( x \right) } \end{array} \right.
$$

where $x$ represents an individual pixel. Before the process of image enhancement, the captured image $\mathbf { F }$ in HSV color space canbeexpressedas follows:

$$
\mathbf { V } _ { b } \left( x \right) = \mathbf { L } \left( x \right)
$$

$$
\mathbf { S } _ { b } \left( x \right) = \frac { \mathbf { L } \left( x \right) - \mathbf { N } \left( x \right) } { \mathbf { L } \left( x \right) }
$$

$$
\mathbf { H } _ { b } \left( x \right) = c _ { 1 } + c _ { 2 } \frac { \mathbf { M } \left( x \right) - \mathbf { N } \left( x \right) } { \mathbf { L } \left( x \right) - \mathbf { N } \left( x \right) }
$$

where $c _ { 1 }$ can be 60,120,240, $c _ { 2 }$ can be $\pm 6 0$ ，their values depend on the three color channels of the image,and for one image, $c _ { 1 }$ and $c _ { 2 }$ are certain value in each pixel. $\mathbf { V } _ { b } ,$ $\mathbf { S } _ { b } , \mathbf { H } _ { b }$ represent the V, S and $\mathrm { ~ H ~ }$ channel of the low light image before enhancement,respectively,and the subscript $b$ represents before.

Based on the Retinexmodel, the desired image $\mathbf { R }$ can be obtained by the following formula:

$$
\mathbf { R } \left( x \right) = \mathbf { F } \left( x \right) / \left( \mathbf { I } \left( x \right) + \varepsilon \right)
$$

where $\varepsilon$ isa very small constant to avoid the zero denominator. For simplicity of writing,we omit $\varepsilon$ in the following formula and directly use $\mathbf { I } \left( x \right)$ to represent $\mathbf { I } \left( x \right) + \varepsilon$

According to Equation (6),the enhanced image $\mathbf { R }$ in HSV color space can be expressed as follows:

$$
\mathbf { V } _ { a } \left( x \right) = \mathbf { L } \left( x \right) / \mathbf { I } \left( x \right) = \mathbf { V } \left( x \right) _ { b e f o r e } / \mathbf { I } \left( x \right)
$$

$$
\mathbf { S } _ { a } \left( x \right) = \frac { \mathbf { L } \left( x \right) / \mathbf { I } \left( x \right) - \mathbf { N } \left( x \right) / I \left( x \right) } { \mathbf { L } \left( x \right) / \mathbf { I } \left( x \right) } = \mathbf { S } _ { b } \left( x \right)
$$

$$
\mathbf { H } _ { a } \left( x \right) = c _ { 1 } + c _ { 2 } \frac { \mathbf { M } \left( x \right) / \mathbf { I } \left( x \right) - \mathbf { N } \left( x \right) / \mathbf { I } \left( x \right) } { \mathbf { L } \left( x \right) / \mathbf { I } \left( x \right) - \mathbf { N } \left( x \right) / \mathbf { I } \left( x \right) } = \mathbf { H } _ { b } \left( x \right)
$$

where ${ \mathbf V } _ { a } , { \mathbf S } _ { a } , { \mathbf H } _ { a }$ represent the $\mathrm { v } , \mathrm { s }$ and $\mathrm { ~ H ~ }$ channel of the low light image after enhancement, respectively,and the subscript $a$ represents after.

It can be seen that $\mathrm { ~ H ~ }$ and S channels of the captured image and the enhanced image are the same,and the enhancement operation only works on the $\mathrm { v }$ channel, then the enhanced $\mathrm { \Delta V }$ channel can well represent the image enhancement operation for methods based on HSV or Retinex model.Itisobvious thatthehueandsaturationaredifferent between the image at night and day,also differentbetween the low light and high light images. This is caused by the non-linearity of camera response curve,and even different color channel have different response curve，so methods based on the simplified Retinex model cannot ensure that the color of the enhanced images looks like a real image captured at day or high light.

Therefore,we provide a supervised image enhancement method called the Conditional Re-Enhancement Network (CRNet)which takes the enhanced V channel as an additional point-wise parameter to allow the network focus on learning the Hand S channels which change with V channel. At the same time,with the enhancedVchannel as additional parameter, we can benefit from previous researches [3], [6], [8] on image contrast and brightness enhancement,and the supervised learning also shows well performance in noise suppression.In this way, we can simultaneously solve the problems of low contrast,low brightness,noise,and color distortion in low light images.

Next, we provide the details of the network and training and further explain the reason and rationality of using the V channel instead of a single parameter.

# 3.2 Conditional re-enhancementnetwork

According to the camera response curve,a pixel on the input and reference image can be expressed as follows:

$$
\left\{ \begin{array} { l l } { \mathbf { X } _ { c i j } = G _ { c } \left( \mathbf { E } _ { i } \Delta t _ { j } \right) } \\ { \mathbf { Y } _ { c i k } = G _ { c } \left( \mathbf { E } _ { i } \Delta t _ { k } \right) } \end{array} \right.
$$

where $\mathbf { X }$ and $\mathbf { Y }$ represent the input low light image and the reference image respectively, $c$ represents one of the color channels, $G _ { c }$ represents the camera response curve of $c$ channel, $i$ represents the pixel, $\Delta t _ { j }$ and $\Delta t _ { k }$ represent the exposure time of low light image and high light image respectively, $\mathbf { E } _ { i }$ represents the irradiance.Obviously, different reference images may have different exposure times for better visual effects, therefore most supervised works shouldincludeatleast one time-relateditem $\alpha$ in order to connect the input and reference image.

![](images/4364854bba4561677ac3588399825e5c24a70b2cc7a0f0a3f24a623b81281a92.jpg)  
Fig.3.RGB values of one pixel under different exposures.

TABLE1 Conditional re-enhancement network structure   

<html><body><table><tr><td>Inputs</td><td>Operator</td><td>Kernel</td><td>Output Channels</td><td>Stride</td><td>Output Name</td></tr><tr><td>RGB&Enhanced V</td><td>Conv&ReLU</td><td>3×3</td><td>32</td><td>111</td><td>Conv0</td></tr><tr><td>RGB&Enhanced V</td><td>Conv</td><td>9×9</td><td>64</td><td></td><td>Conv</td></tr><tr><td>Conv</td><td>Conv&ReLU</td><td>3×3</td><td>64</td><td></td><td>Conv1</td></tr><tr><td>Conv1</td><td>Conv&ReLU</td><td>3×3</td><td>128</td><td>2</td><td>Conv2</td></tr><tr><td>Conv2</td><td>Conv&ReLU</td><td>3×3</td><td>128</td><td>1</td><td>Conv3</td></tr><tr><td>Conv3</td><td>Conv&ReLU</td><td>3×3</td><td>64</td><td>2↑</td><td>Conv4</td></tr><tr><td>Conv4&Conv1</td><td>Concat</td><td>-</td><td>128</td><td></td><td>Conv5</td></tr><tr><td>Conv5</td><td>Conv&ReLU</td><td>3×3</td><td>64</td><td>-1</td><td>Conv6</td></tr><tr><td>Conv6&Conv0</td><td>Concat</td><td></td><td>96</td><td>-1</td><td>Conv7</td></tr><tr><td>Conv7</td><td>Conv</td><td>3×3</td><td>64</td><td></td><td>Conv8</td></tr><tr><td>Conv8</td><td>Conv</td><td>3×3</td><td>3</td><td>1</td><td>Conv9</td></tr><tr><td>Conv9</td><td>Sigmoid</td><td>-</td><td>3</td><td></td><td>Enhanced</td></tr></table></body></html>

Then,most of the learning based models can be de scribed as follows:

$$
\operatorname* { m a x } p \left( \theta | f _ { \theta } , \mathbf { Y } , \mathbf { X } , \alpha \right)
$$

where $f$ and $\theta$ represents the enhancement network and parameters in the network respectively,and $p$ represents the probability. $\alpha$ represents the hyperparameter related to the time difference,which is used to connect $\mathbf { X }$ with manually selected $\mathbf { Y }$ ，and previous works adopted time ratio $\alpha =$ $\Delta t _ { k } / \Delta t _ { j }$ [10],average brightness ratio $\alpha = m e a n \left( \mathbf { Y } / \mathbf { X } \right)$ [5],etc.As we mentioned before,there are two obvious problems in previous works.Firstly, it is difficult to assign a value to $\alpha$ automatically during application phase whether it is time or average brightness difference,because those values are not directly related to image contrast. Secondly, a single parameter can only enhance the whole brightness of the image,and can not guarantee a well contrast of the image on every local area. It can be illustrated through the following Equations (12) and (13).

According to Bayes rule,by calculating the negative logarithm of Equation (11),the training phase can be expressed as follows:

$$
\operatorname* { m a x } p \left( \theta | f _ { \theta } , \mathbf { Y } , \mathbf { X } , \alpha \left( \mathbf { X } , \mathbf { Y } \right) \right) = \operatorname* { m i n } _ { \theta } \left| | f _ { \theta } \left( \mathbf { X } , \alpha \left( \mathbf { X } , \mathbf { Y } \right) \right) - \mathbf { Y } | | \right.
$$

If we assume that $\mathbf { Y }$ is the optimal reference in a series of images with different exposure time and we can manually

select $\alpha ,$ ，the best result during testing without other prior losses can be expressed as follows:

$$
\hat { \mathbf { Y } } = f _ { \theta } \left( \mathbf { X } , \alpha \left( \mathbf { X } , \mathbf { Y } \right) \right) = \mathbf { Y }
$$

where $\hat { \mathbf Y }$ represents the enhanced image.It can be seen that the best result of the network is hard to exceed the manually selected reference $\mathbf { Y }$ . In addition, it is obvious that in many low light scenes,we can never get the optimal image as a ground-truth reference by adjusting the exposure time (e.g.Fig.1 (e)-(f)),which means that we cannot obtain a satisfactory image by only adjusting a single parameter $\alpha$

In fact, without other prior, the end-to-end supervised method cannot solve the problem of low contrast in low light images,or even the problem of low brightness,unless we manually adjust the reference images carefully or use multi images to synthesize reference images. But this will also bring other problems，such as increased time cost, the adjusted image can not guarantee the consistency of brightness (the same low light image patches correspond to different reference images),etc. In order to solve the above problems,we propose the CRENet to explicitly control the contrast and brightness of the enhanced image.The CRENet takes the V channel enhanced by other image contrast enhancement methods as a point-wise condition,and can re-enhance the contrast and brightness of low light image according to the condition.

The $\mathrm { v }$ channel is the max of the three color channels at each pixel, so the $\mathrm { \Delta V }$ channel of the reference image can be expressed with camera response curve as follows:

$$
\mathbf { V } _ { i k } = G _ { V } \left( \mathbf { E } _ { i } \Delta t _ { k } \right)
$$

We make the same reasonable assumption that the function $G$ is monotonically increasing [28]. Therefore, for a fixed pixel $i ,$ there isa certain $\Delta t _ { k }$ with given $\mathbf { V } _ { i k } ,$ which means that $\mathrm { \Delta V }$ channel is enough to connect other two channels between the input and reference during training since the three color channels have the same exposure time.As shown in Fig.3,with the exposure changes, the R,G,B value at one pixell can form a curve in 3D space which is related to the camera response curve. Ourmotivationis to let the network learn the curve,and then with a given V value,it can obtain the values of the other two channels (HSV and RGB are just different color representations,so we directly implement it in the RGB space when designing and training the network). Then, the V channel can be treated as a point-wise parameter that we can achievedifferent levels of enhancement to different areas,and through the Equation (2) to (7),it can be seen that the V channel can well represent the processing results of other contrast enhancement methods.

During training,we can take the $\mathrm { \Delta V }$ channel of the reference images as point-wise parameter $\alpha ,$ ，then it can be expressedas follows:

$$
\alpha = \operatorname* { m a x } _ { c \in \{ R , G , B \} } \mathbf { Y } ^ { c } + \mathbf { n }
$$

1.The data comes from real images taken under 40 different exposure conditions. Under each exposure condition,we collected 80 images and averaged them to reduce the noise.

![](images/9ea4f417110dc5a58e514149abb738481dc1f28e6d26970afb62abab2a9267c1.jpg)  
Fig.4.The structure of our training pipelines.

where n represents the Gaussian noise,it is introduced in order to avoid the identity transformation and at the same time simulate the noise in V channel during testing.

Meanwhile, we can perform brightness mapping on the V channel of low light images according to the reference to get $\alpha ,$ then $\alpha$ can be expressed as follows:

$$
\alpha _ { i } = w \operatorname* { m a x } _ { c \in \{ R , G , B \} } \mathbf { X } _ { i } ^ { c }
$$

where $w$ is the average brightness ratio which is calculated on every local area $\Omega$ around pixel $i ,$ and it can be expressed as follows:

$$
w = \frac { \underset { x \in \Omega ( i ) } { \sum } \mathbf { Y } \left( x \right) } { \underset { x \in \Omega ( i ) } { \sum } \mathbf { X } \left( x \right) }
$$

During testing $, \alpha$ can be expressed as follows:

$$
\alpha = \operatorname* { m a x } _ { c \in \{ R , G , B \} } g \left( \mathbf { X } ^ { c } \right)
$$

where $g$ represents any contrast and brightness enhancement methods in HSV color space or based on Retinex model, such as histogram equalization,LIME [3] and selfsupervised methods[6],etc.

The training procedure is achieved by minimizing the loss between the enhanced image and the supervised image, and the loss can be expressed as follows:

$$
L = | | \hat { \mathbf { Y } } - \mathbf { Y } | | _ { 1 } + \mathrm { S S I M } \left( \hat { \mathbf { Y } } , \mathbf { Y } \right)
$$

where SSIM represents the structural similarity measurement [29].We have also test some other loss functions,such as perceptual loss,color loss expressed by outer product like [7], loss in $\mathrm { ~ H ~ }$ and S channels in HSV space,gradient loss [5],etc.,but the effect of these loss functions on the results is not obvious on LOL dataset,neither in visual effects nor in quantitativemetrics.

Thearchitectureofour CRENetisshownin Table1and the training pipeline is shown in Fig. 4. It should be noted that our method does not have special requirements for the network architecture.The network can be simplified or more carefully designed to reduce running time or further improve processing effect. We have tried complicated network,and it is found that a more complexnetwork structure may bring better visual effects.However, this is not the focus of this paper, so we do not show relevant results in the experiment part.

# 4 EXPERIMENT

# 4.1Implementation Details

The LOL (Low Light) dataset [4] which contains 500 image pairs is used for training and testing, 485 image pairs of the database are used for training and images size is $4 0 0 \times 6 0 0$ During the training process, the batch size is set to 48 and the patch size is set to $4 8 x 4 8$ ，We use Adam stochastic optimization [31] to train the network and the update rate is set to O.0o1. The training and testing of the network are implemented ona Nvidia GTX 2080Ti GPU and Inter Core i9-990oK CPU，and the code is based on the tensorflow framework.

# 4.2 PerformanceEvaluation

In this part,we show the results of combining with some previous methods,including some methods under the HSV color space,such as LAHE (Local Area Histogram Equalization) and Gamma correction,and some methods based on Retinex model, such as LIME [3],self-supervised image enhancement [6],Retinex-Net [4],KinD [5],etc.Also we compared our method with BM3D in the effect of denoising. Three metrics are adopted for quantitative comparison，which are PSNR,SSIM,and NIQE [32].NIQE is a non-reference image quality assessment method, which can evaluate the naturalness of the image and a lower value indicates better quality.While,PSNR and SSIMare reference image quality assessment methods,which indicate the noise level and the structure similarity between the result and the reference,respectively.Please note that SSIM and PSNRare mainlyused to evaluate structure and noise,but brightness differences will have a serious impact on the evaluation of these metrics.In order to better evaluate the results generated by different methods,we first perform a local brightness mapping on the enhanced image to exclude the influence of brightness differences before using SSIM and PSNR,which is the same as in Equation (l6).And the mapping operation acts on the V channel and keep the H and S channels unchanged.

Table 2 and Fig. 5 show the experiment results on LOL dataset when combined with different image enhancement methods.In Table 2,it can be seen that for most of the existing methods,our method can significantly reduce the noise and improve the structure similarity,and make the result more natural. And as shown in Fig. 5, taking images enhanced by other methods as condition, the CRENet can keep similar contrast and brightness to those enhanced images,and at the same time the CRENet can reduce the noise and color distortion in those enhanced images. Also, it should be noted that the CRENet does not bring obvious blur in the process of denoising,and even for the LAHE method which produces severe noise,the re-enhancement network can work well (e.g. Fig.5 (b) and (j)). For KinD [5] method,our method does not achieve the effect of improving the PSNR and SSIM,it is because that there has less noise and color distortion on LOL dataset after KinD[5]. However, KinD can be treated as a whole image exposure time adjustment method,it means that it can not ensure a proper contrast orbrightness on everylocal area.As shown in Fig.6,we have tried different ratio,such as 5 and 8, and the author suggested that the maximum is 5.It can be seen that the lower right corner area of the image cannot be enhanced well even we change the ratio.As a matter of fact, we even tried the case when the ratio parameter is 100 in the experiment, but still cannot get good results.

TABLE 2 Quantitative comparison onLOL dataset in terms of NIQE,PSNR,and SSIM. Ori shows the results of original method   

<html><body><table><tr><td>Metrics</td><td></td><td>LAHE</td><td>GAMMA</td><td>LIME [3]</td><td>RetinexNet [4]</td><td>KinD [5]</td><td>Self-supervised [6]</td><td>Zero-DCE[30]</td></tr><tr><td rowspan="4">NIQE</td><td>ori</td><td>13.51</td><td>10.36</td><td>9.13</td><td>9.73</td><td>3.89</td><td>3.72</td><td>8.22</td></tr><tr><td>BM3D</td><td>8.50</td><td>4.08</td><td>4.03</td><td>4.61</td><td>4.06</td><td>4.15</td><td>4.10</td></tr><tr><td>ours</td><td>3.75</td><td>3.68</td><td>3.63</td><td>3.68</td><td>3.60</td><td>3.63</td><td>3.50</td></tr><tr><td>ori</td><td>12.88</td><td>21.95</td><td>21.06</td><td>21.63</td><td>25.82</td><td>24.37</td><td>21.68</td></tr><tr><td rowspan="3">PSNR</td><td>BM3D</td><td>15.35</td><td>21.99</td><td>22.22</td><td>22.41</td><td>25.69</td><td>24.64</td><td>22.65</td></tr><tr><td>ours</td><td>24.92</td><td>24.83</td><td>24.48</td><td>24.81</td><td>25.43</td><td>24.76</td><td>25.11</td></tr><tr><td>ori</td><td>0.32</td><td>0.62</td><td>0.60</td><td>0.61</td><td>0.84</td><td>0.75</td><td>0.62</td></tr><tr><td rowspan="2">SSIM</td><td>BM3D</td><td>0.41</td><td>0.61</td><td>0.64</td><td>0.64</td><td>0.83</td><td>0.76</td><td>0.64</td></tr><tr><td>ours</td><td>0.80</td><td>0.80</td><td>0.80</td><td>0.80</td><td>0.83</td><td>0.80</td><td>0.82</td></tr></table></body></html>

![](images/7a482d66e5c0a4509d6d1caaa7941119ad057ab92141d33f5a683f813c4c24b0.jpg)  
Fig.5.Teresultsenhancedbysomemethodsandre-enhancedbyourmethod.(a)Orginal.(b)-(h）areLAHE,GammacorectionE [3],Retinexet[i]fdspcielyfe.(ed corresponding to (b)-(h).

Also,we study the influence of different source of $\alpha$ on training, the source of which are from the reference image with noise, the low light image after mapping, and the mixture of the two.The results are shown in Table 3 and Fig.7.It can be seen that,when the condition $\alpha$ is from the mixture of the low light and high light images, the network show better results on the evaluation metrics.In Fig.7,it can be found that when the $\alpha$ comes from the reference,there are still some low frequency noise and impulse noise,such as Fig.7 (b).However, if the $\alpha$ comes from the low light images with brightness mapping operation, there are less noise. This is because we only add Gaussian noise to the reference images in the process of obtaining $\alpha ,$ which cannot simulate the real noise in test process very well. In fact, it also shows that the real low light image contains far more complex noise than Gaussian noise,which means that it is hard to obtain promising results in real low light image enhancement tasks with only synthetic low light images. Training with the real data will also bring some problems in previous works, such as the need of adjusting parameters during test and carefully selecting reference during training，and enhanced results are difficult to exceed the reference,however, the proposed method can well solve those problems.

TABLE3 The influence of different $\alpha$ during training on the evaluation metrics   

<html><body><table><tr><td>α</td><td>NIQE</td><td>PSNR</td><td>SSIM</td></tr><tr><td>Reference+Nosie</td><td>4.37</td><td>23.55</td><td>0.774</td></tr><tr><td>Lowlight+Mappping</td><td>3.83</td><td>24.83</td><td>0.821</td></tr><tr><td>Mixture</td><td>3.72</td><td>24.96</td><td>0.823</td></tr></table></body></html>

![](images/366e5eb80c68e3661cbd68c9d5a2f1f16a32e5145826270ca50e2cc71ac2d691.jpg)  
Fig.6.Visual Comparison with single hyperparameter based method. (a) Original. (b) KinD [5] with ratio 5.(c) KinD[5] with ratio 8.(d) Gamma correction with our method.(Best viewed on high-resolution displays with zoom-in.)

We also tested the consistency of the output results when the input images are the same scene with different brightness,as shown in Fig.8.It can be seen that the enhanced results basically maintain the consistency of the brightness of the same blocks.

![](images/f53fa6c529dbff7de92cae52e77ab2fd0923c6db25432459945532a07cb24720.jpg)  
Fig.7.Visual comparison of different source of $\alpha$ during training.(Best viewed on high-resolution displays with zoom-in.)

![](images/e8d4815ba1f06867f5a3423d7cb09b08323a40c247574223cd9e4db70cc42213.jpg)  
Fig.8.Brightness consistency test results.Top Row: low light images with different exposure time. Bottom Row: the enhanced results by our method combined with HE.(Best viewed on high-resolution displays with zoom-in.)

# 5 CONCLUSION

In this paper, we propose a conditional re-enhancement network for low-light image enhancement to solve low contrast,low light,noise and color distortion simultaneously. The network can be combined with any contrast enhancement method which is based on HSV color space or simplified Retinex model,and enhanced V channel by other methodsistreatedasconditionstoachievere-enhancement. And the experiment results show the effectiveness and advantages of the method.Also, there is still some shortcomings: the final enhancement result depends on the contrast enhancement method,and the image saturation is reduced in some areas (e.g. Fig.1 (l)). Future research will focus on applying the technology in long-term and night-time localization to eliminate the interference of light on feature extraction and generate corresponding night-time data sets, and using extremely low light images or raw images for training, etc.

# REFERENCES

[1]D.J.Jobson,Z.-u. Rahman,and G.A.Woodell,"A multiscale retinex for bridging the gap between color images and the human observation of scenes," IEEE Transactions on Image processing,vol.6, no. 7,pp. 965-976, 1997.   
[2]R.Kimmel,M.Elad,D.Shaked,R.Keshet,and I.Sobel,“A variational framework for retinex," International Journal of computer vision,vol.52,no.1,pp.7-,203.   
[3]X.Guo, Y. Li,and H. Ling,“Lime: Low-light image enhancement viailluminationmapestimation" IEEETransactions onimage pro cessing, vol. 26,no.2, pp.982-993,2016.   
[4]C.Wei, W. Wang, W. Yang,and J. Liu,"Deep retinex decomposition for low-light enhancement," arXiv preprint arXio:1808.04560, 2018.   
[5] Y. Zhang, J. Zhang, and X. Guo, "Kindling the darkness: A practicallow-light image enhancer," inProceedings ofthe27thACM International Conference on Multimedia,2019,pp.1632-1640.   
[6]Y. Zhang,X.Di,B.Zhangand C.Wang,Self-supervisedimage enhancement network: Training with low light images only" arXiv,pp.arXiv-2002,2020.   
[7] W. Xiong, D.Liu, X.Shen, C. Fang,and J. Luo,“Unsupervised realworld low-light image enhancement with decoupled networks," arXiv preprint arXiv:2005.02818,2020.   
[8]S. M.Pizer,E. P.Amburn,_J.D.Austin, _R.Cromartie, A.Geselowitz, T. Greer, B. ter Haar Romeny, J. B. Zimmerman, and K. Zuiderveld, “Adaptive histogram equalization and its variations,"Computer ision,graphics,and image processing,vol.39, no.3,pp.355-368,1987.   
[9]C.Lee,C.Lee,and C.-S.Kim,"Contrast enhancement based on layered difference representation of 2d histograms," IEEE transactions on image processing,vol.22,no.12,pp.5372-5384,2013.   
[10] C. Chen, Q. Chen, J. ${ \mathrm { X u , } }$ and V. Koltun, "Learning to see in the dark,"in Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition,018,pp.3291-3300.   
[11] K.G.Lore,A.Akintayo,and S. Sarkar, “Llnet: A deep autoencoder approach to natural low-light image enhancement," Pattern Recognition,vol. 61, pp. 650-662, 2015.   
[12] E.D. Pisano, S. Zong, B.M.Hemminger M. DeLuca,R.E. Johnston,K.Muller,M.P.Braeuning,and S.M.Pizer,"Contrast limited adaptive histogram equalization image processing to improve the detection of simulated spiculations in dense mammograms," Journal ofDigitalimaging,vol.11,no.4, p.193,1998.   
[13] Y.-T. Kim, "Contrast enhancement using brightness preserving bihistogram equalization,"IEEE transactions on Consumer Electronics, vol. 43, no. 1, pp. 1-,97.   
[14] Y.Wang, Q. Chen, and B. Zhang,"Image enhancement based on equal area dualistic sub-image histogram equalization method," IEEETra 1999.   
[15] T. Celik and T. Tjahjadi, "Contextual and variational contrast enhancement"c pp. 3431-3441, 2011.   
[16] X.Dong G. Wang, Y. Pang, W. Li, J. Wen,W. Meng, and Y. Lu "Fast efficient algorithm for enhancement of low lighting video," in 2011 IEEEInternational Conferenceon Multimediaand Expo. IEEE, 2011, pp.1-6.   
[17] L Li, R. Wang, W. Wang,and W.Gao,"A low-light image enhancement method for both denoising and contrast enlarging," in 2015IEEE International Conferenceon ImageProcessing (ICIP).IEEE, 2015, pp.3730-3734.   
[18] S. Wang, J. Zheng, H.-M. Hu, and B. Li, "Naturalness preserved enhancement algorithm for non-uniform illumination images," IEEE TransaciosonImgerocessing,ol.22no.9,.548, 2013.   
[19] X. Fu,D. Zeng, Y. Huang, Y. Liao, X. Ding,and J. Paisley, "A fusion-based enhancing method for weakly illuminated images," Signal Processing, vol. 129,pp.82-96,2016.   
[20] X.Fu, D. Zeng, Y. Huang, X. Ding, and X.-P. Zhang, “A variational framework for single low light image enhancement using bright channel prior,"in 2013 IEEE Global Conference on Signal and Information Processing.IEEE,213,pp.108-18.   
[21] S. Park, S. Yu, B. Moon, S.Ko,and J. Paik,"Low-light image enhancement using variational optimization-based retinex model," IEEE Transactions on Consumer Electronics,vol.63,no.2,pp.178- 184, 2017.   
[22]G.Fu,L.Duan,and C.Xiao,"A hybrid l2-lp variational model for single low-light image enhancement with bright channel prior,"in 2019 IEEE International Conference on Image Processing (ICIP).IEEE, 2019,pp.1925-1929.   
[23]K.Dabov,A.Foi,V.Katkovnik,andK.Egiazarian,"Image denoisingby sparse 3-d transform-domaincollaborative filtering,"IEEE Transactions on image processing,vol.16,no.8,pp.2080-2095,2007.   
[24] C.Li, J.Guo,F.Porikli,and Y. Pang,"Lightennet: A convolutional neural network for weakly illuminated image enhancement,"Pattern Recognition Letters,vol.104,pp.15-22,2018.   
[25]J.Yang,X. Jiang,C.Pan,and C.-L.Liu,“Enhancement of low light level images with coupled dictionary learning,"in 2016 23rd International Conference onPattern Recognition (ICPR).IEEE,2016, pp.751-756.   
[26] L. Shen,Z. Yue,F.Feng, Q.Chen,S.Liu,and J.Ma,"Msr-net: Lowlight image enhancement using deep convolutional network," arXiv preprint arXio:1711.02488,2017.   
[27] Q.Fu,X. Di,and Y. Zhang,“Learning an adaptive model for extreme low-light raw image processing,"arXivpreprint arXio:2004.10447,2020.   
[28] P.E. Debevec and J.Malik,"Recovering high dynamic range radiance maps from photographs,"in ACMSIGGRAPH 2008 classes, 2008, pp.1-10.   
[29] Z. Wang, A. C. Bovik, H. R. Sheikh,and E.P. Simoncelli, "Image quality assessment: from error visibility to structural similarity, IEEE transactions on image processing,vol.13,no.4,pp.600-612, 2004.   
[30] C. Guo, C. Li, J. Guo, C. C. Loy, J. Hou, S. Kwong,and R. Cong, "Zero-reference deep curve estimation for low-light image enhancement,"inProceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition,2020,pp.1780-1789.   
[31]D.P.Kingma and J. Ba,“Adam: A method for stochastic optimization," arXio preprint arXiv:1412.6980,2014.   
[32]A.Mittal,R.Soundararajan,and A.C.Bovik,“Makinga “completelyblind"imagequalityanalyzer," IEEE Signal Processing Letters,vol.20,no.3,pp.209-212,2012.

![](images/9f376e434f77d531065bcfc5452e7ea4f443c94979e46f05c350d1ba0ae96f30.jpg)

Yu Zhang was born in Hebei, China. He received the B.E.degree and M.S.degree in Control Science and Engineering from Harbin Institute of Technology,China，in 2016 and 2018, respectively.He is currently studying fora Ph.D degree in Electronic science and technology in National Key laboratoryofTunable LaserTechnology, Harbin Institute of Technology.His research interests include image restoration and enhancement, SLAM.

![](images/4cd912e8965d07ca04dfdfd4fa04041dacb58a632624a33e6507aec325ebf150.jpg)

Xiaoguang Di was born in Heilongjiang,China. Hereceived the M.S.and Ph.D degree in navigation，guidance and control from Northwestern Polytechnical University, China,in 1999 and 2004,respectively.He is currently an associate professor with the Control and Simulation Center,Harbin Institute of Technology,Where he is in charge of courses in digital image processing and computer vision.His current research interests include real-time image restoration and enhancement, 3D object detection and recognition,

SLAM.Prof. Di is a member of China Simulation Federation and Chinese Society of Astronautics.

![](images/8251b181085ddea898ba4ec6c2248eae9dda5e7045c986b432623625e702e9e1.jpg)

Bin Zhang was born in Gansu, China. He received the B.Sc.degree inapply physicsand the M.Sc.degree in physics from China University of Petroleum,in 2010 and 2013,respectively. He is currently studying fora PhD degree in National Key Laboratory of_Tunable Laser Technology, Harbin Institute of Technology. His research interests include laser imaging and laser transmission.

![](images/f9005976d858c6e5d1f393a9bdd06e44a17536dbefbf24d9e7cddb9f2df3fd06.jpg)

Ruihang Ji (S'16) received the B.S.degree in automation engineering from the Harbin Institute of Technology, Harbin,China,in 2016,where he is currently pursuing the Ph.D.degree in control science and engineering.

He is currently an exchange Ph.D. student supported by the China Scholarship Council with the Department of Electrical and Computer Engineering，National University of Singapore,Singapore.His current research interests include adaptive control, robust control, Unmanned Aerial Vehicleand computer vision.

![](images/75d08bafe409df815a607973b5b67fb27ba0093570c9e0ea353274a8da7c5d6a.jpg)

Chunhui Wang Chunhui Wang received the BS, MS,and PhD degrees from Harbin Institute of Technology in 1987，1991，and 2005,respectively.He is currentlya processor and Deputy Director,Institute of Optoelectronic Technology, Harbin Institute of Technology. His current major research interests are laser remote sensing, lidar, laser detection and recognition.