# 面向对象分割与混合像元分解相结合提取沙化土地信息

滑永春'，李增元²，高志海²(1.内蒙古农业大学林学院,内蒙古 呼和浩特010011；2.中国林业科学研究院资源信息研究所,北京100091)

摘要：以甘肃省民勤县作为研究区域，使用了3景Landsat 8OLI数据进行民勤县沙地信息的提取,提出了一种混合像元分解(FCLSU)和面向对象图像分割技术相结合的新方法。该方法不仅实现了沙地、盐碱地和裸土的分类识别,还实现了流动沙地、半固定沙地和固定沙地的定量区分,新方法总体沙地分类精度为 $8 7 . 2 3 \%$ ，高于面向对象图像分类的 $8 4 . 8 2 \%$ ,在沙地定量划分中新方法有着更为明显的优势。

关键词：沙地分类；定量；混合像元分解；面向对象多边形分割

沙化土地是指在各种气候条件下，由于自然和人为因素形成的地表呈现以沙物质为主要标志的退化土地，具有这种明显特征的退化土地为沙化土地[]。土地沙化不仅导致生态环境的恶化,还造成巨大的经济损失。开展沙化监测和评价是一项十分必要的工作。

传统的沙化土地调查是以野外路线的踏勘，以及样地测定等方法为主要手段，获取典型地点的土地沙化数据，根据地面上一定数据的特征在地形图或其他工作底图上进行勾绘图斑，最终形成一个地区的沙化土地类型分布状况图表。但是受到时间、经费、交通、人为主观等因素的限制，大部分的样点、样方沿河谷和公路进行设置，数量比较有限且分布不均匀，从而很难准确地获取不同沙化类型的边界。

总的来看，以遥感手段调查土地沙化与动态变化，可有效地提高沙化土地监测的及时性和准确性。目前，多光谱、高光谱、超光谱和雷达数据，不同空间和时间分辨率遥感影像在沙化信息提取中都得到大量的研究应用[2]。基于遥感沙化信息提取主要包含：植被信息的提取、沙化土地分类、沙化土地土壤特征参量的反演。其中植被的提取主要涉及的方法有植被指数法[3-5]、混合像元分解法[6-9]、人工神经网络法[10-1]等;沙化土地分类主要有基于像元图像分类[12-13]、面向对象图像分类[14-15]以及混合像元分解法等;沙化土地土壤特征参量提取主要是对土壤质地、有机质含量、土壤粒径组成、湿度、氮磷钾元素含量等特性的定量反演[17-20]。其中，土壤粒径组成参量是反映沙化土地土壤状况的最佳指示因子，它对土壤是否发生了沙化现象和沙化程度的评价具有至关重要的作用[2]。尽管遥感数据源和研究手段已经呈现多样化，但对沙地定量化提取仍然是一个热点和难点问题。民勤县处于干旱地区，植被利用常规的植被指数等方法难以提取出来，在加上地类比较复杂，沙地和盐碱地、裸土地,流动沙地、半固定沙地和固定沙地难以定量区分。因此，本文提出了一种混合像元分解和面向对象多边形分割相结合的方法，可以实现难区分地类的定量划分。

# 1研究区与数据预处理

研究区甘肃民勤县位于河西走廊东北部、石羊河流域下游，西接巴丹吉林沙漠(图1)，东邻腾格里沙漠，土地总面积约 $1 . 6 0 \times 1 0 ^ { 6 } \mathrm { h m } ^ { 2 }$ ,其中，沙漠、戈壁面积约占 $8 5 \%$ 。全县由沙漠、戈壁、剥蚀山地和绿洲平原4种地理景观组成，大部分被流动、固定和半固定沙丘组成的腾格里和巴丹吉林两大沙漠覆盖，剥蚀山地主要位于北部与内蒙古的接壤地区，戈壁则分布于山麓地带。试验区的自然植被主要包含白刺（Nitraria schoberi）泡泡刺(Nitrariasphaerocar-pa）、珍珠（Phyllanthusurinaria）、红砂（Hololachnesoongarica）膜果麻黄（Ephedraprzewalskii）骆驼刺(Alhagi sparsifolia)和沙蒿(Artemisia desertorum）等，人工植被主要为梭梭林（Haloxylonammodendron）、沙枣(Elaeagnus angustifolia)和花棒(Hedysarum sco-parium)等。

遥感数据为3景覆盖研究区的Landsat8OLI无云影像，1景成像于2014年8月18日，2景成像于2014年8月27日。预处理包括波段合成、大气辐射校正、几何校正、图像的拼接和剪切等(图1)。同时，2014年8月11—31日调查了170个植被和土地利用样地点的数据;并利用ASDFieldSpec Pro 波谱仪测定了民勤县内主要植被和土地类型的光谱（图2）。

![](images/6741204048e7c508516d9edb645a1ae992b267fff8d7d201d1208f391958ca74.jpg)  
图1研究区及采样点位置示意图

# 2研究方法

本文的沙化土地利用和覆盖分类体系是依据《第四次全国荒漠化和沙化监测技术规定》2并结合了民勤的实际地类，最后确定了山体、水体、耕地、戈壁、沙地(流动沙地、半固定沙地、固定沙地）、盐碱地、裸土和其他等。根据各种地类的特点，将分为三步实现沙化土地的分类：

第一步：将山体、水体、耕地、戈壁易分类的地类，利用面向对象的方法进行分类并进行掩膜处理；

第二步：然后利用混合像元分解和面向对象多尺度分割相结合的方法，实现沙地、盐碱地、裸土界线模糊地类的定量区划;

第三步：利用混合像元分解植被分量实现沙地（流动沙地、半固定沙地、固定沙地)的定量化区分。

# 2.1影像分割及面向对象分类

遥感图像分割算法主要有三类[23]，即阈值化分割法、边缘分割法和区域分割法。为了提高遥感图像分割的质量和自动化程度，前人探索了多尺度分割、函数插值等多种方法[24-27],但实际应用中由于分割影像和地类差异，很难找到一种自动计算分割参数的切实可行方法。本文选取多尺度分割算法对Landsat8OLI影像的7个波段进行分割，经过对分割效果的反复目视对比，最终确定了各地类的分割尺度、形状和紧致度因子的大小(表1)。

![](images/f01858dd5a6749206c183c19394a849bde945ab4970d0e50e155ea2829a70e46.jpg)  
Fig.1 Location of study area and sampling points   
图2民勤县内主要的植被和土地类型的光谱曲线  
Fig.2 Spectral curve of typical desert vegetation and land use types in study region

# 表1民勤县土地利用类型尺度分割参数

Tab.1 Scale segmentation parameter of land use type in Minqin county   

<html><body><table><tr><td>土地利用类型</td><td>形状因子</td><td>紧致度</td><td>分割尺度</td></tr><tr><td>山体、戈壁</td><td>0.3</td><td>0.7</td><td>300</td></tr><tr><td>沙地 耕地、其他</td><td>0.3</td><td>0.7</td><td>100</td></tr><tr><td>盐碱地、裸土地</td><td>0.1</td><td>0.9</td><td>50</td></tr><tr><td>水体</td><td>0.4</td><td>0.7</td><td>20</td></tr></table></body></html>

面向对象分类方法有分类回归树(classificationandregressiontree,CART)，贝叶斯(BAYES),K最近邻( $\mathrm { K } -$ nearestneighbour,KNN）和支持向量（supportvectormachine,SVM)等。本文选择SVM分类算法对山体、水体、耕地、戈壁地类进行分类,其中径向基函数(RBF）、核函数惩罚参数(C)和间隔参数(g)分别设置为100和0.15。

# 2.2FCLSU混合像元分解

李晓松[5在甘肃民勤利用Hyperion影像对比分析了植被指数、偏最小二乘回归法、人工神经网络法和混合像元分解法反演稀疏植被覆盖度的能力，发现混合像元分解法尤其全受限的最小二乘法线性分解（fully constrained least-squares based linear un-mixing,FCLSU)对稀疏植被提取效果最好。Ji等[28]利用线性光谱混合模型、核函数非线性光谱混合模型和双线性光谱混合模型对民勤白刺进行提取，发现核函数非线性光谱混合模型相较于线性光谱混合模型在提取白刺信息上没有明显的优势。因此本文选择相对成熟、易操作的FCLSU线性混合像元分解模型来提取民勤的稀疏植被信息。其主要算法如下[29]：

$$
X _ { i } = \sum _ { j = 1 } ^ { n } f _ { j } X _ { i j } + \pmb { \varepsilon } _ { i } \quad i = 1 , 2 , \cdots , L ; j = 1 , 2 , . . . , p
$$

或 $D _ { \scriptscriptstyle N } = M \alpha + E$

$$
\sum _ { j = 1 } ^ { n } f _ { j } = 1 , \quad 0 \leqslant f _ { j } \leqslant 1
$$

$$
J = \frac { 1 } { 2 } ( M \alpha - D _ { _ { N } } ) ^ { T } ( M \alpha - D _ { _ { N } } ) + \lambda ( \alpha - c )
$$

式中： $X _ { i }$ 是 $i$ 波段的像元光谱反射率； $n$ 为端元数目 $; f _ { j }$ 是端元j在像元内所占比重； $X _ { i j }$ 是第 $i$ 波段 $j$ 端元的像 元反射率； $\ \varepsilon _ { i }$ 是第 $i$ 波段误差项。 $D _ { \scriptscriptstyle { N } }$ 为 $L { \times } 1$ 的像元 灰度值列向量; $M$ 为 $L { \times } _ { p }$ 的像元端元灰度值矩阵; $\alpha$ 为 $p { \times } 1$ 的像元内端元所占比例列向量; $E$ 为误差向 量。 $J$ 为拉格朗日函数。 $\mid c \mid$ 为未知的 $p$ 维非负的约 束常量向量。

本研究选用FCLSU方法，利用外业测定的光谱曲线最后确定了稀疏植被、沙地、盐碱地、裸土4个分解端元，由图3可以看出，所测稀疏植被类型比较多，植被光谱反射率与植被长势和覆盖度等有直接的关系，但总体植被光谱反射率在各波长曲线上规律基本一致，由于影像上稀疏植被混合像元的影像，在影像上很难直接提取稀疏植被端元，因此，植被端元光谱反射率是所有实测植被光谱的平均值来作为植被端元值。沙地光谱反射率在各波长值是细沙反射率大于粗沙，逆风坡沙反射率大于背风坡沙，曲线规律也比较一致，沙地端元用实测沙地光谱的平均值代替。同样裸土端元值是由裸土、洼地结皮土的平均值确定。而盐碱地比较特殊，轻度盐碱地和重度盐碱地反射率差别很大，因此盐碱地分为轻度盐碱地端元和重度盐碱地端元，分别进行分解，最后合并为盐碱地。具体实现过程为：首先把实测的各端元光谱平均值数据利用ENVI的光谱库建立工具(spectral librarybuilder)形成一个ENVI格式的(.sil)的光谱数据库；然后再利用光谱库重采样工具(spectral library resampling)将实测光谱采样成和Landsat8OLI中心波长对应的7个波段光谱数据；最后使用FCLSU混合像元分解模型实现了各端元的分解(图3)。

# 2.3沙化土地类型划分

民勤县地处干旱地区，地类比较复杂，沙地和盐碱地、裸土地，流动沙地、半固定沙地和固定沙地难以区分，应用传统的分类方法只能做到定性划分，由于分类样本选取的不确定性，很难做到准确的分类结果。本文将选用混合像元分解和面向对象多边形分割相结合的方法，实现沙化土地类型的定量区划。

![](images/de42a74b12570968735a1c064e8a43ba3aeb855e532263314368824c9ad9e919.jpg)  
图3FCLSU分解各分量  
Fig.3Each component of FCLSU decomposition

首先，在多尺度分割多边形内计算沙地、盐碱地、裸土各FCLSU分量的均值并进行比较，最大值对应的地类就是该多边形最终确定的地类，通过该方法实现沙地、盐碱地、裸土的定量区划;根据沙地(流动沙地、半固定沙地、固定沙地)定义，对植被FCLSU分量进行密度分割，植被盖度在0\~0.1确定为流动沙地、0.1\~0.3为半固定沙地、0.3\~1.0为固定沙地(图4)。

# 2.4精度验证

2.4.1均方根误差（RMSE）采用均方根误差来评 价稀疏植被提取的估算值与实际测量值的偏移度。

$$
{ \mathrm { R M S E } } = { \sqrt { \left( \sum _ { i = 1 } ^ { n } { \bigl ( } X _ { \mathrm { o b s } , i } - X _ { \mathrm { m o d e l } , i } { \bigr ) } \right) ^ { 2 } \int n } }
$$

式中： $X _ { \mathrm { o b s } , i }$ 实际测量值; $X _ { \mathrm { m o d e l } , i }$ 为模型反演值； $n$ 为对应验证样方数。

2.4.2沙化土地分类精度验证指标选取采用混淆矩阵(confusionmatrix)方法进行沙化土地分类精度验证，其主要的指标有总体分类精度(overallaccuracy）、Kappa系数（Kappacoefficient）、制图精度（producer'saccuracy）用户精度(user'saccuracy）进行精度评价。总体分类精度表示所有样本中被正确分类的样本比例;Kappa系数能够表征分类结果与数据的吻合度，利用多元离散分析方法，使误差矩阵中的所有因素参与评价更加准确地反映了整体的分类精度；制图精度是指某类正确分类个数与该类真实参考总数的比率；用户精度是指正确分到某类的个数与分类器分为某类的总数的比率。

# 3结果分析

# 3.1稀疏植被精度验证

植被盖度提取的精确程度直接决定着沙地类型的划分，为了验证FCLSU方法对稀疏植被覆盖度提取的准确度，利用外业120个实测植被调查样点数据进行线性回归分析(图5），结果表明FCLSU方法能够很好地提取稀疏植被， $R ^ { 2 }$ 达到0.80,RMSE为4.88。说明利用FCLSU分解的植被分量可以较好地反映真实的稀疏植被覆盖度。

# 3.2沙化土地分类结果及精度验证

为了比较新方法对沙地信息提取效果，我们做了面向对象和混合像元分解结合图像分割两种分类，最终的分类结果见图6。同时，利用外业调查的数据对分类结果进行精度验证(表2)，可以看到面向对象图像分类总体精度在 $8 4 . 8 6 \%$ ,Kappa系数0.82,而新方法总体精度在 $8 6 . 6 0 \%$ ,Kappa系数$0 . 8 4$ 。本研究的重点是不同类型沙地高精度的提取，在新方法中流动沙地制图精度可以达到$9 1 . 4 3 \%$ ，用户精度高达 $9 0 . 6 9 \%$ ，高于面向对象图像分类的 $8 5 . 2 4 \%$ 和 $8 7 . 6 5 \%$ 。流动沙地是沙地分类中精度最高的，主要原因是民勤境内分布着大量容易分类提取的几乎无植被的流动沙地。新方法半固定沙地制图精度为 $8 3 . 5 8 \%$ ,用户精度为 $78 . 8 7 \%$ ，而面向对象图像分类为 $8 2 . 6 8 \%$ 和 $7 6 . 5 9 \%$ 。半固定沙地是沙地分类精度最低的，其主要原因是稀疏植被提取需要准确界定0.1和0.3边界植被覆盖度，准确提取半固定沙地难度比较大。固定沙地提取精度介于流动和半固定沙地之间，在新方法中制图精度为 $8 6 . 6 7 \%$ ,用户精度为 $8 8 . 1 4 \%$ ,高于面向对象图像分类的 $8 6 . 5 3 \%$ 和 $8 8 . 0 1 \%$ 。新方法总体沙地分类精度为 $8 7 . 2 3 \%$ ，高于面向对象图像分类的 $8 4 . 8 2 \%$ ，在沙地定量划分中更有优势。

![](images/5aa3d734167bef41f469b9dda9144cf1a70ef839d2a81d288e7e10b31bf618fe.jpg)  
图4FCLSU $^ +$ 图像分割沙地定量分类原理  
Fig.4The principle of sand quantitative classification using FCLSU $^ +$ image segmentation

![](images/a115772b2234f5be3cc6b6be9c2f244feefbc13c103a20e6a681d9ac1eb3554d.jpg)  
图5FCLSU算法估测值与实际植被覆盖度线性回归分析 Fig.5Scatter plot between FCLSU-based sparse vegetation fraction and observed vegetation cover

# 4结论与讨论

一般情况下沙地分类是根据影像的地类解译标志，采用基于像元或面向对象等方法进行分类，在干旱区遥感影像稀疏植被在混合像元的作用下，信息占比比较小，解译标志的建立有很大的不确定性。所以，对于沙地分类很难做到严格按照沙化分类定量标准执行，如流动沙地（植被覆盖度在 $10 \%$ 以下）、半固定沙地(植被覆盖度在 $1 0 \% { \sim } 3 0 \%$ )和固定沙地(植被覆盖度在 $3 0 \%$ 以上）。本文利用混合像元分解结合面向对象分割技术，实现了沙化地类的定量化提取。主要结论和存在问题有以下六点：

![](images/cf5c8a885f81d4dcc0a07ac2d02071c4d0f59b3b4fb934646680e6b31aa70a86.jpg)  
图6不同方法图像分类结果  
Fig.6Image classification results of different methods

表2不同图像分类精度评价  
Tab.2 Accuracy evaluation of different imageclassification   

<html><body><table><tr><td rowspan="2">土地类型</td><td colspan="4">面向对象</td><td colspan="4">混合像元+面向对象图像分割</td></tr><tr><td>制图精度/%</td><td>用户精度/%</td><td>总体精度/%</td><td>Kappa系数</td><td>制图精度/%</td><td>用户精度/%</td><td>总体精度/%</td><td>Kappa系数</td></tr><tr><td>山体</td><td>85.71</td><td>85.71</td><td></td><td></td><td>85.71</td><td>85.71</td><td></td><td></td></tr><tr><td>水体</td><td>95.24</td><td>90.91</td><td></td><td></td><td>95.24</td><td>90.91</td><td></td><td></td></tr><tr><td>耕地</td><td>92.31</td><td>82.76</td><td></td><td></td><td>92.31</td><td>82.76</td><td></td><td></td></tr><tr><td>戈壁</td><td>75.68</td><td>82.35</td><td></td><td></td><td>75.68</td><td>82.35</td><td></td><td></td></tr><tr><td>裸土地</td><td>81.11</td><td>92.41</td><td>84.86</td><td></td><td>81.11</td><td>92.41</td><td>86.6</td><td>0.84</td></tr><tr><td>盐碱地</td><td>83.05</td><td>74.24</td><td></td><td>0.82</td><td>83.05</td><td>74.24</td><td></td><td></td></tr><tr><td>流动沙地</td><td>85.24</td><td>87.65</td><td></td><td></td><td>91.43</td><td>90.69</td><td></td><td></td></tr><tr><td>半固定沙地</td><td>82.68</td><td>76.59</td><td></td><td></td><td>83.58</td><td>78.87</td><td></td><td></td></tr><tr><td>固定沙地</td><td>86.53</td><td>88.01</td><td></td><td></td><td>86.67</td><td>88.14</td><td></td><td></td></tr><tr><td>其他</td><td>78.57</td><td>89.19</td><td></td><td></td><td>78.57</td><td>89.19</td><td></td><td></td></tr></table></body></html>

(1）沙化土地分类的尺度如何确定？实际上沙化土地研究尺度(斑块大小)不一样，沙化土地类型也将得出不同的结论。例如一个白刺包区域，单看一个白刺包为固定沙地,白刺间沙地可以认为是流动沙地，但在更大尺度上看(包含白刺包和白刺间沙地)有可能是一个半固定沙地。本研究利用面向对象多尺度分割技术，通过调整分割参数实现其在遥感尺度上沙化土地最佳分割斑块的划分。

(2）利用全受限的最小二乘法线性法(FCLSU)获取研究区的植被信息，结果表明FCLSU方法能够很好地提取稀疏植被， $R ^ { 2 }$ 达到0.80，RMSE为4.88。说明利用FCLSU分解的植被分量可以较好地反映真实的稀疏植被覆盖度。

(3）新方法对植被覆盖区地类划分有着明显的优势，通常在植被覆盖(尤其是高盖度植被覆盖)的情况下，用传统的图像分类方法只能将其划分为植被类型，而应用本文提出的方法则可以根据地类分解分量的大小，准确判断植被覆盖下地类的类型。

（4）从沙地定量提取精度角度来看，混合像元分解结合面向对象分割提取不同类型沙地的精度要高于面向对象图像分类法。在新方法中流动沙地提取分类精度最高，可以达到 $9 0 \%$ 以上；其次是固定沙地，精度可以达到 $8 6 . 6 7 \%$ ；半固定沙地提取精度最低，为 $8 3 . 5 8 \%$ 。总体分类精度高达 $8 7 . 2 3 \%$ ，高于面向对象图像分类的 $8 4 . 8 2 \%$ ,利用本文提出的方法可以很好地实现沙化土地的定量划分。

(5）利用外业测定的光谱曲线确定了最终混合像元分解端元，但每个端元下面其实又包含很多种亚地类或植被类型，FCLSU分解法端元提取是利用各类分解端元的反射率平均值代替里面具体类型的光谱曲线值，在混合像元分解中有可能存在光谱曲线错误的匹配。为此接下来的研究将尝试采用可变端元混合像元分解法来实现干旱区地类或植被的提取。

(6）在面向对象图像分割方面，本文对沙地采用了同一分割参数，没有充分考虑流动沙地斑块比较大，而固定、半固定沙地的斑块比较小，且紧致度和形状因子也略有不同的特性，在接下来的研究中将进一步细化沙地的分割参数。

参考文献(References):   
[1]国家林业局.全国荒漠化监测主要技术规定[R].北京.国家林 业局,1998.[State Forestry Administration.The National Desertification Monitoring Technical Regulations[R]. Beijing: State Forestry Administration,1998.]   
[2]吴见,彭道黎.土地沙化遥感信息提取技术研究进展[J].世界林 业研究,2009,22(4): 47-52.[Wu Jian,Peng Daoli. Research advances in remote sensing monitoring technology for desertification [J]. World Forestry Research,2009,22(4): 47-52.]   
[3]杨怡,吴世新,庄庆威,等.2000—2018年古尔班通古特沙漠 EVI时空变化特征[J].干旱区研究,2019,36(6):1512-1520. [Yang Yi, WuShixin, Zhuang Qingwei, etal.Spatiotemporange of EVI in the Gurbantunggut Desert from 200O to 2018[J].Arid Zone Research,2019,36(6): 1512-1520.]   
[4]滑永春,李增元,高志海.2001年以来甘肃民勤植被覆盖变化 分析[J].干旱区研究,2017,34(2):337-343.[Hua Yongchun,Li Zengyuan, Gao Zhihai. Variation of vegetation coverage in Minqin County since 2001[J]. Arid Zone Research,2017,34(2): 337-34.]   
[5]李晓松.干旱地区稀疏植被覆盖度高光谱遥感定量反演研究 [D].北京:中国林业科学研究院,2008.[Li Xiaosong.Qualitative Retrieval of Sparse Vegetation Cover in Arid Regions Using Hyperspectral Data[D]. Beijing: Chinese Academy of Forestry, 2008.]   
[6]Ballantine JAC,Okin GS,PrentissDE,et al. Mapping North Africanlandforms using continental scale unmixing of MODIS iagery[J]. Remote Sensing of Environment,2005,97(4): 470-483.   
[7]Fan W, Hu B, Miller J,et al. Comparative study between a new nonlinear model and common linear model for analysing laboratory simulated-forest hyperspectral data[J]. International Journal of Remote Sensing, 2009,30(11): 2951-2962.   
[8]Somers B,Cools K,Delalieux S,et al. Nonlinear hyperspectral mixture analysis for tree cover estimates in Orchards[J]. Remote Sensing of Environment,2009,113(6): 1183-1193.   
[9]姬翠翠,贾永红,李晓松,等.线性/非线性光谱混合模型估算白 刺灌丛植被覆盖度[J].遥感学报,2016,20(6):1402-1412.[Ji Cuicui, Jia Yonghong,Li Xiaosong,et al. Research on linear and nonlinear spectral mixture models for estimating vegetation fractional cover of Nitraria bushes [J]. Journal of Remote Sensing, 2016,20(6): 1402-1412.]   
[10] 陈涛,牛瑞卿,李平湘,等.基于人工神经网络的植被覆盖遥感 反演方法研究[J].遥感技术与应用,2010(1):24-30.[Chen Tao, Niu Ruiqing,Li Pingxiang,et al.An artificial neural network method for vegetation cover retrieval with“Beijing-1”microsatelite data[J]. Remote Sensing Technology and Application,2010 (1): 24-30.]   
[11]Silva Junior C A,Nanni M R,Teodoro PE,et al. Comparison of mapping soybean areas in Brazil through perceptron neural networks and vegetation indices[J].African Journal of Agricultural Research,2016,11(43): 4413-4424.   
[12]龙晶.沙化土地遥感评价方法[J].国土资源遥感,2005,17(1): 17-19.[Long Jing. The application of remote sensing technique to sandy desertification assessment[J]. Remote Sensing for Land and Resources,2005,17(1): 17 -19.]   
[13]Liu B,Coulthard T J.Mapping the interactions between rivers and sand dunes: Implications for fluvial and aeolian geomorphology[J]. Geomorphology,2015,231: 246-257.   
[14] 王志波.基于面向对象方法的土地沙化遥感信息提取技术研究 [D].北京:中国林业科学研究院,2012.[Wang Zhibo.Extraction of Sandy Land Information Based on Object-Oriented Method from Remote Sensing Data[D]. Beijing: Chinese Academy of Forestry,2012.]   
[15]Wahidin N, Siregar V P,Nababan B,et al. Object-based image analysis for coral reef benthic habitat mapping with several classification algorithms[J]. Procedia Environmental Sciences,2015,24: 222-227.   
[16] 李晓琴,张振德,张佩民.格尔木土地荒漠化遥感动态监测研究 [J].国土资源遥 感,2006,18(2):61-63.[Li Xiaoqin,Zhang Zhende, Zhang Peimin. Remote sensing survey and monitoring of desertification in Golmud Area[J].Remote Sensing for Land and Resources,2006,18(2): 61-63.]   
[17]Wu C Y,Jacobson A R,Laba M,et al.Accounting for surface roughness effects in the near-infrared reflectance sensing of soils [J].Geoderma,2009,152(1-2): 171-180.   
[18]Montzka C,Moradkhani H,Weihermuller L,et al.Hydraulic parameter estimation by remotely-sensed top soil moisture observations with the particle filter[J]. Journal of Hydrology,2011,399(3- 4): 410-421.   
[19]Curcio D,Ciraolo G,D'Asaro F,et al. Prediction of soil texture distributions using VNIR-SWIR reflectance spectroscopy[J]. Procedia Environmental Sciences,2013,19: 494-503.   
[20]Lu P,Wang L,Niu Z,et al. Prediction of soil properties using laboratory VIS-NIR spectroscopy and Hyperion imagery[J]. Journal of Geochemical Exploration,2013,132:26-33.   
[21] 吴俊君.基于BJ-1多光谱数据的土地沙化信息定量提取技术 研究[D].北京:中国林业科学研究院,2012.[Wu Junjun. Quantitative Extraction of Land Sandification Information Using BJ-1 Multispectral Data[D]. Beijing: Chinese Academy of Forestry,2012.]   
[22]国家林业局.中国荒漠化和沙化状况公报[R].北京:国家林业 局,2011.[State Forestry Administration.A Bulletin of Status Que of Desertification and Sandification in China[R].Beijing: State Forestry Administration, 2011.]   
[23]Haralick R, Shaprio L G.Image segmentation technique[J]. Computer Vision Graphics and Image Processing,1985,12:100-132.   
[24]Johnson Brain,Xie Zhixiao.Unsupervised image segmentation evaluation and refinement using a multi-scale approach [J]. International Society for Photogrammetry and Remote Sensing,2011,2 (6): 473-483.   
[25] Song Y,Wu Y,Dai Y.A new active contour remote sensing river image segmentation algorithm inspired from the cross entropy[J]. Digital Signal Processing,2016,48: 322-332.   
[26] Su T, Zhang S.Local and global evaluation for remote sensing image segmentation[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2017,130: 256-276.   
[27]徐二静.基于K-means 的遥感图像分割[D].乌鲁木齐:新疆大 学,2014.[Xu Erjing.Remote Sensing Image Segmentation Based on K-means[D]. Urumqi: Xinjiang University,2014.]   
[28]Ji C,Jia Y,Gao Z,et al.Nonlinear spectral mixture effects for photosynthetic/non- photosynthetic vegetation cover estimates of typical desert vegetation in Western China[J]. PloS One,2017,12(12): e0189292.   
[29] Chang C I,Heinz D C. Constrained subpixel target detection for remotely sensed imagery[J]. IEEE Transactions on Geoscience and Remote Sensing,2000,38(3): 1144-1159.

# Extraction of sand information using object-oriented segmentation combined with the decomposition of mixed pixels

HUA Yong-chun'， LI Zeng-yuan², GAO Zhi-hai² (1.Forestry CollegeofInner Mongolia Agricultural University,Hohhot Olool1,Inner Mongolia,China; 2.Research Institute of Resource Information,Chinese Academy ofForestry,Beijing 10oo91,China)

Abstract: With three Landsat 8OLI images of the Minqin County,Gansu Province,we proposed a new method combining the decompositionof mixed pixels (FCLSU) and object-oriented polygonsegmentation to quantitatively extractsandinformation.Itnotonlyrealized theclassificationofthesand,saline-alkali land,andbare soilbutalso distinguished theshiftingsandy land,semifixedsandy land,and fixedsandylandquantificationally.Theoverall sand classification accuracy of the new method is $8 7 . 2 3 \%$ , which is higher than that of the object-oriented image classification, $8 4 . 8 2 \%$ ，showingthatthe new methodcanact moreeffectively than the traditional approach in the quantitative division of sandy land.

Keywords:sand classification;quantitative;decomposition of mixed pixels；object-oriented polygon segmentation