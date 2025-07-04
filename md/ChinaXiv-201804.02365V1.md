# 基于双重压缩协议的医学图像压缩方法研究

苏宁¹，禹晓辉²

(1济宁学院 信息管理学院，山东 济宁 273155;2.山东大学 计算机科学与技术学院，济南 250100)

摘要：针对医学图像数据量大、存储和传输对内存和带宽要求高的问题，提出一种基于双重压缩协议的医学图像压缩方法。首先，使用方形网络对图像进行缩小处理；然后，利用数字水印技术在缩小图像的每个像素中，嵌入该像素最佳放大方法的编码；最后，对水印图像利用JPEG-LS无损压缩，得到最终的压缩图像，并进行存储和传输。对磁共振（MR）图像和计算机断层（CT）图像两种医学图像进行实验，实验结果表明，与其他方法相比，所提方法具有明显的优势，在高压缩比的情况下，能够保留良好的图像质量。

关键词：图像压缩；水印图像；医学图像；双重压缩协议；图像质量 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.01.0119

# Research of medical image compression approach based on double compression protocol

Su Ningl, Yu Xiaohui² (1.CollegeofIformationManagement,Jinng UniversityJningSanDong2155,Chna;2.CollgeofComputerience &Technology Shandong University,Jinan 25010o, China)

Abstract:Aiming atthe problemoflarge amountofmedical imageand theharsh requirementsof memoryand bandwidth,the paper proposes anewmedicalimagecompresion approachbasedondoublecompresion protocol.First,itused squareetwork to reducethesizeof images.Then,foreach pixelofthe image,itchosetheoptimal amplificationmethodand embedded the corespondingimage pixels bydigital watermarking technique.Finall,itfurther compressd the watermark image byJPEG-LS lossless compressiontoget the finalcompresion image,and to storage and transmit.Through theexperiment forMRand CT two types of medical image,the result show that,compared with other methods,the proposed method provides significant improvements and have ensured a better preservation of the image quality notably for high compression ratios.

Key words: image compression; watermark image; medical image; double compression protocol; image quality

# 0 引言

互联网使用的爆发式增长，使得互联网成为许多领域中进行数据传输的媒介，例如远程医疗、移动军事应用、在线学习等。当前医院和影像诊断机构正通过计算机，对医疗图像进行处理、存储和传输等数字化处理[1]。

现代医学图像产生海量的数据，使传输和存储系统迅速饱和[2.3]。为克服这一问题，数据压缩常常是必不可少的手段[4]。在此背景下，已经开发出一系列医学图像压缩技术，以降低图像尺寸，如分形编码[5]，分布式信源编码（distributedsourcecoding,DSC）无损压缩[6]、遗传算法[7]和稀疏表示[8]等。然而，由于JPEG[9]、JPEG2000[10]和JPEG-LS方法[]在图像压缩中表现较优，这些方法作为标准得到广泛使用。这些技术以编码算法为基础，将转换后的图像应用于频域或其他变换域。此外，其中的有损压缩保持压缩后图像不导致错误诊断的情况下，为医学应用所接受[12]。但这些方法的压缩比待进一步提高。

针对医学图像压缩，本文提出一种结合图像尺寸缩小和无损图像压缩的双重压缩协议（double compression protocol,DCP）本文首先使用方形网格方法对图像进行缩小处理；然后利用数字水印技术，在缩小图像的每个像素中嵌入该像素最佳放大方法的编码。所使用的图像放大技术包括补零、最近邻插值、三次插值和B样条插值。最后，为将图像尺寸进一步缩小，本文对缩小后的含水印图像进一步进行JPEG-LS无损压缩。恢复图像时，用户须先对图像进行解压缩，然后提取嵌入的水印信息并解码，最后选择放大方法，对图像进行恢复放大。

本文的主要工作包括：a)结合图像尺寸缩小和无损图像压缩的方法，对图像进行两阶压缩，进一步缩小图像的尺寸；b)使用数字水印技术，对放大信息进行评估和编码处理，提高图像恢复的质量。

# 1 基本方法

# 1.1方形网格缩小方法

将一幅图像水平方向和垂直方向的尺寸均缩小为原来的1/2，即从每个方向的两个样本中移除一个，如图1所示。空间函数如式(1)所示。

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { d _ { s } ( x , y ) = 1 } & { \mathrel { \mathop { = } } \mathrel { \mathop { = } } 1 x = \mathrm { y } } \\ { d _ { s } ( x , y ) = 0 } & { \mathrel { \mathop { = } } \mathrel { \mathop { = } } 1 \mathrm { x } \neq y } \end{array} \right. } \end{array}
$$

可以看出，该缩小方法即保留横纵坐标相同的像素 $( x , y )$ 消除其他的像素。

![](images/fff11842c3ea633323880d1e3cc0b4e6d6c410c0f336a9f38c13f7da674e80c4.jpg)  
图1使用方形网格将图像尺寸缩小为原来的1/4

# 1.2放大方法

目前研究人员已提出一些算法对图像进行放大。本文主要利用以下四种放大技术：补零、最近邻插值、三次插值和B 样条插值。为简化对这些方法的介绍，本文仅重点介绍在空间域中的一维插值情况。二维插值函数具有可分性，这些方法可扩展到二维中。

# 1.2.1 补零法

补零法由光谱保持的理念发展而来。图像通过离散傅里叶变换转换到频域；之后，通过在高频中添加0值样本，对光谱进行扩展；最后，对扩展的频率数据应用逆离散傅里叶变换，以得到放大后图像的空间表达。在空间域中，该处理过程如式(2)(3)所示。

$$
g ( x ) = \sum _ { m = - { \frac { a N } { 2 } } } ^ { \frac { a N } { 2 } - 1 } \ f ^ { \uparrow a } ( m ) \cdot h ( { \frac { x - m } { a } } ) = f ^ { \uparrow a } \ast h ( { \frac { x } { a } } )
$$

其中： $g$ 表示扩展后的信号， $h$ 为 sinc 函数， $N$ 表示 $f$ 的样本数量。式(3)表示通过将 $| a - 1 |$ 个零值添加到 $f$ 的样本之间以得到函数。

$$
( - \frac { a N } { 2 } \leq m < \frac { a N } { 2 } ) \{ \begin{array} { l l } { { f ^ { \uparrow a } ( m ) = f ( \frac { m } { a } ) \stackrel { \underbrace { \downarrow \downarrow } } { = } \frac { m } { a } \not \exists \not \exists \not \underline { { \Psi } } \not \exists \not \underline { { \Psi } } \not \downarrow } }  \\ { { f ^ { \uparrow a } ( m ) = 0 \qquad \stackrel { \underline { { \downarrow \downarrow } } } { = } \frac { m } { a } \not \exists \not \exists \not \underline { { \Psi } } \not \exists \not \underline { { \Psi } } \not \downarrow } } \end{array}  ~ ( \downarrow  \downarrow )
$$

# 1.2.2最近邻插值法

该方法是最简单快速的放大技术。其通过复制原始像素，以得到新的放大图像。该方法为每个新的像素分配与其最近的像素的值。该方法的插值函数 $h$ 如式(4)所示。

$$
\left\{ \begin{array} { l l } { \displaystyle h ( x ) = 1 } & { \displaystyle { \ddot { \mathcal { Z } } } \big | x \big | \leq \frac { 1 } { 2 } } \\ { \displaystyle h ( x ) = 0 } & { \displaystyle { \ddot { \mathcal { Z } } } \big | x \big | > \frac { 1 } { 2 } } \end{array} \right.
$$

1.2.3三次插值法

该方法通过应用一个三次多项式，使用四个相邻的像素计算新像素值。为了缩小解空间，在这些多项式上添加各种约束条件，例如零值附近的对称性、连续性和第一连续导数在连接点处等[13]。由此可以得到一个三次插值函数 $h$ ，如式(5)所示;然后将其进行式(2)的扩展操作。

$$
\left\{ \begin{array} { l l } { \displaystyle h ( x ) = \frac { 3 } { 2 } \big | x ^ { 3 } \big | - \frac { 5 } { 2 } x ^ { 3 } + 1 } & { \stackrel { \scriptscriptstyle \perp \perp } { = } \big | x \big | \le 1 \not \mathrm { H } \big | } \\ { \displaystyle h ( x ) = - \frac { 1 } { 2 } \big | x ^ { 3 } \big | + \frac { 5 } { 2 } x ^ { 2 } - 4 \big | x \big | + 2 } & { \stackrel { \scriptscriptstyle \perp \perp } { = } \frac { 1 } { 2 } \le \big | x \big | \le \frac { 3 } { 2 } \mathbb { H } \big | } \\ { \displaystyle h } & { ( x ) = \quad \ 0 \qquad \stackrel { \scriptscriptstyle \perp \perp } { = } \big | x \big | > \frac { 3 } { 2 } \mathbb { H } } \end{array} \right.
$$

# $1 . 2 . 4 \mathrm { ~ B ~ }$ 样条函数插值法

该方法使用所有原始图像像素，以计算放大后的图像像素值。通过对式(4)中定义的矩形函数应用 $n$ 次自卷积，得到连续的B样条[14]函数 $\beta$ ，如下式：

$$
\beta ^ { n } \left( x \right) = \beta ^ { n - 1 } \ast \beta ^ { 0 } \left( x \right) = \beta ^ { 0 } \ast . . . \ast \beta ^ { 0 } \left( x \right)
$$

B 样条函数的插值通过两个步骤实现：建立一个直接变换的B 样条;执行一个间接变换的B样条。

B样条系数 $C ( u )$ 由B样条变换的一个直接线性滤波计算所确定，如式(7)所示。

$$
C ( u ) = F ( u ) \cdot \mathcal { S } ^ { \prime \prime } ( u ) ^ { - 1 }
$$

其中：函数 $\scriptstyle { F = T F D ( f ) }$ 为原始信号的频谱。

要将 $f ( x )$ 从其B样条表示中扩展到原来的 $a$ 倍，最简单的方法是首先在B样条的系数 $C ( x )$ 之间插入 $^ { a - 1 }$ 个零值；然后采用B样条函数 $\beta ^ { n }$ 对上一步得到的结果进行插值，如式(8)所示，其被扩张到原来的 $a$ 倍大小。

$$
g ( x ) = c ^ { \uparrow a } \cdot \mathcal { \beta } _ { a } ^ { n } ( x )
$$

其中， $\beta _ { a } ^ { n } ( x ) = \beta ^ { n } ( \frac { x } { a } ) \ c ^ { \uparrow a }$ 的定义与式(3)类似。

# 1.2.5图像放大方法比较

对于原始CT图像的分块分别利用四种方法进行放大处理，结果如图2所示。图2(b)中，补零方法得到的放大图像的边界位置出现了波动伪迹。这些波动主要由滤波器引起，导致光谱的不连续性。最近邻方法可移除波动，但是出现了图像像素化问题，如图2(c)所示。这一缺陷是由将最近邻的值分配到这些新增加的像素所引起的。在图2(d)中，三次插值法放大的图像显著降低了图像的像素化，并且没有出现波动伪迹。但是，该图像显示一定程度的模糊，这是由估计的像素值对相邻像素值的依赖性所引起。通过将B样条插值函数与之前的方法进行比较可以观察到，其降低了图像的模糊和像素化效果，并移除了波纹缺陷，但该方法计算复杂度较前面方法增大。

T

# 2 提出的方法

# 2.1基本原理

医学图像的尺寸通常很大，网络传输需要消耗很大的可用带宽。为解决这一问题，本文提出了双重图像压缩协议(DCP)。一方面，该方法旨在图像发送前对图像的尺寸进行缩小。另一方面，传输后的图像可以被放大到适合其显示屏幕的大小，以提高视觉舒适度，利于疾病诊断。DCP包括图像压缩和图像解压两个过程，分别如图3(a)(b)所示。

![](images/8d43befa7d98af3d7a07327ce23889077de1cf834462fc0b605616750ec713fa.jpg)  
(a)原始图像

图像压缩过程中，首先以方形网格的方法对图像进行缩小，得到初步缩小图像；然后，对缩小图像每块像素选择合适的放大方法，作为水印信息；随后，将水印信息嵌入缩小图像中，得到水印图像；最后，对水印图像进行JPEG-LS无损压缩，得到最终的压缩图像。图像解压过程中，首先对传输得到的压缩图像进行无损解压得到水印图像；然后，根据水印图像中的嵌入信息，提取每块像素合适的放大方法，得到结合后的恢复图像。

![](images/91b9c08686c2d53598e967bb2aa519a7c258dc4b23bce5e175b293172b898ef3.jpg)  
图2四种放大方法比较  
（a）图像压缩过程

![](images/18233d3aef0ccd91e9a1bf8e3714ecc975b006a59c248342d7528b6b46cca58f.jpg)  
图3双重图像压缩协议（DCP）

# 2.2单层双重压缩协议

在图像缩小过程中，使用方形网格方法实现，原始图像的四分之一像素得到保留；反之，在图像放大过程中，一个像素已知，需要对其他三个像素进行估计，如图1的反过程所示。因此，图像可被划分为 $2 \times 2$ 的分块，每个分块中包括一个已知像素和三个未知像素。

第2章中的四种放大方法，可用于计算放大后图像中所有未知像素的数值。因此，每个估计像素根据所使用的放大方法，可得到四个可能值，则每个分块得到四种估计。本文使用PSNR指标，对原始图像的每个分块和与其相对应的缩小/放大后的图像分块进行比较。根据比较结果，本文建立一个选择矩阵，其可以识别最适合于每个分块的放大函数。四种放大方法，需要使用2比特位对每种放大方法进行编码。本文采用数值‘00'‘01’‘10’和‘11’分别代表补零、最近邻插值、三次插值和B样条插值法。本文在图像传输前将最佳的编码插入保留像素的最低有效位（即最不重要位）中。在放大时，将位于每个像素中的嵌入信息提取出来，识别并使用最适当的放大技术对每个扩充后的分块进行估计。因此，放大后的图像是对缩小的嵌水印图像使用四种放大技术的结合，该方法属于盲水印类型。

基于图像缩小和数字水印的方法，将图像尺寸缩小为原始图像的四分之一大小，即对于灰度图像，每像素位数为2bit（8bit/4）；对于彩色图像每像素位数为6bit（24bit/4）。为进一步缩小图像尺寸，本文利用JPEG-LS无损压缩方法对嵌水印的缩小图像进一步压缩。因此，在恢复图像时必须对其进行解压缩后再放大。

# 2.3多层双重压缩协议

由于JPEG-LS采用无损压缩，应用于一幅图像后得到新的固定尺寸文件，这使得无法进一步缩小将要传输或归档的图像尺寸。本文DCP方法可控制缩小后图像的像素数量，实现对图像尺寸的进一步压缩，该理念是对原始图像进行递归缩减。在0层得到的图像与原始图像具有相同的尺寸。在1层的缩减中，像素数量会被缩减到原先的 $1 / 4 ^ { 1 }$ ；对压缩后的图像，进行第2层缩减，图像尺寸缩减到原先的 $1 / 4 ^ { 2 }$ ；重复迭代缩减过程，在$n$ 层得到的缩小图像是原始图像尺寸的 $1 / 4 ^ { n }$ 。根据在（ $^ { n - 1 }$ ）层得到的图像，完成对在 $n$ 层得到的图像的水印嵌入。

# 3 实验与分析

本文实验环境是一台Inteli5双核 $\textcircled { a } 2 . 4 9 ~ \mathrm { G H z }$ ，8GB内存的个人电脑，采用MATLAB2011b编程，所用图像均为MR和CT标准图像，采自医院影像室。

# 3.1放大-缩小效果比较

在实验中，本文使用方形网格简化方法对图像进行缩小，在放大阶段利用补零（zero fill,ZF）、最近邻插值（nearestneighbor interpolation,NNI）、三次插值（cubic interpolation,CI）、B 样条插值（B-spline interpolation,BSI）四种方法。为说明数字水印在本文提出的压缩方法中的效果，将本文的DCP方法与单独使用各放大方法的实验结果进行对比。本文对两种医学图像数据库进行实验。第一个数据库由30个磁共振（magneticresonance，MR）图像组成，第二个数据库则由30个计算机断层图像（computer tomography，CT）所组成。

表1MR图像上的缩小-放大技术的评价  

<html><body><table><tr><td></td><td>ZF</td><td>NNI</td><td>CI</td><td>BSI</td><td>DCP</td></tr><tr><td>PSNR/dB</td><td>45.20</td><td>37.41</td><td>47.15</td><td>46.85</td><td>50.47</td></tr><tr><td>SSIM</td><td>0.9985</td><td>0.9842</td><td>0.9973</td><td>0.9976</td><td>0.9990</td></tr></table></body></html>

表2CT图像上的缩小-放大技术的评价  

<html><body><table><tr><td></td><td>ZF</td><td>NNI</td><td>CI</td><td>BSI</td><td>DCP</td></tr><tr><td>PSNR/dB</td><td>34.50</td><td>42.11</td><td>34.25</td><td>35.62</td><td>51.25</td></tr><tr><td>SSIM</td><td>0.9975</td><td>0.9991</td><td>0.9962</td><td>0.9963</td><td>0.9992</td></tr></table></body></html>

本文将PSNR和SSIM作为缩小后再放大图像间保真度的评价标准，表1和表2分别给出各种方法的实验结果。实验结果表明，本文DCP方法对于两种医学图像均能更好的保留原始图像质量。事实上，即使某个单一方法能够高效的放大整个图像，其也未必能高效放大图像的成分或分块。DCP方法较其他方法的优势在于其能够为每个分块选择最佳的放大方法。图4(a)和图4(c)分别展示了嵌水印的缩小MR和CT图像，其每个像素都包括所选择的放大方法的标签。图4(b)和图4(d)分别展示了在缩小图像中嵌入的签名，其中蓝色、绿色、红色和黑色分别表示对应分块利用ZF、NNI、CI和BSI技术，其分别代表插入的比特位‘00’‘01’‘10’和‘11’。从这些数字水印中可以明显观察到，不同位置利用了不同的放大方法。

![](images/8a39c9784291fa9d1df5bc90ae99305fde70e4cedf21c2b8cff7853f0d459714.jpg)

![](images/cc5ba701aae7031f493b0b2c4790838a3ee0e28f5a2b79dce3703a93fabfab2b.jpg)  
图4图像分块的适当放大技术

为进一步缩减水印图像的尺寸，本文使用 $n$ 层DCP方法。表3和表4分别给出不同层缩减情况下，不同方法对医学图像的实验结果。可以看出，对于两种医学图像，本文DCP方法随着缩小层数的增大，仍可以保持稳定的恢复效果，而其他方法的图像质量则急剧降低。说明本文DCP方法具有稳定的图像压缩和恢复效果。

表3 $n$ 层MR图像上的缩小-放大技术的评价  

<html><body><table><tr><td></td><td></td><td>ZF</td><td>NNI</td><td>CI</td><td>BSI</td><td>DCP</td></tr><tr><td rowspan="3">PSNR (dB)</td><td>n=1</td><td>45.20</td><td>37.41</td><td>47.15</td><td>46.85</td><td>50.47</td></tr><tr><td>n=2</td><td>35.26</td><td>34.56</td><td>37.53</td><td>36.51</td><td>41.94</td></tr><tr><td>n=3</td><td>29.41</td><td>28.25</td><td>30.23</td><td>29.95</td><td>35.37</td></tr><tr><td rowspan="3">SSIM</td><td>n=1</td><td>0.9985</td><td>0.9842</td><td>0.9973</td><td>0.9976</td><td>0.9990</td></tr><tr><td>n=2</td><td>0.9775</td><td>0.9625</td><td>0.9765</td><td>0.9768</td><td>0.9825</td></tr><tr><td>n=3</td><td>0.9153</td><td>0.9020</td><td>0.9112</td><td>0.9123</td><td>0.9318</td></tr></table></body></html>

表 $\textit { 4 } \textit { n }$ 层CT图像上的缩小-放大技术的评价  

<html><body><table><tr><td></td><td></td><td>ZF</td><td>NNI</td><td>CI</td><td>BSI</td><td>DCP</td></tr><tr><td rowspan="3">PSNR (dB)</td><td>n=1</td><td>34.50</td><td>42.11</td><td>34.25</td><td>35.62</td><td>51.25</td></tr><tr><td>n=2</td><td>28.71</td><td>35.64</td><td>28.52</td><td>30.41</td><td>43.08</td></tr><tr><td>n=3</td><td>26.35</td><td>30.48</td><td>26.21</td><td>28.54</td><td>36.47</td></tr><tr><td rowspan="3">SSIM</td><td>n=1</td><td>0.9975</td><td>0.9991</td><td>0.9962</td><td>0.9963</td><td>0.9992</td></tr><tr><td>n=2</td><td>0.9789</td><td>0.9801</td><td>0.9750</td><td>0.9756</td><td>0.9886</td></tr><tr><td>n=3</td><td>0.9433</td><td>0.9510</td><td>0.9301</td><td>0.9423</td><td>0.9658</td></tr></table></body></html>

# 3.2压缩和恢复效果比较

本文DCP方法的目的在于缩减要发送或存档图像尺寸，由此，每像素位数（bits perpixel，BPP）对压缩方法的性能有很大影响。当使用1层DCP进行处理时，图像尺寸缩小1/4，灰度图像的BPP等于2。本文使用n层DCP对图像进行缩小，然后利用JPEG-LS 图像格式对缩小图像进行存档处理，并实现对嵌水印缩小图像尺寸的进一步减小，得到更小的BPP。本文进行1、2和3层DCP处理后，分别比较未进一步处理和利用JPEG-LS无损压缩进一步处理后，最终压缩图像的BPP，如表5 所示。可以看出采用JPEG-LS[I]和DSC[两种无损图像压缩方法可以较大程度的对图像进一步压缩。

表5处理前后BPP 对比  

<html><body><table><tr><td></td><td></td><td>未处理</td><td>JPEG-LS[11]</td><td>DSC[6]</td></tr><tr><td rowspan="3">MR</td><td>n=1</td><td>0.125</td><td>0.451</td><td>0.501</td></tr><tr><td>n=2</td><td>2.00</td><td>0.71</td><td>0.73</td></tr><tr><td>n=3</td><td>0.50</td><td>0.22</td><td>0.30</td></tr><tr><td rowspan="3">CT</td><td>n=1</td><td>0.125</td><td>0.048</td><td>0.052</td></tr><tr><td>n=2</td><td>2.00</td><td>0.72</td><td>0.75</td></tr><tr><td>n=3</td><td>0.50</td><td>0.24</td><td>0.31</td></tr></table></body></html>

一种优秀的图像压缩方法不但应该确保较高的压缩率（即低BPP），而且应该能够最大限度的保留图像质量。为了显示本文水印缩小方法与JPEG-LS方法结合的有效性，与JPEG-LS[II]和DSC[两种压缩方法的结果进行对比。同等压缩比情况下，几种方法的比较结果如表6和表7所示。可以看出，对于MR图像，在BPP低于0.71时，本文方法能够更好的保留图像质量。对于CT图像，本文方法在BPP较低时，性能比JPEG-LS[I和DSC[更加高效稳定。这主要是因为本文方法使用数字水印技术，对放大信息进行评估和编码处理，提高了图像恢复的质量。

表6几种方法在MR图像上的评价结果  

<html><body><table><tr><td></td><td></td><td>JPEG-LS[11]</td><td>DSC[6]</td><td>本文方法</td></tr><tr><td rowspan="3">PSNR (dB)</td><td>BPP=0.71</td><td>54.65</td><td>53.37</td><td>50.47</td></tr><tr><td>BPP=0.22</td><td>40.12</td><td>40.99</td><td>41.94</td></tr><tr><td>BPP=0.053</td><td>25.31</td><td>29.87</td><td>35.37</td></tr><tr><td rowspan="3">SSIM</td><td>BPP=0.71</td><td>0.9990</td><td>0.9990</td><td>0.9980</td></tr><tr><td>BPP=0.22</td><td>0.9453</td><td>0.9488</td><td>0.9825</td></tr><tr><td>BPP=0.053</td><td>0.8213</td><td>0.8651</td><td>0.9318</td></tr></table></body></html>

表7几种方法在CT图像上的评价结果  

<html><body><table><tr><td></td><td></td><td>JPEG- LS[11]</td><td>DSC[6]</td><td>本文方法</td></tr><tr><td rowspan="3">PSNR (dB)</td><td>BPP=0.71</td><td>49.62</td><td>50.12</td><td>51.25</td></tr><tr><td>BPP=0.22</td><td>35.78</td><td>36.98</td><td>43.08</td></tr><tr><td>BPP=0.053</td><td>28.45</td><td>31.25</td><td>36.47</td></tr><tr><td rowspan="3">SSIM</td><td>BPP=0.71</td><td>0.9995</td><td>0.9996</td><td>0.9992</td></tr><tr><td>BPP=0.22</td><td>0.8632</td><td>0.9132</td><td>0.9586</td></tr><tr><td>BPP=0.053</td><td>0.8741</td><td>0.8841</td><td>0.9558</td></tr></table></body></html>

由于本文方法结合了JPEG-LS[1技术，为了更加直观的比较本文方法与JPEG-LS[1]的效果，图5和6分别给出 $\mathrm { B P P = } 0 . 0 4 8$ 时，两种方法对 MR 图像和CT图像的恢复效果。可以看出，本文方法具有更好的性能，在细节方面的保真度明显优于JPEG-LS方法。

![](images/755b5f7001e829c48551ba5f11b726b731b1136d03ae78efe26cbbc8a9e13cbd.jpg)  
图5MR图像

![](images/f16baaa980ce67b319381a09d8f30e21fe4487679c6ffae57d767e092c887be2.jpg)  
图6CT图像

# 3.3 时间复杂度分析

本文方法的时间复杂度主要体现在图像的缩放、水印嵌入和压缩过程中的JPEG-LS技术。其中，图像缩放的时间对于整个压缩过程影响较小，主要影响因素是水印嵌入和JPEG-LS。因此，在时间复杂度方面略高于 JPEG-LS[1I]。但整体效果，本文方法略好。对于DSC[]，其时间复杂度主要体现在DSC 编码上，采用空间分块策略，其时间复杂度略高于 JPEG-LS[I]。表8 给出了几种方法的时间复杂度，这里将JPEG-LS[11]的时间复杂度归化为1。对于压缩比1.6，其运行时间如表8所示。可以看出这三种方法的时间复杂度都可满足一般压缩的功耗限制。

表8时间复杂度比较  

<html><body><table><tr><td>算法</td><td>复杂度</td><td>压缩比</td><td>运行时间</td></tr><tr><td>JPEG-LS[6]</td><td>1</td><td>1.6</td><td>93ms</td></tr><tr><td>DSC[6]</td><td>1.16</td><td>1.6</td><td>117ms</td></tr><tr><td>本文</td><td>1.08</td><td>1.6</td><td>103ms</td></tr></table></body></html>

# 4 结束语

本文旨在确保对MR图像和CR图像高压缩比的同时，保证良好的图像质量。这样可以降低医学图像的存档容量，有利于医学影像在远程医疗应用中的传输。与基于编码算法的JPEG压缩标准不同，本文方法结合了图像尺寸的缩小和用于无损图像压缩的编码算法。使用了方形网络方法对图像进行缩小，综合使用补零、最近邻插值、三次插值和B样条插值四种放大方法。为充分应用每种图像放大方法的优势，本文将图像再分为$2 \times 2$ 的分块，随后，在每个像素中插入其最适当的放大方法的编码。此外，本文使用JPEG-LS压缩格式，以在提升图像压缩比的同时对数字水印进行保留。最后通过对MR和CT两种医学图像的实验，本文提出方法的图像质量明显优于单独的图像压缩放大方法。与其他压缩方法相比，本文方法能够更好对图像质量进行保留，可保持诊断的准确性。

# 参考文献：

[1]黑啸吉，蒋慧琴，马岭，等．一种基于低剂量CT 图像的肺结节分割方 法[J].计算机应用研究,2017,34(1):290-294.(Hei Xiaoji,Jiang Huiqin, Ma Ling,et al. Method for pulmonary nodules segmentation based on low dose CT images [J].Application Research of Computers,2017,34(1): 290- 294.)   
[2]Juliet S,Rajsingh E B and Ezra K. Projection-based medical image compression for telemedicine applications [J]. Journal of Digital Imaging, 2015,28 (2): 1444-1449.   
[3]Dennison D,Ho K. Informatics challenges-lossy compression in medical imaging[J]. Journal of Digital Imaging,2014,27 (3): 287-291.   
[4]Anusuya V,Raghavan VS,Kavitha G.Lossless compression on MRI images using SWT[J]. Journal of Digital Imaging,2014,27(5): 594-600.   
[5]张方舟，王徐妍，郝庆辉．基于遗传分形编码的嵌入式小波图像编码算 法[J]．计算机技术及发展，2016,52(1):128-132.(Zhang fangzhou, Wang Xuyan, Hao Qinghui. Embedded wavelet image coding algorithm based on a genetic fractal coding [J].Computer Technology and Development,2016,52 (1): 128-132.)   
[6]杨新锋，韩利华，粘永健.DSC 的超光谱图像无损压缩算法[J].红外 与激光工程，2016,45(3):217-223.(Yang Xinfeng,Han Lihua,Lian Yongjian.Lossless compression algorithm for hyperspectral images based on DSC [J].Infrared and Laser Engineering,2016,45 (3): 217-223)   
[7]田振川，李冠朋，王蒙蒙．基于遗传算法的分形图像压缩技术研究[J] 计算机应用与软件,2013,30(4):138-140.(Tian Zhenchuan,LiGuanpeng, Wang Mengmeng.On fractal image compression technology based on genetic algorithm [J].Computer Application and Software,2013,30 (4):

# 138-140.)

[8] 赵海峰，鲁毓苗，陆明，等．基于快速稀疏表示的医学图像压缩[J]. 计算机工程,2014,40 (4): 233-236.(Zhao Haifeng,Lu yumiao,Lu Ming, et al. Medical image compression based on fast sparse representation [J]. Computer Engineering,2014,40(4): 233-236.)   
[9]Qian Z, Zhang X.Improved anti-forensics of JPEG compression [J]. Journal of Systems& Software,2014,91(4): 100-108.   
[10] Kitaeff V V, Cannon A,Wicenec A,and et. al. Astronomical imagery: considerations for a contemporary approach with JPEG2ooo [J].Astronomy & Computing,2014,12 (12): 229-239.   
[11] Haddad S,Coatrieux G,Cozic M,et al. Joint watermarking and lossless JPEG-LS compression for medical image security [C]// International Conference on Watermarking and Image Processing.ACM,2017: 618-628.   
[12]刘玉，王倩楠，粘永健，等．医学图像有损压缩技术研究进展[J].磁 共振成像,2016,7(6):473-480.(Liu Yu,Wang Qiannan,Lian Yongjian,et al. Research progress of medical image lossy compression technology [J]. Chinese Journal of magnetic resonance imaging, 2016,7(6): 473-480.)   
[13]行薇．图像插值技术在图像处理中的应用[D].长春：长春理工大学, 2012. (Hang Wei. Application of image interpolation in image processing [D].Changchun: Changchun University of Science and Technology,2012.)   
[14]李军成．利用二次B样条曲线逼近的图像压缩方法[J].计算机工程与 科学，2014,36 (2): 325-330.(Li Juncheng.Image compression using quadratic B-spline curve approximation,2014,36 (2): 325-330.)   
[15]白韬韬，刘真，卢鹏．基于QR码的Contourlet 域数字水印算法[J]．光 电子激光，2014,52(4):769-776.(Bai Taotao,Liu Zhen,Lu Peng. Contourlet domain digital watermarking algorithm based on QR code [J]. Journal of Optoelectronics Laser,2014,52 (4): 769-776.)