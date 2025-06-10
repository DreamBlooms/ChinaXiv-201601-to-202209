# 面向拷贝检测的图像哈希算法

沈麒，赵琰

(上海电力学院电子与信息工程学院，上海 200090)

摘要：为了准确、快速地将拷 贝图像识别出来，提出一种基于CS-LBP(centrallysymmetric local binarypattern)纹理与位图像统计的图像哈希算法。算法首先对图像做预处理；然后利用三级小波分解得到近似图像和高频信息，对第二、三级近似图像利用Ring分割，提取每一环的统计特征，对第二、三级高频信息的水平方向分量和垂直方向分量进行位图像分解，提取统计特征；最后将所有的低频和高频特征联合起来生成图像哈希序列。实验结果表明所提算法的分类性能优于现有的一些哈希算法，在拷贝检测应用上具有很好的准确率。

关键词：CS-LBP；Ring分割；位图像；图像拷贝检测 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.08.0955

# Image hash algorithm for copy detection

Shen Qi, Zhao Yan+ (College ofElectronics &Information Engineering,Shanghai UniversityofElectric Power,hanghai 2o9o,China)

Abstract:Inorder to identifythecopiedimagesaccuratelyandquickly,this paperpresentedanimagehashalgorithmbasedon CS-LBP(centallymtricocalarype)txtureaditimagesatistics.stlyitpreprocesdteagedad theapproximateimageandhigh frequencyinformationbyusingthe three-level waveletdecomposition.Itsegmentedthesecond andthird approximations imagebyRingandextractedthestatisticalcharacteristics ofeachring.Thehorizontalcomponentand the verticalcomponentofthesecondand third level high-frequency informationexecute bit image decomposition,which extractedstatistical features.Finallallthelow-frequencyandhigh-frequency features togethertogenerateimagehashsequence. Theexperimentalresultsshowthattheclassification performanceofthisalgorithmis beter than some existing hashalgorithms and has good accuracy in copy detection applications.

Key Words: CS-LBP; Ring segmentation; bit image; image copy detection

# 0 引言

随着网络技术的快速发展，各种拷贝图像呈几何倍率的增加，各种编辑软件如美图秀秀、百度魔图、光影魔术手等软件的出现，使得用户不需要专业知识也能够随意地对图像进行编辑处理，图像的拷贝检测变得越来越困难。随着图像哈希的提出，由于其特性，使其在拷贝检测应用方面有着很大的优势。图像哈希指将图像通过算法表示为简短的序列。其特性有鲁棒性、区别性、安全性等。鲁棒性指原始图像和经常规处理的图像的哈希序列相差不大，区别性指两幅不同图像应有不同的哈希序列，安全性指在在错误密钥情况下得到的哈希与正确密钥得到的哈希明显不同。

图像拷贝检测概念的正式提出是在2003年Kim[1提出图像分块结合离散余弦变换（discretecosine transform，DCT）的图像拷贝检测算法，其将图像分块处理，然后对矩阵块进行

DCT变换，利用其AC系数来构建哈希。算法对图像进行了矩阵分块，因此其对旋转不鲁棒。Ling等人[2提出多尺度的SIFT（scale-invariantfeature transform）特征描述符来构建哈希，该方法对一些区域提取不同半径的 SIFT 特征描述符，有效地提高了局部区域的区别能力。吴坤等人[3提出了一种具有针对性的拷贝图像检测算法，该算法利用Shi-Tomasi角点检测算子的旋转不变性提取对旋转不敏感的角点，再计算角点中心圆环内的特征描述子来构建哈希。该方法对剪切和旋转的鲁棒性好，但其对高斯滤波的鲁棒性差。Tang等人[4通过利用DCT系数来构建哈希，该算法将图像分块，对每个图像块进行 DCT 变换，然后利用DCT的系数来构建不变特征得到图像的哈希。算法在运算速度上有着明显的优势，但其不能对旋转鲁棒，在分类性能还有待提高。唐振军等人[5提出了一种基于主成分分析（principalcomponentanalysis，PCA）特征距离的哈希算法，该算法通过对图像进行分块，对每个图像块按列展开构建为二次图像，然后利用PCA进行处理来获得哈希序列。虽然该算法有着较好的分类性能，但其效率不高。李新伟等人[首先利用Gabor变换构建图像的结构图；然后将结构图转变为极坐标情况下，并进行子块划分和归一化使其对旋转具有鲁棒性；最后对结构子图进行加权求和并量化为哈希序列。该算法在保证较好的鲁棒性和区别性的同时还实现了紧凑性。Srivastava等人[7]提出一种基于统计特征的哈希算法，该算法通过对图像进行不同方向的Radon变换，然后对每一列的Randon系数进行DCT变换，最后统计每列的AC系数的均值、标准偏差、峰度和偏差的横向分量得到哈希序列。算法对常规处理有着很好的鲁棒性，但其效率有待提高。

为了使图像哈希在拷贝检测性能上具有良好的分类性能的同时有较好的效率，本文利用CS-LBP纹理具有较强的描述能力和计算速度快等优点对小波分解的对近似图像进行CS-LBP处理结合Ring分割提取统计特征，在此基础上，利用位图像具有较好的抗噪声能力，对小波分解的高频信息应用位图像分解提取其统计特征，提高算法对噪声的鲁棒性；然后联合近似图像和高频信息得到的特征构成中间哈希；最后对中间哈希置乱后得到最终哈希。实验结果表明本文算法有着不错的分类性能和效率。

# 1 本文哈希算法

# 1.1哈希算法框架

本文的哈希算法主要由预处理、小波分解、CS-LBP统计特征、位图像统计特征组成。具体过程如图1所示。

![](images/892cb1ac67a2065d70e3c0e31d19535345d2c830ac953a6c52c2e5b8ce7158f5.jpg)  
图1图像Hash的生成

# 1.2 图像预处理

首先，通过双线性插值将不同大小的图像规格化为 $M { \times } M$ 大小，将图像规格化为相同大小可以提高算法对缩放的鲁棒性；然后进行高斯低通滤波，提高对噪声的鲁棒性；由于本文提取的特征是基于纹理和位图像统计，再将彩色图像转换为灰度图像。

# 1.3小波分解

利用小波分解[8]，将预处理后的图像进行三级小波分解。由于选择的LBP算子是固定半径，只覆盖了固定区域，不能满足不同尺度的纹理特征，通过小波分解，达到获得多尺度的纹理需求，并能够压缩一定的信息量。

在小波分解中，基函数的选择会影响算法的鲁棒性和区别性。本文算法选取Haar小波，原因是Harr小波能够保证算法在运算速度快的同时可以保留大部分的图像信息[9]。

# 1.4基于CS-LBP 算子的纹理提取

CS-LBP算子[10]是在基本LBP算子上定义新的编码方式。CS-LBP在计算速度上相对于LBP算子具有明显优势。CS-LBP的编码规则如式(1)和(2)所示。

$$
C S - L B P _ { R , N } ( x , y ) = \sum _ { i = 0 } ^ { \frac { N } { 2 } - 1 } s ( n _ { i } - n _ { i + } { N \mathord { \left/ { \vphantom { N } 2 } \right. \kern - delimiterspace } 2 } ) ^ { i }
$$

$$
s ( x ) = \left\{ { \begin{array} { l l } { 1 } & { x > 0 } \\ { 0 } & { \not \equiv \not \equiv \not \equiv } \end{array} } \right.
$$

其中： $R$ 表示圆半径； $N$ 表示圆周上的像素点个数。

对三级小波分解中的第二、三级的近似图像应用CS-LBP得到第二、三级CS-LBP纹理图像。

# 1.5基于Ring 分割特征提取

引入Ring分割[I]对第二级CS-LBP纹理图像 $f ^ { \prime } ( x , y )$ 进行分环处理。根据像素点到图像中心距离来划分像素属于哪个像素集， $R _ { i } ( i = 1 , 2 , 3 . . . n )$ 表示第 $i$ 个圆环的像素集。通过统计特征[2]（均值、方差、偏态、峰态）来表示圆环内像素的特征，有效地将高维特征转为低维特征表示，并增加其鲁棒性。设 $n$ 为圆环数量， $r _ { k }$ 为 $f ^ { \prime } ( x , y )$ 内的第 $k ( k { = } 1 , 2 . . . n )$ 个圆半径， $r _ { \mathrm { n } }$ 可以由式(3)计算得到。

$$
r _ { n } = \left\lfloor { \frac { M } { 2 } } \right\rfloor
$$

其中：「表示向下取整。

其他圆半径，通过内接圆面积 $s$ 及均值 $s _ { 0 }$ 来计算。

$$
S = { \pi _ { n } } ^ { 2 } , S _ { 0 } = \left\lfloor { \frac { S } { n } } \right\rfloor
$$

圆半径计算如(5)和(6)所示。

$$
\eta = \left\lfloor { \frac { S _ { 0 } } { \pi } } \right\rfloor
$$

$$
r _ { k } = \sqrt { \frac { S _ { 0 } + \pi ^ { 2 } } { \pi } } ( k = 2 , 3 . . n - 1 )
$$

像素位置到图像中心的距离d为

$$
d _ { x , y } = \sqrt { \left( x - x _ { c } \right) ^ { 2 } + \left( y - y _ { c } \right) ^ { 2 } }
$$

其中： $x _ { c } , y _ { c }$ 为图像中心坐标； $^ { \cdot } x , y$ 为像素坐标。

根据距离d来判断像素是属于哪个像素集，如式(8) (9)所示。

$$
R _ { 1 } = \left\{ p ( x , y ) | d _ { x , y } \leq \eta \right\}
$$

$$
R _ { k } = \big \{ p ( x , y ) \big | r _ { k - 1 } < d _ { x , y } \leq r _ { k } \big \} ( k = 2 , 3 , . . . , n )
$$

计算每个圆环内的均值、方差、偏态和峰态来表示相应圆环的特征。 $n$ 个圆环将会得到 $4 { \times } n$ 维的特征矩阵 $V$ ，对矩阵 $\nu$ 按行进行标准化，设特征矩阵 $\nu$ 第 $\mathbf { \chi } _ { i }$ 行均值为参考向量$C ^ { i } ( i = 1 , 2 , 3 , 4 )$ 。用特征矩阵 $V$ 中元素到参考向量的距离作为不变特征，即

$$
D _ { i , j } = \sqrt { ( V _ { i , j } - C ^ { i } ) ^ { 2 } }
$$

其中 $: i$ ， $j$ 分别表示行和列。

得到 $4 { \times } n$ 维不变特征矩阵 $\textbf {  { D } }$ 将其按列展开得到 $1 \times 4 n$ 的一维特征向量 $_ { D I }$ 作为纹理的特征。同理可以得到第三级CS-LBP纹理图像的特征向量 $\pmb { D } \pmb { 2 }$ ，最终得到特征向量 $H c s { = } [ D _ { I } , ~ D _ { 2 } ]$ 。

# 1.6基于位平面的统计特征

噪声的攻击会对小波分解得到高频信息产生巨大影响，而经过位平面分解噪声信息将会集中于低位平面[13]，高位平面依然保留了重要信息。基于这一特点，对于小波二级分解得到的高频信息中的水平分量和垂直分量应用位平面理论，统计位平面5、6、7、8的统计直方图，并归一化得到8位特征向量 $\pmb { H } _ { W }$ 对小波三级分解的高频信息作相同处理得到8位特征向量 $\pmb { H } _ { W I }$ 最终得到16位的特征向量 $\pmb { H } _ { W P M } { = } [ \pmb { H } _ { W } , \pmb { H } _ { W I } ]$ ，有效地提高了图像对噪声的鲁棒性，并保证不同图像的区别性。

# 1.7哈希生成

为了体现位图像的作用，将得到的低频特征和高频特征按1:4联合起来，如式(11)所示，并进行取整操作，如式(12)所示。

$$
H = [ H _ { C S } , 4 \times H _ { W P M } ]
$$

$$
H = r o u n d ( 1 0 { \times } H + 0 . 5 )
$$

由1.4和1.5节知哈希长度为 $8 n + 1 6$ 个整数,利用随机发生器产生 $8 n + 1 6$ 个伪随机数序列K作为密钥。通过密钥K对哈希序列进行置乱,即

$$
h ( i ) = H ( K [ i ] )
$$

其中： $i$ 表示序列K中第 $i$ 个数。

# 1.8 图像拷贝检测

对需要检测的图像库和需要查询的图像通过哈希函数得到相应的哈希序列库和查询图像哈希序列，将查询图像的哈希序列与哈希序列库中的哈希序列计算哈希距离，本文中哈希距离利用欧氏距离计算，如式(14)所示。当欧氏距离小于设定阈值时，判定图像为拷贝图像。拷贝检测流程如图2所示。

$$
D ( h _ { 1 } , h _ { 2 } ) = \sqrt { \sum _ { i = 1 } ^ { N } ( h _ { 1 } ( i ) - h _ { 2 } ( i ) ) ^ { 2 } }
$$

![](images/834f99432f2546578ee47abc84b8dba40e42b120f4fc6b9e94c654280cc1fff9.jpg)  
图2图像拷贝检测流程

# 2 实验结果与分析

实验中的参数设置如下：图像规格化大小 $\scriptstyle M = 2 5 6$ ，标准差为3的 $3 { \times } 3$ 高斯低通滤波。CS-LBP的半径 $R { = } 1$ ，像素点个数$N { = } 8$ ，圆环数 $\scriptstyle n = 4 0$ ，因此哈希长度为336个整数。

# 2.1鲁棒性实验

在鲁棒性实验中，将Airplane、House、Lena、Baboon 和Peppers五幅图像做测试样本。图像处理如表1所示。实验结果如图3所示。

![](images/d885e13e36a8a787dab299cecd980d444c4e0c2e070370cf784c0a5b531b49cb.jpg)  
图3常规处理对哈希的影响

图3中横坐标表示常规处理（表1），纵坐标表示常规处理图像与原始图像的哈希距离。可以看出，除旋转操作外，常规的处理对哈希的影响不是很大。对于 $1 ^ { \circ }$ 以上的旋转处理，哈希距离会迅速增加。这是因为近似图像转为CS-LBP纹理图像的过程致使其对1°以上旋转的鲁棒性差。通过图3可看出本方法对除大角度旋转以外的常规处理具有良好的鲁棒性。

# 2.2 区别性实验

从华盛顿大学GroundTruthDatabase 图库[l4]中提取700幅图像，从数据库VOC2007[15]中提取300 幅图像，构建1000 幅不同图像的图库。通过MATLAB平台，在构建的图库中验证所提哈希算法的区别性。1000幅图像总共有499500个不同图像对。通过对1000 幅图像进行表2中的处理，产生105000 相似图像对。区别性实验结果如图4所示。其中红色（见电子版）表示不同图像对的哈希距离分布，蓝色表示相似图像对的哈希距离分布。由图4可以看出，不同图像哈希距离分布与相似图像哈希距离分布有着明显的界线，可以选择适当的阈值来区分两种情况。为此引入检错率和碰撞率[16]公式，如(15)和(16)所示。

$$
P _ { E } = \frac { N _ { E } } { N _ { S } }
$$

$$
P _ { C } = { \frac { N _ { C } } { N _ { D } } }
$$

其中： $N _ { E }$ 为相似图像对被检测为不同图像对； $N _ { C }$ 为不同图像对检测为相似对； $N s , \ N _ { D }$ 分别为相似图像对的总数目和不同图像对的总数目； $P _ { E }$ 为检错率； $P _ { C }$ 为碰撞率。

表1常规处理参数  

<html><body><table><tr><td>攻击类别</td><td>软件工具</td><td>参数说明</td><td>参数设置</td></tr><tr><td>亮度调整</td><td>Photoshop</td><td>级别</td><td>-20 -1010 20</td></tr><tr><td>对比度调整</td><td>photoshop</td><td>级别</td><td>-20 -1010 20</td></tr><tr><td>伽马矫正</td><td>MATLAB</td><td>γ值</td><td>0.75 0.9 1.1 1.25</td></tr><tr><td>JPEG压缩</td><td>光影魔术手</td><td>质量因子</td><td>30 40 50 ...100</td></tr><tr><td>图像缩放</td><td>MATLAB</td><td>比例</td><td>0.5 0.75 0.9 1.1 1.5 2.0</td></tr><tr><td>椒盐噪声</td><td>MATLAB</td><td>级别</td><td>0.001 0.002 ...0.01</td></tr><tr><td>3×3 高斯低通滤波</td><td>MATLAB</td><td>标准差</td><td>0.1 0.2 0.3 ... 1</td></tr><tr><td>旋转</td><td>MATLAB</td><td>角度</td><td>0.2 0.40.81 2</td></tr></table></body></html>

表2常规处理设置  

<html><body><table><tr><td>攻击类别</td><td>软件工具</td><td>参数说明</td><td>参数设置</td></tr><tr><td>亮度调整</td><td>Photoshop</td><td>级别</td><td>-20 20</td></tr><tr><td>对比度调整</td><td>photoshop</td><td>级别</td><td>-20 20</td></tr><tr><td>伽马矫正</td><td>MATLAB</td><td>Y值</td><td>0.75 1.25</td></tr><tr><td>JPEG压缩</td><td>光影魔术手</td><td>质量因子</td><td>40 80</td></tr><tr><td>图像缩放</td><td>MATLAB</td><td>比例</td><td>0.5 1.5</td></tr><tr><td>椒盐噪声</td><td>MATLAB</td><td>级别</td><td>0.002 0.006</td></tr><tr><td>3×3 高斯低通滤波</td><td>MATLAB</td><td>标准差</td><td>0.2 0.6</td></tr></table></body></html>

![](images/8d20f4158837b31e0c63ba217ef9b54adbfc50b467bf986fe25a84290e2599b5.jpg)  
图4区别性实验结果

表3 $P _ { \mathrm C }$ 和 $P _ { \mathrm { E } }$ 与阈值的关系  

<html><body><table><tr><td>阈值</td><td>105</td><td>110</td><td>115</td><td>120</td></tr><tr><td>Pc</td><td>0</td><td>4.2×10-5</td><td>1.9×10-4</td><td>9.8×10-4</td></tr><tr><td>PE</td><td>3.7×10-4</td><td>1.7×10-4</td><td>1.2×10-4</td><td>7.6×10-4</td></tr></table></body></html>

$P _ { c }$ 和 $P _ { \scriptscriptstyle E }$ 与阈值的关系如表3所示。从表3中可以看出，碰撞率和检错率是相互约束的关系，因此鲁棒性和区别性是互相矛盾的。在实际运用中可以根据要求选择合适的阈值。根据表3的结果阈值可以选为115，在该阈值下，算法具有较低的碰撞率和检错率。

# 2.3 安全性分析

为了验证算法的安全性，先用一个密钥作为正确密钥提取Lena图像的哈希，然后在其他条件不变情况下，选择1000 个错误密钥来获得相应错误密钥得到的图像哈希。这些错误密钥

得到的图像哈希与正确密钥得到的图像哈希的距离如图5所示。

![](images/5c8b9d8a5acc61f8120d3378770e7a4244bc8a71cb753580261ad1918efc4adc.jpg)  
图5错误密钥的哈希距离

由图5可知，这些错误密钥的距离都高于150，远高于设定的阈值115。说明在不知道正确密钥的情况下得不到正确的哈希序列，因此本文算法安全性比较好。

# 2.4参数讨论

本节主要讨论圆环数和 $H c s , H w p M$ 的比例对算法性能的影响。圆环数分别取 $\mathrm { \ n { = } 1 0 }$ 、20、30、40。比例取1:2、1:4、1:6、1:8、1:10。测试图像仍用2.2节构建的1000 幅图像库，共有499500个不同图像对，并按表2处理得到105000个相似图像对。下面分别讨论这些情况。

# 2.4.1不同圆环数对哈希性能的影响

实验中选取 $\pmb { H } _ { C S }$ ， ${ \pmb { H } } _ { W P M }$ 的比例为1:4，然后讨论圆环数分别为 $1 0 , 2 0 , 3 0 , 4 0$ 对哈希的影响，对应哈希长度为96、176、256、336个整数。并引入ROC曲线[17来比较不同圆环数对应的哈希算法性能。图6为不同圆环数下的ROC曲线对比。图中，横坐标为错误接受率 $P _ { F P R }$ （false positive rate,FPR），体现哈希算法的区别性；纵坐标为正确接受率PrPR（true positiverate,FPR），体现哈希算法的鲁棒性，其公式如(17)和(18)所示。为了保证比较公平，在相同电脑的MATLAB2016a平台运行，计算机配置为Intel(R)Core(TMi7-4720HQ CPU 2.6 GHz 和8 GB内存。由图6可知，圆环数为40时，本文算法有较好的分类性能。因此选取分类性能更好的一个即圆环数为40的能很好地体现本文算法的性能。

![](images/c3f401501c79050ce97254a132cbf5e7de2b07f3ff8a8954d26ba8a377e8423a.jpg)  
图6不同圆环数ROC 曲线对比

$$
P _ { F P R } = \frac { N _ { \mathrm { f a l s e } } } { N _ { 1 } }
$$

$$
P _ { T P R } = \frac { N _ { \mathrm { t r u e } } } { N _ { 2 } }
$$

其中： $N _ { \mathrm { f a l s e } }$ 是不同图像对被判断是相似对数目； $N _ { \mathrm { t r u e } }$ 是相似图像对中被正确判断为相似图像对数目； $N _ { 1 }$ 、 $N _ { 2 }$ 分别是总的不同图像对和总的相似图像对数目。

# 2.4.2不同比例对哈希性能的影响

实验中保持圆环数为40不变，比例分别取1:2、1:4、1:6、1:8、1:10。结果如图7所示。由图可知1:10的哈希性能最差，1:4与1:6相差不大，观察左上角局部放大图可知1:4稍微比1:6的更靠近左上角，所以比例选取1:4。

![](images/0e1b81b0b15f0b5cc496f659d0aac9b7a8b9bc7b79d68c70698288639bae9799.jpg)  
图7不同比例ROC曲线对比

# 2.5性能比较

为了展示本文算法的分类性能和效率，将本文算法与文献[4]、文献[18]、文献[19]和文献[20]的哈希算法进行比较。为了保证公平性，测试图像仍用2.2节构建的1000幅图像库，共有499500个不同图像对，并按表2处理得到105000个相似图像对。其余参数设置与其文献默认设置一致。并使用各自的距离测量方法来分析图像的相似性。选取ROC曲线作为分析工具。图8是不同算法的ROC曲线对比结果。由图可知，本文算法的分类性能优于对比的算法。通过记录唯一性实验时消耗的总时间求得哈希函数运行一次所需的平均时间，结果如表4所示。由表4可知，文献[4]算法运算快但其分类性能远低于本文算法，文献[18]算法运行时间与本文相差不大，文献[19]和文献[20]的算法运行时间均低于本文算法的运行时间。

表4不同算法的运算时间/s  

<html><body><table><tr><td>算法</td><td>本文</td><td>文献[4]</td><td>文献[18]</td><td>文献[19]</td><td>文献[20]</td></tr><tr><td>时间</td><td>0.180</td><td>0.031</td><td>0.126</td><td>0.528</td><td>0.702</td></tr></table></body></html>

# 3 拷贝检测应用

为了测试本文算法的拷贝检测性能，通过MATLAB、Photoshop和光影魔术手生成图9(a)的拷贝图像。具体的数字操作有亮度、对比度、伽马矫正、JPEG 压缩、图像缩放、椒盐噪声、 $3 { \times } 3$ 高斯低通滤波、乘性噪声、水印嵌入、马赛克、文本添加。各种操作的参数设置如下：亮度 $+ 2 0$ 、对比度 $+ 2 0$ 、伽马矫正值为1.25、JPEG压缩质量因子60、图像缩放比例为0.75、椒盐噪声级别为0.006、 $3 { \times } 3$ 高斯低通滤波标准差为0.6、乘性噪声级别为0.02、水印嵌入透明度为0.7、马赛克单位格大小为50、文本添加文字大小为72。通过这些操作得到11幅拷贝图像，将得到的拷贝图像加入到构建的1000幅图像库中共得到1011个图像的图像库。

![](images/5930191bdd85606aed1ffee563fc8b51b786627a0088784e0f3834aa244e8edc.jpg)  
图8不同哈希算法的ROC 曲线比较

![](images/e4a9a9a99599dd4455a47b2ff43cab49d5a957de198e5e554af89ab4fffb817c.jpg)  
图9原始图像和11个拷贝版本

表5距离最小的前13个图像  

<html><body><table><tr><td>序列</td><td>图像</td><td>距离</td></tr><tr><td>1</td><td>图10(i)</td><td>10.48</td></tr><tr><td>2</td><td>图10(k)</td><td>12.12</td></tr><tr><td>3</td><td>图10(h)</td><td>14.76</td></tr><tr><td>4</td><td>图10(c)</td><td>15.03</td></tr><tr><td>5</td><td>图10(i)</td><td>25.02</td></tr><tr><td>6</td><td>图10(g)</td><td>27.58</td></tr><tr><td>7</td><td>图10(e)</td><td>36.67</td></tr><tr><td>8</td><td>图10(d)</td><td>37.18</td></tr><tr><td>9</td><td>图10(b)</td><td>40.84</td></tr><tr><td>10</td><td>图10(l)</td><td>43.79</td></tr><tr><td>11</td><td>图10(f)</td><td>49.56</td></tr><tr><td>12</td><td>其他图像</td><td>123.70</td></tr><tr><td>13</td><td>其他图像</td><td>126.28</td></tr></table></body></html>

表6查询拷贝图像时间/s  

<html><body><table><tr><td>查询图像哈希提取时间</td><td>哈希序列库建立时间</td><td>查找时间</td></tr><tr><td>0.282</td><td>198.331</td><td>0.056</td></tr></table></body></html>

原始图像作为查询图像。表5为与查询图像距离最小的13幅图像。表6为查询图像在数据库中查询到的拷贝图像的各阶段时间。由表5可知，11个拷贝图像的距离均小于100。当阈值取115时，可以将所有的拷贝图像准确地识别出来。由表6可知，在含有1011幅图像的图像库的哈希序列库没有建立时，查找拷贝图像需要 $1 9 8 . 6 6 9 \mathrm { s }$ ；当哈希序列库已经建立时，则查找拷贝图像只需要 $0 . 3 3 8 \mathrm { ~ s ~ }$ 。查询图像哈希提取时间高于2.5节实验所得的算法运行时间是因为查询图像的维度为$3 1 3 6 \times 4 2 8 1 \times 3$ 远高于2.2节图像库中图像的维度。实验结果表明本文算法在拷贝检测应用方面具有不错的效果。

# 4 结束语

本文采用对纹理信息的统计结合高频信息的位图像统计来构建哈希算法，利用纹理信息的统计特征来实现哈希的鲁棒性和区别性，通过对高频信息应用位图像理论，提高算法的抗噪声能力。实验表明，本文算法的哈希长度较短、运算速度较快，具有较低的碰撞率和检错率，与现有的一些哈希算法对比，本文算法的分类性能较好，在拷贝检测应用方面能够准确地检测出所有的拷贝图像，有很好的应用前景。本文下一步工作是提高算法对大角度的旋转鲁棒性，并进一步提高算法运算速度。

# 参考文献：

[1]Kim C.Content-based image copy detection [J].Signal Process Image Commun Signal Processing Image Communication,20o3,18 (3): 169-184.   
[2]Ling H,Cheng H,Ma Q,et al. Efficient image copy detection using multiscale fingerprints [J].IEEE Multimedia,2012,19(1):60-69.   
[3]吴坤，王小华，姚金良.Shi-Tomasi 角点区域的拷贝图像检测[J]．中国 计量学院学报,2014,25(3):263-267.   
[4]Tang Z, Yang F, Huang L,et al. Robust image hashing with dominant DCT coefficients [J].Optik-International Journal for Light and Electron Optics, 2014,125(18): 5102-5107.   
[5] 唐振军，杨帆，黄紫晴，等．基于PCA 特征距离的图像哈希算法[J]. 广西师范大学学报：自然科学版,2016,34(4):9-18,7.   
[6]李新伟，夏秀珍．基于内容结构图的鲁棒图像哈希[J].应用科学学报， 2016,34 (6): 691-701.   
[7]Srivastava M,Siddiqui J,Ali MA.Robust image hashing based on statistical features for copy detection [Cl// Proc of IEEE Utar Pradesh Section International Conferenceon Electrical，Computer and Electronics Engineering. 2017: 490-495.   
[8]王玮，黄非非，李见为，等．采用LBP 金字塔的人脸描述与识别[J]. 计算机辅助设计与图形学学报,2009,21(1):94-100.   
[9]童苗苗，王春兴，张志杰.DWT 域的图像哈希算法[J].山东师范大学 学报：自然科学版,2016,31(2):64-67.   
[10] Heikkila M, Pietikainen M, Schmid C.Description of interest regions with center-symmetric local binary patterns [J].Lecture Notes in Computer Science,2006,42 (3): 58-69.   
[11] Tang Z, Zhang X, Zhang S.Robust perceptual image hashing based on ring partition and NMF[J].IEEE Trans on Knowledge & Data Engineering,2014, 26 (3): 711-724.   
[12] Tang Z, Zhang X,Li X,et al. Robust image hashing with ring partition and invariant vector distance [J].IEEE Trans on Information Forensics & Security,2015,11 (1): 200-214.   
[13]冯思玲，钟声，姚孝明，等．常见水印攻击对灰度图像多个位平面噪声 研究[J].计算机技术与发展,2012(11):250-252.   
[14] University of Washington. Ground truth database [EB/OL].[2017-10-07]. http://imagedatabase.cs.washington.edu/groundtruth/.   
[15]Redmon J. Pascal VOC dataset mirrir. [EB/OL]. (2012)[2017-10-07]. https://pjreddie.com/projects/pascal-voc-dataset-miror/.   
[16]赵琰，王朔中，姚恒，等.结合保角变换和 Zernike 矩的稳健图像Hash [J]．应用科学学报,2012,30(1):75-81.   
[17] Fawcet T.An introduction to ROC analysis [J].Pattern Recognition Letters, 2006,27 (8): 861-874.   
[18] Tang Z, Yang F,Huang L,et al. DCT and DWT based image hashing for copy detection [J]. Icic Express Letters,2013,7(11): 2961-2967.   
[19] Monga V, Mihcak M K. Robust and secure image hashing via non-negative matrix factorizations [J]. IEEE Trans on Information Forensics & Security, 2007,2 (3): 376-390.   
[20] Ou Y, Rhee K H. A key-dependent secure image hashing scheme by using radon transform [C]// Proc of International Symposium on Intelligent Signal Processing and Communication Systems.[S.1.]: IEEE Xplore,2009:595- 598.