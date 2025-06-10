# 无人机影像与地形指数结合的梯田信息提取

薛牡丹ä，张宏鸣a，杨江涛ʰ，李星恕‘

(西北农林科技大学a.信息工程学院;b.水利与建筑工程学院;c.机械与电子工程学院，陕西 杨凌 712100)

摘要：目前，通过卫星遥感、低空遥感影像自动，半自动化解译梯田信息有一定的研究进展，但是受数据获取成本、精度、解译方法单一等限制，只限于大面积提取梯田区域。低成本地进行梯田的田面精准提取以及面积统计仍需进一步研究。基于面向对象方法分别对 $0 . 5 \mathrm { m }$ 分辨率的无人机正射影像和地形指数，及两种数据的结合进行梯田区域分割、提取及面积统计。结果表明，将正射影像数据与地形指数结合的梯田的田面提取结果优于基于单一数据源。

关键词：梯田；无人机正射影像；地形指数；面向对象；监督分类 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.01.0182

# Extraction of terrace information based on UAV image and topographic index

Xue Mudana, Zhang Hongminga†, Yang Jiangtaob,Li Xingshuc (a.CollegeofInformationEngineering,b.CollgeofWaterResources&ArchitecturalEngineering,c.InstituteofMechanical &Electrical Engineering,Northwest A&F University,Yangling Shaanxi 7121oo,China)

Abstract:Atpresent,semi-utomatic interpretingterace informationhadcertainresearch progress troughsatelitemote sensingandlow-altituderemotesensingimagery.However,limitedbydataacquisitioncost,accuracyandsingleinterpetation methods,itwascurretlylimitedtolrgescaleextractionofterracedareas.Accurateextractionoftrrcefieldndreastatistics atlowcoststillrequire furtherstudy.Inthisstudy,basedonthebject-orientedapproach,theorthophotoandterrainindexof UAV with $0 . 5 \mathrm { m }$ resolution,and the fusion of the two kinds ofdata were used for extraction of terrce field and area statistic. The results show that withthe fusion oforthophoto and terrain index it is superior to those based onasingle data source.

KeyWords: terrace; UAV orthophoto; topographic index; object-oriented ; supervised classification

# 0 引言

梯田的修筑是人类在坡耕地上探索的一种水土保持措施，很大程度上开发了坡耕地的农业生长潜力，具有蓄水、保土作用[1]。长期以来，通过目视解译是获取梯田信息的主要技术手段。但限于经验知识，技术成本等，对于梯田的数量、面积及分布等信息的调查资料不完善，导致梯田在水土保持中的贡献缺乏定量研究。随着高分辨率影像获取技术和处理技术的不断发展，基于纹理特征的傅里叶变换算法，模板匹配算法等梯田信息提取成为可能[2-4]。但由于纹理特征不明显，不规则，以及傅里叶变换算法窗口大小影响，模板匹配算法的模板尺寸固定不灵活等限制，大量漏提和错提现象。而且算法只考虑梯田的纹理特征和灰度特征，对于梯田的颜色，形状，坡度等地形指数并未充分利用。

面向对象分类方法能充分利用梯田的颜色，形状等信息而应用于梯田信息提取。张雨果[51，党恬敏[等研究者基于分辨率相对较低的单一卫星遥感数据源，试错法找到最优尺度（主观性强，缺乏定量分析)，采用了基于规则（需人为设定规则，主观性强）和K最邻近（K-nearestneighbor,KNN）的面向对象分类方法。在分类之后手工参与错分，漏分调整，属于半自动化梯田区域提取。Eckert等人[7结合4波段的多光谱数据和DSM数据，运用面向对象分类方法梯田进行提取，将光谱信息和DSM结合相较于单独使用光谱信息提取精度更高。与卫星数据相比，无人机航摄系统有低成本，高效率快速及时获取高分辨率影像的优势。Han 等人[8基于DEM，和基于DEM与正射影像与红外波段结合的两类数据源，对比分析基于规则梯田分类结果。但是该研究并未分析单独基于正射影像与红外波段结合的数据源的分类情况，缺乏一定的严谨性和说服力。Diaz-Varela等[9]，结合DEM与多光谱影像数据，通过面向对象的分析方法进行梯田区域的提取，但研究区域田面植被覆盖率较高，提取

精度受到一定影响。

基于面向对象分析，结合高分辨率的影像数据和DEM数据，对大面积梯田区域提取研究已有一定进展。但是存在如下问题：a）几乎所有研究者都停留在大面积提取梯田区域，田面精准提取，面积统计等信息研究目前几乎没有研究进展，没有满足精准农业的需求，而且大部分数据源为卫星遥感影像，获取难度大，成本昂贵;b）目视解译获得多尺度分割的最佳分割尺度，停留在定性阶段，缺乏定量分析;c）分类方法单一，且对于精度评价几乎都未提及评价样本的获取。评价样本越客观，评价结果越具有参考性。

针对目前梯田提取存在的问题，本文结合无人机影像低成本，高效率快速及时获取的优势，应用无人机拍摄的甘肃龙泉$0 . 5 \mathrm { ~ m ~ }$ 高分辨率正射影像影像数据，对无植被覆盖的水平梯田进行提取方法研究。采用面向对象分类技术，对大面积梯田区域的田面进行提取，并统计相应梯田面积。首先，对无人机拍摄的正射影像数据进行预处理和DEM数据地形指数分析；其次应用胡忠文等人[10,I的最优尺度研究方法，基于区域合并演化分析选择评估最佳分割尺度，然后进行分类特征筛选；最终采用KNN，支持向量机（support vector machine，SVM）、决策树（decisiontree）等三种监督方法进行分类，并对比分析三种监督分类的精度结果表明数据结合的提取方法能够获得较高的梯田提取结果。

# 1 实验数据和研究方法

# 1.1实验数据

研究区为中国甘肃省榆中地区龙泉乡黄土丘陵区典型旱梯田，地理坐标范围东经 $1 0 4 ^ { \circ } 1 0 ^ { \prime } 5 8 ^ { \prime \prime } { \sim } 1 0 4 ^ { \circ } 1 9 ^ { \prime } 5 1 ^ { \prime \prime }$ ，北纬$3 5 ^ { \circ } 3 4 ^ { \prime } 4 ^ { \prime \prime } { \sim } 1 3 5 ^ { \circ } 4 0 ^ { \prime } 5 6 ^ { \prime \prime }$ 。数据于2016年3月拍摄，采用安翔动力开发的AF1000 型号无人机，搭载 SONYA5100 相机，单幅影像面积约 $3 4 0 \mathrm { m } \times 5 0 0 \mathrm { m }$ ，影像分辨率 $0 . 0 5 \mathrm { m }$ 。拍摄期，风力小于4级，天气晴朗，能见度高，飞行采用自动起飞/规划航线飞行/自动降落模式，全程总计耗时约 $2 4 \mathrm { h }$ 。数据处理采用Agisoftphotoscan软件，导入影像，POS数据及控制点数据，将整个区域分成25个测区块进行处理，平均每个块5000张左右照片，对每个块逐一进行点云提取和立体模型建立，最后再进行合并、纹理提取，获得数字表面模型（DigitalSurfaceModel，DSM)，采用CGCS2000_3_Gauss_Kruger_CM_105E 投影。由于研究区所在范围在该段时间几乎没有植被覆盖，建筑用地较少，可通过对点云数据进行分类，分为地面点和非地面点两类，将非地面点作为噪声处理，通过滤波后得到剔除非地面点的DEM数据。DEM分辨率 $0 . 5 \mathrm { m }$ ，30000行 $\times 2 4 0 0 0$ 列。依据无人机影像制作的 $1 : 5 0 0$ 地形图的平面和高程精度均满足 $\langle \langle 1 : 5 0 0 \ 1 \$ ：$1 0 0 0 \mathrm { ~ 1 ~ } \colon 2 0 0 0$ 地形图航空摄影测量内业规范》[12]对 $1 : 5 0 0$ 平地、丘陵的成图要求。

本文截取具有不同特征代表性的三块 $1 0 0 0 \mathrm { { p i x ^ { * } l 0 0 0 \mathrm { { p i x } } } }$ 数据区进行试验，如图1所示。区域一的梯田区有部分山丘，建筑物以及道路，田面无覆盖物，田块形状特征较短，较宽，梯田数量较少。区域二的梯田区有部分建筑物，田面有部分庄稼堆积物，田块形状特征整体舒长，较窄，田块边缘曲线光滑，田块数量较多。区域三的梯田区有部分建筑物，田面覆有大面积积雪，田块形状蜿蜒曲折。三块研究区基本代表了样区的梯田地表特征。

![](images/3d0786cc83adcd046ae99527edbd5d0c080edae5a700547892e46f1a06b61995.jpg)  
图1甘肃省榆中县龙泉乡DEM和正射影像数据及其所在位置

# 1.2 研究方法

本文首先对无人机获取的数据进行预处理并得分为三种数据源：a）无人机正射影像直方图均衡化之后的结果作为数据源1；b）用DEM数据提取相应正负地形指数PN（positiveandnegative）、累计曲率AC（accumulativecurvature）、坡度S（slope）剖面曲率数（profilecurvature，PC）、高程变异系数（coefficientofvariation in elevation,CVE）、粗糙度（terrain roughness,TR）、山体阴影HS（hillshade）等7种地形指数，并对7种地形指数进行主成分分析（principal component analysis,PCA）降维处理，降维后的数据作为数据源2；c）直方图均衡化后的无人机影像与PCA降维后的地形指数结合的数据作为数据源3。

其次基于面向对象方法对三种不同数据源进行分类，最后对分类精度进行评价，进行面积统计。研究的技术路线如图2所示。

![](images/0027a04fe8af31c93e035662ef6f5135468b016028ae50076a666745ccdad2c1.jpg)  
图2本文的技术路线图

# 1.2.1无人机正射影像直方图均衡化

高分辨率无人机正射影像地物景观的结构、形状、纹理和细节等信息较突出，但受拍摄天气状况影响，易出现对比度不足，云雾模糊等现象，为特征提取增加了难度。通常采用一定的方法对影像进行预处理，以增大对比度，提高提取精度。

直方图均衡化（histogramequalization，HE）[l3]是常用的图像对比度增强方法。HE是对图像全局进行调整的方法，在某些细节上效果较差；自适应直方图均值化（adaptive histogramequalization，AHE）[14]算法通过计算图像的局部直方图，然后重新分布亮度来改变图像对比度，但该方法在部分区域有过度放大图像中相同区域的噪声的问题；限制对比度直方图均衡化算法（contrast limited adaptive histogram equalization，CLAHE）[15]算法主要是通过限制 AHE 算法的对比提高程度来达到的，对每个小区域都必须使用对比度限幅，从而克服了AHE的过度放大噪声的问题。

在本文中，结合CLAHE 方法既能增强影像对比度又能克服噪声过度放大的优点，对无人机正射影像进行对比度增强和去雾预处理，处理结果作为数据源1，为后续面向对象分析提供良好的数据支持。

# 1.2.2地形指数的计算与降维

梯田的田面识别主要是对田坎变化区域的有效分割，目视解译中，作为地形指数之一的坡度最能够展现该变化的结果。但哪些常用的地形指数还可以作为特征识别的参数，需要进行界定。因此本文先通过ArcMap10.5软件，通过DEM数据计算出相应地形指数：PN，S，AC，PC，CVE，TR，HS。定义及计算公式如下：

a)PN：分析区域内所有栅格中最大高程与最小高程的差。设 $H _ { \mathit { m a x } }$ 为局部最大高程值， $H _ { m e a n }$ 为局部平均高程值。 $P N$ 的计算公式如下：

$$
P N = H _ { m a x } - H _ { m e a n }
$$

b)S：指地表单元陡缓程度，通常把坡面的垂直高度 $H$ 和水平距离 $L$ 的比叫做坡度的比叫做坡度。设 $\boldsymbol { H } _ { d }$ 为高程差，S的计算公式如下：

$$
S = \arctan \left( \frac { H _ { d } } { L } \right)
$$

c)PC：坡度沿地面最大坡降方向的地面高程变化率，本文研究区的坡度以度数法表示。 $P C$ 的计算公式如下：

$$
\scriptstyle P C = S l o p \ o f \ S
$$

d)AC：地面曲率是对地形表面一点扭曲变化程度的定量化度量因子，底面曲率在垂直和水平两个方向上分量分别称为剖面曲率（profile curvature）和平面曲率（planformcurvature）。累计曲率是剖面曲率与平面曲率的差值。设 $K p$ 为剖面曲率,$K c$ 为平面曲率，则AC的计算公式如下：

$$
A C = K p - K c
$$

d)CVE：反映分析区域内地表单元格网各顶点高程变化的指标，它以格网单元顶点的标准差与平均高程的比值来表示，设 $\boldsymbol { s D }$ （StandardDeviation）为标准差， $Z$ 为领域海拔高度， $C V E$ 的计算公式如下

$$
C V E = S D / Z
$$

e)HS：山体阴影是假想一个光源在某个方向和某个太阳高度的模拟下，用过临近像元的计算来生成一副0-255的灰度图。假设 $H i l l s h a d e < 0$ ，则设Hillshade $= 0$ ，Zenith_rad为太阳天顶角的弧度数，Slope_rad为某点的坡度弧度数，Azimuth_rad为太阳光线方向角的弧度数，spect_rad为某一点的坡向弧度数，则HS的计算公式如下：

$$
H S = 2 5 5 , 0 ~ * ~ \left( \left( \begin{array} { l } { \cos { ~ Z e n i t h _ { - } r a d ~ ^ { * } } } \\ { \cos { ~ S l o p e _ { - } r a d } } \\ { \sin { ~ Z e n i t h _ { - } r a d } } \\ { \sin { ~ Z e n i t h _ { - } r a d } } \\ { \sin { ~ S l o p e _ { - } r a d } } \\ { \cos { ~ \left( A _ { A S } m e t h _ { - } r a d - \right) } } \\ { \cos { ~ \left( A _ { A S } p e c t _ { - } r a d \right) } } \end{array} \right) \right) ~ .
$$

f)TR：地表单元的曲面面积 $s$ 与其在水平面上的投影面积之比。计算公式如下：

$$
T R \ = \ 1 / c o s \ S
$$

在包含高程、坡度等的多波段栅格中，地形指数通常由高程数据直接或间接得出，数据冗余现象较为明显。为了减少在面向对象分类时的数据冗余，本文采用主成份分析法 $\mathrm { \Delta [ 1 6 ] _ { P C A } }$ 进行数据降维后，作为数据源2。

# 1.2.3面向对象分类及评价

本文利用面向对象方法对梯田的田面进行提取。首先对三类数据源进行多尺度分割的最优尺度选择，将选择的结果作为专题数据，在eCognition Developer 9.0 软件中进行梯田的田面提取。面向对象分类采用KNN,SVM,决策树等三种监督方法，并对比分析三种监督分类的精度。

a）最优尺度分割。对于基于面向对象分析的遥感图像地物提取而言，图像分割是第一步，图像分割的质量直接决定着后续的面向对象分类提取梯田的精度[17]。近年来，图像分割方法的研究主要概括为基于图论，聚类，分类等算法[18,19]。目前基于超像素的图像分割法较为流行[20-22]，如 SLIC（Simple LinearIterative Clustering )[23]、SEEDS(Superpixels Extracted via Energy-Driven Sampling）[24]、LSC（Linear Spectral Clustering）[25]、MeanShift[26]、Marker-basedWatershed[27]、Graph-Cuts[28]等等。基于超像素法对影像进行分割，能有效利用影像的光谱、纹理、形状等特征，能获得较为均质的对象。但是，目前的超像素分割不能产生细节保留和过分割结果。大多数情况下，超像素分割产生大量的过分割碎片，造成大量数据冗余，在图像分类和目标检测中，冗余的分割碎片很难提高效率和鲁棒性，而且还增加计算负载[10]。因此，需要在分割的基础上进行进一步的处理。分割后处理阶段通常是根据分割目的，对分割后的结果再次进行处理，例如区域合并及区域内滤波去噪等。

目前较为流行的FNEA[29]多尺度分割就是基于超像素初始分割后，再进行区域合并获取分割对象。多尺度分割法是一种自下而上的分割方法，从单个像元开始，向上逐渐合并成较大的对象，直到满足所设置的分割参数条件。与基于单像元光谱特性的影像信息提取方法相比，多尺度分割能够更充分地利用高分辨率遥感影像的信息。eCognitionDeveloper9.0 软件提供的FNEA多尺度分割算法，所涉及主要参数包括尺度、形状、紧致度3个，尤其是与分割对象大小密切相关的尺度参数，需要解译人员根据研究区域、目标并结合以往经验设定。这极大地限制了高分辨率遥感影像的自动解译。借鉴人工试错方法对分割结果定量评价，实现分割参数自动选择已成为当前的一种新趋势[30]。

能自适应地选取较为合适的分割尺度是高分辨率遥感图像多尺度分割技术中的关键问题。本文应用胡忠文等[10,I1]的最优尺度研究方法，在尺度集模型中进行全局演化分析并进行非监督尺度集约简，得到最优分割尺度。该研究结合FNEA[29]算法，应用层次迭代优化的区域合并方法，构建了区域层次结构，并得到梯田影像的多尺度表达，即尺度集模型。尺度集模型可以把层次区域合并过程完整的记录下来，并记录整个过程中产生区域的层次关系，并将每个区域进行尺度索引。因此通过尺度集模型可以反算任意尺度的影像分割结果，从而解决调整分割尺度参数的问题。在区域合并的同时进行了全局演化分析，依据最小风险贝叶斯决策规则进行基于全局演化分析的尺度集约简，最后再基于局部演化分析进行尺度集约简。选择欠分割的代价权重 $\scriptstyle { \mathrm { C } = 1 }$ 时，尺度集达到最佳约简，选择其为最佳分割尺度。

b）分类特征筛选。多尺度分割完成之后，本文先基于区域一的三种数据源，目视解译出一定量的梯田和非梯田样本对象，对样本对象的各波段进行分类特征计算，计算方法如表1。对得到的分类特征进行箱线图统计直观分析，筛选可分性较强的特征作为分类特征。

表1分类特征  

<html><body><table><tr><td>特征</td><td>说明</td></tr><tr><td>平均值 Mean</td><td>影像对象的所有像素的图层值的平均值</td></tr><tr><td>标准差StdDev</td><td>影像对象的所有像素的图层值计算得到标准差</td></tr><tr><td>亮度Brightness</td><td>影像对象的图层数量除以包含光谱信息的图层 平均值的总和</td></tr><tr><td>长宽比</td><td></td></tr><tr><td>Length/Width</td><td>协方差矩阵的特征值的比值，较大的作为分子</td></tr><tr><td>形状指数</td><td>影像对象的边界长度除上它的面积的平方根的</td></tr><tr><td>Shape Index</td><td>4倍</td></tr><tr><td></td><td>相关性（Correlation）</td></tr><tr><td>灰度共生矩阵</td><td>对比度（Contrast）</td></tr><tr><td>GLCM</td><td>熵（Entropy）</td></tr><tr><td></td><td>均质性(Homogeneity)</td></tr></table></body></html>

c)监督分类。应用分类特征对多尺度分割的对象进行KNN，SVM，决策树监督分类。

KNN算法是一种非参数的，基于统计的分类算法。主体思想：在训练集中数据和标签已知的情况下，输入测试数据，将测试数据的特征与训练集中对应的特征进行相互比较，找到训练集中与之最为相似的前K个数据，则该测试数据对应的类别就是K个数据中出现次数最多的那个分类。计算对象间不同特征值之间的距离作为各个对象之间的非相似性指标，避免了对象之间的匹配问题，距离计算方法一般使用欧氏距离(式(8))。对于本文的关于梯田与非梯田的二分类问题，K值应选择为奇数。

$$
d ( x , y ) = { \sqrt { \sum _ { k = 1 } ^ { n } ( x _ { k } - y _ { k } ) ^ { 2 } } }
$$

SVM算法，最早由Cortes 和Vapnik 提出[31]，是一个凸二次规划求解问题，即对线性不可分的两类问题，其最优的分类形式为：把学习样本非线性映射到高维特征空间，在高维特征空间构造线性判别函数，将原样本空间中非线性可分的问题转化为在高维特征空间线性可分的问题，使得两类无错误地分开，并使两类的分类间隙最大。在小样本、非线性情况下，具有较好的泛化性能。本文基于径向核函数（radialbasisfunction,RBF)采用遗传算法（geneticalgorithms，GA）寻找最优参数（惩罚系数c与核函数半径g)，对多尺度分割后的梯田与非梯田对象建立分类模型。

决策树是一种基本的分类与回归方法。决策树模型呈树形结构，在分类问题中，表示基于特征对实例进行分类的过程。决策树学习算法包含特征选择、决策树的生成与剪枝过程。分类与回归树（classificationand regression tree,CART）算法[32]选择特征采用基尼指数（Ginicoefficient)。将训练数据集（训练样本）划分为测试变量和目标变量，通过对这两变量的循环分析形成二叉决策树。基于对象的决策树分类在地物提取得到广泛应用[33,34]，能更好的挖掘图像信息，是图像分类从一种纯粹的认识过程转化为一种具有先验知识的再认识过程[34]。

d)分类精度评价。精度评价是指比较实地数据与分类结果，以确定分类过程的准确程度。本文通过目视解译获得分类评价样本。在arcmap10.5里绘制接近于实际梯田的真值图，并且统计了田面的实际面积。基于目视解译获得的评价样本，采用eCognition Developer9.0 软件中提供的“Error Matrix based onTTAMASK”对分类结果进行评价。最常用的精度评价方法是混淆矩阵[35-37]（ErrorMatrix）方法。设样本总类别数为 $k$ ，样本总数为 $N$ ，测试样本中i类的样本总数 $N _ { _ { i + } }$ 计算公式如式(9)所示。实际分类中被分为j类的样本总数 $N _ { + j }$ 的计算公式如式（10）所示。

$$
N _ { i + } = \sum _ { j = 1 } ^ { k } N _ { i j }
$$

$$
N _ { + j } = \sum _ { i = 1 } ^ { k } N _ { i j }
$$

其中： $N _ { _ { i j } }$ 为测试样本中本应该分为i类而实际分类结果中却被分为j类的样本数目。从混淆矩阵可以计算出各种精度统计值，如生产者精度（producer'saccuracy，PA）[38]，用户精度（user'saccuracy，UA)，总体精度（overallaccuracy，OA)，Kappa系数[39]等，计算公式分别如式（11) $\sim$ （14）所示。

$$
P A _ { j } = \frac { N _ { j j } } { N _ { + j } }
$$

$$
U A _ { i } = \frac { N _ { i i } } { N _ { i + } }
$$

$$
O A = \frac { \displaystyle \sum _ { i = 1 } ^ { k } N _ { i i } } { N }
$$

$$
K = { \frac { N . { \sum _ { i } ^ { k } } N _ { i i } - { \sum _ { i = 1 } ^ { k } } ( N _ { i + } * N _ { + j } ) } { N ^ { 2 } - { \sum _ { i = 1 } ^ { k } } ( N _ { i + } * N _ { + j } ) } }
$$

# 2 结果与讨论

# 2.1 CLAHE处理结果

本文对无人机正射影像采用CLAHE 算法进行增强(图3)，对比增强前后可以得出，增强后的影像数据田坎轮廓更加清晰，为进一步研究提供良好的数据源。

# 2.2地形指数计算及降维结果

利用ArcMap10.5软件求出三块样区的七种地形指数，并进行PCA分析，得出相关系数矩阵，如表2，3，4所示。观察三个相关性分析表，得出，PN与CVE的相关系数分别为0.980，0.975，0.978。PN与S的相关系数分别为0.924，0.910，0.894。CVE与S的相关系数分别为0.939，0.929，0.903。设相关系数阈值为0.9，可以确定CVE，PN，S之间具有强关联性，信息有冗余。对7种地形指数进行PCA主成份分析，得出5种相关性弱的数据组合。实验结果为S，PC，AC，HS，TR这5种地形指数为主要成份，如图4所示。其中S1，PC1，AC1，HS1，TR1代表区域一的，依此类推。

表2区域1地形指数相关性分析  

<html><body><table><tr><td>波段</td><td>PN</td><td>AC</td><td>CVE</td><td>S</td><td>PC</td><td>TR</td><td>HS</td></tr><tr><td>PN</td><td>1.000</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>AC</td><td>0.025</td><td>1.000</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CVE</td><td>0.980</td><td>-0.010</td><td>1.000</td><td></td><td></td><td></td><td></td></tr><tr><td>S</td><td>0.924</td><td>-0.007</td><td>0.939</td><td>1.000</td><td></td><td></td><td></td></tr><tr><td>PC</td><td>0.171</td><td>0.004</td><td>0.175</td><td>0.191</td><td>1.000</td><td></td><td></td></tr><tr><td>TR</td><td>-0.001</td><td>-0.000</td><td>-0.001</td><td>-0.001</td><td>0.001</td><td>1.000</td><td></td></tr><tr><td>HS</td><td>-0.328</td><td>0.005</td><td>-0.330</td><td>-0.332</td><td>-0.040</td><td>-0.000</td><td>1.000</td></tr><tr><td></td><td></td><td>表3</td><td></td><td>区域2 地形指数相关性分析</td><td></td><td></td><td></td></tr><tr><td>波段</td><td>PN</td><td>AC</td><td>CVE</td><td>S</td><td>PC</td><td>TR</td><td>HS</td></tr><tr><td>PN</td><td>1.000</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>AC</td><td>0.034</td><td>1.000</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CVE</td><td>0.975</td><td>-0.009</td><td>1.000</td><td></td><td></td><td></td><td></td></tr><tr><td>S</td><td>0.910</td><td>-0.003</td><td>0.929</td><td>1.000</td><td></td><td></td><td></td></tr><tr><td>PC</td><td>0.237</td><td>-0.001</td><td>0.241</td><td>0.256</td><td>1.000</td><td></td><td></td></tr><tr><td>TR</td><td>-0.000</td><td>-0.001</td><td>-0.000</td><td>-0.000</td><td>0.000</td><td>1.000</td><td></td></tr><tr><td>HS</td><td>-0.016</td><td>0.005</td><td>-0.003</td><td>0.000</td><td>0.030</td><td>-0.002</td><td>1.000</td></tr></table></body></html>

表4区域3地形指数相关性分析  

<html><body><table><tr><td>波段</td><td>PN</td><td>AC</td><td>CVE</td><td>S</td><td>PC</td><td>TR</td><td>HS</td></tr><tr><td>PN</td><td>1.000</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>AC</td><td>0.031</td><td>1.000</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CVE</td><td>0.978</td><td>-0.010</td><td>1.000</td><td></td><td></td><td></td><td></td></tr><tr><td>S</td><td>0.894</td><td>-0.003</td><td>0.903</td><td>1.000</td><td></td><td></td><td></td></tr><tr><td>PC</td><td>0.229</td><td>0.002</td><td>0.234</td><td>0.268</td><td>1.000</td><td></td><td></td></tr><tr><td>TR</td><td>-0.000</td><td>0.000</td><td>-0.000</td><td>-0.001</td><td>-0.001</td><td>1.000</td><td></td></tr><tr><td>HS</td><td>-0.177</td><td>0.003</td><td>-0.180</td><td>-0.135</td><td>-0.052</td><td>-0.000</td><td>1.000</td></tr></table></body></html>

![](images/5a3ea963b16416124d6f84d6422397f080312af9f2f5705e37b3988730719cd5.jpg)  
图3CLAHE 前后对比图

# 2.3 分类及结果评价

# 2.3.1多尺度分割

基于研究区域的三类数据源，首先应用胡忠文等[10,II方法，将形状因子为0.5，紧致度因子为0.8，建立相应的尺度集并找出最佳分割尺度，其次将分析结果导入到eCognitionDeveloper9.0中，作为专题数据，并进行多尺度分割，如图5所示。对比基于三种数据源的分割结果，分析区域1图5b，c,d)，区域2图5f，g，h）,区域3图5j，k，1）的红，蓝，绿框线区域。

a）基于数据源1（图5b，f，j）的分割。红框和蓝框区域都出现欠分割。欠分割的原因：梯田边缘光谱差异较小，覆盖物，田块窄小（红框区域)，田坎过窄（蓝框区域）等的干扰，导致无法分割。

![](images/443b11d62f5a9a12a3f87179ea93ecff4d33ca6e28e12768d19574e6b6b11158.jpg)

图5研究区域1\~3的三类数据源的多尺度分割最优效果图

b)基于数据源2（图5c、g、k）的分割。在区域一、三（图5c、k）的红框和蓝框区域分割完好，边缘清晰可见。与基于数据源1区域1、区域3（图5b、j)分割比较(红框和蓝框区域)，都能很好地区分出梯田边缘，但在绿框区域，基于数据源2的分割处于欠分割状态。而且区域2（图 $5 \mathrm { g }$ ）分割结果较差，边缘模糊难辨。分割效果差异原因：在光谱差异不明显的梯田边缘区域，地形指数信息却有很好的可分性，能良好地为梯田分割提供数据支持，但是从区域2的地形指数（图4、S2、PC2、

AC2、HS2、TR2）分析来看，区域2（图5g）的梯田由于田面过窄，高度不足（红框和篮框）等原因，地形指数已经不能充分表达梯田信息。也可对比绿框（图5，j，k）区域分析，发现对于平坦的田面，当好几块田处于同一个平面，虽然光谱差异大，但地形指数的可区分行就相对较弱。

c）基于数据源3（图5d、h、1）的分割。在区域1\~3的红框和篮框中，分割结果边缘清晰可见，将基于数据源1和数据源2的优势结合，充分地得到相对较为接近真值图的分割结果。

# 2.3.2监督分类

1）分类特征提取对多尺度分割后的对象进行特征提取，分别求对象的R，G，B，S，PC，AC，HS，TR等各个波段的特征。随机选取梯田与非梯田样本，尽量使样本保持平衡。对于基于数据源1，数据源2的分类，对其各个波段进行特征计算（表2)，然后参与分类。但是对数据源3，由于特征数量过多、数据冗余，需要进行特征优化。统计样本的特征，筛选出能区别梯田与非梯田较为明显的特征信息，制作箱线图(图6)。结果表明，R波段的均值（MeanR)，S波段的均值（MeanS），G，B，TR，HS 波段的标准差（StandarddeviationG，B，TR，HS），S波段的纹理特征（GLCMcorrelationsS，GLCMhomogeneityS，GLCMdeviationS）区分度较大，适合作为分类特征参数。

![](images/a68ccc1e107f29cc0d3983d29418cd323ceba274d9bbe9755dc1668d66027d27.jpg)  
图6多尺度分割对象的特征信息

2）分类与评价本文首先基于区域一的三种数据源进行KNN，SVM，CART的监督分类研究，其中图7是区域一的真值图，图8\~10为分类结果，红色区域为梯田的田面，黄色区域为非梯田区域。分类精度评价如表5所示。

# a）分类结果定性分析如下：

（a）基于数据源1的三种监督分类，在蓝，黑，紫框内区域，都出现错分现象。错分原因：蓝，紫框内区域，在多尺度分割时，因光谱特征与周边对象差异不大而出现欠分割，而黑框区域可能因样本特征的选取不完整或分类方法所致；

（b）基于数据源2的三种监督分类，在黑，紫，绿框内区域出现错分现象。错分原因：由于地形指数差异不明显而导致多尺度分割处于欠分割状态。而其他错分的原因是地形指数特征并没充分表达梯田特征；

(c)基于数据源3的三种监督分类，都不同程度地出现错分现象，其中黑框区域都出现错分现象，图10d内紫框区域，图10d蓝框区域出现错分。错分的原因：分类特征的选取和训练样本的选择差异及分类方法所致。

总结以上分析结果发现，影响分类结果的首要因素是多尺度分割的效果，基于数据源1的多尺度分割，在梯田边缘光谱变化不明显的区域会容易出现欠分割，从而导致分类结果出错；基于数据源2的多尺度分割，在光谱差异很大，但地形指数差异不明显的地方出现欠分割，从而导致分类结果出错；基于数据源3的多尺度分割，参考图5d、h、1，多尺度分割结果都优于基于数据源1、2，但分类结果出现不同程度的差异，是因为监督分类的影响。至此，本文相对充分地验证了，基于数据源3作为梯田的田面提取的数据源最为合适。对于基于三种监督分类的影响，本文基于分类精度评价的结果进行定量分析。

b）分类结果定量分析如下：

对比分析表5中每一种分类方法基于三种数据源的分类精度评价。

（a）从生产者精度和用户精度角度分析。如应用KNN分类方法，基于数据源1分类提取的生产者精度，用户精度分别为0.759，0.908。基于数据源2分类提取的生产者精度，用户精度分别为0.744，0.771。基于数据源3分类提取的生产者精度，用户精度分别为0.776，0.908。显然基于数据源3的分类提取梯田的错分最少。同理分析应用SVM，CART分类方法，基于数据源3分类提取的生产者精度，用户精度几乎都高于基于数据源1，2。

（b）从总体精度和Kappa系数角度分析。如应用KNN的分类方法，基于数据源1提取为梯田的总体精度，Kappa系数分别为0.875，0.730。基于数据源2提取为梯田的总体精度，Kappa系数分别为0.809，0.600。基于数据源3提取为梯田的总体精度，Kappa系数分别为0.887，0.739。显然基于数据源3的提取梯田的分类精度高于基于数据源1、2。同理分析应用SVM、CART分类方法，基于数据源3的总体精度，Kappa系数都高于基于数据源1、2。因此，将正射影像数据与地形指数相结合的梯田的田面提取方案优于单一数据源提取方案。

根据区域1的研究结果，对区域2、3的数据源3进行面向对象分析，多尺度分割结果如图5h、1所示。基于KNN、SVM、CART的三种监督分类结果如图11所示。分类精度评价如表6所示。对比分析表5区域1的基于数据源3的精度评价，KNN分类法总精度和Kappa系数为0.887，0.739；SVM分类法总精度和Kappa系数为0.887,0.765；CART分类法总精度和Kappa系数为0.872，0.732。显然SVM分类法优于KNN法和CART法。同理对比分析表8，区域2、3的基于数据源3的三种分类评价。对于区域2，SVM分类法优于KNN法和CART法。对于区域3，CART分类法优于KNN法和SVM法。

从实验整体结果分析，基于SVM分类法优于基于KNN法和CART法。从算法原理的角度分析，KNN法简单，有效，重新训练的代价较低，但计算量较大。CART法易于理解和解释，能够同时处理数据型和常规型属性。但对于各类别样本数量不一致的数据，在CART当中，信息增益的结果偏向于具有更多数值的特征。SVM法可以解决小样本情况下分类，可以提高泛化性能，解决高维问题，非线性问题。结合本文的数据特点，研究区域的梯田与非梯田样本数量有限，样本特征多样，较为适合基于SVM法进行分类提取。本文最终以SVM的分类结果，对梯田的面积进行了统计，如表7所示。与目视解译获得的面积差距相对较大。其主要原因是基于SVM法的核函数及参数设置的不够合理，同时目视解译存在一定的不可避免的误差也影响着参考数据。

# 福

![](images/4c6ff23da49e2720a693e88dbcfd98e360f0aede043fd3ffe4b07fd864de74cd.jpg)  
图7区域1的真值图

![](images/795a6be05ced4feb68488ebee66b52b082ce0869ed5a9206364a76de6c328c0d.jpg)  
图8区域1的三种数据源的KNN分类对比图

![](images/94d0ed7be94f1e6a698538fc3fc266cbf16fdc6489697e7f15e3d868b888456c.jpg)  
图9区域1的三种数据源的SVM分类对比图

![](images/72d5b752a3a8e520496d9f6f2ebb82bea5c7a8532e564a8d6b6ab67709b318bd.jpg)  
（b）基于数据源1分类

![](images/9c71f03fd8eb6c0e9c405a48a6dfc6fce6f04362facb52a6b47c91cddcf57d15.jpg)  
（d）基于数据源3分类  
（b）基于数据源1分类

![](images/53e17b7da500dc56b9a981cf07f39e6300d1fbe1a4333513278f3c3244068d46.jpg)  
（d）基于数据源3分类  
图10区域1的三种数据源的CART分类对比图

![](images/5a0485e4777802281c89b7883f25e646c75de9b111887beda788967fb3680390.jpg)  
图11区域2、3基于数据源3的监督分类对比图

表5区域1的分类精度评价  

<html><body><table><tr><td colspan="2">分类方法及精度评价</td><td colspan="2">数据源1</td><td colspan="2">数据源2</td><td colspan="2">数据源3</td></tr><tr><td>分类方法</td><td>精度评价</td><td>T</td><td>NT</td><td>T</td><td>NT</td><td>T</td><td>NT</td></tr><tr><td rowspan="4">KNN</td><td>生产者精度</td><td>0.759</td><td>0.95</td><td>0.744</td><td>0.852</td><td>0.776</td><td>0.944</td></tr><tr><td>用户精度</td><td>0.908</td><td>0.859</td><td>0.771</td><td>0.838</td><td>0.908</td><td>0.868</td></tr><tr><td>总精度</td><td>0.875</td><td></td><td>0.809</td><td></td><td>0887</td><td></td></tr><tr><td>Kappa系数</td><td>0.730</td><td></td><td>0.600</td><td></td><td>0.739</td><td></td></tr><tr><td rowspan="5">SVM</td><td>生产者精度</td><td>0.757</td><td>0.935</td><td>0.807</td><td>0.857</td><td>0.876</td><td>0.894</td></tr><tr><td>用户精度</td><td>0.883</td><td>0.894</td><td>0.792</td><td>0.866</td><td>0.848</td><td>0.919</td></tr><tr><td>总精度</td><td></td><td>0.865</td><td></td><td>0.838</td><td></td><td>0.887</td></tr><tr><td>Kappa 系数</td><td></td><td>0.710</td><td></td><td>0.662</td><td></td><td>0.765</td></tr><tr><td>生产者精度</td><td>0.732</td><td>0.954</td><td>0.818</td><td>0.840</td><td>0818</td><td>0.908</td></tr><tr><td rowspan="3">CART</td><td>用户精度</td><td>0.912</td><td>0.854</td><td>0.774</td><td>0.879</td><td>0.858</td><td>0.886</td></tr><tr><td>总精度</td><td></td><td>0.867</td><td></td><td>0.832</td><td></td><td>0.872</td></tr><tr><td>Kappa 系数</td><td></td><td>0.711</td><td></td><td>0.625</td><td></td><td>0.732</td></tr></table></body></html>

表6区域2、3的基于数据源3的分类评价  

<html><body><table><tr><td colspan="2">分类方法及精度评价</td><td colspan="2">区域二</td><td colspan="2">区域三</td></tr><tr><td>分类方法</td><td>精度评价</td><td>T</td><td>NT</td><td>T</td><td>NT</td></tr><tr><td rowspan="5">KNN</td><td>生产精度</td><td>0.870</td><td>0.770</td><td>0.792</td><td>0.834</td></tr><tr><td>用户精度</td><td>0.857</td><td>0.787</td><td>0.853</td><td>0.768</td></tr><tr><td>总精度</td><td>0.829</td><td></td><td>0.811</td><td></td></tr><tr><td>Kappa系数</td><td>0.644</td><td></td><td>0.621</td><td></td></tr><tr><td>生产精度</td><td>0.897</td><td>0.778</td><td>0.761</td><td>0.874</td></tr><tr><td rowspan="5">SVM</td><td>用户精度</td><td>0.854</td><td>0.839</td><td>0.880</td><td>0.807</td></tr><tr><td>总精度</td><td>0.848</td><td></td><td>0.812</td><td></td></tr><tr><td>Kappa系数</td><td></td><td>0.682</td><td></td><td>0.626</td></tr><tr><td>生产精度</td><td>0.770</td><td>0.856</td><td>0.990</td><td>0.775</td></tr><tr><td>用户精度</td><td>0.885</td><td>0.720</td><td>0.832</td><td>0.885</td></tr><tr><td>CART</td><td>总精度</td><td>0.805</td><td></td><td>0.855</td><td></td></tr><tr><td></td><td>Kappa系数</td><td></td><td>0.608</td><td>0.704</td><td></td></tr></table></body></html>

表7区域1\~3的面积统计  

<html><body><table><tr><td>区域</td><td>目视解译面积</td><td>SVM分类面积</td><td>差值</td></tr><tr><td>区域一</td><td>98484.50</td><td>93811.50</td><td>-4673.00</td></tr><tr><td>区域二</td><td>147601.00</td><td>155128.75</td><td>+7527.75</td></tr><tr><td>区域三</td><td>137070.50</td><td>139780.25</td><td>+2709.75</td></tr></table></body></html>

# 3 结束语

本文基于高分辨率无人机正射影像、地形指数和两种数据源的结合的面向对象梯田信息提取。研究表明基于无人机正射影像与地形指数结合的数据，充分利用了影像的光谱、纹理、形状信息、以及地形指数信息，结合SVM分类方法的面向对象提取梯田，精度达到较好的效果。

本文还有许多需要改进之处：a)在基于SVM分类方法的面向对象梯田提取中，参数择优应用GA算法，但是否存在更合理的寻优算法，有待进一步探索;b)本文的样本特征优化只应用了箱线图进行了统计分析，并未探索更为合理的优化方法;c)能否将多种分类方法结合起来使用，即集成机器学习方法，或者应用深度学习等方法进行分析，有待进行进一步探索。

# 参考文献：

[1]张宏鸣，杨勤科，杨江涛，等．梯田区侵蚀地形因子随 DEM 分辨率变 化的特征分析[J]．农业机械学报，2017,48(10):172-179.(Zhang Hongming,Yang Qinke,Yang Jiangtao,et al.Analysis of DEM resolution on erosional terrain characteristics of terrace area [J].Transactions of the Chinese Society of Agricultural Machinery,2017,48 (10): 172-179.)   
[2]Zhang Yi,Shi Mingchang,Zhao Xin，et al. Methods for Automatic identification and extraction of terraces from high spatial resolution satellite data (China-GF-1)[J].International Soil and Water Conservation Research, 2017,5(1): 17-25.   
[3] 赵欣，王晓晶，赵院，等．国产高分一号卫星数据傅里叶变换提取梯田

影像可行性分析 [J]．中国水土保持,2016,(1):63-65.(Zhao Xin,Wang Xiaojing,Zhao Yuan,et al.Feasibilityanalysis on methodologyof terraced extraction by using fourier transform based on domestic hi-resolution remote rensing images ofGF-1 satellite [J]. Soil and Water Conservation In China,2016,(1): 63-65.)

[4] 于浩，刘志红，张晓萍，等．基于傅立叶变换的梯田纹理特征提取[J]. 国土资源遥感,2008,20(2):39-42.(Yu Hao,Liu Zhihong,Zhang Xiaoping, et al.Extraction of terraced fileld texture features based on fourier transformation [J].Remote Sensing for Land& Resources,20o8,20 (2): 39- 42.）   
[5] 张雨果．基于面向对象的遥感影像梯田信息提取研究[D].杨凌：西北 农林科技大学,2016. (Zhang Yuguo.Terrace Information Extraction from remote sensing image based on object-oriented classification method [D]. Yang Ling: Northwest A&FUniversity, 2016. )   
[6] 党恬敏．基于高分影像的黄土高原梯田提取技术研究[D]．杨凌：西北 农林科技大学,2017.(Dang Shumin.Discriminating technology of the terraceinloessplateau basedon gaofensaltellite imagery[D].Yangling Northwest A&F University,2017.)   
[7]Eckert S,Tesfay G S,Hurni H,et al. Identification and classification of structural soil conservation measures based on very high resolution stereo satellite data[J].JEnviron Manage,2017,193 (592-606).   
[8]Zhao Hanqing,Fang Xuan, Ding Hu,et al. Extraction of terraces on the loess plateau from high-resolution DEMs and imagery utilizing object-based image analysis [J].ISPRS International Journal of Geo-Information,2017, 6 (6): 157.   
[9]Diaz-Varela R A,Zarco-Tejada PJ,Angileri V,et al. Automatic identification of agricultural terraces through object-oriented analysis of very high resolution dsms and multispectral imagery obtained from an unmanned aerial vehicle [J]. Journal of Environmental Management,2014, 134: 117-126.   
[10] Hu Zhongwen,LiQingquan, ZhangQian,etal. Unsupervised simplification of image hierarchies via evolution analysis in scale-sets framework [J]. IEEE TransonImage Processing,2017,26 (5): 2394-247.   
[11] Hu Zhongwen,Li Qingquan, Zou Qin,etal.ABilevel scale-sets model for hierarchical representation of large remote sensing images [J]. IEEE Trans on Geoscience and Remote Sensing,2016,54 (12): 7366-7377.   
[12]国家测绘局西安标准化测绘研究所起草.1:5001:10001:2000地形图 航空摄影测量内业规范[M].西安：测绘出版社,1988   
[13] Jaspers Cornelis A.M. Histogram equalization: US,6741736 [P//OL].2004- 2000-02-01].   
[14] Pizer S M,Amburn EP,AustinJD,et al.Adaptive histogram equalization and its variations [J]. Computer Vision Graphics & Image Processing,1987, 39 (3): 355-368.   
[15] Zuiderveld K.Contrast limited adaptive histogram equalization [M]. Academic PressProfessional,Inc.,994

[16] Principal component analysis [J].Chemometrics & Intelligent Laboratory

Systems,1987,2(1): 37-52.   
[17]郭建聪，李培军，肖晓柏．一种高分辨率多光谱图像的多尺度分割方法 [J]．北京大学学报：自然科学版,2009,45(2):306-310.(Guo Jiancong,Li Peijun, Xiao Xiaobai. A hierarchical segmentation method for multispectral imagery [J].Acta Scientiarum Naturalium Universitatis Pekinensis,2009, 45 (2): 306-310.)   
[18]王晓峰．水平集方法及其在图像分割中的应用研究[D].合肥：中国科 学技术大学,2009.(Wang Xiaofeng. Study of Level Set Methods and Their Application in Image Segmentation. [D]. Hefei: University of Science and Technology of China,2009.）   
[19]周莉莉，姜枫．图像分割方法综述研究[J].计算机应用研究,2017,34 (7):1921-1928.(Zhou Lili, Jiang Feng.A survey on imagesegmentation methods [J].Application Research ofComputers,2017,34(7): 1921-1928.)   
[20]Malik J. Learning a clasification model for segmentation [J]. Proc of ICCV. 2003: 10-17.   
[21] Csillik O.Superpixels: the end of pixels in OBIA.a comparison of stat-ofthe-art superpixel methods for remote sensing data [EB/OL]. (2016-11-22) http://proceedings. utwente. nl/439/1/Csillik-Superpixels-92. pdf.   
[22] Crommelinck S,Bennett R,Gerke M,et al.SLIC superpixels for object delineation from UAV data [EB/OL]. (2017-09-16). htp:/uavg17. ipb.unibonn.de/wp-content/papercite-data/pdf/crommelinck2017uavg. pdf   
[23] Achanta R, Shaji A,Smith K,et al.SLIC superpixels compared to state-ofthe-art superpixel methods [J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2012,34 (11): 2274-282.   
[24] Van Den Bergh M,Boix X,Roig G,et al. SEEDS: superpixels extracted via energy-driven sampling [C]// Proc of European Conference on Computer Vision. 2012: 13-26.   
[25] Li Zhengqin,Chen Jiansheng. Superpixel segmentation using linear spectral clustering [Cl//Proc of International Conference on Computer Vision and Pattern Recognition. 2015: 1356-1363.   
[26] Mean_Shift:a robust approach toward feature space analysis[J]. IEEE Trans on Pattern Analysis & Machine Intellgence,200,24 (5): 603-619.   
[27] Gao Hai, Xue Ping,Lin Weisi.A New Marker-Based Watershed Algorithm [J].Acta Electronica Sinica,206,2(11): I-81-84 Vol.82.   
[28] Felzenszwalb Pedro F.，Huttenlocher Daniel P.Efficient Graph-Based Image Segmentation [J]. International Journal ofComputer Vision,2004,59 (2): 167-181.   
[29] Baatz Martin,Schape A.An optimization approach for high quality multiscale image segmentation [C]// Proc of Beiträge Zum AGIT-Symposium. 2000: 12-23.   
[30]王志华，孟樊，杨晓梅，等．高空间分辨率遥感影像分割尺度参数自动 选择研究[J].地球信息科学学报,2016,18(5):639-648.(Wang Zhihua, Meng Fan, Yang Xiaomei,et al.A study on the automatic selection of segmentation scale parameters for high spatial resolution remote sensing images.[J].Journal ofGeoinformation,2016,18 (5): 639-648.)   
[31] Cortes C. Vapnik V. Support-vector networks [J]. Machine Learning,1995,

20 (3): 273-297.

[32]BreimanLI,FriedmanJH, OlshenRA,et al.Classificationand regression trees (CART)[J].Encyclopedia of Ecology,1984,40 (3): 582-588.   
[33]张森，陈健飞，龚建周．面向对象分类的决策树方法探讨一一以 Landsat-8OLI 为例[J].测绘科学,2016,41(6):117-121.(Zhang Sen, Chen Jianfei, Gong Jianzhou. Object-oriented classification based on C5. 0 algorithm.[J]. Science of Surveying and Mapping,2016,41(6):117-121.)   
[34]孙华，林辉，莫登奎，等．面向对象的决策树分类技术[J]．中南林业 科技大学学报,2007,27(4):39-43.(Sun Hua,Lin Hui,Mo Dengkui,et al. Technology of object-oriented decision tree cassification [J].Journal of Central South Forestry University,2007,27(4):39-43.)

[35] Stehman Stephen V. Selecting and interpreting measures of thematic

classification accuracy [J].Remote Sensing of Environment,1997,62(77- 89).   
[36]Richards John A.Classifier Performance and Map Accuracy [J].Remote Sensing of Environment,1996,57:161-166.   
[37] Congalton Russell G.AReview ofAssessing the Accuracy ofClassifications ofRemotely Sensed Data [J].Remote Sensing of Environment,1991,37: 35-46.   
[38] Story M.Accuracy Assessment:a User's Perspective [J].Photogrammetric Engineering& Remote Sensing,1986,52(3):397-399.   
[39] Chmura Kraemer H,Periyakoil V.S.，Noda A.Kappa Coefficients in Medical Research [J]. Statistics in Medicine,2002,21 (14):2109.