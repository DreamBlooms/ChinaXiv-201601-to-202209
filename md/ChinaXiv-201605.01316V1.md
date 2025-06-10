Research Article

# Detection of Dendritic Spines Using Wavelet-Based Conditional Symmetric Analysis and Regularized Morphological Shared-Weight Neural Networks

Shuihua Wang2 MengmengChen,34,5 YangLi,' YudongZhang2,6   
Liangxiu Han,′ Jane Wu,34 and Sidan Du1

1Department of Electronic Engineering, Nanjing University, Nanjing 2l0024, China   
2School ofComputer Scienceand Technology Nanjing Normal University Nanjing 2l023,China   
3State KeyLboatoryofridogniveienceItiuteofoicsnsecadeofencseina   
4DepartmentofNeurologyLurieCancer Center,CenterforGeneticMedicine,Northwestern UniversitySchoolofMedicine,   
Chicago,IL 606ll,USA   
5Universityof Chinese AcademyofSciences,Beijing 10oo1,China   
Translational Imaging Division,Columbia University,New York,NY32,UA   
7School ofComputing,athematicsandDigital Technologanchesteretropolitan Universityanchester MD,UK

Correspondence should be addressed to Sidan Du; coffl28@nju.edu.cn

Received 17 June 2015; Revised 2 September 2015;Accepted 27 September 2015

AcademicEditor:ValeriMakarov

Copyright $\odot 2 0 1 5$ Shuihua Wang et al.This is an open accessarticle distributed under the Creative Commons Atribution License, which permits unrestricteduse,distribution,and reproduction inanymedium,provided theoriginal work is properlycited.

Identificationanddetectionofdendriticspines inneuronimagesareofhigh interestindiagnosisandtreatmentofneurological andpsychiatricdisorders(.g,lzheimersdisease,arkinson'sdiseases,andautism).Inthispaperwehaveproposedaovel automatic approach using wavelet-based conditional symmetricanalysis andregularized morphological shared-weight neural networks(RMSNN)fordendritic spineidentificationinvolving thefollowing steps:backbone extraction,localizationofdendritic spines,andclasification.First,anealgoritmbasedonwavelettransformandondtionalsymmetricanalysishasbeendeveloped to extractbackbone and locate the dendrite boundary.Then,the RMSNNhas been proposed toclasify the spines into three predefined categories (mushroom,thin,and stubby).We have comparedour proposed aproachagainst the existing methods. Theexperimental result demonstrates that theproposedapproachcanaccuratelylocate thedendriteandaccuratelyclassifythe spines into three categories with the accuracy of $9 9 . 1 \%$ for“mushroom” spines, $9 7 . 6 \%$ for“stubby” spines,and $9 8 . 6 \%$ for“thin” spines.

# 1. Introduction

Dendritic spines are small “doorknob”shaped extensions from neuron's dendrites,which can number thousands to a single neuron. Spines are typically classified into three types based on the shape information:mushroom,stubby, and thin.“Mushroom” spine has a bulbous head with a thin neck;“stubby”spine only has a bulbous head;“thin” spine has a long thin neck with a small head.Research has shown that the changes in shape,length,and size of dendritic spines are closely linked with neurological and psychiatric disorders,such as attention-deficit hyperactivity disorder (ADHD),autism,intellectual disability,Alzheimer's disease, and Parkinson's disease [1-5]. Therefore, the morphology analysis and identification of structure of dendritic spines are critical for diagnosis and further treatment of these diseases [6,7].

Traditional manual detection approach of dendritic spines detection is costly and time consuming and prone to errordue to human subjectiveness.With the recent advances in biomedical imaging,computer-aided semiautomatic or automatic approaches to detect dendritic spines based on image analysis have shown the efficacy. SynD method proposed by Schmitz et al.[8] is a semiautomatic image analysis routine to analyze dendrite and synapse characteristics in immune-fluorescence images.For the fluorescence imaging,the neurite and soma were captured in the separated imaging channels. In that case, soma and synapse were detected without intervention from neurite [9-ll] based on the channel information.However, this method cannot be extended to the images,of which the information is captured in the same channel. Therefore,many other methods were proposed to solve this problem,for instance,ImageJ [12],NeuronStudio [13], NeuronJ [14],and NeuronIQ[15]. However, these methods have some limitations. For example,NeuronIQ was designed for the confocal multiphoton laser scanning. NeuronJ was used to trace the dendrite growing in the condition of manually marking the dendrite first.Koh et al. detected spines from stacks of image data obtained by laser scanning microscopy [16]. The algorithm first extracted the dendrite backbone defined as the medial axis and then geometric information was employed to detect the attached and detached spines according to the shape of each candidate spine region. Features including spine length, volume, density,and shape for static and time-lapse images of hippocampal pyramidal neurons were used as key points for the detection. The disadvantage of this method is that it might lose many spines during the detection because of the thresholding method used in this case.To overcome this problem, Xu et al. proposed a new detection algorithm for the attached spines from the dendrites by two grassfire steps [17]: a global threshold was chosen to segment the image and then the medial axis transform (MAT) was applied to find the centerlines of the dendrites. Then some large spines (noncenterlines) were removed from the centerlines. After the backbone was extracted, two grassfire procedures were applied to separate the spine and dendrite.The results of the proposed method were similar to the results of the manual method. Cheng et al. proposed a method using an adaptive threshold based on the local contrast to determine the foreground,containing the spine and dendrite,and detect attached and detached spines [18]. Fan et al. used the curvilinear structure detector to find the medial axis of the dendrite backbone and spines attached to the backbone [19]. To locate the boundary of dendrite,an adaptive local binary fitting (aLBF) energy level set model was_proposed for localization. Zhang et al. extracted the boundaries and the centerlines of the dendrite by estimating the second-order directional derivatives for both the dendritic backbones and spines [2o]. Then a classifier based on Linear Discriminate Analysis (LDA） was built to classfy the attached spines into true and false types. The accuracy of the algorithm was_calculated according to the backbone length, spine number, spine length,and spine density. Janoos et al. used the medial geodesic to extract the centerlines of the dendritic backbone [21].He etal. proposed a method based on NDE to classify the dendrite and spines [22]. The principle of their method was that spine and dendrite had different shrink rates. Shi et al. proposed a wavelet-based supervised method for_classifying 3D dendritic spines from neuron images [231.

Existing work is encouraging. However, the problems remain on how to improve accuracy (e.g.,accurate extraction of backbone,accurate detection of attached and detached spines).Different from existing approaches,in this paper, we have proposed new algorithms for efficient detection of dendritic spines using wavelet-based conditional symmetric analysis and regularized morphological shared-weight neural network. Our contributions include the following:

(1)A new extraction model for dendrite backbone and its boundary localization using wavelet-based conditional symmetric analysis and pixel intensity difference,which can allow accurate extraction of backbone,the first important step for dendritic spines.   
(2)A new way for spine detection based on regularized morphological shared-weight neural networks (RMSNN） to efficiently detect spines and classify them into right categories,that is,mushroom, thin, and stubby.

The rest of this paper is organized as follows. Section 2 describes the proposed methods including wavelet-based conditional symmetry analysis and pixel intensity difference for the dendrite detection and localization and regularized shared-weight neural networks for the spine detection.In Section 3,we have conducted experimental evaluation and demonstrated the effectiveness of the proposed algorithm. Section 4 discusses the results. Section 5 concludes the proposed approach and highlights the future work.

# 2.Methods

Figure 1 shows the steps of our proposed approach to dendritic spines. In the image acquisition phase,we demonstrated the process for the neuron culture,label,and imaging. In the second step, we preprocessed the images by reducing the noise and smoothing the background [24,25]. Then, we extracted the dendrite backbone based on the conditional symmetric analysis and located the dendrite boundary based on the difference of the pixel intensity.Afterwards,the spines were detected,classified,and characterized byRMSNN.

2.1.Image Acquisition. The neurons used for imaging in this paper were cortical neurons,primary cultured from Embryonic l8th-(El8-) day rat and next cultured until the $2 2 \mathrm { n d }$ day in vitro. Then,the neurons were transfected by Lipofectamine 20oO and imaged at the 24th day by Leica SP5 confocal laser scanning microscopy (CLSM) by $6 3 \mathrm { x }$ The size of the image is $1 0 2 4 \times 1 0 2 4$ ，and the resolution is $0 . 2 4 \mathrm { u m } ,$ /pixel at the confocal layer. The images used for the morphology analysis were obtained by the maximum intensity projection (MIP) of the original 3D image stack.As the images were captured as Z-stack series,we projected the 3D image stack onto the xy, $y z$ ,and $z x$ planes, respectively. Since the slices along the optical direction $( z )$ provided very limited information and the computation time based on the 3D image stacks is highly increased,it was desired to consider only the 2D projection onto the $x y$ plane. The 2D image used for analysis was a maximum intensity projection of the original 3D stack. It was obtained by projecting in the xy plane the voxels with maximum intensity values that fall in the way of parallel rays traced from the viewpoint to the plane of projection.

![](images/98c03fe026db521326aae15bed5b7e6589761788e883f6eee036575a5843ad99.jpg)  
FIGURE 1: Flowchart of the proposed detection method of the dendritic spines.   
FIGURE 2: Samples of the subimages used in the image library.

Werandomly selected15different images fromLeica SP5 confocal laser scanning microscopy to form the spines library to test our algorithm.All images contain distinct spines including mushroom, stubby, and thin types.The typical size of the image is $1 0 2 4 \times 1 0 2 4$ .Most spines in the images are within a rectangle of $2 0 \times 2 0$ in pixel, but the“thin” spine is within an about $5 \times 2 0$ rectangle in pixel. The spines have variable gray-level intensities. Spines collected from the image library were employed to build an image base library. Spine subimages in the library were taken as samples to test the classification accuracy ofRMSNN.In order to cover as many cases as possible,the image base library contains distinct sizes and spines with different orientations.

In order to build the golden-standard spine library, five experts in the neuroscience field were employed to manually mark the spines in the collected images and classify the spines into three predefined categories including“mushroom,” "stubby,”and “thin” types.For the conflict of the manual marking, the minority was supposed to be subordinated to the major. Then according to the marked spines,we computed the maximum width, length,area,and the center point. The randomly selected image base library contains about 2700 subimage samples,9oo for each type of spines.Figure 2 shows some image samples in our image base library.As we can see from the image sample,spines of“mushroom" type contain a thin neck and head,the stubby type connects directly with the dendrite without neck,and the thin type is with the smallest size with only a thin neck and without head.

2.2. Image Preprocessing. Considering the limitation of imaging technique,we have employed the 2D median filter to deal with the noise introduced by the imaging mechanism of the photomultiplier tubes (PMT) and then used the partial

（MA(a)Mushroom(b) Stubby  
1(c)Thin

differential equation (PDE) proposed by Wang et al. [26] to enhance the image.Figure 3 shows an example of the original image and the preprocessed result.

2.3.Backbone Extraction Using the Wavelet Transforma tionBased Conditional SymmetricAnalysis.Considering the attached spines,itis necessaryto firstlylocate the dendrites in order to segment the spines from the dendrite.The backbone extractionand boundarylocalization are critical fordendritic spine classfication and analysis,which include the following steps.

Step 1. Remove the noise and small isolated point-set.

Step2.Locate the backbone of the dendrite.

Step3.Locate the boundary of the dendrite

The backbone is defined as the thinning of the dendrite. Due to the variance of width of dendrite,attached and detached spines,it is achallenging task to locate the boundary of the dendrite directly from the preprocessed images.Therefore,we have developed a new extraction model utilizing wavelet transform based conditional symmetric analysis.The essence of this model is to conduct a local conditional symmetry analysis of the contour of the region of interest (ROI)and then compute the center points to produce the backbone of the dendrite.

![](images/eb0992b40d0e1946327866474fdc73e37b546958706b67db0b985fb6ebf3000d.jpg)  
FIGURE 3:An example of preprocessed image.

Due to the complexity of the dendrites and dendrite spines'distribution,we have employed morphological operation to remove the small isolated point-set for the dendrite in the binary image obtained by local Otsu [27-29] via (1), which could decrease the disconnection rate of the dendrite detection:

stands for the partial derivative of $y$ ,respectively. $\theta ( x , y )$ is a low pass filter.

For $\varphi _ { x } ( x , y )$ and $\varphi _ { y } ( x , y )$ ,the scale wavelet transform (WT) could be written as the following equations:

$$
\begin{array} { c } { { W _ { x , s } f \left( x , y \right) = \left( f \ast \varphi _ { x , s } \right) \left( x , y \right) = s \displaystyle \frac { \partial } { \partial x } \left( f \ast \theta _ { s } \right) \left( x , y \right) , } } \\ { { { } } } \\ { { W _ { y , s } f \left( x , y \right) = \left( f \ast \varphi _ { y , s } \right) \left( x , y \right) } } \\ { { { } } } \\ { { { } = s \displaystyle \frac { \partial } { \partial y } \left( f \ast \theta _ { s } \right) \left( x , y \right) . } } \end{array}
$$

Here, $\theta _ { s } = ( 1 / s ^ { 2 } ) \theta ( x / s , y / s )$ .We can get the modulus of the gradient vector as

in which $n$ is the threshold of the number of positive pixels. The value of $n$ could be determined by trial and error method and means that the pixel belongs to the major line if there are more than $n$ positive pixels in its $3 \times 3$ neighborhood window. Otherwise, the value of the pixel is forced to be O,treated as the small isolated point-set. The determination of the centerline of the dendrite is based on the conditional symmetric analysis.

The symmetric analysis was accomplished via the wavelet transform.We have applied the wavelet transform to detect a pair of contour curves:

$$
\begin{array} { l } { \displaystyle \varphi _ { x } \left( x , y \right) = \frac { \partial } { \partial x } \theta \left( x , y \right) = \phi ^ { \prime } \left( \sqrt { x ^ { 2 } + y ^ { 2 } } \right) \frac { x } { \sqrt { x ^ { 2 } + y ^ { 2 } } } , } \\ { \displaystyle \varphi _ { y } \left( x , y \right) = \frac { \partial } { \partial y } \theta \left( x , y \right) = \phi ^ { \prime } \left( \sqrt { x ^ { 2 } + y ^ { 2 } } \right) \frac { y } { \sqrt { x ^ { 2 } + y ^ { 2 } } } , } \end{array}
$$

in which $x$ and $y$ stand for the coordinate of the contour curve. $\varphi _ { x } ( x , y )$ means the partial derivative of $x$ and $\varphi _ { y } ( x , y )$

$$
\nabla W _ { s } f \left( x , y \right) = \left( \begin{array} { l } { W _ { x , s } f \left( x , y \right) } \\ { W _ { y , s } f \left( x , y \right) } \end{array} \right) ,
$$

$$
\left| \nabla W _ { s } f \left( x , y \right) \right| = \sqrt { \left| W _ { x , s } f \left( x , y \right) \right| ^ { 2 } + \left| W _ { y , s } f \left( x , y \right) \right| ^ { 2 } } ,
$$

$$
A _ { s } f \left( x , y \right) = \arctan \left( \frac { W _ { y , s } f \left( x , y \right) } { W _ { x , s } f \left( x , y \right) } \right) ,
$$

where $\nabla$ is the gradient vector and the gradient direction is given as (6). The contour points $( x , y )$ are the local maxima of $| \nabla W _ { s } f ( x , y ) |$ in the direction of $A _ { s } f ( x , y )$ at scale s.However, the local maxima modulus is not the exact edge point.

We selected (7) as the basis function. We set $\varphi ^ { - } ( x ) \ =$ $- \varphi ^ { + } ( - x )$ and had $\varphi ( x ) = \varphi ^ { + } ( x ) + \varphi ^ { - } ( x )$ as the wavelet function,which had the following properties: gray invariant, slope invariant,width invariant,and symmetric [29,3o].The advantage is to make the extraction of a pair of contours with accurate protrusions.Consider

φ

$$
\mathbf { \xi } = \left\{ \begin{array} { l l } { \displaystyle \frac { 2 } { \pi } \left( 4 x \ln \frac { \left( 1 - 8 x ^ { 2 } + 2 \sqrt { 1 - 1 6 x ^ { 2 } } \right) \left( 1 + \sqrt { 1 - x ^ { 2 } } \right) } { 9 x - 8 x ^ { 2 } + 3 \sqrt { 9 - 1 6 x ^ { 2 } } } - \frac { 1 } { 2 x } \left( \sqrt { 1 - 1 6 x ^ { 2 } } - 3 \sqrt { 9 - 1 6 x ^ { 2 } } + 8 \sqrt { 1 - x ^ { 2 } } \right) \right) , } & \\ { \displaystyle = \left\{ \begin{array} { l l } { \displaystyle \frac { 2 } { \pi } \left( 4 x \ln \frac { 8 x \left( 1 + \sqrt { 1 - x ^ { 2 } } \right) } { 9 + 3 \sqrt { 9 - 1 6 x ^ { 2 } } } - \frac { 1 } { 2 x } \left( 3 \sqrt { 9 - 1 6 x ^ { 2 } } - 8 \sqrt { 1 - x ^ { 2 } } \right) \right) , } & \\ { \displaystyle \frac { 2 } { \pi } \left( 4 x \ln \frac { 1 + \sqrt { 1 - x ^ { 2 } } } { x } - \frac { 4 } { x } \sqrt { 1 - x ^ { 2 } } \right) , } & \\ { \displaystyle 0 , } & \end{array} \right. } \end{array} \right.
$$

The distance between two symmetric points is equal to the scale of the wavelet transform.If the distance between two symmetric points is larger than or equal to the width of regular region,the center point of the symmetric pair can potentially be located outside of the dendrite.The regular region is defined as the dendrite is smooth,where the function has a stable variation along the axis.Thus,we defined the stable symmetry as follows.

If the scale of wavelet transform is larger than or equal to the width of regular region,the modulus maxima points generate two new parallel contours inside the periphery of the dendrite.All the symmetric pairs of the wavelet transforms that do not have a counterpart are defined as the unstable symmetry.In this case,we have considered the width as the constraint condition.In the direction of the perpendicular to the gradient direction,we selected the width nearest to the regular region.

The center of every symmetric pair located on the centerline of the original regular region of the stroke point. Finally, the backbone of the regular region was defined by the curve of all connected symmetric points.

2.4.BoundaryLocationBasedonthePixelIntensityDifference. The morphological operation of removing noise blurred the boundary. Therefore,after localization of backbone, the boundary of the dendrite was detected via varies of the pixel intensity of the preprocessed image from Section 2.2.We can observe that the pixel intensity of the line pixel changes abruptly at the boundary locations.The boundary location was performed in two steps.In the first step,we have searched the image along the two directions perpendicular to the local line direction until the pixel intensity of the line pixel changed sharply. We set a threshold for each pixel. The local line direction is determined as

$$
A _ { s } f \left( x , y \right) = \arctan \left( \frac { W _ { y , s } f \left( x , y \right) } { W _ { x , s } f \left( x , y \right) } \right) .
$$

The formulation of each pixel is given by $( \alpha , I ( \boldsymbol { p } ) )$ ,in which $I ( p )$ is the pixel intensity of point $P$ in the original image and $\alpha$ is a predefined pixel intensity value, that is,

$$
\operatorname { i f } { \left\{ \begin{array} { l l } { I \left( p \right) \geq \alpha , } & { p { \mathrm { ~ b e l o n g s ~ t o ~ t h e ~ l i n e ~ p i x e l } } } \\ { I \left( p \right) < \alpha , } & { p { \mathrm { ~ d o e s ~ n o t ~ b e l o n g ~ t o ~ t h e ~ l i n e ~ p i x e l } } . } \end{array} \right. }
$$

In the second step,some boundary points that were not on the searching path could be missed. The missed boundary points were detected from the neighboring boundary points. Provided that there are two known boundary points,if they are adjacent, there were no other boundary points between them; otherwise, the method proposed by Tang and You [31] was used to find the missed points,which can link the two points into a discrete line with one point as the starting point and the other one as the ending point.

There are several advantages of our proposed algorithms forbackbone detection and boundary location.(1) The first are computing efficiency and noise reduction. Our approach uses less computing time than the method based on the derivatives of the Gaussian kernel and is more robust when dealing with the noise.(2)Meanwhile,it reduces the error rate for misclassifying spine pixels as dendrite pixels and sharply reduces the disconnection rate,which means our approach is more robust when dealing with the disturbance information than other methods,such as NDE proposed by He et al. [22].

2.5.Spine Detection Based on Regularized Morphological Shared-Weight Neural Network (RMSNN). Considering the dendritic spine's structure,we have employed the regularized morphological shared-weight neural networks for the detection and classification of spines. The regularized morphological shared-weight neural networks consist of two-phase heterogeneous neural networks in series as shown in Figure 4: the first phase is for feature extraction and the second phase is for classification.In the first phase,it is accomplished via the gray-scale Hit-Miss transform. The feature extraction phase has multiple feature extraction layers.Each layer is composed of one or more feature maps. Each feature map is generated by the Hit-Miss transform with a pair of structure elements (SEs) from the previous layer and is accompanied by a new pair of SEs,in which one is for the erosion and the other one is for the dilation. In the classification stage, it shows a fully connected Feedforward Neural Network(FNN) [32- 34]. The input of FNN is the direct output of the feature extraction stage. The output of the classification stage is a three-node layer,in which each node stands for one type of spine.Figure 4 shows the structure of the morphological shared-weight neural network (MSNN) [35]. The MSNN has been widely applied in the following research fields, including laser radar (LADAR), forward-looking infrared (FLIR),synthetic aperture radar, and visual spectrum image. The existing research demonstrates that the MSNN is robust for detection with rotation, image intensity translation, and occlusion variables [36]. In this paper, we have proposed to apply the regularized morphological shared-weight neural network to spine classification.

![](images/d4d1f19aa02897697426a6cffa1ca7048b03f706cb62996291c28c3c5f720c2c.jpg)  
FIGURE 4: Structure of morphological shared-weight neural network.

Dilation is defined as

$$
A \oplus B = \left\{ x \mid \left( { \widehat { B } } \right) _ { x } \cap A \neq \varnothing \right\} ,
$$

in which $A$ and $B$ are sets in $Z ^ { 2 }$ and $\widehat { B }$ is the reflection of $B$ $\varnothing$ is the empty set.Equation (lO) is termed the dilation of $A$ by SE $B$ .Dilation is the reflection of $B$ about its origin, then translated by $x _ { i }$ with the set of all $x$ ,whichallow $\widehat { B }$ to intersect $A$ with at least one element.

Erosion is defined as (ll) or (l2)by the duality of the erosion-dilation relationship:

$$
\begin{array} { r l } & { A \ominus B = \left\{ x \mid ( B ) _ { x } \subseteq A \right\} , } \\ & { } \\ & { A \ominus B = \left( A ^ { c } \oplus \widehat { B } \right) ^ { c } , } \end{array}
$$

in which $A ^ { c }$ is defined as the complement of $A$ （204号

Hit-Miss transform is defined as an operation that detects a given pattern ina binary image based on a pair of disjoint structure elements,one for Hit and the other one for Miss. The result of the Hit-Miss transform is a set of positions, where the first SE fits in the foreground of the input image and the second SE misses it completely:

$$
\boldsymbol { A } \otimes \boldsymbol { B } = \left( \boldsymbol { A } \otimes \boldsymbol { X } \right) \cap \left( \boldsymbol { A } ^ { c } \left( \boldsymbol { W } - \boldsymbol { X } \right) \right) ,
$$

in which $X$ is a SE that consisted from set $B , W$ is an enclosing window of $X$ and $( W - X )$ is the local background of $X$ By supposing $X$ as $H$ ,the Hit SE,and $( W - X )$ as $M$ ,theMiss SE,we can get

$$
A \otimes B = ( A \otimes H ) \cap \left( A ^ { c } \ominus M \right) ,
$$

in which $B = ( H , M )$ and it can be written as

$$
A \otimes B = \left( A \ominus H \right) - \left( A ^ { c } \oplus { \widehat { M } } \right) .
$$

As far as the gray scale is concerned, we assume the image function as $I = f ( x , y )$ ,inwhich $f ( x , y )$ was the intensity value of the point $( x , y )$ . Meanwhile,we made the SE $b ( x , y )$ The morphological operation canbe thought of as a 3D binary set by way of the umbra transform.The umbra of a3D surface function is defined as

$$
U \left( f \right) = \left\{ \left( x , y , z \right) \mid \left( x , y \right) \in D _ { f } , \ z \leq f \left( x , y \right) \right\} ,
$$

where we take $D _ { f }$ as the domain of $f$ .Then the gray scale dilationcanbedefinedas

$$
\begin{array} { l } { \left( f \oplus b \right) ( s , t ) = \operatorname* { m a x } \left\{ f \left( s - x , t - y \right) \right. } \\ { \left. \qquad + b \left( x , y \right) \mid \left( s - x \right) , \left( t - y \right) \in D _ { f } ; \left( x , y \right) \in D _ { b } \right\} . } \end{array}
$$

Meanwhile,erosionisdefined as

$$
\begin{array} { l } { \left( f \ominus b \right) ( s , t ) = \operatorname* { m i n } \left\{ f \left( s + x , t + y \right) \right. } \\ { \left. \qquad - b \left( x , y \right) \mid \left( s + x \right) , \left( t + y \right) \in D _ { f } ; \left( x , y \right) \in D _ { b } \right\} . } \end{array}
$$

The gray scale erosion measures the minimum gap between the image values $f$ and the translated SE values over the domain of $x$ .The gray scale dilation is the dual of the erosion and indirectly measures how well the SEs fit above $f$ The Hit-Miss transform measures how a shape $h$ fits under $f$ using erosion and how a shape $m$ fits above $f$ via dilation. The high value of Hit-Miss transform means good fit. The gray scale Hit-Miss transform is independent of shifting in gray scale.

2.5.1.The Feature Extraction Phase. There are four elements associated with each layer of feature extraction phase: feature maps,input,and two structure elements.In the first layer, the subimage is used as input,and the last layer's output is the input of the classification stage.In each feature extraction layer,a pair of Hit-Miss SEs is shared within all the feature maps.These SEs are translated as input weights for the feature map nodes in the feature extraction layer. Table1 shows the input parameters and output parameters related to the feature extraction phase.

According to the above parameters,we can define the HitMiss transform as follows:

$$
\begin{array} { r l } & { \mathrm { \mathrm { n e t } } _ { y } ^ { h } = \displaystyle \operatorname* { m i n } _ { x \in D _ { t _ { y } } } \left\{ a \left( x \right) - t _ { y } ^ { h } \left( x \right) \right\} , } \\ & { \mathrm { \boldsymbol { n } e t } _ { y } ^ { m } = \displaystyle \operatorname* { m a x } _ { x \in D _ { t _ { y } } } \left\{ a \left( x \right) - t _ { y } ^ { \widehat m } \right\} , } \\ & { \quad a _ { y } = \mathrm { \boldsymbol { n } e t } _ { y } ^ { h } - \mathrm { \boldsymbol { n } e t } _ { y } ^ { m } . } \end{array}
$$

Here, $\boldsymbol { \mathrm { n e t } } _ { y } ^ { h }$ stands for the input for Hit operation in node $y$ and $h$ means the Hit operation. $\mathrm { n e t } _ { y } ^ { m }$ means the net input for the Miss operation in node $y . m$ and $\widehat { m }$ here mean the Miss operation and reflection of $m$ ,respectively. $a _ { y }$ is the result of Hit-Miss transform performed at node $y$ .The learning rule for the Hit and Miss SE is derived based on the gradient decent as

TABLE l: Parameters of the feature extraction phase.   

<html><body><table><tr><td>Parameter Definition</td><td></td></tr><tr><td>a(x)</td><td>The input to a node y from node x Connections associating the node y with</td></tr><tr><td>ty(x)</td><td>node x</td></tr><tr><td>Input t（xy）</td><td>Hit SE associating node y with node x</td></tr><tr><td>t（x)</td><td>Miss SE associating node y with x</td></tr><tr><td>w(x）</td><td>Weight for Miss SE nodey with x</td></tr><tr><td>w（x)</td><td>Weight for Hit SE nodey with x</td></tr><tr><td>Output ay</td><td>The output of node y</td></tr></table></body></html>

$$
\begin{array} { c } { { \Delta t _ { y } ^ { h } = \eta \delta _ { y } \displaystyle \frac { \partial \mathrm { n e t } _ { y } ^ { h } } { \partial t _ { y } ^ { h } \left( x \right) } , } } \\ { { \Delta t _ { y } ^ { \widehat m } = - \eta \delta _ { y } \displaystyle \frac { \partial \mathrm { n e t } _ { y } ^ { m } } { \partial t _ { y } ^ { \widehat m } \left( x \right) } , } } \end{array}
$$

where $\eta$ is the learning rate of the network and $\delta _ { y }$ is expressed as

$$
\delta _ { y } = \delta \left( y \right) = \sum _ { k } \delta _ { k } w _ { k } \left( y \right) .
$$

Equation (21) is for the top level or final extraction layer. $\delta _ { y }$ for the lower layers of multiple-layer feature extraction is expressed as

$$
\delta _ { y } = \delta \left( y \right) = \sum { _ { k } \delta _ { k } } \left( \frac { \partial \mathrm { n e t } _ { y } ^ { h } } { \partial a \left( y \right) } - \frac { \partial \mathrm { n e t } _ { y } ^ { m } } { \partial a \left( y \right) } \right) ,
$$

in which $k$ is the node in the layer next to the node $y$

Based on the back-propagation of error from the classification stage with these learning rules,the MSNN learns the optimized SE to extract the features by each set ofHit-Miss transforms.Consider

$$
E = \frac { 1 } { 2 } { \sum _ { o } \left( t _ { o } - O _ { o } \right) ^ { 2 } } .
$$

Here, $t _ { o }$ stands for the target node output and $O _ { o }$ the actual node output:

For the output layer nodes, $\boldsymbol { w } _ { k j }$ stands for the connection strength to node $k$ from node $j$

$$
\delta _ { j } = \left( t _ { j } - O _ { j } \right) f ^ { \prime } \left( \mathrm { n e t } _ { j } \right)
$$

and for the hidden layer nodes

$$
\delta _ { j } = f ^ { \prime } \left( \mathrm { n e t } _ { j } \right) \sum _ { k } \delta _ { k } w _ { j i } .
$$

2.5.2.The Classification Phase. The classificationphase takes the output directly from the last feature extraction layer as its input.The parameters used for the classification phase are predefined in the feature extraction phase. There are three output nodes for the classfication stage of our algorithm, indicating which type of spines the subimage contains.

2.5.3.Accelerationof theMSNNBased on theRegularization. In order to accelerate the learning rate and decrease the learning epochs,we employed the regularization factor. Regularization is used to reduce near-zero connection weight value to zero, therefore reducing the complexity of the network.It is defined as

$$
\begin{array} { l } { \displaystyle R \left( w \right) = E _ { s } \left( w \right) + \lambda E _ { c } \left( w \right) , } \\ { \displaystyle E _ { c } \left( w \right) = \sum _ { \forall w \mathrm { ~ i n ~ n e t w o r k } } \frac { \left( w _ { i } / w _ { o } \right) ^ { 2 } } { 1 + \left( w _ { i } / w _ { 0 } \right) ^ { 2 } } , } \end{array}
$$

where $E _ { s } ( \omega )$ is the performance measure of the learning algorithm, the total network error, and $E _ { c } ( \omega )$ is the complexity penalty of the network model. $\lambda$ is the regularization factor. $\boldsymbol { w } _ { 0 }$ isa predefined parameter.Meanwhile,research shows that a network with proper SEs produces better result [36].Therefore,it is essential to choose the suitable SEs.In this paper,according to the average size of spine and the comparisonresult in Table3,we defined the SE asa diskwith the radius of 4 pixels.

For the training procedure,the RMSNN takes the subimage as the input and makes one output value for each image. For the testing procedure,our proposed algorithm scans the whole ROI and generates an image named the detection plane,which is based on the outputs from the target class nodes.

$$
\begin{array} { c } { { \displaystyle { \cal O } _ { j } = f \left( \mathrm { n e t } _ { j } \right) , } } \\ { { \displaystyle \mathrm { n e t } _ { j } = \sum _ { i } w _ { j i } { \cal O } _ { i } + \Delta _ { j } , } } \end{array}
$$

in which $\boldsymbol { w } _ { j i }$ is the connection weight strength to node $j$ from node $i$ and $\Delta _ { j }$ is the bias output for node $j . \ \underset { . } { w } _ { j i }$ is typically learned by the back-propagation of error. The update rule of connecting weight for each connection is expressed as follows:

$$
\Delta w _ { j i } = - \eta \frac { \partial E } { \partial w _ { k j } } = \eta \delta _ { j } O _ { j } .
$$

# 3.Experimental Evaluation

3.1.Experiment Design.We have trained neural networks with the back-propagation algorithm. The subimages were submitted to the input nodes of the neural network.The error of the output was propagated through all the connections.The process repeated until the network converged to a stable state with required MSE.When the MSE approximated to a preset value or the maximum epoch was achieved,the algorithm converged and the training would stop.During the training, the RMSNN took each subimage as the input and produced one output value for each of the three categories.Figure 2(a) shows the samples of subimages containing mushroom type spine.Figure 2(b) shows the samples of the subimages containing the stubby type,and Figure 2(c) shows the samples of thin type subimage.

In the training step,the subimage samples were input to the network sequentially. The median-squared error was employed to measure the training effectiveness.For each subimage,the RMSNN produced one output value,which indicated the type of spine in the subimage.Then,we scanned the entire microscopy image and finally generated a detection plane according to the output nodes of RMSNN.

In order to test the classification accuracy, we randomly selected 9oo samples for each type of spine,respectively. Following common convention and ease of stratified cross validation, $1 0 \times 1 0$ -fold stratified cross validation(CV) was used for the dataset to perform an unbiased statistical analysis. The RMSNN was constructed in the form as two feature extraction layers,one hidden layer with ten hidden neurons and one output layer with three neurons.The input subimage size was 20 by 20 pixels,and the size of the structure elements was with the radius of 4 pixels.The initial weight was in the range of $[ - 1 . 0 , 1 . 0 ]$ . The learning rate was set to 0.0015. The maximum training epoch was predefined as l5o0o. The expected output values for mushroom, stubby,and thin type spines were[1 0 O],[0 1 O],and [0 0 1].

# 3.2.Experiment Results

3.2.1.Backbone Extraction. The extraction resultis shown in Figure 5. Figure 5(a) shows the original image. Figure 5(b) shows the extracted backbone,of which the width covers merely one pixel.

3.2.2.Boundary Location. Figure 6(a) shows the mark of the located backbone of the dendrite based on the originalimage, and Figure 6(b) shows the marked boundary of the dendrite after the backbone is extracted.Figure $6 ( \mathrm { c ) }$ shows the marked dendrite that determines the starting point of the spine.

3.2.3.Spine Analysis.Figure7 shows a ROI of our sample image,and Figure7(b) shows the detection result of the spines. The backbone is marked by the purple color and the boundary is marked by the red color. The spines are marked by their periphery of blue color.

Figure 8(a） shows the original image with the marked region of interest.Figure 8(b) shows the classification result based on the features extracted in the first phase.The corresponding SE gets respect features around each pixel,but it is blind for readers to understand which features are obtained. The detected spines contain 8 mushroom types,8 stubby types,and 4 thin types. The average of the classification accuracy of RMSNN is shown in Table2 based on the 2700 samples in total.We can find that the detection of the mushroom and thin types has better performance than the stubby type. It is because the stubby type seems connected with the major lines,and the neck of the spine is blurred. Figures 8(c),8(d),and 8(e) demonstrate partial geometric attributes of the spines,including the area,perimeter, and width.We found that the areas of the spines of the ROI ranged within [10,23] and the perimeter ranged within [8,88].

TABLE 2:Average of the classification accuracy onal0-by-l0 CV.   

<html><body><table><tr><td>Spine types</td><td>Mushroom</td><td>Stubby</td><td>Thin</td></tr><tr><td>Mushroom</td><td>99.1%</td><td>1.3%</td><td>1.1%</td></tr><tr><td>Stubby</td><td>0.7%</td><td>97.6%</td><td>0.3%</td></tr><tr><td>Thin</td><td>0.2%</td><td>1.1%</td><td>98.6%</td></tr></table></body></html>

3.3.Optimal Parameter in SE. According to [36],unsuitable SEs will degrade the performance of the RMSNN; hence, it is critical to choose the proper SEs.According to the average size of the spines as 20 by 20 pixels,we selected SEs with different sizes and shapes to test the performance. The comparison of classification accuracies based on the 2700 samples is shown in Table3.We can find that the disk with aradius of 4 pixels reaches the best performance.Therefore, we finally defined the SEs as a disk with the radius of 4 pixels.

3.4.Algorithm Comparison. To further validate the efficacy of our proposed approach,we have compared the proposed algorithm with Cheng et al.'s method [18] and the manual method.In Cheng et al.'s paper, the authors employed the adaptive threshold to segment the image and Chen and Molloi's algorithm[37] to extract the backbone and then used the local SNR for the detection of the detached spine and local spine morphology for the detection of the attached spines. The comparison results based on ROIl in Figure 8 and 15 images collected in our database are shown in Table 4.It is found from Figure 9 that Cheng et al's method missed some small protrusions whose number of pixels is more than 5. The number of detected spines via our algorithm is 19,13 by Cheng et al.'s method,and 20 via the manual method as shown in Table 4.Cheng et al's method is robust at dealing with the spines detached from the dendrite but weak at spines attached with the dendrite.However, the detached spines from the dendrite are caused by the deconvolution to denoise the image. Our proposed algorithm overcomes the problem of detecting attached spines.

# 4. Discussion

In this paper, we have proposed new algorithms using conditional symmetric analysis and regularized morphological shared-weight neural network to detect and analyze the dendrite and dendritic spines.

Figure 5 shows that backbone extraction result based on the conditional symmetry analysis.Compared to the secondorder directional derivatives method in [14],our proposed algorithms reduced the computation time of linking the breaking point of the backbone.

Figure 6 shows the result of the marked backbone and the boundary of the dendrite,which is used to determine the starting point of the spines.

Table2 shows the classification result of the different types of spines.The row in Table2 stands for the actual class and the column in Table2 stands for the predicted class. The“mushroom” type has an obvious head and thin neck. The“stubby” type lacks obvious neck,and the“thin” type lacks obvious head. In Table 2, the detection accuracy of the mushroom type is higher than the other two types,and part of the stubby type is misclassified into mushroom and thin types as its head and neck ratio is at the level of average.A percent of 1.l of thin spines are misclassified into mushroom type and $0 . 3 \%$ into stubby type,which is caused by the similar size of thehead and neck.Table4 shows the result of detected spines of Figure 8,respectively, by manual,ALS [18],and ourproposed method SRMSNN. The results demonstrate that our algorithm has better performance than the other two methods for the images obtained by the confocal laser scanning microscopy.

TABLE 3: Classification accuracy by different SEs (unit is in pixel, bold denotes the best, $r$ is radius, and $\boldsymbol { w }$ is width)   

<html><body><table><tr><td></td><td>Disk(r = 5)</td><td>Disk (r = 4)</td><td>Disk (r = 3)</td><td>Square (w = 3)</td><td>Square (w = 4)</td></tr><tr><td>Mushroom</td><td>98.7%</td><td>99.1%</td><td>95.4%</td><td>85.3%</td><td>89.2%</td></tr><tr><td>Stubby</td><td>96.2%</td><td>97.6%</td><td>94.1%</td><td>87.2%</td><td>91.2%</td></tr><tr><td>Thin</td><td>94.3%</td><td>98.6%</td><td>96.2%</td><td>79.1%</td><td>75.3%</td></tr></table></body></html>

![](images/3cd9f94aba3cce85e16619feb890d987023465cfdc785a122c440fe2064b64d1.jpg)  
FIGURE 5:Backbone extraction result.

![](images/8fb57c15158ec0fba443c7ccffa3d075b4bd710e6e72920db872ddc6bf96773f.jpg)  
FIGURE 6:Dendrite location results.

![](images/dbb8f6616f2fb7639e94abe7af16a19f636739bbe8dec772dd2811014f8bfc1b.jpg)  
FIGURE 7:(a) ROI of the original Image.(b) Detection result of the spines.

TABLE 4: Detection result of ROIl in Figure 8 and 15 images in our database.   

<html><body><table><tr><td>Methods</td><td>ROI1</td><td>15 images</td></tr><tr><td>Manual</td><td>20</td><td>2021</td></tr><tr><td>ALS [18]</td><td>13</td><td>1750</td></tr><tr><td>SRMSNN (proposed)</td><td>19</td><td>1987</td></tr></table></body></html>

![](images/b0090c097ae84b856258b62702cbfbefd471d82c43dfd2426133b0c207219f4f.jpg)  
FIGURE 8: Experiment result with corresponding parameters for characterization.

# 5. Conclusion

In this paper, we proposed a new automatic approach to accurately identify dendritic spines with different shapes.

The novelty of this approach includes (1) a new model using wavelet-based conditional symmetry analysis for dendrite backbone extraction and localization, which is the first step towards identification of dendritic spins; (2) a new algorithm based on regularized morphological shared-weight neural networks for classification of spines into the right classes (i.e.,mushroom,stubby,and thin),entitled “RMSNN.”This research was based on our collected microscopy images.We have applied our approach to image base library containing around 2700 subimage samples, 9oo for each type of spines, and have compared the proposed method with the existing methods. The experimental results demonstrate that our algorithm outperforms existing methods with a significant improvement in accuracy in terms of classifying spines into the different spine categories. The classification accuracy is $9 9 . 1 \%$ for mushroom spines, $9 7 . 6 \%$ for stubby spines,and $9 8 . 6 \%$ for thin spines.

![](images/5990c7e23b485beb8279ea6493a6bf4b2212f04d6b6b7aded2ebef5bf00d798f.jpg)  
FIGURE 9:Detection resultbased on ALS and SRMSNN.

The future work will be focusing on further validation of the robustness of the algorithms through collecting more samples and testing on different datasets.A user-friendly interface will be also built for usability improvement and enhancement. Meanwhile,we will be focusing on reducing the computation time while improving the classification accuracy based on the 3D image stacks.Other feature extraction tools (such as wavelet packet analysis [38],wavelet entropy[39],and 3D-DWT[40]) and other advanced classification tools [4l,42] will be tested.Besides,swarm intelligence method will be used to find optimal parameters [43].

# Conflict of Interests

Theauthors declare that there is no conflict of interests regarding the publication of this paper.

# Acknowledgment

This work was financially supported by the National Natural Science Foundation of China (no. 6l271231).

# References

[1] J.L.Krichmar, S.J. Nasuto,R. Scorcioni, S.D.Washington, and G.A.Ascoli，“Effects of dendritic morphology on CA3 pyramidal cell electrophysiology:a simulation study”Brain Research,vol.94l, no.1-2,pp.11-28,2002.   
[2]D.Johnstonand S.M.-S.Wu,FoundationsofCellularNeurophysiology,MITPress,Cambridge,Mass,USA,1995.   
[3] Z.F. Mainen and T. J. Sejnowski,“Influence of dendritic structure on firing pattern in model neocortical neurons" Nature,vol.382,no. 6589,pp.363-366,1996.   
[4]N.Keren,N.Peled,and A.Korngreen,"Constraining compartmental models using multiple voltage recordings and genetic

algorithms,Journal ofNeurophysiology,vol.94,no.6,pp.3730-

3742,2005.   
[5] B.Van Calster, D.Timmerman,C.Lu et al.,“Preoperative diagnosis of ovarian tumors using Bayesian kernel-based methods, Ultrasound in Obstetrics and Gynecology,vol.29,no.5,pp.496- 504,2007.   
[6] K.M. Stiefel and T. J. Sejnowski,“Mapping function onto neuronal morphology” Journal of Neurophysiology, vol. 98, no. 1, pp.513-526,2007.   
[7] S.Wang,H.Pan,C. Zhang,and Y. Tian,“RGB-D image-based detection of stairs,pedestrian crosswalks and traffc signs” Journal of Visual Communication and Image Representation, vol. 25,no. 2, pp.263-272,2014.   
[8]S.K.Schmitz,J.J.J.Hjorth,R.M.S.Joemai et al.,“Automated analysis of neuronal morphology, synapse number and synaptic recruitment” Journal of Neuroscience Methods,vol. l95,no. 2, Pp.185-193,2011.   
[9] T.M.Liu,G.Li, J.X.Nie et al.,“An automated method for cell detection in zebrafish,Neuroinformatics,vol. 6, no.l, pp.5-21, 2008.   
[10] W.Yu,H.K.Lee,S.Hariharan,W.Bu,and S.Ahmed, "Evolving generalized voronoi diagrams for_accurate cellular image segmentation" Cytometry Part A,vol.77, no. 4, pp.379- 386,2010.   
[11]M.K.Bashar, K.Komatsu, T.Fujimori,and T.J.Kobayashi, "Automatic extraction of nuclei centroids of mouse embryonic cells from fluorescence microscopy images”PLoS ONE,vol.7, no.5,Article ID e35550,2012.   
[12] J.L.Martiel,A.Leal, L. Kurzawa et al.,“Measurement of cell traction forceswith ImageJ’in Methodsin Cell Biology,E.K. Paluch,Ed.,vol.125,chapter 15,pp.269-287,Academic Press, 2015.   
[13]D.L.Dickstein,A. Rodriguez,A.B.Rocher et al.,“NeuronStudio:an automated quantitative software to assess changes in spine pathology in Alzheimer models,Alzheimer's & Dementia, vol. 6,no.4,article S4l0,2010.   
[14] E.Meijering,M. Jacob,J.-C.F Sarria,P. Steiner,H.Hirling,and M. Unser,“Design and validation of a tool for neurite tracing and analysis in fluorescence microscopy images”Cytometry Part A,vol.58,no.2,pp.167-176,2004.   
[15] J. Cheng, X. B. Zhou, B.L. Sabatini,and S. T. C. Wong,“NeuronIQ:a novel computational approach for automatic dendrite spines detectionand analysis,inProceedingsof the IEEE/NIH Life Science Systems and Applications Workshop (LISA'07), pp. 168-171,IEEE,Bethesda,Md,USA,November 2007.   
[16] I. Y. Y. Koh,W. B.Lindquist, K. Zito,E.A. Nimchinsky, and K.Svoboda,"An image analysis algorithm for dendritic spines" Neural Computation,vol.14, no.6,pp.1283-1310,2002.   
[17] X. Y. Xu,J. Cheng,R. M. Wit, B.L. Sabatini, and S.T. C.Wong, "A shape analysis method to detect dendritic spine in 3D optical microscopy image"in Proceedings of the 3rd IEEE International Symposium on Biomedical Imaging: From Nano to Macro, pp. 554-557,Arlington, Va, USA,April 2006.   
[18] J.Cheng,X. Zhou,E.Miller et al.,“A novel computational approach for automatic dendrite spines detection in twophotonlaser scan microscopy" Journal ofNeuroscience Methods, vol.165,no.l, pp.122-134,2007.   
[19] J.Fan,X. Zhou,J.G. Dy, Y. Zhang,and S. T. C.Wong,“An automated pipeline for dendrite spine detection and tracking of 3D optical microscopy neuron images of in vivo mouse models" Neuroinformatics,vol.7,no.2,pp.3-130,2009.   
[20] Y. Zhang,X. B. Zhou,R. M. Witt, B.L. Sabatini, D.Adjeroh, and S. T. C. Wong,“Dendritic spine detection using curvilinear structure detector and LDA classifier” NeuroImage,vol. 36, no. 2,pp. 346-360,2007.   
[21] F Janoos,K. Mosaliganti, X. Xu,R. Machiraju, K. Huang,and S.T. C.Wong,“Robust 3D reconstruction and identification of dendritic spines from optical microscopy imaging” Medical Image Analysis,vol.13,no.1,pp.167-179,2009.   
[22] T. He, Z. Xue,and S. T. C.Wong,“A novel approach for three dimensional dendrite spine segmentation and clasification” in Medical Imaging 2012: Image Processing, vol. 8314 of Proceedings of SPIE,San Diego, Calif, USA,February 2012.   
[23] P. Shi, Y.Huang,and J. Hong,“Automated three-dimensional reconstruction and morphological analysis of dendritic spines based on semi-supervised learning" Biomedical Optics Express, vol.5,no.5,pp.1541-1553,2014.   
[24] S.Reid, C.Lu,I. Casikar et al.,“Prediction of pouch of Douglas obliteration in women with suspected endometriosis using a new real-time dynamic transvaginal ultrasound technique: the sliding sign” Ultrasound in Obstetrics e Gynecology,vol. 4l, no. 6, pp. 685-691,2013.   
[25] S.Reid, C.Lu,I. Casikar et al.,“The prediction of pouch of Douglas obliteration using offline analysis of the transvaginal ultrasound ‘sliding sign’ technique: inter-and intra-observer reproducibility” Human Reproduction,vol.28, no.5,pp.1237- 1246,2013.   
[26] Y.-H.Wang,W.-N. Liu,A.-H. Chen,and Y.Wang,“Nonlinear dim target enhancement algorithm based on partial differential equation” Journal of Dalian Maritime University,vol.34,no.2, Pp.57-60,2008.   
[27] L.Chen, J. H. Zhang, S. Y. Chen,Y. Lin, C. Y. Yao, and J. W. Zhang,“Hierarchical mergence approach to cell detection in phase contrast microscopy images” Computational and Mathematical Methods in Medicine,vol.2014,ArticleID758587, 10 pages, 2014.   
[28] N. Otsu,"A threshold selection method from gray-level histograms” IEEE Transactions on Systems, Man and Cybernetics, vol. 9, no.1,pp. 62-66,1979.   
[29] P.-S.Liao,T.-S.Chen,and P.-C. Chung,“A fast algorithm for multilevel thresholding’Journal of Information Science and Engineering,vol.17,no.5,pp.713-727,2001.   
[30]L.H. Yang,X. You,R.M. Haralick, 1. T. Philips,and Y. Y. Tang, "Characterization ofDiracedge with new wavelet transform"in Proceedings ofthe2nd International Conference on Wavelets and Applications, vol.1, pp.872-878,Hong Kong,December 2001.

![](images/d6480c11cf636dce2e51e13e8dcaba0a835127b49c5d86cfca6114ca99aac897.jpg)

![](images/4503012c3abf190bda8ce052fa92a47485eebde9f461710433d97c521939c88f.jpg)

@

![](images/1c7425e94dfe44eacb2db5e02684b075e554803333057378011e6711460c8166.jpg)

![](images/e858d5a55a947152dbccaa528670bd7fa77cd8da1677cf5c3180af944b8e9e45.jpg)

# Hindawi

Submit your manuscripts at http://www.hindawi.com

![](images/542dc953054811cb8797cf7d1432968b895916093e1e1b195327569e6abbe271.jpg)

![](images/cf7bda9eed1c98f6a62dea076d3390af6d84fc1dff6d39a781e52191d6b74277.jpg)