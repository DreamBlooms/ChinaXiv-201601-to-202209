# 基于多模态牙科图像的牙体硬组织自动配准

汪伟，程斌

(上海理工大学 光电信息与计算机工程学院，上海 200093)

摘要：牙科图像由于成像模式、图像质量、不同病人之间存在差异性，导致临床应用中牙体硬组织的精确配准成为难点。针对这些问题，并根据相关研究工作，提出了一种更适用于多模态牙科图像的牙体硬组织自动配准方法。该方法基于改进的ICP算法，对多模态的牙科荧光图像和自然光图像进行分析。首先，根据多模态牙科图像的特点，算法对图像进行了预处理；其次，研究了鲁棒的特征点提取方法，即将牙体硬组织边缘选取为特征点，并同时根据口腔病理学先验知识，提取多模态图像中的病损组织区域，进一步优化了配准点集；最后，利用改进的ICP算法对齿科图像进行了配准，配准过程中对ICP的迭代策略和鲁棒损失函数进行了分析和优化。实验结果表明，该方法能更快速地收敛，且具有更好的鲁棒性和准确性。

关键词：齿科图像；多模态医学图像配准；改进ICP算法；鲁棒损失函数 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2017.11.0775

# Dental hard tissue registration based on multi-modality dental images

Wang Wei, Cheng Bin (SchoolofOptical-Electrical&ComputerEngineering,UniversityofShanghaiforScience&Technologyhanghai200093, China)

Abstract:Dentalhard tisueregistration is verychalengingduetothecomplexityofhistological structure,thevariabilityof imaging modalityand imagequality.To benefit fromtheadvantagesoftherelative works,we proposed anovel dental hard tisue auto-registration method basedon multi-modality dental images.It employed the modified ICPalgorithmand was especialleffectivefordentalfluorescenceimagingandthereflectance imaging.Thealgorithmfirstlypre-processedthedental imagesto decrease the impactofimbalance localillmination.Secondly,we investigatedarobust feature points extraction strategy,i.e.tocalculatethboundariesofhardtisseasinitialfeaturepointsetsandtofurtherextractelesionareasbased onthe prior kowledgeoforal histopathology fortherefinementoffeature points.Finally,our method executed themodified ICPalgorithm on the basisofthe special designed point-pairs rejection method and the improved registration strategy.The experimentalresults showthattheproposed method is notonlyrobust,but alsocanconverge more quicklyandachieve higher accuracy.

Key Words: dental image; multi-modality medical image registration; modified ICP algorithm; robust loss function

# 0 引言

牙体硬组织作为口腔内组织的重要组成部分，其病变常常表现为龋病、四环素牙、楔状缺损、牙隐裂、牙髓病和根尖周病等各种形式。根据我国近期口腔流行病学调查显示，当前形势不容乐观，临床工作仍面临巨大的压力[1]，因此在牙科的临床应用中，探索新的、安全、高效的齿科计算机自动辅助检测方法显得更加有意义，从而通过牙科诊疗的智能化，提高牙科医生的工作效率。

医学图像自动配准技术作为计算机自动辅助检测中的一个重要组成部分,引起了研究人员的广泛重视。具体到牙科影像处理与分析领域，需要对不同时刻的牙体硬组织区域进行配准，继而完成对病损目标的检测和跟踪处理，为临床诊断提供更多有判断价值的信息。然而，数字化的齿科视频图像大多是由牙科医生手持光学成像设备在对患者进行治疗时拍摄所得，因此在成像时不可避免地存在成像设备抖动、光照不均等问题，增加了对牙齿硬组织自动配准的难度。

本文研究了基于多模态牙科图像的牙体硬组织自动配准，其研究对象包含了由定量光导荧光技术所产生的荧光图像，以及由口腔内窥镜所获取的普通自然光图像。定量光导荧光技术的原理是利用紫外光激发牙齿组织，其主要构成物羟基磷灰石会产生自体荧光效应，而龋损组织较健康组织具有较大的散射系数，导致牙体表面出射的荧光强度会有所不同，其荧光信息是临床中龋病诊断、去腐治疗的重要参考[2][3]；而由口腔内窥镜所获取的高分辨率普通自然光图像在医生的传统视诊及手术治疗过程中起到了重要作用，在检测和诊断牙体、牙周组织及口腔黏膜的早期疾病方面有着较高的应用价值。本文通过对不同时刻或不同角度所拍摄的牙科荧光图像与自然光图像进行空间上的配准，将相同的牙体硬组织区域标记出来，从而有助于实现进一步的智能化分析。

关于多模态医学图像自动配准，相关研究人员对此提出了很多方法，按照所采用映射模型的不同，主要可分为刚体配准和非刚体配准[4]，如基于X光图像和MRI图像的刚体配准[5]和基于MRI图像和PET-CT图像的非刚体配准[等研究在临床上都取得了较好的结果。按照多模态图像匹配特征点选取方法的不同，可分为基于全局的特征匹配方法和基于局部的特征匹配方法7。其中，基于全局的特征匹配方法是基于对整体图像信息的统计结果，如基于交互信息的方法在多模态医学图像配准中得到了较多的应用[8],但此种方法容易受到图像遮挡、图像截断、干扰噪声等因素的影响。而基于局部的特征匹配法又可分为基于梯度的配准和基于边缘的配准[9][10]，与全局特征匹配法相比，其抵抗干扰的能力强，并且基于边缘的局部特征匹配法更适合于多模图像配准[7]。

由于牙科图像的特殊性，只有采取合适的配准方法，实验结果才能达到较好的鲁棒性和准确性。考虑到多模态牙科图像的特点，本文采用了基于改进ICP(iterative closest point）配准算法的多模态图像配准方法，在特征点提取和对应ICP迭代策略等方面进行了创新。

# 1 ICP算法及改进策略分析

ICP配准算法是由Besl和McKay提出[I1],该算法是一种基于目标轮廓特征点配准的算法,自1992年提出后得到了广泛的应用。经典ICP算法的原理是通过计算目标特征点集和源特征点集间的最优旋转矩阵和平移向量后，对目标特征点集进行坐标变换，使得变换后的目标特征点集合与源特征点集匹配，即使得下式的误差计算值最小：

$$
D _ { \operatorname* { m i n } } = \operatorname* { m i n } \sum _ { j = 1 } ^ { k } [ x _ { j } - y _ { j } ^ { ' } ] ^ { 2 }
$$

其中：源特征点集为 $X = x _ { i } , ( i = 0 , 1 , 2 . . . n )$ ；目标特征点集为$Y = y _ { j } , ( j = 0 , 1 , 2 . . . k )$ ；通过搜索集合 $X$ ，确定与 $y _ { j }$ 距离最短的点为最近点 $\boldsymbol { x } _ { j }$ 。经过坐标变换后的目标特征点集为$Y ^ { ' } = y _ { j } ^ { ' } , ( j = 0 , 1 , 2 . . . k )$ ，坐标变换公式如下所示：

$$
y _ { j } ^ { ' } = R _ { _ { I C P } } y _ { j } ^ { } + T _ { _ { I C P } }
$$

其中: $R _ { _ { I C P } }$ 为旋转矩阵， $T _ { _ { I C P } }$ 为平移向量。

经典ICP算法就是通过多次迭代，在每次迭代过程中，搜索每个目标特征点 $y _ { j }$ 的对应点 $\boldsymbol { x } _ { j }$ ，然后通过最小二乘法计算出 $R _ { { _ { I C P } } }$ 、 $T _ { _ { I C P } }$ ，使得 $D _ { \mathrm { m i n } }$ 最小。如果如 $D _ { \mathrm { m i n } }$ 小于某个预设的阈值，即表示正确配准的收敛准则得到满足，则迭代计算结束；否则，将此次迭代过程中的 $Y ^ { ' }$ 代替Y，进行下一次迭代，直到满足迭代收敛条件。进而完成目标点集合与源点集间的配准。经典ICP算法需要满足两个假设条件：首先是目标特征点集合和源特征点集合存在包含关系；其次是对应点搜索过程中，欧式距离最近的点对即为对应点[12]。

经典ICP算法在一般情况下，可以具备较好的收敛性，取得较精确的配准结果。但此算法也存在一些不足之处，主要体现在对应点的搜索方面，一方面是对应点搜索所需计算量较大、计算复杂度高(理想状态下为 $O ( N _ { p } \log N _ { x } )$ )[11];另外一方面,在实际应用过程中，由于经典ICP算法所需的两个假设条件无法满足，导致了在每次迭代过程中的对应点搜索结果错误，影响了最终的配准精度。

针对经典ICP算法所存在的不足，许多研究人员从不同角度提出了各种改进方案。Nishino对不同的改进措施进行了归纳总结，主要有三类：配准点集筛选、配准策略以及误差函数求解[13]。

在配准点集筛选方面，主要是研究如何有效地对对应点集进行优选，以减少计算的特征点数。一种是用采样的方法来对配准点集进行筛选，当前主要有一致采样法[14]和随机采样法[15];另一种方法是优选出能包含目标某些特征的点来进行配准，如利用图像的梯度信息[16]和边缘信息[17]来做配准点集。

在配准策略方面，主要是研究如何有效、准确地将目标特征点集和源特征点集一一对应。一类方法是着重于对特征度量的选取。如经典ICP算法是采用了目标特征点和源特征点间的欧氏距离作为特征度量，改进的ICP算法考虑了新的特征度量方法，比如用点到面的距离来建立目标函数[18][19]、利用Hausdorff距离来描述两点集相似程度的距离度量[23]、利用几何特征（主要有法向量、曲率等特征)来优化特征度量[211；另外，为了减少一些偏差较大的点的干扰，一些鲁棒损失函数也被引入到特征度量中，如Huber 函数[22]、Tukey'sBiweigh 函数[23]等。

在配准策略方面，另一类方法是侧重于研究提高对应点对的搜索速度。在对应点对的搜索算法方面，Greenspan 提出的近似多维二元搜索树算法[24]、Blais 和Neugbeuaer采用反向定标技术的投影搜索算法[25]等有了一定的改进。

在误差函数求解方面，应用最广泛的方法有两种，一是奇异值分解的方法[26]，二是单位四元数法[27]。

通过对ICP算法改进策略的分析，可看出国内外学者提出的各种改进方法分别在配准精度和速度上进行了提升。然而，由于牙科图像的特殊性，针对牙科图像配准方面的研究较少，传统的ICP配准方法难以取得较好的效果。因此，本文将主要从配准点集筛选、配准策略的制定方面来进行深入研究，提出适合多模态牙科图像的改进ICP算法，以用于牙齿硬组织的自动配准。

# 2 基于多模态牙科图像的牙体硬组织配准方法

# 2.1算法流程

本文所采用的适合多模态牙科图像的牙体硬组织自动配准算法为非监督的方法，可作为计算机自动辅助检测中的重要组成部分，为进一步的后处理作准备。其算法流程如图1所示。

![](images/baee68a5eb258c4618932fb77c431804ddf925ae8639dc761c0e57552bac9c58.jpg)  
图1改进ICP 算法主流程

该算法的具体步骤简述如下：

a)将输入待配准的荧光图像和自然光图像进行图像预处理，作图像去噪及均衡化处理，排除部分光照及噪声的干扰；

b)在多模态牙科图像中，结合数学形态学对牙体硬组织完成自动分割；

c)对提取出的牙齿硬组织区域进行处理,提取出边缘区域作为特征点;

d)对牙齿硬组织区域的边缘特征进行筛选，形成初始配准点集；

e)利用ICP算法对其进行迭代，当迭代结果满足预设的精度要求，或者达到预设的迭代次数，则初次迭代结束；

f)如果初次迭代结果满足精度要求、初次迭代结束后，则计算最优参数，完成图像配准；

g)如果初次迭代结果不满足精度要求，结合数学形态学以及口腔病理学先验知识，在荧光图像和自然光图像中，优选出部分典型病损组织区域；

h)对优选出的病损组织进行处理，选取出特征点，增加到初始的配准点集中去，并对初始的配准点集进行优化；

i)设置鲁棒损失函数;

j)利用ICP算法再次进行迭代，当迭代结果满足预设的精度要求，或者达到预设的迭代次数，则二次迭代结束。

1)二次迭代完成后，计算最优参数，完成图像配准。

# 2.2多模态图像预处理

由于牙科图像的成像特点，在不同的图像之间存在光照差异性的问题，故需要对图像作均衡化处理，而同时也要考虑实时性方面的要求。本文中所处理的图像原始输入格式为RAW格式，按拜尔阵列分布处理后，转换为24位RGB格式。考虑到本研究课题允许图像预处理后带来的部分颜色失真，论文中对多模态的自然光图像和荧光图像皆采用了如下图像均衡化算法：

假设原输入齿科图像为 $f ( x , y )$ ，其对应 RGB 通道为$f _ { R } ( x , y )$ 、 $f _ { G } ( x , y )$ 、 $f _ { B } ( x , y )$ ，其中 $f _ { G } ( x , y )$ 的灰度变化区间为 $[ 0 , f _ { \mathrm { G m a x } } ]$ ；经过均衡化处理后，输出图像为 $g ( x , y )$ ，其对应 RGB 通道为 $g _ { R } ( x , y ) \circ . \quad g _ { G } ( x , y ) \circ . \quad g _ { B } ( x , y )$ ，其中期望$g _ { G } ( x , y )$ 的灰度范围为 $[ 0 , g _ { G \operatorname* { m a x } } ]$ ，则变换表达式为

$$
g _ { _ G } ( x , y ) = \left\{ \begin{array} { l r } { \displaystyle { \frac { g _ { _ { G \mathrm { m a x } } } } { T _ { _ { N } } } \bullet f _ { _ { G } } ( x , y ) } } & { f _ { _ G } ( x , y ) \leq T _ { _ { N } } } \\ { g _ { _ { G \mathrm { m a x } } } } & { T _ { _ { N } } < f _ { _ { G } } ( x , y ) \leq f _ { _ { G \mathrm { m a x } } } } \end{array} \right.
$$

$$
\begin{array} { l } { { g _ { _ B } ( x , y ) { = } \displaystyle \frac { g _ { _ { G \mathrm { m a x } } } } { T _ { _ N } } f _ { _ B } ( x , y ) } } \\ { { \displaystyle g _ { _ R } ( x , y ) { = } \displaystyle \frac { g _ { _ { G \mathrm { m a x } } } } { T _ { _ N } } f _ { _ R } ( x , y ) } } \end{array}
$$

其中: $T _ { \scriptscriptstyle { N } }$ 值为自适应阈值，由对 $g _ { G } ( x , y )$ 进行灰度直方图统计后得出，用于保证了对齿科图像的有效均衡化。

# 2.3牙体硬组织分割

2.3.1自然光图像牙体硬组织分割

根据牙科图像的特点，本小节充分利用图像的灰度信息和颜色特征，并结合数学形态学对预处理后的自然光图像进行分析，完成了牙体硬组织的自动分割。具体算法步骤描述如下：

1）背景区域自动分割，确定背景区域点集 $B _ { s }$

假设 $b \big ( i , j \big )$ 为 $B _ { s }$ 所对应的二值图像中 $( i , j )$ 处的像素，则

$$
b ( i , j ) = \left\{ \begin{array} { l r } { 1 } & { g _ { _ R } ( i , j ) < \mathrm { T _ { R } } \ \& \ g _ { _ G } ( i , j ) < \mathrm { T _ { G } } \& g _ { _ B } ( i , j ) < \mathrm { T _ { B } } } \\ { 0 } & { \qquad \quad \ \mp / \ \pmb { \mu } } \end{array} \right.
$$

其中 $g _ { R } ( i , j ) \setminus g _ { G } ( i , j )$ 和 $g _ { B } ( i , j )$ 分别为预处理后自然光图像的R、G、B 通道在 $( i , j )$ 处的灰度值； $T _ { \scriptscriptstyle R }$ 、 $T _ { \scriptscriptstyle G }$ 和 $T _ { _ B }$ 为预设阈值，即为了满足实时性的要求,背景区域的分割是通过对RGB三个颜色通道设置全局阈值来完成的。

2）牙体软组织区域自动分割，确定对应点集 $G _ { s }$ 牙体软组织区域的获取主要由形态学中的重构操作来获得，形态学的重构操作不但克服成像过程中光照不均的干扰，也对存在图像弱边缘的牙体软组织区域有很好的效果。按照式(7)可得重构操作后的初步结果 $G _ { s } ^ { ' }$ 。

$$
G _ { s } ^ { ' } = i m r e c o n s t n c t ( G _ { \scriptscriptstyle M a r k e r } , G _ { \scriptscriptstyle M a s k } )
$$

其中： $G _ { M a r \mathrm { k e r } }$ 和 $G _ { M a s k }$ 的计算充分考虑了自然光图像中的强度和色度信息，具体可由式(8)和(9)分别进行定义：

$$
G _ { _ { M a r k e r } } ( i , j ) = \left\{ \begin{array} { r l r } { 1 } & { \mathrm { ~ g _ { R } } ( i , j ) > \mathrm { T _ { R 2 } } \& ~ \frac { \mathrm { g _ R } } { g _ { G } ( i , j ) } > \mathrm { T _ { R G } } } \\ { 0 } & { } & { \quad \mathrm { ~ j \mathrm { \notin \mathcal { M } } } } \end{array} \right.
$$

1

$$
G _ { _ { M a s k } } ( i , j ) = \left\{ \begin{array} { l l } { 1 } & { \frac { g _ { _ R } ( i , j ) } { g _ { _ G } ( i , j ) } > \mathrm { T } _ { \mathrm { R G } } } \\ { 0 } & { \mp \mathrm { M } \uparrow \mathrm { H } } \end{array} \right.
$$

其中： $T _ { R 2 }$ 和 $T _ { R G }$ 为预设阈值， $g _ { R } ( i , j )$ 和 $g _ { G } ( i , j )$ 为预处理后自然光图像的R、G通道在 $( i , j )$ 处的灰度值。经过重构操作后的初步结果 $G _ { s } ^ { ' }$ 还需要进一的优化，即删除 $G _ { s } ^ { ' }$ 中面积过小的区域,最终获得点集 $G _ { s }$ 。

3）牙体硬组织区域自动分割，确定初步点集 $T _ { s } ^ { ' }$

通过对背景区域和牙体软组织区域的去除，可以获得牙体硬组织区域的初步点集，其计算式如下所示：

$$
T _ { s } ^ { ' } = { \overline { { B \cup G } } }
$$

4）通过对牙体硬组织分割区域优化，获得最终点集 $T _ { s }$ 在获取到初步点集 $T _ { s } ^ { ' }$ 后，还需要进一步的形态学操作来对分割结果进行优化，本算法中采用的主要策略为对 $T _ { s } ^ { ' }$ 所对应的二值图像作孔洞填充操作，保证所获得的牙体硬组织区域的完整性，最终获得点集 $T _ { s }$ 。

# 2.3.2荧光图像牙体硬组织分割

根据由定量光导荧光技术所产生的荧光图像的特点，牙体软组织在荧光图像上呈现出的强度很低，与背景区域的荧光成像特性十分类似。因此，荧光图像牙体硬组织分割方法改进如下：

a)在荧光成像中，将软组织区域和背景区域归为一类，并采用与2.3.1节中所阐述的与 $B _ { s }$ 相同的方法来计算，即采用全局阈值来完成背景区域与牙体软组织区域的自动分割;

b)利用与式(10)相同的计算方法，去除背景区域和牙体软组织区域后，可获得初步点集 $\boldsymbol { T } _ { t } ^ { \prime }$ ;

c)采用与2.3.1节中相同的形态学优化方法对 $\boldsymbol { T } _ { t } ^ { \prime }$ 进行处理，获得优化后的最终牙体硬组织区域点集 $T _ { t }$ 。

# 2.4病损组织特征区域优选

牙齿硬组织病也常常表现为龋病、四环素牙、楔状缺损、牙隐裂、牙髓病和根尖周病等，本小节中的病损组织区域优选并不是要检测出上述所有情况，而仅仅是分割出具有色素沉着的病损区域。这些区域边界清晰、在多模态图像中皆成像特征明显，从而保证了所选取特征点的鲁棒性，有助于牙齿硬组织自动配准的精度提升。

# 2.4.1自然光图像病损组织分割

自然光图像中病损组织区域点集 $\vec { L _ { s } } ^ { " }$ 的获取骤如下所示：

a)对预处理后的自然光图像的G通道图像 $g _ { G } ( x , y )$ 作特定数学形态学操作处理，即执行基于灰度图象的孔洞填充操作，通过式(11)可获得中间结果 $g _ { \scriptscriptstyle G } ^ { \prime } ( x , y )$ ：

$$
g _ { G } ^ { ^ { \cdot } } ( x , y ) = i m f i l l ( g _ { G } ( x , y ) )
$$

b)计算初步病损组织区域点集 $L _ { s } ^ { ' }$

$$
\begin{array} { r l r } { \dot { L _ { s } } ( x , y ) = \left\{ \begin{array} { r l r } { 1 } & { { } } & { \quad \boldsymbol { g } _ { _ G } ^ { * } ( x , y ) - \boldsymbol { g } _ { _ G } ( x , y ) > T _ { _ { G 2 } } } \\ { 0 } & { { } } & { \quad \quad \mathbb { H } ^ { \cdot } \dot { \boldsymbol { \Xi } } \times \nabla } \end{array} \right. } \end{array}
$$

其中 $T _ { G 2 }$ 为预设阈值。

c)基于牙体硬组织区域的自动分割结果 $T _ { s }$ ，对初步病损点集进行处理，获得最终病损组织区域点集 $\vec { L _ { s } }$

$$
\begin{array} { r } { L _ { s } ^ { ' } = L _ { s } ^ { ' } \cap T _ { s } } \end{array}
$$

# 2.4.2荧光图像病损组织分割

荧光图像中病损组织区域点集 $\vec { L _ { t } }$ 的获取步骤同 $\vec { L _ { s } } ^ { " }$ 的计算方法，即与2.4.1节中描述的方法类似。

# 2.4.3病损组织特征区域优选

由于自然光图像和荧光图像成像模式的差异性，对病损组织的成像结果也存在一定的差异性，需要对获得的 $\ddot { L _ { s } }$ 和 $\ddot { L _ { t } }$ 区域作进一步的优选，其主要优选规则如下：

假设病损组织特征区域 $s _ { 1 } \in \ddot { L } _ { s } ^ { " }$ ， $t _ { 1 } \in L _ { t } ^ { " }$ ； $s _ { 1 }$ 对应的病损面积为 $A r e a _ { S _ { 1 } }$ ，其所在的牙体硬组织面积为 $A r e a _ { { _ T _ { S 1 } } }$ ； $t _ { 1 }$ 对应的病损面积为 $A r e a _ { t _ { 1 } }$ ，其所在的牙体硬组织面积为 $A r e a _ { { _ T _ { t 1 } } }$ 。如果要使 $ { s _ { 1 } } \in L _ { s }$ 和 $t _ { 1 } \in L _ { t }$ 成立，必须满足下式：

$$
\left| \frac { A r e a _ { s _ { 1 } } } { A r e a _ { T _ { s 1 } } } - \frac { A r e a _ { t _ { 1 } } } { A r e a _ { T _ { t 1 } } } \right| < T _ { A r e a } \cdot \frac { A r e a _ { s _ { 1 } } } { A r e a _ { T _ { s 1 } } }
$$

其中: $T _ { A r e a }$ 为预设阈值。病损组织特征区域经过优选后，从自然光图像中计算出病损组织区域优选特征点集 $L _ { s }$ ，从荧光图像中

计算出对应优选特征点集 $L _ { \mathrm { \Lambda } _ { t } }$ 。

# 2.5配准点集选取及优化

# 2.5.1初始配准点集生成

通过自动分割出牙体硬组织区域后,接下来就是筛选出初始配准点集。通过对测试数据集内多模态牙科图像特点的分析，本文中初始配准点集选取策略将主要着重于牙体硬组织的边缘特征点。初始配准点集筛选步骤如下：

1)提取牙体硬组织区域点集 $T$ 对应的轮廓特征点集 $E$

在常用的边缘检测算法中，相比于Canny 算子，Sobel算子虽然检测精度较低，但具有较低的运算复杂度、对噪声不敏感。故综合考虑下来，本文中采用Sobel算子来对牙体硬组织区域点集 $T$ 进行处理：

$$
E = S o b e l \left( T \right)
$$

2)配准点集采样及初步配准点集生成

$$
M o d e l = S a m p l e _ { E } ( E _ { s } )
$$

$$
D a t i \stackrel { \cdot } { a } = S a m p l e _ { E } ( E _ { t } )
$$

其中: $E _ { s }$ 和 $E _ { t }$ 分别为自然光图像和待配准的荧光图像所对应的牙体硬组织区域轮廓特征点集； $S a m p l e _ { E } ($ )为预设的采样函数，一般可为均匀采样或者随机采样函数。

牙体硬组织轮廓点集经过采样处理后，则分别得到对应于自然光图像的初始配准点集Model，和对应于待配准的荧光图像的初始配准点集Data'。

# 2.5.2配准点集优化

初始配准点集通过ICP算法迭代后，如果配准精度不满足要求，则需要对配准点集进行优化。通过实验分析，本文发现由于多模态牙科图像的固有成像特点，不可避免地会存在偏差较大的牙体硬组织区域轮廓特征点集，继而会影响配准的精度，使得ICP算法迭代容易陷入局部极值。

而与牙体硬组织区域相比，本文又优选了具有色素沉着、在多模态图像中特征稳定、边缘清晰的病损区域为代表，并提取其特征点 $L$ 来作为匹配点，从而保证配准特征点选取的鲁棒性。

本文中采用了如下策略对初步配准点集进行优化：

$$
M o d e l = M o d e l \cup S a m p l e _ { L } ( L _ { s } )
$$

$$
D a t a = D a t a \cup S a m p l e _ { L } ( L _ { t } )
$$

其中： $L _ { s }$ 和 $L _ { \mathrm { \Lambda } _ { t } }$ 分别为自然光图像和待配准的荧光图像所对应的优选病损组织区域特征点集；SampleO为预设的采样函数，一般可为均匀采样或者随机采样函数。优选病损组织区域特征点集经过采样处理后，将其与初始配准点集合并，则分别得到对应于自然光图像的优化配准点集Model，和对应于待配准的荧光图像的优化配准点集Data。

# 2.6 ICP 算法迭代

2.6.1ICP迭代策略

本算法中的ICP迭代策略采用两轮ICP迭代法，一般第一轮迭代可以满足 $50 \% { \sim } 6 0 \%$ 的配准情况，引入第二轮的ICP算法迭代，虽然可以进一步提高配准精度，但是也增加了计算量。

第一轮ICP迭代的具体策略描述如下：

a)获取对应于自然光图像的初始配准点集Model，和对应于荧光图像的初始配准点集Data'；

b)使用ICP算法进行第一轮迭代。在第一轮迭代的每次迭代中，于Model点集中寻找与Data最近点当作同源点，并且对这些同源点进行距离最小化，同源点距离最近时的变换参数则认为是本次迭代中的最优参数 $R _ { _ { I C P } }$ 、 $T _ { _ { I C P } }$ ，并作用于目标点集；第一轮迭代过程中，最小距离计算采用欧式距离函数;

c)经过多次迭代后，第一轮迭代结束，其终止条件为：

迭代次数最多不超过预设值 $C o u n t _ { 1 }$ ：

配准精度小于预设值 $R M S E _ { _ { T 1 } }$ 。

d)如果第一轮迭代结束后，配准精度小于预设值 $R M S E _ { _ { R 1 } }$ ，则第一轮迭代所得的变换参数为最优参数，图像配准结束。

第二轮ICP迭代的具体策略描述如下：

a)如果第一轮迭代结束后，配准精度大于预设值 $R M S E _ { _ { R 1 } }$ ，则对配准点集进行优化，于多模态牙科图像中进一步优选出病损组织特征点集，得到优化后的配准点集Model和Data；

b)使用ICP算法进行第二轮迭代。在第二轮迭代过程中，会先设定鲁棒损失函数；然后在每次迭代中，于Model点集中寻找与Data最近点当作同源点，计算最优参数 $R _ { _ { I C P } }$ 、 $T _ { _ { I C P } }$ ，并作用于目标点集；

c)经过多次迭代后，第二轮迭代结束，其终止条件为：

迭代次数最多不超过预设值 $C o u n t _ { 2 }$ ：

配准精度小于预设值 RMSET2。

d)第二轮迭代结束后，得到最终的配准结果。

# 2.6.2鲁棒损失函数分析

经典ICP算法中，在利用最小二乘法对配准点对计算最优变换矩阵时，一般用的是欧氏距离平方和最小来进行求解。除此方法外，文献[23]中也介绍了一些鲁棒损失函数，可以减少偏差较大的点的干扰，有助于ICP算法迭代精度的提高。

1）Huber函数

$$
\rho _ { H u } ( r ) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 } r ^ { 2 } } & { i f \left| r \right| \leq \kappa _ { H u } } \\ { \displaystyle \kappa _ { H u } \left| r \right| - \frac { \kappa _ { H u } ^ { 2 } } { 2 } } & { i f \left| r \right| > \kappa _ { H u } } \end{array} \right.
$$

2）Tukey'sBiweigh 函数

$$
\rho _ { T u } ( r ) = \left\{ \begin{array} { c c } { { \displaystyle \kappa _ { T u } ^ { 2 } \left\{ 1 - \left( 1 - \frac { r ^ { 2 } } { \kappa _ { T u } ^ { 2 } } \right) ^ { 3 } \right\} } } & { { i f \left| r \right| \leq \kappa _ { T u } } } \\ { { \displaystyle \frac { \kappa _ { T u } ^ { 2 } } { 6 } } } & { { i f \left| r \right| > \kappa _ { T u } } } \end{array} \right.
$$

3）Cauchy函数

$$
\rho _ { C a } ( r ) = \frac { \kappa _ { C a } ^ { 2 } } { 2 } \log \left( 1 + \left( \frac { r } { \kappa _ { C a } } \right) ^ { 2 } \right)
$$

其中 $r$ 指的是残差， $\kappa _ { H u }$ 、 $\kappa _ { T u }$ 和 $\kappa _ { { C a } }$ 为预设值。

# 3 实验结果与分析

# 3.1图像测试数据库及算法评价体系

本文中所采用的图像测试数据库由开发数据集和测试数据集组成。其中，开发数据集共包含600余张自然光图像与荧光图像，全部是临床中通过口腔内窥镜和定量光导荧光设备采集而成，处理后所得的图像为24位RGB格式，分辨率为 $1 0 2 4 \times 7 6 8$ 共计300余组开发用例。

测试数据集由100张图像构成，分别是50张自然光图像和50张对应的荧光图像；测试数据集中，每个测试样本至少包含平移、旋转或者缩放中的一种情况；基于各种情况实际发生的概率，测试数据样本中，平移情况占 $60 \%$ ，旋转情况占 $30 \%$ 缩放情况占 $10 \%$ 。

利用改进算法对测试数据集处理后，本文主要从两个方面来对算法进行定量评估，即ICP的迭代收敛速度和配准精度。其中算法收敛速度和计算复杂度、迭代次数相关；配准精度则继续沿用均方根误差（RootMean Square Error,简称RMSE）这一通用评估方法来进行，RMSE计算表达式如下：

$$
\sigma = { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } d _ { i } } { \displaystyle n - 1 } } }
$$

其中：n为测量次数， $d _ { i }$ 为配准后源和目标点集之间欧氏距离的测量值与平均值的偏差。

# 3.2实验结果

# 3.2.1经典算法实验结果

建立了图像测试数据库及算法评价体系后，本文利用经典ICP算法对测试数据库中的图像进行了实验，经典算法仅用ICP算法的传统迭代策略，同时在利用最小二乘法对配准点集计算最优变换矩阵时，采用欧式距离的平方和最小来进行求解，未考虑鲁棒损失函数的设定。实验表明对于 $50 \% \sim 6 0 \%$ 左右的情况，经典算法可以取得较为满意的结果。

以图2中的自然光图像和荧光图像为例，对图像中牙体硬组织区域的提取结果如图2(c)和(d)所示，其对应的初始特征点集为图2(e)和(f)；图2(g)和图2(h)分别为配准前和配准后的牙体硬组织边缘坐标图像，其中红色曲线为自然光图像的牙体硬组织边缘轮廓，黄色曲线为荧光图像的牙体硬组织边缘轮廓，蓝色曲线为配准后的荧光图像牙体硬组织边缘轮廓；图2(i)为ICP配准后的均方根误差曲线，横坐标为ICP的迭代次数，纵坐标为RMSE值除以1000。

。。(a）自然光图像 (b)荧光图像  
DD  
(c)a 图牙体硬组织区域 d)b图牙体硬组织区域  
O  
(e)a 图初始特征点 (f)b 图初始特征点  
700 700  
600 600  
500 500  
400 400  
300 300  
200 200  
100 100  
200 400 600 800 1000 200 400 600 800 100  
(g）配准前坐标图 (h）配准后坐标图0.040.0350.0250.020．01(i)RMSE 结果图

图2的实验中，主要参数设置如下：对于自然光图像，背景区域自动分割过程中 $T _ { \scriptscriptstyle R }$ 、 $T _ { \scriptscriptstyle G }$ 和 $T _ { _ B }$ 都选取为40，而荧光图像中对应参数值为20；牙体软组织区域自动分割过程中 $T _ { R G }$ 选取为 $1 4 0 , T _ { R 2 }$ 选取为45;病损组织自动分割过程中 $T _ { G 2 }$ 选取为7；对于病损组织特征优选过程中， $T _ { A r e a }$ 选取为0.3；ICP迭代过程中迭代收敛条件设置为：最大迭代次数不超过40，配准精度RMSE小于预设值0.000001。

# 3.2.2迭代策略实验

由于牙科图像的多模态成像特点，牙体硬组织区域会存在成像差异性，进而会影响到配准特征点的选取，从而影响到ICP算法的配准精度。针对这种情况，本实验基于经典算法的传统迭代策略，对ICP的迭代策略进行了修正。结合数学形态学以及先验知识，在荧光图像和自然光图像中，首先优选出部分病损组织区域，然后对配准点集进行了优化，进而通过新的迭代策略保证了算法的精度。

图3为一典型例子，图3(a)和(b)对应于自然光图像和荧光图像；初始特征点计算如图3(c)和(d)所示；图3(e)和(f)为经过优化过后的特征点集，增加了优选的病损区域特征；图3(g)和(h)分别为配准前的特征点坐标图象和应用改进算法配准后的坐标图像，不同颜色曲线定义与图

2中的设置相同；图3(i)对

首次ICP迭代和二次ICP迭代配准后的均方根误差进行了比较。

(a)自然光图像 (b)荧光图像  
O  
陸(e)a图优化特征点 (f)b 图优化特征点  
700 700  
600 600  
500 500  
400 400  
300 300  
200 200  
100 100200 400 600 800 1000 200 400 600 800 1000(g）配准前坐标图 (h）配准后坐标图（迭代策略改进法）0.05改进ICP-第一轮迭代结果0.045 改进ICP-第二轮迭代结果0.040.0350.030.0250.020.0150.0120 25 30 35 40(i)RMSE 结果比对图

由实验结果比较可知，对于图3中的典型例子，通过迭代策略改进后，其RMSE值由首次迭代中的结果19.347下降到二次迭代中的结果14.181。图3中的主要参数设定同图2例，仅ICP迭代策略部分参数特别设置如下：ICP迭代过程中Count、Count都设置为40， $R M S E _ { T 1 }$ 和 $R M S E _ { T 2 }$ 都设置为0.000001， $R M S E _ { R 1 }$ 设置为0.012。

# 3.2.3鲁棒损失函数实验

理论上鲁棒损失函数可以减少偏差较大的配准点的干扰，如果在ICP算法的再次迭代中，选用合适的鲁棒损失函数来替代欧式距离，可以在一定程度上提高配准的精度。

本次实验中，本文将在相同的ICP迭代参数设定下,选取典型的三组测试用例来对不同的鲁棒损失函数进行评估，分别包含了牙体硬组织颊面、舌面和咬合面三种情况，其自然光图像分别对应于图4中的(a)(d)和(g)图，荧光图像则分别对应(b)(e)和(h)图；迭代完成后利用RMSE值大小来判断配准准确率，进而分析其对ICP配准精度的影响。

![](images/0852422189815dcfc37eac496c3dc95b555b35ec8a9bd1ca8d2dae09ca608bed.jpg)  
图3改进迭代策略算法实验结果  
图4不同鲁棒损失函数评估实验结果

对应于三组测试数据所得的误差值如表1所示，由数据本文可以看出，其他三类鲁棒损失函数确实可以减少对应特征点集在坐标上的差值，有效地提高了点集的配准率。三类鲁棒损失函数实验效果差别不大，其中Tukeybi-weight函数在总体上取得了最小的配准误差，在图4(c)(f)和(i)中详细展示了三组采用Tukeybi-weight函数所获得的配准结果。

表1利用不同鲁棒函数的配准误差  

<html><body><table><tr><td rowspan="2"></td><td colspan="3">RMSE值</td></tr><tr><td>组1图 4(a),(b)</td><td>组2图</td><td>组3图 4(g),(h)</td></tr><tr><td>改进ICP 算法-欧式距离</td><td>10.633</td><td>4(d),(e) 13.363</td><td>12.132</td></tr><tr><td>改进ICP 算法-Huber 函数</td><td>7.006</td><td>9.161</td><td>11.586</td></tr><tr><td>改进ICP 算法-Tukey's Biweigh 函数</td><td>0.462</td><td>9.083</td><td>11.522</td></tr><tr><td>改进ICP 算法-Cauchy 函数</td><td>6.789</td><td>9.101</td><td>11.515</td></tr></table></body></html>

# 3.2.4实验结果分析与比对

本小节的实验将基于50个测试用例的数据库来对算法进行评测，计算出这50组图像的平均RMSE值，并将本文中的改进ICP算法与经典ICP算法对比，所绘曲线如图5所示。

![](images/1b32ec665753422a00164565eb954ec1f40354082a42a03e019b53e16c54231c.jpg)  
图5RMSE平均值对比曲线图

图5中，红色虚线为经典ICP算法对应的RMSE结果曲线；三条其他颜色的点线为改进ICP算法的RMSE结果曲线，分别对应于ICP再次迭代时采用不同的鲁棒损失函数设置。由图中可直观地看出，改进ICP算法的收敛速度更快，配准平均误差更小；ICP再次迭代时，三类鲁棒损失函数实验效果差别不大，而采用 Tukey bi-weight 函数可以取得最小的RMSE 值。

表2还对50组图像的RMSE值在不同算法下的实验结果做了统计。表2中第一列对应于不同的实验方法，后面三列分别为RMSE的中值、平均值和均方差值。由表2可看出，改进ICP算法的RMSE值所对应的各项指标均小于经典ICP算法;而 ICP 算法再次迭代时，鲁棒损失函数选用Tukeybi-weight 函数时，测试算法库所得的实验效果最佳。

表2算法对比数据表  

<html><body><table><tr><td rowspan="2"></td><td colspan="3">RMSE值</td></tr><tr><td>中值</td><td>平均值</td><td>均方差值</td></tr><tr><td>经典ICP 算法</td><td>26.137</td><td>24.443</td><td>14.415</td></tr><tr><td>改进ICP 算法-Huber函数</td><td>11.891</td><td>17.751</td><td>14.341</td></tr><tr><td>改进ICP 算法-Tukey's Biweigh 函数</td><td>11.854</td><td>17.637</td><td>14.371</td></tr><tr><td>改进ICP 算法-Cauchy 函数</td><td>11.836</td><td>17.716</td><td>14.287</td></tr></table></body></html>

# 4 结束语

本文将ICP算法应用于多模态牙科图像的自动配准,并根据其成像特点提出了改进方法,使算法具有更好的鲁棒性和准确性。在对多模态牙科图像进行了预处理后，本文首先研究了特定的特征点提取方法，将牙体硬组织边缘选取为初始特征点，有助于提高算法的鲁棒性；其次，本文应用特定的牙科图像自动分割技术，通过对病损组织的优选，进一步优化了配准点集，从而提高了算法的准确性；最后，本文利用改进的ICP算法对多模态牙科图像中的牙体硬组织区域完成了自动配准，论文中依次对ICP算法的迭代策略进行了改进，并对鲁棒损失函数进

行了分析和优化。实验结果表明，该方法能更快速地收敛，且   
具有更高的准确率。   
参考文献：   
[1]齐小秋．第三次全国口腔健康流行病学调查报告[M].北京：人民卫 生出版社,2008.   
[2]Heyducka C.Mellera C,Traneusb S,et al.A new in vivo method for measuring caries activity using quantitative light-induced fluorescence [J]. Cares Res,2006,40 (2): 90-96.   
[3]AmaechiBT,HighamSM. Quantiative light-inducedfluorescence:a potential tool for general dental assessment [J].JBiomed Opt,20o2,7(1): 7.   
[4]Hipwell JH,Vavourakis V,Han L,et al.A review of biomechanically informed breast imageregistration[J].Physics in Medicine & Biology,2016, 61 (2): R1-R31.   
[5]Mertzanidou T,HipwellJH,HanL,etal.Intensity-based MIt $\mathbf { x }$ -ray mammography registration with an integrated fast biomechanical transform [Cl// Proc of International Conference on Breast Imaging.Berlin: Springer, 2012: 48-55.   
[6]DmitrievID,Loo C E, Vogel W V,et al. Fully automated deformable registration of breast DCE-MRI and PET//CT[J].Phys.Med. Biol.,2013, 58 (4): 1221-33.   
[7]Zhao Chunyang, Zhao Huaici,LvJinfeng,et al.Multimodalimage matching based on multimodalityrobust ine segment descriptor [J]. Neurocomputing, 2016,177: 290-303.   
[8]S.Suri, P. Reinartz. Mutual-information-based registrationof terraSAR-X and ikonos imagery in urban areas [J]. IEEE Trans on Geosci. Remote Sens., 2010, 48 (2): 939-949.   
[9]Zhao Dong,Yang Yan,Ji Zhihang,et al. Rapid multimodality registration based on MM-SURF[J]. Neurocomputing,2014,131 (131): 87-97.   
[10] Pang G,Neumann U.The Gixel array descriptor(gad) for multimodal image matching [C]//Proc of IEEE Workshop on Applications of Computer Vision. 2013: 497-504.   
[11] Besl PJ,Mckay N D.A method for registration of 3-D shapes [J]. IEEE Transs on Pattern Analysis & Machine Intelligence,2002,14 (2): 239-256.   
[12] 刘承香，阮双琛，刘繁明，等．基于迭代最近点算法的地形匹配算法可 靠性分析[J].深圳大学学报：理工版,2005,22(1):22-26.   
[13]NishinoK,keuchi K.Robustsimultaneousregistrationof multiplerange imagescomprising a large number of points[J].Electronics& Communications in Japan,2004,87 (8): 61-74.   
[14] Turk G Levoy,M, Zippered polygon meshes from range images [C]// Computer Graphics Proceedings.1994: 311-318.   
[15] Masuda T,Sakaue K, Yokoya N. Registration and integration of multiple range images for 3D model construction [C]/ Proc of International Conference on Pattern Recognition.1996:879.   
[16] Weik S. Registration of3D partial surface models using luminance and depth information[C]//Proc of International Conference on Recent Advances in 3D Digital Imaging& Modeling.1997: 93.   
[17] Sappa AD,Restrepo-Specht A,Devy M. Range image registration by using an edge-based representation [C]//Proc of the 9th International Symposium on Intelligent Robotic Systems.2001:167-176.   
[18] Medioni G,Chen Y. Object modeling by registration of multiple range images [J].Image & Vision Computing,1991,10(3): 145-155.   
[19]PulliK.Multiview registration for large data sets [C]//Proc of International Conference on 3D Digital Imaging& Modeling.1999:160-168.   
[20] Ezra E,Sharir M,Efrat A.On the performance of the ICP algorithm [J]. Computational Geometry Theory & Applications,2008,41(1-2): 77-93.   
[21] Godin P,Boulanger G.Range image registration through viewpoint invariant computation of curvature [C]// Proc of International Archivesof Photogrammetry and Remote Sensing.1995:170-175.   
[22] Binder T.，Kostina E.Robust parameter estimation based on Huber estimatorin systemsof differential equations [M]//Modeling,Simulation and Optimization fo Complex Processes.Berlin: Springer,2012:13-23.   
[23] Bergstrom P,Edlund O.Robust registration of point sets using iteratively reweighted least squares [J]. Computational Optimization and Applications, 2014, 58 (3): 543-561.   
[24] GreenspanM, Yurick M.Approximate K-D tree search for efficient ICP[C]// Proc of International Conference on 3D Digital Imaging and Modeling.2003: 442-448.   
[25]魏大刚，唐常杰，段磊，等．基于最优投影和动态阈值的最近邻搜索算 法[J]．四川大学学报自然科学版,2006,43(4):777-782.   
[26]刘瑞祯，谭铁牛．基于奇异值分解的数字图像水印方法[J]．电子学报， 2001,29 (2): 168-171.   
[27]王可伟，岳东杰，王性猛．基于单位四元数的三维坐标转换新方法[J]. 测绘与空间地理信息,2014,37(11):216-218.