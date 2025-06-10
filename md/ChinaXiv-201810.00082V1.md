# 自适应不同条件的车牌检测算法

杨秀杰1，李芳²

(1．重庆电子工程职业学院，计算机学院，重庆 401331;2.重庆大学，计算机学院，重庆 沙坪坝 400044)

摘要：车牌检测(license plate detection，LPD)是自动车牌识别中(automatic icense plate recognition，ALPR)主要步骤，针对不同条件下车牌检测速度慢和检测精度低的问题，提出了一种改进改进自适应形态闭和开操作的车牌检测算法。该算法首先采用局部直方图对车牌图像均衡化处理，使用自适应形态闭操作对所有灰度化区域进行平滑处理，之后引入局部自适应阈值处理，能得到平滑图像和被分离的车牌，最后采用形态学开操作，将外部区域和车牌数连接部分分离。实验结果表明，所提方法的检测精度高于其他算法，同时，平均检测时间少于其他算法，适合不同条件下实时车牌检测。

关键词：车牌检测；局部直方图；自适应形态闭操作；局部自适应阈值；形态学开操作 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2018.06.0423

# Adaptive license detection algorithm for different conditions

Yang Xiujie1, Li Fang² (1.CollgeofComputer,ChongqingCollegeofElectronicEngineering,Chongqing401331,China;2.SchoolofComputer Science,Chongqing University,Chongqing 40o044,China)

Abstract: The license plate detection (LPD)was the main step of automatic license plate recognition (ALPR).According to the problemof slow license plate detection and low detectionaccuracy under diferent conditions,this paper proposed an improvedadaptive morphological closed and open operation to improve the license plate detection algorithm.The algorithm firstused the local histogram to equalize the license plate image.The adaptive morphological closed operation was used to smooth all grayscaleregions,and then introduced the local adaptive threshold procesing toget the smooth image and the separated licenseplate.Finally,the morphological open operation wasadopted to separatetheconnectionpartsbetween the externalregionand thenumberofthelicense plates.The experimentalresults showthat the detectionaccuracyof the proposed method is higher than other algorithms.At the same time,theaverage detection time is less thanother algorithms.The proposed method is suitable for real-time license plate detection under different conditions.

Keywords:license platedetection;local histogram;adaptive morphological closed operation;local adaptive threshold; morphological opening operation

# 0 引言

智能交通系统(intelligent transportation system,ITS)是交通管理的重要组成部分，在降低交通成本方面发挥着巨大的作用[1,2]。车牌自动识别(ALPR)是ITS 中的主要步骤[3-5]。交通监控、保安管理、公共及私人停车以及找寻被盗车辆是其在ITS中的若干应用。因为每辆车都有一个规则的独一无二的车牌号码，且不需要任何新的技术或者材料造成额外的花费。因此，在相关技术中，可视化的ALPR的更新比起其他技术来说，更简单和更便宜[6-8]。

大部分的ALPR系统包含三个主要的部分，车牌检测，字符分割和字符识别。车牌检测是这些步骤中最主要的一步[9,10]。因为字符分割和字符识别的精确度是基于第一步车牌检测。如果车牌定位能精确检测没有额外的区域或者像素，那么字符分割和识别精确度将会提高，针对LPD，提出了很多不同的算法。

文献[11]提出了一种边缘密度和协方差SVM联合的车牌检测方法，该方法使用边缘密度来检测候选板区域，采用链码跟踪和形态学腐蚀去除过长和过短的边缘，保留由于边缘检测器造成的断裂的车牌边缘，之后，使用带有协方差的线性支持向量机进行车牌候选集的验证，以实现视频的快速准确检测。文献[12]中车牌检测中使用频率滤波器和一个新的对比度增强的方法用在危险的情况如雨雾天气、低对比度环境、背景图像中与车牌相似的图片等。文献[13]提出了角落特征的车牌检测，首先，通过选择大梯度阈值去除无角度点，其次，通过使用改进的Harris角落分类器和集群查找车牌候选集，最后，在车牌候选集中降低阈值和检测角度。文献[14]基于小波变换和经验模式分解（EMD）分析的鲁棒方法来搜索图像中牌照的位置，该方法使用小波变换提取图像水平和垂直的细节，然后使用经验模态分解（EMD）查找车牌位置，最后使用希尔伯特变换提出车牌的属性特征。

虽然已经有很多车牌检测方法，但是由于如环境光照、遮挡，运动模糊，车牌失真，天气因素等影响因素，车牌定位仍然是一个挑战。本文在现有方法的基础山，提出了一种适应不同环境的车牌检测算法，该算首先采用自适应形态闭操作(adaptive morphological closing，AMC)对灰度图像进行平滑处理，引入局部自适应阈值处理得到平滑的图像和基本上被分离的车牌，最后为了将车牌数据与外部区域分离，进行形态学开操作(morphologicalopening,MO)实现车牌精准检测，通过在真实数据集上使用opencv库进行实验，结果表明，本文提出的算法在精确度和处理时间上优于其他的一些算法，适用于不同条件下的实时车牌检测。

# 改进AMC和MO的车牌检测算法

本文提出的车牌检测方法流程图如图1所示，该方法对自适应形态学闭操作进行改进，在自适应形态学闭操作和开操作之间引入局部自适应阈值，使得检测的车牌更平滑与清晰。

自适应形态学 局部自适应阈图像预处理 形态学开操作闭操作 值处理

本文中预处理方法是改进的直方图均衡化，直方图均衡化是为了帮助图像对比度的延伸。图像的直方图均衡化将像素的值限制在0\~L-1的范围内，如式（1）所示。

$$
s _ { k } = \frac { L - 1 } { N } \sum _ { i = 0 } ^ { k } n _ { i }
$$

其中： $k = 1 , 2 , . . . , L - 1$ ，其中 $s _ { k }$ 是变换像素的新值， $N$ 表示像素的数量和 $n _ { i }$ 表示像素值等于 $i$ 的数量。直方图均衡方法对于均匀光照条件充足情况下效果较好，但是如果光照或者反射不均匀，则会导致检测精度下降。为了克服这个问题，采用局部直方图均衡方法，来解决光照条件不理想的车牌检测问题，图2给出直方图均衡和局部直方图均衡之间的检测效果对比。

![](images/407d1408bf20ef9783fad30d0027b71b99c75ed007b05d7ed6a6ece084793290.jpg)  
图1本文车牌检测算法流程  
图2不同方法的检测效果  
图3使用构造结构元素的自适应形态学闭操作

图2中，(a)是原始图片，(b)是直方图均衡结果，(c)是局部直方图均衡结果。可以看出原始图像对比度很低，看起来很暗。在该图像上应用直方图均衡化，并且输出图像如图(b)所示，整个图像都得到增强，效果并不好，有的区域太过饱和，为了解决这个问题，应用局部直方图均衡方法，在这个方法中，车牌图像被分成不同的重叠块，在每个重叠块上进行操作。

# 1.1改进自适应形态学闭操作

形态学闭操作的目标是为了填充图像的特征并平滑车牌区域，常见的形态学闭操作使用一个固定的结构化特征（structuringelement，SE)。在应用SE时，其尺寸和形状不能改变，该固定的SE特征在实际应用中缩放比例是非常重要的也是一个缺陷。因此，使用多融合的SE 特征也是一个方法，但是其计算成本会大大增加，为了解决这一问题，自适应形态学闭操作被使用，在自适应形态学闭操作使用的主要方法中，取一组SE特征进行形态学闭操作。

对于图像A和结构元素B，腐蚀和膨胀操作的简单形态学操作被定义为

$$
\left\{ \begin{array} { l l } { \displaystyle A \Theta B ^ { s } \left( i , j \right) = \operatorname* { m i n } _ { \left( t _ { 1 } , t _ { 2 } \right) \in B _ { i , j } } \left( A \left( t _ { 1 } , t _ { 2 } \right) \right) } \\ { \displaystyle A \oplus B ^ { s } \left( i , j \right) = \operatorname* { m a x } _ { \left( t _ { 1 } , t _ { 2 } \right) \in B _ { i , j } } \left( A \left( t _ { 1 } , t _ { 2 } \right) \right) } \end{array} \right.
$$

其中: $\Theta$ 表示腐蚀操作， $\oplus$ 表示膨胀操作， $\boldsymbol { B } ^ { s }$ 表示集合B 的对称集， $A { \left( t _ { 1 } , t _ { 2 } \right) }$ 表示被 $\left( t _ { 1 } , t _ { 2 } \right)$ 操作转换后的像素值，在腐蚀和膨化的基础上，闭合操作被定义为

$$
\boldsymbol { A } \cdot \boldsymbol { B } = \Big ( \boldsymbol { A } \oplus \boldsymbol { B } ^ { s } \Big ) \Theta \boldsymbol { B }
$$

闭操作会消除狭窄的剪短和长细的鸿沟，消除小的空洞，并填补图像中的断裂。基于自适应形态学闭操作取代使用多个闭操作的串联，能够使用结构化特征进行闭操作，图3显示AMC对使用一组SE进行的操作。

A(i,j) y(i,j) Y三o E(i，j) 腐蚀 构建结构元素 膨胀

其中 $d$ 是三 总中一个基础元素， $\gamma = \left( A \oplus d ^ { s } \right) \left( i , j \right)$ ，通过应用此程序可节省内存等资源的数量。

本文在自适应形态学闭操作后面加入局部自适应阈值处理，使用的局部自适应阈值处理使用矩形窗口代替了传统的正方形窗口，这样使得能检测更多的像素，且计算时间被减少。在伪代码中，in表示输出图像， $i n t$ 表示完整的图像， $\mathbf { \nabla } _ { m }$ 表示车牌的宽度， $n$ 表示车牌的高度， $w$ 表示输入图像的宽度， $h$ 表示输入图像的高度， $t$ 表示阈值，则局部阈值处理伪代码如下：

procedureAdaptiveThreshold $\prime ( i n , o u t , m , n , w , h )$   
for $i = 0$ to $w$ do （204号 $s u m \gets 0$ for $j = 0$ to $h$ do

$s u m \gets s u m + i n [ i , j ]$ if $i = 0$ then intImg[i, $j ]  s u m$ else $i n t I m g [ i , j ] \longleftarrow i n t I m g [ i - 1 , j ] + s u m$ end if end for end for for $i = 0$ to $w$ do for $j = 0$ to $h$ do $x _ { 1 } \gets i - s / 2$ {border checking is not shown/ $x _ { 2 } \gets i { + } s / 2$ （202 $y _ { 1 } \gets j { - } s / 2$ （20 $y _ { 2 } \gets j + s / 2$ $c o u n t \gets ( x _ { 2 } – x _ { 1 } ) { \times } ( y _ { 2 } – y _ { 1 } )$ sum $i n t I m g [ x _ { 2 } , y _ { 2 } ] - i n t I m g [ x _ { 2 } , y _ { 1 } - 1 ] - i n t I m g [ x _ { 1 } - 1 , y _ { 2 } ] + i n t I m g [ x _ { 1 } - 1 , y _ { 1 } - 1 ] = 0 .$ 证 $( i n [ i , j ] { \times } c o u n t ) \leq ( s u m { \times } ( 1 0 0 - t ) / 1 0 0 )$ then $o u t [ i , j ] \gets 0$ else $o u t [ i , j ] \gets 2 5 5$ end if end for end for

从 $m$ 和 $n$ 中，车牌的最小化和最大化被需要，主要通过空间因素或者车辆到相机之间的距离影响最小化和最大化因素。在车牌检测中，车牌的 $m$ 和 $n$ 通过式(4)进行计算。

$$
\begin{array} { l } { \displaystyle { \left\{ m = \frac { 1 } { 2 } \big ( L P _ { \mathrm { m i n } , w i d t h } + L P _ { \mathrm { m a x } , w i d t h } \big ) \right. } } \\ { \displaystyle { \left. \left[ n = \frac { 1 } { 2 } \big ( L P _ { \mathrm { m i n } , h e i g h t } + L P _ { \mathrm { m a x } , h e i g h t } \big ) \right. \right. } } \end{array}
$$

其中: $L P _ { \mathrm { m i n } , w i d t h }$ 和 $L P _ { \operatorname* { m a x } , w i d t h }$ 分别表示车牌宽度的最小值和最大值， $L P _ { \mathrm { m i n } , h e i g h t }$ 和 $L P _ { \mathrm { m a x } , h e i g h t }$ 分别表示车牌高度的最小值和最大值。局部自适应阈值检测车牌区域方法中，出现车牌区域和非车牌区域的连接，为了解决车牌区域和非车牌区域的连接问题，进行形态学开操作。

# 1.2形态学开操作

通风器，散热器和保险杆通常与车牌区域相连接。经过形态学开操作扩张后腐蚀，这些操作能断开连接较弱的区域。在腐蚀和膨化的基础上，开合操作与闭操作正好相反，被定义为

$$
A \circ B = \left( A \Theta B ^ { s } \right) \oplus B
$$

开操作使得对象的轮廓变得光滑，断开狭窄的剪短和消除细的突出物。在图4中给出了与车牌连接的区域图像，经过形态学开操作以后将连接区域分开。

![](images/431236e74c5103b37c0c14aff5f6a915e71384b58001437b0d5c0fb035532e9c.jpg)  
图4形态学开操作

图4中(a)和(b)描绘了两个样本图像，其中缓冲器已经附接到LP区域，车牌区域与其他区域之间存在连接，形态开操作分别将图(a)和(b)中接连区域分开，显示在图(c(d)中。

形态学开、闭操作是使用一个 $K \times K$ 的矩阵对车牌图像进行操作，因此对于本文的算法，对于输入图像为 $w \times h$ ，w是输入图像的宽度，h是输入图像的高度，计算复杂度为$O \big ( w \times h \times K \times K \big ) ~ .$ 0

# 2 实验结果与分析

本文实验使用的数据集包含有2232幅真实照片，其中有通过真实场景中商业照相机拍摄的照片，如高速公路、自动闸门、白天和夜晚的照片以及不同天气条件下拍摄的照片，部分图片不止一个车牌。如图5所示部分示例数据集。

![](images/89612a2b740832fa346ba3da3efac4025da21288bac6aee56f159e1c8ff4890e.jpg)

(c）实验车牌图像3

![](images/5859f04e9c06ea081955f5c996842a61a31c950cbad75b9675e584df45e3e1e8.jpg)  
图5实验用到的部分实际车牌图像

本文提出的算法使用 $^ { C + + }$ 和OpenvCV3.2库实现，局部直方图均衡和自适应形态学闭操作是在GPU上通过使用OpenCL实现的。

本文使用检出率和检出时间来验证本文方法有效性，检出率定义为车牌被完全检测的数量，检测出的车牌应该有所有的特征，而不仅是通风机或者保险杆的数量；检测时间表示算法开始和结束直接所用的时间，这个时间包括从磁盘中读照片到将结果显示出来所有的时间，而不仅是计算的时间。

图6给出了通过本文方法应用于图5中的样本图像而提取的牌照。

![](images/698cd1e1e3130e1e3dea1f69ee6fb095a3d458d9295740516b465ac07c4636af.jpg)

经过大量实验求平均值，图(a)中提取车牌的时间为20.53毫秒，图(a)中提取车牌的时间为21.01毫秒，平均用时20.77毫秒，运行时间少，适合实时的车牌检测与识别，说明所提方法可行性与有效性。

为验证本文算法的有效性，对实际高速公路收费站得到的18625幅图像进行测试，包括不同条件下的车牌图像（黑夜、白天、阴天、雨天、完整和残缺等条件)，得到的平均车牌检出率为 $9 9 . 3 2 \%$ ，平均车牌提取时间为 $2 1 . 0 5 ~ \mathrm { m s }$ ，说明本文算法的有效性。

将所提方法与现有方法进行比较，图7和图8分别给出了不同方法的车牌检测检出率和车牌检测时间结果对比。现有车牌检测方法有：经验模式分解[14](empirical mode decomposition,EMD)、二值化[l2](binarization,BIN)、模糊化的Gabor 滤波器[15](fuzzified gabor filter,FGF)、离散小波变换[14] (discrete wavelettransform,DWT)、垂直边缘检测算法[16](vertical edge detectionalgorithm，VEDA)、LOG 算子边缘检测算法[16](LOG edgedetectionalgorithm,LOGEDA)、Harris角点检测[14]、强度方差和边缘密度(intensity variance&edge density,IV&ED)检测算法[12]。

![](images/fdf22a40c4ee666b1f89f5e3c6d0d60b624463ee23d1731b54cf039a88fa0122.jpg)  
图7不同算法的车牌检出率

从图7可以看出，所提方法的检测率高于其他方法，检出率高达超过 $9 9 . 3 \%$ ，这是因为本文方法使用自适应形态学闭操作，针对不同条件下的车牌能够自适应地实现对比度增强，而自适应阈值处理使用矩形窗口代替了传统的正方形窗口，检测到更多像素，最后的形态学开操作断开车牌相连区域，使得检测区域更光滑。

![](images/914635a3a98e7b6b9936899c358005a416a0c3a12b613a71a6798c52a67b73df.jpg)  
图6本文方法提出的车牌照  
图8不同算法的车牌检出时间

从图8可以看出，所提方法具有最低的检测时间，平均检测时间仅为 $2 0 . 0 1 ~ \mathrm { m s }$ ，能够用于车牌的实时检测，这是因为所提算法中自适应阈值处理中使用矩形窗口，矩形窗口比方形窗□中有更多的像素，这会导致计算时间缩短。

# 3 结束语

为了提高车牌检测的检测率和降低检测时间，提出了一种改进自适应形态学闭操作的车牌检测算法。该算法分为四个部分，首先使用局部直方图均衡对车牌进行预处理，然后使用自适应形态学闭操作，针对不同条件下车牌自适应地实现对比度增强，之后对处理过的图像进行自适应阈值处理，采集更多像素、减少计算时间，最后使用形态学开操作将车牌与其他区域接连部分分开，最终实现了车牌的快速精准检测。在不同情况下真实数据集上的实验结果表明，所提方法能够实现不同条件下车牌快速检测，平均检测率达到 $9 9 . 3 \%$ ，检测时间仅为20.01毫秒，在检出率和检测时间两个性能方面都优于其他现有方法。

# 参考文献：

[1]Sadek A. Intelligent Transportation System [J].Perspectives in Science, 2016,7 (3): 304-311.   
[2]赵会群，李会峰，刘金塞.RFID物联网复杂事件模式聚类算法研究[J]. 计算机应用研究,2018,35(2):339-341.(Zhao Huiqun,Li Huifeng,Liu Jinluan.Study on RFID complex event pattern clustering algorithm of Internet of things [J].Application Research of Computers,2018,35 (2): 339-341.)   
[3]Janowski L,Kozlowski P,Baran R,et al.Quality assessment for a visual and automatic license plate recognition [J].Multimedia Tools& Applications,2014,68 (1): 23-40.   
[4]Do HN,Vo M T,Vuong B Q,et al.Automatic license plate recognition using mobile device [Cl// Proc of International Conference on Advanced Technologies for Communications.2016: 268-271.   
[5]Janowski L,Kozlowski P,Baran R,et al. Quality assessment for a visual and automatic license plate recognition [J].Multimedia Tools and Applications,2014,68(1): 23-40.   
[6]Rashedi E,Nezamabadi-Pour H.A hierarchical algorithm for vehicle license plate localization [J].Multimedia Tools and Applications,2018,77 (2): 2771-2790.   
[7]Bajpai A.A survey on automatic vehicle number plate detection system [J]. International Journal of Computer Science Trends and Technology,2017,5 (2): 291-297.   
[8]Wang Ran,Xia Yuanchun,Wang Guoyou,et al.License plate localization in complex scenes based on oriented FAST and rotated BRIEF feature [J]. Journal of Electronic Imaging,2015,24(5):1-10.   
[9]牛博雅，黄琳琳，胡健．自然场景下的车牌检测与识别算法[J].信号 处理,2016,32(7): 787-794.(Niu Boya,Huang Linlin,Hu Jian.Detection and recognition algorithm for license plate in natural scene [J]. Journal of Signal Processing,2016,32(7):787-794.)   
[10] Du S,Ibrahim M, Shehata M,et al.Automatic license plate recognition (ALPR):a state-of-the-art review [J].IEEE Trans on Circuits & Systems for Video Technology,2013,23(2):311-325.   
[11] Feng Boyuan,Ren Mingwu,Zhang Xuyao,et al.Effective license plate detection using fast candidate region selection and covariance feature based filtering [Cl// Proc of the 1lth IEEE International Conference on Advanced Video and Signal Based Surveillance.2O14: 1-60.   
[12] Azam S,Islam M M.Automatic license plate detection in hazardous condition [J]. Journal of Visual Communication and Image Representation, 2016,36: 172-186.   
[13] Panchal T,Patel H,Panchal A.License plate detection using Harris corner and character segmentation by integrated approach from an image [J]. Procedia Computer Science,2016,79: 419-425.   
[14] Yu Shouyuan,Li Baopu, Zhang Qi,et al.A novel license plate location method based on wavelet transform and EMD analysis [J].Pattern Recognition,2015,48 (1): 114-125.   
[15] Samma H,Lim C P,Saleh JM,et al.A memetic-based fuzzy support vector machine model and its application to license plate recognition [J]. Memetic computing,2016,8(3): 235-251.   
[16] Gou Chao,Wang Kunfeng，Yao Yanjie,et al.Vehicle license plate recognition based on extremal regions and restricted Boltzmann machines [J].IEEE Trans on Intelligent Transportation Systems,2016,17(4): 1096-1107.