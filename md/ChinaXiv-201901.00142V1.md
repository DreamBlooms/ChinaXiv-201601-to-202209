# 自适应滤波结合改进T-Snake模型的甲状腺超声图自动分割方法

周春瑜，程显毅

(南通大学 电气工程学院，江苏 南通 226006)

摘要：提出一种基于T-Snake模型的甲状腺超声波图像分割的新方法。首先，结合基于窗口的各向异性扩散滤波方法与自适应加权中值滤波算法有效地消除甲状腺超声波图像斑点噪声;其次，以传统T-Snake模型为基础，增加自适应的区域能量和膨胀力对非连续边界与弱边界进行有效提取，实现甲状腺超声波图像的自动分割；最后，设定模型参数，使用临床数据进行实验。结果证明，应用该方法得到的自动分割结果的平均相对差异度小于 $5 \%$ ，平均相对重叠度大于 $91 \%$ ，验证了方法的可行性。

关键词：甲状腺超声波图像；图像分割；T-Snake；自适应；加权中值滤波；各向异性扩散滤波 中图分类号：TP391.41 doi: 10.19734/j.issn.1001-3695.2018.09.0787

# Automatic segmentation of thyroid ultrasound images based on adaptive filtering combined with T-Snake model

Zhou Chunyu, Cheng Xianyi (SchoolofElectrical Engineering,Nantong University,NantongJiangsu 226019,China)

Abstract: This paper proposed a new segmentation method of thyroid ultrasonic image basedon T-Snake model.Firstly,a window-basedanisotropicdifusionfilter,combined withandaptive weighted median filter,efectivelyeliminatedspeckle noise inthyroid ultrasonic images.Secondly,themethod,based onthetraditionalT-Snake model and theadaptiveregion energyandexpansion force,extracted the discontinuous boundaryand weak boundary efectively，and realized the automaticsegmentationofthyroidultrasonicimage.Finally,itsetthemodelparametersandexperimentedwiththelinical data.The results showed that the average relative difference is less than $5 \%$ and the average relative overlap is more than $91 \%$ . It verifies the feasibility of the proposed method.

Key words:thyroid ultrasonic image;image segmentation;t-snake;adaptive;weighted median filter;anisotropicdifusior filter

# 0 引言

医学图像的分割问题一直是难题，也是研究热点。目前的分割方法的精度难以满足应用要求。由Kass等人[1提出的Snake模型，是近年来图像处理中用于目标轮廓提取的一种主流模型,但是，传统Snake方法存在许多不足，其分割结果对初始位置依赖较大，对拓扑结构复杂多变的轮廓线提取效果较差。于是有许多研究人员对Snake模型进行了改进[2\~7],Mclnerney等人[8]提出一种拓扑自适应主动轮廓模型（T-Snake)，随着轮廓线的演化，T-Snake模型能够自适应地改变其拓扑结构，对初始位置的要求较低。孟令奎等人[9]提出一种基于正交T-Snake模型的图像分割方法，Zhou等人[10]提出基结合全局与局部分布信息的 Snake 模型的医学图像分割方法，陈能成等人[1]提出一种基于T-Snake模型的改进图像分割方法。虽然这些方法对特定的图像分割效果较好，但是还是存在以下问题：a)斑点噪声对于分割方法效果的影响较大；b)边界连续性差、边界特征信息弱对分割结果影响较大；c不能较好应对甲状腺超声波图像灰度不均匀、边缘特征信息较弱、轮廓连续性较差的问题。

针对上述问题，本文提出一种改进的T-Snake模型。首先，结合自适应加权中值滤波算法与基于窗口的各向异性扩散滤波方法有效去除斑点噪声;其次，在传统T-Snake模型中引入自适应的区域能量和膨胀力来提升方法的鲁棒性，实现非连续边界与弱边界的有效提取。

# 1 斑点噪声自适应的滤波

原始甲状腺超声波图像具有显著的斑点噪声，对于图像分割影响较大，因此必须对原始图像进行预处理。各向异性扩散算法（SRAD）[I2]是常用的斑点噪声滤波算法，其方程定义为

$$
\frac { \partial I ( x , y , t ) } { \partial t } = d i \nu [ c ( q ) \nabla I ( x , y , t ) ]
$$

其中： $I$ 为输入图像； $\textit { t }$ 为扩散时间； $d i \nu$ 为散度算子； $c ( q ) \in$ [0,1]为扩散系数方程。通常，该算法对与中心像素相邻的四像素进行各向异性扩散计算，其缺点在于图像特征边缘常被过度平滑，造成失真。基于窗口的改进的各向异性扩散算法（WSRAD）[13]用子窗口中的像素灰度均值代替四邻域像素灰度值，其缺点在于方法中采用的中值滤波无法保留图像的局部细节信息，亦造成失真。根据超声波图像的斑点噪声的分布特性，本文在WSRAD滤波方法基础上对子窗口进行自适应加权中值滤波，子窗口像素 $( i , j )$ 的权值定义为

$$
W ( i , j ) = \left[ \omega - c d \delta ^ { 2 } \mathrm { / } m \right]
$$

其中： $\mid c \mid$ 为调节因子， $\textit { d }$ 为子窗口像素点(i,j)与窗口中心点的距离， $\delta ^ { 2 }$ 为子窗口灰度方差， $m$ 为子窗口灰度均值， $\omega$ 为子窗口中心像素点的权值，[]为取整运算符。在本文实验中，取中心点权值 $\omega$ 为15，调节因子c为1。实验结果如图1所示。

![](images/c3a88a9f6eca71f04330d39ef95ee3044ea78c6d7b39c96df9a7b39de569111a.jpg)  
图1斑点噪声滤波实验结果  
Fig.1Experimental results of speckle noise filtering

图1中，SRAD方法产生了斑块效应，WSRAD方法避免了斑块效应，但是造成了图像局部信息的丢失。本文提出的WSRAD方法很好的保留了图像局部特征信息，同时有效滤除了斑点噪声，较好的完成了超声波图像的预处理。

# 2 改进的 T-Snake 模型

在T-Snake中，其能量函数定义为

$$
E _ { t o t a l } = E _ { i n } + E _ { e x }
$$

其中： $E _ { i n }$ 为内力，其表征轮廓的连续性和光滑性，与轮廓的形状密切相关； $E _ { e x }$ 为外力，表征演化轮廓与目标轮廓之间的距离，其与图像梯度，图像灰度的统计特性等图像性质密切相关。

在传统的 Snake 模型中，内力定义为

$$
E _ { i n } = \int _ { 0 } ^ { 1 } \alpha ( s ) { \big | } C ( s ) { \big | } ^ { 2 } d s + \int _ { 0 } ^ { 1 } \beta ( s ) { \big | } C ^ { \cdot } ( s ) { \big | } ^ { 2 } d s
$$

其中： $C ( s )$ 为轮廓曲线的参数方程， $C \left( s \right)$ 为曲线的一阶导数;$C ^ { " } ( s )$ 为曲线的二阶导数； $\alpha ( s )$ 表示曲线的弹性系数； $\beta ( s )$ 表示曲线的刚性系数；第一项为弹性势能，起到收缩曲线的作用，保证曲线的连续性；第二项为刚性势能，起到限制曲线弯曲度的作用，保证曲线的光滑性。

T-Snake 模型对传统的Snake 模型进行了离散化处理。将轮廓曲线用 $\mathfrak { n }$ 个采样点表示 $\left\{ x _ { i } \vert 1 \leq i \leq n , n \in N ^ { + } \right\}$ ，对于某个轮廓节点 $x _ { i }$ ，其内力定义[14]为

$$
E _ { i n } = \sum _ { i = 1 } ^ { n } a | \overrightarrow { 2 x _ { i } } - \overrightarrow { x _ { i - 1 } } - \overrightarrow { x _ { i + 1 } } | ^ { 2 } + b | \overline { { d _ { i } } } - d _ { i } |
$$

其中： $x _ { i + 1 }$ 与 $x _ { i - 1 }$ 为节点 $x _ { i }$ 的相邻节点； $d _ { i }$ 为相邻节点之间的距离； $\overline { { \overline { { d } } } } _ { i }$ 为 $d _ { i + 1 }$ 与 $d _ { i - 1 }$ 的加权平均值； $\boldsymbol { a }$ 为弹性系数； $b$ 为刚

性系数。

常用T-Snake模型包括膨胀力与图像力，对于图像中清晰且连续的边界轮廓检测效果较好，但是，在甲状腺超声波图像中，甲状腺轮廓边缘特征信息较弱，连续性较差。对此，本文在传统T-Snake 模型基础上，引入一种基于局部区域最小方差的区域能量项[15]，外力定义为

$$
E _ { e x } = \sum _ { i = 1 } ^ { n } ( 1 - \eta ) ( E _ { \mathrm { I m } a g e } + E _ { { I n } \eta { I a t i o n } } ) + \eta E _ { \mathrm { R e } g i o n }
$$

其中： $E _ { I m a g e }$ 为图像力，推动轮廓向目标轮廓演化逼近 $E _ { I n f l a t i o n }$ ：为膨胀力，使得轮廓快速收敛到目标轮廓。 $E _ { R e g i n }$ 为区域能量项，在目标轮廓边界特征信息较弱，连续性较差的情况下，区域能量项保证收敛边界的正确性； $\mathfrak { n }$ 为区域能量项 $E _ { \scriptscriptstyle { R e g i o n } }$ 的权重值。图像力 $E _ { I m a g e }$ 定义为

$$
E _ { I m a g e } = - c \big | \nabla G ( x , y ) ^ { * } I ( x , y ) \big | ^ { 2 }
$$

其中： $\mid c \mid$ 为图像力大小系数； $\boldsymbol { \nabla }$ 表示梯度算子； $\nabla G ( x , y ) \ast I ( x , y )$   
表示高斯平滑函数与输入图像的卷积。

膨胀力 $\pmb { { \cal E } } _ { \mathrm { I n f l a t i o n } }$ 定义为

$$
E _ { I n f l a t i o n } = - q \cdot F ( I ( x , y ) ) \cdot n ( x , y )
$$

其中： $F ( I ( x , y ) )$ 根据轮廓点 $( x , y )$ 邻域内图像统计特性决定膨胀力的方向； $n ( x , y )$ 为轮廓节点 $( x , y )$ 处的法向量大小； $q$ 为自适应的膨胀力系数。在传统方法中， $q$ 通常设定为常数，为了达到更好的鲁棒性与收敛速度，本文定义自适应膨胀力系数为

$$
q = 2 - \exp ( - \delta - \sigma )
$$

$$
\delta = \operatorname* { m a x } _ { ( x , y ) \in \Omega } I ( x , y ) - \operatorname* { m i n } _ { ( x , y ) \in \Omega } I ( x , y )
$$

$$
\sigma = \sum _ { ( x , y ) \in \Omega } \left( I ( x , y ) - \mu \right) ^ { 2 }
$$

其中： $\Omega$ 为轮廓点 $( x , y )$ 的 $3 { \times } 3$ 邻域，轮廓线将此邻域分割为内部区域与外部区域； $\delta$ 为邻域内最大灰度值与最小灰度值之差； $\sigma$ 为邻域内灰度方差； $\mu$ 为邻域内灰度均值。当轮廓线位于灰度均匀图像区域时， $q$ 近似于1，此时轮廓保持原有特性进行演化；轮廓位于灰度不均匀区域时， $q$ 介于1与2之间，额外的膨胀力驱动轮廓加速离开这一区域。

区域能量项 $E _ { \mathrm { R e g i o n } }$ 定义为

$$
E _ { \mathrm { R e } g i o n } = \frac { 1 } { 2 } { \Biggl [ \sum _ { p \in \Omega _ { 1 } } } ( I _ { P } ( x , y ) - \mu _ { 1 } ) ^ { 2 } + \sum _ { p \in \Omega _ { 2 } } ( I _ { p } ( x , y ) - \mu _ { 2 } ) ^ { 2 } { \Biggr ] }
$$

其中： $I _ { p } ( x , y )$ 为邻域 $\Omega$ 内点 $p ( x , y )$ 处灰度值， $\mu _ { 1 }$ 为邻域在轮廓内部区域灰度均值； $\mu _ { 2 }$ 为轮廓外部区域灰度均值； $\Omega _ { \scriptscriptstyle 1 }$ 为内部区域； $\Omega _ { 2 }$ 为外部区域。

从数学的观点看，总体能量 $E _ { t o t a l }$ 是一个关于轮廓曲线的泛函，利用贪婪算法可求得总能量最小时的轮廓曲线，此曲线即为目标轮廓。

# 3 实验分析

# 3.1实验准备

由先验知识可知，描述甲状腺轮廓曲线时设定的弹性系数不宜过小，刚性系数不宜过大，区域能量权重系数不宜过小。本文方法中，模型参数设置为：弹性系数 $a = 0 . 1$ ；刚性系数 $b = 0 . 4$ ；区域能量权重系数 $\eta = 0 . 3$ ；图像力系数 $c = 5$ ；高斯平滑函数核设为1.5。

实验环境为：MATLAB7.1,Lenovo X230i,CPU $2 . 4 \ : \mathrm { G H z }$ 内存6GB；实验数据为：南通市第一人民医院提供的20套甲状腺超声波图像，其中包括了原始数据集与专家标注集，对数据集图像进行归一化处理作为实验导入数据。

# 3.2评估方法

本文采用超声波图像分割效的常用评估方法:相对重叠度(ROD)与相对差异度(RDD)。两者公式定义为

$$
R O D = \operatorname* { m i n } \left( \frac { \left| C _ { T } \bigcap C _ { s } \right| } { \left| C _ { T } \right| } , \frac { \left| C _ { T } \bigcap C _ { s } \right| } { \left| C _ { s } \right| } \right) \times 1 0 0 \%
$$

$$
R D D = \frac { | C _ { T } | - | C _ { s } | } { | C _ { T } | } \times 1 0 0 \%
$$

其中： $C _ { T }$ 为目标轮廓区域，本文中以专家手动分割结果作为目标区域； $C _ { s }$ 为实验收敛轮廓区域。 $R O D$ 表示的是收敛轮廓曲线与目标轮廓曲线的重叠程度， $R D D$ 表示两者的差异程度。

# 3.3实验结果

20套临床数据的分割实验结果如表1、2所示，图2\~4为典型的分割实验结果图示。

表1实验结果ROD  
Table1 Experimental results-ROD   

<html><body><table><tr><td colspan="5">TabieTExpennentalTesults-ROD</td></tr><tr><td></td><td>最大ROD</td><td>最小ROD</td><td>平均ROD</td><td>方差</td></tr><tr><td>本文方法</td><td>94.3%</td><td>87.2%</td><td>91.3%</td><td>4.8%</td></tr><tr><td>正交T-Snake</td><td>88.4%</td><td>76.4%</td><td>83.6%</td><td>9.2%</td></tr><tr><td colspan="3">表2实验结果RDD</td><td></td><td></td></tr><tr><td colspan="3">Table 2 Experimental results-RDD</td><td></td><td></td></tr><tr><td></td><td>最大RDD</td><td>最小RDD</td><td>平均RDD</td><td>方差</td></tr><tr><td>本文方法</td><td>6.2%</td><td>3.6%</td><td>4.8%</td><td>1.6%</td></tr><tr><td>正交T-Snake</td><td>12.7%</td><td>4.2%</td><td>8.6%</td><td>5.4%</td></tr></table></body></html>

表1与2的实验结果表明，平均相对差异度小于 $5 \%$ 平均相对重叠度大于 $91 \%$ ，验证了本文方法的可行性。

图2\~4中，本文方法的结果与专家分割的结果吻合度较高，较好地处理了甲状腺超声波图像灰度不均匀、边缘特征信息较弱的问题。

![](images/074598a99e612c7dd14610349bee6a4ff8cec7cee8831a5b59368a6a72064f65.jpg)  
图2实验数据分割结果IFig.2Results of segmentation I

![](images/cde3a3cbe9ede77f80a8cbe3c2de24a20a414450a2fb69a4323ab32a993e1f1b.jpg)  
图3实验数据分割结果II

![](images/17a48660bff65b185e07b57b8497aadbca399ce587740e7d7636ef74cbab47a1.jpg)  
Fig.3Results of segmentation II   
图4实验数据分割结果 IIIFig.4Results of segmentation III

# 4 结束语

本文提出了一种新的甲状腺超声波图像的分割方法。在各向异性滤波方法的基础上，引入自适应中值滤波，有效地滤除了斑点噪声；将自适应的区域能量与膨胀力引入T-Snake模型，实现了对弱边缘特征信息的有效提取。下一步将致力于将本研究应用于甲状腺超声图像的在线实时分析。

# 参考文献：

[1]Kass M,Witkin M,Terzopoulos D.Snake:active contour models [J]

International Journal of Computer Vision,1987,1（4）:321-331.   
[2] 胡学刚，邱秀兰．基于 Snake 模型的图像分割新算法[J].计算机应 用，2017,37 (12):3523-3527.(Hu Xuegang，Qiu Xiulan.A new algorithm for image segmentation based on Snake model[J]. Journal of Computer Applications,2017,37(12):3523-3527.)   
[3] 张庭亮，甄倩倩．一种基于Snake模型改进的虹膜边界定位算法[J]. 现代计算机(专业版），2017(31): $1 4 - 1 7 + 3 0$ .(Zhang Tingliang,Zhen Qianqian.An improved iris boundary location algorithm based on Snake model[J].Modern Computer,2017 (31): 14-17+30.)   
[4]蔡舒妤，余乃春，师利中．基于改进 Snake模型的机体损伤区域划分 方法[J].计算机工程，2017,43（7): $2 9 8 \substack { - 3 0 2 + 3 0 8 }$ 、(Cai Shuyu,Yu Naichun,Shi Lizhong.Division method of damage area based on improved Snake model [J].Computer Engineering，2017,43(7): $2 9 8 - 3 0 2 + 3 0 8 .$ ）   
[5] 凌滨，索健文，许景涛．一种结合 Snake 与GAC 模型的虹膜定位方 法[J].计算机工程与应用，2017,53(1):201-206，231.(Ling Bin, Suo Jianwen,Xu Jingtao.An iris location method combining Snake and GAC model[J].Computer Engineering and Applications,2017,53 (1): 201-206，231.)   
[6]林克正，李慧，李新元．基于 Snake 和外观模板的组合式图像对象 分割[J].计算机应用研究,2016,33(3):927-929,944.(Lin Kezheng, Li Hui,Li Xinyuan.Combined image object segmentation based on Snake and appearance template [J].Application Research of Computers, 2016,33 (3):927-929,944.)   
[7]赵立川，高阳．基于改进自仿射映射系统与参数活动轮廓的医学图 像分割算法[J].计算机应用研究，2017,34(2）：616-620.(Zhao Lichuan,Gao Yang.Medical image segmentation algorithm based on improved self affine mapping system and parametric active contour [J]. Application Research of Computers,2017,34(2) 616-620.)   
[8]McInerney T,Terzopoulos D.T-snakes: topology adaptive snakes [J]. Medical Image Analysis,2000,4(2): 73-91.   
[9]孟令奎，吕琪菲．复杂水体边界提取的改进正交 T-Snake 模型[J]. 测绘学报,2015,44(6):670-677.(Meng Linkui,Lyu Qifei.Improved orthogonal T-Snake model for complex water body boundary extraction [J].Acta Geodaetica et Cartographica Sinica,2015,44(6):670-677.)   
[10] Zhou S,Wang J, Zhang S,et al.Active contour model based on local and global intensity information for medical image segmentation[J]. Neurocomputing,2016;186(4): 107-118.   
[11]陈能成，刘丹丹，杜文英．改进Balloon Snake 算法提取遥感影像水 体边界[J].遥感学报,2017,21(3):425-433.(Chen Nengcheng,Liu Dandan,Du Wenying. Extraction of water boundary of remote sensing image using improved Balloon Snake algorithm [J].Journal of remote sensing,2017,21(3):425-433.)   
[12]Deepak M,Santanu C,Mukul S,et al.Edge probability and pixel relativity-based speckle reducing anisotropic diffusion [J].IEEE Trans on Image Processing,2018,27 (2): 649-664.   
[13] Hong R, Zhang PY, Zhang Y X,et al.Assessment of left ventricular myocardialviabilityby3-Dimensional speckle-tracking echocardiography in patients with myocardial infarction [J].Journal of Ultrasound in Medicine,2016,35 (8):1631-1638.   
[14] Claire B,Nicolas C,Philippe C,et al. On the generation of sampling schemes for magnetic resonance imaging [J]. SIAM Journal on Imaging Sciences,2016,9(4): 2039-2072.   
[15] Carlini E,Ferreti R.A semi-Lagrangian scheme with radial basis approximation forsurfacereconstruction[J].Computingand Visualization in Science,2017,18 (2-3):103-112.