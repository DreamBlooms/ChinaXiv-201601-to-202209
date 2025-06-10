# 基于多尺度支撑域描述子的多光谱图像匹配算法

赵恩波1,2,3,4，史泽林1,3,4，刘云鹏1,3,4

(1．中国科学院沈阳自动化研究所，沈阳 110016;2.中国科学院大学，北京10049;3．中国科学院光电信息处理重点实验室，沈阳110016;4.辽宁省图像理解与视觉计算重点实验室，沈阳110016)

摘要：针对现有多光谱图像匹配算法鲁棒性不强的问题，提出一种新的基于多尺度支撑域描述子的多光谱图像匹配算法。该算法首先提取Harrs 角点作为特征点；然后分别统计特征点不同尺度邻域内的边缘方向直方图，组合构成特征描述子；以欧氏距离为相似度准则，使用比值法获得初始匹配结果；最后提出了一种基于 RANSAC 算法的外点去除算法。实验结果表明，该算法可有效匹配多光谱图像，且与已有算法相比鲁棒性更强，获取的正确匹配对更多。

关键词：多光谱图像匹配；特征描述子；外点去除 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.04.0235

# Multi-spectral image registration algorithm based on multi-scale support region descriptors

Zhao Enbo1,2,3,4, Shi Zelin1,3,4, Liu Yunpeng1, 3, 4 (1.Shenyang InstuteofAutomation,Chinese Academyof Sciences,Shenyang l10o16,China;2.Universityof Chinese AcademyofSciences,Beijing10o49,China;3.KeyLaboratoryofOpto-Electronic InformationProcessng,ChineseAcademy of Sciences,Shenyang0o16,China;4.TheKeyLaboratoryof Image Understanding&Computer Vision,Shenyang0016, China)

Abstract: To improve therobustnessof the existing multi-spectral image registration algorithms,this paper proposed a new algorithmbasedonmulti-scale supportregiondescriptors.Firstly,thealgorithm extractedthe Haris corner pointsas feature points.Secondly,itconstructed thedescriptorbycombiningthe edge direction histogramscalculatedrespectively in the support egionsof diferent sizes around afeature point.Then,thesimilarity criterion was the Euclidean distance,and it obtainedthe initialmatchesbytheratio method.Finall,thispaper proposedanoutlierremovalalgorithmbasedonRANSAC algorithm.The experimentalresultsshow thatthe proposedalgorithmcan match multi-spectral images efectively,be more robust than the existing algorithms,and obtain more matches that are correct.

Key words: multi-spectral image registration; feature point descriptor; eliminating outliers

# 0 引言

多光谱图像被广泛应用于如遥感[1]、视频监控[2]和军事[3]等领域。相对于单光谱图像，多光谱图像可提供多样、可靠、互补的信息。例如可见光图像可提供丰富的细节信息，但受环境条件的影响较大；而红外传感器可全天候工作，受天气等因素的影响较小，但图像的分辨率不高。通过配准并融合两种图像，可将两者的优势综合起来，得到更加丰富、全面、包含更多细节的图像，相对于单光谱图像更有助于实际问题的解决，如电力设备温度实时监控[4]、夜间行驶视野受限的问题[5]。

为了获得多光谱图像间的互补信息，需要将图像配准，而图像的配准需要确定多光谱图像间特征的对应关系。确立对应关系的难点在于如何克服可见光图像与红外图像的像素强度之间的非线性关系。通常红外传感器工作在 $0 . 7 5 \sim 1 5 \mu \mathrm { m }$ 的光谱范围，而可见光传感器工作在大约 $0 . 4 { \sim } 0 . 7 \mu \mathrm { m }$ 的光谱范围。因此，可见光图像中像素强度的变化与物体的颜色和反射的光线有关，而红外图像的像素强度随物体温度的变化而变化，使得两者之间的关系是非线性的。这种非线性关系使得适用于可见光图像匹配的经典算法(如SIFT[]与SURF[7])在匹配红外图像与可见光图像时，匹配效果受到很大限制。

尽管像素强度不同，不同材质之间边界的边缘趋于一致。这是因为不同材质的物体通常具有不同的外观特性(如颜色、形状等)，这些特性决定了哪部分光线被反射及如何反射，导致可见光图像中不同材质处像素强度不同。不同的材质也具有不同的辐射特性，而辐射特性是影响红外图像像素强度的主要因素。简言之，不同的材质具有不同的反射和辐射特性，使得它们在可见光图像和红外图像中都具有不同的像素强度。因此，不同材质之间的边界将存在于多光谱图像的对应位置。这种对应性促使人们充分利用多光谱图像的边缘信息来获得有效的配准方法。

文献 $[ 8 \sim 1 0 ]$ 对由不同类型的传感器采集到的图像匹配问题进行了概述。现有的红外和可见光图像配准算法可以分为基于像素强度的方法和基于特征的方法两类。基于像素强度的方法首先定义一种相似性度量，如平方差的总和、互相关和互信息[1]，测量两个图像块间的距离，后将配准问题转换为两个图像块距离的最小化问题。这类方法不需要对图像进行分割或特征提取等预处理，便于直接应用；但计算复杂度高，且当图像对分辨率不同或重叠率较低时，统计稳定性的假设难以得到保证，使得配准效果下降甚至误匹配。基于特征的方法首先提取特征点和边缘等特征，然后应用匹配度量查找两个图像的相对应的特征，最后根据对应关系计算几何映射关系。这种方法可以有效匹配低重叠的图像对，并能适应较大的几何形变。

考虑到适用性和计算效率，本文着重研究基于特征的方法。Coiras等人[2]首先提取边缘片段，然后将它们分组构成三角形，通过匹配三角形计算变换矩阵。基于直线特征的方法[13,14]利用了图像中的强边缘和梯度信息，在匹配人造场景图像时效果较好，但匹配自然图像时效果不佳，因为自然图像中的直线特征较少。SIFT 的一种改进版本对称-SIFT(symmetric-SIFT)算法[15]利用SIFT算法的思想提取特征点，后利用了多光谱图像中常见的梯度反转现象对特征点描述。构建描述子时，将处于在$1 8 0 ^ { \circ } \ \sim 3 6 0 ^ { \circ }$ 范围内的梯度方向转换到其相反的方向；后参照SIFT算法构建初始描述子，后与其 $1 8 0 ^ { \circ }$ 反转的结果结合构成最终的描述子。这两个过程使算法能够解决部分多光谱图像配准的任务。利用边缘信息的方法还包括HOG(histogram oforiented gradients)[16]、形状上下文[17]、豪斯多夫距离和边缘方向直方图(edge orientationhistogram,EOH)[18]。形状上下文和豪斯多夫距离较适用于边缘像素集可以完整描述对象轮廓的情况，然而很多应用中提取到的对象轮廓不完整。HOG算法统计特征点邻域内每个像素的梯度大小和方向，而红外图像的纹理信息明显减少，因此无须统计每个像素点的梯度信息。EOH算法是SIFT 算法的另一种改进版本，描述了特征点邻域内的边缘分布而不是梯度分布。相较于其他方法，该方法没有明显的应用局限，既能够匹配人造场景图像，也能够匹配自然场景图像，但存在正确匹配对数量少的问题。针对这一问题，本文提出了基于多尺度支撑域描述子的多光谱图像匹配算法。

与现有的大多数基于特征的图像匹配方法类似，所提方法可分为特征提取，特征描述和特征匹配三个部分。在特征点提取部分，通过对几种典型特征点的分析，发现角点更适用于多光谱图像匹配；在特征描述部分，在EOH的基础上提出了一种构建描述子的新方法；匹配描述子时，使用欧氏距离作为距离准则，使用SIFT算法中的比值策略得到初始的匹配结果；针对初始匹配结果中低内点率的问题，提出了一种基于

RANSAC的外点去除算法。

# 1 多尺度支撑域描述子

# 1.1特征点选取

如前所述，在多光谱图像中边缘信息比灰度信息更相似、一致性更高，因此理论上利用边缘信息提取特征点的算法检测到的特征点一致性更高。最早被提出的特征点是角点，其利用邻域像素点的强度信息区分角点和无关像素点，后自相关矩阵和特征值准则被用于计算图像的角点图[19]。角点本质上可以视为两个或更多边缘的交点。之后，特征点的研究转向于能够估计特征点尺度特性的算法，以适应有尺度变换的匹配场景。被广泛应用的SIFT算法是一个典型代表，该算法利用尺度空间理论提取特征点并估计其尺度特征，提取到的特征点也被称做“斑点”，因为它们体现的是特征点邻域像素灰度分布与高斯函数的相似程度。后来，为了提高计算效率以满足实时应用的需要，FAST特征点[20]及其改进版本被提出，然而该算法需要机器学习改善检测到的特征点的质量。因此，以角点作为多光谱图像匹配的特征点是一个较合理的选择。

为了证明角点更适合于多光谱图像，本文设计了一个对比SIFT 算法和具有代表性的角点提取算法一一Harris 算法提取特征点性能的实验。评估标准是重复度，即在位置上对应的特征点的数量与所有特征点的数量之比。与同一算法在红外与可见光图像中设置相同的参数的实验不同，此处提取相同数量的特征点。这种方法的好处是不需要根据多光谱图像的差异调整算法的每个参数，同时对两种方法都是公平的，此处提取最佳的1000个特征点。由于图像采集自不同的传感器，允许对应特征点在位置上有4个像素距离的容差，该容差应用于本文提到的所有实验。实验采用可见光一长波红外图像数据集[21作为实验对象。实验结果如图1所示。可见在大多数情况下，Harris角点的重复度更高，因此选定Harris角点作为要提取的特征点。

![](images/af3a5471bda1131707f8f9111047093ccc87d5036ad8d7e91af9460e9fa4c1f7.jpg)  
图1每对图像中特征点的重复度

# 1.2边缘像素梯度方向的计算

在计算边缘像素点的梯度方向时，EOH算法使用5方向Sobel算子，获取的方向较粗糙。为了增强描述子的代表性，使用8方向Sobel算子[22]计算边缘像素点的方向。边缘方向的增加可以增加描述子的维度，增强描述子间的差异性。8方向Sobel滤波模板如图2所示。

0 0 0 0 0 0 0 0 0 0 0 0 0 -1 0 0 0 -1 0 0  
-1 -2 -4 -2 -1 0 -2 -4 -2 -1 0 -2 -4 0 +1 0 -2 -4 +2 0  
0 0 0 0 0 -1 -4 0 +4 +1 0 -4 0 +4 0 0 -4 0 +4 0  
+1 +2 +4 +2 +1 0 +2 +4 +2 0 -1 0 +4 +2 0 0 -2 +4 +2 0  
0 0 0 0 0 0 0 0 0 0 0 +1 0 0 0 0 0 +1 0 0  
(a) (b) (c) (d)  
0 -1 0 +1 0 $| | \begin{array} { c c c c c c c c } { 0 } & { 0 } & { + 1 } & { 0 } & { 0 } \\ { 0 } & { - 2 } & { + 4 } & { + 2 } & { 0 } \\ { 0 } & { - 4 } & { 0 } & { + 4 } & { 0 } \\ { 0 } & { - 2 } & { - 4 } & { + 2 } & { 0 } \\ { 0 } & { 0 } & { - 1 } & { 0 } & { 0 } \end{array} | | \begin{array} { c c c c c c c } { 0 } & { + 1 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { - 1 } & { 0 } & { + 4 } & { + 2 } & { 0 } \\ { 0 } & { - 4 } & { 0 } & { + 4 } & { 0 } \\ { 0 } & { - 2 } & { - 4 } & { 0 } & { + 1 } \\ { 0 } & { 0 } & { 0 } & { - 1 } & { 0 } \end{array} | | \begin{array} { c c c c c c c } { 0 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { + 2 } & { + 4 } & { + 2 } & { 0 } \\ { - 1 } & { 4 } & { 0 } & { + 4 } & { + 1 } \\ { 0 } & { - 2 } & { - 4 } & { - 2 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 0 } & { 0 } \end{array} |$   
0 -2 0 +2 0  
0 -4 0 +4 0  
0 -2 0 +2 0  
0 -1 0 +1 0  
(e)

注：滤波模板（a) $\sim$ （h）分别计算 $0 ^ { \circ }$ 、 $2 2 . 5 ^ { \circ }$ 、 $4 5 ^ { \circ }$ 、67.5°、 $9 0 ^ { \circ }$ ：$1 1 2 . 5 ^ { \circ }$ 、 $1 3 5 ^ { \circ }$ 和 $1 5 7 . 5 ^ { \circ }$ 方向的导数

边缘像素点的方向由式（1）计算。

$$
O r i ( x , y ) = a r g m a x { \left| F _ { i } \bullet P a t c h ( x , y ) \right| } , i = { \cal I } , 2 , 3 , . . . , 8
$$

其中： $( x , y )$ 表示当前边缘像素点的坐标； $P a t c h ( x , y )$ 表示边缘像素点在原始图像的灰度图中的邻域像素块，且与卷积模板的尺寸相同； $F i$ 表示Sobel算子；·表示卷积运算； $O r i ( x , y )$ 对应于8个Sobel算子所得到的卷积结果中最大值代表的方向。

# 1.3描述子的构建

由多尺度邻域计算得到的描述子可充分利用多光谱图像中的边缘信息。人造环境中常存在多个外形相似的物体，如图 3(a)红色矩形框中窗户的形状与大小非常相似，且从图3(b)中可发现这些窗户的边缘基本相同，此时由单邻域构建的描述子会受到一些限制。当邻域较小时，描述子只包含特征点的局部信息，如果两个特征点邻域内的边缘较相似，则描述子的相似性会很高，使匹配效果下降。此时，需要扩大邻域以添加不同的边缘，进而提高描述子的差异性。然而当邻域较大时，如果两个特征点彼此靠近，则两者的支撑区域的重叠率增大，构建的描述子的相似度较高，导致误匹配。在这种情况下，可以通过包含局部信息的小尺度支持区域来增加差异。因此，本文提出使用多个不同尺度的支持区域计算描述子，这意味着描述子由几个子描述子组成，这些子描述子是从特征点多个不同尺度的邻域计算得到，称这种方法为多尺度支撑域边缘方向直方图(EOHMSR)。本文的目的是提高描述子对不同场景的多光谱图像的鲁棒性，因此不考虑图像间的几何变化关系，如旋转、缩放和仿射变换等。

![](images/11911bd510438e60afa7590c2d6ee69041dc1f0c765c71edc74f45b6ad98489f.jpg)  
图28方向 Sobel算子

描述子的计算过程如图4所示。边缘图像 $E d g e ( x , y )$ 由Canny算法从原始图像 $I ( x , y )$ 中获得，Canny 算法的阈值根据最大梯度模值自动设定，参数 $\scriptstyle \sigma = { \sqrt { 2 } } \circ E d g e ( x , y )$ 中每个边缘像素的方向由1.2 节所示的方法计算，得到边缘像素方向图 $E d g e O r i ( x , y )$ 。从$E d g e O r i ( x , y )$ 得到特征点不同尺度的支撑区域$S R { = } \langle S R _ { I } , S R _ { 2 } , { \ldots } , S R _ { n } \rangle$ ，将每个支撑区域分成 $4 X 4 = 1 6$ 个子区域，统计每个子区域的边缘方向直方图 $H i$ ，进而得到具有 $1 2 8 ( 4 \times 4$ $\times 8 = 1 2 8 ,$ 维的子描述子，最后组合 $H i$ 得到最终的描述子。

![](images/28e14e0fccdb45de549c57058d7a859620c328ca195181d95eaa5de388409d7e.jpg)  
图3a)红外图像(上);(b)图(a)的边缘图像(下)  
图4所提描述子的计算流程

# 2 特征点的匹配

特征点匹配是通过比较特征点的描述子，找到相对应的特征点对。在计算描述子时，删除邻域边缘信息太少的特征点，因为根据较少边缘信息计算出的描述子的代表性较弱。使用欧氏距离作为相似性度量准则。使用比值准则[6判定是否为对应点，即当最短距离和次短距离的比率小于给定阈值时，才将两个特征点认定为匹配的。

![](images/8862b9961702a0d403d7679a0cdebc982f701ad7c34c3e6bdc1928744a95c853.jpg)  
图5初始匹配结果(上)和直接使用RANSAC 的结果(下)

初始匹配结果如图5(a)所示。通过观察可发现误匹配点对可分为两种类型：单点对应的类型与一个点匹配多个点的类型。出现第二种错误类型的主要原因包括图像中有较多相似的区域及部分特征点的位置相对较近。由于内点率较低(26/208)，直接使用RANSAC算法[23]得到的结果(图5(b))较差，计算出的变换模型仅反映了第二种外点的变换关系，这也表明第二种误匹配类型比例较高。受此启发，本文提出了一种实用的外点去除算法。

该算法的关键是根据与同一个点匹配的点的数目将初始匹配结果分成两部分，然后对两部分分别处理。该算法的流程图如图6所示。如果数目为2，则表示一个点与一个点匹配；如果数目大于2，则表示一个点与多个点匹配，相应地将初始的匹配结果 $D _ { o r i g i n a l }$ 分为 $D _ { s i n g l e }$ 和 $D _ { m u l t i p l e }$ 两部分。由于第二种误匹配比例较高，所以先使用RANSAC 算法从单点匹配部分 $D _ { s i n g l e }$ 获得粗糙但基本正确的模型 $M _ { s i n g l e }$ ，同时获得大多数内点InLsingleo

但是在某些情况下， $D _ { m u l t i p l e }$ 仍然有正确的匹配对。为了使得到的变换模型适合所有正确的匹配结果，将 $M _ { s i n g l e }$ 应用于

$D _ { m u l t i p l e }$ 以提取可能正确的匹配对 $D _ { c a n d i d a t e }$ 。首先将属于Dmultiple的红外图像中的特征点 $P I r _ { m u l t i p l e }$ 通过式(2)变换到可见光图像上，变换结果记为PIrTmultipleo

$$
P I r T _ { m u l t i p l e } = M _ { s i n g l e } \mathrm { X } P I r _ { m u l t i p l e }
$$

后根据式(3)计算 $P I r T _ { m u l t i p l e }$ 中的每个点与 $P V s _ { m u l t i p l e }$ 中每个点的欧氏距离

$$
d = \left| P I r T _ { m u l t i p l e } - P V s _ { m u l t i p l e } \right|
$$

其中： $P V s _ { m u l t i p l e }$ 为属于 $D _ { m u l t i p l e }$ 的可见光图像中的特征点。如果$d { < } 4$ ，将这两个点视为正确匹配的候选。

最后，将 $I n L _ { s i n g l e }$ 和 $D _ { c a n d i d a t e }$ 组合构成 $D _ { n e w }$ ，并在其上使用RANSAC 算法，获得最终的变换模型 $M _ { f i n a l }$ 和所有内点 $I n L _ { f i n a l }$ 0如图7所示，与直接使用RANSAC算法相比，所提方法能克服低内点率的问题，得到正确的匹配模型。

![](images/cd953f501993762d3bf41ad0727b4e0b544b99846e7aaf563f2b42283b081d81.jpg)

![](images/3fdba517b6135cabe06757e3cd41c8177650a7ef953adb53e1376cdbc4a8bc7e.jpg)  
图6提出的外点去除算法的流程  
图7提出的外点去除算法的结果

![](images/3635c81a99bd62405e9d56c741f99ed089e0f848ddcaed587d55af1ee36cb3df.jpg)  
图8重复度与特征点数目间的变化关系

# 3 实验结果与分析

# 3.1参数选择

所提算法有几个参数需由实验决定，这些参数包括所提取的特征点数目K、支撑区域数量N 和支撑区域的最小尺寸DXD。为了确定这些参数，在一个可见光-长波红外数据集[2I]上进行了实验，该数据集包含44个图像对，每对图像包含一个可见光图像和一个红外图像，且每对图像都被校正，使得图像的视角与分辨率都相同。

在整个数据集上重复度随特征点数目K的变化如图8所示。重复度是指位置上对应的特征点数目与所有特征点数目之比。容易看出，重复度随着K的增加而增加，这是因为特征点的数目增多时，特征点重复的可能性增加。考虑到计算效率，设置 ${ \bf K } = 1 0 0 0$ ，因为当数量大于1000时，重复度的提高不显著。

召回率和精确度被用做选择支撑区域的数量N和支撑区域最小尺寸DXD评估标准，分别由式（4）（5）计算得出。

$$
P r e c i s i o n { = } \frac { \# c o r r r e c t m a t c h e s } { \# m a t c h e s }
$$

$$
R e c a l l = \frac { \# c o r r e c t m a t c h e s } { \# c o r r e s p o n d e n c e }
$$

其中：#correctmatches是通过第2章介绍的方法去除外点后匹配对的数目；#matches是包含内点和外点初始匹配对的数目；#correspondences是应当正确匹配的特征点的数目。当正确匹配的数量太少而无法获得变换模型或得到的变换模型错误时，将精确度和召回率置为0。

平均精确度和平均召回率随着N和DXD的变化如图9所示。D 随着N的增加而增加相同的间隔20。当N增加时，不管DXD的值是多少，平均精度都会增加，但是不大于 $3 5 \%$ 。平均召回率具有相同的趋势，并且在N为5时达到最大值(约$1 5 \%$ )。由于N每增加1，描述子的维度增加128，考虑到描述子的维度，最终设定 $\Nu = 5$ ， $ { \mathbf { D } } = 3 0$ 。

# 3.2性能对比

本文实验环境为Windows64位系统，运行配置为IntelCorei7， $3 . 4 ~ \mathrm { G H z }$ CPU，内存为4GB，算法采用MATLABR2014b实现。

将所提方法与其他三种经典算法在可见光一长波红外图像数据集[21]上进行评估，使用精确度和召回率作为评判准则。该数据集包含44个图像对，每对图像包含一个可见光图像和一个红外图像，且每对图像都经过校正，使得图像的视角与分辨率都相同，分辨率都为 $6 3 9 X 4 3$ 。图10 显示了几个图像对。由于图像对都经过矫正，正确匹配点对的连线应当是水平的，如图11所示，所提算法比其他三种算法得到的正确匹配结果更多。图12显示了该数据集中每对图像的召回率和精确度。在召回率曲线图中所提方法明显优于其他三种方法，在精确度曲线图中所提方法在大部分图像对中优于其他三种方法。整个数据集上平均每对图像的结果如表1所示。在平均召回率、平均精确度及平均正确匹配数目上，所提算法明显优于其他三种方法；在匹配用时上，所提算法稍优于Sym-SIFT算法，但大约是EOH算法的1.5倍，不过要获得与EOH算法相同的平均正确匹配数目18，所提算法只需要 $5 . 5 2 \mathrm { ~ s ~ }$ ，约为EOH算法的三分之一，从此角度看，所提算法在匹配时间上仍优于EOH 算法。本文着重对算法的有效性进行研究，提高算法对不同场景的适用性。在下一步的工作中，将从软件和硬件上对算法进行改进，提高算法的实时性。

![](images/7b6dc59e8001bc1924ab553b47dc8b36ba90e0f742a5ea71cb205fcfbef1d41a.jpg)

![](images/52a694794ab721ac33f56417237910db0186cd447fd2058d824a39c0b101f7cb.jpg)

图9设置不同的最小尺度支持区域、平均精度和平均召回率随支持区域数量的变化曲线

![](images/96a42ff425a155515f5287fd2d61e87ca92af1bb02cff146b9a836bfdc6cf5cd.jpg)  
图10数据集中的三对可见光一长波红外图像

![](images/951db3ee414ee98250cb178d8866f1dfe407fc7c723cac6a387bd9539cb44d0a.jpg)  
图11四种算法的结果对比:SIFT(左上);Sym-SIFT(右上);EOH(左下);所提算法(右下)

表1整个数据集上平均每对图像的结果对比  

<html><body><table><tr><td>匹配方法</td><td>SIFT[4]</td><td>Sym-SIFT [6]</td><td>EOH [7]</td><td>EOHMSR (ours)</td></tr><tr><td>平均召回率</td><td>0.49%</td><td>1.02%</td><td>2.78%</td><td>14.07%</td></tr><tr><td>平均精确度</td><td>4.31%</td><td>12.89%</td><td>12.68%</td><td>32.06%</td></tr><tr><td>平均正确匹配数目</td><td>3</td><td>9</td><td>18</td><td>84</td></tr><tr><td>平均匹配时间/s</td><td>10.12</td><td>26.88</td><td>16.81</td><td>25.77</td></tr></table></body></html>

![](images/1b194f604e6e857d55b451d82e7aecd26baaa2b5442df877b6aae2e263f1354c.jpg)  
图12在数据集上每对图像的召回率(上)和精确度(下)

# 4 结束语

本文提出了一种有效的多光谱图像匹配算法，首先，选择Harris角点作为特征点，确保了所提取特征点的高重复性；然后，利用不同尺度的支撑域中的边缘信息计算描述子，增强了描述子间的差异性；最后，针对初始匹配结果中低内点率的问题，在RANSAC 算法的基础上，提取了一种新的外点去除算法。实验结果表明，所提出的算法比传统多光谱图像算法的鲁棒性更强，且获得的正确匹配点对更多。在下一步的工作中，将增强所提方法对旋转、尺度和仿射变换的鲁棒性，提高算法的实时性。

# 参考文献：

[1]程国华，王阿川，陈舒畅，等．多源遥感影像高精度自动配准方法研究 [J].液晶与显示,2016,31(6): 604-612.(Cheng Guohua,Wang Achuan, Chen Shuchang，et al. High accuracy-automatic registration method research on multi-source remote sensing image [J]. Chinese Journal of Liquid Crystals & Displays,2016,31(6): 604-612.)   
[2] 李艳梅，陈雷霆，饶云波，等．基于双变换的红外与可见光图像融合增 强[J].计算机应用研究，2013,30(10):3142-3145.(Li Yanmei，Chen Leiting,Rao Yunbo,et al.Infrared and visual image fusion enhancement by dual-transform [J].Application Research of Computers,2013,30 (10): 3142-3145.)   
[3]郭少军，刘峰，奚晓梁．海面舰船红外与可见光图像配准[J].红外技 术,2016,38(5):403-408.(Guo Shaojun,Liu Feng,Xi Xiaoliang. The registration of warship infrared and visible images [J]. Infrared Technology, 2016,38 (5): 403-408.)   
[4]肖儿良，刘雯雯．多尺度梯度域可见光与红外热图像融合方法研究[J]. 计算机应用研究，2015,32(10):3160-3163,3167.(Xiao Erliang，Liu Wenwen.Research of multi-scale gradient domain visible and thermal image fusion method [J].Application Research of Computers,2015,32 (10): 3160-3163,3167.)   
[5] 郭全民，董亮，李代娣．红外与可见光图像融合的汽车抗晕光系统[J]. 红外与激光工程,2017,46(8):171-176.(Guo Quanmin,Dong Liang,Li Daidi. Vehicles anti-halation system based on infrared and visible images fusion [J]. Infrared & Laser Engineering,2017,46 (8): 171-176.)   
[6]Lowe D.Distinctive image features from scale-invariant keypoints [C]// Proc of International Journal of Computer Vision.2Oo4: 91-110.   
[7]Bay H,Ess A,Tuytelaars T,et al.Speeded-up robust features [J]. Computer Vision & Image Understanding,2008,110 (3): 404-417.   
[8]Brown L.A survey of image registration techniques [J].Computing

Surveys,1992,24:325-376.

[9]Zitova B,Flusser J. Image registration methods:a survey [J]. Image and Vision Computing,2003,21: 977-1000.   
[10] Xiong Zhen,Zhang Yun.A critical review of image registration methods [J].International Journal of Imageand DataFusion,2O10,1: 137-158.   
[11] Maes F, Vandermeulen D,Suetens,P. Medical image registration using mutual information [J].Proceedings of the IEEE,2003,91:1699-1622.   
[12] Coiras E,Santamaria J,Miravet C.Segment-based registration technique for visual-infrared images [J]. Optical Engineering,20o,39:282-289.   
[13]Han J,Pauwels E,Zeeuw P. Visible and infrared image registration employing line-based geometric analysis[Cl// Proc of International Conference on Computational Intelligence for Multimedia Understanding. Berlin: Springer,2011: 114-125.   
[14]魏丽君．多光谱图像的直线匹配[D].北京：北京邮电大学,2017.(Wei Lijun.Line matching algorithm on multispectral images [D].Beijing: Beijing University of Posts and Telecommunications,2017.)   
[15] Chen Jian,Tian Jie. Real-time multi-modal rigid registration based on a novel symmetric-sift descriptor [J]. Progress in Natural Science-Materials International,2009,19: 643-651.   
[16] Dalal N,Triggs B.Histograms of oriented gradients for human detection [C]// Proc of IEEE Computer Society Conference on Computer Vision & Pattern Recognition.[S.1.] : IEEE Computer Society,2005: 886-893.   
[17]Belongie S,Malik J,Puzicha J. Shape matching and object recognition using shape contexts [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2002,24: 509-522.   
[18] Aguilera C,Barrra F,Lumbreras F,et al. Multispectral image feature points [J]. Sensors,2012,12:12661-12672.   
[19] Harris C.A combined corner and edge detector[J].Proc Alvey Vision Conf, 1988,1988 (3): 147-151.   
[20] Rosten E,Drummond T.Machine learning for high-speed corner detection [Cl// Proc of European Conference on Computer Vision. Berlin: Springer, 2006: 430-443.   
[21] Dalal N,Triggs B.Histograms of oriented gradients for human detection [C]/Proc of IEEE Computer Society Conference on Computer Vision & Pattern Recognition. [S.1.] : IEEE Computer Society, 2005: 886-893.   
[22]郑英娟，张有会，王志巍，等．基于八方向 Sobel 算子的边缘检测算法 [J].计算机科学，2013，40 （11A):354-356.(Zheng Yingjuan，Zhang Huiyou,Wang Zhiwei,et al. Edge detectionalgorithm based on the eight directions Sobel operator [J].Computer Science，2013，40(11A): 354-356.)   
[23]FischlerM,Boles R.Randomsample consensus:a paradigm for model-fittingwith applicationstoimage-analysisandautomated cartography [J]. Communications of the ACM,1981,24: 381-395.