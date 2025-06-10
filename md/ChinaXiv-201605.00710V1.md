# Evaluation of Autofocus Algorithms for Automatic Detection of Caenorhabditis elegans Lipid Droplets

ZHANG Xiangl, 2)\*\*， JIA $\mathrm { C e } ^ { 2 ) }$ ， XIE Kang2) (CollegeofLifeScienceandTechnology,Huazhong UniversityofcienceandTechnology，Wuhan43oo74,China; 2 Institute of Biophysics,Chinese Academy of Sciences,Beijing 1Oo1o1,China)

AbstractAutofocusingisafundamentalstep towardsautomated microscopicscreningof Caenorhabditiselegans.Determinngthe optimal focus inanoptical microscopeisbasedonaclarity-evaluation functionthatisappliedtoimagesacquiredfromdiferent focusesof thesamefield.Themaximumvalueof thefunctionisconsideredasthepointofoptimalfocus.Inthispaper,16utofocus algorithms which werecollcted fromwell-nownalgorithms aswellaste mostrecentlyproposed focusingalgorithmshavebeen evaluated. Through these evaluations,an optimal algorithm was found for $C .$ ，elegants lipid droplets to set up an automatic screening system.Manyeauresressssdinthisrforistaceccracyomputatioaltieditioofoisendousingre. Ourresultshaveshownthatmostofthealgorithmsshowanoverallhighperformanceforthistpeofimage,andabsoluteTenengrad algorithm willbe our first choice for its best performance considering accuracy.

Key wordsC.ele gants lipid droplets,autofocus algorithms,automatic screening DOI:10.16476/j.pibb.2015.0189

Caenorhabditiselegans(C.elegans） isan established model organism for studying lipid droplets andenergymetabolismbecause it hasmany advantages.For example,its mutation is simple to use as genetic tool,and it is easily to be examined in microscope [1. In the past few years,owing to the identification of lipid droplet-associated proteins such as DHS- $3 ^ { [ 1 ] }$ and PLN[2],lipid droplets can be marked with fluorescence protein-tagged as a fat storage indicator. RNAinterference(RNAi) hasbeen investigated in $C .$ .elegans since 1998 by Fire et al. (Nobel Prize in Physiology or Medicine in 2006)[3]. Through an RNAi screen,uncharacterized fat storage regulatory genes can be identified in C. elegans [2, 4-6]. However， manual identification and countingof C.elegans lipid droplets is exhausting and timeconsuming. Moreover, it requires a trained operator, and presents a high false-negative rate.Therefore,in order to reduce this rate and speed up the process, automatic screening is necessary.

Focusing is a fundamental and crucial step in automatic system.Determining the optimal focus in an optical microscope is based on a clarity-evaluation function that is applied to images acquired from different focuses of the same field[7]. The maximum value of the function is regarded as the point of optimal focus.Many autofocus algorithms have been proposed in the literature, but their accuracy can vary depending on contents of the processed images. According to the previous studies,Santos et $\boldsymbol { a l }$ [8] compared autofocus algorithm in molecular cytogenetic, and drew the conclusion that the method Vollath-4 is the most appropriate for FISH (fluorescence in situ hybridization) images. Osibote et al.[9] determined that method Vollath-4 [o] has the best focus accuracy for tuberculosisin bright-field microscopy. However, other studies such as Kimura et al.[i] found that method variance provided the best overall performance for tuberculosis.Liu et al.[2] drew the same conclusion in both blood smear and pap smear.Redondo et al.[13] claimed that variance, normalized variance and Vollath-5 are the most suitable method for automatic systeminbright-filedmicroscopypathology. Furthermore， the study by Mateos-Pérez et al.[14] includedadditional assessingfeaturessuchas variability of the fluorescent microscopy images, additionofnoise, illuminationchanges,and prefiltering processes.

This paper focuses on the ascertainment of the optimal autofocus algorithms for C. elegans lipid droplets fluorescence imaging through a systematic evaluation of16 commonly-used autofocus algorithms. A set of criteria, such as accuracy error,computation time,thenumberoflocalmaxima,FWHM(full width at half maximum) of the focus curve and the noise robustness,were assessed to evaluate the performance of the autofocus algorithms.In the previous literature, optimally focused image was identified by trained operators,which will lead to a little uncertainty and inaccuracy,because different observers could choose slightly different images around the optimal focus plane.For example,Osibote et al.[] determined that method Vollath-4 has the best focus accuracy for tuberculosis,whereas Kimura et al.[i] found that method variance provides the best overall performance for tuberculosis.Therefore，we adopted an objective way to determine the optimal focus plane in this paper to avoid subjective deviation.

# 1 Materials

Strains Pvha-6:dhs-3::GFP (single copy) were created by professor Ho Yi Mak (Hong Kong University of Science and Technology).DHS-3 can be used as a lipid droplet marker protein in $C .$ ，elegans,as well as a fat storage indicator in live worms.This marker protein will facilitate further mechanistic studies of lipid droplets in C. elegans [1]. All strains were maintained on NGM plates under standard conditions[15].

Worms were raised at approximately $2 2 ^ { \circ } \mathrm { C }$ and prepared for imaging asdescribed previously [16]. Briefly, the worms were soaked in a solution of $0 . 1 \%$ tricaine and $0 . 0 1 \%$ levamlsole(Sigma-Aldrich) in M9 for $2 0 \sim 3 0 ~ \mathrm { m i n }$ prior to imaging[17]. The immobilized worms were then transferred with a glass hook to a slab of $3 \%$ agarose in M9.The coverslip was then sealedwithVaseline.

Images were acquired using a motorized Zeiss Imager M2 Microscope equipped with AxioCam CCD camera(Carl Zeiss,Germany） and X-Cite 12OQ light source (Lumen Dynamics， Canada） drivenby Axiovision(Carl Zeiss,Germany).Green fluorescence images were acquired with the resolution of $1 3 8 8 \times$ 1040 pixels and 16bits of dynamic range in grayscale. Atrained operator selected the best focal plane from which 3O images were captured upward in axrzial direction and another 29 downward, thus the stacks are made of 6O images.Two different magnifications were used: $\times 1 0$ $( N A = 0 . 3 0 )$ and $\times 4 0$ 0 $\mathrm { T } A = 0 . 7 5 ) ,$ .Different magnification used different $Z$ step: $\Delta { Z } { = } 0 . 5 ~ \mu \mathrm { m }$ at $\times 4 0$ and $\Delta Z { = } 2 ~ \mu \mathrm { m }$ at $\times 1 0$ . Ten stacks were captured with two different magnifications each from ten different worms.All algorithms implemented in Matlab 7.6.0 (The Mathworks, America) on an Intel Corei5 3.50 GHz 16 GB RAM computer using the Windows 8 operating system (Microsoft,America).

# 2 Autofocus methods

Autofocus is characteristic of automatic system. There are two kinds of autofocus methods: active methods and passive methods. Active methods are based on measuring the distance between the lens and object of the scene by emitting ultrasonic or infrared waves[l3]. But these methods have limitations in case of live model organisms such as C. elegans.Passive methods are grounded on analyzing the image sharpness of the objects by autofocus functions,which are usually related to high frequencies of the image.

The autofocus function gives a mathematical value that shows the degree of focus for each image of the same sample.The fundamental assumption behind most of the functions is that a defocused image results from convolution of the image with a certain point spread function (PSF)，which usuallyproducesa decrease in the high frequencies of the image[8]. This result can also be regarded as the assumption that focused images contain more information and detail than defocus images.The sixteen autofocus functions analyzed in this study can be classified into five groups:(1) Derivative-Based function,(2) TransformBased function，(3） Statistics-Based function，(4) Histogram-Based function and (5） Intensity-Based function. For an image of size $M { \times } N _ { i }$ ,the notation $\boldsymbol { g } ( \boldsymbol { x } , \boldsymbol { y } )$ refers to the image intensity at point $\left( x , ~ y \right)$ ，while the symbol $\otimes$ indicates the convolution operator.

# 2.1Derivative-based function

These functions are based on a derivative suppose that defocusedimagesusually have less high-frequency content than focused images.

Brennergradient(BREN).Thisfunction calculates the first difference between a pixel and its neighbor two points away[18].

$$
A F _ { \mathrm { { B R E N } } } = \sum _ { x } \ \sum _ { y } \vert g ( x , y + 2 ) - g ( x , y ) \vert ^ { 2 }
$$

While $| g ( x , y + 1 ) - g ( x , y ) | \geqslant \tau$ (threshold value)

Laplacian(LAP). This focus function was originally used to find focusing errors caused by noise [9].The algorithm implements the image convolution with a discrete Laplacianmask as follows:

$$
\begin{array} { c } { { A { \cal F } _ { \mathrm { L A P } } = \displaystyle \sum _ { x } \sum _ { y } [ g ( x - 1 , y ) + g ( x + 1 , y ) + } } \\ { { g ( x , y - 1 ) + g ( x , y + 1 ) - 4 g ( x - 1 , y ) ] ^ { 2 } } } \end{array}
$$

Tenengrad (TEN). This algorithm convolves an image with Sobel operators and then it sums the square of all the magnitudes greater than a threshold value[20-22].

$$
\begin{array} { c } { { A { \cal F } _ { \mathrm { T E N } } = \displaystyle \sum _ { x } \sum _ { y } [ g ( x , y ) \otimes S ] ^ { 2 } + } } \\ { { { } [ g ( x , y ) \otimes S ^ { \prime } ] ^ { 2 } , \forall g ( x , y ) > \tau } } \end{array}
$$

Where $S$ and $S ^ { \prime }$ are the Sobel's kernel and its transpose respectively,where $S$ is given by:

$$
S { = } { \left[ \begin{array} { l l l } { 1 } & { 0 } & { - 1 } \\ { 2 } & { 0 } & { - 2 } \\ { 1 } & { 0 } & { - 1 } \end{array} \right] }
$$

Absolute Tenengrad(ATEN).This focus function issimilar to the previous Eq(3),but the absolute value of the gradient coefficients is used in order to reduce the computation time[23].

$$
A { \cal F } _ { \mathrm { A T E N } } = \sum _ { x } \sum _ { y } | g ( x , y ) \otimes S | + | g ( x , y ) \otimes S ^ { \prime } |
$$

Gaussian filter(GS).This focus function is based on a gradient filter derived from convolving the image witha first-order Gaussian derivative[24].

$$
\begin{array} { c } { { A { \cal F } _ { \mathrm { G S } } ( { \bf \underline { { { \sigma } } } } ) { = } \displaystyle \frac { 1 } { M N } \sum _ { x } \sum _ { y } [ g ( x , y ) \otimes { \cal G } _ { x } ( x , y , { \bf \sigma } { \bf \underline { { { \sigma } } } } ) ] ^ { 2 } + } } \\ { { { } [ g ( x , y ) \otimes { \cal G } _ { y } ( x , y , { \bf \sigma } { \bf \sigma } { \bf \sigma } ) ] ^ { 2 } } } \end{array}
$$

Where $G _ { x }$ and $G _ { y }$ are the first-order Gaussian derivatives in the $x$ and $y$ directions.The $\mathbf { \sigma } _ { \mathbf { \sigma } } \mathbf { \sigma } _ { \mathbf { \sigma } }$ parameter of the Gaussian method should be adjusted in relation to the objects present in the image.We evaluated different $\mathbf { \sigma } _ { \mathbf { \sigma } } \mathbf { \sigma } _ { \mathbf { \sigma } }$ values to test the robustness of the method. Here we set $\scriptstyle \mathbf { \sigma } \mathbf { \sigma } \mathbf { \sigma } \mathbf { \sigma } \mathbf { \sigma } \mathbf { \sigma } \mathbf { \sigma } \mathbf { \sigma }$ ：

# 2.2 Transform-based function

Transform-basedfunctionsareutilizedto calculate the degree of focusing for each image by a

mathematical transform

Discrete Cosine Transform (DCT). Focusing techniques based on band-passed filters perform well. In this algorithm,images are divided into blocks of $4 0 { \times } 4 0$ pixels then DCT is applied,and the sum of four band-pass diagonal bands representing mid and high frequencies is chosen[25]:

$$
C ( u , v ) { = } \frac { 1 } { 1 6 } \sum _ { x } \sum _ { y } g ( x , y ) \mathrm { c o s } \Bigg ( \begin{array} { c } { { { \pi } ( 2 m { + } 1 ) u } } \\ { { { 2 } M } } \end{array} \Bigg )
$$

$$
\cos \left( \begin{array} { c } { { \pi ( 2 n + 1 ) v } } \\ { { 2 N } } \end{array} \right)
$$

Midfrequency-DCT (MDCT). The influence of the band-pass DCT coefficients on the focus measure has been analyzed [26]．A $4 \times 4$ convolution mask for extracting the central coefficient $C ( 4 , 4 )$ of the DCT, which is used as a focus measurement.The MDCT operator can be calculated as:

$$
A F _ { \mathrm { M D C T } } = \sum _ { x } \sum _ { y } ( \varrho ( x , y ) \otimes { \cal O } _ { \mathrm { M D C T } } ) ^ { 2 }
$$

With

$$
O _ { \mathrm { M D C T } } = \left[ \begin{array} { l l l l } { 1 } & { 1 } & { - 1 } & { - 1 } \\ { 1 } & { 1 } & { - 1 } & { - 1 } \\ { - 1 } & { - 1 } & { 1 } & { 1 } \\ { - 1 } & { - 1 } & { 1 } & { 1 } \end{array} \right]
$$

Wavelet transformation (WT).This functionis based on discrete wavelet transformation.The wavelet focus function calculates ratio of the energy in low and high pass bands[27].

$$
A F _ { \mathrm { { w } } \mathrm { { r } } } = \frac { \parallel \mathbf { \nabla } h _ { w } ( f ) \parallel } { \parallel \mathbf { \nabla } l _ { w } ( f ) \parallel }
$$

Where $h _ { w } ( f )$ is the discrete wavelet transformation in high pass band,and $l _ { w } ( f )$ is the discrete wavelet transformation in the low pass band.

# 2.3 Statistics-basedfunction

Statistics-based functions use features such as variance and autocorrelation to calculate the degree of focusing for each image.

Variance (VAR). This function computes the variations in the gray level among the image pixels, where bright and dark pixels have the same influence[28].

$$
A { \cal F } _ { \mathrm { V A R } } = \frac { 1 } { M N } \sum _ { x } \sum _ { y } [ g ( x , y ) - \bar { g } ] ^ { 2 }
$$

Whereg= M∑∑g(x,y)istheimage ean.

Normalized variance (NVAR)[28]. This function is a variation of Eq(11) by normalizing with the mean $\bar { g }$ which compensates for changes in the average image brightness.

$$
A { \cal F } _ { \mathrm { N V A R } } { = } \frac { 1 } { M N \bar { g } } \sum _ { x } \sum _ { y } [ g ( x , y ) { - } \bar { g } ] ^ { 2 }
$$

Vollath-4(VOL4)[29-30]. This algorithm proposed by Vollath is based on an autocorrelation function.

$$
\begin{array} { r } { A F _ { \mathrm { V O L } } = \displaystyle \sum _ { x } ^ { M - 1 } \sum _ { y } g ( x , y ) \cdot g ( x + 1 , y ) - } \\ { \displaystyle \sum _ { x } ^ { M - 2 } \sum _ { y } g ( x , y ) \cdot g ( x + 2 , y ) } \end{array}
$$

Vallath-5(VOL5) $[ 2 9 - 3 0 ]$ ．Vollath proposeda modification of Eq(13) which is based on the standard deviation function.

$$
A F _ { \mathrm { v o L } s } { = } \sum _ { x } ^ { M - 1 } \sum _ { y } g ( x , y ) { \cdot } g ( x { + } 1 , y ) { - } M N _ { g } ^ { - 2 }
$$

# 2.4Histogram-based function

These functions are grounded on the assumption that focused images have a greater number of grey levels than defocused images[31].

Log-histogram(LOG).Imagehistogram approximates a probability distribution function of gray levels,where the variance of this distribution increases as the image sharpness increases too[l3]. This algorithm is based on the bright pixels in the image by multiplying the variance by the logarithm function:

$$
A F _ { \mathrm { L O G } } = \sum _ { l } { [ l { - } E _ { \mathrm { l o g } } \{ l \} ] ^ { 2 } { \bullet } \mathrm { l o g } ( p _ { l } ) }
$$

Where $p _ { l }$ is the probability if the intensity level $l$ and $E _ { \log } \{ l \} = \sum _ { \mathit { l } } \mathit { l } \cdot \log ( p _ { \mathit { l } } )$ is the expected value of the log-histogram.

Weighted histogram (WHS). Images focused underfluorescenceilluminationpresenthigher portions ofpixels with bright gray levelsthan unfocused image. This recently proposed algorithm is based on a weighted image histogram without introducing a constant threshold[32].

$$
A F _ { \mathrm { { W H S } } } = \sum _ { l } ~ [ ~ \sqrt [ 5 ] { h ( l ) } \bullet l ^ { 5 } \bullet 1 0 ^ { - 1 5 } ~ ]
$$

# 2.5 Intensity-based function

Intensity of the image is another feature that characterizes the degree of focusing. It canbe estimated with different ways.

Power squared (PS).This focus function sums all image intensities[8].

$$
A F _ { \mathrm { P S } } = \sum _ { x } \sum _ { y } g ( x , y ) ^ { 2 }
$$

Threshold(TH).This function sums the number of pixels above a threshold as follows[28]:

$$
A { F } _ { \mathrm { { T H } } } = \sum _ { x } \sum _ { y } T _ { \tau } [ g ( x , y ) ]
$$

With

$$
T _ { \tau } { = } \{ _ { 0 } ^ { 1 \mathrm { i f } \ g ( x , \ y ) > \ \tau }
$$

We used a fixed threshold at $50 \%$ of maximum brightnessvalue in thewhole stack.

# 3 Results

# 3.1 Accuracy error and computational time

Because the $Z$ -axis step is small,it is hard to distinguish the best focused image around the focus plane for human observers.Different observers could choose slightly different images around the focus plane. So the assessment of autofocus algorithms would be slightly different from different observers.In this paper,we adopted an objective way to determine the optimal focus plane to avoid subjective deviation. Autofocus functions were computed for each stack. The focus plane calculated by each function was not the same.Therefore,we defined the focus point as the point which most algorithms are considered as the focus point. We compared the focus point obtained by most algorithms and human observers.The results are shown in Table 1.Because of the cases are similar in both $\times 1 0$ and $\times 4 0$ ，only the data at $\times 4 0$ is shown in the

Table 1 Comparison of most algorithms and human observers at $\times 4 0$   

<html><body><table><tr><td></td><td></td><td>Most algorithms (frame）Human observerl (frame)</td><td>Deviation1 (frame)</td><td>Human observer2(frame)</td><td>Deviation2 (frame)</td></tr><tr><td>Stack1</td><td>32</td><td>33</td><td>1</td><td>32</td><td>0</td></tr><tr><td>Stack2</td><td>32</td><td>32</td><td>0</td><td>32</td><td>0</td></tr><tr><td>Stack3</td><td>32</td><td>32</td><td>0</td><td>34</td><td>2</td></tr><tr><td>Stack4</td><td>34</td><td>33</td><td>-1</td><td>33</td><td>-1</td></tr><tr><td>Stack5</td><td>31</td><td>32</td><td>1</td><td>33</td><td>2</td></tr><tr><td>Stack6</td><td>37</td><td>38</td><td>1</td><td>36</td><td>-1</td></tr><tr><td>Stack7</td><td>30</td><td>31</td><td>1</td><td>30</td><td>0</td></tr><tr><td>Stack8</td><td>31</td><td>30</td><td>-1</td><td>30</td><td>-1</td></tr><tr><td>Stack9</td><td>33</td><td>33</td><td>0</td><td>34</td><td>1</td></tr><tr><td>Stack10</td><td>34</td><td>35</td><td>1</td><td>34</td><td>0</td></tr></table></body></html>

present work.

The deviation with the focus point was considered as the focus error for each algorithm.The errors of the algorithms applied to the ten stacks are shown in Figure 1.The variance of data was indicated by the lines drawn above the bars. The stacks acquired at different focus points using a constant $Z$ step( $\Delta Z =$ $0 . 5 ~ { \mu \mathrm { m } }$ at $\times 4 0$ ， $\Delta Z { = } 2 ~ \mu \mathrm { m }$ at $\times 1 0 ^ { \cdot }$ ).The error of the algorithm (sum of average and variance) less than one step indicates that the algorithm has high performance.

![](images/7b43c3d39cffabb92e6369436cf53bd6e3e0aa71f70510caa8af34842ee63f66.jpg)  
Fig.1 Error according to magnification value□： $\times 4 0 ( \mathrm { N A } { = } 0 . 7 5 )$ ： $\pmb { \bigtriangledown } : \times 1 0 ( \mathrm { N A } { = } 0 . 3 0 )$

Accordingto theplots,ATEN,BREN,DCT,WT, MDCT, GS,TEN show high performance at $\times 4 0$ (less than $0 . 5 ~ { \mu \mathrm { m } }$ which indicates 1 frame distance),while ATEN，BREN，DCT,MDCT,LAP,GS,TEN，VAR, VOL4,WHS show high performance at $\times 1 0$ (less than $2 ~ { \mu \mathrm { m } }$ which indicates 1 frame distance).So ATEN,

BREN，DCT， MDCT，GS， TENshowhigh performance at both magnifications. Furthermore, ATEN achieves the best accuracy of all algorithms.In addition, the percentage of correctly focused images was computed and show in Figure 2.

![](images/6bab05bb97a5ea43ec541b785d79b4ba374747e182cb24b4eef69c2590780c5c.jpg)  
Fig.2Percentage of images correctly focused □： $\times 4 0 ( \mathrm { N A } { = } 0 . 7 5 )$ ； $\mathbf { \overline { { u } } } : \times 1 0 ( \mathrm { N A } { = } 0 . 3 0 )$ ·

Computational time and accuracy in automatic systems is a trade-off and the algorithms with the best ranking in computational time are not necessarily effective in accuracy (Figure 3). Autofocus functions implemented inMatlab7.6.O(TheMathworks, America) on an Intel Core i53.50 GHz16 GB RAM computer using the Windows 8 operating system (Microsoft, America). According to the evaluated algorithms， the TH method was the fastest with $5 . 2 8 \mathrm { m s }$ per image and the WT method was the slowest with $2 8 9 . 6 5 ~ \mathrm { m s }$ per image.

![](images/4d2a5f957185737c99397653c5451472b0eb00602751bee9333a9c1c7af3aca1.jpg)  
Fig.3Mean computation time required by each algorithm per image

# 3.2 Noise responses

The performance of autofocus function has been evaluatedwhendifferentlevelsofnoiseareaddedto the stacks.We have added increasing levels of white Gaussian noise to the original data(Figure 4).Although the used values are not the real experiment conditions, this test can give additional information about the robustness of the algorithms. We calculated their influence in the accuracy error and the results for noise robustness are summarized in Figure 5.It is noticed that most of the algorithms are relatively stable until the distortion becomes very large,with the exception of WT which demonstrate more sensibility to noise than other algorithms.

![](images/bd9173b108837cad23a00e38e670c14bba214bdcae7a7f19659ee5eaed168ec9.jpg)  
Fig.4C.elegans lipid droplets fluorescence images used in evaluation

(a) $\times 4 0$ focused image.(b) $\times 4 0$ focused image with 8O dBW Gaussian noise. (c) $\times 1 0$ focused image. (d) $\times 1 0$ focused image with 80 dBW Gaussian noise.

![](images/11e4e610039fc0cd77ebc95fc516fbd696634f24e4e9001cc4f5a90810f7ddc9.jpg)  
Fig.5Responses of algorithms to white Gaussian noise at $\mathbf { \times 4 0 ( a ) }$ and $\mathbf { \times 1 0 ( b ) }$ （204号 3ecause the valueofATENis0,0,0,0,0.2here,itdoesn'tshowinthelogarithmiccoordinate.-:BREN;:LAP; $\mathbf { \nabla } \cdot - \mathbf { \nabla } \mathbf { \vec { v } } :$ TEN; $\blacktriangle ^ { -- } \big \blacktriangleup$ : ATEN; -□:GS;-:DCT; $\diamond$ ！ $\diamondsuit \mathrm { : }$ MDCT $\diamond$ 1 $\cdot \diamond$ :WT;:VAR; $\cdot \cdot$ : NVAR; ·--- $\cdot$ VOL4;•--· : VOL5; ·---·: LOG;---· : WHS; - : PS;---△ : TH.

# 3.3 Accuracy in focus curve

The reliable and fast autofocusing method is an important aspect in the automatization system and the shape of the focus curve can play an influential role in this aspect.The focus function should be unimodal in theory,but in factit can present diverse local maxima which can affect the convergence of the autofocus procedure.Moreover, the focus curve should be sharp at the peak,which can speed up the convergence of the procedure.In order to characterize the autofocus algorithms more completely, we take into account two aspects:the number of local maxima and the width at $50 \%$ maximum of the focus curve(FWHM, full width at half maximum).

First, we can see in Figure 6 that most algorithms present a unique maximum except PS.In terms of the width ratio of the focus curve,(Figure 7)，ATEN, BREN，DCT，WT，MDCT，LAP,GS，TEN，VOL4, WHS show high performance both at $\times 4 0$ (less than $1 0 \mu \mathrm { m } )$ and at $\times 1 0$ (less than $4 0 \mu \mathrm { m } ,$ ）

3.0 2.5 g 0.5 BREN LAP TEN ATEN GSDCT MDCTWT VAR NVAR VOL4 VOL5 LOG WHSPS TH

70   
50   
40 山   
30   
201   
BREN LAPTEN ATEN GSDCTMDCTWT VAR NVAR VOL4VOL5LOGWHSPSTH

# 4Discussion

Identifying thegene which related tofat metabolism in C. elegansis a laboriousand time-consuming task. Therefore,automatic screening system,from image acquisition to analysis,will be beneficial to the gene identification in C. elegans.We have presented here a study of autofocus algorithms for automatic detection of $C$ ，elegans lipid droplets in fluorescence images.

From the results,most of the algorithms show a low accuracy error.Especially,ATEN,DCT,MDCT,

GS， TENshowhighperformanceatboth magnification $\times 4 0$ and $\times 1 0$ . So they could be regarded assuitable algorithms for a $C$ ，elegans automatic system.Moreover，ATEN achieves the best accuracy of all algorithms for $C .$ 、elegans lipid droplets. In the presence of noise，most of the algorithms do not change noticeably except WT.These results show that most of thealgorithms are quite robust and independent of noise.In addition， most ofthe algorithms show no false maxima except PS.In terms of the width ratio of the focus curve,ATEN,BREN, DCT,WT,MDCT,LAP,GS,TEN,VOL4,WHSsho high performance at both magnification $\times 4 0$ and $\times 1 0$

To sum up，in our study WT show a poor accuracy,and has a long computational time,so it is not suitable for $C .$ ，elegans lipid droplets,although WT may have a good performance in other applications. Comprehensiveconsiderationofaccuracyand computational time，we recommend ATEN,MDCT and TEN for $C _ { ☉ }$ ，elegans lipid droplets. Moreover, ATEN achieves the best accuracy. In an automatic screening system,we often require both high accuracy and fast acquisition.In this case，we can apply the fastest algorithm TH for rough search,and then apply ATEN algorithm for fine search.

AcknowledgmentsWe thank professor Ho Yi Mak (Hong Kong University of Science and Technology) forPvha-6::dhs-3::GFPstrains. Wealsothank professor XU Tao (Institute of Biophysics,Chinese Academy of Sciences） for the comments on the manuscript.

# References

[1]Zhang P,NaH,Liu Z,et al.Proteomic study and marker protein identification of Caenorhabditis elegans lipid droplets.Mol Cell Proteomics,2012,11(8):317-328   
[2]Liu ZL,Xun H.A lipid droplet-associated GFP reporter-based screen identifies new fat storage regulators in C.ele gans.JGenet Genomics,2014,41(5): 305-313   
[3]Fire A,Xu SQ,K.MontgomeryM,et al.Potent and specific genetic interference by double-stranded RNA in Caenorhabditis ele gans. Nature,1998,391(6669): 806-811   
[4]Guo Y,Walther T C,Rao M,et al.Functional genomic screen reveals genes involved in lipid-droplet formation and utilization. Nature,2008,453(7195): 657-661   
[5]Wang MC,MinW,FreudigerCW,et al.RNAi screening for fat regulatory genes with SRS microscopy.Nat Methods,2O11,8(2): 135-138   
[6]Zhang Y,Zou X,Ding Y,et al.Comparative genomics and functional studyoflipid metabolic genes in Caenorhabditis elegans. BMC Genomics,2013,14: 164   
[7]Klmuira A,Costa MGF,Filho CFF C,et al.Evaluation of autofocus functions of conventional sputum smear microscopy for tuberculosis//32nd Annual International Conference of the IEEE EMBS 2010, 2010   
[8]Santos A,Sol6rzano C O D,Vaquero JJ,et al.Evaluation of autofocus functions in molecular cytogenetic analysis.J Microscopy, 1997, 188(3): 264-272   
[9]Osibote OA,Dendere R,Krishnan S,et al.Automated focusing in bright-field microscopy for tuberculosis detection.JMicrosc,2010, 240(2): 155-163   
[10] Vollath D.The influence of the scene parameters and of noise on the behavior of automatic focusing algorithms.J Microsc,1988, 151(2): 133-146   
[11] Kimura A,Costa MGF,Filho CFFC,et al.Evaluation of autofocus functions of conventional sputum smear microscopy for tuberculosis//O1oInternationalConferenceoftheIEEE Engineering in Medicine and Biology Society，Engineering in Medicine and Biology Society,Buenos Aires,2010:3041-3044   
[12] Liu X Y, Wang W H, Sun Y. Dynamic evaluation of autofocus-ing for automated microscopic analysis of blood smear and papa smear. JMicrosc,2007,227(1): 15 -23   
[13] RedondoR1, Bueno G, ValdiviezoJC,et al. Autofocus evaluation for brightfield microscopypathology. Biomed Opt，2012,17(3): 036008   
[14]Mateos-Pérez JM,Redondo R，Nava R，et al.Comparative evaluation of autofocus algorithms for a real-time system for automatic detection of Mycobacterium tuberculosis. Cytometry, 2012, 81(3): 213-221   
[15]Brenner S.The genetics of Caenorhabditiselegans. Genetics,1974, 77(1): 71-94   
[16] McCarter J,Bartlett B,Dang T,et al.On the control of oocyte meiotic maturation and ovulation in Caenorhabditis elegans.Dev Biol,1999,205(1): 111-128   
[17] Dong X,Liu O W,Howell A S,et al.An extracellular adhesion molecule complex patterns dendritic branching and morphogenesis. Cell,2013,155(2): 296-307   
[18] Brenner JF,Dew B S,Horton JB,et al.An automated microscope for cytologic research.J Histochem Cytochem，1971，24(1): 100-111   
[19] Russell M J, Douglas T S.Evaluation of autofocus algorithms for tuberculosis microscopy/29th International Conference of the IEEE EMBS，Engineering in Medicine and Biology Society，2007: 3489-3492   
[20] Tenenbaum J M. Accommodation in Computer Vision,Ph.D. Thesis, (Stanford University),1970   
[21] Krotkov E.Focusing.Int JComput Vision,1988,1(3): 223 -237   
[22] Schlang JF,Sanderson A C,Neuman,et $\boldsymbol { a l }$ .Implementation of automatic focusing algorithms for a computer vision system with camera control, Tech. Rep.CMU-RI-TR-83-14, Carnegie Mellon University,1983   
[23]Jarvis R A.Focus optimization criteria for computer image processing.Microscope,1976,24(2):163-180   
[24]Geusebroek J,Frans C,Smeulders A W M,et al.Robust autofocusing in microscopy. Cytometry,20oo,39(1): 1-9   
[25] Subbarao M,Choi T,Nikzad A. Focusing techniques.Opt Eng, 1993,32(11):2824-2836   
[26]Lee SY,KumarY,Cho JM,et al.Enhanced autofocus algorithm using robust focus mea-sure and fuzzy reasoning.IEEE Trans Circ Syst Video Tech,2008,18(9): 1237-1246   
[27]KautskyJ,FlusserJ,Zitove B,et al.A new wavelet based measure of image focus.Pattern Recogn Lett,2002,23:1785-1794   
[28] Groen F,YoungIT,Ligthart G.A comparison of different focus functions for use in autofocus algorithms.Cytometry,1985,6(2): 81-91   
[29] Vollath D.Automatic focusing by correlative methods.JMicrosc, 1987,147(3): 279-288   
[30] Vollath D.The influence of the scene parameters and of noise on the behaviour of automatic focusing algorithms.J Microsc,1988, 151(2): 133-146   
[31]Firestone L,Cook K,Culp K,et al.Comparison of autofocus methods for use in autofocus algorithms.Cytometry,1991,12(3): 195-206   
[32]Zeder M,Pernthaler J.Multispot live-image autofocusing for high-throughput microscopy of fluorescently stained bacteria. Cytometry,2009,75A(9): 781-788

# 自动对焦算法评估线虫脂滴图像的研究

张翔1，2)\*\* 贾策²谢康2)(华中科技大学生命科学与技术学院，武汉430074；2中国科学院生物物理研究所，北京100101)

摘要自动对焦是实现线虫自动化筛选的一个重要步骤．在光学显微镜系统中，通过采集同一个视野下不同焦面的图像，再通过清晰度评价函数对这些图像进行运算，得到的最大值被认为是最佳对焦位置．在本研究中，对16种常用的自动对焦算法以及最近提出的一些算法进行了评估，通过评估找出最适合线虫脂滴图像的自动对焦算法，从而搭建一套线虫脂滴自动化筛选系统．同时就对焦精度、运算时间、抗噪声能力、对焦曲线等特征进行了分析评价，结果表明，大多数算法对线虫脂滴图像都有较好的表现，特别是绝对 Tenengrad算法在对焦精度上有最好的表现，我们将优选该算法应用到线虫脂滴自动化筛选系统中.

关键词线虫脂滴，自动对焦算法，自动化筛选学科分类号Q334，Q336

DOI:10.16476/j.pibb.2015.0189