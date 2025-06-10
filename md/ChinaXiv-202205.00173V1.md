# 基于概率霍夫变换的太阳射电II和Ⅱ型暴自动识别及参数提取

\*

沈发新1,2，高冠男1,，汪 敏,3(1．中国科学院云南天文台，云南 昆明 650011;2．中国科学院大学，北京1000493．中国科学院天体结构与演化重点实验室，云南 昆明650216)

摘要：耀斑和日冕物质抛射（Coronal MassEjection，CME）期间产生的非热高能粒子流和激波是产生灾害性空间天气事件的两种主要因素，它们主要观测特征分别是具有快速频率漂移特征的射电Ⅲ型暴和具有较为缓慢频率漂移的射电Ⅱ型暴。本文主要介绍了使用概率霍夫变换(Probabilistic Hough Transform)的方法，在观测数据中自动识别出太阳射电III型暴和ⅡI型射电暴，并提取射电Ⅲ和Ⅱ型暴的特征参数，最后利用识别出的射电Ⅱ型暴的物理参数估计了CME激波的速度。

关键词：太阳爆发；太阳射电暴；概率霍夫变换；自动识别中图分类号：P162.11文献标识码：A文章编号：xxxxx

# 0引言

作为一个非常活跃的天体，太阳上经常会有剧烈活动或爆发现象（例如耀斑和CME）。耀斑和CME过程中产生的高能粒子和激波等在日地空间中传播，有可能会到达地球，由此引发一系列的日地物理效应（例如太阳高能粒子事件、地磁暴等），对人类的航天工程、通讯设施、以及长距离输油管道等都会有非常重要的影响。因此，为了对空间天气进行有效的预报和预警，减少灾害性空间天气对人类的生产生活的破坏，继续对耀斑和CME过程中产生的高能粒子和激波进行深入和细致的研究是有必要的。

一般来说，天体射电信号都十分微弱，但太阳射电暴的信号略强。太阳射电爆发指的是太阳活动期间在射电波段出现的剧烈且短促的流量增强现象，根据其在射电动态频谱上展现的不同的形态，可以分为太阳射电I-V型射电暴。太阳射电II型和Ⅱ型暴是目前研究的比较多的两种类型的太阳射电暴，分别是由耀斑和CME期间产生的高能电子束流和激波所导致的。

具体来说，耀斑和CME期间的磁重联加速电子形成高能电子，高能电子束流以亚相对论速度（约为 $0 . 2 { \sim } 0 . 6$ c）沿着磁力线快速运动引起周围的等离子振荡产生射电Ⅲ型暴，因此射电IⅢ型暴在射电动态频谱上展现出快速的频率漂移，射电Ⅲ型暴是高能电子束流的最佳示踪器。

而CME在日冕和行星际空间快速运动时，当CME的速度超过本地的阿尔芬速度时，会产生日冕激波或行星际激波。目前通常认为太阳射电ⅡI型暴是由于激波在日冕中向外传播引起等离子体振荡产生朗缪波，再转换为电磁波辐射并以本征等离子体频率和二倍频向外辐射。所以，射电ⅡI型暴的观测特征一般具有基频和二次谐频结构，由于激波的运动速度远低于高能电子束流，因此太阳射电Ⅱ型暴在射电动态频谱上通常表现为缓慢的频率漂移。射电Ⅱ型暴可以被视作CME激波的最佳示踪器。

目前通常认为太阳射电II型和ⅡI型暴的主要辐射机制为等离子体辐射，根据等离子体辐射的特点可以通过射电暴的信号频率直接得到射电辐射源所在区域的密度。再根据日冕密度模型可以获得辐射源所处的日冕高度，进而获得辐射源的运动速度，例如CME激波速度[]。

现有的太阳射电观测设备普遍有着较高的频率分辨率和时间分辨率，数据量较大，如果仅

采用人工识别的方法的话，效率上无法满足实际需求。到目前为止,世界上已经发展了多种太  
阳射电暴识别算法。这些算法从不同角度处理观测数据，如对流量数据使用阈值法来确认爆发[2]  
的有或无"，对频谱图像数据使用霍夫变换和主动轮廓的方法来确定爆发事件的频率-时间关[3]  
系。

本文在这些识别算法的基础上，进一步使用了概率霍夫变换的方法，提取太阳射电ⅢI型和ⅡI型暴的起止时间、起止频率、频率漂移率等重要参数，提高了识别的准确率和识别速度，并利用识别出的射电暴的物理参数结合相应的物理模型估计了CME激波的速度。这不但对空间天气的预报和预警有重要的实用价值，并对研究高能粒子束流和CME在日冕和行星际空间传播物理过程也具有重要的意义。

# 1射电II型暴的自动识别

射电Ⅲ型暴是一种最常见的太阳射电暴，是太阳剧烈活动后产生的非热高能电子束在日冕[4]和行星际空间中运动的最佳示踪器""，同时也能最先反映太阳暴能量释放和粒子加速等物理过程，是耀斑/CME等太阳爆发事件的先兆。

![](images/be24145be997d994babedab37454874ea9937b1a53ba6b1162aaecbbca2d4685.jpg)  
16FEB 2014   
图1Phoenix4射电频谱仪、Nancay10米波射电频谱仪和WIND/WAVES射电探测器在2014年2月16日获得的一例超宽带射电IⅢI型暴的综合频谱图[5]  
Figure.1 A synoptic spectrogram of a type I radio burst with super-wide frequency band observed by Phoenix 4 decimeter spectrometer，Nancay decameter array and WIND/WAVES on 2014 February $1 6 ^ { [ 5 ] }$

由图1可知，在不同的频率范围内，太阳射电I型暴的频谱特征也不同。例如，低于10MHz,由于Ⅲ型射电暴辐射源所处的日冕密度随着日冕高度的变化较慢，因此，10MHz以下的射电Ⅲ型暴的频率漂移速度要远低于10MHz以上的。而高于10MHz的射电III型暴具有类似直线的结构，这也使得本文使用概率霍夫变换算法来进行射电IⅢ型暴识别成为可能。

本文使用法国南希的十米波天线阵（NDA，Nancay Decameter Array）的太阳射电观测数据进行IⅢ型暴识别，其时间分辨率为1s，其观测频率范围为 $1 0 { - } 8 0 \mathrm { M H z }$ ，其中均匀分布着 400个通道。

为了识别出观测数据中所包含的太阳射电暴的数据，需要对观测数据进行处理。处理过程分为三个部分：(1)原始动态频谱图的分段及背景去除，(2)动态频谱图的前景提取及噪声处理，(3）识别IⅢ型暴事件并提取爆发相关信息。

Dynamic Spectrogram Segment and Remove Background Segment wi thout Background Binarize and Erode Binarization Spectrogram Probabilistic Hough Transform Start and End Coordinates of the Lines

1.1太阳射电频谱数据预处理

在太阳射电动态频谱图上，IⅢ型暴表现为具有快速频率漂移的信号，且不同IⅢ型暴事件的相对强度有很大差异，而背景信号强度则在几小时的时间内逐渐变化。因此我们把原始数据切分成若干小片段，这样有助于去除背景效应，同时也能尽量避免信号强的射电暴和弱的射电暴在同一个数据片段中而导致弱的射电暴不被识别，经过多次实验测试，我们得出每个片段为10分钟的观测数据可以有助于射电暴的识别与参数提取。

在 NDA 可观测的频率范围内，我们将每个数据段的时间长度设置为 600s，采样间隔 500s，即两个相邻数据段的重叠时间为100s，这种切分方式可以保证在某个片段中恰好被切断的爆发事件在下一个片段中可以被识别。因此，切分之后每一个数据段都是一个 $[ 6 0 0 \times 2 5 0 ]$ 的二维数组 $I \big ( t _ { i } , f _ { j } \big )$ 。

由于观测设备的不同通道之间存在明显的增益差异，由此产生的通道效应在频谱图上表现为一条条高亮的横条纹，这些横条纹会造成爆发结构间断，有时甚至会遮盖较弱的爆发事件，影响对太阳射电暴的识别，所以必须先消除观测数据中的通道效应。

具体处理过程为：在各通道的数据上减去该通道所有数据的均值，以去除背景，只保留来自太阳的射电信号，实现各通道数据的归一化，具体公式如下：

$$
I ^ { \prime } \big ( t _ { i } , f _ { j } \big ) = \left| I \big ( t _ { i } , f _ { j } \big ) - \frac { \sum _ { n = a } ^ { b } I \big ( t _ { n } , f _ { j } \big ) } { b - a } \right| \#
$$

其中， $I \big ( t _ { i } , f _ { j } \big )$ 与 $I ^ { \prime } \big ( t _ { i } , f _ { j } \big )$ 分别表示经过处理之前和之后的数据， $a$ 与 $b$ 分别表示该数据段的开始时刻与结束时刻的索引。需要对数据段 $I$ 中的每个值都进行公式1所示的计算，以生成新的消除通道效应后的 $I ^ { \prime }$ 。

1.2Yen算法二值化及图像腐蚀

在对太阳射电动态频谱图进行预处理后，还需要对图像进行二值化，将图像灰度值置为0或255，经过归一化后即将灰度值置为0或1。使其目标前景与背景被区分开来，以便避开背景的影响，利于寻找目标前景中的太阳射电IⅢ型暴事件。

可以对太阳射电动态频谱图进行二值化的算法有很多种，但效果各有优劣。本文使用多种自动确定阈值的算法对观测数据进行测试，生成二值化图像，原始图像与使用各种阈值法进行二值化的图像如图3所示。

![](images/a4be2b70fd2d5e7205cb411df0e9c255335d86159475291c46a9e107cd49a04d.jpg)  
图3各种自动确定阈值的算法的二值化效果

在图3中，Original代表原始图像，其余图像代表各种算法（如：Isodata、Li、Mean、Minimum、Otsu、Triangle、Yen）对原始图像进行二值化的输出结果。其中最为典型的大津法0（即Otsu法）‘，也被称为最大类间方差法，就是一种使用较为广泛的自适应阈值化方法。该算法通过不断尝试将各种值作为阈值，来计算图像的类间方差，选取类间方差最大时的阈值作为对该图像进行二值化的标准。此时，原图像以该阈值作为界限，将图像中的所有像素分为背景像素和目标像素两大类。

经测试，可以从图3的测试结果中看出，只有Yen算法能较好地确定阈值，在二值化后明确区分图像前景与背景，并较好地保留了前景的信息，即爆发的信息，未与背景信息混淆在一起。而其他算法的输出结果未能准确区分图像前景与背景，导致爆发信息被干扰，难以识别。

Yen算法是一种自动多门限阈值法，能够根据太阳射电频谱图像本身的灰度特性，将图像分割为目标前景与背景两个部分。与Otsu法类似，Yen算法也能自动选取最佳阈值T，实现图像的二值分割，但其选择最佳阈值T的依据是最大熵准则，基本思想是通过选择阈值，来使背景和目标所共同提供的信息量最大。

![](images/768b8be95c2e7375b2bdb7ea3ff28127914e9fb0eb71afb131a21b4ac28d027a.jpg)  
Figure.3 Binarization effect of various automatically determining threshold algorithm   
图4经过二值化与腐蚀后的图像  
Figure.4 Image after binarization and erosion

如图4所示，在对太阳射电动态频谱图进行二值化后，还需要对图像进行腐蚀操作，以去除图像中约每小时一次的定标信号，以及某些在频谱图中所占面积较小的瞬时干扰信号。

腐蚀(erosion)是一种基本的形态学运算,可以寻找图像中的极小区域，将图像中的高亮区域进行缩减，在其输出的图中，高亮区域比原图的高亮区域更小。

从图4中可以看出，利用腐蚀算法，频谱图中的定标信号与瞬时干扰都被较好地去除掉了。同时，受到腐蚀算法的影响，爆发事件的结构的边缘也遭到腐蚀，但整体结构与频率漂移率变化不变，不影响后续的识别。

1.3使用概率霍夫变换算法算法识别太阳射电暴事件

霍夫变换是一种特征检测方法，被广泛地应用在图像分析、计算机视觉等领域。使用霍夫变换的方法，可以在图像中寻找某些图形，如：直线、圆、椭圆。

![](images/c227857732904701e8cd1145f3458d1a0e8bc162df93fbb96b47898901334a88.jpg)

Figure.5 Hough transform principle[8]

常用的霍夫变换检测直线的方法,是运用下式在图像空间和参数空间之间,将图像中的曲线转换为参数空间的一点，建立对偶变换。

式中, $\rho$ 为极径； $\alpha$ 为极角, $\alpha$ 取 $0 \mathrm { \sim } 1 8 0 ^ { \circ }$ ；x为像素点相对图像原点的行坐标；y为像素点相对图像原点的列坐标。

![](images/4cafbf2b2832f11129a2dc4e4ac20cb714da92f83ab93da8219f7d96faa6cfb3.jpg)  
图5霍夫变换原理[]   
图6霍夫变换的效果[9]  
Figure.6 The effect of Hough transform[9]

如图6所示，输入的图像被从图像空间转换到参数空间后，在参数空间中存在明显的三个亮点，而参数空间的亮点则代表着输入的图像中的直线结构。利用霍夫变换的直线检测功能，我们可以在太阳射电频谱图像中寻找拥有类似直线的结构的太阳射电暴。

本文使用的概率霍夫变换算法利用解析曲线的几何特性，尽量避免对图像中的每个非零像素进行计算量大的投票过程，而是从点集中随机选取一个像素点进行分析。

概率霍夫变换算法具体步骤如下：

(1)每个区间对应一个累加器 $A ( r , \theta )$ ，从每个区间的点集中随机地选取一个像素点，在参  
数空间中计算0对应的 $r$ 值，并在对应的累计器 $\mathfrak { A } ( r , \theta )$ 上加1;(2)从点集中删除该点并更新累加器;(3)若累加器的值大于提前设定好的阈值，则表示已检测到直线，然后删除该直线上所有  
的点；(4)重复以上3个步骤，直至点集为空。

根据太阳射电I型暴的频谱信号特征，可以知道爆发事件在太阳射电动态频谱图中近似一条倾斜的直线。直线的倾斜程度与太阳射电III型暴的频率漂移率相关。

对太阳射电动态频谱图使用霍夫变换来寻找IⅢ型暴。如果在动态频谱数据片段中存在符合约束条件的直线，则可以认为该动态频谱数据片段中可能存在Ⅲ型暴事件。但是，在数据段中可能还存在其他类型的射电暴，例如太阳射电ⅡI型暴，其在频谱上也可能具有类似直线的图像特征。所以需要根据识别出的频率漂移率来限制及过滤其他类型爆发事件。

动态频谱数据片段经过前文所述的二值化、腐蚀处理后，对于每一帧二值化后的图像进行霍夫变换，检测图像中的直线结构。同时，已知在NDA观测数据的频率范围内，太阳射电Ⅲ型暴的频率漂移率约为1-10MHz/s，所以需要对检测出来的直线进行筛选，只留下频率漂移率符合IⅢ型暴的直线。

若经过筛选后，数据片段中仍存在一条或多条直线，则确定该数据片段中包含至少一个事件。

![](images/8d99ad8e7f3f203dd27c842302aba27e8807517bd41d5ba783f6181af946ee2f.jpg)  
图7霍夫变换算法识别出的爆发事件 Figure.8 Burst event identified by Hough transform algorithm

如图7所示，图中有直线特征的结构被识别出来并标红，此处很可能是一个IⅢ型暴事件。同时还可以获取线段两端的坐标值，即获取爆发事件的起始时间、起始频率、终止时间、终止频率。图8中所示事件的起始频率为50MHz，终止频率为27MHz，持续时间为15秒，频率漂移速率为-1.5MHz/s，负值表示II型暴从高频向低频漂移。

1.4NDA数据中II型暴的识别结果

使用以上识别算法可以高效地在10MHz以上的频谱数据中识别形态类似直线的II型暴事件，并获得关于其起止频率、起止时间，频率漂移率等信息。为之后对爆发事件的研究提供支持。

图8识别出的不同参数的爆发事件  
![](images/dae3463a623d0e0cb4f7af97d7de1afcdea02254e6da841da7c90b9e7f5f910c.jpg)  
Figure.8 Burst events with different parameters identified

如图8所示，图8(a)中爆发事件的起始频率为67MHz，终止频率为23MHz，持续时间为17s,频率漂移率为-2.6MHz/s。图8(b)中爆发事件的起始频率为37.3MHz，停止频率为28MHz，持续时间为6s，频率漂移率为1.55MHz/s。以上两例爆发事件的识别结果证明识别算法可以识别从各频率开始的爆发事件。

图8(c)中爆发事件的起始频率为 $5 8 \mathrm { M H z }$ ，终止频率为46MHz，持续时间为6s，频率漂移率为-2.1MHz/s。图8(d)中爆发事件的起始频率为48MHz，终止频率为26MHz，持续时间为18s，频率漂移率为-1.22MHz/s。以上两例爆发事件的识别结果证明识别算法可以识别各种长度的持续时间的爆发事件。

![](images/432bc4bfbb63fbaa5ddc2a1029d4bfae25e43e4091b569f14dcee85afc478539.jpg)  
图9识别出的低频的爆发事件 Figure.9 Burst event with low frequency identified

但由于NDA观测的频率范围有限，且在观测范围内的低频频段中存在较强的持续不断的干扰，如果爆发事件的终止频率较低，这些干扰信号可能会影响算法对爆发事件终止频率的识别。如图9所示，算法识别出的爆发事件的终止频率与干扰信号所在频率紧密结合，这样在识别爆发事件终止频率时，会有一定的误差。

# 2射电Ⅱ型暴的自动识别

从太阳射电观测数据中识别太阳射电Ⅱ型暴的方法与识别太阳射电IⅢ型暴的方法类似，需要对数据进行图2所示的处理过程。但在使用霍夫变换算法识别出频谱图中的直线结构及其起正点坐标后，需要根据ⅡI型暴的物理特征进行筛选。例如： $\mathrm { I I }$ 型暴的基波所在的起始频率通常不会很高（通常<300MHz），其频率漂移速率较为缓慢（通常<1 MHz/s）。

太阳射电ⅡI型暴的主要辐射机制为等离子体辐射，所以可以通过射电暴的信号频率直接得到射电辐射源所在区域的密度。根据等离子体辐射的特点，观测频率 $\mathbf { f _ { o b s } }$ 、等离子体辐射频率$\mathrm { f _ { p e } }$ 和电子密度 $\mathfrak { n } _ { \mathrm { e } }$ 的关系可表示为 $\mathrm { f _ { o b s } = s f _ { p e } }$ ， $\mathrm { f _ { p e } ( k H z ) } = 8 . 9 8 \sqrt { \mathrm { n _ { e } ( c m ^ { - 3 } ) } }$ 。这里s代表谐波数，$s = 1$ 时代表基频结构（Fundamental）， $s = 2$ 代表是二次谐频结构（Harmonic）。在此基础之上，还可以根据日冕密度模型计算射电辐射源所在的日冕高度或位置，并进一步估算出CME[10]的速度。在日冕高度的计算中我们经常采用的模型之一是Newkirk(1961)模型

$$
N _ { e } = N _ { 0 } \times 1 0 ^ { 4 . 3 2 R s / R }
$$

其中, $N _ { 0 } = 4 . 2 \times 1 0 ^ { 4 } \mathrm { c m } ^ { - 3 }$ ·， $R s$ 是太阳半径。

基于以上自动提取算法和日冕密度模型(公式3)，我们对于云南天文台米波太阳射电频谱仪 2012年11月13日的观测数据进行处理，识别其中的Ⅱ型暴，并提取起止频率、起止时间、频率漂移率等参数，并计算所对应的CME的特征参数(如图10)。

CME特征参数提取  
识别目标：Ⅱ型射电暴（H）\*  
开始时间：02:02:20UT  
结束时间：02:05:44UT  
开始频率： $3 8 8 \mathrm { M H z }$   
结束频率： $1 5 8 \mathrm { M H z }$   
频率漂移率： -0.56MHz/s\*\*  
CME激波速度： $8 7 0 \mathrm { k m / s }$   
注：\*中的H（Harmonic）代表II型射  
电暴的二次谐波结构  
\*\*中的负号代表ⅡI型射电暴的频率漂  
移是从高频到低频

![](images/5f9578418d69d106a32906c40b2c0b02cdd2c2ac05b331b68f302caf3f584385.jpg)  
图10利用观测数据提取CME特征参数  
Figure.10 Extracting CME feature parameters from observation data

通过概率霍夫变换算法别出该ⅡI型射电暴的物理参数，并得出对应的CME在02:02:20 UT-02:05:44UT时刻的速度为 $8 7 0 \mathrm { k m / s }$ ，而后，LASCOC2日冕仪在02:24:06UT发现该CME，并获得该CME的速度为851km/s（数据来源：

https://cdaw.gsfc.nasa.gov/CME_list/UNIVERSAL/2012_11/univ2012_11.html），通过对比发现，这两种方法所给出的CME速度非常接近，因此，我们认为利用概率霍夫变换算法所自动识别出的参数是合理可信的。

# 3总结与展望

本文提出了一种基于概率霍夫变换算法的太阳射电IⅢ型和Ⅱ型暴识别算法。首先通过一系列的算法对太阳频谱图像进行预处理：多次实验测试选择合适的时间长度对原始观测数据进行合理切分；对各通道进行均值消去，消除通道不均匀性的干扰；对图像进行二值化，提取前景信息；对图像进行腐蚀，消除一些窄带的射频干扰信号。然后使用概率霍夫变换算法寻找频谱图像中的直线结构，获取II和Ⅱ型暴事件的起止时间、起止频率和频率漂移率等信息，并根据这些信息进一步筛选频率漂移率符合ⅢI型和ⅡI型暴特征的直线结构。

本文还利用该方法从云南天文台2012年11月13日Ⅱ型暴的观测数据中自动提取了ⅡI型暴的物理参数，并结合相应的日冕密度模型获得CME的特征参数。这些参数对空间天气的预报预警具有实用价值。该方法虽然可以识别典型的Ⅱ型暴，但由于Ⅱ型暴容易与其他类型射电暴同时发生，信号有混叠，未来我们将在更多的Ⅱ型暴数据上对该算法进行检验和改进，以达到更好的、对多种数据来源普遍适用的识别效果。

实验结果表明，该方法能有效地识别太阳射电IⅢ型暴与Ⅱ型暴，并获取射电暴的起止频率、起止时间和频率漂移率等信息，并能快速地对长期、大量的观测数据进行识别和分析。

同时，概率霍夫变换算法比标准霍夫变换算法的计算量更小，计算过程更短，更适合在观测过程中实时识别太阳射电III型和ⅡI型暴，提取观测参数得出CME激波速度等关键物理信息，实现空间天气预报预警，维护相关人员、设备的安全。

Automatic ldentification and Parameter Extraction of Solar Type III and II Radio Burst Based on

# Probabilistic Hough Transform

Shen Faxinl.2, Gao Guannan1,³， Wang Min1,3

(1.Yunnan Observatories,Chinese Academy of Sciences，Kunming 65oo11，China; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China 3.Key Laboratory of the Structure and Evolution of Celestial Objects，CAS，Kunming 65O216，China)

Abstract:Nonthermal energetic particle flow and shock wave generated during flares and coronal mass ejection are the two main factors that produce disastrous space weather events. Their main observational characteristics are type III radio burst with fast frequency drift feature and type I radio burst with relatively slow frequency drift feature.

This paper mainly introduces the method of using the probabilistic Hough transform to automatically identify the type II and type_II solar radio burst in the observation data,and to extract the characteristic parameters of the type III and type II radio burst, finally te velocity of the CME shock wave is estimated by using the physical parameters of the identified radio type II bursts.

Key words:solar burst; solar radio burst; probabilistic Hough transform; auto recognition

参考文献：   
[1]高冠男,林隽,汪敏,谢瑞祥.太阳米波和分米波Ⅱ型、Ⅲ型射电暴及其精细结构观测研究进展[J].天文学进展,2012,30(01):35- 47.GA0 G N,LIN J， WANG M,XIER X. Research and observation of metric and decimetric type IIand type II solar radio bursts with fine structures[J].Progress in Astronomy,2012,30(01) :35-47.   
[2]陈昌硕．高分辨率太阳射电接收数据处理与存储方法研究与实现[D].山东大学,2019.CHEN C S．Research and   
implementation of high-resolution solar radio reception data processing and storage methods[D]. Shandong University,2019.   
[3]张沛锦．太阳射电暴源的观测和辐射传播模拟[D].中国科学技术大学,2021.D0I:10.27517/d.cnki.gzkju.2021.00200. ZHANG P J. Observation and radiation propagation simulationof solar radio burst sources[D]. University of Science and Technology of China，2021．DOI:10.27517/d.cnki.gzkju.2021.000200.   
[4]谭宝林，谭程明，黄静，等．空间甚低频太阳射电I型爆研究进展[J]．深空探测学报（中英文），2021,8（1）：92-99.TAN BL,TANCM,HUANG J，etal.Research advancesof type IIsolar radio burstsat space verylow frequencies[J]. Journal of Deep Space Exploration，2021，8（1）：92-99.   
[5] REIDHA S，KONTAR E P. Stopping frequency of type III solar radio bursts in expanding magnetic flux tubes[J]. Astronomy& Astrophysics，2015，577：A124.   
[6]Otsu,N.，1979.A threshold selection method from gray-level histograms.IEEE transactions onsystems，man, and cybernetics，9(1)，pp.62-66.   
[7] Jui-Cheng Yen，Fu-Juay Chang and Shyang Chang， $^ { \prime \prime } \mathrm { A }$ new criterion for automatic multilevel thresholding,"in IEE Transactions on Image Processing，vol.4，no.3，pp.370-378，March 1995，doi: 10.1109/83.366472.   
[8]邱东,翁蒙,杨宏韬.基于改进概率霍夫变换的车道线快速检测方法[J].计算机技术与发展,2020,30(05):43-48.QIU D，WENG M, YANG HT.Fast lane detection method based onimproved probabilistic Hough transform[J]．Computer Technology and Development,2020,30(05) :43-48.   
[9] Straight line Hough transform — skimage v0.19.0.dev0 doc.htps://scikit  
image.org/docs/dev/auto_examples/edges/plot_line_hough_transform. html.   
[10] Newkirk Gordon，Jr..The Solar Corona in Active Regions and the Thermal Origin of the Slowly Varying Component of Solar Radio Radiation.[J].The Astrophysical Journal,1961,133.   
[11]冯士伟,吕茂水.太阳ⅡI型射电暴精细结构的观测研究[J].天文学进展,2021,39(02):129-143.FENG S W，LV M S. Observational study on the fine structures of type II solar radio bursts[J]. Progress in   
Astronomy,2021,39(02) :129-143.   
[12]李国良,袁国武,高冠男.太阳射电ⅡI型爆发中频率分裂现象的特征自动提取研究[J].电子测试,2021(05):49-   
51.D0I:10.16520/j.cnki.100-8519.2021.05.017.LIGL，YUANGW，GAOGN.Research on automatic featureextraction of frequency splitting phenomenon in type II solar radio bursts[J]．Electronic Test,2021(05):49-51.   
DOI:10.16520/j.cnki.1000-8519.2021.05.017.   
[13]滕今朝,邱杰.利用Hough变换实现直线的快速精确检测[J].中国图象图形学报,208(02):234-237.TENG JZ，QIU J.Fast and precise detectionof straight line with Hough transform[J].Journal of Image and Graphics,2008(02):234-237. [14］高冠男,汪敏,董亮,郭少杰.空间甚低频太阳ⅡI型射电暴研究进展[J].深空探测学报(中英文),2021,8(04):423-   
432.D01:10.15982/j.issn.2096-9287.2020.2019022001.GAOGN，WANGM，DONGL，GUOSJ.AdvancesinspaceVLFtypeII solar radio bursts[J]．Journal of Deep Space Exploration,2021,8(04):423-432.D0I:10.15982/j.issn.2096-   
9287. 2020.20190222001.

[15]冯士伟,赵飞.II型太阳射电爆发精细结构的观测研究[J].中国科学:技术科学,2021,51(01):35-45.FENG S W，ZHAO F. Observational study on the fine structures of type II solar radio bursts[J]．SCIENTIA SINICA Technologica, 2021,51(01) :35-45. [16］钟晓春.太阳射电爆发纤维精细结构的观测与理论研究[D].西南交通大学,2003.ZHONG XC.Observation and theoretical study on the fine structures of solar radio burst fibers[D]． Southwest Jiaotong University,2003. [17]张韬,苏彦.嫦娥四号低频射电频谱仪降低背景噪声方法的研究[J].天文研究与技术,2019,v.16;No.63(03):312- 320.D0I:10.14005/j.cnki.issn1672-7673.2018119.02.ZHANG T，SUY.Researchon themethodofreducingbackground noise with the Chang' $\mathrm { e ^ { - 4 } }$ low-frequency radio spectrometer[D].Astronomical Research & Technology,2019,v.16;No.63(03):312-320.D0I:10.14005/j.cnki.issn1672-7673.20181119.002. [18」耿立红,谭程明,敦金平,章宏,贾彦辉，颜毅华,陈志军,马素丽,刘东浩,杜静,苏仓.三频段太阳射电望远镜与空间天气[J].天文 研究与技术,2018,v.15;No.60(04):380-389.D0I:10.14005/j.cnki.issn1672-7673.20180426.020GENGLH，TANCM,DUNJP, ZHANG H,JIAYH,YANYH,CHEN ZJ，MASL，LIUDH,DUJ，SUC.Tri-band solar radio telescopes and space weather[J]．Astronomical Research& Technology,2018,v.15;No.60(04):380-389.D0I:10.14005/j.cnki.issn1672- 7673.20180426. 020.

收稿日期：2022-xX-xX； 修订日期：2022-xx-xx

\*基金项目：国家自然科学基金(11941003,U203113,U1831201），云南省应用基础研究计划面上项目（2019FB009）项目，2021昆明市对外科技合作基地项目：“中国科学院云南天文台-马来亚大学先进射电天文技术联合研发合作基地支持”作者简介：沈发新(1996-)，男，湖北黄石人，硕士研究生，主要从事太阳射电暴识别方面的研究工作。