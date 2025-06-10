Article

# A Moving Ship Detection and Tracking Method Based on Optical Remote Sensing Image of Geostationary Satellite

Wei $\mathbf { Y } \mathbf { u } ^ { \ 1 , 2 , 3 ^ { * } }$ ,Hongjian You 1,2,3,Peng $\mathbf { L } \mathbf { v } ^ { 2 , 3 }$ , Yuxin ${ \bf H u } ^ { 1 , 2 , 3 }$ , and Bing Han 1,2,3

Citation:Lastname,F.; Lastname,F.; Lastname,F.Title. Sensors 2021,21, x.https://doi.org/10.3390/xxxxx

Academic Editor:Firstname Lastname

Received: date Accepted: date Published: date

Publisher's Note:MDPI stays neutralwith regard to jurisdictional claims in published maps and institutional affiliations.

Copyright: $\circledcirc$ 2021 by the authors. Submitted for possible open access publication under the termsand conditions of the Creative Commons Attribution (CC BY) license (https://creativecommons.org/license $\mathrm { s / b y / 4 . 0 / ) }$ ：

1University of Chinese Academy of Sciences, Beijing 10o049, China; hjyou@mail.ie.ac.cn (H.Y.); LvPeng@mail.ie.ac.cn(P.L.);han_ bing@mail.ie.ac.cn (B.H.)   
2Key Laboratory of Technology in Geo-Spatial Information Processng and Application Systems, Chinese Academy of Sciences,Beijing 100190, China   
3Aerospace Information Research Institute,Chinese Academy of Sciences, Beijing 100194, China \*Correspondence: yuwei@mail.ie.ac.cn; Tel.: +86-10-588-7208-8958

Abstract: The geostationary optical remote sensing satelite has the advantages of high temporal resolution and wide coverage, which can continuously track and observe ship targets on the sea in a large range.However, the ship targets in geostationary satelite remote sensing image are usually small and weak,and are easilyaffected by cloud,island and other factors,which brings great difficulty to the detection of ship targets. This paper proposes a new method for detecting ships moving on the sea surface from geostationary optical remote sensing images: Firstly, the adaptive nonlinear gray stretch (ANGS) method is used to enhance the image to highlight the small and weak ship targets.Secondly,a multi-scale dual-neighbor difference contrast measure (MDDCM) method is designed to detect the position of the candidate ship target.Then, the shape characteristics of each candidate aera isanalyzed to remove false ship targets.Finally,the joint probabilitydata association (JPDA)method is used for multi-frame data association and tracking. Experiments show that the proposed method can efectively detect and track moving ship targets in GF-4 satelite optical remote sensing images,and the method has beter detection performance compared with other classical methods.

Keywords: geostationary orbit satellites; GF-4 satelites; ship detection; ship tracking; visual saliency; data association;

# 1. Introduction

Surveillance of sea-surface ships has great significance to the economic development of sea areas,marine environmental protection,marine ship management, and fishery safety supervision [1]. With the rapid development of aerospace technology, sensor technology, computer technology and other technologies, satellite remote sensing technology has developed rapidly and has become an important means of maritime ship monitoring [2]. For many years, Synthetic Aperture Radar (SAR) images are often used as an important means of ship detection and tracking because SAR images are less affected by weather and time. Compared with SAR satelite images, optical satellite remote sensing images can better reflect the shape of ships and are easy to recognize and interpret manually. In recent years, high-resolution optical remote sensing images from Low Earth Orbit (LEO) satellites are often used to detect and identify ships on the sea [3-8], because high-resolution optical remote sensing images can display rich information about the shape and texture of ship targets. However, the disadvantages of small coverage and long revisit period of LEO satellites make it unable to meet the requirements of real-time and continuous monitoring of ship targets moving on the sea surface. Geostationary Orbit (GEO) satellites can continuously observe a large area, and have significant advantages such as wide observation range and short observation period [9]. Therefore, the use of

GEO satelites for near real-time monitoring and tracking of maritime ships can quickly obtain dynamic motion information such as the position, heading, speed,and trajectory of moving ships [10]. In 2015, China launched gaofen-4 (GF-4),a medium resolution optical remote sensing satelite in geostationary orbit, which has multiple observation modes, such as gaze mode and cruise mode,and can perform near real-time observation of ship targets moving on the sea [11-14].

The extraction of candidate ship targets and the removal of false targets (islands, clouds) are two key issues for ship detection in optical images.At present, the mainstream target detection methods of optical remote sensing image include: detection method based on gray statistical features,detection method based on deep learning and detection method based on visual attention mechanism. Methods based on gray statistical features [3][14][15] use the feature that the gray value of ships or their wakes is significantly higher than that of the sea surface for detection, but this type of method can only be applied to the absence of clouds,which is easy to be disturbed by clouds and islands, causing false alarms or missed detections; The target detection method based on deep learning [16][17][18] extracts the texture and geometric features of the target for detection. However, due to the lack of texture information of the target in the GEO optical image, the target detection method based on deep learning cannot be applied to medium-resolution and low-resolution remote sensing images. The method based on visual attention mechanism [19][20] can quickly and accurately extract regions of interest from complex scenes, and the contrast mechanism,multi-resolution representation, size adaptation and other characteristics of human vision system (HVS) make it efficient and robust in small target detection.

Generally, the gray value of ship targets is much lower than that of clouds and islands in optical remote sensing images. Due to the long imaging distance, coupled with atmospheric attenuation and cloud occlusion, it is difficult to see the ship itself in the optical remote sensing image of GEO satellite with medium resolution,and it is not easy to detect the ship directly. During the movement of the ship,a wake will be formed behind the direction of movement, and the spread area of the wake is always larger than the ship itself. Moreover, compared with sea surface and hull ship wake often has stronger optical reflection characteristics, which can become the main feature of moving ship for detection. Therefore, detecting and analyzing the wake of moving ships is an effective means to detect moving ships on the sea surface.At present, some researchers have carried out research on ship target detection and tracking methods based on GEO optical images [15] [21] [22] [23], but these methods do not fully consider the wake information of moving ships,the ability to resist cloud and island interference is insufficient, which is easy to cause false alarms ormissed detection.

The core issue of ship tracking is data association. Classical data association methods include Nearest Neighbor (NN) data association methods, various improved methods based on NN,and Joint Probability Data Association (JPDA) methods,and Multiple Hypothesis Tracking (MHT) method.[21] uses the MHT method to achieve the multi-frame GF-4 optical satellite remote sensing image ship target associated tracking, while suppressing false alarms.[22] uses the DCF-CSR algorithm to track ship targets in the remote sensing image of geosynchronous orbit optical satellite. Considering that the track crossing will not occur at the same time for ships moving on the sea, the calculation of MHT method is complicated, so JPDA method is more suitable for ship tracking.

This paper analyzes the wake characteristics of sea moving ships, and proposes a moving ship detection and tracking method based on optical remote sensing images of GEO satellites. The research object involved is GF-4 satelite panchromatic remote sensing images. Firstly, the ANGS method is used to enhance the optical remote sensing image to suppress the bright cloud and sea clutter in the image and highlight the weak ship wake. Secondly, based on the visual saliency theory，we propose a multi-scale dual-neighbor difference contrast measure (MDDCM) method, which calculates the saliency map of the image and obtains the location of the salient target; Then, the wake shapes of moving ship targets are analyzed,and the false targets such as speckle clouds are removed from the candidate targets by the shape verification of ship wakes; Finally, JPDA method is used to carry out data association and multi-target tracking for multi-frame images to obtain the speed and track of real moving ship targets,and further remove the false targets such as stationary islands.

The following chapters are arranged as follows: In Section 2, we analyze the imaging characteristics of GF-4 image and the moving ship wake characteristics in the image; In section 3, the methods proposed in this paper are described in detail, including image enhancement method, target detection method, data association method, etc. In section 4, the experimental results and analysis of our method are explained.In section 5, we draw the conclusion.

# 2.Analysis of ship wake characteristics in GF-4 Satellite optical remote sensing im ages

The spatial resolution of GF-4 image is $5 0 \mathrm { m }$ . A ship target with several hundred meters in length and tens of meters in width occupies only a few pixels in the GF-4 image. Moreover, many hulls may be coated with stealth materials and lack reflective features, making them difficult to detect directly. When the ship is moving, regular distribution of ripples will be generated in the tail, which is the wake of the ship, wake detection is an effective way to detect the ship,so this paper analyzes the characteristics of the wake to detect the ship target.

The wake of a ship is mainly caused by the force between the hull(propeller) and the sea when the ship moves on the sea,which makes the sea water in the subsurface rise to the surface, thus forming the wake. Normally, the width of the wake is about 1 to 3 times the width of the ship,and the length of the wake is 1 to 20 times the length of the ship. The wake of a moving ship is mainly composed of kelvin wave, divergent wave, transverse wave, turbulent wave and breaking wave, as shown in Figure 1. The performance of wake in different detection methods is also different.For example,in SAR remote sensing images, kelvin wave, divergent wave, shear wave and broken wave can be observed. And kelvin wave, divergent wave, shear wave, turbulent wave and broken wave can be observed in high resolution optical remote sensing images.In the GF-4 satellite optical remote sensing image, we can only see turbulent waves. The observed wake of turbulent wave appears as a spindle-shaped bright area in the GF-4 image,and its brightness and width decrease continuously along the opposite direction of the ship's motion. The main factors affecting the turbulence wake size in GF-4 images are ship size and sailing speed.

![](images/82ccc246763aec277960c6e3c1bbcb633d00a4b7a07f1bb16e0264e41bbaeb0c.jpg)  
Figure 1. Wake composition of moving ship.

The coverage of GF-4 satellite remote sensing image is $5 0 0 \mathrm { k m } \times 5 0 0 \mathrm { k m } .$ ,that is,10,000 pixels $\times 1 0 , 0 0 0$ pixels. Figure 2(a) shows a real GF-4 image.In order to better analyze the characteristics of the GF-4 satellite optical remote sensing image and the ship wake, a

$5 0 \mathrm { k m } \times 5 0 \mathrm { k m }$ (1000pixelsx1oooPixels) area of interest is selected from the original image for analysis and illustration, which is shown in Figure 2(b).

![](images/ac901f2d88d099dea287f60471c21a0270840180214b1082f5e06078b740ab6e.jpg)  
Figure 2. (a) Panchromatic remote sensing image of GF-4 satellite; (b) Enlarged view of the red area.

The raw gray scale of GF-4 image is 16bit, and the theoretical maximum gray value is 65536.Figure 3 shows the comparison of Figure 2(b) before and after stretching.Figure 3(a) is the two-dimensional(2D) view of the original GF-4 image,and Figure 3(b) is the 2D view of the stretched GF-4 image. Figure 3(c) is the three-dimensional(3D) view of Figure 3(a). We can see that extremely bright bad pixels appear at (245,448) and dark bad pixels appear at (672,966). Therefore, it can be concluded that in GF-4 images, the maximum and minimum gray values are often bad pixels. In addition, the gray value difference between cloud and sea is not obvious,and the gray value change is mainly reflected in the floating change of cloud brightness, and the ship wake can hardly be found.Figure 3(b) is the 3D view of stretched GF-4 image. It can be seen that the gray difference between cloud and sea background is enlarged, the bad pixels at (245,448) and (672,966) are suppressed, and the ship wakes at (713,131) and (944,291) are highlighted. It is more conducive to the detection of ship wake later.

![](images/0a8fae8d7fda411d684d6668fc5cc511c9812aaab176348b8b89942b4e6d7e34.jpg)

![](images/53b0595caaaa82bbcbedfbd0e7f119ef77d0a5282340eff5e50cbe830e7ab8bc.jpg)

![](images/a78dc2efd5e3f5d48927e60bea196e32d9a67653804dcf5375c0cc9de8049be9.jpg)  
Figure3.(a)2Dviewof theoriginal GF-4sateliteimage;(b)2Dviewofthe stretched GF-4sateliteimage;(c)3Dviewof the original GF-4 satellite image (d) 3D view of the stretched GF-4 satellite image.

GF-4 satellite optical remote sensing images often contain cloud clutter, ship wakes, and flaws. Figure 4 shows an enlarged view of the ship's wake, cloud clutter,and flaws in the area of Figure 2(b). After the analysis of the image, we can find that 1) The GF-4 satellite optical remote sensing image contains a lot of bright clouds,and the gray value of the cloud is higher than that of the ship's wake; 2) In the process of sea surface movement, the ship will form obvious wake,and the gray value of wake is higher than the sea background; 3) Wakes of different ships have different sizes and brightness, which are related to the size of the ship itself and the speed of the ship; 4) Due to the very harsh electromagnetic radiation environment of the stationary orbit, some bad pixels appeared in the camera of the GF-4 satelite. There are several bright and black flaws in the remote sensing image,but the number of pixels of the flaws is less than ship wake; 5) The brightness of the cloud is variable,including large areas of bright cloud or local bright spot-shaped cloud.

![](images/cbd33d32c9f6edd824f8935a3fc446569f81b8aaff7c75c1a63793b70637cdb2.jpg)  
Figure 4.(a) stretched image of GF-4; (b) enlarged view of ship wake in red box areal (c) enlarged view of ship wake in red box area2;(d) enlarged view of flaw point in red box area3 (e) enlarged view of spot-shaped cloud in red box area4.

# 3.The Method Proposed

According to the above analysis, ship targets in GF-4 satellite optical remote sensing images are easily disturbed by clouds and flaws,and the brightness of ship wakes is lower than that of clouds and higher than that of sea background.Image stretching can better enhance ship wakes in images. The ship wake in the image is a turbulent wake with a certain shape, but it is still weak and occupies a small number of pixels in the image. At the same time, GF-4 satelite is a video-like satelite, which can continuously scan the observation area and form image sequence.Therefore, the method of multi-frame association can be used to confirm the moving ship and remove false alarms.The target detection and tracking framework of sea-surface moving ships proposed in this paper is shown in Figure 5.

![](images/b3fdb10b67a7afd9b22feb1162f9e53a915a1cfa9d3b2ae2f18b8b9e6390241a.jpg)  
Figure 5.Proposed detectionand tracking framework

The method proposed in this paper includes four stages: image enhancement, saliency detection, shape check and multi-frame association. (1) Image enhancement stage: ANGS is used to enhance each frame of GF-4 image sequence to improve image contrast and highlight ship wakes in the image; (2) Target detection stage: Target detection based on visual saliency is the focus of this paper. MDDCM method is used to calculate the saliency map, and then the image is segmented according to the dynamic threshold value to obtain the location of the candidate ship target. (3) Shape verification stage: Based on the detection results of MDDCM, the region where the target is located is binarized to obtain the shape of the ship wake and remove the false targets that do not meet the characteristics of the ship wake. (4) Multi-frame tracking stage: JPDA method is used for data association to confirm the real moving ship target from the candidate targets in multi-frame images. In addition, ship speed and its track are obtained,and false targets such as stationary islands are further removed.

# 3.1.GF-4 satellite optical remote sensing image enhancement

As analyzed above,we found that the pixels with the greatest brightness in GF-4 satellite optical remote sensing image is often a flaw,and the brightness of the cloud is generally higher than that of the ship wake. Therefore, in order to effectively detect ships on the sea surface, it is necessary to enhance GF-4 image to enhance the contrast between ship wake and sea background. Generally, image enhancement methods are divided into spatial domain enhancement method and frequency domain enhancement method. Due to the uncertain size and shape of ship wake, frequency domain enhancement method is not suitable for image enhancement. Commonly used spatial domain image enhancement methods include histogram equalization， Laplace transform, Log transform, gamma transform and so on. In this paper, an adaptive nonlinear gray stretch (ANGS) method is used to suppress high-brightness clouds,and at the same time, to enhance the brightness of the ship wake.The formula of ANGS is as follows:

$$
F \left( x , y \right) = \frac { 1 } { 1 + \left( \displaystyle \frac { m } { G \left( x , y \right) + \mathrm { e } p s } \right) ^ { E } }
$$

Where, $\boldsymbol { G } \left( \boldsymbol { x } , \boldsymbol { y } \right)$ is the original remote sensing image of GF-4, $m$ is the mean value of the original image $G \left( x , y \right) , E$ is the stretch factor,which controls the slope of the stretch curve, eps is a very small value to prevent the formula from being meaningless when $G \left( x , \right.$ $y ) = 0$ $E$ is an empirical value,and different stretching factor $E$ has different stretching effects on the image. The larger the value of $E$ is, the greater the gray contrast near the mean value $m$ will be,and the gray value compression of high and low gray levels will also be stronger.

# 3.2.MDDCM method for ship wake detection

According to the previous analysis, the gray value of ship wake in GF-4 image is lower than that of clouds and land. Ship wake generally only occupies a dozen or even a few pixels in GF-4 image,which is a small and dim target. In recent years,algorithms based on HSV show good performance in dim and small targets detection. HVS algorithms generally use the local gray difference between the target and the surrounding background to calculate contrast, such as Local Contrast Measure (LCM) [25] and the improved algorithm based on LCM. Based on HVS theory, we propose a multi-scale dualneighbor difference contrast measure (MDDCM) method for ship wake detection in GF-4 images.

# 3.2.1.DDCM window structure

The traditional LCM window is shown in Figure 6(a), including 9 sub-blocks, namely the central block and the adjacent 8 sub-blocks.The traditional LCM algorithm measures the visual salience of the central block by calculating the contrast between the central block and the surrounding 8 sub-blocks.

![](images/8d15b4ad6718bb8be7e849d6602f61d2c4e97258c8915b5634e0a03b61975506.jpg)  
Figure 6. (a) structure of LCM; (b) slide whole image by DDCM window; (c) structure of DDCM

Different from the traditional LCM window, we designed a dual-neighborhood window, which includes the center region, the middle region and the background region. By sliding the dual-neighborhood window on the whole image, the local contrast of the image is calculated and the saliency map is generated.The sliding process is shown in Figure 6(b).The structure of the dual -neighborhood window is shown in Figure 6(c), which contains a central sub-block, 8 middle sub-blocks M1-M8 and 16 background sub-blocks B1- B16.

# 3.2.2.DDCMlocal contrast calculation

From the previous analysis, we know that the ship's wake appears as a spindleshaped bright area in the GF-4 image. When the wake is small it appears as a gaussian spot, and when the wake is large, it appears as a long strip. The distribution of gaussian spot-like ship wake on the DDCM window is shown in Figure 7(a).Since the course of the hull is arbitrary,we use four angles of Figure 7(b), Figure 7 (c), Figure 7 (d) and Figure 7 (e) to roughly describe the distribution of strip-like ship wake on the DDCM window

![](images/6e33549f12277c1390bc78c724a76ed72df206bdea38d5426cad669aae74c5d6.jpg)  
Figure 7. Distribution of ship wake in DDCM window

Based on DDCM window structure, the difference between the three regions is used to measure the local contrast.The contrast between the central sub-block $\mathrm { \Delta T }$ and each subblock $M _ { i }$ in the middle region is represented by $d ( T , M _ { i } )$ ，and the expression of $d ( T , M _ { i } )$ is:

$$
d ( T , M _ { i } ) = \left\{ \begin{array} { l l } { { m e a n _ { T } - m e a n _ { M _ { i } } } } & { { \quad i f \quad m e a n _ { T } - m e a n _ { M _ { i } } > 0 } } \\ { { 0 } } & { { \quad e l s e } } \end{array} \right. , i = 1 , 2 , 3 . . . 8
$$

Where, $m e a n _ { { _ T } }$ represents the gray mean of the central T sub-block, $m e a n _ { M _ { i } }$ repreients the gray mean of the middle sub-block $M _ { i }$ ,and $i = 1 , 2 \dots 8$

The contrast between the center sub-block $\mathrm { \Delta T }$ and the background region is represented by $D _ { { _ B } }$ ， and the expression of $D _ { { } _ { B } }$ is:

$$
{ \bf D } _ { B } = \left\{ \begin{array} { l l } { m e a n _ { T } - \operatorname* { m a x } ( m e a n _ { B _ { k } } ) \quad } & { \mathrm { i f ~ } m e a n _ { T } - \operatorname* { m a x } ( m e a n _ { B _ { k } } ) > 0 } \\ { \quad 0 \quad } & { \mathrm { e l s e } } \end{array} \right. , k = 1 , 2 , 3 . . . 1 6
$$

Where, $m e a n _ { { _ T } }$ represents the gray mean of the central sub-block $\mathrm { T }$ meanBk represents the gray mean of the background sub-block $B _ { k }$ ，where, $k _ { \mathrm { \ell } } = 1 , 2 . . . .$ 16, $\operatorname* { m a x } ( m e a n _ { B _ { k } } )$ ） represents the maximum value of $m e a n _ { B _ { k } }$ in 16 background subblocks . Generally, the gray value of the central region where the ship wake is located is higher than that of the outer background region, so $D _ { { _ B } }$ can effectively suppress cloud clutter and highlight the ship wake.

Ship wakes are generally distributed symmetrically along the central axis. When the central sub-block of the DDCM window passes through the center of ship wake, part of ship wakes may be distributed in the middle region. Therefore, the contrast between the central region T and the middle region M can be expressed by $D _ { { } _ { m } }$ , and the expression of $D _ { { \scriptscriptstyle m } }$ is as follows:

$$
D _ { m } = \left\{ \begin{array} { c c c c c } { { d ( T , M _ { 3 } ) \times d ( T , M _ { 7 } ) } } & { { \mathrm { i f } } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 1 } } } } & { { o r } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 1 } } } } \\ { { d ( T , M _ { 4 } ) \times d ( T , M _ { 8 } ) } } & { { \mathrm { e l s e ~ i f } } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 2 } } } } & { { o r } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 1 } } } } \\ { { d ( T , M _ { 5 } ) \times d ( T , M _ { 1 } ) } } & { { \mathrm { e l s e ~ i f } } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 3 } } } } & { { o r } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 1 } } } } \\ { { d ( T , M _ { 6 } ) \times d ( T , M _ { 2 } ) } } & { { \mathrm { e l s e ~ i f } } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 4 } } } } & { { o r } } & { { \operatorname* { m a x } ( m e a n _ { M _ { i } } ) = m e a n _ { M _ { 3 } } } } \end{array} \right.
$$

Where, $\operatorname* { m a x } ( m e a n _ { M _ { i } } )$ )represents the maximum value of $m e a n _ { M _ { i } }$ for 8 sub-blocks in the middle region, and the sub-block corresponding to $\operatorname* { m a x } ( m e a n _ { M _ { i } } )$ may be the subblock where the ship wake symmetry axis is located. So, we use the sub-block perpendicular to the sub-block of $\operatorname* { m a x } ( m e a n _ { M _ { i } } )$ to calculate the contrast between the central region T and the middle region M.

Figure 8(a) shows the GF-4 satellite optical remote sensing image, which contains a ship wake with an angle of about $4 5 ^ { \circ }$ . When the DDCM window slides to the center of the ship wake, the mean value of $\mathrm { T }$ in the central region reaches the maximum value. Among the 8 sub-blocks $m e a n _ { M _ { i } }$ in the middle region, $m e a n _ { M _ { 3 } }$ has the largest gray mean, so $M _ { 3 }$ and $M _ { 5 }$ perpendicularto $M _ { 3 }$ are used to calculate $D _ { { \scriptscriptstyle m } }$ ，thatis, ${ \cal D } _ { m } = d ( T , M _ { 5 } ) \times d ( T , M _ { 1 } ) .$ （20

![](images/b9e56b023deaa54c58ee730b4c6e1760e4cac24259f6a68973a72d0be2349668.jpg)  
Figure8.(a)A ship wake in the GF-4 satelite optical remotesensing image (b)Ship wake covered by DDCM window.

If the size of the sub-block $\mathrm { T }$ in the central region of the DDCM window is $\mathbf { k } \times \mathbf { k } ,$ the visual saliency of the $\mathbf { k }$ -size DDCM can be expressed by $\mathrm { D D C M } _ { k }$ , and the formula for DDCMk is as follows:

$$
\mathrm { D D C M } _ { k } = D _ { { \mathrm { } } m } \times D _ { { \mathrm { } } B }
$$

Where, $D _ { { \scriptscriptstyle m } }$ is the contrast between the central region and the middle region, and $D _ { { _ B } }$ is the contrast between the central region and the background region. By setting the value of DDCM window size $k$ and using DDCM window to slide through the whole GF4 image, we can get a single-scale DDCM saliency map.

# 3.2.3.MDDCMlocal contrast calculation

Since the size of ship wake is variable,it is influenced by many factors such as hull size, sailing speed, image spatial resolution, etc.A single-scale DDCM window cannot be suitable for detecting ship wakes of all sizes. Therefore,we use the Multi-scale Dualneighbor Difference Contrast Measure (MDDCM) method to detect ship wakes.

The DDCM saliency map of size $\mathbf { k }$ can be represented as $\mathrm { D D C M } _ { k }$ , and the saliency of pixel $P ( i , j )$ in the image can be represented as $\mathrm { D D C M } _ { k } ( i , j )$ ,The expression of the saliency $\mathbf { M D D C M } _ { k } ( i , j )$ of pixel $P ( i , j )$ in the MDDCM algorithm is as follows:

$$
\mathbf { M D D C M } _ { k } ( i , j ) = \operatorname* { m a x } ( \mathbf { D D C M } _ { k } ( i , j ) ) , k = 2 , 3 , 4 , 5 \ldots \mathbf { N }
$$

Where, $\mathbf { k }$ is the size of DDCM, the minimum value is 2 and the maximum value is N.3   
Therefore, the MDDCM with the largest scale of K can be expressed as: 3

$$
\mathsf { M D D C M { = } m a x } ( \operatorname { D D C M } _ { k } ) , k = 2 , 3 , 4 , 5 { \ldots } \mathbf { K }
$$

3.2.3.Adaptive extraction of ship position based on MDDCM

After MDDCM calculation, the MDDCM saliency map of the image can be obtained. The contrast of the ship wake area has been enhanced, while bright flaws, random noise, cloud clutter and sea background clutter have been effectively suppressed,and the signalto-noise ratio(SNR) has been significantly improved. In order to extract the target, we normalize the saliency map to make it distributed between O and 1,and then use an adaptive threshold to segment the saliency map to obtain the location of the target. The expression of threshold $\tau$ used for saliency map segmentation in this paper is:

$$
\begin{array} { r } { \tau = \mu + \lambda _ { { \scriptscriptstyle t h } } \sigma } \end{array}
$$

Where, $\mu$ is the mean value of MDDCM saliency map, $\sigma$ is the standard deviation of MDDCM saliency map. $\lambda _ { { } _ { t h } }$ is the segmentation factor, usually ranging from 20 to 50. Using the threshold $\tau$ to segment the saliency map,we can extract the position of the target, which is the candidate ship.

# 3.3.Shape-based falsealarmremoval

The detection result of MDDCM saliency map can only get the position of candidate ships in the image,but it cannot show the size and shape of candidate ship.In fact, the extraction result in MDDCM saliency map is usually the center position of ship wake. Therefore, it is necessary to segment the target candidate region to obtain the contour information of the candidate ship after obtaining the location of the ship using MDDCM, and then we can use the shape verification to remove false targets such as spot-shaped cloud.

Based on the location of candidate target extracted by MDDCM, we extract 64 pixels $\times 6 4$ pixels regions of interest (ROI),and then use Otsu method to perform binary segmentation of ROI to separate target from sea surface background. The formula is as follows:

$$
\mathbf { S } ( x , y ) = \left\{ { 1 , S ( x , y ) \geq T } \right.
$$

Where, $\mathrm { T }$ is the segmentation threshold of Otsu method. For the segmented image, the connected region centered on the detection result of MDDCM saliency map is the ship region. The detection results of MDDCM saliency map often contains false alarms. Through binary segmentation of the target area, the target contour can be obtained,and then the target shape characteristics can be verified.

The spatial resolution of GF-4 satellite optical remote sensing image is $5 0 \mathrm { m } ,$ generally the width of ships is within $5 0 \mathrm { m } _ { \cdot }$ ， the maximum is not more than $1 0 0 \mathrm { m }$ . According to the above analysis, the wake width of the ship is about 1 to 3 times of the hull width,and the wake length is 1 to 20 times of the hullength.Therefore, the width of ship wake in GF-4 image is only a few pixels,while the length may reach dozens of pixels. Generally, the larger the wake width, the larger the size of the ship or the faster the motion speed, which means that the turbulent wake formed behind the ship willbe longer, so there is a positive correlation between the length and width of the ship wake.Based on this feature, we can verify the shape of targets and remove the false alarm targets that do not meet the shape characteristics of the wake.If the length of the smallest enclosing ellipse of the target area is $L e n g t h _ { \scriptscriptstyle T }$ , and the width is $W i d t h _ { { _ T } }$ . The length-to-width ratio is represented by $R _ { l w }$ · The width $W i d t h _ { { _ T } }$ and the length-to-width ratio $R _ { l w }$ of the ship's wake should meet a certain range.We use the following formula to verify the shape of the ship's wake:

$$
W i d t h _ { m i n } < W i d t h _ { _ T } < W i d t h _ { _ { m a x } }
$$

$$
R _ { _ { t h } } = \frac { W i d t h _ { _ T } + 1 } { 2 }
$$

$$
R _ { _ { l w } } = \frac { L e n g t h _ { _ { T } } } { W i d t h _ { _ { T } } } > R _ { _ { t h } }
$$

Where, $W i d t h _ { \operatorname* { m i n } }$ and $W i d t h _ { m a x }$ are the minimum and maximum value ranges of wake widths. Limiting the range of $W i d t h _ { \scriptscriptstyle T }$ can effectively remove small noise points, large clouds and islands,etc. $R _ { t h }$ is the adaptive threshold value associated with $W i d t h _ { \scriptscriptstyle T }$ . Using $R _ { t h }$ to verify the length-width ratio $R _ { l w }$ can better reflect the physical characteristics of ship wake.

# 3.5.Ship tracking based on JDPA

The GF-4 optical satellite is equipped with a staring camera. The shortest single-spectrum repetitive imaging time is only 5s,and the shortest full-spectrum repetitive imaging time is 10Os. It has video-like satelite characteristics and can meet the needs of tracking ship targets moving at high speeds at sea. [11]. Using GEO satellites to detect and track marine moving ships can obtain its moving track and estimate its movement trend.At the same time, it can further remove false alarm targets such as stationary islands,iregular clouds,and random noise by data association.

JPDA is a classic data association method. Its main idea is to comprehensively consider all targets and measurements.According to the association between all measurements and all targets.JPDA first establishes a confirmation matrix,and then lists all possible events based on the criterion that the target has at most one measurement information in a period,and a measurement has and only one source. Finally,all events are connected in probability to obtain the final status update value of each target.

In JPDA method, the predicted state equation of the target is defined as:

$$
{ \hat { X } } ^ { t } ( k | k { - } 1 ) = F ^ { t } ( k { - } 1 ) { \hat { X } } ^ { t } ( k { - } 1 | k { - } 1 )
$$

Where， $\hat { X } ^ { t } ( k | k { - } 1 )$ represents the state vector of $t$ at time $k$ predicted by time $k { - } 1$ ,and $F ^ { t } ( k - 1 )$ is the state transition matrix of $t$ at time $k { - } 1$ ：

The prediction vector of measurement target is defined as:

$$
\hat { Z } ^ { t } ( k | k { - } 1 ) = H ( k ) \hat { X } ^ { t } ( k | k { - } 1 )
$$

Where, $H ( k )$ represents the measurement target matrix.

According to the Kalman filter formula, the equation for calculating the status update is as follows:

$$
\hat { X } ^ { t } ( k | k ) = \hat { X } ^ { t } ( k | k - 1 ) + K ^ { t } ( k ) V ^ { t } ( k )
$$

Where, $K ^ { t } ( k )$ represents the Kalman gain matrix of $t$ at time $k$ ，and $V ^ { t } ( k )$ （204号represents the combined information of $t$ at time $k$ ：

Define the associated area as:

$$
\operatorname { A } ( k ) = \left[ \mathbf { z } \left( k \right) - { \hat { \mathbf { z } } } \left( k \mid k - 1 \right) \right] ^ { \mathrm { T } } \mathbf { S } ^ { - 1 } \left( k \right) \left[ \mathbf { z } \left( k \right) - { \hat { \mathbf { z } } } \left( k \mid k - 1 \right) \right] \leq \gamma
$$

Where, $\mathbf { S } ^ { - 1 } \left( k \right)$ represents the innovation covariance matrix at time $k$ ,and $\gamma$ is a fixed threshold,which can be obtained from the $\chi ^ { 2 }$ distribution table.

As an extension and optimization of the PDA method, the JPDA method mainly introduces the concept of joint events within the association cycle:

$$
\theta _ { i } \left( k \right) = \bigcap _ { j = 1 } ^ { M _ { k } } \theta _ { j t } ^ { i } \left( k \right)
$$

Where, $\theta _ { i } \left( k \right)$ is the joint associated event, $k$ is the time, $\theta _ { i } \left( k \right)$ is the $i$ th joint event at the time $k , M _ { k }$ represents the total number of measured targets at time $k$ ,and $\theta _ { j t } ^ { i } \left( k \right)$ represents the event that whether the measured target $j$ is related to track $t$ （20 at time $k$ in the joint event of $i$ . When $t = 0$ , it means that the measured target $j$ has no related events, that meansa false alarm.

JPDA method assumes that the states of different targets are independent of each other under historical measurement conditions.The state estimation can be converted into irrelevant estimation of different targets,and edge association probability needs to be calculated based on joint probability,that is,to calculate the sum of the associated events related to the target.

We use the target location extracted by the MDDCM method as the data source for data association (shape verification has been passed). Then, JDPA is used to associate the target data in multi-frame GF-4 image to obtain the ship target's track information and calculate the average speed. The candidate targets in GF-4 satelite image sequences often contain false targets. Therefore，we use constraints such as the minimum associated frames, the maximum target speed, the minimum target speed and the minimum moving distance to further remove false targets and filter the displacement of the stationary targets caused by the camera shaking.

# 4. Experiment and Analysis

Five groups of GF-4 satellite optical remote sensing image sequences are used for experiments,and the experimental results are analyzed.The effectiveness and performance of the proposed method are demonstrated by the results verification and comparison with other methods.

# 4.1.Experimental data

The GF-4 satellite has imaging capabilities in the visible near-infrared spectrum and mid-wave infrared spectrum.There are 6 imaging bands B1-B6 in the visible near-infrared spectrum, of which the B1 band is the panchromatic band. The wake of moving ship on the sea surface is more significant in the B1 panchromatic band. We use the panchromatic optical remote sensing images of GF-4 satellite as experimental data.The width of the GF4 image is $5 0 0 \mathrm { k m } \times 5 0 0 \mathrm { k m } ,$ which is 10000 pixels $\times 1 0 0 0 0$ pixels.The ship's wake generally only occupies a few pixels in the remote sensing image.In order to better observe the ship's wake and verify the experimental results,we cut out an area of $2 5 \mathrm { k m } \times 2 5 \mathrm { k m }$ (500 pixels $\times 5 0 0$ pixels) from the original image as the experimental area.In order to fully verify the effectiveness of the proposed method, 5 groups of GF-4 satellite optical remote sensing panchromatic image sequences are used as experimental data, and the experimental data included various scenes, such as few clouds, thick clouds, speckled clouds, islands,and multiple targets.Moreover,the size of the ship's wake is also differentin these experimental data, in order to better verify whether the method can support target detection of different scales. The description of the experimental data is shown in Table 1:

Table1.Data used in the experiment   

<html><body><table><tr><td> Image Sequence</td><td>Band</td><td>Number of Images</td><td>Features of the scene</td></tr><tr><td>Image Sequence1</td><td>B1(panchromatic)</td><td>28</td><td>Multi ship</td></tr><tr><td>Image Sequence2</td><td>B1(panchromatic)</td><td>28</td><td>Having island</td></tr><tr><td>Image Sequence3</td><td>B1(panchromatic)</td><td>28</td><td>Dense cloud</td></tr><tr><td>Image Sequence4</td><td>B1(panchromatic)</td><td>24</td><td>spot-shaped cloud + Thick clouds</td></tr><tr><td> Image Sequence5</td><td>B1(panchromatic)</td><td>12</td><td>Thick clouds</td></tr></table></body></html>

# 4.2.Detection and comparison

# 3.1.1. Detection

According to our detection and tracking framework,ANGS should be used to stretch single frame image to improve image contrast and highlight ship target before ship target detection of single frame remote sensing image. According to the stretching experiment of several groups of GF-4 satellite panchromatic optical remote sensing images, it is found that the stretching effect is beter when the value of $E$ is set between 6 and 8. We set parameter $E$ to 6 in the experiment.MDDCM algorithm is used for multi-scale target detection based on the enhanced image.The range of MDDCM window size depends on image resolution and target size. According to the previous analysis, the width of the ship's wake of the GF-4 image is about a few pixels,and the length may reach dozens of pixels.Therefore, the size $k$ of the MDDCM window is set in the range of $3 { \sim } 6$ for multi-scale saliency map calculation. Then, the binary segmentation of MDDCM saliency map needs to determine the segmentation threshold $\tau$ between the target and the background. The segmentation factor $\lambda _ { { } _ { t h } }$ of $\tau$ is an empirical value, and we set $\lambda _ { { } _ { t h } }$ as 20. The parameter descrip tion is shown in Table 2:

Table 2.Parameter values in ship detection experiments   

<html><body><table><tr><td>Method</td><td>Symbol</td><td>Parameter description</td><td>Value</td></tr><tr><td rowspan="2">ANGS</td><td>E</td><td>stretch factor</td><td>6</td></tr><tr><td>Kmin</td><td>min size of center window</td><td>2</td></tr><tr><td rowspan="2">MDDCM</td><td>Kmax</td><td>max size of center window</td><td>4</td></tr><tr><td></td><td>segmentation factor</td><td>20</td></tr></table></body></html>

According to the parameter values in Table 2,we use ANGS method and MDDCM method respectively to carry out image enhancement and saliency map calculation for five groups of GF-4 image sequences,and then detect candidate ship targets by binarization segmentation. The experimental results are shown in Figure 9:

![](images/997356d5a8c09124f0b66da76aed7104ec0563bed049f00fc2107b9b860f4dad.jpg)

Figure 9.(a)original image;(b)3Dview of original image; (c)stretched image by ANGS;(d)3D view of stretched image by ANGS; (e)saliency map by MDDCM; (f) 3D view of saliency map by MDDCM; (g)Ship wake detection results.

By comparing Figure 9(b) and Figure 9(d),itcan be found that the ANGS method can effectively suppress bright clouds and islands, improve image contrast and visual effects, and highlight ship targets. According to Figure 9(e) and Figure 9(f), it can be found that MDDCM method can significantly suppress background and improve the SNR of the image. Figure $9 ( \mathrm { g ) }$ is the detection result after the binary segmentation of the MDDCM saliency map. It can be seen that: The first group of experimental data contains 6 ship targets, and the ship passes through the cloud, our method can detect all 6 ship targets； The second group of experimental data contains islands and ship targets. The brightness of islands is much higher than that of ship targets. Our method can detect ship targets and suppress high-brightness islands; The third group of experimental data contains two ship targets that can be detected; The lower right corner of the fourth group of experimental data contains a ship target with significant wake, which can be accurately detected by our method. At the same time, due to the influence of spot-shaped cloud, false alarms appear, which can be further removed by the following methods in this paper; The fifth experiment included two ship targets with significant wakes, both of which could be detected.

# 3.1.1. Comparison

We have carried out comparative experiments between MDDCM Method and other visual saliency methods,includingLCMmethod[25]and Multiscale patch-based Contrast Measure (MPCM) method [26].Local Peak signal-to-noise Ratio (PSNR) method [21], and Spectral Residual (SR) method based on frequency domain [27]. Experimental parameter setings of MDDCM are shown in Table2, and experimental parameter settings of other methods are shown in Table 3:

Table 3.experimental parameter values of other visual saliency methods   

<html><body><table><tr><td>Method</td><td>Symbol</td><td>Parameter description</td><td>Value</td></tr><tr><td rowspan="2">LCM</td><td>K</td><td>size of center window</td><td>3</td></tr><tr><td></td><td>segmentation factor</td><td>5</td></tr><tr><td rowspan="2">MPCM</td><td>K</td><td>size of center window</td><td>3、5、7</td></tr><tr><td></td><td>segmentation factor</td><td>20</td></tr><tr><td rowspan="3">PSNR</td><td>Kin</td><td>size of inner window</td><td>10</td></tr><tr><td>Kout</td><td>size of outer window</td><td>20</td></tr><tr><td>th</td><td>fixed segmentation threshold</td><td>4</td></tr><tr><td rowspan="2">SR</td><td>n</td><td>size of convolution kernel</td><td>3</td></tr><tr><td></td><td>segmentation factor</td><td>20</td></tr></table></body></html>

Using the five groups of experimental data introduced above, the comparative experimental results of ship detection are shown in Figure 10:

![](images/4d47cbb9ad10fc1d1c247cdd22300db742963a62986fe9b9afd45625202b68ae.jpg)  
(a) Stretched image by ANGS

![](images/ad56e8b117a70fc49139c7de63687a2c0de5741a55e4f8354abfcce8fcbcf673.jpg)

![](images/eda749618c9e7eb8a5d70d01fa185642e64f2468c655f455209b72596efd7b24.jpg)  
(k) ship detection result of saliency map by MDDCM   
Figure10. (a)Stretched image by ANGS; (b)3D view of saliency map byLCM;(c) ship detection result of saliency map by LCM;(d)3D view of saliency map by MPCM;(e)ship detection result of saliency map by MPCM;(f)3D view of saliency map by PSNR;(g)ship detection result of saliency mapby PSNR; (h)3D view of saliency map by SR;(i) ship detection result of saliency map by SR;(j)3D view of saliency map by MDDCM;(k)ship detection result ofsaliency map by MDDCM.

From Figure 10,we can see that: LCMalgorithm is prone to the interference of clouds and islands.In the second group of data, it missed the detection of ships,while in the fourth group of data, it missed the detection of ship targets with obvious wakes, and a large number of false alarms appeared in the fifth group of data.This is because the LCM algorithm uses the maximum gray value of the center window instead of the average gray value to participate in the calculation,and the window size is fixed. Moreover, it should be noted that the segmentation factor $\lambda _ { { \scriptscriptstyle t h } }$ of the LCM saliency map is set to 5,because the contrast of the LCM saliency map is not as good as other visual saliency methods. If the default value of $\lambda _ { { } _ { t h } }$ is 20,it is almost impossible to segment and detect the target. MPCM has a good detection performance, but there are some false alarms appear in the first and fourth group of data. At the same time, MPCM algorithm has a very good background suppression ability, which can improve the SNR of images. The background suppression ability of the PSNR method provided by the paper [21] is not good, resulting in the low SNR of the saliency map. Some targets are missed in the first group of data, and a large number of false alarms appeared in the fourth group of data, indicating that the anti-interference ability of PSNR is insufficient. This may be due to the segmentation threshold provided in literature [21]. Fixed threshold will make it difficult to balance the relationship between missed detection and false alarm. SR method also has good detection performance, but its background suppression ability is mediocre. It missed some targets in the first group of data and failed to detect targets in the second group of data, which may be related to the value of the segmentation factor (set as 2O).Its detection effect in the third and fourth group of data is mediocre. In contrast, our MDDCM method successfully detected all targets with a low false alarm rate and excellent background suppression ability, which can greatly improve SNR and has the best detection performance among all comparison methods. Although there are false alarms in the second and fourth group of data, these false alarms can be removed by our follow-up method.

# 4.3.Shape-based false alarm removal

According to the previous analysis of the image resolution,as well as the size and shape of the ship's wake. The value of $W i d t h _ { \operatorname* { m i n } }$ is set to 2, the value of $W i d t h _ { m a x }$ is set to $6 ,$ and $R _ { t h }$ is the adaptive threshold,which is determined by Width.The purpose of shape verification is to further remove false alarms from candidate ship targets, especially to avoid the interference of spot-shaped cloud to target detection. Table 4 shows the shape verification results of some candidate ship targets.

Table4.Shape-based verification   

<html><body><table><tr><td>Candidate Target</td><td>Width</td><td>Length</td><td>Rlw</td><td>Rth</td><td>Verification</td></tr><tr><td></td><td>2.6277</td><td>11.0888</td><td>4.2200</td><td>1.8138</td><td>True</td></tr><tr><td></td><td>3.1409</td><td>8.6349</td><td>2.7492</td><td>2.0704</td><td>True</td></tr><tr><td></td><td>3.2342</td><td>10.2844</td><td>3.1799</td><td>2.1171</td><td>True</td></tr><tr><td></td><td>4.4772</td><td>7.1736</td><td>1.6022</td><td>2.7386</td><td>False</td></tr><tr><td></td><td>3.6485</td><td>12.4416</td><td>3.4100</td><td>2.3243</td><td>True</td></tr><tr><td></td><td>3.0827</td><td>4.9899</td><td>1.6187</td><td>2.0414</td><td>False</td></tr><tr><td></td><td>6.2077</td><td>10.1860</td><td>1.6409</td><td>3.6038</td><td>False</td></tr><tr><td></td><td>3.8072</td><td>8.6802</td><td>2.1068</td><td>2.4036</td><td>False</td></tr><tr><td></td><td>5.0590</td><td>7.0992</td><td>1.4033</td><td>3.0295</td><td>False</td></tr><tr><td></td><td>3.0048</td><td>13.3384</td><td>4.4391</td><td>2.0024</td><td>True</td></tr></table></body></html>

The candidate ship targets detected by MDDCM algorithm often contain false alarms, such as small islands and spot-shaped cloud, which tend to have high brightness. Figure 11(a) is the detection result of MDDCM algorithm, where target C is an island and target A is a moving ship. The $R _ { \scriptscriptstyle { l w } }$ of target C does not meet the threshold $R _ { t h }$ , so it is removed from the candidate target, and the result is shown in Figure 11(b).

![](images/e8ab360c0cc20c3c23fca927d51364a44e0b139226b3f2bbd20993de733bd882.jpg)

# 4.4. Ship Tracking

After the target detection and shape verification of single frame image in the image sequence, the candidate ship of single frame image can be obtained. Taking the center pixel of each candidate target as the data source, the multi-frame data association of the image sequence can be carried out to obtain the track and speed of the ship.At the same time, conditions such as the minimum number of associated frames, the maximum speed, the minimum speed,and the minimum moving distance can be used to further remove false targets. The corresponding parameter settings are shown in Table 5:

![](images/6cb9007a7025e9ca6aec2cfaad4b2318db4996773f8d93757656d1973db0a237.jpg)  
Figure 11. (a) detection result of MDDCM; (b) false alarm removal by shape verification.

Table 5. Constraint parameters for ship tracking   

<html><body><table><tr><td>Item</td><td>value</td></tr><tr><td>Minimum association frames</td><td>3</td></tr><tr><td>Minimum speed</td><td>10 km/h</td></tr><tr><td>Maximum speed</td><td>80 km/h</td></tr><tr><td>Minimum distance</td><td>2km</td></tr></table></body></html>

Figure 12 shows the process of associating with three frames of data by JPDA method. The previous method detects two targets A1 and B1 in Figure 15(a), A2 and B2 in Figure 12(b),and A3 and B3 in Figure 12(c).The track and speed of target A are obtained successfully by associating three frames of data. However, the false alarm target B is a fixed island, which is not associated with a stable track, so it is filtered out.

Figure 12. (a)frame1 withtarget A1 and B1(b)frame2 withtarget A2 and B2(c)frame 3 with target A3 and B3 (d) data association result with real target A and false target B

JPDA algorithm is used for data association of candidate targets detected by five groups of experimental data,and the obtained track information is shown in Table 6:

Table 6.Tracking result   

<html><body><table><tr><td>Image Sequence</td><td>Total frames</td><td>Track Id</td><td>association frames Mean Speed</td><td></td></tr><tr><td rowspan="5">Image Sequencel</td><td rowspan="5">28</td><td>Track1</td><td>28</td><td>48.75 km/h</td></tr><tr><td>Track2</td><td>28</td><td>41.93 km/h</td></tr><tr><td>Track3</td><td>22</td><td>47.06 km/h</td></tr><tr><td>Track4</td><td>12</td><td>52.74 km/h</td></tr><tr><td>Track5 Track6</td><td>8</td><td>40.82 km/h</td></tr><tr><td rowspan="2">Image Sequence2</td><td></td><td>Track7</td><td>6 6</td><td>41.26 km/h 40.83 km/h</td></tr><tr><td></td><td>Track1</td><td>28</td><td>37.27 km/h</td></tr><tr><td>Image Sequence3</td><td>28 28</td><td>Track1</td><td>28</td><td>48.24 km/h</td></tr><tr><td>Image Sequence4</td><td>12</td><td>Track2</td><td>15</td><td>43.51 km/h</td></tr><tr><td></td><td></td><td>Track1</td><td>9</td><td>38.72 km/h</td></tr><tr><td>Image Sequence5</td><td>24</td><td>Track2</td><td>62</td><td>18.78 km/h</td></tr></table></body></html>

# 4.6.Results evaluation

In order to verify the effectiveness and performance of the proposed method, we use Recall,Precision,and F-Score to evaluate the method and compare it with other methods. Recall represents the effectiveness of the detection, Precision represents the accuracy of the detection,and F-Score is the comprehensive response of Recall and Precision.The calculation formulas of Recall,Precision and F-Score are as follows:

$$
R e c a l l = \frac { N _ { \scriptscriptstyle T P } } { N _ { \scriptscriptstyle T P } + N _ { \scriptscriptstyle F N } }
$$

$$
P r e c i s i o n { = } \frac { N _ { \scriptscriptstyle T P } } { N _ { \scriptscriptstyle T P } + N _ { \scriptscriptstyle F P } }
$$

$$
F - S c o r e = \frac { 2 \times R c a l l \times P r e c i s i o n } { R c a l l + P r e c i s i o n }
$$

Where, $N _ { { } _ { T P } }$ and $N _ { { } _ { F N } }$ are the number of correctly detected targets and the number of ships that have not been detected respectively. $N _ { { } _ { F P } }$ is the number of false targets detected.According to the previous experimental data and experimental parameters, the detection results of the five groups of experimental data are statistically analyzed, and the comparison between the proposed MDDCM method and other visual saliency methods is shown in Table 7:

Table 7.Performance comparison between MDDCM and other methods   

<html><body><table><tr><td>Method</td><td>NTP+NFN</td><td>NTP+NFP</td><td>NTP</td><td>NFN</td><td>NFP</td><td>Recall (%)</td><td>Precision (%)</td><td>F-Score (%)</td></tr><tr><td>LCM</td><td rowspan="6"></td><td>284</td><td>177</td><td>51</td><td>97</td><td>81</td><td>62.3</td><td>70.4</td></tr><tr><td>MPCM</td><td>257</td><td>198</td><td>20</td><td>59</td><td>90</td><td>77</td><td>83</td></tr><tr><td>PSNR</td><td>223</td><td>181</td><td>37</td><td>42</td><td>83</td><td>81.2</td><td>81.1</td></tr><tr><td>SR</td><td>207</td><td>175</td><td>43</td><td>32</td><td>80</td><td>84.5</td><td>82.2</td></tr><tr><td>MDDCM</td><td>252</td><td>213</td><td>5</td><td>39</td><td>98</td><td>84.5</td><td>90.75</td></tr></table></body></html>

The experimental results show that LCMhas the worst performance among all methods,and the proposed MDDCM method has the best performance.MPCM method and MDDCM method in this paper have higher Recall, but MPCM method has more false targets.Although SR method has a higher Precision, it has a lower Recall rate.

Although the MDDCM method has the highest Recall among all methods, reaching $9 8 \%$ ,its Precision is only $8 4 . 5 \%$ , and there are still many false targets. The proposed shape verification method can further remove the false targets that do not meet the characteristics of ship wake.Then, JPDA is used for multi-frame data association of candidate targets in a single frame image, which can further remove the false targets that cannot be associated with stable track. Thus, the Precision of detection can be improved. Table 8 shows the improvement of detection performance after shape verification and multi-frame data association.

Table 8.Performance improvement by shape verification and data association   

<html><body><table><tr><td>Method</td><td>Recall (%)</td><td>Precision (%)</td><td>F-Score (%)</td></tr><tr><td>MDDCM</td><td>98</td><td>84.5</td><td>90.75</td></tr><tr><td>After shape verification</td><td>96</td><td>94.2</td><td>95.1</td></tr><tr><td>After dataassociation</td><td>95</td><td>99</td><td>98</td></tr></table></body></html>

Experimental results show that after shape verification, some false targets are further filtered,and the Precision is increased from $8 4 . 5 \%$ to $9 4 . 2 \%$ . After multi-frame data association, the Precision is improved to $9 9 \%$ and most false targets are removed. Some real targets are filtered out due to shape verification, while some targets are discarded because they are not associated with a stable track, resulting in a slight decrease in recal rate. The comprehensive evaluation F-Score increased from $9 0 . 7 5 \%$ to $9 8 \%$

# 5. Conclusions

Geostationary optical remote sensing satellites can continuously observe a fixed area, GF-4 satelite has the advantages of high temporal resolution and large coverage, which make it possible to continuously observe ships moving on the sea surface. However, due to the spatial resolution of the image,as well as the interference of high-brightness clouds, islands,sea clutter, etc., the ship target is weak and small in the image,which brings great difficulties to the direct detection of the ship. Based on the wake characteristics of moving ships on the sea surface,a moving ship detection and tracking method for GEO satellite images is proposed in this paper. The method includes four steps: image enhancement, target extraction, removing false alarms using shape features,and multi-frame association tracking.Firstly, the ship wake in the image is enhanced by ANGS,and then the candidate ship target is extracted by MDDCM algorithm based on the visual salience theory. Then, the false target is further filtered by the shape feature of the ship wake. Finally, the track information of moving ship target is obtained by JPDA multi-frame data association.

Through experimental analysis and comparison with other methods, the proposed method has good detection performance, especially in the case of weak targets or complex clouds environment, and can effectively detect and track the moving ships on the sea surface in the GEO optical remote sensing satelite images. Since we only use GF-4 satellite panchromatic image data for experiment, sea surface moving target detection and tracking based on GF-4 satellite multi-spectral image data can be further studied in the future. The method proposed in this paper can also be applied to other moving target monitoring applications of medium and low resolution optical remote sensing satellites.

# References

1.Li,B;Xie,X;Wei,X;TngW.Shipdetectionandclasificationfromopticalremotesensingimages:AsrveyScienceDirec. Chinese. J. Aeronaut. 2020,34, 145-163.

2. Kamirul,K.;biW;,R;inoiceisalgce. 2020,8,221918-221931.   
3. Yang,G.;LiB;J;GoF;XuQSipetecofrooicalateliteagessedoaurfceaalysEGoste Sens. Lett.2014,11,641-645.   
4. Yu,Y.; AiH; He,X;Yu,.ZhongX.;Lu,M.Shideectioninticasatelieimagesusing Haar-ikefeaureandriphry cropped neural networks.IEEE Access.2018,6,71122-71131.   
5. Heiselberg,H.Adirectandfastmetodologyforsipcognitioninsntil-ultispectraliageryemoteens610 1043.   
6. Bi,F.K.;Hou,JY;Chen,Lng,Z.H; WangYP.Sdtectioforopticalremotessingimagesbasednualattioe hanced network. Sensors.2019,19,2271-2283.   
7. Li, H.C.; Chen,L.;Li,F.;Huang,M.YShipdetectionandtrackingmethodforsatelitevideobasedonmultiscalesaliencyadur rounding contrast analysis. J. Appl. Remote. Sens. 2019,13,1-17.   
8. Zhu,C.; Zhou,H.;WangR; Guo,J.Anveierarchicalmethodofsipetectionfromspacebreopicalimagebsedonape and texture features.IEEE Trans. Geosci.Remote Sens.2010,48,3446-3456.   
9. Meng,LJ;Guo,D.;Tang,M.H; WangQ.DevelopmentStatusandProspectofHighResolutionImagingSatelitein Geostationar Orbit. Spacecraft Recovery &Remote Sens.2016,37,1-6.   
10.Liu,T.GeostationaryObigHigResolutnOpticalIagingateliinreatotetforrineurvllanceteiteApl cations， 2014,12, 70-74.   
11.Wang.;gYF;ngLJY;ZuObiecbtodgeericalie resolution geostationary optical satelite GaoFen4.ISPRS J. Photogramm. Remote Sens.2017,125,6-77.   
12.Wang,D.Z;HeHOseanCapabilyApcaorospectfG-4atelite.SpaceftRecoey&motee8,   
2 98-106.   
13 Zhang,ZX.;Shao,Y.;Tan,W.;WeiQ.F.;Zhang,YZ;ZhangQJApplicationPotentialofGF-4IagesforDynamicShipoitor ing.IEEE Geosci. Remote Sens.Lett.2017,14,911-915.   
D Liu,Y.; Yao,LB.;XiongW.;Zhou,ZM.GF-4SateliteandAutomaticdentficationSystemDataFusionforipTracking.IEE   
9   
武 Sensing Images. IEEE Access.2020,8, 9325-9334.   
A Kang,K.M.;Kim,DJShipVelocityEtimationFromShpWakesDetectedUsingConvolutionalNeuralNetworks.inIEJ.Sel.Top. Appl. Earth Obs. Remote Sens.2019,12,4379-4388.   
keu Diao,W.H.;Sun,X.;ZengX.W;DouF.Z;WangHQ.;Fu,K.EfcientSancasedObjectDetectioninRemoteesingIage Using Deep Belief Networks.IEEE Geosci. Remote Sens.Lett.2016,13,137-141.   
20 BiF.K.; ZhuBC.;GaoLN;anM.A ViuaSearchIspiedComputationalModeorSiptectioinOpticaei Images,"IEEE Geosci.Remote Sens.Lett2012,9,749-753.   
21Yao,LB;Liu,Y;He,Y.ANeipacingetodfrGF-telieSquenalagesSs.1,1.   
22.Xiao,FQ.;YuanF;ChengEDetectioandTrackingMethodofaritieovingargetsBasedoGeoschronousOrbielite Optical Images. Electronics. 2020,9,1092-1110.   
23.Zhang,ZX.;Xu,QJ;ZhangC.;ZhaoD.ShipovingFeatureDetectionUsingaSingleG-4ultispectralmage.RemoteSs.ech. Appl.2019,34,892-900.   
24. Fortmann,T.;Bar-Shalom,Y.;Schefe,M.SonarTrackingofMultipleTrgets Using JointProbabilistic DataAsociation.IEJ. Oceanic Eng. 1983,8, 173-184.   
25.Chen,CLP;Li,H;WeiY;XiaT;TngYY.ALcalConrastMetodforSmalraredTrgetDeteconEEEaGeosc. Remote Sens.2014,52, 574-581.   
26.Wei,Y.T.;You,X.G;Li,HMultiscalePatch-ased ContrastMeasurefrSmallInfraredTargetDetection.PaternRecogition. 2016, 58,216 - 226.   
27.Hou, XD.; Zhang,LQ.Sliencydetection: Aspectralresidualapproach.IEEConferenceonComputer Visioand PatteRecog nition(CVPR2007), Minneapolis, Minnesota, USA,19-21 June 2007.

592   
593   
594   
595   
596   
597   
598   
599   
600   
601   
602   
603   
604   
605   
606   
607   
608   
609   
610   
611   
612   
613   
614   
615   
616   
617   
618   
619   
620   
621   
622   
623   
624   
625   
626   
627   
628   
629   
630   
631   
632   
633   
634   
635   
636   
637   
638   
639   
640   
641   
642