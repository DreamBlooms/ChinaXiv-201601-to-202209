# 多级分解的Retinex低照度图像增强算法

王萍1，孙振明 2†

(1．北京电子科技职业学院 经济管理学院，北京 10029;2.中国矿业大学(北京）资源与安全工程学院，北京100083)

摘要：针对现有算法对图像边缘细节增强不足及无法有效控制各尺度信息增强程度的问题，提出了多级分解的Retinex 低照度图像增强算法。该算法在Retinex分解模型和双边滤波的基础上，通过设置不同的滤波参数，获取表征图像不同尺度信息的反射分量和照度分量；通过使用指数函数对分解得到的各级反射分量进行增强，能够有效提升图像边缘细节的表达能力；通过使用S型函数对最终的照度分量进行处理，能够在提升低照度图像整体亮度的同时抑制高亮度区域；通过颜色恢复函数对增强图像进行后处理，进一步避免色彩偏差和失真的问题。实验结果表明，新算法能够改善低照度图像的视觉质量，在清晰度、信息熵、对比度等指标方面都有所提升。

关键词：双边滤波；多级分解；低照度图像增强；Retinex算法 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.07.0788

Multi-level decomposition Retinex low-light image enhancement algorithm

Wang Pingl, Sun Zhenming2† (1.College ofEconomics&Management,BeijingPolytechnic,Beijingl029,China;2.CollegeofResources&Safety Engineering,China University ofMining&Technology,Beijing looo83,China)

Abstract:Theexistingalgorithms can't enhance the detailsofimage edges and efectivelycontroltheenhancement degree ofeach scale information.Aimingat theproblem,this paper proposed amulti-level decomposition Retinex low-light image enhancement algorithm.Onthe basisofRetinex decomposition modeland bilateral fitering,thealgorithmcanobtain the mult-levelreflectioncomponentsandillumination componentbyseting diferent filtering parameters.Using the exponential function toenhance themulti-levelreflectioncomponents,thealgorithmcan efectivelyenhancethe expression abilityofthe imageedgedetails.Andusingthe S-type function toprocessthe final luminancecomponent,thealgorithmcan improvetheoverall brightnessofte low-light image while suppressing the high-luminance area.By processing thecolor restorationfunction as post-processing,the algorithmcan further avoidthe problems of colordeviation and distortion.The experimentalresults show that the proposed algorithmcan improve the visual qualityoflow lightimages and is superior to the existing algorithms in terms of clarity, information entropy, and contrast.

Key words: bilateral filter; multi-level decomposition; low light image enhancement; Retinex algorithm

# 0 引言

随着信息化手段的发展，生产生活中产生了大量低照度环境下获取的图像。这些图像具有整体亮度低、分辨率低、噪声大等特点，制约了人眼辨识和进一步的图像处理与分析。为了提升图像可视化效果，有必要设计专门的低照度图像增强算法。传统的低照度图像增强算法可以分为基于伪雾图的增强算法、对比度增强相关算法和Retinex相关算法。由于低照度图像的负片与雾霾图像非常相似，基于伪雾图的增强算法能够根据雾霾成像机制对低照度图像的负片进行“雾霾”清晰化处理，最后转换得到增强后的图像[1,2]。对比度增强算法通过调整图像的像素或直方图分布来提升图像整体的对比度，实现低照度图像的增强，典型的算法包括受限对比度自适应直方图均衡化算法[3]、广义非锐化掩膜算法[4]等。

Retinex相关算法认为图像可以表示为照度分量和反射分量的卷积，其中照度分量反映整体变化缓慢的光照信息，而反射分量才是图像的本证属性。早期的Retinex相关算法通过去除照度分量对图像的影响，将获取的反射分量作为最终增强的图像。对于低照度图像而言，早期的Retinex相关算法存在严重的色彩失真现象。为解决上述问题，现有的Retinex算法同时考虑照度分量和反射分量对图像的影响，通过使用不同的增强函数对分解得到的照度分量和反射分量进行处理从而有效提升图像的质量，典型的算法包括非均匀照度图像色彩恢复算法[5]、低照度图像增强算法[]等。然而，上述算法在处理图像时缺少对图像多尺度信息的考虑，使得算法那对边缘细节等高频信息增强不足，限制了图像视觉质量的提升。

为了有效解决现有算法对图像多尺度信息考虑不足的问题，本文提出多级分解的Retinex低照度图像增强算法。该算法通过迭代使用双边滤波实现对图像的多级分解，获取表征图像不同尺度细节信息的照度分量和反射分量；改进图像增强函数，使用对数增强函数和S型增强函数对获取得到的多级反射分量和照度分量进行增强；最后，融合各分量，获得最终的增强图像。

# 1 Retinex理论及存在问题

# 1.1Retinex图像分解模型

Retinex理论是基于人眼视觉系统提出的图像增强理论，它能够在保持图像色彩信息的同时有效增强图像细节。围绕Retinex理论产生了一系列图像增强算法[7]，包括基于路径的Retinex算法、基于随机采样的Retinex算法、基于中心环绕的Retinex算法、基于偏微分方程的阈值Retinex算法以及基于变分的Retinex算法。1986年，Jobson等人[8]将高斯低通滤波与Retinex结合，通过改进Land等人提出的中心环绕Retinex算法（center/surroundRetinex），提出了单尺度Retinex（SSR）算法。Jobson等人使用低通滤波获取照度分量的方式使算法的执行效率有了极大的提升，称这种方式为基于分解的Retinex 算法。

Retinex理论的基本内容是物体的颜色是由物体对长波（红）、中波（绿）和短波（蓝）光线的反射能力决定的，而不是由反射光强度的绝对值决定的；物体的色彩不受光照非均匀性的影响，具有一致性，即Retinex 理论是以色感一致性（颜色恒常性）为基础的。Retinex算法的核心是通过去除可见光图像的场景光照信息，获取反射图像分量，从而实现对图像的增强。

基于图像生成模型，可以将图像看做照度分量和反射分量的卷积，即

$$
U ( x , y ) = F ( x , y ) \otimes L ( x , y )
$$

其中： $\pmb { F } ( x , y )$ 表示图像的反射分量， ${ \pmb L } ( x , y )$ 表示图像的照度分量， $\pmb { U } ( x , y )$ 表示原图像， $\otimes$ 表示卷积操作。

通常，物体的反射分量在全部反射和全部吸收之间，即反射分量的取值范围满足 $F ( x , y ) \in [ 0 , 1 ]$ 。进而，可以推断照度分量满足如下关系：

$$
L ( x , y ) { = } U ( x , y ) / F ( x , y ) { \geq } U ( x , y )
$$

# 1.2Retinex图像增强模型

Retinex模型将图像分解为照度分量和反射分量，分别刻画了图像的不同方面。为了使图像获得更好的可视化效果，使用不同的函数对图像的照度分量和反射分量进行增强，进而融合增强后的照度分量和反射分量，获得最终增强后的图像。基于分解的Retinex图像增强模型可以表示为

$$
U ^ { e } ( x , y ) = \operatorname { f } \left( F ( x , y ) \right) \otimes \operatorname { g } \left( L ( x , y ) \right)
$$

其中： $U ^ { e } ( x , y )$ 表示增强后图像，f()表示反射分量的增强函数，g()表示照度分量的增强函数。基于分解的Retinex图像模型已经广泛的应用于各种图像处理领域，如非均匀照度图像增强、低照度图像增强、细节增强、高动态范围图像映射等。针对不同的图像处理领域，需要有针对性的设计相应的增强函数，从而满足处理需求。典型的基于分解的Retinex图像增强流程如图1所示。

基于分解的Retinex算法的核心要素可以从以下三个方面进行考察，即获取照度分量的滤波器、照度分量和反射分量的增强函数以及多尺度信息的保持。照度分量反映的是图像变化缓慢的信息，早期研究者主要使用高斯滤波、频域低通滤波等滤波方法。由于这些滤波方法不具有保边特性，即在模糊图像的时不能够保持图像的边缘，从而使得最终获取的图像存在伪影。近几年，双边滤波[10,11]、迭代中值滤波、脉冲滤波、引导滤波[12]等具有边缘保持特性的滤波器被广泛的运用于基于分解的Retinex算法中。

对于低照度图像处理，可以使用伽马函数来对图像的照度分量进行调整。对于非均匀照度图像，可以使用S型函数实现图像照度的均衡，即对低照度区域进行增强、对高照度区域进行抑制。除此之外，有许多文章在伽马函数和S型函数的基础上提出了自适应的增强函数。

![](images/ad1b1254fcae11420e6acacbb58411a097db1d511cf809bfb1294812717c9d00.jpg)  
图1基于分解的Retinex 图像增强流程  
Fig.1Flowchart of Retinex based image enhancement process

基于分解的Retinex算法使用不同的滤波函数来获取图像的照度分量。通常，由于滤波尺度不好把握，不能平衡图像的细节对比度与色彩保留的关系。为此，研究者提出了多尺度的处理策略，包括多尺度Retinex 算法[13]和带色彩恢复的Retinex算法[14]。多尺度处理策略的关键是使用不同尺度的滤波器对图像进行滤波，使得获取的照度分量包含不同尺度大小的信息；进而得到反映图像不同尺度信息的照度分量进行加权求和作为最终的照度分量。这种使用不同尺度照度分量的加权和的方法不能较好反映具体图像的特点，同时不能实现对图像不同尺度增强程度的有效控制，为此本文在双边滤波的基础上提出多级分解的滤波策略，实现对图像不同尺度信息的获取；同时通过使用增强函数对不同尺度的反射分量和最终照度分量进行增强，实现对不同尺度信息有效控制，从而能够更好实现在提升低照度图像整体亮度的同时增强图像的边缘细节等高频信息。

# 2 多级分解的Retinex图像增强模型

为了解决高斯滤波等方法导致的颜色失真和光晕效应，迭代中值滤波、双边滤波、引导滤波等具有边缘保持特性的算法被广泛的应用到Retinex相关算法中。双边滤波是在高斯滤波基础上提出的一种具有保边特性的滤波方法，同时能够通过空域和值域两方面调节照度图像的生成，本文将在其基础上构建图像的多级分解。

# 2.1双边滤波及其性能分析

高斯滤波方法在图像处理中有广泛的应用，它使用邻域加权均值来实现图像光滑，并减少图像中的噪声。在滤波过程中，高斯滤波核的值只与空间领域的距离有关，而与图像的像素值无关，即每个像素点的滤波核都一致，而不能根据像素所处的图像上下文进行调整，从而使得获取的模糊图像不具有保边特性。为了解决上述问题，Tomasi和Manduch在1998年的国际计算机视觉大会上提出了具有边缘保持特性的双边滤波方法[10]。双边滤波的公式可以表示为

$$
\mathrm { B F } [ U ] _ { p } = \frac { 1 } { W _ { p } } \sum _ { q \in \Omega } G _ { \sigma _ { s } } ( \| p - q \| ) G _ { \sigma _ { r } } ( U _ { p } - U _ { q } ) U _ { q }
$$

$$
W _ { p } { = } { \sum _ { q \in \Omega } } G _ { \sigma _ { s } } ( \| p - q \| ) G _ { \sigma _ { r } } ( U _ { p } - U _ { q } )
$$

其中： $\boldsymbol { W } _ { p }$ 为归一化因子，使图像的像素值在滤波前后处在统一范围； $\pmb { p }$ 和 $\pmb q$ 表示图像中像素的位置， $\pmb { p }$ 为当前的滤波位置， $\pmb q$ 表示 $\pmb { p }$ 的邻域 $\Omega$ 中的像素位置； $\boldsymbol { { U } } _ { p _ { } }$ 和 $U _ { q }$ 分别表示像素 $\pmb { p }$ 和 $\pmb q$ 处的像素值。其中 $G _ { \sigma _ { \mathrm { s } } }$ 和 $G _ { \sigma _ { r } }$ 表示二维高斯滤波核，即

$$
\scriptstyle { G _ { \sigma } ( x ) = { \frac { 1 } { 2 \pi \sigma ^ { 2 } } } \exp ( - { \frac { x ^ { 2 } } { \sigma ^ { 2 } } } ) }
$$

由式（6）可以看出，双变滤波的核由两部分组成，即$G _ { \sigma _ { s } } ( \left\| p - \pmb q \right\| )$ 和 ${ \pmb G } _ { \sigma _ { r } } ( { \pmb U } _ { p } - { \pmb U } _ { q } )$ ， $G _ { \sigma _ { \mathrm { s } } }$ 由空间领域距离构成， $G _ { \sigma _ { r } }$ 由图像的灰度差值构成。相应的 $\sigma _ { \mathrm { { s } } }$ 和 $\sigma _ { \mathrm { r } }$ 分别表示相应的标准差，一般而言，标准差越小，平滑效应越不明显；标准差越大，平滑效应越明显。

由于双边滤波的核包含了图像邻域像素值的差异，因此它能够根据图像邻域像素值的差异的改进而自使用调整，并实现边缘保持的目的。

![](images/ce6b3470729d1a4dcebff04ecd6faa335e9d4b59ad26c56af33083cc7214871e.jpg)  
图2展示了双边滤波不同参数下的滤波效果。  
Fig.2Influence of different parameters of bilateral filtering on image blur

由图2中可以看出，双边滤波能够有效根据不同的滤波参数实现对图像不同程度的模糊，在模糊的同时能够有效保持图像的边缘。而且，随着参数的增加，双边滤波对图像的模糊呈现逐级递增的效应，或者说可以通过使用不同参数的双边滤波来获取模糊程度不同的图像序列。一般而言，当使用小尺度的滤波函数对图像处理时，图像的细节保留比较多，结合Retinex模型可以获取小尺度上的反射分量；进而可以实现逐级增加滤波参数，获取不同尺度上的模糊图像作为照度分量；并逐级获取反映不同尺度情况的反射分量。受此启发，本文提出了图像的多级分解，并基于Retinex原理获得不同尺度下的照度分量和反射分量。

# 2.2基于双边滤波的图像多级分解

根据Retinex理论，使用带有较小滤波半径的双边滤波对图像处理后仍然保留了大量的细节特征，这为图像的多级分解提供可能。在此基础上，本文提出的图像多级分解的示意图如图3所示。

本文提出的图像多级分解的步骤为：

a）使用具有较小滤波半径 $r _ { \mathrm { i } }$ 的双边滤波对输入图像进行处理，获取图像的一级照度分量 $\pmb { L } _ { 1 }$ ，根据式(2)对照度分量进行修正，使其满足 $\pmb { L } _ { 1 } \geq \pmb { L } _ { 0 }$ ；根据公式 $\pmb { F } _ { 1 } = \pmb { L } _ { 0 } / \pmb { L } _ { 1 }$ 获取图像的一级反射分量 $F _ { 1 }$ □

b)考虑步骤a)获取的一级照度分量 $\pmb { L } _ { 1 }$ 包含丰富的纹理特征，使用具有较大滤波半径 $r _ { 2 }$ （ $r _ { 2 } \rangle r _ { 1 }$ ）的双边滤波对一级照度分量 $L _ { \mathrm { 1 } }$ 进行滤波，获取图像的二级照度分量 $\pmb { L } _ { 2 }$ ，根据式(2)对照度分量进行修正，使其满足 $\pmb { L } _ { 2 } \geq \pmb { L } _ { 1 }$ ；根据 $\pmb { F } _ { 2 } = \pmb { L } _ { 1 } / \pmb { L } _ { 2 }$ 获取图像的二级反射分量 $\boldsymbol { F } _ { 2 }$ 0

c）按照同样的方式获取更高级的反射分量和照度分量，如 $\pmb { L } _ { 3 }$ 、 $\pmb { F } _ { 3 }$ ， $\pmb { L } _ { 4 }$ 和 $F _ { 4 }$ 。

图像多级分解能够有效提取图像不同尺度的信息。在使用的过程中，需要注意如下几点，为提取图像不同尺度下的信息，对原图像滤波使用的滤波半径应该比较小，然后在后续滤波中持续的增加，即 $r _ { 1 } < r _ { 2 } < r _ { 3 } < r _ { 3 } < \cdots$ 。不同于传统的多尺度滤波使用不同尺度的滤波器对同一幅图像分别进行滤波，然后取滤波后的图像取加权和作为最终输出，本文提出的多尺度滤波能够以多级分解的方式获取图像多个尺度的信息。进而，图像可以通过以连乘的方式从获取的各尺度反射分量和最终的照度分量来重建，这为控制各尺度的增强结果从而适应更多的图像应用提供了可能。通过多次实验，发现使用三级的多级分解的滤波过程就可以取得较好的效果。从图3可以看出，随着分解层次的提升，图像的照度分量越来越光滑，同时能够有效保持图像中的边缘；同时，反射分量所能反映的高频信息的尺度也越来越大，即反射分量中图块的聚集性逐渐提高。

![](images/1117c5925a5ca10a520ef5a51f991464ddfbc05d1e75f86788643b9e37dd7aa5.jpg)  
图2双边滤波不同参数对图像模糊的影响  
图3基于双边滤波的图像多级分解示意图  
Fig.3Multilevel image decomposition based on bilateral filtering

图4展示了图3中第一列各图像中第100行的提取线示意图，其中蓝色表示原图像像素分布；红色表示一级照度分量的光滑情况，由图中可以看出，一级照度分量对图像的光滑效应较弱，对应于图3(a2)包含了大量的纹理细节；绿色表示二级照度分量，是根据Retinex模型基于一级照度分量获取的；青色表示三级照度分量的提取线的像素情况，同样根据Retinex模型基于二级照度分量获取，其对图像的光滑效应比较强，反映了图像较大尺度上的变化趋势。

![](images/bbf22abfaf5ffaee3a23b849215192bef2a6305e8835b276ab29284e1aa54436.jpg)  
图4图像多级分解的效果示意图（以图3为例）

# 2.3多级分解的Retinex增强模型

图像的多级分解能够将图像表达为一系列的照度分量和反射分量，该过程可以表示为

$$
\begin{array} { r c l } { { } } & { { } } & { { U = F _ { 1 } \otimes L _ { 1 } } } \\ { { } } & { { } } & { { = F _ { 1 } \otimes F _ { 2 } \otimes L _ { 2 } } } \\ { { } } & { { } } & { { = F _ { 1 } \otimes F _ { 2 } \otimes \cdots \otimes F _ { n } \otimes L _ { n } } } \end{array}
$$

其中: $n$ 表示最终分解的级数， $F _ { k } , k \in [ 1 , n ]$ 表示 $\mathbf { k }$ 级反射分量，$\pmb { L _ { k } } , k \in [ 1 , n ]$ 表示 $\mathbf { k }$ 级照度分量。本文将式（7）表示的图像模型成为广义化的Retinex模型。在此基础上，可以使用不同的增强函数分别对各级反射分量和照度分量进行增强，然后将增强后的各分量进行处理，得到最终增强的图像，即

$$
U ^ { e } = \mathrm { f } ( { \cal F } _ { 1 } ) \otimes \mathrm { f } ( { \cal F } _ { 2 } ) \otimes \cdots \otimes \mathrm { f } ( { \cal F } _ { n } ) \otimes \mathrm { g } ( { \cal L } _ { n } )
$$

其中：f()表示各级反射分量的增强函数; $\mathbf { g } ( \pmb { L } _ { n } )$ 表示 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 阶照度分量的增强函数。针对不同的增强任务，可以采用不同的增强函数对各分量进行处理，针对本文低照度图像增强的应用，本文将分别使用指数函数和S型函数实现对各级反射分量和照度分量的增强，具体公式将在后文进行叙述。

多级分解的Retinex 增强模型的推导过程如下：首先，根据Retinex原理，对原图像进行分解，即 $\pmb { U } = \pmb { F } _ { 1 } \otimes \pmb { L } _ { 1 }$ ，获取一级反射分量和照度分量。考虑到一级照度分两种仍然包含了大量的纹理细节，从而为图像的进一步分解提供可能。为此，对一级照度分量进行处理，即 $\pmb { { \cal L } } _ { 1 } = \pmb { { \cal F } } _ { 2 } \otimes \pmb { { \cal L } } _ { 2 }$ 获得二级反射分量和照度分量。依此类推，可以获得式（7）的表述。在获得各级反射分量及照度分量的表示后，根据式（8）对图像进行增强。其中需要解决问题，即增强后的像素值范围不能超出[0,255]。

事实上，根据Retinex原理，照度分量 $L ( x , y )$ 反映了入射到物体上的光源能量总和，它表示了图像中变化缓慢的低频信息，满足 $L ( x , y ) \in [ 0 , \infty ]$ 。反射分量 $\pmb { F } ( x , y )$ 是物体的反射系数，它包含了图像的高频的细节部分，满足 $F ( x , y ) \in \left[ 0 , 1 \right]$ 。通常，物体的反射分量在全部反射和全部吸收之间，即反射分量的取值范围满足 $F ( x , y ) \in \left[ 0 , 1 \right]$ 。

在进行图像的级联分解过程中，本文将图像从[0,255]调整到[0.0,1.0]进行处理。这样处理的好处是能够最大限度的保证增强后的图像像素值限定在[0.0,1.0]内，从而不会造成图像的过增强或欠增强问题。事实上，根据式（7)，本文获取的各级反射分量和照度分量的值都限定在[0.0,1.0]内。

# 3 低照度图像增强算法

为了对低照度图像进行处理，本文在多级分解的Retinex增强模型的基础上提出了本文的增强算法。该算法首先将图像从RGB颜色空间转换到HSI色彩空间，并提取亮度通道进行处理；然后对亮度通道进行多级分解，获取表征图像不同尺度的反射分量和照度分分量；为提升图像不同尺度细节信息的表达能力，使用指数函数对获取的各级反射分量进行处理，为提升图像整体亮度的同时抑制高亮度区域，使用S型函数对获取的最终照度分量进行处理；融合增强后的各分量得到增强后的亮度通道并转换回RGB 颜色空间，对其进行色彩恢复并输出。算法流程如图5所示。

![](images/a1233b010897df2a7ca2d9c5b5cca254ee1268d37561d4d51cd7c031dfad823a.jpg)  
Fig.4Schematic diagramof image multilevel decomposition effect (Fig. 3)   
图5基于图像多级分解的低照度图像增强算法 Fig.5Low illumination image enhancement algorithm based on image multilevel decomposition

# 3.1 颜色空间转换

为提高图像处理的时间效率同时较好的保持图像的色彩信息，本文选择对HSI颜色空间的亮度通道进行处理。RGB颜色空间转换到HSI颜色空间可以表示为

$$
\pmb { I } = ( \pmb { R } + \pmb { G } + \pmb { B } ) / \sqrt { 3 }
$$

$$
\pmb { H } = [ 9 0 - \arctan ( \frac { 2 \pmb { R } - \pmb { G } - \pmb { B } } { \sqrt { 3 } ( \pmb { G } - \pmb { B } ) } )
$$

$$
+ \left\{ 0 , G \ge B ; 1 8 0 , G < B \right\} ] / 3 6 0
$$

$$
S = { \frac { 2 } { \sqrt { 6 } } } \times { \sqrt { ( R - G ) ^ { 2 } + ( R - B ) ( G - B ) } }
$$

对于HSI空间，各颜色分量的取值分别为 $0 ^ { o } \leq H \leq 3 6 0 ^ { o }$ ，$1 \leq S \leq 1$ ， $1 \leq I \leq 1$ 。通常HSI颜色空间到RGB颜色空间的通常按照色调 $\mathrm { ~ H ~ }$ 的不同分区进行。对于RG扇区( $0 ^ { \circ } \leq H < 1 2 0 ^ { \circ } \ )$ ，转换公式为

$$
\pmb { { \cal B } } = \pmb { { \cal I } } ( 1 - S )
$$

$$
R = I [ 1 + \frac { S \cos H } { \cos ( 6 0 ^ { o } - H ) } ]
$$

$$
\pmb { G } = 3 \pmb { I } - ( \pmb { R } + \pmb { B } )
$$

对于GB扇区（ $1 2 0 ^ { o } \leq H < 2 4 0 ^ { o }$ )，令 $\pmb { H } ^ { 1 } = \pmb { H } - 1 2 0 ^ { o }$ ，则转换公式为

$$
\pmb { R } = \pmb { I } ( 1 - S )
$$

$$
G = I [ 1 + \frac { S \cos { H ^ { 1 } } } { \cos ( 6 0 ^ { o } - H ^ { 1 } ) } ]
$$

$$
\pmb { { \cal B } } = 3 \pmb { { \cal I } } - ( \pmb { { \cal R } } + \pmb { { \cal G } } )
$$

对于 BR 扇区（ $2 4 0 ^ { o } \le H < 3 6 0 ^ { o }$ )，令 $\pmb { H } ^ { 2 } = \pmb { H } - 2 4 0 ^ { o }$ ，则转

换公式为

$$
\pmb { G } = \pmb { I } ( 1 - \pmb { S } )
$$

$$
B = I [ 1 + \frac { S \cos { \cal H } ^ { 2 } } { \cos ( 6 0 ^ { o } - H ^ { 2 } ) } ]
$$

$$
\pmb { R } = 3 \pmb { I } - ( \pmb { B } + \pmb { G } )
$$

# 3.2图像多级分解和增强

在获取图像的亮度通道 $\textbf {  { I } }$ 之后，使用本文提出的多级分解对其进行处理。对于低照度图像，首先对其进行分解，分别获取表征图像精细的小尺度信息、中尺度信息和大尺度信息的三级反射分量和最终的照度分量。对于一级分解，设定双边滤波参数为 $r _ { 1 } = 5$ ， $\sigma _ { s } = 5 . 0$ ， $\sigma _ { r } = 5 . 0$ ；对于二级分解，设定双边滤波的参数为 $r _ { 1 } = 1 0$ ， $\sigma _ { s } = 1 0 . 0$ ， $\sigma _ { r } = 1 0 . 0$ ；对于三级分解，设定双边滤波的参数为 $r _ { 1 } = 3 0$ ， $\sigma _ { s } = 1 5 . 0$ ， $\sigma _ { r } = 1 5 . 0$ 。最终，得到一级反射分量 $\pmb { F } _ { 1 }$ 、二级反射分量 $\boldsymbol { F } _ { 2 }$ 、三级反射分量 $\boldsymbol { F } _ { 3 }$ 和三级照度分量 $\pmb { L } _ { 3 }$ 。

为了提升各级反射分量的细节表达能力，采用指数函数对各级反射分量进行处理。即

$$
\mathrm { f } ( F _ { k } , x _ { k } ) = ( F _ { k } ) ^ { x _ { k } }
$$

其中：下标 $k$ 表示反射分量的序号且 $k \in \{ 1 , 2 , 3 \}$ ； $x _ { k }$ 表示指数增强系数。由于具体的图像增强场景对各尺度细节增强强度的要求不一样，所以对于各级的反射分量应设置不同的指数系数。本文提出了基于双边滤波的图像多级分解，并在此基础上提出了多级分解的低照度图像增强算法。该算法的核心是通过图像的级联分解，获取表征图像不同尺度的细节信息的反射分量，进而在对使用不同的增强系数对各级反射分量进行增强。

在2.2节，本文详细分析了多级分解的步骤及获取的各级反射分量情况。一般而言，由于使用较小滤波半径的双边滤波对原始图像进行处理，其获取的一级反射分量表征的更多是图像高频的细节信息；随着滤波半径的增大，双边滤波对图像的光滑作用增强，之后获取的各级反射分量所表征的细节信息的尺度越来越大。

在图像增强的过程中，根据具体的图像增强场景，其对图像不同尺度细节增强的要求不尽相同。如对于低照度图像增强的场景，在设计增强参数时应适当增加图像表征图像大尺度细节的反射分量的增强参数；对于高动态范围图像的增强，在设计时应适当增加中尺度和小尺度细节反射分量的增强参数，以使图像的纹理细节得到有效恢复；对于细节增强（detailsexaggeration.）的任务，应主要通过控制图像小尺度细节反射分量的增强参数。同时，考虑图像中噪声点等小尺度信息会反映在一级反射分量上，为了避免噪声的方法，通常将 $x _ { 1 }$ 设置为1；而 $x _ { 2 }$ 和 $x _ { 3 }$ 的取值范围设置为[1,3]，在处理低照度图像时，本文将其分别设置为1.5和1.3。在对反射分量进行增强时，通常在对数域中将三个反射分量同时进行处理，即

$$
\begin{array} { r } { \mathrm { ~ f ~ } ( F _ { \mathrm { 1 } } , F _ { \mathrm { 2 } } , F _ { \mathrm { 3 } } ) = \exp [ x _ { \mathrm { 1 } } * \ln { ( F _ { \mathrm { 1 } } ) } \qquad } \\ { + x _ { \mathrm { 2 } } * \ln { ( F _ { \mathrm { 2 } } ) } + x _ { \mathrm { 3 } } * \ln { ( F _ { \mathrm { 3 } } ) } ] } \end{array}
$$

对照度分量的增强，应在提升图像整体亮度的同时对高亮度区域进行抑制，为此本文采用S型曲线函数对图像的三级照度分量进行处理，即

$$
\mathrm { g } ( L _ { 3 } ) = 1 { } / ( 1 + \alpha \sqrt { ( 1 - L _ { 3 } ) / \left( L _ { 3 } + \varepsilon \right) } )
$$

其中： $\alpha$ 是照度调整系数，其取值范围为[0.1，2.0]； $\boldsymbol { \varepsilon }$ 是防止除数为零的微小扰动变量。图6展示了不同的 $\alpha$ 对应的函数图像。低照度图像增强要求对图像大部分区域进行增强，而对少部分高亮区域进行抑制，因此建议将 $\alpha$ 设置为0.5。

![](images/fd899a34bec517ee0452a166dbd7a6cffd87d51486f84f3f620c2241997e2467.jpg)  
图6不同参数下的S型曲线函数  
Fig.6S-type function under different parameters

在对各分量进行增强之后得到增强的亮度通道图，即

$$
I ^ { e } = \mathbf { f } ( F _ { 1 } , F _ { 2 } , F _ { 3 } ) \otimes \mathbf { g } ( L _ { n } )
$$

然后根据式（ $( 1 2 ) \sim ( 2 0 )$ 将图像由 HSI 颜色空间转换回RGB颜色空间。

# 3.3颜色恢复

由于上述增强方法只对图像的亮度图进行处理，而缺少对色调信息的处理，容易造成图像存在色彩偏差，为此参考带色彩恢复的多尺度视网膜增强算法（MSRCR）对图像进行颜色恢复。为表达方便，用 $\pmb { G } _ { i }$ （204 $( i = 1 , 2 , 3 )$ 表示原始输入的低照度图像的R,G，B颜色通道； ${ \pmb g } _ { i } \ ( i = 1 , 2 , 3 )$ 表示待色彩恢复的图像； $\tilde { \pmb { g } } _ { i } \ ( i = 1 , 2 , 3 )$ 表示色调恢复后的输出图像。则颜色恢复的公式可以表示为

$$
C _ { i } = \beta ^ { * } \ln \left[ 1 + \frac { \gamma { \cal G } _ { i } } { \displaystyle \sum _ { j = 1 } ^ { 3 } { \cal G } _ { j } + \theta + 1 } \right]
$$

$$
\pmb { \tilde { g } } _ { i } = \pmb { C } _ { i } \otimes \pmb { g } _ { i }
$$

其中： $\beta$ 表示增益参数； $\gamma$ 用来调节彩色图像的亮度程度； $\theta$ 用来调整三个颜色通道之间的比重； $\boldsymbol { C } _ { i }$ 为各颜色通道的颜色调整因子，通过与待色彩恢复的图像进行卷积操作得到最终的输出图像。在本文实验中，颜色恢复相关的参数设置如下：$\beta { = } 1 . 5$ ， $\scriptstyle \gamma = 6 . 5$ ， $\scriptstyle \theta = 0 . 2$ 。

针对多尺度Retinex 算法增强后的图像存在的色彩失真问题，文献[19]提出了色彩恢复的方法。该方法的核心是保持图像三通道颜色之间的比例，并通过颜色调整因子实现色彩的恢复和增强。本文在此选用的公式和相关参数设置参照文献进行设置。事实上，在实验的过程中，通过控制变量法对三个参数进行分析，例如对于，让其在[4,10]间进行以0.1为步长进行调整，结果表明，对于本文算法及低照度场景，文献[19]给出的参数设置能够在大多数条件下取得比较好的效果，表现在图像的整体照度更加均衡，图像信息熵也越高。

# 3.4算法的形式化描述

本文算法的流程为：

a）按照式（9） $\sim$ （11）将图像从RGB颜色空间转换到HSI空间，并提取亮度分量 $I$ 进行处理;

b)根据本文在2.2节提出基于双边滤波的图像多级分解算法及式（7)，对亮度通道 $I$ 进行分解，获取反映图像大尺度、中尺度和小尺度信息的各级反射分量 $F _ { 1 } , F _ { 2 } , F _ { 3 }$ 及最终的照度分量 $\pmb { L } _ { 3 }$ ;

c）为增强各级反射分量的细节表达能力，按照式（21) ～（22）对各级图像各级反射分量进行增强，获得增强后的 反射分量 $\mathrm { ~ f ~ } ( F _ { 1 } , F _ { 2 } , F _ { 3 } )$ ;

d）为增强低照度图像的整体照度分布，按照式（23）对

3级照度分量进行增强，获取增强后的照度分量 $\mathrm { g } ( { \pmb L } _ { 3 } )$ ：

e）按照公式（1）（7）将增强后的照度分量和反射分量进行融合，获得增强后的亮度分量 $I ^ { e }$ ；

f）按照式 $( 1 2 ) \sim ( 2 0 )$ 将图像从HSI颜色空间转换回RGB颜色空间，并根据式（25）（26）对增强后的图像进行颜色调整，获得最终增强图像。

# 4 实验结果和分析

为了验证本文所提算法的有效性，选择了多组低照度图像进行实验对比。选择具有代表性的六种低照度图像增强算法进行对比，包括Zuiderveld等人[3]提出的受限对比度自适应直方图均衡化算法(contrast limited adaptive histogramequalization,CLAHE)，Ibrahim等人[15]提出的亮度保持动态直方图均衡化算法(brightness preserving dynamic histogramequalization，BPDHE)，Dong等人[16]提出的基于伪雾图清晰化的算法，NASA中心提出的带有颜色恢复的多尺度Retinex算法（MSRCR)，Shin等人[5]提出的ENR算法，Wang等人[17]提出的 NPEA 算法。其中，CLAHE 算法和 BPDHE 算法属于对比度增强相关算法，Dong的算法属于基于伪雾图清晰化的算法，MSRCR算法、ENR算法和NPEA算法属于Retinex相关算法。算法涉及的参数使用相关论文推荐的进行设置。实验中所有算法均基于Matlab软件平台实现，同时为提升双边滤波的效率，使用Guarnieri等人[18]提出的加速的双边滤波方法。

# 4.1主观评价

为了衡量本文算法的有效性，选择经典的低照度图像进行处理。图7展示了在阴天环境下获取的野外照片，从图中可以看出图像整体两地比较低，左侧部分很难辨认图像细节。经过算法处理，都有效的提升了图像的整体视觉效果。其中，CLAHE算法有效的提升了图像的对比度，但同时放大了图像中右上方天空区域的噪声并降低了亮度；BPDHE算法对图像的增强效果有效，左侧部分仍然难以辨识。Dong算法是基于伪雾图实现的低照度增强算法，算法对图像整体的处理比较好，但在图像的边缘区域过渡不自然，影响了整体效果。MSRCR算法、ENR算法和NPEA算法都属于Retinex相关算法，但MSRCR算法处理后的图像存在较为明显的色彩偏差；ENR算法对图像的细节处理较好，但对于低照度图像存在增强不足的问题；NPEA算法处理后的图像照度整体比较均衡，但图像整体仍然偏暗。而本文算法能够在提升图像整体照度的同时有效保持图像的纹理细节，同时色彩丰富。

![](images/a54e23a2bddf0179cd3c3cfea347fa70c6779e32a4c30cc728cd15afbb87d9b8.jpg)  
图7低照度图像处理算法处理效果对比图

![](images/5a03c6dc5974359f11a73bf5a80254cee561a10a9d53ab2769bcaa6b1b82dadb.jpg)  
Fig.7The comparison of low-illumination image processing algorithms   
图8低照度图像处理算法处理效果对比图  
Fig.8The comparison of low-illumination image processing algorithms

图8选自NASA兰利研究中心（LangleyResearchCenter）官网，是常用的图像增强对比素材。由图中可以看出，CLAHE算法处理后图像照度分布更加无序；BPDHE算法未能有效增强图像照度，甚至降低了图像的整体亮度；Dong 算法在图中白塔的边缘存在明显的黑边；MSRCR 算法处理后图像整体偏褐色，即存在色偏；ENR算法和NPEA算法对图像的增强存在明显不足。相比较而言，本文算法的处理效果更好。

# 4.2客观评价

1）所给方法的评价指标

为客观评价算法结果，选取局部标准差平均值（AverageLocal StandardDeviation，ALSD)，信息熵（Entropy），以及平均梯度（Average Gradient，AG）作为评价指标。

ALSD首先将图像进行分块（本文中分块尺寸为 $2 5 { \times } 2 5 \$ )，取分块图像的标准差平均值作为图像对比度评价指标。ALSD计算公式为

$$
A L S D = \frac { 1 } { M } \sum _ { i = 1 } ^ { M } ( \sqrt { \frac { 1 } { 2 5 \times 2 5 } \sum _ { j } ^ { 2 5 \times 2 5 } ( I _ { j } ^ { i } - \overline { { { I ^ { i } } } } ) ^ { 2 } } ) .
$$

$$
\overline { { I ^ { i } } } = \frac { 1 } { 2 5 \times 2 5 } \sum _ { j } ^ { 2 5 \times 2 5 } I _ { j } ^ { i }
$$

式（27）中 $M$ 表示将原图像分成的块数， $I _ { j } ^ { i }$ 表示第 $i$ 个分块上第 $j$ 个位置上的像素值， $\overline { { I ^ { i } } }$ 表示第 $i$ 个分块的平均像素值。

信息熵用于度量图像信息的丰富程度，信息熵越大表明信息越丰富，其定义为

$$
E n t r o p y = - { \sum _ { i = 1 } ^ { M } } p ( x _ { i } ) \lg p ( x _ { i } ) .
$$

式（29）中 $p ( x _ { i } )$ 表示像素值为 $x _ { i }$ 的概率， $M$ 表示图像像素的总个数。

平均梯度，反映图像细节对比的表达能力，它是图像清晰度的重要表征。其计算公式为

$$
A G = \frac { 1 } { 2 M } \sum _ { i = x , y } \sum _ { j = 1 } ^ { M } \nabla _ { j } ^ { i }
$$

式（30）中， $\nabla _ { \ j } ^ { i }$ 表示沿 $i$ 方向（ $x$ 表示水平方向、 $y$ 表示垂直方向）上的梯度图像在位置 $j$ 处的梯度值。

表1展示了使用局部标准差平均值、离散熵及平均梯度对低照度图像增强算法的对比结果。对于图7，本文算法在离散熵和局部标准差平均值两项中都取得了比较高的得分，表明本文算法能够有效增强低照度图像的信息丰富程度和清晰度。对于平均梯度这一指标，本文算法不如MSRCR算法，但相比于其他算法仍然比较高，但从主观评价中，MSRCR算法的结果存在明显的色彩偏差和照度不均衡。除了本文算法，CLAHE 算法和NPEA算法的主观评价结果紧随其后，这与主观评价的结果相一致。事实上，CLAHE算法侧重于通过调整图像的直方图分布实现图像增强，其能有效改善图像的信息熵，但容易造成图像存在严重的过增强，例如图7中（b）所出现的天空区域的过暗，以及边缘处的光晕效应。NPEA算法注重图像自然色彩的恢复，但对图像的对比度等侧重不足。对于图8，本文算法同样在离散熵和局部标准差平均值方面取得较高的得分。同时相对梯度方面不如 Dong等提出的基于伪雾图算法、CLAHE算法和MSRCR算法。这主要是由于本文算法更加侧重于不同尺度细节信息的增强，因此图像能够使得表征图像信息丰富程度的离散熵指标比较高。综上所述，本文算法能够有效提升图像的信息丰富程度和清晰度，同时对图像对比度的提升也较为合理，与4.1节主观评价的结果相一致。

# 5 结束语

针对低照度图像增强算法存在的问题，提出了多级分解的Retinex低照度图像增强模算法。本文的主要结论包括：

a)通过对现有双边滤波性能的分析，提出基于双边滤波的Retinex多级分解，从而获得表征不同尺度信息的多级反射分量和最终的照度分量。

b)通过使用带有不同系数的指数函数对分解得到的多级反射分量进行增强，能够有效控制图像各尺度信息的表达能力，同时有效增强图像的边缘细节等高频信息。通过使用S型曲线函数对分解得到的最重的照度分量进行处理，能够在提升图像整体亮度的同时抑制高亮度区域。最后，为了减少增强图像的色彩偏差和失真，使用颜色恢复函数对结果进行后处理，得到最终输出图像。

c）实验结果表明，相比于现有的低照度图像，本文算法能够更加有效的提升图像的清晰度、对比度和信息丰富程度，展现了本文算法的优越性。

表1低照度图像增强算法客观评价指标比较  
Table 1Comparison of objective evaluation for low-illumination   

<html><body><table><tr><td colspan="11">image processingalgorithms</td></tr><tr><td rowspan="2">示例</td><td rowspan="2">指标</td><td rowspan="2">原图像</td><td colspan="7">算法</td></tr><tr><td>CLAHE BPDHE Dong MSRCR</td><td></td><td></td><td></td><td>ENR</td><td></td><td>NPEA 本文算法</td></tr><tr><td rowspan="3">Fig.7</td><td>DE</td><td></td><td></td><td></td><td>7.08697.1806 6.7536 6.87967.4921</td><td></td><td>7.5885</td><td>7.1043</td><td>7.7185</td></tr><tr><td>ALSD</td><td></td><td></td><td></td><td></td><td>15.4116 23.504 19.2311 28.2269 25.254 18.8145 22.654 36.7398</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>平均梯度 5.4102 10.9322 7.8767 11.7013 12.7391 6.9651 7.8339</td><td></td><td></td><td></td><td>12.0331</td></tr><tr><td rowspan="3"></td><td>DE</td><td></td><td></td><td></td><td></td><td>6.86517.5107 7.2926 7.2733 7.53167.6441 7.1657</td><td></td><td></td><td>7.5873</td></tr><tr><td>Fig.8 ALSD</td><td></td><td></td><td></td><td></td><td>16.8432 33.8842 21.8602 35.5895 34.4887 28.3034 28.7496</td><td></td><td></td><td>44.791</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>平均梯度 5.8698 13.4004 7.8712 15.5982 13.9417 10.2034 10.48</td><td></td><td></td><td>12.7194</td></tr></table></body></html>

# 参考文献：

[1]余春艳，徐小丹，林晖翔，等．应用雾天退化模型的低照度图像增强 [J]．中国图象图形学报,2017,22(9):1194-1205.(Yu Chunyan,Xu Xiaodan,Lin Huixiang,et al.Low-illumination image enhancement method based on a fog-degraded model [J].Journal of Image and Graphics,2017,22(9):1194-1205.)   
[2]陈勇，詹帝，刘焕淋．基于物理模型与边界约束的低照度图像增强 算法[J].电子与信息学报，2017,39(12):2962-2969.(Chen Yong, Zhan Di,Liu Huanlin.Enhancement algorithm for low-lighting images based on physical model and boundary constraint [J]. Journal of Electronics & Information Technology,2017,39(12):2962-2969.)   
[3]Zuiderveld K. Contrast Limited Adaptive Histogram Equalization [J]. Graphics Gems,1994: 474-485.   
[4]Deng Guang.A generalized unsharp masking algorithm[J].IEEE Trans on Image Processing,2011,20 (5): 1249-1261.   
[5]Shin Y,Jeong S,Lee S.Efficient naturalness restoration for non-uniform illumination images [J].IET Image Processing,2015,9 (8): 662-671.   
[6]Guo Xiaojie,Li Yu,Ling Haibin.LIME: Low-Light image enhancement via illumination map estimation [J]. IEEE Trans on Image Processing, 2017,26(2):982-993.   
[7]智宁，毛善君，李梅．基于相对梯度正则化的 Retinex 变分模型及其 应用[J].通信学报,2017,38(11):65-75.(Zhi Ning,Mao Shanjun,Li Mei.Variational Retinex model based on an extension of TV regularization with relative gradient and its applicate [J].Journal on Communications,2017,38(11): 65-75.)   
[8]Jobson DJ,Rahman Z,Woodell G A.Properties and performance of a center//surround retinex [J]. IEEE Trans on Image Processing,1997,6 (3): 451-62.   
[9]Land E H.An alternative technique for the computation of the designator in the retinex theory of color vision [J].Proceedings of the National Academy of Sciences of the United States of America,1986, 83 (10): 3078-3079.   
[10] Tomasi C,Manduchi R.Bilateral filtering for gray and color images

[C]//Proc of the 6th International Conference on Computer Vision. Piscataway,NJ:IEEE Press,1998:839-846.   
[11] Chaudhury K N,Sage D, Unser M,et al. Fast $o$ (1） bilateral filtering using trigonometric range kernels [J]. IEEE Trans on Image Processing, 2011,20(12):3376-3382.   
[12]He Kaiming,Sun Jian,Tang Xiaoou,et al.Guided image filtering [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2013,35 (6): 1397-1409.   
[13] Rahman Z,Jobson DJ,Woodell G A,et al.Multi-scale retinex for color image enhancement [C]//Proc of the 3rd International Conference on Image Processing.Piscataway,NJ:IEEE Press,1996:1003-1006.   
[14] Rahman Z,Jobson D J,Woodell G A,et al.Retinex processing for automatic image enhancement [J].Journal of Electronic Imaging,2004, 13 (1): 390-401.   
[15] Ibrahim H,Kong N S P. Brightness preserving dynamic histogram equalization for image contrast enhancement [J].IEEE Trans on Consumer Electronics,2007,53(4):1752-1758.   
[16]Dong Xuan,Wang Guan,Pang Yi,et al.Fast efficient algorithm for enhancement of low lighting video [C]//Proc ofIEEE International Conference on Multimedia and Expo.Washington DC: IEEE Computer Sciety,2011:1-6.   
[17]Wang S,Zheng J,Hu HM,et al.Naturalness preserved enhancement algorithm for non-uniform illumination images [J].IEEE Trans on Image Processing,2013,22 (9):3538-3548.   
[18] Guarnieri G,Marsi S,Ramponi G.Fast bilateral filterfor edge-preserving smoothing [J].Electronics Letters，2006,42 (7): 396-397.   
[19] Jobson D J,Rahman Z,Woodell G A.A multiscale retinex for bridging the gap between color images and the human observation of scenes [J]. IEEE Trans on image processing,1997,6(7): 965-76.