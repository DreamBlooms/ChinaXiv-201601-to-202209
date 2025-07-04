# 基于模糊相似性的彩色形态学图像处理方法

何晓军‘，徐爱功ʰ，李玉b

(辽宁工程技术大学 a.创新实践学院;b.测绘与地理科学学院，辽宁阜新 123000)

摘要：为了将传统灰度图像数学形态学扩展到彩色图像，提出一种结合矢量空间模糊相似性的彩色形态学图像处理方法。首先，在RGB彩色空间中利用彩色矢量间的距离和角度定义模糊相似性测度，以刻画与人类视觉感知相一致的彩色相似程度；以上述相似性测度为准则定义彩色空间中任意一组彩色的上确界和下确界；利用中心像素及其结构单元内像素的上确界和下确界构建彩色形态学的基本操作，包括膨胀、腐蚀、开、闭等操作；进一步将提出的彩色形态学操作应用于高分辨率遥感图像，通过实验对比验证其对地物目标的形变和平滑能力，说明其实用性和有效性。

关键词：彩色空间；彩色形态学；模糊相似性测度；图像处理 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.06.0654

# Color morphology image processing method based on fuzzy similarity

He Xiaojun1, Xu Aigong², Li ${ \mathrm { Y u } } ^ { \mathrm { b } }$ （204号 (a.CollegeofInnovation&Practice,b.SchoolofGeomaticsLiaoningTechnicalUniversityFuxinLiaoning23oo,China)

Abstract:To extendthemathematical morphology for grayscale image toitsalterativeforcolor image,acolormathematical morphology basedonfuzzysimilaritydefinedonRGBcolorvector spaceis proposed in this paper.Firstly,inRGBcolorpace, thefuzzysimilarity measure,which isconsistent withthe human visual perception,is defined byusing the distance and angle between two vectors to describe the similarity degree between the two colors.Theupperand lower bound functions ina collection ofcolors fromin RGBcolor spaceare defined bytheir similaritymeasures.The basic operations ofthecolor mathematical morphologyare formulatedbyusing theupperandlowerbounds foraany pixeland its neighborpixels withinthe structuralunitcenteredthepixel,includingdilation,rosion,openingandclosingoperations.Theproposedcolrmorpological operations areapplied tothe highresolutionremote sensing images,and thedeformationand smothing ability toobjects are verified by comparing experiment, and its practicability and validity are explained.

Key Words: color space; color morphology; fuzzy similarity measure; image processing

# 0 引言

在图像处理领域，数学形态学利用结构元素（圆形、正方形、线段等）为基本单元处理图像信息，用以分析和辨识图像目标的几何特征和结构。作为一种非线性图像处理和分析方法，数学形态学成功应用于二值和灰度图像，并形成了完备的形态学理论[1]。其中，二值形态学将二值图像看成集合，运用最简单的集合运算（如交、并、补和平移等）探测蕴含在图像中的几何结构。由于采用的运算均基于集合，因此二值形态学具有原理清晰、计算简单、易于扩展，且适合于并行计算等特点，并已广泛用于去噪、边界检测、骨架化、区域分割等图像处理领域[2]。灰度形态学则是由二值形态学发展而来，只需将二值形态学中的交、并分别换成结构单元内像素灰度的最小和最大值

即可[3]。

近年来，彩色图像已广泛用人类生产、生活的各个领域。与二值和灰度图像相比较，除了亮度信息彩色图像还包含人类能够感知的色彩信息，因此彩色图像处理受到越来越多的关注。目前，将数学形态学推广到彩色图像，并由此实现彩色图像的滤波、分割、特征提取、边缘检测、图像增强和恢复等，是彩色图像处理领域中的一个重要研究方向[4-6]。

一般情况下，将灰度形态学拓展到彩色形态学的最简单方式是将RGB彩色图像看成由红、绿、蓝三幅单色图像构成，利用灰度形态学分别处理这三幅单色图像，最后将形态学处理结果还原为RGB 彩色图像。但这样的处理结果一方面将改变原图像中的彩色，从而丢失或歪曲原图像信息；另一方面由于没有考虑彩色图像各分量间的相关性，而仅仅将彩色图像假设为红、绿、蓝三幅独立图像，从而无法更加有效利用彩色信息。另一种把灰度形态学拓展到彩色形态学的方法就是基于多元数据排序准则，如边缘序、条件序、区域序和退化序等，排序结构单元内的彩色，并用类似灰度形态学中的最小值和最大值原则定义基本形态学操作[7-8]。但对于丰富多彩的彩色图像难以找到合适、通用的彩色矢量排序方法，所以这种彩色形态学方法具有很大的局限性。

为了克服和解决目前彩色形态学方法存在的问题及局限性，本文在RGB彩色空间中引入模糊相似性测度的概念以刻画彩色矢量间的相似性程度，并据此定义彩色形态学的基本操作。这种彩色形态学不但能够平滑彩色目标，而且可以很好的处理同质区域像素不一致性的细节特征，最终达到彩色图像分析和处理的目标。

# 1基于模糊相似性的彩色形态学方法

# 1.1模糊相似性测度

RGB彩色空间是表示彩色最基本、最常用的三维矢量空间[9]，设 $\mathbf { V } = \{ \pmb { v } _ { i } , i = 1 , . . . , n \}$ 是 RGB 彩色空间中所有彩色矢量的集合，其中, $n$ 为该彩色空间的总彩色数，i为彩色索引， $\pmb { \nu _ { i } } = \left( \nu _ { i R } , \right.$ （204号$\nu _ { i G } , \nu _ { i B } )$ 为彩色 $i$ 的彩色矢量，ViR、ViG、 $\nu _ { i B }$ 分别表示彩色矢量 $i$ 的红、绿、蓝分量。

在该彩色空间中，给定彩色矢量对 $\pmb { \nu } _ { i } , \pmb { \nu } _ { i ^ { \prime } } \in \mathbf { V }$ ，如图1所示，则模糊相似性测度定义为

$$
\mu ( \pmb { \nu } _ { i } , \pmb { \nu } _ { i } , \pmb { \nu } ) = e ^ { - k _ { 1 } d ( \pmb { \nu } _ { i } , \pmb { \nu } _ { i } , \pmb { \nu } ) } \cos \left( k _ { 2 } \theta ( \pmb { \nu } _ { i } , \pmb { \nu } _ { i } , \mathbf { \nu } ) \right)
$$

其中： $k _ { 1 } = [ 0 , \infty )$ 和 $k _ { 2 } = [ 0 , 1 ]$ 为控制相似程度的参数， $d ( \pmb { \nu } _ { i } , \pmb { \nu } _ { i ^ { \prime } } )$ 和 $\theta ( \pmb { \nu } _ { i } , \pmb { \nu } _ { i ^ { \prime } } ) \in [ 0 , \pi / 2 )$ 分别为两彩色矢量间的欧几里德距离和夹角，可表示为

$$
d ( \nu _ { i } , \nu _ { i ^ { \prime } } ) = \left( ( \nu _ { i R } - \nu _ { i ^ { \prime } R } ) ^ { 2 } + ( \nu _ { i G } - \nu _ { i G } ) ^ { 2 } + ( \nu _ { i B } - \nu _ { i ^ { \prime } B } ) ^ { 2 } \right) ^ { 1 / 2 }
$$

$$
\theta ( \nu _ { i } , \nu _ { i } , ) = \operatorname { a r c c o s } \frac { \nu _ { i R } \nu _ { i ^ { \prime } R } + \nu _ { i G } \nu _ { i ^ { \prime } G } + \nu _ { i B } \nu _ { i ^ { \prime } B } } { \left( { \nu _ { i R } } ^ { 2 } + { \nu _ { i G } } ^ { 2 } + { \nu _ { i B } } ^ { 2 } \right) ^ { 1 / 2 } \left( { \nu _ { i ^ { \prime } R } } ^ { 2 } + { \nu _ { i ^ { \prime } G } } ^ { 2 } + { \nu _ { i ^ { \prime } B } } ^ { 2 } \right) ^ { 1 / 2 } }
$$

由式(1)可以看出，定义的模糊相似性测度取值区间为[0,1]:对应RGB彩色空间，当两个彩色矢量在距离和角度上越接近时，即其距离和夹角越小，相似性测度的值越大，表示两者具有较高相似性；反之，当两个彩色矢量间距离或夹角较大时，则其相似性测度的值越小，表示相似程度较低。当然，当两个彩色矢量重合（即为同一矢量）时，距离及夹角均为0，则相似性测度为1，表征其相似程度最高，这些都与实际视觉感知相符合。另外，由于人对彩色认知的差异，即对于同样两种彩色矢量，相似性会因个人的视觉感知而不同，使得这种相似具有一定的模糊性，所以式(1)中引入参数 $k _ { 1 }$ 和 $k _ { 2 }$ ，通过改变其值能达到人为调整两个矢量的相似性程度的目的，使其与人类视觉感知的模糊性相一致。

本文定义的这种模糊相似性测度不仅能刻画彩色矢量间的相似性程度，而且与人类视觉感知的不确定性和模糊性相符合，这也是构建彩色形态学的理论基础。

![](images/c27668bfa25f367a42ad16937bcf0ddded6afeaba5235dcee218848fe04a7d19.jpg)  
图1 RGB矢量空间

# 1.2基于模糊相似性测度的彩色形态学

虽然数学形态学在二值和灰度图像处理中取得了良好的效果，并已构建了完备的二值和灰度形态学理论基础[10]，但对于彩色图像而言，由于缺乏明确、统一、有效的彩色矢量排序方法，使得数学形态学在彩色图象处理中的受到极大地限制。尽管提出了一些应用于彩色图像处理的形态学方法，但这些方法都难以达到彩色图像处理的预期效果。为了能够将数学形态学的思想真正用于彩色图像的处理，并避免彩色矢量排序的难题，在上述定义的模糊相似性测度基础上，提出一种新型彩色形态学方法，该方法基于模糊相似性测度来获取结构单元的上确界和下确界，并以此构建彩色形态学的基本操作。

给定彩色图像 $C$ ，设 $C$ 中所有彩色矢量构成的彩色集合为$V _ { C } { = \{ \nu _ { j } , j { = } 1 , . . . , m \} }$ ，其中 $\mathbf { \nabla } _ { j }$ 为像素索引， $m$ 是彩色图像 $C$ 中的像素数。 $V _ { j }$ 表示彩色图像 $C$ 中以像素 $j$ 为中心的结构单元内彩色矢量集合，即 $V _ { j } = \{ \pmb { \nu } _ { j p } , p = 1 , . . . , q \} \subset V _ { C }$ ，其中， $p$ 为 $V _ { j }$ 中像素索引， $q$ 是该集合中彩色矢量数。

在当前结构单元 $V _ { j }$ 中，最不相似的彩色矢量对集合 $V _ { j d s }$ 可表示为

$$
V _ { j d s } = \{ ( \nu _ { j p } , \nu _ { j p } , ) , ~ ( \nu _ { j p } , \nu _ { j p } , ) = \arg \operatorname* { m i n } _ { 1 \leq k , l \leq q } \{ \mu ( \nu _ { j k } , \nu _ { j l } ) , ~ \nu _ { j k } , \nu _ { j l } \in V _ { j } \} \}
$$

即集合 $V _ { j d s }$ 是 $V _ { j } \times V _ { j }$ 中所有彩色矢量对模糊相似性测度最小的矢量对集合。然后在 $V _ { j d s }$ 中，随机选取一矢量对作为最不相似的彩色向量对，记为 $( { \pmb { \nu } } _ { j d s 1 } , { \pmb { \nu } } _ { j d s 2 } ) \in V _ { j d s }$ 。按其模的大小Vjdsl和 $\nu _ { j d s 2 }$ 分别称为最大彩色矢量（模值大者） $\nu _ { j m a x }$ 和最小彩色矢量（模值小者） $\nu _ { j m i n }$ 。如图2所示，假设以像素 $j$ 为中心的结构单元内彩色矢量集合 $V _ { j }$ 由16个二维矢量组成，这里将矢量长度和相对方向作为判断相似性的依据，而各矢量的颜色只是为了说明定义方便而设置。经模糊相似性测度计算，最不相似的彩色矢量对为 $( \pmb { \nu } _ { j m a x } , \pmb { \nu } _ { j m i n } )$ ，加粗红色表示的向量比加粗蓝色长度长，所以加粗红色表示的最大彩色矢量为 $\nu _ { j m a x }$ ，加粗蓝色表示的最小彩色矢量为 $\nu _ { j m i n }$ 。

分别以最大和最小彩色矢量 $( \pmb { \nu } _ { j m a x } , \pmb { \nu } _ { j m i n } )$ ）为核心，将V中所有彩色矢量分成两类，记为 $C L _ { j m a x }$ 和 $C L _ { j m i n }$ 。对于任意彩色矢量 $\boldsymbol { \nu } _ { j p } \in V _ { j }$ ，如果 $\boldsymbol { v } _ { j p }$ 与 $\nu _ { j m a x }$ 的相似性测度大于 $\boldsymbol { v } _ { j p }$ 与 $\nu _ { j m i n }$ 的相似性测度，则 $\boldsymbol { \nu } _ { j p }$ 属于 $C L _ { j m a x }$ ，否则， $\boldsymbol { \nu } _ { j p }$ 属于 $C L _ { j m i n }$ ，即

$$
\mathrm { C L } _ { \mathrm { j m i n } } = \{ \mathbf { v } _ { \mathrm { j p } } , \mu ( \mathbf { v } _ { \mathrm { j p } } , \mathbf { v } _ { \mathrm { j m i n } } ) \geq \mu ( \mathbf { v } _ { \mathrm { j p } } , \mathbf { v } _ { \mathrm { j m a v } } ) , \mathbf { v } _ { \mathrm { j p } } \in \mathrm { V } _ { \mathrm { j } } \}
$$

$$
\mathrm { C L } _ { \mathrm { j m a x } } = \{ \mathbf { v } _ { \mathrm { j p } } , \mu ( \mathbf { v } _ { \mathrm { j p } } , \mathbf { v } _ { \mathrm { j m a x } } ) \geq \mu ( \mathbf { v } _ { \mathrm { j p } } , \mathbf { v } _ { \mathrm { j m i n } } ) , \mathbf { v } _ { \mathrm { j p } } \in \mathrm { V } _ { \mathrm { j } } \}
$$

根据计算的相似性测度可以判断出图2中用蓝色表示的其他矢量与 $\nu _ { j m i n }$ 的相似性比与 $\nu _ { j m a x }$ 相似性大，因此，用蓝色表示的矢量属于 $C L _ { j m i n }$ ；同理，红色表示的其他矢量与 $\nu _ { j m a x }$ 的相似性比与 $\nu _ { j m i n }$ 相似性大，用红色表示的矢量属于 $C L _ { j m a x }$ 。 $C L _ { j m i n }$ 中所有的蓝色矢量具有较好的相似性， $C L _ { j m a x }$ 中所有的红色矢量具有较好的相似性。

![](images/b1a44198cddf0a45f5c1d60360b6d2a2b3ad632bdebd55382b5832bf99f6fe3e.jpg)  
图2各个矢量定义

则 $\mathrm { { C L } _ { j m i n } }$ 和 $\mathrm { C L } _ { \mathrm { j m a x } }$ 中最高相似性彩色矢量 $\mathbf { v } _ { \mathrm { c l j m i n } }$ 和Vcljmax分别可表示为

$$
\pmb { \nu } _ { _ { c l j m i n } } = \mathbf { a r g } \operatorname* { m a x } _ { \pmb { \nu } _ { j p } \in C L _ { j m i n } } \left\{ \sum _ { \pmb { \nu } _ { j p } , \in C L _ { j m i n } } \mathcal { \mu } ( \pmb { \nu } _ { j p } , \pmb { \nu } _ { j p } , ) \right\} (
$$

$$
\nu _ { _ { c l j m a x } } = \arg \operatorname* { m a x } _ { \nu _ { j p } \in C L _ { j m a x } } \left\{ \sum _ { \nu _ { j p } , \in C L _ { j m a x } } \mathcal { \mu } ( \nu _ { j p } , \nu _ { j p } , ) \right\}
$$

根据式(7)和(8)得到的最高相似性彩色矢量，即可得到结构单元 $V _ { j }$ 中的下确界操作∧和上确界操作 $\vee$ ：

$$
\wedge V _ { j } = \wedge \{ \pmb { \nu } _ { j 1 } , \pmb { \nu } _ { j 2 } , . . . , \pmb { \nu } _ { j q } \} = \pmb { \nu } _ { c l j m i n }
$$

$$
\mathsf { v } V _ { j } = \mathsf { v } \{ \pmb { { \nu } } _ { j 1 } , \pmb { { \nu } } _ { j 2 } , . . . , \pmb { { \nu } } _ { j q } \} = \pmb { { \nu } } _ { c l j m a x }
$$

由式(9)和(10)可以看出，下确界操作入和上确界操作 $\vee$ 输出的彩色矢量分别为彩色矢量类 $C L _ { j m i n }$ 和 $C L _ { j m a x }$ 中最高相似彩色矢量 $\pmb { \nu } _ { c l j m i n }$ 和 $\pmb { \nu } _ { c l j m a x }$ ，它们分别与 $C L _ { j m i n }$ 和 $C L _ { j m a x }$ 中所有其他彩色矢量的相似性测度之和最大[13]。此外，上确界和下确界操作输出的彩色矢量均为给定彩色图像中结构单元内彩色矢量，即该操作并不会产生新的彩色矢量，在很大程度上有效保持了原图像信息。本文提出的新型彩色形态学基本操作就是用结构单元 $V _ { j }$ 的上确界和下确界来定义。

给定的彩色图像 $C$ ， $C$ 中所有彩色向量构成集合 $V _ { C }$ ，彩色图像的膨胀操作 $\delta c$ ，腐蚀操作 $\varepsilon c$ ，闭运算 $\chi _ { C } ,$ 开运算 $o c$ 分别表示

为

$$
\delta _ { C } ( V _ { C } ) = \{ \lor V _ { j } , j = 1 , \ 2 , \ . . . , m \}
$$

$$
\varepsilon _ { c } ( V _ { c } ) = \{ \land V _ { j } , j = 1 , \ 2 , \ . . . , m \}
$$

$$
\chi _ { c } ( V _ { c } ) = \varepsilon _ { c } ( \delta _ { c } ( V _ { c } ) )
$$

$$
o _ { c } ( V _ { c } ) = \delta _ { c } ( \varepsilon _ { c } ( V _ { c } ) )
$$

由这种彩色形态学操作可以看出，针对彩色图像矢量集合$V _ { C }$ 的膨胀操作就是在结构单元 $V _ { j }$ 中找出该彩色矢量子集的上确界；同理，腐蚀操作就是在结构单元 $V _ { j }$ 中找出该彩色矢量子集的下确界；开、闭运算是膨胀、腐蚀的复合运算，只是每次计算上、下确界的顺序不同而已。这样，不但能有效地完成对彩色图像的形态学处理，而且在很大程度上保留了原图像的像素彩色矢量基本特征，将其应用于实际彩色图像处理时的算法流程图如图3所示。

![](images/474f499db9cb8c911d30bb5f6c7abdcda19c208bbb98f34c11b1a55a13238a87.jpg)  
图3算法流程图

# 2 实验结果与分析

# 2.1模糊相似性测度的参数分析

模糊相似性测度是本文所提彩色形态学操作的基础，其中引入参数 $k _ { 1 }$ 和 $k _ { 2 }$ 用于控制和调整两个矢量的相似性程度，即对于同样两个矢量，由于参数 $k _ { 1 }$ 和 $k _ { 2 }$ 的不同，使其具有不同的相似性程度，这就与人类视觉感知的模糊性相一致。为了研究参数 $k _ { 1 }$ 对所定义的模糊相似性测度的影响，令式(1)中 $k _ { 2 } { = } 1$ ，当参数 $k _ { 1 }$ 分别取0、0.1、0.25、0.5、0.75及1.0时，模糊相似性测度的变化情况如图4所示。在图4(a)中，由于取 $k _ { 1 } = 0$ ，所以相似性测度与两彩色矢量间的距离无关，仅与角度有关，且随矢量间相对角度的增大，相似性测度逐渐减小；当 $k _ { 1 }$ 分别取0.1、0.25、0.5、0.75和1.0 时，相似性测度变化如图4(b)-(f)所示，从图中可以清楚的看出相似性测度对参数 $k _ { 1 }$ 十分敏感，随着 $k _ { 1 }$ 的逐渐增加相似性测度迅速减小。

同理，为了研究参数 $k _ { 2 }$ 对所定义的模糊相似性测度的影响，令式(1)中 $k _ { 1 } = 1$ ，参数 $k _ { 2 }$ 分别取 $0 . \ 0 . 6 , 0 . 7 , 0 . 8 , 0 . 9$ 及1.0时，相似性测度的变化影响如图5所示。从图5(a）可以看出，当k2$= 0$ 时，彩色矢量间的相似性测度与夹角无关，仅与距离有关，且随距离的增大而减小；当 $k _ { 2 }$ 分别取0.6、0.7、0.8、0.9及1.0时，相似性测度变化如图5(b)-(f)所示，从图中能够看出彩色矢量间的相似性测度随着 $k _ { 2 }$ 的逐渐增加而减小。

![](images/6031a41fb7e99727cc2d980e615111e68921f3fbf797b920525e35a136436c96.jpg)  
图4当 $k _ { 2 } = 1$ 时 $k _ { I }$ 对模糊相似性测度的影响

![](images/a34890bf20c8d0002bbe00af09bcf6236b4e096b6afd2ad6beb873719b41131c.jpg)  
图5当 $k _ { 1 } = 1$ 时 $k _ { 2 }$ 对模糊相似性测度的影响

另外，为了进一步分析参数 $k _ { 1 }$ 和 $k _ { 2 }$ 同时变化对模糊相似性测度的影响，假设 $d = 1$ 、 $\theta = \pi / 4$ ，两个矢量间模糊相似性测度变化如图6所示。从图中能够清楚的看出，针对同样的两个彩色矢量，当参数 $k _ { 1 }$ 和 $k _ { 2 }$ 取不同值时，由式(1)所得到的模糊相似性测度是不同的，参数 $k _ { 1 }$ 和 $k _ { 2 }$ 的不同组合直接决定了两个矢量的相似程度，随着 $k _ { 1 } , k _ { 2 }$ 的增加，矢量间的相似性测度减小，相似程度降低；反之，相似程度升高；参数 $k _ { 1 }$ 比 $k _ { 2 }$ 对相似性测度的影响更大，相似性测度对于 $k _ { 1 }$ 的变化更加敏感，这符合彩色矢量的相似性因人、环境而异的特征，能满足和符合彩色图像处理过程中的由于人的视觉感知带来的不确定性和模糊性。

![](images/4b319d3e793ce1d2cb3aeeca21a2f1c5a06cca46872d59b5bc71cd46b2ed582c.jpg)  
图6当 $d = 1$ 5 $\theta = \pi / 4$ 时 $k _ { 1 }$ 、 $k _ { 2 }$ 对相似性测度的影响

# 2.2结构单元中的参数分析

结构单元是彩色形态学图像处理的基本单元和窗口，为了进一步分析其最不相似的彩色矢量对、最大（最小)彩色矢量、最高相似性彩色矢量及上、下确界的获取和确定。在这里，假设彩色图像 $C$ 中存在一个结构单元 $V _ { j }$ ，其中包含(255,0,0)、(205,0,0)、(205,50,0)、(40,255,0)、(40,215,0)和(80,215,0)等六个彩色矢量。根据上面参数 $k _ { 1 }$ 、 $k _ { 2 }$ 对模糊相似性测度的影响分析，选取参数 $k _ { 1 } { = } 0 . 0 0 1$ ， $k _ { 2 } { = } 0 . 8$ 利用式(1)来计算这六个彩色矢量间的模糊相似性测度，计算结果如表1所示。

从表1中可以看出，彩色矢量1(255,0,0)和彩色矢量4(40,255,0)具有最小的模糊相似性测度(0.3043)，根据式(4)可得到模糊相似性最小的彩色矢量对集合 $V _ { j d s }$ ，其中仅包含唯一的彩色矢量对{(255,0,0),(40,255,0)}，因此为最不相似的彩色矢量对。由于彩色矢量4(40,255.0)比彩色矢量1(255.0.0)有更大的模值，由此彩色矢量4和彩色矢量1分别为最大和最小彩色矢量。比较 $V _ { j }$ 中彩色矢量与最大（彩色矢量4）和最小彩色矢量（彩色矢量1）的相似性测度，可以发现彩色矢量2和3与彩色矢量1的相似性测度比彩色矢量4的高，而彩色矢量5和6与彩色矢量4有更高的相似性测度，则彩色矢量1、2、3属于彩色矢量类 $C L _ { j m i n }$ ，彩色向量4、5、6属于彩色矢量类 $C L _ { j m a x }$ 。据式(7)和(8)，可以计算彩色矢量类 $C L _ { j m i n }$ 中彩色矢量2(205,0,0)与其他两种彩色矢量相似性测度累加和最大（2.8851)，所以该彩色矢量为 $C L _ { j m i n }$ 中最高相似彩色矢量 $\nu _ { c l j m i n }$ ，即结构单元 $V _ { j }$ 的下确界，也就是当前结构单元彩色形态学的腐蚀输出。同理，彩色矢量5(40,215,0)是 $C L _ { j m a x }$ 中最高相似彩色矢量 $\nu _ { c l j m a x }$ ，即此结构单元 $V _ { j }$ 的上确界，同时也是当前结构单元彩色形态学的膨胀输出。

# 2.3彩色形态学基本操作实验

基于前面彩色形态学的定义及参数分析，选取彩色图像Peppers中以像素(70,55)为中心的 $3 0 \times 3 0$ 区域作为形态学操作区域如图7(a)蓝色框所示，其中包含红色辣椒、绿色辣椒、黄色辣椒和黑色阴影等四种典型目标对象，取出该区域如图7(b1)所示，并将该区域放大5倍如图7(b2)所示。计算彩色模糊相似性测度的参数设为 $k _ { 1 } { = } 0 . 0 0 1$ 和 $k _ { 2 } { = } 0 . 8$ ，形态学操作的结构单元为尺度 $3 { \times } 3$ 像素的正方形。对测试图像的彩色形态学操作，包括腐蚀、膨胀、开、闭等，结果如图7(c1)-(c4)所示。为了清楚地观察形态学操作结果的细节，将各形态学处理结果图像放大5倍，如图7(d1)-(d4)所示。从图7(c1)和(d1)可以看出，腐蚀操作使原图像中阴影（背景）面积扩大了，其他目标被压缩了，原来的小的间隙被填补，同时每个目标的颜色及边缘变得更加平滑。由图7(c2)和(d2)可以看出，膨胀操作的结果正好与腐蚀操作相反，原图像的阴影（背景）部分被压缩了，其他目标被扩大了，即浅色被扩展，深色被压缩，原图像中的"毛刺"被消除，同样目标的颜色及边缘也变得平滑。开、闭运算、与腐蚀、膨胀运算相似，如图7(c3)和(d3)以及图(c4)和(d4)所示，通过上面的实验可以看出，提出的彩色形态学操作符合形态学操作的基本原理，且能较好的解决同质区域像素不一致的问题，这将使基于彩色形态学的彩色图像分割、滤波、目标提取等成为可能。

表1结构单元中彩色的模糊相似性测度  

<html><body><table><tr><td>序号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td rowspan="2">彩色矢量类 相似性测度</td></tr><tr><td>RGB</td><td>(255,0,0)</td><td>(205,0,0)</td><td>(205,50.0)</td><td>(40,255,0)</td><td>(40,215,0)</td><td>(80,215,0)</td></tr><tr><td></td><td>1.0000</td><td>0.9512</td><td>0.9147</td><td>0.3043</td><td>0.3284</td><td>0.4274</td><td>2.8659</td></tr><tr><td>2</td><td>0.9512</td><td>1.0000</td><td>0.9339</td><td>0.3135</td><td>0.3395</td><td>0.4398</td><td>2.8851</td></tr><tr><td>3</td><td>0.9147</td><td>0.9339</td><td>1.0000</td><td>0.4528</td><td>0.4809</td><td>0.5778</td><td>2.8486</td></tr><tr><td>4</td><td>0.3043</td><td>0.3135</td><td>0.4528</td><td>1.0000</td><td>0.9605</td><td>0.9329</td><td>2.8934</td></tr><tr><td>5</td><td>0.3284</td><td>0.3395</td><td>0.4809</td><td>0.9605</td><td>1.0000</td><td>0.9517</td><td>2.9122</td></tr><tr><td>6</td><td>0.4274</td><td>0.4398</td><td>0.5778</td><td>0.9329</td><td>0.9517</td><td>1.0000</td><td>2.8845</td></tr></table></body></html>

![](images/3d907b087a0da47c7383199f665491a23e03e6ad575c6cefc94deffa330f4a3e.jpg)  
图7彩色形态学操作

# 3 高分辨率遥感图像的彩色形态学处理

# 3.1模糊相似性测度参数对彩色形态学图像处理的影响分析

为了进一步分析模糊相似性测度参数对实际彩色图像操作结果的影响。选取尺度为 $1 5 0 \times 1 5 0$ 像素的Ikonos 高分辨率彩色遥感影像，如图8所示，采用三组模糊相似性测度参数 $k _ { 1 }$ 和 $k _ { 2 }$ ，即 $( \mathrm { a } ) k _ { 1 } { = } 0 . 0 1$ 和 $k _ { 2 } { = } 0 . 2$ 、 $( \mathsf { b } ) k _ { 1 } { = } 0 . 0 0 5$ 和 $k _ { 2 } { = } 0 . 5$ ， $( \mathrm { c } ) k _ { 1 } { = } 0 . 0 0 1$ 和 $k _ { 2 } { = } 0 . 8$ ，形态学操作的结构单元为尺度 $3 { \times } 3$ 像素的正方形，以实现彩色形态学腐蚀、膨胀、开运算、闭运算等基本操作，其操作结果如图9\~12所示。

膨胀、开运算、闭运算）无论是从光滑目标还是保留原图像边缘特性都达到了最优。当 $k _ { 1 }$ 变小、 $k _ { 2 }$ 增加时，所有形态学操作结果都明显的改善，且参数 $k _ { 1 }$ 变化对形态学操作的影响比 $k _ { 2 }$ 变化的影响大。另外，当参数 $k _ { 1 }$ 减小而 $k _ { 2 }$ 增加时，膨胀操作和腐蚀操作后的图像相似性增大。无论形态学操作使目标收缩还是膨胀，在操作之后，彩色目标及边缘均变得更加平滑，达到了彩色图像处理的预期目标。

# 3.2彩色形态学的对比实验

![](images/5f011bc6f66b41bbc9d5b1acd5764049de9b70553d984f447fb8319afa134968.jpg)  
图8高分辨率遥感影像

从图9\~12可以看出模糊相似性测度的参数 $k _ { 1 }$ 和 $k _ { 2 }$ 对彩色形态学操作的影响情况。对于同样的彩色影像，采用相同的彩色形态操作，但由于选取参数 $k _ { 1 }$ 和 $k _ { 2 }$ 的不同，使得最终得到的彩色图像处理结果不同，符合人类视觉感觉的模糊性和不确定性的要求。通过对形态学操作的结果图像比较，可以看出当$k _ { 1 } { = } 0 . 0 0 1$ 和 $k _ { 2 } { = } 0 . 8$ (图9(c)-12(c))时，所有的形态学操作(腐蚀、

为了将提出的彩色形态学与由灰度形态学拓展的彩色形态学、基于区域排序的形态学进行对比，仍选择图8所示的IkonoS彩色遥感影像作为测试图像。灰度形态学拓展的彩色形态学就是将彩色影像看成由红、绿、蓝三幅单色图像构成，利用灰度形态学分别处理这三幅单色图像，最后用形态学处理结果还原彩色影像；基于区域排序的形态学就是以当前区域（区域为 $3 { \times } 3$ 像素）中矢量的梯度进行排序并将梯度最小、最大的矢量作为形态学输出；本文的彩色形态学操作中模糊相似性测度的参数 $k _ { 1 } { = } 0 . 0 0 1$ 和 $k _ { 2 } { = } 0 . 8$ ，结构单元为 $3 { \times } 3$ 像素。图13\~16分别为腐蚀、膨胀、开、闭运算后的结果，其中(a)彩色形态学处理结果，(b)由灰度形态学拓展的彩色形态学处理结果，(c)基于区域排序的形态学处理结果。从彩色影像处理结果可以看出，提出的彩色形态学对彩色影像处理更为细致，经过这种形态学操作可以使彩色目标边缘更加平滑，而且能很好地保留原图像的细节特征，不会使图像失真，如图13(a)-16(a)所示；采用拓展灰度形态学方法的彩色形态学，处理后有些图像细节丢失，目标边缘不平滑，造成影像失真，如图13(b)-16(b)所示；基于区域排序的形态学,由于腐蚀操作采用梯度最接近的矢量，所以效果较好，但其他涉及到膨胀的操作，其效果均不理想，如图

13(c)-16(c)所示。通过以上对比实验，可以清晰的看出本文提出的彩色形态学不但能对彩色影像进行有效处理，而且具有较好的处理效果，这将为彩色影像的目标提取、滤波、分割等奠定坚实基础。另外，这种彩色形态学还可以通过改变参数 $k _ { 1 }$ 和 $k _ { 2 }$ 及移动窗口大小，得到更加切合实际的处理结果。这也充分说明了这种彩色形态学的有效性和实用性。

![](images/e8a388c270d06e62bd58526283e6b4a68215a8bac6144a8aa212765a5e111e53.jpg)  
图9采用不同参数组合进行腐蚀操作

![](images/b854103eec3194307667d71dce8a5336bf41ff3157a0f0b9e1a69a690a7ed033.jpg)  
图10采用不同参数组合进行膨胀操作

![](images/8fde107e0c78297e1081002d389d5e2856de4c0e04b4ec9604af660a55c27ff0.jpg)  
图11采用不同参数组合进行开操作

![](images/349c6b9888ce55567a8ec90e457f769c345ad31af70fe1ef1af1b15d5e9acad5.jpg)  
图12采用不同参数组合进行闭操作

# 3.3彩色形态学操作性能分析

为了评价本文提出的彩色形态学操作性能，这里以形态学操作后对彩色影像的灰度及彩色信息影响进行量化分析。从灰度形态学理论而言，将图13-16所示用三种不同形态学方法进行腐蚀、膨胀、开、闭等操作后的彩色影像转换成其对应的灰度图像，求其与原彩色影像所对应灰度图像相似性测度的平均值，如图17所示，可以清楚的看出，腐蚀、膨胀、开、闭等操作均能改变原影像所对应灰度信息，本文提出的彩色形态学和由灰度形态学拓展的彩色形态学，完成同样形态学处理后的灰度图像与原灰度图像有更高的相似性和一致性，且本文提出的彩色形态学对彩色影像的改变更平缓一些，即更有利于影像灰度信息的细节保持，而基于区域排序的形态学在灰度值改变上不是很理想。

![](images/e99387da89619dedf981591727b93b4f68e03dbbeebfde2d6ea2e180b491f2d2.jpg)  
图13腐蚀操作结果对比

![](images/3bbc40a25915ac4b5cbc4f74205313dab6284ffe4d80ff290f87b13ad60c915d.jpg)  
图14膨胀操作结果对比

![](images/eb67056efa358d4b2f3f617659ed6255c2f2ff0be83056b3760205cd98d6babb.jpg)  
图15开操作结果对比

![](images/063d236ddd641200a25c21b5a492eea52d20d777e7762bb4a086f0ef88a53016.jpg)  
图16闭操作结果对比

另外，从彩色影像相似性角度进行对比，计算图13-16所示的形态学操作结果与原影像对应像素的模糊相似性测度平均值，即腐蚀-原图、膨胀-原图、开-原图、闭-原图，评价其与原影像的相似性程度，如图18所示，可以看出，腐蚀、膨胀、开、闭等操作均能改变原影像，但本文提出的彩色形态学操作后相似性最高，也就是说，在达到同样彩色影像处理目标的情况下，本文提出的形态学操作，对原影像细节特征改变最小，这样就可以极大降低因操作而造成彩色影像失真的现象，这个量化分析结果与从视觉上观察图13\~16的形态学操作结果相符合。

通过以上操作结果的量化对比，可以看出本文提出的基于模糊相似性的彩色形态学对影像进行处理时，不但能与经典的二值及灰度形态学理论相一致，而且能很好的保持原影像的细节特征，具有较好的处理效果，这也为这种彩色形态学的推广和应用奠定了基础。

![](images/07a221cca2339591707652d59e9fb76fe032f87537ca29a6f1876dbdb7a70732.jpg)  
图17形态学操作后灰度相似性的变化

![](images/4814657aa576bc94c4c2bc73c5177c7132e904c9936421502d25007c6cfb8df9.jpg)  
图18形态学操作后模糊相似性测度变化

# 4 结束语

为了发展彩色形态学，本文依据人类的视觉感知特点，在RGB彩色空间中利用彩色矢量的距离和角度引入了一种刻画彩色矢量间关系的模糊相似性测度；然后以模糊相似性测度、上确界、下确界为基础，定义了针对彩色图像的膨胀、腐蚀、闭和开运算等彩色形态学操作；最后，通过实验对模糊相似性测度的参数及特性进行了深入的分析和研究，通过彩色形态学操作结果的分析和对比，进一步说明了提出的彩色形态学操作不但能够收缩、拓展目标并对其进行平滑处理，而且能够较大程度的保留原图像的细节特征，也充分证明了这种彩色形态学在实际图像处理中的应用价值。

# 参考文献： \\

?  
[1]王树文，闫成新，张天序，等．数学形态学在图像处理中的应用[J].计算机工程与应用,2004,32(11):89-92.  
[2]王瑜，闫沫．采用全局相似性测量的彩色图像分割[J]．信号处理,2016,32 (08): 951-959.  
[3] 陈鑫元，李筠，杨海马，等．自适应阈值图像二值化及形态学处理的FPGA 实现[J]．电子测量技术,2016,39(07):67-71.  
[4] 刘辉，张云生，张印辉，等．均匀空间色差度量的矢量形态学图像处理[J]．中国图象图形学报,2011,16(12):2145-2151.  
[5] 刁智华，赵春江，吴刚，等．数学形态学在作物病害图像处理中的应用研究[J].中国图象图形学报,2010,15(02):194-199.  
[6] 安静．基于数学形态学的图像增强算法及其应用[D].兰州：西北师范大学,2016.  
[7]李伟．基于数学形态学的边缘检测算法研究[J].计算机与数字工程,2008,11(36):20-22.  
[8]方智文，曹治国，肖阳．深度图像的目标潜在区域提取算法[J].信号处理,2016,32(2): 193-202.  
[9] 汤红忠，黄辉先，郭雪峰，等．新型彩色图像形态学处理方法[J]．计算机应用,2010,30(8):2101-2104.  
[10]徐天芝，张贵仓，贾园．基于形态学梯度的分水岭彩色图像分割[J].计算机工程与应用,2016,52(11):200-203+208.  
[11]于海燕，牛庆丽．计算机技术在图像轮廓提取中的有效应用[J].现代电子技术,2016,39(10):34-36.  
[12]肖红光，文俊，陈立福，等．一种新的高分辨率 SAR图像道路提取算法[J]．计算机工程与应用,2016,52(15):198-202+207.  
[13]郑亚惠．基于超图与数学形态学的灰度形态学新算子[D].西安：西安电子科技大学,2016.[14]甄勇，刘伟，陈建宏，等．高分辨率SAR图像舰船目标几何结构特征提取[J]．信号处理,2016,32(04):424-429.  
[15]王玉，李玉，赵泉华．基于规则划分和RJMCMC的可变类图像分割[J].仪器仪表学报,2015,36(06):1388-1396.  
[16]赵雪梅，李玉，赵泉华．结合高斯回归模型和隐马尔可夫随机场的模糊聚类图像分割[J].电子与信息学报,2014,36(11):2730-2736.  
[17]江晓亮．基于模糊聚类及活动轮廓模型的图像分割技术研究[D].成都：西南交通大学,2016.  
[18]赵泉华，赵雪梅，李玉．结合HMRF 模型的模糊 ISODATA高分辨率遥感图像分割[J]．信号处理,2016,32(2):157-166.  
[19] Xu Zeshui. On similarity measures of interval-valued intuitionist fuzzy setsand their application to pattern recognitions [J]. Journal of SoutheastUniversity,2007,4(5): 139-143.[20] Vardavoulia MI,Andreadis I,TsalidesP.Vector ordering and morphological

operations for color image processing: fundamentals and applications [J]. Pattern Analysis and Applications,2002,5(3):271-287. [21] Santini S,JainR.Similarity measures[J].IEEE Trans onPattern Analysis

andMachine Intelligence,1999,21(9): 871-883.[22]王淑青，姚伟，陈进，等．基于直方图均衡化与形态学处理的边缘检测[J].计算机应用与软件,2016,33(3):193-196.