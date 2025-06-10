# 一种对光照鲁棒的道路边缘检测算法

马玛双，杨小冈，李维鹏(火箭军工程大学，西安710025)

摘要：针对在光照变化和强阴影干扰条件下的道路边缘检测问题，提出了一种对光照鲁棒的道路边缘检测算法。该算法结合导向滤波和抗阴影特征提取器,首先，采用导向滤波对图像的边缘进行增强，减少背景噪声干扰；其次，利用抗阴影道路特征提取器提取道路粗边缘轮廓；最后，采用模糊联通性分析，结合道路边缘全局信息将道路边缘分为远、近两部分，对提取的边缘点进行修正，并采用RANSAC进行拟合。实验部分采用ROMA数据集对算法进行验证，实验结果表明，提出的边缘检测算法的综合性能指标为 $8 3 . 6 7 \%$ ，在各种道路条件下，具有较好的鲁棒性和准确性。

关键词：道路检测；导向滤波；模糊连通性；驾驶辅助系统中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.10.0848

Illumination-robust method for road detection

Ma Mashuang, Yang Xiaogang, Li Weipeng (RocketForce University of Engineering,Xi’an 710025,China)

Abstract:For solving the problem ofroad detection under thecondition of light change and strong shadow,this paper proposedan ilumination-robust roaddetection method.Firstly,in order toreduce the background noise interference,this paperused guided fitering toenhance the boundaryof image.Secondly,this method introduced anillumination-robust to extractthe outlineof therough boundaryof theroad.Finally,the model divided theroad into two parts to modify the boundary pointsof the extraction,and adopted fuzzyconnectivity analysis to select boundary,fiting with RANSAC in combing withtheglobal informationof theroad.The experimentalresultsshowthatthecomprehensive performance index of the proposed algorithm checked by ROMA dataset is $8 3 . 6 7 \%$ .The proposed method achieves good robustness and accuracy in different road scenarios.

Key words: road detection; guided filtering; fuzzy connectivity; driving auxiliary system

# 0 引言

近年来，随着车辆的增多，交通事故的频率正逐年上升。据有关调查，大部分交通事故的原因是驾驶人员的疲劳驾驶和驾驶环境的恶劣。因此，为提升驾驶人员的人身安全，驾驶辅助系统，比如，偏离车道警告，车道保持助手，障碍物检测，车辆碰撞警告和车辆自动导航等，成为了当前研究的重点领域之一。

道路检测是各种驾驶辅助系统的基础。其主要的任务是：根据安装在车辆上摄像头采集的图像，将道路从背景中分离出来，为驾驶辅助系统提供相应的位置，车道边缘、标志物和道路方向等信息。目前，道路检测的方法大致可以分为两种[1\~3]：基于特征的方法和基于模型的方法。基于特征的方法，通常用来提取道路的低维特征信息，包括梯度、颜色、亮度和结构信息等。其对于道路的形状具有良好的鲁棒性，但是易受光照、阴影和遮挡的影响，道路检测效果不佳。文献[4]提出基于视觉特征的道路感兴趣区域选取，并利用消失点和线段的位置来检测道路区域。文献[5,6]通过构造对光照具有鲁棒特性的特征提取器，实现道路边缘的检测。文献[7]提出了基于光照不变的PCA空间变换，用于降低空间中的光照和阴影干扰，在全局空间对光照的影响进行削弱。文献[8]基于光照不变理论，利用Chebyshev理论得到与光照无关的图像，通过建立置信度将道路从背景中分离出来。基于模型的方法，主要是根据先验知识，对道路的模型进行假设，包括直线模型、双曲线模型和抛物线模型等。由于采用固定的模型，该方法仅需对有限的参数进行拟合，能够有效的处理阴影和遮挡等问题。然而在现实各种复杂的道路条件下，没有任何一种道路模型能够普遍适用，缺乏相应的灵活性。文献[9]提出一种基于结构化学习的方法，有效利用图像上下文信息和标签的结构信息，实现道路标志物检测。文献[10]融合纹理和形状特征，采用基于最大稳定极值区域检测器和Adaboost训练方法，实现标志物检测。文献[11]将道路分为近场和远场区域，采用改进的河流流量法和RANSAC拟合法，对道路的标志进行拟合，在有车辆遮挡的状况下有较好的检测效果。

为了提升算法的通用性，本文采用了特征和模型相结合的方法。一方面，利用导向滤波对图像的边缘进行增强，降低噪声的干扰，解决了平滑滤波对道路线特征干扰的问题，并通过分析道路与周边环境的特征，采用抗阴影的灰度化算法降低阴影对道路检测的干扰，快速提取道路的轮廓；另一方面，将道路分为远、近两个视场区域，近场区域，通过模糊联通性分析进行自适应道路分割点的选取，利用RANSAC进行直线部分拟合；远场区域，为避免道路模型拟合的复杂性，采用领域增长法进行道路边缘点的选取，提取道路边缘。

# 1 相关算法

# 1.1导向滤波

为降低图像中噪声的影响，一般采取滤波的方式进行预处理。目前，常用的低通滤波器有简单平滑或者高斯平滑等。从原理上看，该滤波方式属于各向同性滤波器。显而易见，由于噪声点四周的梯度相近，而道路边缘沿法线方向差别最大，切线方向差别小，各向同性滤波器在滤除噪声等不利因素的同时，也将图像边缘、纹理和梯度特征加权处理，使原始特征受到影响。因此，研究人员已经提出了许多边缘保持的图像平滑算法，比如双边滤波、自适应平滑滤波、基于PM方程的各向异性滤波和导向滤波等。

导向滤波是2013年由何凯明等人[12]提出的。其原理是采用引导图I对原始图像 $\mathfrak { p }$ 进行滤波，得到滤除噪声，保留边缘的图像 $\mathsf { q }$ 。滤波器的公式为

$$
q _ { i } = \sum _ { j \in w _ { i } } W _ { i j } ( I ) \cdot p _ { j }
$$

其中： ${ \boldsymbol { p } } _ { j }$ 是图像中某点的像素值， $W _ { i j } ( I )$ 是引导图I确定的相应的点权值， $q _ { i }$ 是相应点经过加权滤波后的值。

![](images/5141cd602318f43a8fa15ac67f2be0089f6ee2539d149095b580b1efbc50419e.jpg)  
图1导向滤波  
Fig.1Guided filtering

导向滤波的滤波示意图如图1所示。在整个滤波的过程中，导向滤波依赖于一个重要假设：导引图像与原始图像之间存在线性关系，即导向滤波器在导引图像I和滤波输出q之间在一个二维窗口中是一个局部线性模型，a和b是当前窗口中心位于 $\mathbf { k }$ 是线性函数的系数，可以表述为$q _ { i } = a _ { k } I _ { i } + b _ { i } , \forall i \in w _ { k }$ 。通过导引图像提供的信息，指定边缘区域和非边缘区域，当导引图为边缘区域，则保留边缘信息；当导引图为非边缘区域，则通过各向同性平滑滤波去除噪声的影响。

根据无约束图像的复原方法，假设噪声为 $\mathfrak { n }$ ，则 $q _ { i } = p _ { i } - n _ { i }$ 。通过求解噪声 $\mathfrak { n }$ 的最优化目标函数 $\operatorname* { m i n } \| n \|$ ，并适当引入惩罚项，可以求解线性参数a和 $\boldsymbol { \mathbf { b } }$ 。

目标函数为

$$
\arg \operatorname* { m i n } _ { i \in w _ { k } } \sum _ { i \in w _ { k } } \Bigl [ \left( a _ { k } I _ { i } + b _ { k } - { p _ { i } } \right) ^ { 2 } + \tau { a _ { k } } ^ { 2 } \Bigr ]
$$

求解最优化得到

$$
a _ { k } = \frac { \displaystyle \frac { 1 } { | w | } \sum _ { i \in w _ { k } } I _ { i } p _ { i } - \mu \overline { { p } } _ { k } } { \sigma _ { k } ^ { 2 } + \tau }
$$

$$
b _ { k } = \overline { { p } } _ { k } - a _ { k } \mu _ { k }
$$

其中： $u _ { k }$ 是I中窗口 $w _ { k }$ 中的平均值， $a _ { k } ^ { 2 }$ 是I中窗口 $w _ { k }$ 中像素的个数， $\overline { { p } } _ { k }$ 是原始图像 $\mathfrak { p }$ 在窗口 $w _ { k }$ 中的均值。

由于获取导向图I较为困难，当导引图和原图相同，即$\scriptstyle \mathbf { I = p }$ 。那么，导向滤波退化为边缘保持滤波，求解的上式可以变为

$$
a _ { k } = \frac { a _ { k } ^ { 2 } } { a _ { k } ^ { 2 } + \tau }
$$

$$
b _ { k } = ( 1 - a _ { k } ) \mu _ { k }
$$

因此可能出现两种情况：当为高方差区域， $a _ { k } ^ { 2 } > > \tau$ ，于是 $a _ { k } \approx 1$ ， $b _ { k } \approx 0$ ，则保持图像边缘区域原值不变；当为平滑区域时， $a _ { k } ^ { 2 } < < \tau$ ，于是 $a _ { k } \approx 0$ ， $b _ { k } \approx 1$ ，则使用邻近像素均值，降低噪声的干扰。

# 1.2模糊连通性

模糊连通性，被广泛地应用于图像分割中。在图像中的相邻元素中，模糊连通性是通过对坐标空间距离、梯度和强度信息，进行相似性度量，赋予特征相应的权值，给出图像最佳分割点。

首先，本文定义图像模糊数字空间 $( Z ^ { n } , \alpha )$ ，其中 $Z ^ { n }$ 为空间维度，由于图像为二维空间，此处 $\mathfrak { n }$ 取2， $\alpha$ 为相邻元素的邻接度。假设 $L = ( C , f )$ 是模糊数字空间 $( Z ^ { 2 } , \alpha )$ 的子集，即从空间 $c$ 到映射函数 $f$ ， $C \subseteq Z ^ { 2 }$ ， $f$ 是度量相似邻接度函数，范围是[0.1]。可以表示为

$$
\boldsymbol { u } _ { k } ( \boldsymbol { c } , d ) = g ( u _ { a } ( \boldsymbol { c } , d ) , u _ { \varphi } ( \boldsymbol { c } , d ) , u _ { \varphi } ( \boldsymbol { c } , d ) , \boldsymbol { c } , d )
$$

其中： $\mathbf { g }$ 是范围在[0,1]的度量函数， $u _ { a } ( c , d )$ 度量邻近元素的坐标空间邻接度， $u _ { \varphi } ( c , d )$ 度量邻近元素的强度， $u _ { \phi } ( c , d )$ 感兴趣区域的强度邻接度。

在图像的候选序列点中，候选点构成边缘路径$P _ { c d } { = } ( c { = } c _ { 1 } , c _ { 2 } { , } { \cdots } , c _ { m } , d )$ ，其中 $\mathrm { ~ m ~ }$ 是路径的长度。对于每一段$( c _ { i } , c _ { i + 1 } )$ ，通过最小化连接度函数，提升每一段道路 $\rho _ { c d }$ 的连接准确性，可以表述为

$$
u _ { x } ( \rho _ { c d } ) = \operatorname* { m i n } ( u _ { k } ( c , c _ { 2 } ) , \cdots , u _ { k } ( c _ { m - 1 } , d ) )
$$

最后通过由每一段的最小化连接度函数，构成整条道路边缘的最强连接函数。可表述为

$$
P _ { c d } : u _ { \xi } ( \rho _ { c d } ) = \operatorname* { m a x } ( \rho _ { c d } ) , \rho _ { c d } \in P _ { c d }
$$

在此，采用图像中的梯度和边缘强度信息作为道路边缘的重要特征，综合权重对边缘点进行选取和修正。

强度相似性度量。通常采用高斯函数 $g _ { 1 } ( t )$ ，根据道路边缘点强度信息，测量灰度图像之间的相似性 $u _ { 1 } ( c , d )$ ，可以表述为

$$
u _ { 1 } ( c , d ) { = } g _ { 1 } ( t ) * S _ { 1 } ( f ( c ) , f ( d ) )
$$

其中： $g _ { 1 } ( t )$ 为高斯核函数，其均值和方差是作用在候选点的均值和方差， $S _ { 1 } ( f ( c ) , f ( d ) )$ 为道路边缘两点的强度信息。

梯度相似性度量。采用高斯函数 $g _ { 2 } ( t )$ ，根据道路边缘梯度信息，用于测量道路边缘的相似性 $u _ { 2 } ( c , d )$ ，可以表述为

$$
u _ { 2 } ( c , d ) { = } g _ { 2 } ( t ) * S _ { 2 } ( f ( c ) , f ( d ) )
$$

其中： $g _ { 2 }$ 为高斯核函数，其均值和方差是作用在候选点的均值和方差， $S _ { 1 } ( f ( c ) , f ( d ) )$ 为道路上边缘相邻两点的强度信息。

因此，将两种相似性度量结合，加权表示道路边缘相似程度，可以表述为

$$
u ( c , d ) = w _ { 1 } u _ { 1 } ( c , d ) + w _ { 1 } u _ { 2 } ( c , d )
$$

其中： $w _ { 1 }$ 为强度的权值， $w _ { 2 }$ 为梯度的权值，并且 $w _ { 1 } + w _ { 1 } { = } 1$ ，在此，假设强度和梯度的对边缘的重要性一样，那么 $w _ { 1 } = w _ { 1 } = 0 . 5$ 0

# 2 基于模糊连通性分析的道路边缘检测算法

一般地，道路边缘检测框架[13]可以分为图像预处理、鲁特征提取、道路边缘检测、模型拟合等步骤。本文提出的道路边缘检测算法的流程如图2所示。

# 2.1对光照鲁棒特征提取

# 2.1.1导向滤波

在图像滤波的过程中，导向滤波需要引导图I，在实际的情况下，边缘梯度信息未知，条件难以满足。因此，采用式（5）（6）对图像进行滤波，保留图像的边缘特征，滤除图像中非边缘区域的杂波干扰。滤波效果如图3所示。

![](images/c5eeb6c52e2e835eab15e2679a0e9a0aafec182b4d6718e0a766c5956fe0750e.jpg)  
图2道路检测流程

![](images/94cab0c4d70c7f387b848577e7fe97e785fb8e5046435779a61d7a9e8d807616.jpg)  
Fig.2Processing flow of the road detection   
Fig.3Image filtering

# 2.1.2感兴趣区域选取

通过安装在车辆前方的摄像头采集图像信息，对道路的区域进行分析。采集的图像大小为 $r \times c$ 。从图像的信息来看，道路信息在图像的水平线以下，水平线以上为天空部分。本文依靠经验选取图像的下 $2 / 3$ 作为感兴趣区域。之后，根据检测到的消失点，自适应地裁剪感兴趣区域，使得能够在有效提取道路信息的同时减少冗余信息、降低计算的负担。

# 2.1.3鲁棒特征提取

特征提取是基于特征检测方法的核心因素。目前，大部分提取的道路特征都是基于亮度特征，鉴于此，阴影对于道路特征的影响是不容忽视的。并且，原始图像的R、G、B三通道特征信息高度相关，同时处理三通道中的特征信息会存在大量的信息冗余、占用系统资源。为克服这个缺陷，研究人员进行了多种颜色空间的变换，试图降低或者消除阴影对道路亮度特征的影响。

从阴影的影响效果来分，特征提取可以分为光照鲁棒特征提取器和无阴影特征提取器。在光照鲁棒特征提取器中，主要是为了降低阴影对于图像特征的干扰程度，因此，常常将颜色空间中的亮度通道信息单独分离出来，比如HSI空间中的 $H$ 通，和YUV通道中的 $Y$ 通道等。以HSI空间为例，单独采用 $H$ 通道适用于提取道路特征， $s$ 通道适用于提取道路边缘植被信息，但是单通道信息对于阴影鲁棒性较差，难以在复杂的道路条件中。因此，可以综合几个通道中的信息，采用 HSV空间中的 $s$ 分量用于描述道路信息，比如文献[14]提出的变换，在强阴影的场景中，阴影对道路的阴影较小。可以描述为

$$
S ^ { \prime } { = } \frac { \operatorname* { m a x } ( R , G , B ) - B } { \operatorname* { m a x } ( R , G , B ) }
$$

其中：R、 $G$ 、 $B$ 分别代表RGB颜色空间中的红、绿、蓝三通道， $s ^ { \prime }$ 是图像饱和度的一种描述。

在无阴影特征提取器中，主要是为了完全去除阴影的影响，实现道路特征的选取。常用的方法有LCS空间变换及其推广。由于不同的颜色在LCS空间中是平行的直线，可以将道路与周边植被完全分离，实现无阴影的特征提取。可以描述为

$$
\begin{array} { r } { L _ { \theta } = \sin \theta \cdot \log ( R / G ) + \cos \theta \cdot \log ( B / G ) } \end{array}
$$

其中： $\theta$ 是依赖于相机的参数， $R$ 、 $G$ ， $B$ 分别为RGB空间中的红、绿、蓝三通道。

从算法性能、检测效果和计算性能上看，无阴影特征提取器的效果好于光照鲁棒性性提取器，但是其计算的复杂度明显更高，且需要知道相机参数，对于外部环境的依赖较大。

图像灰度化。本文采用的是式(13)所示的灰度化的方法，相较于其他灰度化的方法，在强阴影的状况下能够有较好的显示效果，如图4所示。

![](images/5d48a67a4bc45334e95650e4a40430beb2e0c19227f36e02567b9d313740c77e.jpg)  
图3图像滤波  
图4灰度化对比   
Fig.4Comparison of grayscale method

# 2.2 模糊连通性分析

模糊连通性分析包含两步：a)通过图像分割、边缘点检测和Hough变换，为后续模糊连通性分析提供初始搜索方向；b)在提供的搜索方向的基础上，采用模糊连通性分析分别对直线边缘点进行修正和曲线边缘点选取。

# 2.2.1图像分割

在图像预处理的过程中，获取到了对光照具有鲁棒性的灰度化图像，阴影的影响已经被大幅的削弱。因此，可以通过固定阈值对道路边缘进行提取。在此，采用了常用的大津法[15]进行二值化，通过最小化类内方差和最大化类间方差进行阈值处理，将道路与背景分离。

如图5所示，从道路分割结果可以看到，依然会存在道路标志物、土壤、车辆等因素的干扰。结合具有启发性的信息，道路前方的一定区域内是路面这一条件，可以进一步去除车辆前方行驶区域的无关因素。此处，考虑单行道的车道宽度为w和图像的透视影响，以图像的 $c / 4$ 处起始点为中心，宽度为w，构建等腰梯形，将该梯形区域的二值图像设置为0，减少标志物和其他无关因素的干扰。在图中可以看到，道路区域的干扰明显减少。

# 2.2.2边缘候选点提取

从图像分割的结果中可以将道路与非道路区域分割开来。图像中间主要是道路区域，两边为草丛。在此基础上将图像中道路边界提取出来即可对边缘进行明显的标注，为后续初始方向的确定提供参考点。

受“从中间到两边”搜索策略的启发，本文采用了“两步法”搜索策略进行道路边缘点的提取。具体的实施方法是将分割的图像从中间分为左、右两个部分，分别对道路的左、右边缘进行提取。首先，针对分割后的图像，采用从下到上的搜索策略，可以提取出候选边缘点的行坐标；其次，对左半部分图像，采用从中间到左边的搜索策略，当首次遇到值为1的点，即看做左边缘候选点；最后，同样的方法用于道路右边缘点的提取。结果如图6所示。

![](images/532d925d76327ee4713f943c1fa430d91164123ac9bfc3fea5d230ca65fceca3.jpg)  
图5图像分割

![](images/137e4ec4f1cf6baeb1a54d7b41298bbba1ad101351d66dad967089025d7521ea.jpg)  
Fig.5Image segmentation   
图6边缘候选点  
Fig.6Candidate edge points

2.2.3确定搜索方向

在寻找到粗边缘点的基础上，通过直线拟合确定道路边缘点的搜索方向。在图像近场的区域，道路边缘完全可以看成直线;并且直线模型相较于曲线模型的拟合参数计算少，能极大降低计算量。另一方面，通过阈值分割的二值图像寻找到的边缘点误差较大，并不适合用于曲线拟合，因此本文采用直线模型先进行拟合来确定模糊连通性分析的初始搜索方向

对于直线的拟合，采用霍夫变换将直角坐标系转换到极坐标中，通过确认曲线交点进行直线的选取。为了加快霍夫直线检测的速度，结合图像是由安装在车辆前方摄像头采集的先验知识可知，道路边缘的角度范围设置为 $4 5 ^ { \circ } \sim 7 5 ^ { \circ }$ 和$- 4 5 ^ { \circ } \sim - 7 5 ^ { \circ }$ 。检测结果如图7所示。

# 2.2.4模糊连通性分析道路边缘

在Hough空间变换提供初始搜索方向的基础上，自底向上，将图像分为直线和曲线两个部分，对道路边缘点进行模糊连通性分析。

# 1)直线部分

采用直线模型。如图8所示，根据霍夫变换拟合的直线，沿Hough拟合的直线方向等距采集候选点，对候选点邻域内进行模糊连通性分析。由于道路边缘点是在候选点的邻域内，并且考虑到道路标志物的正常间隔为w，搜索的邻域大小设定为2w。设定最佳分割目标函数，寻找最优解：

$$
\arg \operatorname* { m a x } _ { x \in I _ { 1 } , l _ { 2 } } f ( y ) = \left| \sum _ { j \in [ i - w , y ] } u _ { x } ( j ) - \sum _ { k \in [ y , i + w ] } u _ { x } ( k ) \right|
$$

其中：x表示霍夫变换拟合直线上等距选取的候选点，y表示求解邻域内的最佳分割点。

![](images/7630087203689759a3571c3e576f3a99e3414cbf5af2a735f1f03c3bfd78a249.jpg)

![](images/fcdf3986bbb80600242a4d4b187120d9a0b895fe1a31e13a65b83763a223e438.jpg)

![](images/d7725b87798fa8209406e35c37ab1ac2c970e4cab0838d5ffffafa33ae54505e.jpg)  
图8直线边缘点分析  
Fig.8Boundary analysis of line

通过对候选边缘点函数的优化求解实现最优分割点的选取,即在有限的邻域范围内，实现对原有道路边缘点的快速修正。

# 2)曲线部分

曲线部分采用邻域增长法进行分析。传统的曲线模型拟合需要事先假定道路的几何模型，并且需要对参数进行估计，过于复杂。为避免参数的计算，本文采用领域增长法对曲线边缘点进行分析和提取，通过邻域增长算法对边缘点的目标函数优化实现最佳分割点的选取。

起点的选取。曲线与直线模型连接点的选取是为了避免直线与曲线中间出现断裂。本文将曲线的起始点设置为检测到的直线上符合要求的第一个点，终点设置为图像道路边缘端点。

![](images/c322781afdca3622ee74bdaff9b14d72604001b2e8c313ba2b83fb0783ab2119.jpg)  
Fig.7Determine search directions   
图9曲线边缘点分析Fig.9Boundary analysis of curve

如图9所示，在进行邻域增长法时，通过自底向上的邻域寻找进行相邻像素点之间的模糊连通性分析，每次更新后即以该修正点为中心，沿梯度方向，选取下一候选点，分析其邻域内的最佳非分割点，达到曲线边缘点的选取。由于图像的透视影响，在远处的图像会出现相交或者小于一定的距离。针对这一现象，当左右边搜寻到的最佳边缘点小于一定的距离时，即停止曲线边缘的增长。

# 2.3模型拟合

在模糊连通性分析阶段，本文对道路的边缘点进行了分段处理。相应地，在拟合的过程中，为了避免模型单一带来表达能力不足的问题，影响道路边缘检测结果，本文采用的道路模型拟合依然按照直线部分和曲线部分两个部分。

直线部分，根据修正后的道路边缘点集，采用RANSAC进行拟合。能够有效地清除野值干扰，保证在最优化的条件下进行直线拟合。如图10（a）所示。

![](images/0cb55e0540c073a8f9e8edd3e4ebe8a8dce30d34bc6df5761726fe249cdf8f73.jpg)  
图10 模型拟合

曲线部分，根据等距采集的曲线边缘点，从直线部分端点开始向消失点进行候选点的分析。在此过程中，加入直线的约束，当曲线的候选点在直线延伸的最大约束范围内，分析结果合理，作为候选点；否则，作为误差项舍弃，直至达到消失点时停止。如图10（b）所示。

# 3 实验结果分析

本文算法的性能测试是在ROMA数据集[I6]和KITTI数据集[7]上进行的。在ROMA和KITTI数据集中包含了结构化道路和非结构化道路边缘，并且有许多富有挑战性的场景，如建筑物、车辆和树木的阴影干扰等。实验结果是在MATLAB2014a上进行仿真和测试的。图像的大小归一化为$4 8 0 \times 6 4 0$ 的图像。

如图11所示，基于模糊连通性分析的方法可以有效地将道路直线部分和曲线部分的边缘提取出来。图11（a）（b)在有强阴影干扰的条件下也能够提取出道路边缘，并且检测出车道线标志，说明了算法具有较强的抗阴影的特征提取能力；图11（c） $\sim$ （f）则是在不同道路、不同时间、不同光照等条件下的道路边缘检测结果，本文的算法都能正确检测出道路边缘和车道线，验证了算法具有较好的鲁棒性。

在一些条件下，由于道路标志的类型、车辆遮挡和阴影等干扰，存在错误识别的结果。图12中，（a）由于道路中间的标志物较少，同时存在车辆的干扰，造成了标志物的错误检测；(b)由于强阴影和车道线具有相似的边缘和强度信息，并且在某些情况下，强阴影的边缘特征要强于标志物边缘，因此，造成了错误检测；（c）（d）由于道路中的标志物过多，造成标志物提取出现困难。

![](images/6116ab0340cd23262e8af302e03f276343668560075363217ddfefdda583c038.jpg)  
Fig.10Model fitting   
图11正确检测结果

![](images/1117ba854d86a91ce90ac1b516450e80994804468975f8e2398b1c0c31b0e2e7.jpg)  
Fig.11Test and for correct results   
图12错误结果 Fig.12False results

为定量分析实验算法，现手工对ROMA数据集中的116张道路区域进行标注，对道路边缘检测结果性能指标进行统计分析。实验结果如图13所示，正确检测的道路区域面积为（TP)，虚检的道路区域面积（FP)，漏检的道路区域面积(FN)，通过统计算法平均的准确率（P）、召回率（R）和F测量（F）三个指标进行综合评价。

$$
P = { \frac { T P } { T P + F P } }
$$

$$
R = { \frac { T P } { T P + F N } }
$$

$$
F = ( 1 + \beta ^ { 2 } ) \frac { P R } { P + R }
$$

其中：准确率 $P$ 评价算法的虚检率，召回率 $R$ 用于评价算法的漏检率， $F$ 测量反映算法的综合性能， $\beta$ 作为调和精确率和召回率的参数，此处取1。

在表1中，给出了本文算法和文献[2]算法的统计结果，本文的 $F$ 测量比文献[2]提高了 $3 . 8 6 \%$ ，可以看出本文算法具有较好的综合性能。

图14为本文算法和文献[2]算法进行道路检测的对比实验结果。图中，（a）为原始图，（b）为文献[2]的方法，(c)为本文方法。从实验的对比效果来看，文献[2]基于直线道路模型的假设，能够较好地检测直线道路边缘，但是在道路标志物提取中易受外界的干扰，出现了错误的检测结果。因此，从综合性能来看，本文的方法具有较好的检测效果。

0.8 YA Pwwww   
0.7 0.7 0.7   
0.6 0.6 0.6   
美 品 0 0.4   
0.3 0.3 0.3   
0.2 0.2 0.2   
0.1 文法 0.1 文法 0.1 文法   
品 20 40 图像数（张） 80 100 120 20 40 60 80 100 120 % 20 40 60 80 100 120 图像数（张） 图像数（张） (a)准确率 (b）召回率 (c)F测量 (a)Precision (b) Recall (c)F-measure

表1实验结果统计  
Table.1 Experimental results   

<html><body><table><tr><td>算法</td><td>数据集</td><td>准确率</td><td>召回率</td><td>F测量</td></tr><tr><td>本文算法</td><td>ROMA数据集</td><td>0.9602</td><td>0.7491</td><td>0.8367</td></tr><tr><td>文献[2]</td><td>ROMA数据集</td><td>0.9503</td><td>0.7244</td><td>0.7981</td></tr></table></body></html>

![](images/cab861cd5c38846a40072c8bbc346e5f647bafe94d2b950a13e652bbe60d4e1c.jpg)  
图13算法性能指标对比  
Fig.13Comparison of algorithms performance   
图15KITTI数据集实验结果Fig.15Experimental results on KITTI dataset

![](images/e3cc319f019c8d5bbfcfaf63fa09ff3f6229233248a4faf8139143633466aa70.jpg)  
图14ROMA数据集对比实验结果  
Fig.14Experimental results on ROMA dataset图15为本文算法在部分KITTI数据集上的测试结果。

# 4 结束语

本文主要的贡献是有以下两个方面。一方面，采用了导向滤波对图像的边缘特征进行加强，抑制道路平滑区域的噪声;另一方面，引进了模糊连通性分析的方式用于道路模型分段拟合。通过将道路场景分为远、近两个视场，运用邻域分析法减少了道路模型拟合带来的参数估计过程，极大地降低对计算机的性能要求。在数据集的测试过程中，本文提出的一种对光照鲁棒的道路边缘检测算法，在各种道路条件下对光照和强阴影干扰具有较好的鲁棒性，体现出了较好的道路边缘检测效果。

# 参考文献：

[1]Aharaon B H,Ronen H,Dan L,et al.Recent progress in road and lane detection:a survey [J].Machine Vision and Applications,2014,25(3): 727-745.   
[2]Ding Weili,Li Yong,Liu Honghai．An Efficient vanishing point detection method in unstructured road environments based on dark channel prior[J].Iet Computer Vision,2017,10(8): 852-860.   
[3]Yang Weibin,Fang Bin,Tang Yuanyan.Fast and accurate vanishing point detection and its application in inverse perspective mapping of structured road [J].IEEE Trans on Systems Man & Cybernetics Systems,2018,48(5): 755-66.   
[4]Ding Dajun,Lee C,Lee K Y.An adaptive road ROI determination algorithm for lane detection [C]//Proc of IEEE International Conference ofIEEE Region 10.Piscataway,NJ:IEEE Press,2013:1-4.   
[5]Ying Zhenqiang,Li Ge,Tan Guozhen.An Illumination-robust approach forfeature-based road detection[C]//Proc of IEEE International Symposium on Multimedia.Washington DC：IEEE Computer Society, 2015:278-281.   
[6]Ying Zhenqiang,Li Ge,Zang Xiaohong,et al.A novel shadow-free feature extractor for real-time road detection [C]//Proc of the 24th ACM International Conference on Multimedia.New York:ACMPress,2016: 611-615.   
[7]Kim T,Tai Y W,Yoon S E.PCA based computationof illumination-invariant space for road detection [C]//Proc of IEEE Winter Conference on Applications of Computer Vision.Washington DC: IEEE Computer Society,2017:632-640.   
[8]杜凯，宋永超，巨永锋,etal.改进的光照不变道路检测算法[J].交 通运输系统工程与信息,2017,17(5):45-52.(Du Kai,Song Yongchao, Ju Yongfeng，et al. Improved road detection algorithm based on illuminant invariant [J]. Journal of Transportation Systems Engineering & Information Technology,2017.)   
[9]Xiao Liang,Li Chuanxiang,Zhao Dawei,et al.Road marking detection based on structured learning[C]//Proc of the 12th World Congress on Intelligent Control and Automation.Piscataway,NJ:IEEE Press,2016: 2047-2051.   
[10] Chen T,Lu S.Context-aware lane marking detection on urban roads [C]//Proc of IEEE International Conference on Image Processing. Piscataway,NJ:IEEE Press,2015:2557-2561.   
[11] Tan Huachun,Zhou Yang,Zhu Yong,et al.A novel curve lane detection based on Improved River Flow and RANSA [C]//Proc of IEEE, International Conference on Intelligent Transportation Systems. Piscataway,NJ:IEEE Press,2014:133-138.   
[12]He Kaiming,Sun Jian,Tang Xiaoou.Guided image filtering [C]//Proc of European Conference on Computer Vision.Berlin: Springer, 2010: 1-14.   
[13]王晓栋，徐成，刘彦．一种实时鲁棒的非结构化道路检测算法 [J]. 计算机应用研究,2010,27(7):2763-2765.(Wang Xiaodong,Xu Cheng, Liu Yan.Real-time and robust method for unstructured roads detection [J].Application Research of Computers,2010,27(7):2763-2759.)   
[14] Ying Zhenqiang，Li Ge. Robust lane marking detection using boundary-based inverse perspective mapping [C]//Proc of IEEE International Conference on Acoustics,Speech and Signal Processing. Piscataway,NJ:IEEE Press,2016:1921-1925.   
[15]周莉莉，姜枫．图像分割方法综述研究[J].计算机应用研究，2017, 34(7):1921-1928.(ZhouLili,Jiang Feng.Survey onimage segmentation methods [J].Application Research of Computers,2017.)   
[16] Veit T,Tarel JP,Nicolle P,etal.Evaluation ofRoad Marking Feature Extraction [C]//Proc of International IEEE Conference on Intelligent Transportation Systems.Piscataway,NJ:IEEE Press,2009.   
[17] Geiger A,Lenz P,Stiller C,et al.Vision meets robotics:The KITTI dataset [J].International Journal of Robotics Research,2013,32(11): 1231-1237.