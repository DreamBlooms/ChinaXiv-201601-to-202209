# 基于梯度特征的双核非局部均值去噪算法

张玉征1,²，杨词慧1,2†，林泉1

(1．南昌航空大学 信息工程学院，南昌 330063;2.江西省图像处理与模式识别重点实验室，南昌 330063)

摘要：针对传统非局部均值（NLM）滤波算法中邻域间相似性计算易受噪声干扰的问题，提出了一种基于梯度特征的双核非局部均值滤波算法。通过图像块之间的欧氏距离及梯度特征度量邻域间相似性，采用双核函数代替传统指数核函数计算相似性权值，并通过衡量搜索区域中的邻域块与当前像素邻域的相似程度，对像素点的权值进行重分配，在此基础上，重估像素点去噪值并得到滤波图像。实验结果表明，提出的滤波算法与传统的 NLM滤波算法及分别含有高斯核和正弦核的改进NLM滤波算法相比，可以更准确地反映邻域间的相似度，保存图像的细节及边缘信息，从而有效提升图像的去噪效果。

关键词：非局部均值；高斯函数；正弦函数；梯度特征 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.12.0830

# Dual kernel non-local means denoising algorithm based on gradient feature

Zhang Yuzheng1, ², Yang Cihui1,2†, Lin Quan1 (1.SchoolofInformationEngineering,NanchangHangkongUniversityNanchang3063,China;2.KeyLaboratoryofJangi Province for ImageProcessing&Pattern Recognition,Nanchang 33oo63,China)

Abstract: Inthetraditionalnon-lcal mea (NLM)filteringalgorithm,the presenceofnoiseinthe image interferes heaccuracy of similaritycalculation betweenneighborhood blocks.Toaddressthis problem,this paper proposedadual kernelnon-local means denoising algorithm based on gradient feature.This algorithm calculates the similarityof neighborhood block by Euclideandistanceandgradientfeaturebetweepixels,andreplaces theoriginal exponentialfunctionwithdualkerelfunction tocalculate similarweights.Inaddition,itmeasuresthesimilaritybetweentheneighborhoodblocksofthepixels inthesearch areaandthe currnt neighborhoodtoreassign thepixels' weight. Onthis basis,itreevaluates the denoising values and get the denoisedimage.Experimentalresultsshowthatthisalgorithmcanaccuratelyreflectesimilaritybetweenneighborhood block of pixels and preservethe detailsand edge informationofimages efectively whilecompared with the traditional NLMfiltering algorithm and two other improved NLM algorithms,and improve the efect of image denoising significantly.

Key Words: non-local means; Gaussian function; wave function; gradient feature

# 0 引言

图像在采集、取样、传输及编码的过程中，由于外界环境及设备自身的影响，不可避免地受到噪声干扰。噪声的存在降低了图像视觉效果，影响了人类对图像的正确识别与理解。因此，降低噪声对图像的干扰是图像处理过程中必不可少的环节。针对图像去噪问题，研究学者们提出了多种图像去噪算法，如各向异性扩散法[1,2]、总变分法[3.4]、非局部均值（non-local means,NLM）滤波算法[5,6]等。

NLM算法是Buades等人[5]2005年结合纹理合成及双边滤波的原理提出的一种滤波算法，该算法通过在图像中搜索相似邻域，并将相似邻域的中心像素点进行加权平均，以计算图像像素的去噪值。相比已有的经典去噪算法，NLM算法充分利用了图像中的相似冗余信息，较大程度地避免了虚假信息的引入，并能充分体现图像的结构特征，而且在去除噪声的同时能较好地保存边缘及纹理信息。然而，采用NLM 算法计算邻域间的相似性时，图像噪声的存在会对该算法中相似性计算的准确性产生干扰，会使某些相似性较大的邻域获得较小权值，从而导致细节丢失和图像模糊。因此，众多学者对NLM算法进行了改进研究。

孙伟峰等人[7利用图像的结构对称性，首先对邻域进行方向变换，再计算邻域间欧式距离，充分利用图像的自相似性提高算法的去噪效果。Deledalle 和Daval[8提出在含有不同特征的区域中，采用不同形状的邻域代替传统矩形邻域进行相似性度量，该方法在一定程度上提高了邻域搜索率。陈世媛等9通过判断区域中纹理的复杂度，自适应调整图像块及搜索窗口大小，以提高相似块搜索的准确性。Park 和Kang[10提出使用权重中位数代替中心像素权重，以增加当前像素在灰度估计中的权重合理性。文献[11-13]采用高斯、倒数、余弦等多种核代替传统NLM算法中指数核，提高了权值分配的合理性。上述方法在去噪效果上都有了改进，但仍存在图像模糊、细节丢失等问题，且当图像中噪声比较严重时，去噪效果明显下降。

针对该问题，本文提出了一种基于梯度特征的双核非局部均值去噪算法(dual kernel non-local means denoising algorithmbasedongradientfeature，DKGNLM)。采用欧氏距离及梯度特征对图像块的相似性进行度量，利用新的核计算方法代替传统算法中的指数核并通过权重重分配方法获得更准确的像素估计值，以提高算法的去噪性能。

# 1 NLM算法概述

一幅含有高斯噪声的图像 $I$ 其模型可表示为

$$
y ( i ) = x ( i ) + n ( i )
$$

其中： $y ( i )$ 表示受到噪声影响的图像像素点， $x ( i )$ 表示未受到噪声影响的原始图像像素点 $, n ( i )$ 表示加在图像上并满足$n ( i ) { \sim } N ( 0 , \sigma ^ { 2 } )$ 的噪声， $i \epsilon S$ 且 $s$ 是图像中像素点的坐标集。

传统NLM算法通过对搜索邻域中所有像素点的灰度值进行加权平均得到图像像素点的去噪估计值，其数学模型可表示为

$$
\hat { y } ( i ) = { \sum } _ { j \subset S _ { \mathrm { i } } } W ( i , j ) ^ { * } y ( j )
$$

其中： $S _ { i }$ 表示以当前像素点 $i$ 为中心的搜索邻域中像素点的坐标域， $y ( j )$ 为噪声图像中 $j$ 点的灰度值， $W ( i , j )$ 表示分别以像素点 $i$ 和像素点 $j$ 为中心的两个邻域间的相似性权重，该相似性权重表示为

$$
W ( i , j ) = \frac { 1 } { \sum _ { j \subset S _ { j } } W ( i , j ) } * \exp ( - \frac { d } { h ^ { 2 } } )
$$

其中：平滑参数 $h$ 决定该算法的滤波程度， $d$ 表示邻域间的欧式距离，用来度量以 $i , j$ 为中心的邻域之间的相似度，当欧式距离越小时，邻域间的相似性越大。该欧式距离表示为：

$d = \parallel N ( i ) - N ( j ) \parallel _ { 2 , \alpha } ^ { 2 }$ (4)其中： $N ( i ) , \ N ( j )$ 分别表示以 $i , j$ 为中心的邻域。

# 2 改进的非局部均值滤波算法

# 2.1梯度特征相似度判断

梯度特征以局部梯度为基础。局部模式主要有两个基本要素：邻域像素的灰度值以及像素间的亮度变化。图像的亮度反映图像边缘变化情况，已有研究[14表明噪声对边缘区域影响较小，而图像边缘可以用梯度表示出来。因此，本文采用文献[15]提出的图像匹配相似特征方法，通过结合梯度特征与传统的欧氏距离计算邻域间相似性，以解决噪声对相似块搜索产生干扰的问题。像素邻域在水平、垂直、45度和135度四个方向上的梯度分别定义为

a)水平方向梯度

$$
\begin{array} { r } { H D ( x , y ) = \sum _ { i = 0 } ^ { k } \sum _ { j = 0 } ^ { k } { ( g _ { x + i , y + i } - g _ { x + i , y + j + 1 } ) ^ { 2 } } } \end{array}
$$

b)垂直方向梯度

$$
\begin{array} { r } { V D ( x , y ) = \sum _ { i = 0 } ^ { k } \sum _ { j = 0 } ^ { k } ( g _ { x + i , y + i } - g _ { x + i + 1 , y + j } ) ^ { 2 } } \end{array}
$$

c)45度方向梯度

$$
\begin{array} { r } { D D 4 5 ( x , y ) = \sum _ { i = 0 } ^ { k } \sum _ { j = 0 } ^ { k } \left( g _ { x + i , y + i } - g _ { x + i + 1 , y + j + 1 } \right) ^ { 2 } ( 7 ) \left| \begin{array} { l l l l l l l l } \end{array} \right. } \end{array}
$$

d)135度方向梯度

$$
D D 1 3 5 ( x , y ) = \sum _ { i = 0 } ^ { k } \sum _ { j = 0 } ^ { k } { \left( g _ { } \right)} _ { x + i , y + i } - g _ { } _ { x + i - 1 , y + j + 1 }  ^ { 2 }
$$

其中： $( x , y )$ 表示图像 $I$ 中任意像素点的坐标， $k$ 为邻域的尺寸 $\mathcal { S } ^ { x } .$ （2$_ y$ 表示以 $( x , y )$ 为坐标的像素点的灰度值。像素的邻域梯度特征可表示为

$$
I V ( x , y ) = \operatorname * { m i n } \big ( H D ( x , y ) , V D ( x , y ) , D D 4 5 ( x , y ) , D D 1 3 5 ( x , y ) \big )
$$

两个像素 $( x _ { 1 } , y _ { 1 } )$ 和 $( x _ { 2 } , y _ { 2 } )$ 的邻域间梯度特征相似性定义为

$$
D = \parallel I V ( x _ { 1 } , y _ { 1 } ) - I V ( x _ { 2 } , y _ { 2 } ) \parallel
$$

# 2.2双核函数

传统NLM算法采用指数函数计算相似邻域权重值。从图1中可以看出，指数函数在相似度高的区域具有较高权值，但随着欧氏距离的增加其权值衰减过快，会降低权值分配的准确性，导致去噪图像模糊。为解决该问题，文献[11,16]利用高斯(Gaussian)、正弦(Wave)等核函数代替传统NLM算法中的指数函数。高斯核随着距离的增大而迅速下降，在邻域欧式距离较大时，欧式距离对相似权重影响较小，相似度趋近于零；而正弦核在一定欧氏距离内下降趋势缓慢，当欧式距离大于某个阈值时其相似权重为零，滤除了相似度较低的邻域。

![](images/f52926f766ccbfa12be508535de4f566aae497be29c5a16bf4cec42488a315f2.jpg)  
图1不同核函数变换趋势图

文献[11]提出的几种采用不同核函数的改进NLM算法，改善了传统NLM算法存在的问题，但其实验结果表明，这些改进算法在噪声强度比较弱时，得到的滤波效果比传统的NLM算法好。然而当图像噪声较强时，采用高斯核函数的改进NLM算法会因加权不足而导致去噪性能下降，而采用正弦核函数的改进NLM算法则因加权过重易引起图像模糊。

本文结合高斯核函数与正弦核函数的特点提出一种新的核函数：高斯正弦核函数（Gaussian-wave function,GW)，该函数采用阈值的方法滤除相似性较低的邻域，以减少相似性较小的像素点对像素估计的干扰，提高图像去噪的准确性。高斯正弦核函数可表示为

$$
W ( i , j ) = \{ \begin{array} { l l } { { \exp ( - \displaystyle \frac { d ^ { 2 } } { 2 * h ^ { 2 } } ) * \sin ( \displaystyle \frac { \pi * D } { h 1 } ) } } & { { \quad 0 < d < h 1 } } \\ { { 0 } } & { { \quad \mp \updownarrow \{ | \updownarrow | \propto \langle | h | ^ { 2 } \rangle \} } } \end{array} 
$$

其中，h1、h2均为平滑参数， $d$ 表示像素邻域之间的灰度欧氏距离， $D$ 为两个像素邻域之间梯度特征的相似性。

# 2.3权重重分配

在传统NLM算法中，采用指数函数计算得到的当前像素点权值恒为1，在像素估计中容易产生过加权的现象。为解决该问题，Li等人[17采用搜索邻域中权重最大值作为当前像素点的权值，然而在当前像素受噪声影响较小时，该邻域的最大权值小于当前像素点的应具有的权值；在当前像素点受噪声影响较大时，最大权值大于该像素点应具有的权值，因此采用权值最大值的方法无法充分发挥高相似像素点在估计值中应有的作用。为此，本文提出一种权重重分配方法，以此提高当前像素点的利用率。

权重重分配法采用权重最大值与权重均值之间的比值判断搜索邻域中图像块与当前像素邻域的相似程度。当权重最大值与权重均值的比值大于某个阈值时，说明该搜索区域中的其他图像块与当前邻域相似性较低。若按传统NLM算法进行加权相加，相似率较低的邻域会降低像素估计值的准确性。因此，在改进方法中增大当前像素点在估计值中占有的比例，降低低相似邻域在估计值中的作用，以此来减少低相似像素点对估计值的影响。相反，当权重最大值与权重均值之间的比值小于某个给定阈值时，说明搜索邻域中相似性较高的图像块相对较多，此时减少当前邻域在估计值中占有的比例，提高相似邻域的权值，避免加权过重现象的出现。权重重分配方法可表示为

$$
{ N L } [ i ] = \left\{ \begin{array} { l l } { p * W _ { \mathrm { m a x } } * X _ { i } + ( 1 - p ) * \sum _ { j \subset Q } W _ { j } * X _ { j } \quad } & { \displaystyle \frac { W _ { \mathrm { m a x } } } { W _ { s u m } } * \left| N _ { i } \right| > A } \\ { \sum _ { j \subset Q } W _ { j } * X _ { j } \quad } & { \displaystyle \sharp \sharp \overset { . . . } { \sum } } \end{array} \right.
$$

其中：NL[i]表示像素点 $i$ 的估计值， $p$ 为当前像素点在像素估计中占有的比例， $W _ { m a x }$ 、 $W _ { s u m }$ 分别表示权重的最大值及所有权值的和， $X _ { i }$ 、 $X _ { j }$ 表示点 $i , j$ 的像素值， $W _ { j }$ 为 $j$ 点的权值，$\varrho$ 表示搜索邻域的坐标域， $A$ 为阈值。

# 3 实验结果与分析

# 3.1 实验设置及实现

为验证提出的DKGNLM算法的去噪性能，本文通过实验对DKGNLM算法和传统NLM算法、分别含有高斯核(GNLM)、正弦核(WNLM)的改进NLM 算法的图像去噪效果进行对比。采用Lena、Tree、House 和Cameraman 四种不同细节的图像（如图2所示）进行实验。对四幅图像加入均值为0，噪声标准差o分别为10、15、20、25和30的加性高斯白噪声，得到的噪声图像即为实验中需要处理的噪声图像。为了保证实验的可比性，本文采用与文献[4-7]一致的方法，算法测试参数采用经验值，相似邻域窗口大小设置为 $7 { \times } 7$ ,搜索邻域窗口大小设置为 $2 1 \times 2 1$

![](images/e1592f6a4bfb957ef91126fb0ed03cf6c485758aac8e5ec8b1d878e22e6dcefd.jpg)  
图2测试图像

# 3.2评价标准

本文通过视觉效果及峰值信噪度量算法的去噪性能。视觉效果通过人类视觉系统感知图像质量变化，它不仅依赖于人来大脑视觉系统，还与人类后天的文化背景、生活环境等有着密切联系，因此主观评价标准一直以来都存在着争议性。然而，在图像中存在伪影、过渡平滑等现象时，主观评价标准较客观评价标准更具有说服力。

峰值信噪比[18](peak signal to noise ratio,PSNR)作为一种客观的评价标准，通过数据有效展示算法的去噪性能。PSNR 定义为

$$
P S N R = 1 0 \log _ { 1 0 } \Biggl ( \frac { 2 5 5 ^ { 2 } } { M S E } \Biggr )
$$

其中： $M S E$ 为均方误差，其模型可表示为

$$
M S E = \frac { 1 } { M N } { \sum } _ { x = 1 } ^ { M } { \sum } _ { y = 1 } ^ { N } [ X ( x , y ) - Y ( x , y ) ] ^ { 2 }
$$

这里， $X ( x , y ) , \ Y ( x , y )$ 分别表示原始图像与滤波图像中像素点 $( x , y )$ 的值， $M$ 、 $N$ 分别表示图像的高度和宽度。

# 3.3 参数的确定

在实验过程中采用含有噪声标准差为30的4种噪声图像进行参数的实验，利用控制变量的方法确定平滑参数的最佳值，即先固定第二个参数，将第一个参数作为未知数进行实验；再固定第一个参数，针对第二个参数进行实验，最终得到参数最佳值。

# 3.3.1平滑参数的确定

改进算法的去噪效果容易受到平滑参数h1、h2的影响，平滑参数的大小决定算法对图像滤波的平滑程度。平滑参数较大时，在去除噪声的同时也会滤除图像的一些细节信息，造成去噪图像的模糊。平滑参数较小时，图像中的噪声不能被充分滤除，去噪效果降低。图3为确定平滑参数的实验结果，采用PSNR值作为评价标准。PSNR值越大，算法的去噪性能越高，此时参数越符合实验要求。平滑参数范围设置在 $0 { \sim } 0 . 1$ 。

![](images/a90ac5c26caf688a50907dc1b86596482e1bde1bdd1c7a1d4809331daa51b717.jpg)  
(b)PSNR 随h2变换曲线

图3平滑参数的曲线图

在确定h1的实验中，先将h2取值固定为0.03，然后在0至0.1的范围内改变h1的值，计算算法在不同h1取值下的去噪结果，结果如图3(a)所示。从结果可以看出，当h1取值小于0.02时，PSNR值随着h1的增加而增加。当h1取值大于0.03时，由于平滑参数较大，导致算法在滤除噪声的同时丢失了图像中的细节信息，降低了图像的清晰度，因此PSNR值随1增加而明显下降。当h1位于0.02与0.03之间时，PSNR值变化较小，此时的平滑参数使算法的去噪效果达到最佳值，在滤除图像噪声的同时最大限度保存图像中原有信息。

在确定h2的实验中，将h1的取值固定为0.02，在0至0.1的范围内改变h2的值。平滑参数h2同h1的作用相同，都是控制图像的平滑程度，因此，测试图像的PSNR变换趋势同1相似，均是先上升后下降，在PSNR值最大时，取得了最佳的去噪效果。通过上述的两个实验结果确定h1、2的最佳取值分别为0.02、0.04。

# 3.3.2阈值A及权值比例p的确定

在确定参数 $A$ 的实验中，首先假设 $p$ 为0.05，并在0到10之间搜索参数 $A$ 的最佳值，实验结果如图4(a)所示。当参数 $A$ 小于某一阈值时，PSNR值随着阈值的增加而缓慢提高，此时搜索区域中的相似性在减少，但搜索区域中的相似邻域数量可以保证相似估计值的准确性。然而当相似性降低到一定程度时，PSNR值开始下降，当临界阈值为8时，针对Lena图像去噪结果的PSNR达到了最大值，说明邻域的相似程度达到最佳。而针对Tree、Cameraman图像去噪结果的变换趋势在阈值分别为7、9时，PSNR达到了最大值。因此，本文中将 $A$ 的值确定为8。

在确定参数 $p$ 时，首先确定阈值 $A$ 为8，并在 $0 { \sim } 0 . 0 8$ 搜索$p$ 的最佳值，实验结果如图4(b)所示。从图中可以看出当 $p$ 值在 $0 { \sim } 0 . 0 1$ 时，PSNR值快速提高，尤其对于Tree及Cameraman图像，它们在 $p$ 为0.01时的PSNR与 $p$ 为0时的PSNR相比，均相差了 $4 . 0 \mathrm { d B }$ 以上。从图2的测试图像中可以看出，这两张图像中细节信息相对较少，相似邻域在整张图片中占有的比例较细节丰富的Lena 图像要大，该现象完全符合文中提出的权重重分配的原理。当 $p$ 大于0.01时，PSNR值随着 $p$ 的增大而逐渐减小，此时由于当前像素的权值过大，反而降低了算法的去噪性能。

![](images/6308ee3c456ed4a87200bb33adfb474d23e0206014dffd1f254fc4d702e6e628.jpg)  
图4参数p及A对去噪效果的影响图

# 3.4实验结果及其对比分析

表1\~4为几种去噪算法针对不同噪声程度的图像进行去噪的PSNR值结果。从表1中可以看出，当噪声标准差为10时，WNLM的PSNR取得最大值，而本文改进算法的PSNR虽不是最大值，但相对于最大值只相差 $0 . 0 9 \mathrm { d B }$ 。随着噪声强度的增加，改进算法的PSNR值均为最大值，在含有标准差为20 的噪声图像中，改进算法处理结果的PSNR值比其他几种算法提高$1 . 1 7 \mathrm { d B }$ 。其他图像的实验结果同表1数据的变换趋势大体相似，在含噪较低时，改进算法的PSNR值虽不是最好，但与最高PSNR值平均相差小于 $0 . 3 \mathrm { d B }$ ；噪声较强时，改进算法的PSNR值均达到最大值，且比传统NLM算法平均提高1.2dB。

表1Lena 图像去噪峰值信噪比  

<html><body><table><tr><td>0</td><td>Noise</td><td>NLM</td><td>GNLM</td><td>WNLM</td><td>DKGNLM</td></tr><tr><td>10</td><td>27.79</td><td>30.83</td><td>31.04</td><td>31.24</td><td>31.15</td></tr><tr><td>15</td><td>24.78</td><td>29.95</td><td>29.75</td><td>30.05</td><td>30.07</td></tr><tr><td>20</td><td>22.49</td><td>29.06</td><td>28.54</td><td>29.07</td><td>30.24</td></tr><tr><td>25</td><td>20.27</td><td>28.01</td><td>27.77</td><td>27.97</td><td>29.32</td></tr><tr><td>30</td><td>19.19</td><td>27.47</td><td>26.97</td><td>27.40</td><td>28.67</td></tr></table></body></html>

表2Tree 图像去噪峰值信噪比  

<html><body><table><tr><td>0</td><td>Noise</td><td>NLM</td><td>GNLM</td><td>WNLM</td><td>DKGNLM</td></tr><tr><td>10</td><td>27.77</td><td>27.71</td><td>27.80</td><td>28.05</td><td>27.86</td></tr><tr><td>15</td><td>24.91</td><td>27.17</td><td>26.98</td><td>27.55</td><td>27.43</td></tr><tr><td>20</td><td>22.71</td><td>26.54</td><td>26.10</td><td>26.87</td><td>27.43</td></tr><tr><td>25</td><td>21.04</td><td>25.92</td><td>25.34</td><td>25.96</td><td>26.75</td></tr><tr><td>30</td><td>19.65</td><td>24.28</td><td>24.91</td><td>24.50</td><td>25.59</td></tr></table></body></html>

表3House 图像去噪峰值信噪比  

<html><body><table><tr><td>0</td><td>Noise</td><td>NLM</td><td>GNLM</td><td>WNLM</td><td>DKGNLM</td></tr><tr><td>10</td><td>27.93</td><td>34.18</td><td>33.42</td><td>34.43</td><td>34.32</td></tr><tr><td>15</td><td>24.76</td><td>33.23</td><td>32.59</td><td>33.20</td><td>33.13</td></tr><tr><td>20</td><td>22.44</td><td>32.44</td><td>31.89</td><td>32.54</td><td>33.59</td></tr><tr><td>25</td><td>20.54</td><td>31.53</td><td>30.98</td><td>31.45</td><td>32.95</td></tr><tr><td>30</td><td>19.06</td><td>30.68</td><td>30.09</td><td>31.25</td><td>31.76</td></tr></table></body></html>

表4Cameraman 图像去噪峰值信噪比  

<html><body><table><tr><td>0</td><td>Noise</td><td>NLM</td><td>GNLM</td><td>WNLM</td><td>DKGNLM</td></tr><tr><td>10</td><td>27.91</td><td>30.71</td><td>31.24</td><td>31.24</td><td>30.98</td></tr><tr><td>15</td><td>24.97</td><td>28.92</td><td>30.04</td><td>30.05</td><td>30.27</td></tr><tr><td>20</td><td>22.76</td><td>28.78</td><td>29.56</td><td>29.53</td><td>30.79</td></tr><tr><td>25</td><td>20.98</td><td>28.51</td><td>28.62</td><td>28.76</td><td>29.98</td></tr><tr><td>30</td><td>19.40</td><td>27.77</td><td>27.83</td><td>28.13</td><td>28.86</td></tr></table></body></html>

图5给出了Lena 图像对比实验的视觉效果图。实验结果显示，传统的NLM算法虽然去除了图像中含有的噪声，但过度平滑导致图像中的部分细节信息丢失，致使五官、头发、帽檐等细节及边缘信息较丰富的区域模糊。GNLM和WNLM算法相对于传统NLM算法去噪效果有了提升，降低了图像的模糊程度，但相比于本文提出的DKGNLM算法仍存在着细节丢失较重的问题。本文中提出的改进算法明显降低了图像模糊程度，五官清晰，在帽子及下巴处有了明显的边界区分，保留了图像更多的细节信息。

![](images/f28da1b7e7aac13f8b6cca88b82c30bada8dc7b0a4707f32da4f4e7a6cbc2f42.jpg)  
图5不同算法滤波效果对比图

# 4 结束语

本文提出了一种改进的非局部均值滤波算法，采用邻域梯度特征与欧氏距离相结合代替传统NLM算法中单一的欧氏距离，以此度量邻域间的相似性，降低噪声对相似性计算的影响，从而提高像素邻域间相似性计算的精确度。同时通过对各种核函数的分析研究，提出一种双核函数，计算相似像素点的权重值，以减少非相似性像素对去噪值计算的影响；采用新的权重重分配方法，提升高相似像素点在去噪像素估计值中权值的准确性。从对含有不同程度噪声图像进行去噪的对比实验结果可知：本文提出的改进算法可以有效降低图像的模糊程度，提高图像的去噪效果，图像所含噪声越严重，去噪效果提升越明显。

# 参考文献：

[1]Zeng Weili,Lu Xiaobo,Tan Xianghua.Non-linear fourth-order telegraphdiffusion equation for noise removal [J]. Image Processing Iet, 2O13,7 (4): 335-342   
[2]Tang Min,Wang Yihong.An asymptotic preserving method for strongly anisotropic diffusion equations based on field line integration [J]. Journal of Computational Physics,2017,330:735-748   
[3]Zhu Yining,Zhao Mengliu, Zhao Yunsong,et al.Noise reduction with low dose CT data based on a modified ROF model[J]. Optics Express,2012,20 (16): 17987-8004   
[4]Zeng Weili,Lu Xiaobo,Tan Xianghua.A Class of Fourth-Order TelegraphDiffusion Equations for Image Restoration [J].Journal of Applied Mathematics,2011,(2011-06-26),2011,2011(1-4): 447-469   
[5]Buades A, CollB,Morel JM.A Review of Image Denoising Algorithms, with a New One[J]. Siam Journal on Multiscale Modeling& Simulation, 2005,4(2):490-530   
[6]Van DVD,Kocher M.Nonlocal means with dimensionality reduction and SURE-based parameter selection[J].IEEE Trans on Image Processing,2011, 20 (9): 2683-90   
[7]孙伟峰，彭玉华．一种改进的非局部平均去噪方法[J]．电子学报,2010, 38 (4): 923-928   
[8]Deledalle CA,Duval V,Salmon J.Non-local Methods with Shape-Adaptive Patches (NLM-SAP)[J].Journal of Mathematical Imaging& Vision,2012, 43 (2):103-120   
[9] 陈世媛，李小将．基于自适应非局部均值的 SAR 图像相干斑抑制[J]. 系统工程与电子技术,2017,(12):2683-2690   
[10] Park SW,Kang MG.NLM algorithm with weight update[J].Electronics Letters,2010,46 (15): 1061-1063   
[11] Tian Jing,Yu Weiyu,Xie Shengli.On the kernel function selection of nonlocal filtering for image denoising[C]//Proc of International Conference on Machine Learning and Cybernetics.2008:2964-2969 [12]刘晓明，田雨，何微，等．一种改进的非局部均值图像去噪算法[J]. 计算机工程,2012,38(4):199-201 [13]张兆伦．基于非局部均值图像去噪算法研究[D]．南京：南京邮电大学，   
2015 [14]曹璟，周宁宁，洪龙．基于边缘检测的自适应非局部均值去噪算法 [J]. 济南大学学报：自然科学版，2016,30(3):209-214 [15]陈志刚，宋胜锋，李陆冀，等．基于相似原理的点特征松弛匹配算法 [J]．火力与指挥控制,2006,31(1):49-51 [16] Vignesh R,Oh B T,Kuo C C J. Fast non-local means (NLM) computation with probabilistic early termination [J].IEEE Signal Processing Letters,   
2010,17 (3): 277-280 [17]Li Hongjun, Suen Ching Y.A novel non-local means image denoising method based on grey theory[J] Pattern Recognition,2016,49(1): 237-248. [18] Wang Xinjian, Chen Guangyi, Luo Guangchun.A logarithm-based image denoising method for a mixture of Gaussian white noise and signal dependent noise [J].Journal of Inteligent & Fuzzy Systems,2O17,33(1):   
281-291