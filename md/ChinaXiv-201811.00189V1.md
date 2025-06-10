# 深度图辅助的主动轮廓分割算法

刘骥，曾文亮，梁晓升(重庆大学 计算机学院，重庆 400044)

摘要：针对由前后背景相似而导致从图像中很难分割出精确图像的问题，以主动轮廓分割方法为基础，结合深度图为辅助，提出了一种新的深度图辅助的基于区域的主动轮廓图像分割方法。首先，使用滤波算法对深度图进行修补，得到较为完善的深度图；然后使用混合高斯模型计算得到彩色图和深度图的置信图；最后使用置信图，计算给定区域中颜色与深度的权重，从而指导分割过程。提出算法能够正确的使用彩色信息和深度信息来指导分割，更准确地实现前后背景的分离。实验结果表明，该方法得到的分割结果较为接近真实情况，提高了图像分割的准确率。

关键词：深度图像；滤波算法；主动轮廓模型；置信图 中图分类号：TP391.41 doi: 10.19734/j.issn.1001-3695.2018.05.0493

# Depth assisted active contour segmentation algorithm

Liu Ji, Zeng Wenliang†,Liang Xiaosheng (College of Computer Science,Chongqing University,Chongqing 40o044,China)

Abstract:Thesimilarityofforegroundandbackgroundisatough questioninimage segmentation.Basedontheactivecontours, combining withthedepth map,this paper proposes adepth-asistedregion-based activecontour method.Ituses the filtering algorithm torecover the depth mapfirstly,thencalculates theconfidence mapsofthe RGB image and the depth image by Gausian Mixture Model,finallyuses theconfidencemaptocalculate the weightsof thecolorsanddepthsinthegivenregion to guidethe segmentation proces.The proposed algorithm uses the local information ofcolorand depth images to guide the segmentation,whichobtainamoreaccurate segmentation.The experimental results show thatthe proposed methodobtains the segmentation results are nearer to the true circumstance,also it improves the accuracy of image segmentation.

'ey words: depth image; hybrid filtering; active contours; confidence map

# 0 引言

图像分割是指将图片分割成不同区域，从而提取特定目标的一种方法。图像分割算法可以划分为以下几类：基于区域颜色等信息的分割、基于物体边缘信息的分割、基于给定阈值的分割以及一些特定理论研究中提供的分割方法。典型传统方法有图割方法[1]、水方法[2]、主动轮廓方法[3]。这些方法能够巧妙的利用相关区域信息来实现特定目标的分离，但是其所能依靠的信息较少，往往不能达到很好的分割效果。特别是针对图像中前后背景相似的情况，传统的分割算法往往难以得到正确的分割结果。

针对前后背景相似的情况，已有学者4开始引入深度图来辅助图像分割。因为深度图像的灰度值表示图像中物体与摄像机之间的距离，值越大表示距离越远。那么针对前景背景相似但深度值不同的区域，就可以利用深度信息进行分割。诸如李树涛等人[5]是提出了一种利用水平集和深度图来进行图像分割的方法，其方法主要分为两步，首先使用水平集对深度图进行分割，然后对分割结果边缘进行细化。葛玲等人[则是提出一种在经典图割算法中引入深度图进行交互式图像分割的方法，其主要思想为使用深度图改变图像分割时边的权值，从而改变分割结果。

然而，大多数人利用深度图像辅助图像分割时，使用的大都是较为完善的深度图。实际情况下，在深度图像的获取过程中，由于设备本身的限制（如Kinect)和外界环境因素的干扰，采集到的深度图像存在着很多问题，主要包括深度信息缺失导致的图像空洞、深度值准确值不高及图像噪声问题，从而导致很多应用深度图像进行分割的方法效果不佳。

本文提出一种利用深度相机采集的深度图来辅助图像分割的方法，其贡献点主要分为两点：使用改进的滤波算法来对深度图进行修补；引入置信图机制，提出深度图辅助的基于区域的主动轮廓算法，置信图的使用能够使彩色图和深度图得到合理的使用，这样在修补后深度图效果较好的情况下，就能主要依靠深度图完成分割，而在深度图修补不佳的情况下也能够利用彩色信息完成分割。实验结果表明，所提出的方法能够较好恢复深度图像，而基于修补后的深度图，本文提出的深度图辅助的基于区域的主动轮廓算法能够产生较好的分割结果。

# 1 算法描述

为了解决图像分割前后背景相似的问题，本文提出了深度图辅助的基于区域的主动轮廓分割方法，流程如图1所示。

![](images/75b91359d5d1d8aa7dd1632ae4cc9c53873aecfa48d02005ffcd0627d6430ddf.jpg)  
图1系统流程图

该方法由两个关键环节构成，其一为修补深度图，其二为使用修补后的深度图进行图像分割。本文方法的具体步骤描述如下：a)使用所提出的滤波方法，对深度图进行空洞修补;b)分别计算彩色图和深度图的置信图;c)由置信图得到给定区域的颜色与深度权重分量，从而指导后续的分割过程。

# 2 修补深度图的滤波算法

# 2.1 深度图空洞产生

以Kinect为例，说明空洞产生原因以及具体的空洞效果图。Kinect设备主要有三个组件：传感器；摄像机；麦克风。深度信息传感器由一个红外发射器和红外接收器组成，彩色摄像机采集彩色图像，用来获取同一场景的彩色图像。利用Kinect采集深度图像时。默认模式下，Kinect的有效视距是0.8米到4.0米，因此处于有效视距外的物体无法通过Kinect获得深度信息。从而造成Kinect数据缺失、图像空洞。图2为利用Kinect采集的彩色图像（图2右图）与其对应的深度图像（图2左图)。深度图像中，黑色区域表示像素值为0的点，即深度值为0的点也就是空洞像素。

![](images/b76114e0d04f21821e299ed8adcd624845ac2a1320047f777d5e8c35c2ebeeef.jpg)  
Fig.1System flowchart   
图2Kinect获取到的深度图  
Fig.2depth map acquired by Kinect

# 2.2滤波算法

本文在基于方向的联合双边滤波（directionaljointbilateralfilter，DJBF）[9]算法的基础上，提出了一种新的用于修补深度图的滤波算法。DJBF由Le等人提出，其计算公式如下：

$$
D _ { p } = \sum _ { q \in \phi ^ { p } } D ( q ) f _ { d s } ^ { d } \left( q _ { x } - p _ { x } , p _ { y } - q _ { y } \right) f _ { r } ^ { c } \left( I ^ { p } - I ^ { q } \right)
$$

其中: $D _ { { } _ { p } }$ 是指待测中心像素的深度值， $p$ 为中心像素点，

$p { = } \big ( p _ { x } , p _ { y } \big )$ ， $q$ 为中心像素的邻域像素点， $q = \left( q _ { x } , q _ { y } \right)$ 。 $p$ ，$q$ 之间的距离使用欧氏距离公式。

$$
f _ { r } ^ { c } \left( I ^ { p } - I ^ { q } \right) = e ^ { - \frac { 1 } { 2 } \left( \frac { \left( G ^ { p } - G ^ { q } \right) } { \sigma _ { r } } \right) ^ { 2 } }
$$

其中： $G ( i , j )$ 是作为引导图的彩色图像转换为灰度图后在点$( i , j )$ 处的灰度值。滤波器的核函数仍然是高斯函数， $\sigma _ { r }$ 为高斯公式的标准差。 $f _ { r } ^ { c } \left( I ^ { p } - I ^ { q } \right)$ 使用高斯函数作为核函数进行计算。在空间邻近度因子的计算上采取了DGF的方法，具体如下：

$$
f _ { d s } ^ { d } \left( q _ { x } - p _ { x } , p _ { y } - q _ { y } \right) = e ^ { - \frac { 1 } { 2 } \left( \frac { x _ { \theta } ^ { 2 } } { \sigma _ { x } ^ { 2 } } + \frac { y _ { \theta } ^ { 2 } } { \sigma _ { y } ^ { 2 } } \right) }
$$

$$
x _ { \theta } = ( q _ { x } - p _ { x } ) \cos \theta - ( p _ { y } - q _ { y } ) \sin \theta
$$

$$
y _ { \theta } = ( q _ { x } - p _ { x } ) \sin \theta + \oint p _ { y } - q _ { y } \mathrm { ) c o s } \theta
$$

在DGF中，根据边界方向 $\theta$ ，分别在水平和垂直两个方向进行计算，此处边界方向 $\theta$ 具体计算方式如下：

$$
\theta = \tan ^ { - 1 } \left( \frac { g _ { x } } { g _ { y } } \right)
$$

其中： $\left( g _ { x } , \mathcal { Y } _ { y } \right)$ 是沿 $\mathbf { x }$ 和 $\mathbf { y }$ 两个方向上的梯度。

本文所提出算法在DJBF 算法的基础上，先按照是否处于空洞区域分为空洞像素和非空洞像素，对所有空洞内的像素设置优先级，并按照优先级顺序进行填补；待空洞中的像素填补完成后，再对图中存在的处于非空洞区域的噪声进行去除，最后得到空洞修复后的图像。本文在计算每个待测空洞像素的深度之前，为所有的未知空洞像素设置了优先级，即填补顺序的优先程度。空洞区域内所有的空洞像素会按照其优先级进行排序，填补空洞时，会根据每个待测像素的优先级顺序由大到小进行深度值计算。而待测像素的优先级 $m$ 是由两个量来决定的，分别是临近像素的支持度 $p$ 和可信度 $q$ 的线性组合，即式（7)。

$$
m = p + \lambda q \left( \lambda > 0 \right)
$$

其中：支持度 $p$ 是指待测中心像素周围的已知邻域像素的个数。在本文实验中，滤波窗口大小采取为 $7 ^ { * } 7$ ，即中心像素的邻域像素个数为48。置信度 $q$ 为邻域像素与中心像素之间的相似度，包括空间临近度和灰度值相似度，其计算方法与联合双边滤波的中邻域像素深度的权重计算方法相同，如下所示：

$$
q = f _ { s } ^ { d } \left( q _ { x } - p _ { x } , p _ { y } - q _ { y } \right) f _ { r } ^ { c } \left( I ^ { p } - I ^ { q } \right)
$$

$f _ { s } ^ { d } \left( q _ { x } - p _ { x } , p _ { y } - q _ { y } \right)$ 为空间邻近度因子, $\begin{array} { r l } { f _ { r } ^ { c } \left( I ^ { p } - I ^ { q } \right) } \end{array}$ 为灰度值相似度因子。

计算优先级步骤如下：

a)首先为优先级 $\mathrm { ~ m ~ }$ 设定一个初始阈值 $T$ ，本文是实验中初始阈值 $T$ 为1.5。

b)由式（7）计算空洞区域内所有像素的优先级 $\mathbf { \nabla } _ { m }$ ，将所有大于 $T$ 的空洞像素插入到优先级队列TSet中，并计算该队列中各个像素的深度值。

c每填补完当前队列中所有空洞像素后，会对当前所有空洞像素重新通过计算支持度和可信度来计算新的优先级 $\mid m$ ，并根据剩余所有空洞像素的优先级更新阈值 $T _ { : }$ ，并按照新的阈值将空洞像素排列到队列中。这里 $T$ 是自适应性改变的，如果队列中没有待补像素，则将阈值降低0.1，反之升高0.1，通过不断调整阈值，使得优先级最高的像素总是可以被优先计算。这样在每次循环中，计算出目前剩余所有空洞像素的新的优先级，并依据新的优先级更新阈值，并不断地往优先级队列中加入新的优先级最高的空洞像素，计算其深度值。

d)待所有空洞像素的深度值都计算出，则跳出循环，即空洞填补完。

# 3 深度信息辅助基于区域的主动轮廓分割算法

# 3.1基于区域的主动轮廓算法

主动轮廓算法主要分为两种：基于区域以及基于边缘[10]。基于边缘的算法主要使用图像的梯度信息来停止特定对象边界上的曲线，基于区域的分割算法则是在演化过程中，找到满足边界情况下的最小能量函数。在本文中采用的是由Lankton等人[1提出来的基于区域的主动轮廓分割方法。与以往方法不同，该基于区域的方法主要考虑局部信息而不是全局图像的统计量，并通过局部信息来指导轮廓演化过程。

基于区域的主动轮廓算法进行图像分割时，对于给定图像$I$ ，将 $\Omega$ 定义为 $I$ 的二维空间，其演化过程中的能量函数可以表示为

$$
E ( \phi ) = \int \displaylimits _ { \Omega _ { x } } ^ { \Omega } \delta \phi ( x ) \int \displaylimits _ { \Omega _ { y } } ^ { \Omega } B ( x , y ) \cdot F ( I ( y ) , \phi ( y ) ) d y d x + \lambda \delta \phi ( x ) d i \nu \overline { { \left( \frac { \delta \phi ( x ) } { | \delta \phi ( x ) | } \right) } }
$$

其中 $E$ 为演化的能量函数， $\Omega$ 为图片区域， $\delta \phi ( { \boldsymbol { x } } )$ 代表狄拉克函数， $B ( x , y )$ 表示两点之间的距离关系，当两点 $x , y$ 距离小于给定半径值时， $B ( x , y ) = 1$ 否则为0， $I ( y )$ 是颜色分量和深度分量的组合值， $\lambda$ 是惩罚系数，在正则项中使用来保证曲线的平滑，其设置和文献[]相同。

$F$ 则是一个能量度量函数,用于保证轮廓上局部区域的点遵循给定的模型。其表达如下:

$$
F = \lambda _ { c } { \cdot } ( \nu _ { c } - \nu _ { c } ) ^ { 2 } + \lambda _ { d } \cdot \left( \nu _ { d } - \nu _ { d } \right) ^ { 2 }
$$

其中: $\lambda _ { c }$ 和 $\lambda _ { d }$ 由置信图决定， $\upsilon$ 表示的是区域内部像素均值，$\nu$ 表示区域外部像素的均值。

# 3.2 置信图的方法

在使用深度图辅助的主动轮廓算法进行图像分割时，需要引入置信图来指定 $\lambda _ { c }$ 和 $\lambda _ { d }$ 。其采用的判别方法如下所示：

$$
\left\{ \begin{array} { l l } { \displaystyle \lambda _ { c } = 0 , \lambda _ { d } = 0 } & { \displaystyle C < \frac { S } { \alpha } \mathrm { a n d } D < \frac { S } { \alpha } } \\ { \displaystyle \lambda _ { c } = 1 , \lambda _ { d } = 0 } & { \displaystyle C - D > \frac { S } { \beta } } \\ { \displaystyle \lambda _ { c } = 0 , \lambda _ { d } = 1 } & { \displaystyle D - C > \frac { S } { \beta } } \\ { \displaystyle \lambda _ { c } = 0 . 5 , \lambda _ { d } = 0 . 5 } & { \displaystyle | C - D | > \frac { S } { \beta } } \end{array} \right.
$$

$c$ 和 $D$ 分别为置信图对应区域中属于前景的值的个数,S为给定区域的面积, $\alpha$ 和 $\beta$ 都是常量,在实验中指定 $\alpha = 8 , \beta = 4$ 。

本文采用期望最大化的高斯混合模型（EM-GMM）的来计算置信图。除此以外，还有几种可选的方案，诸如高斯模型、直方图、高斯混合模型、期望最大化算法。本文对比了这几种方法后发现，EM-GMM最为有效。EM-GMM计算过程中，两个关键步骤是使用EM算法的初始化和求解过程，计算步骤描述如下：

a)初始化 $K = 2 , \pi _ { k } = 0 . 5 , \mathbf { I } _ { c } = 0$ ，初始化高斯模型 $G _ { k } =$ $\pi _ { k } N ( p _ { i } | \mu _ { k } , \delta _ { k } ^ { \ 2 } )$ ，循环步骤2-5，直到达到最大迭代条件则退出；b)对图像 $I$ 中的每个像素点 $p _ { i }$ ，令 $\mathrm { p } ( p _ { i } , G _ { k } ) = 0$ ·$\operatorname { p } \left( p _ { i } , G _ { k } \right) = { \frac { \pi _ { k } N ( p _ { i } \mid \mu _ { k } , { \mathcal { S } } _ { k } ^ { ~ 2 } ) } { \sum _ { k } ^ { K } \pi _ { k } N ( p _ { i } \mid \mu _ { k } , { \mathcal { S } } _ { k } ^ { ~ 2 } ) } } ~ ;$ ${ \bf N } _ { k } = \sum _ { i \in N } \mathrm { P } \left( p _ { i } , G _ { k } \right)$

$$
\mu _ { k } = \frac { 1 } { N _ { k } } \underset { k } { \overset { \kappa } { \sum } } \mathbf { p } ( p _ { i } , G _ { k } ) p _ { i }
$$

$$
\delta _ { k } ^ { \ 2 } = \frac { 1 } { N _ { k } } \sum _ { k } ^ { K } \mathsf { p } ( p _ { i } , G _ { k } ) ( p _ { i } - \mu _ { k } ) ( p _ { i } - \mu _ { k } ) ^ { T }
$$

e)如果 $\mathsf { p } ( p _ { i } , G _ { 0 } ) < \mathsf { p } ( p _ { i } , G _ { 1 } )$ ，则 $\mathbf { I } _ { \mathrm { c } ^ { i } } = 1$ 。

其中， $K$ 为高斯模型数量， $I _ { c }$ 为得到的置信图， $\pi _ { \boldsymbol { k } }$ 是每个高斯模型的权重。分别得到颜色和深度的置信图，从而就能在分割过程中通过改变权重值来改变函数 $F$ ，实现深度图辅助的基于区域的主动轮廓模型的分割。

# 4 实验结果

实验环境和参数在实验前均已正确配置，本方法基于OpenCV的 $\scriptstyle \mathbf { C } + +$ 实验环境下进行实验，实验数据集为$\mathsf { N T U } 2 0 0 0 ^ { [ 1 4 ] }$ 。本文实验过程中涉及到的深度图修补、置信图计算以及最后的主动轮廓分割按顺序执行，即每一环节的最优结果构成了最后的最优解。深度图修补过程中，其计算优先级的阈值 $T$ 初始设置为1.5，其余参数参考文献进行设置；主动轮廓分割过程中 $\alpha$ 和 $\beta$ 的变化范围为1到10，经多次实验在$\alpha = 8 , \beta = 4$ 时得到的 $\lambda _ { c }$ 和 $\lambda _ { d }$ 最为合适，其余参数参考文献[I]进行设置。

本文实验环节参考了文献[12]的实验过程，为了验证算法的有效性，实验过程将针对两个方面展开：一是验证滤波算法对深度图修复的有效性，二是验证深度图辅助的基于区域的分割算法的有效性。

本文实验效果的评价指标分为两类：其一是基于视觉观察的主观判断，其二是客观指标PSNR（峰值信噪比）、MSE（均方误差）、Jaccardindex（杰卡德系数）、Dicecoefficient（戴斯相似性系数）、Precision（精准率）以及参考文献[l3]所提供的针对分割结果的评价指标Conformitycoefficient（一致相似性系数)，所有的实验结果均与标准图GroundTruth进行对比。

# 4.1实验滤波算法的深度图修补结果

验证深度图修补算法的有效性的结果图如图3（bel1）和图4（tower）所示。在图3、4中，从左到右分别对应标准深度图、人工加以空洞的深度图、修补后的深度图（用红色标记存在的误差点）、修补后的深度图。在此阶段，对于客观评价，将从Error(填补误差)、Radio(空洞修补比例)和PSNR三个方面进行对比。

$$
{ \mathrm { E r r o r } } = { \mathrm { H o l e F i l l i n g - G r o u n d t r u t h } }
$$

HoleFilling为修复后的深度图像，Error是修复后的图像HoleFilling与Groundtruth对比后填补错误的像素数。

$$
\mathrm { R a d i o } = 1 - { \frac { \mathrm { E r r o r } } { \mathrm { H o l e _ { \mathrm { { s u m } } } ^ { \mathrm { ? } } } } }
$$

其中: $H o l e _ { s u m }$ 为空洞像素总个数。

PSNR是衡量图像失真水平或是噪声水平的客观标准，其是最普通的用来评鉴图像画质的客观测量法。

$$
\mathrm { P S N R } = 1 0 \log _ { 1 0 } \left( \frac { \mathrm { M A X } ^ { 2 } } { \mathrm { M S E } } \right)
$$

这里的MAX表示图像颜色的最大数值，8bit图像取值为255。MSE 为均方差（mean square error），即 $\mathrm { m } ^ { * } \mathrm { n }$ 的GroundTruth图和空洞填补后的深度图像 $K$ 之间的均方误差。

$$
M S E = \frac { 1 } { m n } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } K \left( i , j \right) - I \left( i , j \right) ^ { 2 }
$$

因此，PSNR的数学公式为

$$
P S N R = 1 0 \cdot \log _ { 1 0 } { \left( \frac { M A X _ { I } ^ { 2 } } { M S E } \right) } = 2 0 \cdot \log _ { 1 0 } { \left( \frac { M A X _ { I } } { \sqrt { M S E } } \right) }
$$

其中： $M A X _ { I }$ 是图像颜色的最大数值，8位的采样点表示为255。由计算原理可得，两幅图之间的PSNR值越大，则表明两幅图越相似。

![](images/31f5c8801465752a8ed0ef8e38861a8a9fe62b331dc1b187de68d7867b40addf.jpg)  
图3深度图修复算法结果(bell)   
Fig.3Results of depth image inpainting algorithm (bell)   
图4深度图修复算法结果(tower)   
Fig.4Results of depth image inpainting algorithm (tower)

IEID

本文使用滤波算法修补深度图的过程中利用的是局部信息，故最终结果不可能和标准图完全相同，但从图3以及图4最右边修补后的深度图来看，不难发现，该滤波算法能够有效地修补不完美的深度图。表1中数据也表明，经过滤波算法的修补，深度图得到了较好的恢复。

表1深度图修补算法数据对比  
Table 1Data comparison of depth map patching algorithm   

<html><body><table><tr><td></td><td>Error</td><td>Radio (%)</td><td>PSNR</td></tr><tr><td>修补前深度图 (bell)</td><td>4130</td><td>80.78</td><td>20.95</td></tr><tr><td>修补后深度图(bell)</td><td>2502</td><td>88.36</td><td>38.08</td></tr><tr><td>修补前深度图（tower）</td><td>3500</td><td>75.18</td><td>17.85</td></tr><tr><td>修补后深度图（tower）</td><td>2061</td><td>85.39</td><td>41.29</td></tr></table></body></html>

# 4.2基于区域的主动轮廓算法分割结果

为验证深度图辅助的基于区域的分割算法的有效性，本文进行了两类对比实验。其一是与只使用颜色信息产生的分割结果进行对比，其二是与葛玲等人提出的基于RGBD图像的图割方法进行了对比。只使用颜色信息的方法选择为基于轮廓指导的彩色分割[7]（ICCV2015)以及超像素分割方法[8]（CVPR2015）使用RGBD信息的为葛玲等人提出的方法。除此以外，本文在实验环节使用了基于深度学习的FCN（图像语义分割）来进行分割，但是深度学习作为一种需要大量训练数据的方法，针对未训练的图像并不能得到明显的分割结果。

本次实验中，分割结果的评估采用PSNR、Jaccard index、Dice coefficients、Precision、Conformity coefficient。Jaccard 系数可以用于比较样本集的相似性，其定义方式为样本集的交集除以样本集的并集，如式（17）所示，其中 $\Omega _ { 1 } \mathfrak { F } \mathbb { H } \Omega _ { 2 }$ 为两个样本集。

$$
\boldsymbol { \kappa } _ { j } = \frac { \left| \Omega _ { 1 } \cap \Omega _ { 2 } \right| } { \left| \Omega _ { 1 } \cup \Omega _ { 2 } \right| } \times 1 0 0 \%
$$

显然，Jaccard值越大，也即是数据越相似，得到的分割结果更为接近真实情况。Dice系数也是一种相似度度量函数，Dice系数越大，表示数据越相似，其定义如下：

$$
\boldsymbol { \kappa } _ { d } = \frac { 2 \left| \Omega _ { 1 } \cap \Omega _ { 2 } \right| } { \left| \Omega _ { 1 } \right| + \left| \Omega _ { 2 } \right| } \times 1 0 0 \%
$$

Precision即是精准率，其值代表了正确分割样本占总样本的比例，也是值越大，则分割越精准。

Conformitycoefficient是由参考文献[13]提出的一种衡量分割结果的评价指标，可以由 $\kappa _ { d }$ 进行表示，如下所示：

$$
\kappa _ { c } = 3 - \frac { 2 } { \kappa _ { d } }
$$

根据参考文献[13]，相比于Dice 和Jaccard，Conformitycoefficient更敏感、更严格，在识别变化较小的分割图像是，其识别能力更佳。

分割结果如图5和6所示，不难发现在具有空洞的情况下，由于本文提出了在进行图像分割前首先对深度图使用滤波算法进行修补，得到的分割结果更为接近真实情况。

表2以及表3为具体的评价指标数据，数据显示由本文提出的修补深度图算法和深度图辅助的基于区域的主动轮廓算法得到的分割结果，其各项指标均相对较好，也即是最为接近真实情况，能够得到较好的分割。

![](images/ad0744f47396fc078b0afa049ea698c94f3e2c563aefacd33c70c398cd2ef1d0.jpg)  
图5不同算法分割结果对比(bell)  
Fig.5Segmentation results of different algorithm(bell)   
Fig.6Segmentation results of different algorithm(Tower)

111 I图6不同算法分割结果对比(tower)

Table 2Data comparison of segment algorithm(bell)   
表3分割算法数据对比(tower)  

<html><body><table><tr><td>指标</td><td>方法[]</td><td>方法[7]</td><td>方法[8]</td><td>本文</td></tr><tr><td>PSNR</td><td>40.64</td><td>43.87</td><td>44.37</td><td>47.15</td></tr><tr><td> Jaccard(%)</td><td>90.52</td><td>96.38</td><td>96.33</td><td>96.89</td></tr><tr><td>Dice(%)</td><td>95.03</td><td>98.15</td><td>98.13</td><td>98.42</td></tr><tr><td>Conformity(%)</td><td>89.53</td><td>96.24</td><td>96.19</td><td>96.79</td></tr><tr><td>Precision(%)</td><td>93.08</td><td>97.36</td><td>97.37</td><td>98.52</td></tr></table></body></html>

表2分割算法数据对比(bell)  
Table 3Data comparison of segment algorithm(tower)   

<html><body><table><tr><td>指标</td><td>方法[6]</td><td>方法[7]</td><td>方法[8]</td><td>本文</td></tr><tr><td>PSNR</td><td>32.40</td><td>37.59</td><td>37.74</td><td>38.65</td></tr><tr><td>Jaccard(%)</td><td>60.22</td><td>89.39</td><td>89.94</td><td>91.71</td></tr><tr><td>Dice(%)</td><td>75.17</td><td>94.40</td><td>94.70</td><td>95.68</td></tr><tr><td>Conformity(%)</td><td>33.95</td><td>88.13</td><td>88.82</td><td>90.97</td></tr><tr><td>Precision(%)</td><td>64.30</td><td>99.25</td><td>96.93</td><td>99.38</td></tr></table></body></html>

# 5 结束语

图像分割一直是计算机视觉领域的一大研究热点。本文提出了深度图辅助的基于区域的主动轮廓分割方法，为解决实际获取到的深度图存在空洞等问题，在DJBF基础上提出了新的滤波算法来修补深度图。本文所提出方法是首先会对深度图进行修补，接着计算出彩色图和深度图的置信图，并由置信图得到彩色分量和深度分量的权重值，最后完成分割过程。实验结果表明本文提出的方法能够较好的修补深度图并产生更接近真实情况的分割结果。

参考文献：   
[1] 温佩芝，陈晓，吴晓军，等．基于三次样条插值的 GrabCut 自动目标分 割算法[J].计算机应用研究,2014,31(7):2187-2190.(Wen Peizhi,Chen Xiao,Wu Xiaojun,et al. Automatic target segmentation algorithm of GrabCut based on cubic spline interpolation [J].Application Research of Computers,2014,31(07): 2187-2190. )   
[2] 汪澜，张慧，张海涛.结合新颜色空间与Otsu 的分水岭彩色图像分割 算法[J].计算机应用研究,2017,34(12):3873-3879.(Wang Lan,Zhang Hui,Zhang Haitao．Watershed image segmentation algorithm which combining with Otsu in new color space [J].Application Research of Computers,2017,34 (12): 3873-3879.)   
[3]李天庆，张毅，刘志，等.Snake 模型综述[J].计算机工程,2005,31(9): 1-3.(Li Tianqin, Zhang Yi, Liu Zhi,et al. A review of Snake model [J]. Computer Engineering,2005,31(9): 1-3.)   
[4]Zanuttigh P, Marin G,Mutto CD,et al. Time-of-Flight and Structured Light Depth Camera [M].[S.1.] : Springer Publishing Company, 2016.   
[5]Lu Ting,Li Shutao.Image mating with color and depth information [C]// Proc of International Conference on Pattern Recognition.2012:3787-3790.   
[6] Ge Ling，Ju Ran，Ren Tongwen，et al. Interactive RGB-D image segmentation using hierarchical graph cut and geodesic distance [Cl// Proc of Pacific Rim Conference on Multimedia. Cham: Springer, 2015: 114-124.   
[7]Fu Xiang, Wang CY, Chen Chen,et al. Robust image segmentation using contour-guided color palettes [C]// Proc of International Conference on Computer Vision. 2015: 1618-1625.   
[8]Li Zhengqin，Chen Jiansheng. Superpixel segmentation using Linear Spectral Clustering [C]/ Proc of Computer Vision and Pattern Recognition. 2015: 1356-1363.   
[9]Le A V, Jung SW,Won C S.Directional Joint Bilateral Filter for Depth Images [J]. Sensors,2014,14(7): 11362-11378.   
[10] Hu Ping,Bing Shuai,Liu Jun,et al.Deep level sets for salient object detection [Cl//Proc ofComputer Vision and Pattern Recognition. 2017: 540- 549.   
[1]Lankton S,Tannenbaum A.Localizingregion-basedactivecontours[J]. IEEE Trans on Image Processing,2008,17(11): 2029-2039.   
[12] Lei Tao,Jia Xiaohong, Zhang Yanning,et al. Significantly fast and robust fuzzy c-means clustering algorithms based on morphological reconstruction and membership filtering [J]. IEEE Trans on Fuzzy Systems,2018.   
[13] Chang H H,Zhuang A H,Valentino D J,et al.Performance measure characterization for evaluating neuroimage segmentation algorithms [J]. NeuroImage,2009,47(1): 122-135.

[14]Ju Ran,Liu Yang,Ren Tongwen,et al.Depth-aware salient object detection using anisotropic center-around difference [J]. Signal Processing: Image

Communication,2015,38(10):115-126.