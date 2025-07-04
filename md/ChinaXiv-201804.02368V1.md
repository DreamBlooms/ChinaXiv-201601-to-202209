# 基于Canopy聚类的噪声自适应模糊C-均值算法‘

陈凯，陈秀宏，孙慧强(江南大学 数字媒体学院，江苏 无锡 214122)

摘要：针对局部空间信息的模糊C-均值算法（WFLICM）中空间影响因子容易受到噪声影响出现错误标识的问题，提出一种融合局部和非局部空间信息的模糊C-均值聚类图像分割算法(NLWFLICM)，在WFLICM算法的模糊影响因子中引入非局部空间信息，根据噪声程度自适应地设置局部和非局部信息权重，并重新标记中心点的模糊影响因子。实验结果表明，NLWFLICM算法具有比WFLICM算法更强的鲁棒性和自适应性，并在一定程度上提高了WFLICM算法对含有大量噪声图像进行分割的鲁棒性,同时保留了图像的纹理。为了提高算法的聚类性能和收敛速度,结合Canopy算法能够快速对数据进行粗聚类的优点，提出基于Canopy聚类与非局部空间信息的FCM图像分割改进算法(Canopy-NLWFLICM)，可以在NLWFLICM算法聚类前，对聚类中心进行预处理，从而提高收敛速度和图像分割精度。

关键词：聚类算法；Canopy算法；模糊C-均值算法；局部和非局部空间信息 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.01.0116

# Improved fuzzy C-means clustering algorithm based on canopy clustering

Chen Kai, Chen Xiuhong, Sun Huiqiang (SchoolofDigital Media,Jiangnan University,WuxiJiangsu 214122,China)

Abstract:Aiming at the problem thatthe spatial influencefactors areeasily misidentifiedby noisein the fuzzy C-means algorithm(WFLICM） for local spatial information,this paper proposed a fuzzyC-means clustering algorithm for image segmentation (NLWFLICM)basedonlocaland non-local spatial information.Itintroducedthenon-local spatialinformation into thefuzzy influencingfactorofWFLICMalgorithm,the weightoflocalandnon-local informationisadaptivelysetaccording to the noiselevel,andthefuzzyinfluence factorsofthecentralpointarere-marked.Theexperimentalresultsshowthatthe NLWFLICMalgorithm is more robust and adaptive thanthe WFLICMalgorithm,and improves the robustnessofthe WFLICM algorithmtoalarge extent,while preservingthe image texture.Inordertoimprove theclusteringperformanceandconvergence speed of the algorithm,combined with the advantagesofCanopy algorithm for fast clustering ofdata,this paper proposes an improved algorithm forFCM image segmentation based on Canopyclustering and non-local spatial information (CanopyNLWFLICM) before clustering algorithm.This can improve the convergence speed and image segmentation accuracy. Key Words: clustering algorithm ; Canopyalgorithm ; fuzzy C-means cluster; local and non-local spatial information

# 0 引言

图像分割是图像处理中的关键所在，被广泛应用在人脸识别、医学影像及指纹识别等各种图像处理应用中。当前，图像分割方法有多种，比如区域增长法等。其中基于聚类方法被广为认同，硬C-均值聚类算法以及模糊C-均值聚类算法(fuzzyC-meansalgorithm，FCM)[1]是最常用的两种聚类算法。与HCM算法相比，FCM算法为每个像素的归属引入了模糊概念，保留更多纹理细节信息。

由于传统的FCM算法存在不足，只关注到图像像素灰度相似性，忽视了图像其他影响信息，从而导致FCM的分割结果不理想。为此，国内外学者研究了许多基于局部空间信息的改进FCM算法。Ahmed 等人[2]在FCM的目标函数中加入邻域项，提出了基于空间约束的模糊C-均值算法（FCMalgorithmbasedonspaceconstraint)，增强了抗噪声能力，但也增加了算法的时间复杂度。针对该问题，Chen等人[3]用邻域像素的均值或中值来代替对应的像素点提出了FCM_S1和FCM_S2模型。该模型减少了算法计算时间，但模糊了图像的许多细节。于是，Cai 等人[1提出了同时考虑邻域位置和像素关系的快速FCM聚类算法（fast generated fuzzy C-means algorithm）。该算法虽在一定程度上抑制了噪声，却引入了太多人工参数，且分割精度不高。

对于参数比较多同时要人工进行设定问题，Stelios等人[4]在经过研究之后，阐述了局部空间模糊C-均值算法(fuzzylocalinformation C-meansalgorithm，FLICM),该算法引入了模糊影响因子，考虑邻域像素的空间信息和灰度信息，且参数不用人为设定，大大增强了算法适用范围。其全部参数能够自适应确定，在鲁棒性方面表现非常出色，能够让图像细节得到有效的保存。基于此，Gong 等人[5]在局部空间信息模糊C-均值（fuzzy localinformationC-meansalgorithm）算法的基础上引入了像素点的邻域像素变异系数c_k，提出了修正的局部空间模糊C-均值算法（modified fuzzy local information C-means algorithm）。若噪声高度污染图像时，在一个像素的邻域像素中可能会包含很多异常特征，如图1所示，容易出现分割错误。此外，WFLICM算法用欧氏距离作相似性度量，容易造成低维空间线性不可分现象。

为解决这些问题，本文在模糊影响因子中引入了非局部空间信息影响因子，根据图像噪声污染程度同时考虑局部信息和非局部信息对中心像素点的影响，提出了融合局部和非局部空间信息的模糊C-均值聚类(NLWFLICM)算法，并用和距离代替传统欧氏距离。而对于算法本身依赖于初始类中心选择和复杂度较高的问题，本文提出了Canopy-NLWFLICM算法，在聚类之前得到较为准确的初始类中心，在此基础上用改进算法聚类，实验结果也说明了方法的有效性及对实际问题的实用性。

# 1 相关工作

# 1.1局部空间信息的模糊C-均值聚类（WFLICM）算法

为了克服传统模糊C-均值聚类算法在图像分割时仅利用像素点灰度值信息的问题，WFLICM算法继承了FCM算法的优势，同时还融入了领域空间信息，综合像素点邻域框内像素点对中心点的影响，构造目标函数：

$$
J = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { c } u _ { i j } ^ { m } \left[ \left( x _ { i } - \nu _ { j } \right) ^ { 2 } + G _ { i j } \right]
$$

其中 $\pmb { x } _ { i }$ 在 WFLICM 算法中表示第i个像素点的灰度值 ${ \bf \nabla } _ { \bf \cdot } v _ { j }$ 在WFLICM算法中为第类的类中心灰度值， $\tilde { G } _ { i j }$ 是加入的模糊影响因子,相关定义具体如下:

$$
G _ { i j } = \sum _ { i \neq k } w _ { i k } \frac { 1 } { ( d _ { i k } + 1 ) } \Big ( 1 - u _ { k j } \Big ) ^ { m } \Big ( x _ { k } - \nu _ { j } \Big ) ^ { 2 } ,
$$

其中： $N _ { \mathrm { i } }$ 表示像素点 $x _ { i }$ 所在的邻域窗口； $d _ { i k }$ 表示邻域窗口中的点 $\boldsymbol { \mathfrak { X } } _ { k }$ 与中心像素点 $\pmb { x } _ { i } ^ { \prime }$ 的坐标位置距离； $w _ { \dot { \mathrm { i } } \dot { \kappa } }$ 是邻域内像素点影响因子权重，定义为

$$
w _ { i k } = \left\{ \begin{array} { l l } { \displaystyle { \frac { 1 } { 2 + \operatorname* { m i n } \Big ( \big ( c _ { k } / c _ { i } \big ) ^ { 2 } , \big ( c _ { i } / c _ { k } \big ) ^ { 2 } \Big ) } } , i f c _ { k } > \overline { { c } } } \\ { \displaystyle { \frac { 1 } { 2 - \operatorname* { m i n } \Big ( \big ( c _ { k } / c _ { i } \big ) ^ { 2 } , \big ( c _ { i } / c _ { k } \big ) ^ { 2 } \Big ) } } , i f c _ { k } < \overline { { c } } ^ { - } } \end{array} \right. ,
$$

其中： $c _ { k }$ 是邻域像素点的变异系数，以中心像素点 $x _ { k }$ 为中心：

$$
c _ { k } = { \frac { \operatorname { v a r } \left( x \right) } { \left( { \overline { { x } } } \right) ^ { 2 } } } ,
$$

其中： $v a r ( x )$ 代表邻域中全部像素点灰度值的方差， $\frac { \ d } { \ d x }$ 是邻域内像素点灰度值的均值。

$$
\overline { { c } } = \frac { \displaystyle \sum _ { k \in N _ { i } } c _ { k } } { N _ { i } } ,
$$

于是，由利用拉格朗日乘子法得到隶属度更新公式为

$$
u _ { i j } = \frac { 1 } { \displaystyle \sum _ { k = 1 } ^ { c } \left( \frac { d _ { i j } ^ { 2 } + G _ { i j } } { d _ { i k } ^ { 2 } + G _ { i k } } \right) ^ { \gamma _ { m - 1 } } } , 1 \le j \le c , 1 \le i \le n
$$

聚类中心更新公式为

$$
\nu _ { j } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } u _ { i j } ^ { m } x _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } u _ { i j } ^ { m } } , 1 \leq j \leq c
$$

# 1.2 Canopy 算法

Canopy 是聚类算法的一种实现,它是一种快速、简单，但是不太精确的聚类算法，Canopy 聚类最大的特点是不需要事先指定聚类的个数，因此具有很大的实际应用价值，可以用在预处理阶段，对数据进行粗聚类。Canopy算法基本流程如下：

a）设置阈值T1、T2， $\mathrm { T } 1 { > } \mathrm { T } 2$ （关于阈值的选取可通过交叉验证得到)；b）从数据集中任取一点P，将P作为第一个Canopy，并将它从数据集中删除;c）继续从集合中取点，计算其到已经产生的所有Canopy的距离，如果到某个Canopy的距离小于T2，则将其加入到该Canopy，如果它到所有Canopy中心的距离都大于T1，则将其作为一个新Canopy，如果该点到某个Canopy 距离小于T1，并在其与所有Canopy 距离计算完成后仍未加入任何Canopy，则将它作为一个新的Canopy;

d）重复第c)步，直至数据集为空。  
算法流程图如图1所示。

![](images/7d8f801bf1a3804ad0f9a91c4e1a73892604774dbe6e6c499898efb1bbc61a51.jpg)  
图1Canopy 算法流程图

# 2 本文改进算法

# 2.1融合局部和非局部空间信息的模糊C-均值聚类(NLWFLICM)算法

WFLICM算法充分考虑了局部空间信息和局部灰度值关系对像素点的影响，在很大程度上降低了对噪声的敏感度。但当图像噪声污染严重时，一个像素点的邻域像素会存在异常特征造成局部信息对中心像素点聚类的影响发生错误。对于这种情况，显然只考虑局部空间信息会导致图像分割效果很难令人满意。本文提出融合局部和非局部空间信息的模糊C-均值聚类算法(NLWFLICM)，该方法将非局部空间信息加入到影响因子中，并根据图像中噪声的大小程度在去噪的同时尽量保留图像的细节特征。定义目标函数(5)中的模糊影响因子为

$$
\begin{array} { l } { { \displaystyle { G _ { i j } = \left( 1 - \alpha _ { i } \right) \sum _ { k \ne i } w _ { i k } \frac { 1 } { \left( d _ { i k } + 1 \right) } \left( 1 - u _ { k j } \right) ^ { m } \left( x _ { k } - \nu _ { j } \right) ^ { 2 } } \ ~ } } \\ { { \displaystyle { } } } \\ { { \displaystyle { + \alpha _ { i } \sum _ { r \ne i } S _ { i r } \left( x _ { r } , x _ { i } \right) \left( x _ { r } - \nu _ { j } \right) ^ { 2 } } , } } \end{array}
$$

$$
{ \mathrm { \Large ~ _ { i \bf \overline { { { c } } } } ~ } } A _ { i j } = \sum _ { { k \ne i } \atop { k \in N _ { i } } } w _ { i k } \frac { 1 } { \left( d _ { i k } + 1 \right) } \Big ( 1 - u _ { k j } \Big ) ^ { 2 } \Big ( x _ { k } - \nu _ { j } \Big ) ^ { 2 } ,
$$

$$
B _ { i j } \ = \ \sum _ { { r \neq i } \atop { r \in \Omega _ { i } } } S _ { i r } \big ( x _ { r } , x _ { i } \big ) \big ( x _ { r } \ - \ \nu _ { j } \big ) ^ { 2 } ,
$$

则 $A _ { \mathbf { i j } }$ 为局部空间信息影响因子， $\bar { B } _ { \dot { \mathrm { i } } \dot { J } }$ 为非局部空间信息影响因子。在非局部空间信息影响因子 $\cdot B _ { \mathrm { i } j }$ 中， $S _ { i r } ( x _ { i } , x _ { i } )$ 表示搜索窗□ $\underline { { \hat { n } } } _ { i }$ 中像素 $x _ { p }$ 与中心像素 $\mathbf { x _ { i } }$ 间的相似度， $S _ { i \nu } ( \boldsymbol { x } _ { p } , \boldsymbol { x } _ { i } )$ 满足条件 $0 \leq S _ { i r } ( x _ { r } , x _ { i } ) \leq 1$ 和 $\begin{array} { r } { \sum _ { r \in \varOmega _ { i } } S _ { i r } \left( x _ { r } , x _ { i } \right) = 1 } \end{array}$ ，它的值由以 $x _ { p }$ 、$\boldsymbol { x } _ { i }$ 为中心的矩形邻域 $N _ { r }$ 与 $N _ { \widehat { \mathbf { z } } }$ 间的距离 $\| V ( N _ { r } ) - V ( N _ { i } ) \| ^ { 2 }$ 决定：

$$
S _ { i r } ( x _ { r } , x _ { i } ) = \frac { 1 } { S \big ( x _ { i } \big ) } e ^ { - \frac { \big \| V \big ( N _ { r } \big ) - V \big ( N _ { i } \big ) \big \| ^ { 2 } } { h ^ { 2 } } } ,
$$

其中 $\| V ( N _ { r } ) - V ( N _ { i } ) \| ^ { 2 }$ 是两个邻域中像素点灰度值均值之差，$5 { \binom { x _ { \mathrm { i } } } { \mathrm { i } } }$ 为归一化系数：

$$
S \big ( x _ { i } \big ) = \sum _ { r \in \Omega _ { i } } e ^ { - \frac { \big \| V \big ( N _ { r } \big ) - V \big ( N _ { i } \big ) \big \| ^ { 2 } } { h ^ { 2 } } } ,
$$

$h$ 用来对高斯函数的衰减程度进行控制。 $h$ 的大小影响去噪效果和细节的保留，越大去噪能力会更强，不过易造成过平滑，越小可以保留更多图像细节，不过去噪效果会变差。本文参数可以根据被污染图像的噪声级别自适应设置。设 $\sigma$ 是噪声的标准差，它可以通过图像估算得到[9]， $\gamma$ 是图像的平滑参数，（本文设置为10），则

$$
h \ : = \ : \gamma \sigma _ { \circ }
$$

模糊因子 $\vec { G } _ { i j }$ 中控制局部和非局部空间信息的权重参数 $\tilde { \alpha } _ { i }$ 可用定义为

$$
\alpha _ { i } = \frac { 1 } { Q - 1 } S \big ( x _ { i } \big )
$$

其中Q表示搜索窗口内所有像素点的个数。

由于使用相似度函数计算权重参数，而相似度函数取决于参数h的值，而h又与噪声的标准差成正比，所以当噪声污染程度较小时，h 的值将会很小，同时权重参数 $\bar { \alpha } _ { \mathrm { i } }$ 也会很小，此时主要考虑局部空间 信息的影响；反之，当噪声污染程度较大时，非局部空间信息对中心像素点聚类的影响较大。因此根据自适应参数h，局部和非局部空间信息可以合理地得到利用。

本文用高斯核距离]代替WFLICM算法中传统的欧式距离。本文提出NLWFLICM算法，NLWFLICM的目标函数如下：

$$
\begin{array} { l } { { \displaystyle { G _ { i j } = \left( 1 - \alpha _ { i } \right) \sum _ { \stackrel { k \neq i } { k \in i } } w _ { i k } \frac { 1 } { \left( d _ { i k } + 1 \right) } \left( 1 - u _ { k j } \right) ^ { \mathrm { m } } \left\| \Phi ( x _ { i } ) - \Phi ( \nu _ { j } ) \right\| ^ { 2 } } } } \\ { { \displaystyle ~ + ~ \alpha _ { i } \sum _ { r \neq i } S _ { i r } \big ( x _ { r } , x _ { i } \big ) \Big \| \Phi ( x _ { i } ) - \Phi ( \nu _ { j } ) \Big \| ^ { 2 } , } } \\ { { \displaystyle ~ { r \in \Omega _ { i } } ~ } } \end{array}
$$

$\| \Phi ( x _ { i } ) - \Phi ( v _ { j } ) \| ^ { 2 }$ 在NLWFLICM算法中表示高维特征空间中定义的距离， $\Phi ( \cdot )$ 则表示低维到高维空间的映射。具体定义为[17]

$$
\begin{array} { r l } & { \| \Phi ( x _ { i } ) - \Phi ( v _ { j } ) \| ^ { 2 } } \\ & { = \Big ( \Phi ( x _ { i } ) - \Phi ( v _ { j } ) \Big ) ^ { \mathrm { T } } \Big ( \Phi ( x _ { i } ) } \\ & { - \Phi ( v _ { j } ) \Big ) } \\ & { = \Phi ( x _ { i } ) ^ { \mathrm { T } } \Phi ( x _ { i } ) - \Phi ( v _ { j } ) ^ { \mathrm { T } } \Phi ( x _ { i } ) - \Phi ( x _ { i } ) ^ { \mathrm { T } } \Phi ( v _ { j } ) } \\ & { + \Phi ( v _ { j } ) ^ { \mathrm { T } } \Phi ( v _ { j } ) } \\ & { = K ( x _ { i } , x _ { i } ) + K \big ( v _ { j } , v _ { j } \big ) - 2 K \big ( x _ { i } , v _ { j } \big ) } \end{array}
$$

NLWFLICM算法中核函数使用的是高斯核函数：

$$
\mathbf { K } { \left( x , y \right) } = \exp \left( { \frac { \mathsf { H } \ x \mathsf { I } \ y \mathsf { I } ^ { 2 } } { \sigma ^ { 2 } } } \right)
$$

于是，由利用拉格朗日乘子法得到隶属度更新公式为

$$
\begin{array} { r } { \mathbf { u } _ { \mathbf { i } \mathbf { j } } = \frac { 1 } { \sum _ { \mathbf { k } = 1 } ^ { \mathbf { c } } \left( \frac { \left( 2 - 2 ^ { * } \mathbf { k } \left( \mathbf { x _ { i } } , \mathbf { v _ { j } } \right) + \mathbf { G _ { i j } } ^ { * } \right) } { \left( 2 - 2 ^ { * } \mathbf { k } \left( \mathbf { x _ { i } } , \mathbf { v _ { k } } \right) + \mathbf { G _ { i k } } ^ { * } \right) } \right) ^ { 1 / \left( \mathbf { m } - 1 \right) } } } \end{array}
$$

$$
\begin{array} { r } { \mathbf { v } _ { \mathrm { j } } = \frac { \sum _ { \mathrm { i = 1 } } ^ { \mathrm { N } } \left( \mathbf { u } _ { \mathrm { i j } } ^ { \mathrm { m } } \mathbf { k } ( \mathbf { x } _ { \mathrm { i } } , \mathbf { v } _ { \mathrm { k } } ) \mathbf { x } _ { \mathrm { i } } \right) } { \sum _ { \mathrm { i = 1 } } ^ { \mathrm { N } } \left( \mathbf { u } _ { \mathrm { i j } } ^ { \mathrm { m } } \mathbf { k } ( \mathbf { x } _ { \mathrm { i } } , \mathbf { v } _ { \mathrm { k } } ) \right) } } \end{array}
$$

# 2.2 Canopy-NLWFLICM 算法

融合局部和非局部空间信息的模糊C-均值聚类算法（NLWFLICM）解决了图像局部空间信息被噪声污染导致图像分割精度下降和分割错误的问题，但在算法在收敛速度和算法复杂度上和传统FCM 算法一样依赖初始中心点的选取，从而导致算法复杂度高，收敛速度慢等缺点。为此本文在NLWFLICM算法聚类前用Canopy 算法先对图像进行预处理，得到粗聚类中心，提出Canopy-NLWFLICM算法，降低了算法复杂度，提高了聚类收敛速度。

Canopy-NLWFLICM算法如下：

a）选定聚类数目c、模糊指数m、邻域窗口 $N _ { \mathrm { i } }$ 、搜索窗口$\bar { \varOmega } _ { \bar { \varepsilon } }$ 、最大迭代次数T和阈值ε、T1和T2;

b）用Canopy算法得到聚类初始中心;c）利用式(4)计算 $\boldsymbol { w _ { \mathrm { i k } } }$ ，式(11)计算 $\cdot \bar { s } _ { i \gamma } ( \boldsymbol { x } _ { p } , \boldsymbol { x } _ { i } )$ d）利用式（15）计算Gj；e）利用式(18)计算隶属度矩阵 $U$ ，利用式(19)计算聚类中心；f）根据当前和 $\pmb { U }$ ，计算目标函数(8)的值。若迭代次数大于T或者相邻两次目标函数值差的绝对值小于阈值E，则算法停止；否则，令 $t = t + 1$ ，转b)。

# 3 实验结果与分析

为了测试本文提出的Canopy-NLWFLICM算法图像分割性能，分别在人工合成图像和自然图像上进行对比实验。实验运行环境是Matlab2014b。以下实验中设定模糊指数 $\mathrm { m } { = } 2$ ，迭代阈值 $\scriptstyle \varepsilon = 0 . 0 0 1$ ，最大迭代次数 $\scriptstyle \mathrm { T = } 5 0 0$ ， $N _ { \widehat { \mathbf { z } } }$ 为 $3 ^ { * } 3$ 邻域， $\bar { \varOmega } _ { i }$ 为$1 1 ^ { * } 1 1$ 的搜索窗口。为说明Canopy-NLWFLICM算法的分割有效性，本文用KFLICM、WFLICM和Canopy-FCM作为比较算法。

# 3.1人工合成图像分割实验

第一节实验围绕人工合成图像进行，总数为3张，添加的高斯以及椒盐噪声强度有差异。对比分析图像分割算法的抗噪声能力，我们常采用分割准确性(SA)指标来衡量其好坏。SA是指正确分类的像素点占总分割像素点的百分比，代表图像分割精度：

$$
S A = \sum _ { i = 1 } ^ { c } \frac { A _ { i } \bigcap C _ { j } } { \sum _ { j = 1 } ^ { c } C _ { j } } ,
$$

其中：c为分割的类数， $\blacktriangleleft _ { i }$ 指算法分割到第i类的像素点，$\vec { C _ { i } }$ 指图像中属于第i类的像素点集。

图2为四种分割算法在第一张人工合成图像中添加均值为0方差为0.02高斯噪声后的分割结果。从分割结果可以看出，KFLICM算法和Canopy-FCM算法的分割图受噪声影响非常严重；WFLICM算法能够消除一定的噪声；Canopy-NLWFLICM算法在去噪声和保持边缘细节上表现最好，几乎不受噪声影响，表现出较强的去噪能力。

![](images/5c6634a19e34a13a5f23a9fa4505292567504200506a48e74465bdddd3d265c7.jpg)  
图2第一张合成图像分割实验

基于图3可以看到，随着高斯噪声强度越来越大，在这种情况下，对比算法会有着越来越低的SA值，而本文改进的两种算法分割精度变化最小，基本上保持在 $9 9 \%$ 以上。SA数据说明Canopy-NLWFLICM算法比KFLICM、WFLICM和Canopy-FCM去噪效果更具鲁棒性。

![](images/eac705c48c3dd0d21449790a3e2614281016523d9d82349a4866c3277178b7ba.jpg)  
图3四种算法在第一张合成图像上的分割精度 $( \mathrm { S A \% } )$ （204号

第二张合成图像分四类共 $2 4 4 ^ { * } 2 4 4$ 个像素点，图4是四种算法在第二张图像受密度为0.15的椒盐噪声污染后的分割结果。WFLICM算法受噪声影响非常严重，分割图上留有大量的噪声点；Canopy-NLWFLICM算法去椒盐噪声能力最强，分割结果图没有明显噪声点。

![](images/9e4eaa8c30b6c88a6b9676489a4f63878860b1349e2d4ff1079e919b891961e2.jpg)  
图4第二张合成图像分割实验

基于图5可以看到，随着椒盐噪声强度越来越大，在这种情况下，对比算法会有着越来越低的SA值，而本文改进的两种算法分割精度变化最小，其他两种种算法的分割精度 SA明显下降，Canopy-NLWFLICM算法精度下降幅度最小。SA数据说明Canopy-NLWFLICM算法较其他三种算法有着更好的椒盐噪声能力。

![](images/04328f1efe63128d1f101153f8666fcd02eba2c70211e6b6ac01607ef64d41fd.jpg)  
图5四种算法在第二张合成图像上的分割精度 $( \mathrm { S A \% } )$

第三张合成图像分四类共 $2 5 6 ^ { * } 2 5 6$ 个像素点。图6为四种算法在第三张图像添加均值为0方差为0.02高斯噪声后的分割结果。KFLICM算法受噪声影响严重，分割图上留有大量的噪声点；Canopy-NLWFLICM算法去椒盐噪声能力最强，Canopy-NLWFLICM算法的分割结果图几乎和原图像一致。

![](images/c812a59d2463b2ce51dbb810abf14d7727f04ab2ec04e8f379ea5f86526294d9.jpg)  
图6第三张合成图像分割实验

基于图7可以看到，随着高斯噪声强度越来越大，在这种情况下，对比算法会有着越来越低的SA值，而本文改进的两种算法分割精度变化最小，其他三种算法的分割精度 SA 明显下降，Canopy-NLWFLICM算法精度下降幅度最小。SA数据说明本文改进的算法较其他三种算法去噪能力更强。

![](images/4f056310d697b89d808b22ad3e2b6ab8d60812426947b5990da9d428286d71ed.jpg)  
图7四种算法在第二张合成图像上的分割精度 $( \mathrm { S A \% } )$

# 3.2 自然图像分割实验

本实验用三张自然图像来比较四种算法的在处理自然噪声图像时的分割性能。在比较四种算法在自然图像上的抗噪声能力时将涉及到结构相似性(SSIM),SSIM用来判断两幅图像的相似性程度：

$$
\mathrm { S S I M } = \frac { \big ( 2 \mu _ { x } \mu _ { y } + C _ { 1 } \big ) \big ( 2 \sigma _ { x } \sigma _ { y } + C _ { 2 } \big ) \big ( \sigma _ { x y } ^ { 2 } + C _ { 3 } \big ) } { \big ( \mu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } + C _ { 1 } \big ) \big ( \sigma _ { x } ^ { 2 } + \sigma _ { y } ^ { 2 } + C _ { 2 } \big ) \big ( \sigma _ { x } \sigma _ { y } + C _ { 3 } \big ) } ,
$$

其中： $C _ { 1 } = ( K _ { 1 } L ) ^ { 2 } , C _ { 2 } = ( K _ { 2 } L ) ^ { 2 } , C _ { 3 } = \frac { C _ { 2 } } { 2 } , K _ { 1 } = 0 . 0 1$ $K _ { 2 } = 0 . 0 3 , L = 2 5 5$ ，平均值和方差的计算公式如下：

$$
\mu _ { x } = \frac { 1 } { m * n } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } X \bigl ( i , j \bigr ) ,
$$

$$
\sigma _ { X } ^ { 2 } = \frac { 1 } { m * n - 1 } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \left( X \Big ( i , j \Big ) - \mu _ { X } \right) ^ { 2 } ,
$$

$$
\sigma _ { X Y } ^ { 2 } = \frac { 1 } { m * n - 1 } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \big ( X \big ( i , j \big ) - \mu _ { X } \big ) \big ( X \big ( i , j \big ) - \mu _ { Y } \big ) ,
$$

此外实验采用欠分割率（UR）对分割结果进行评价。

$$
U R = \frac { U _ { s } } { R _ { s } + O _ { s } }
$$

其中： $U _ { s }$ 表示本应该包含在分割结果中实际却不在分割结果中的像素点个数， $R _ { s }$ 表示理论分割图像中像素点个数， $o _ { s }$ 表示不应该包含在分割图像中的像素点个数。

第一张自然图像大小分别为 $^ { 1 7 3 * 1 7 3 }$ ，图8给出了四种算法在第二张图像添加椒盐(0.10)噪声后的分割结果。从第一张自然图像分割效果图明显可以看出，WFLICM算法出现了分割错误，Canopy-FCM算法和KFLICM算法边缘分割不够清晰，噪点明显，而Canopy-NLWFLICM算法分割图最接近原图。

![](images/c1fd424de46398f611e74284a64d6b7013a9dbbfff25fd52c5d19312cfed678c.jpg)  
图8第一张自然图像分割实验

表1给出了四种算法分割结果图与第一张自然图像间的结构相似性。SSIM的数据说明Canopy-NLWFLICM分割图与原图结构上最相似。

表1四种算法分割图与第一张自然图像间的结构相似性  

<html><body><table><tr><td>噪声</td><td>KFLICM</td><td>WFLICM</td><td>CanopyFCM</td><td>Canopy-NLWFLICM</td></tr><tr><td>椒盐(0.10)</td><td>0.9515</td><td>0.9428</td><td>0.9503</td><td>0.9769</td></tr><tr><td>椒盐(0.15)</td><td>0.9483</td><td>0.9346</td><td>0.9369</td><td>0.9722</td></tr><tr><td>椒盐(0.20)</td><td>0.9301</td><td>0.9243</td><td>0.9274</td><td>0.9682</td></tr></table></body></html>

表2给出了四种算法在第一张自然图像上的欠分割率，数据说明Canopy-NLWFLICM算法在分割准确率相比另三种算法要更高。

表2四种算法在第一张自然图像上的欠分割率 $\mathrm { U R \% }$   

<html><body><table><tr><td>噪声</td><td>KFLICM</td><td>WFLICM</td><td>CanopyFCM</td><td>Canopy-NLWFLICM</td></tr><tr><td>椒盐(0.10)</td><td>0.1856</td><td>0.1271</td><td>0.1583</td><td>0.0774</td></tr><tr><td>椒盐(0.15)</td><td>0.2539</td><td>0.1694</td><td>0.1843</td><td>0.1109</td></tr><tr><td>椒盐(0.20)</td><td>0.3328</td><td>0.2208</td><td>0.2535</td><td>0.1592</td></tr></table></body></html>

第二张自然图像大小分别为 $^ { 1 7 3 * 1 7 3 }$ ，图9给出了四种算法在第二张图像添加椒盐(0.15)噪声后的分割结果。Canopy-FCM 算法在自然图像上去椒盐噪声能力最差，Canopy-NLWFLICM分割效果图比另三种算法在去噪和保留图像细节上的效果更好。

![](images/cd9b8bab1f4c3a363f4204ce6d7c62887ec48568f14823d69b70bbdb07dba3f9.jpg)  
图9第二张自然图像分割实验

表3给出了四种算法分割结果图与第二张自然图像间的结构相似性。SSIM的数据说明Canopy-NLWFLICM分割图与原图结构上最为相似。

表3四种算法分割图与第二张自然图像间的结构相似性  

<html><body><table><tr><td>噪声</td><td>KFLICM</td><td>WFLICM</td><td>CanopyFCM</td><td>Canopy-NLWFLICM</td></tr><tr><td>椒盐(0.10)</td><td>0.9335</td><td>0.9422</td><td>0.9366</td><td>0.9597</td></tr><tr><td>椒盐(0.15)</td><td>0.9283</td><td>0.9318</td><td>0.9295</td><td>0.9536</td></tr><tr><td>椒盐(0.20)</td><td>0.9107</td><td>0.9259</td><td>0.9131</td><td>0.9498</td></tr></table></body></html>

表4给出了四种算法在第一张自然图像上的欠分割率，数据说明Canopy-NLWFLICM算法在分割准确率相比另三种算法要更高。

表4四种算法在第二张自然图像上的欠分割率 $\mathrm { ( U R \% ) }$   

<html><body><table><tr><td>噪声</td><td>KFLICM</td><td>WFLICM</td><td>CanopyFCM</td><td>Canopy-NLWFLICM</td></tr><tr><td>椒盐(0.15)</td><td>0.1605</td><td>0.1226</td><td>0.1589</td><td>0.0919</td></tr><tr><td>椒盐(0.20)</td><td>0.1977</td><td>0.1536</td><td>0.1953</td><td>0.1232</td></tr><tr><td>椒盐(0.25)</td><td>0.2353</td><td>0.1877</td><td>0.2322</td><td>0.1604</td></tr></table></body></html>

第三张自然图像大小分别为 $2 2 0 ^ { * } 2 2 0$ ，图10给出了四种算法在第二张图像添加椒盐(0.02)噪声后的分割结果。Canopy-NLWFLICM分割效果图比其他三种算法分割效果图去噪效果更好，图像背景与人物细节分割最为清晰，也更加光滑流畅。

![](images/1bd6a2d216b88441b9a948743c82e10410fcea30ee4b574980e2621477e868eb.jpg)  
图10第三张自然图像分割实验

表5给出了四种算法分割结果图与第三张自然图像间的结构相似性。SSIM 的数据明显说明Canopy-NLWFLICM分割图与原图结构性最相似。

表5四种算法分割图与第三张自然图像间的结构相似性  

<html><body><table><tr><td>噪声</td><td>KFLICM</td><td>WFLICM</td><td>CanopyFCM</td><td>Canopy-NLWFLICM</td></tr><tr><td>椒盐(0.01)</td><td>0.8925</td><td>0.8742</td><td>0.8906</td><td>0.9039</td></tr><tr><td>椒盐(0.02)</td><td>0.8276</td><td>0.7906</td><td>0.8538</td><td>0.8577</td></tr><tr><td>椒盐(0.03)</td><td>0.7503</td><td>0.7255</td><td>0.8322</td><td>0.8407</td></tr></table></body></html>

表6给出了四种算法在第一张自然图像上的欠分割率，数据说明Canopy-NLWFLICM算法在分割准确率相比另三种算法要更高。

表6四种算法在第三张自然图像上的欠分割率 $( \mathrm { U R \% } )$ 号  

<html><body><table><tr><td>噪声</td><td>KFLICM</td><td>WFLICM</td><td>CanopyFCM</td><td>Canopy-NLWFLICM</td></tr><tr><td>椒盐(0.10)</td><td>0.1905</td><td>0.1866</td><td>0.1952</td><td>0.1644</td></tr></table></body></html>

<html><body><table><tr><td>椒盐(0.15)</td><td>0.2283</td><td>0.2103</td><td>0.2313</td><td>0.1893</td></tr><tr><td>椒盐(0.20)</td><td>0.2579</td><td>0.2399</td><td>0.2679</td><td>0.2271</td></tr></table></body></html>

以上所有试验都证明Canopy-NLWFLICM算法比KFLICM算法和WFLICM算法有更强的去噪声能力，相比Canopy-FCM算法能更好地保存图像细节，与原图的结构性也最为相似。此外，在大量噪声污染时，WFLICM算法出现分割错误问题，而Canopy-NLWFLICM算法会通过噪声程度对局部和非局部信息进行对应地调整，从而克服分割错误所带来的问题。

# 4 结束语

针对局部空间信息的模糊C-均值算法（WFLICM）在被大量噪声污染时分割错误问题，本文引入非局部信息影响因子，提出了NLWFLICM 算法，实验结果表明该方法具有更好的图像分割能力。由于参数h可以根据图像中存在的噪声标准差计算，使其适应于噪声的比例，而局部与非局部空间的权重可通过非局部空间信息来计算，从而使局部和非局部空间信息自适应地影响目标函数中的相似性度量。以这种方式，局部和非局部空间信息可以被适当地用于低程度和高程度损坏的噪声图像的分割。针对算法依赖初始类中心选择问题，本文提出Canopy-NLWFLICM算法，首先用Canopy算法进行预处理，得到初始类中心，在此基础上用NLWFLICM算法进行聚类，提高了算法的分割精度和收敛速度。通过不同类型的分割实验证明了本文算法的优秀的去噪声的能力和良好的鲁棒性，图像细节也同时得到一定的保留，具有一定的实际应用价值。当然，本文也存在一些不足之处，其算法复杂度较高，接下来的工作就是在此基础上提高时间效率，使其更具实用性。

# 参考文献：

[1]Dunn JC.A fuzzy relative of the isodata process and its use in detecting compact well-separated clusters [J].Cybernetics,1973,3:32-57.   
[2]Ahmed M N,Yamany S,Mohamed N,et al.A modified fuzzy C-means algorithm for bias field estimation and segmentation ofMRI data [J].IEEE Trans on Medical Imaging,2002,21 (3): 193-199.   
[3]Chen Songcan, Zhang Daoqiang. Robust image segmentation using FCM with spatial constraints based on new kernel-induced distance measure [J]. IEEE Trans on Systems Man& Cybernetics PartB Cybernetics,2004,34 (4): 1907-1916.   
[4]Krinidis S,Chatzis V.A robust fuzzy local information C-means clustering algorithm [J].IEEE Trans on Image Processing,2010,19(5):1328-1337.   
[5]Gong Maoguo,Liang Yunfeng,Jiao Shi,et al.Fuzzy C-means clustering with local information and kernel metric for image segmentation [J].IEEE Trans on Image Processing,2013,22 (2): 573-584.   
[6]Bezdek JC,Ehrlich R,Full W. FCM:the fuzzy C-means clustering algorithm[J].Computers& Geosciences,1984,10(2):191-203.   
[7] Zhang Daoqiang,Chen Songcan.A novel kernelized fuzzy C-means algorithm with application in medical image segmentation [J].Artificial aigoritnm witn noniocal aaaptuve spatial constraint Ior image segmentaton [J]. Signal Process,2011,91(4): 988-999.   
[9]Pyatykh S, Hesser J, Zheng Lei. Image noise level estimation by principal component analysis [J]. IEEE Trans on Image Processing,2013,22 (2): 687   
[10] Cai Weiling, Chen Songcan, Zhang Daoqiang.Fast and robust fuzzy Cmeans clustering algorithms incorporating local information for image segmentation [J].Pattern Recognition,2007,40 (3): 825-838.   
[11] Zhao Feng, Jiao Licheng,Liu Hanqiang. Fuzzy C-means clustering with nonlocal spatial information for noisy image segmentation [J].Frontiers of Computer Science in China,2011,5 (1): 45-56   
[12] Zhao Feng. Fuzzy clustering algorithms with self-tuning non-local spatial information for image segmentation [J]. Neurocomputing,2013,106 (6): 115-125.   
[13] Chen Long,Chen C L,Lu Mingzhu.A multiple-kernel fuzzy C-means algorithm for image segmentation [J].IEEE Trans on Systems Man & Cybernetics,Part B: Cybermetics,2011,41(5): 1263-1274.   
[14] Chen Long,Lu Mingzhu, Chen C L. Multiple kernel fuzzy C-means based image segmentation [C]//Proc of IEEE International Conference on Systems Man and Cybernetics. 2010: 4123-4129.   
[15] Dubey Y,Mushrif M.FCM clustering algorithms for segmentation of brain MR images.[J].Advances in Fuzzy Systems,2016 (3): 1-14.   
[16]Qing Yu, Zhimin Ding.Improved Canopy-FCM algorithm based on MapReduce [C]// Proc of the 9th International Congress on Image and Signal Processing. 2017: 1975-1977.   
[17] Yu Qing,Ding Zhimin. An improved Fuzzy C-means algorithm based on MapReduce [C]//Proc of the 8th International Conference on Biomedical Engineering and Informatics.2016: 634-638.   
[18] KaurA,Kumar R,Kaur S.Novel approach of new dualistic enhancement fordigital image segmentation using FCM[J].International Journal of Computer Applications,2017,158 (10): 5-10.   
[19] Zhang Zhenkai, Cheng J,Wu J,et al. A novel data association algoritm based on FCM-DFA[J]. ICIC Express Leters,2017,11(10):1489-1496.   
[20] Hamdi T, Ghith A,Fayala F. Characterization of drape profile using fuzzyC-mean (FCM) method [J].Fibers & Polymers,2017,18(7): 1401-1407.   
[21] Sweta S,Lal K.Personalized adaptive learner model in e-learning system using FCM and fuzzy inference system [J] International Journal of Fuzzy Systems,2017,19 (5): 1-12.   
[22]肖林云，陈秀宏，林喜兰．邻域信息熵的核模糊C-均值聚类图像分割 算法[J].微电子学与计算机,2016,33(11):166-170.(Xiao Linyun,Chen Xiuhong，Linxilan. New kernel fuzzy C-meansclustering image segmentation algorithm with local entropy information[J]. Microelectronics and Computers,2016,33 (11): 166-170. )   
[23]马自堂，苟杰．基于MapRed uce的FCM聚类集成算法[J].计算机应 用研究,2016,33(12):3554-3558.(Ma Zitang,Gou Jie.FCM clustering

ensemble algorithm based on MapReduce [J].Application Research of Computers,2016,33(12):3554-3558.)

[24]李玉峰，李景芳．基于FCM算法的SAR图像相干斑噪声滤波算法研究 [J].计算机应用研究,2016,33(8):2496-2499.(Li Yufeng,Li Jingfang. Coherent noise filtering algorithm in SAR images based on FCMalgorithm [J].Application Research ofComputers,2016,33(8):2496-2499.)

[25]李明，夏鸿斌.基于CMT-FCM的自适应谱聚类算法[J].计算机应用 研究,2017,34 (3): 739-742.(Li Ming,Xia Hongbin,Adaptive spectral clustering algorithm based on CMT-FCM [J].Application Research of Computers,2017,34(3):739-742.)