# 基于谱域特征提取与线性回归分类的智能人脸识别算法

陈汶滨，曾渌麟

(西南石油大学 计算机科学学院，成都610500)

摘要：针对人脸识别中由于光线、表情变化和遮挡导致人脸图像变化的问题，提出了一种谱域特征提取与线性回归分类算法相结合的智能人脸识别方法。为了实现特征提取的目的，首先使用Viola-Jones 算法从原始图像中提取初始人脸部分，并将其转换为 $1 2 0 \times 1 2 0$ 像素大小的灰度图像；然后提出了一种计算极坐标傅里叶变换（FFT）以获得预处理人脸图像主要幅度谱特征的新框架，进一步在预处理的图像上执行2D-DFT，并表示为IDP-FFT。特征值是1DP-FFT幅值中的最大值，提取的特征值用于构造表示人脸图像的符号对象。最后利用快速有效的线性回归分类算法实现分类。在AR和GT数据库上进行了各种实验，分别取得了 $9 7 . 5 1 \%$ 和 $9 8 . 0 2 \%$ 的准确率。与最近报道的一些人脸识别技术相比，提出的方法识别准确率更高。

关键词：人脸识别；线性回归；快速傅里叶变换；分类算法；谱域特征 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.04.0336

# Intelligent face recognition algorithm based on spectral feature extraction and linear regression classification

Chen Wenbin, Zeng Lulin (School of Computer Science,Southwest Petroleum University,Chengdu 61o5oo,China)

Abstract: Aiming at the problemofface imagechangecaused bylight,expression changeandocclusioninfacerecognition,a smartface recognition method combining spectral domain feature extractionand linearregression clasificationalgorithmis proposed.Forthe purposeoffeature extraction,the initial human facepartis first extractedfromtheoriginal imageusing the Viola-Jones algorithm and converted into a grayscale image with a size of $1 2 0 \times 1 2 0$ pixels.Then,a new framework is proposedtocompute the polar amplitudeFourier transform (FFT）toobtain the mainamplitude spectral features of the preprocessed face image.The 2D-DFT is further performed on the preprocessed image and expressd as a 1D P-FFT.The eigenvalue is the maximum valueof the1DP-FFTamplitude,and the extracted eigenvalueisused toconstructa symbol objectrepresentingafaceimage.Finallyclassificationisimplementedusingafastandeficient linearregressionclasifiation algorithm. Various experiments were performed on the AR and GT databases，achieving $9 7 . 5 1 \%$ and $9 8 . 0 2 \%$ accuracy, respectively.Compared with somerecentlyreported facerecognition techniques,the proposed method has higherrecognition accuracy.

Keywords:facerecognition; linearregression;fastFouriertransform; clasificationalgorithm;spectraldomain feature

# 0 引言

人脸识别是计算机视觉、人工智能、模式识别和生物识别领域的一个活跃的研究领域[1-4]。与其他生物识别方式(如指纹、虹膜、手印等）相比，人脸识别的最重要优势在于它可以在远距离和友好的方式下进行。在过去的几十年中，许多人脸识别方法已经被提出和开发。然而这些人脸识别方法在光照变化和存在遮挡的情况下识别准确率受到严重影响[5]。提取最优特征和有效的分类方法是人脸识别系统的两个主要步骤。因此，为了提高人脸识别系统的性能，找到一个好的特征提取器和一个有效的分类器是至关重要的。此外，还需要降低所提取的特征空间的维度，以便提高该算法在其分类过程中的效率和鲁棒性。

近年来，许多基于外观的人脸识别系统被开发出来，以减少面部图像分类所需的计算时间。一些文献提出基于外观的人脸识别系统。这些文献直接使用人脸图像像素强度值作为识别的特征值，并使用单值变量表示[6.7]。但是这样的单值变量可能无法捕捉同一主题图像的特征值的变化，并且也将具有高维度特征数据。研究人员为了开发特征数量更少的高效系统，采用了特征学习方法。特征学习或主动学习在通过区分表征或构建训练图像数据（提取特征），以提高分类任务的性能方面起着重要作用。因此，近年来研究人员已经提出了许多主动学习方法，它们将训练样本的代表性与信息性结合起来以获得更好的分类准确性。其中，文献[8]提出了一种有监督的特征学习模型来分类低维和高维数据。该技术使用判别回归方法估计回归向量来估计测试数据和训练数据之间的相似性。然而，当低维或高维图像数据受到诸如遮挡、几何变化和照明等情况时，分类任务变得具有挑战性[9]。

研究表明，符号对象提供了一种有效的方法来表示关于人脸图像的这种可变信息。本文提出了一种用于人脸识别的基于新颖外观识别方法的谱域特征提取算法，有效利用了人脸图像中的局部空间变化，如光照、表情。为了特征提取的目的，所提出的方法使用与傅里叶分析相关的技术，其中当在极坐标中观察时，频率集合等于Averbuch等人[1o]提出的等式。此外，在极坐标网格中，生成的快速傅里叶变换（fastFouriertransform，FFT)特征被评估为单维等距极坐标FFT值并转换为1DP-FFT（polar-FFT）。来自1DP-FFT的最大量值用于表示面部识别的特征值。此外，本文还利用符号建模方法更好地表示提取的特征。因此，所提出的工作引入了一种新的符号建模技术，该技术仅依靠原始数据的外观来减少2D-DFT频谱特征的维度。最后利用快速有效的线性回归分类算法实现分类。通过对AR[]和GT[I2]数据库进行了各种实验，证明了本文方法的准确性。

# 1谱分析与极坐标FFT的计算

对于许多图像处理应用来说，对极坐标中傅里叶变换的快速和准确估计一直是一个主要挑战。在过去的几十年中，已经提出了几种技术来解决这些问题。文献中有两种方法来计算极坐标或对数极坐标傅里叶变换，其区别在于直接在二维笛卡尔FFT域内的原始图像上进行插值还是在处理后的图像中进行插值。由于存在插值误差，基于快速傅里叶变换的图像配准技术不能准确地恢复新变换的数据，甚至无法恢复大尺度因子。在相位相关的过程中，FFT方法经常遭遇错误的峰值。伪极坐标FFT因此被提出，并且在图像配准中进行了测试。在某些条件下，这些方法在计算与二维FFT相同复杂度的极坐标傅里叶变换时能够显著降低插值误差。文献[13]提出的基于伪极坐标FFT的算法PPFFT可以通过迭代过程将尺度恢复到4。极坐标FFT还可用于改进或简化计算极坐标网格中的频率值的数字处理步骤。

极坐标FFT的实现中，首先是在频域中定义伪极坐标网格点，将这些点分为垂直子集 $V S$ 和水平子集 $H S$ 。在伪极坐标网格中，Vs 和 $H S$ 点以同心圆为中心，非等间隔分布于射线上,这些方块边的大小为 $\pi t / N$ ，其中 $\scriptstyle t = 0 , 1 , \ldots , N$ 。VS 射线有$2 p / N , - N / 2 \le p < N / 2$ 和均布斜坡。 $H S$ 射线与之类似，但顺时针旋转 $9 0 ^ { \circ }$ 。一般 $\boldsymbol { V } \boldsymbol { S }$ 和 $H S$ 网格点可以表示如下：

$$
V S = \left\{ \begin{array} { l } { { \displaystyle \xi _ { l } = \frac { \pi t } { N } \mathrm { f o r } - N \le t \le N , \smallskip } } \\ { { \displaystyle \xi _ { k } = \xi _ { l } . \frac { 2 \mathrm { p } } { \mathrm { N } } \mathrm { f o r } - \frac { \mathrm { N } } { 2 } \le p < \frac { N } { 2 } } } \end{array} \right\}
$$

$$
H S = \{ \begin{array} { l l } { \displaystyle \xi _ { k } = \frac { \pi t } { N } \mathrm { f o r } - N \le t \le N , } \\ { \displaystyle \xi _ { l } = \xi _ { k } . \frac { 2 \mathrm { p } } { \mathrm { N } } \mathrm { f o r } - \frac { \mathrm { N } } { 2 } < p \le \frac { N } { 2 } ] } \end{array} 
$$

在式（1）错误！未找到引用源。和（2）错误！未找到引用源。中， $N$ 表示伪极坐标网格中同心正方形的数量。文献[14]的研究表明，为了计算傅里叶变换值，在给定的伪极坐标网格点VS和 $H S$ 的情况下，一个简单的1D-FFT 就可以得到令人满意的效果。为了得到几何上的直线，VS 和 $H S$ 伪极坐标网格点必须在轴向和径向同时过采样，即在伪极坐标网格中需要均布的点集。这种伪极坐标网格的转换涉及两个操作。通过旋转射线得到轴向均匀的射线采样，并通过将圆变换成正方形（如同极坐标系中所要求的那样）得到同心圆。为了获得轴向均布的射线采样，用 $\tan ( N \pi p / 2 )$ 替代式（1）和（2）中 $\xi _ { k }$ 和 $\xi _ { l }$ 的 $2 p / N$ ，形成新的网格点 $\boldsymbol { V } \boldsymbol { S } _ { n e w }$ 和 $H S _ { n e w }$ ，这些新的网格点可以通过下式计算：

$$
V S _ { n e w } = \left\{ \begin{array} { l l } { \displaystyle \xi _ { l } = \frac { \pi t } { N } \mathrm { f o r } - N \le t \le N , } \\ { \displaystyle \xi _ { k } = \frac { \pi \mathrm { t } } { \mathrm { N } } \tan \left( \frac { \pi \mathrm { p } } { 2 \mathrm { N } } \right) \mathrm { f o r } - \frac { \mathrm { N } } { 2 } \le p < \frac { N } { 2 } } \end{array} \right\}
$$

$$
H S _ { n e w } = \{ \begin{array} { l l } { \displaystyle \xi _ { k } = \frac { \pi t } { N } \mathrm { f o r } - N \le t \le N , } \\ { \displaystyle \xi _ { l } = \frac { \pi \mathsf { t } } { \mathbf { N } } \tan ( \frac { \pi \mathsf { p } } { 2 \mathrm { N } } ) \mathrm { f o r } - \frac { \mathrm { N } } { 2 } < p \le \frac { N } { 2 } \} } \end{array} 
$$

新的网格点 $\boldsymbol { V } \boldsymbol { S } _ { n e w }$ 和 $H S _ { n e w }$ 仍然以同心方格的方式组织，但是射线则根据角度而不是斜率等距分布。为了将圆形变换为正方形，根据其角度 $\xi _ { k }$ 和 $\xi _ { l }$ 沿每条射线除以一个常数，因此参数$p$ 的函数为

$$
R \left( p \right) = \left( 1 + \tan ^ { 2 } \left( \frac { \pi p } { 2 N } \right) \right) ^ { \frac { 1 } { 2 } }
$$

网格的结果如式（6）所示。

$$
\begin{array} { l } { \displaystyle \xi _ { \iota } = \frac { \pi \mathfrak { t } } { \mathbf { N } \mathbf { R } \left( \mathfrak { p } \right) } \mathrm { f o r } - \mathbf { N } \le 1 < N , } \\ { \displaystyle \xi _ { \iota } = \frac { \pi t } { N R \left( \mathfrak { p } \right) } \mathrm { t a n } \left( \frac { \pi p } { 2 N } \right) \mathrm { f o r } - \frac { \mathbf { N } } { 2 } < \mathfrak { p } \le \frac { N } { 2 } } \end{array}
$$

新的伪极坐标网格点 $\boldsymbol { V } \boldsymbol { S } _ { n e w }$ 和 $H S _ { n e w }$ 位于一条线上，并且以不同的间距等间距分布。通过使用式（6），频率的新极坐标网格点可以被定义为

$$
\xi _ { m , n } = \{ \xi _ { k } \left[ m , n \right] , \xi _ { l } \left[ m , n \right] \}
$$

在基础区域 $\xi \in \ [ - \pi , \pi ] ^ { 2 }$ 中，采样频率可以表示为

$$
\left\{ \begin{array} { l } { { \displaystyle \xi k \big [ m , n \big ] = \frac { \pi \mathrm { m } } { \mathrm { N } } \cos \big ( \pi n / 2 N \big ) } } \\ { { \displaystyle \xi l \big [ m , n \big ] = \frac { \pi \mathrm { m } } { \mathrm { N } } \sin ( \pi n / 2 N } } \end{array} \right\}
$$

大体来看，极坐标 DFT 映射 PDFT： $\tau [ m , n ] \ \to \Gamma \big ( \xi _ { m , n } \big )$ 是一个线性算子。

# 2人脸识别的符号数据建模方法

任何类型的生物识别系统的识别准确性都依赖于从训练生物特征集合中提取的差异特征。在本文所提出的工作中，使用频域变换来提取空间域中的局部变量。使用FFT获得的频域特征，在频域中表示不同的照明、表情变化和遮挡等情况。此外，保留低频分量以便提取分类所需的差异特征。在极坐标网格中，生成的FFT特征被评估为单维等距极坐标FFT值并转换为1DP-FFT。一维极坐标FFT中的最大幅度值被认为是人脸图像的特征描述符，并且被用来表示符号对象。所提出的工作使用与其他基于外观的人脸识别系统不同的特征表示，并且使用了一个特征值来表示整个脸部图像。不同人脸上的面部特征点如图1所示。

![](images/b1d6edf142dbf483d56d8e2fdea92005485451820a8be161e91f0aea5aefbbee.jpg)  
图1不同人脸上的面部特征点

此外，对于属于同一类的符号对象由区间值变量表示，即通过面部类别的 $N$ 个符号对象的最大和最小量值确定。

本文描述的工作使用FFT的周期性和复共轭对称性来进行数字人脸图像数据的2D-FFT分析。傅里叶变换用于将图像信息转换为空间频率域[15]。人脸图像 $\tau ( m , n )$ 上的二维离散傅里叶变换（2D-DFT）可以表示为

$$
\Gamma ( k , l ) = \sum _ { m = 0 } ^ { M - 1 } \sum _ { n = 0 } ^ { N - 1 } \tau ( m , n ) e ^ { - j { \frac { 2 \pi } { M } } m k - j { \frac { 2 \pi } { N } } n l }
$$

其中：坐标 $( k , l )$ 表示2D-DFT系数在原始谱中的位置；而坐标$( m , n )$ 表示图像 $\tau$ 中响应位置的灰度级。DFT 计算的高效率形式是快速傅里叶变换（FFT）。图像的FFT可以将图像信息转换到频域空间。FFT算法是信号和图像处理领域的核心，具有广泛的应用领域，如电信、密码学、医学成像和频谱分析等。在频域工作的一个优点是一些具有较高幅值的DFT系数足以代表图像或图像的一部分。

在这项工作中，通过使用Viola-Jones算法[l6]从相应标准数据库的原始图像裁剪人脸部分，并进一步将其转换为尺寸为$1 2 0 \times 1 2 0$ 像素的灰度图像来构建人脸数据库，如图2所示。接下来对已处理图像应用 FFT 以生成 2D-DFT 系数。在生成的2D-DFT系数中，低频分量分布在频谱的角落，表示图像中存在的边缘/线条。图像的低频分量包含了代表特定脸部图像所需的大部分信息，并具有较高的辨别力。然而有助于获得更精细细节的高频成分对于识别不太重要，并且对识别过程没有有效贡献。因此，本文在所提出的工作中，利用频谱的对称性来有效地保留低频分量。

![](images/fa0d9ba252d4f0ff284cb3cc1b79630558005df84887826803a38d7a0bb34909.jpg)  
图2原始图像

由于频谱的对称性，象限位置可以对角交换。通过考虑这个事实，低频位置被对角交换，使得低频位置出现在图像的中间，即偶数和奇数象限被交换以有效地计算低频分量。真实图像的DFT的基本性质是它的周期性和复共轭对称性。频谱在两个方向上无止尽地重复着。因此，只有DFT频谱的非冗余系数被考虑用于特征提取。

与使用面部图像的灰度值获得的协方差矩阵( $\cdot N R \times N C$ )相比，所得到的协方差矩阵 $\left( N R / 2 + 2 \right) \times \left( N C / 2 + 2 \right)$ 的大小约为四分之一。因此，协方差矩阵的估计可能对于特征提取更准确。在这项工作中，通过在新的合成协方差矩阵的末尾添加一串零来完成零填充，以便与人脸图像的原始大小，即 $N R \times N C$ 相同。现在，通过参考式（9），2D-DFT可以针对尺寸为 $N \times N$ （假设N 是偶数）的人脸图像 $\tau ( m , n )$ 定义新频谱，如式（10）所示。

$$
\begin{array} { r l } & { \Gamma ( k , l ) { = } \displaystyle \sum _ { m = - N / 2 n = - N / 2 } ^ { N / 2 } \tau ( m , n ) e ^ { - j \frac { 2 \pi } { N } m k - j \frac { 2 \pi } { N } n l } } \\ & { \mathrm { w h e r e } \frac { - N } { 2 } \mathrm { { \le } m / \mathrm { n } { \le } \displaystyle \frac { N } { 2 } } } \end{array}
$$

在式（10）中，坐标 $( k , l )$ 表示 2D-DFT 系数在新频谱中的位置；坐标 $( m , n )$ 表示图像 $\tau$ 相应位置的灰度值。在非冗余系数频谱上计算新的2D-DFT值与在原始频谱上计算2D-DFT 是类似的。使用式（10）可以计算非冗余DFT频谱（NRDFT)的半径和相位角。此外，非冗余傅里叶频谱可以通过DC系数移动到中心的 DFT 频谱的系数和 NRDFT 的半径的卷积来计算。相位谱的非冗余系数用于脸部图像的符号表示。与从原始灰度人脸图像获得的原始大小相比，相位谱的新表示将光谱的大小减小到其四分之一[17]。本章介绍了通过极坐标傅里叶变换（polarFouriertransform，PFT）分析NRDFT进行特征提取的方法。PFT生成旋转不变数据，特别适合提取具有细微变化的人脸图像的方向特征。

由于伪极坐标网格更接近极坐标网格，所以伪极坐标FFT到极坐标FFT的转换涉及1D 等间隔FFT，并且只有单个1D内插。对于一个尺寸为 $N \times N$ 的给定的二维人脸图像，极坐标FFT 算法产生一个复杂度为 $O \big ( N ^ { 2 } l o g N \big )$ 的极坐标 FFT。因此,在所提出的工作中实现伪极坐标FFT可以更高的精度和更快的速度计算面部特征。

# 3谱域特征提取与线性回归分类

# 3.1人脸特征的符号表示

一个人的脸部图像可能在表情、照明和遮挡等方面有所不同。由于这些信息的存在，那些使用更少特征值的传统系统难以进行精确识别。符号对象提供了一种有效方法来表示这种类型的信息。符号对象是经典数据类型的扩展。符号对象可以分为断言对象(assertion object)、囤积对象(hoard object)和合成对象(syntheticobject)。断言对象由属于给定对象的一组事件组成。事件是逻辑链接的特征变量和特征值/属性对的组合。一个或多个断言对象的组合称为囤积对象[17]，一个或多个囤积对象的组合称为合成对象。

在这项工作中，初始人脸图像是从原始图像中剪切出来的，并且用于提取极坐标FFT特征（表示为断言对象）。符号面部对象被描述为囤积对象，并由不同的断言类型对象使用最大一最小规则来构建。假设人脸图像数据集包含 $c$ 个图像类别，每个类别由 $s$ 个图像样本组成，这些人脸图像样本在表情、遮挡和照明方面各不相同。令 $\Omega _ { i } = \{ \tau _ { 1 , } \tau _ { 2 , } \tau _ { 3 } \ldots \tau _ { s } \}$ 表示一个人脸类的$s$ 个样本图像的集合，作为一级对象。一般来说，所有人脸图像的类别都可以表示为

$$
X = \left\{ \Omega _ { \mathrm { i , j } } \right\} , \forall i = 1 \mathrm { t o } C \mathrm { a n d } \forall j = 1 \mathrm { t o } S
$$

其中： $c$ 是人脸类别的数量；而 $s$ 表示第 $i$ 类的样本数量。表示属于第 $i$ 类的面部图像的符号数据模型的向量 $S D ^ { ( i ) }$ 可以表示为

$$
\mathbf { S D } ^ { ( \mathrm { i } ) } = \left\{ F 1 D \big ( \tau _ { 1 } ^ { i } \big ) , F 1 D \big ( \tau _ { 2 } ^ { i } \big ) , . . . , F 1 D \big ( \tau _ { s } ^ { i } \big ) \right\}
$$

此外，使用 $S D ^ { ( i ) }$ 的最大值和最小值作为第 $i$ 类的符号区间数据表示，可以按式（13）计算得到。

$$
F 1 D - M M ^ { ( i ) } = \left\{ m a x \big ( S D ^ { ( i ) } \big ) , m i n \big ( S D ^ { ( i ) } \big ) \right\}
$$

$$
\forall i = 1 \mathrm { t o } \ N
$$

进一步，使用式（13）所表示的 $c$ 类的符号知识库可以表示为

$$
S K B = \left\{ F 1 D - M M ^ { ( i ) } \right\} \forall i = 1 \mathrm { t o } C
$$

符号知识库矩阵 $S K B$ 表示所有的 $c$ 类， $S K B \ \in \ R ^ { \mathbb { C } \times \ 2 }$ ， $c$ 表示人脸类别的数量，数字2表示F1D-MM 的最大值和最小值。一般来说，第 $i$ 类的符号建模可以通过式（15）实现：

$$
{ S O } ^ { ( i ) } = \left\{ { S D } ^ { ( i ) } , { F 1 D } - { M M } ^ { ( i ) } \right\}
$$

其中： $S D ^ { ( i ) }$ 是 $F 1 D ( \tau _ { j } ^ { ~ i } )$ 的 $1 \times S$ 向量； $F 1 D - M M ^ { ( I ) }$ 是 $S D ^ { ( i ) }$ 的最大值和最小值， $\forall i = 1 , . . . , C ~ , ~ \forall j = 1 , . . . , S$ 。总之，矩阵 $S K B$ 包含每个类的 $s$ 个样本的 $F 1 D$ 的最大值和最小值，并且 $\boldsymbol { s D }$ 矩阵包含所有类的 $s$ 个样本的 $F 1 D$ 值。 $\boldsymbol { s D }$ 矩阵中的每个 $F 1 D$ 值表示一个图库脸部图像和 $S K B$ 矩阵中的每对值，即第 $i$ 类的最大和最小 $F 1 D$ 值代表该类的 $s$ 个样本。所提出的符号数据建模方法仅使用很少的特征值来表示图像的不同变化。3.2节将利用快速有效的线性回归分类算法实现分类。

# 3.2线性回归分类

使用线性回归方法进行人脸识别直接使用下采样的人脸图像作线性回归分析，然后采用最近邻分类器进行分类。

基于线性回归的人脸识别方法基本过程如下所述：

输入：类别模型 $X _ { i } \in R ^ { q \times S } ( i = 1 , 2 , . . . , C )$ 和测试图像向量y= R。其中，c是人脸的类别数；s是第i类人脸的训练图像数量； $\mathbf { \Phi } _ { q }$ 是每个图像的特征向量长度。

原始训练图像可表示为$\mu _ { i } ^ { m } \in R ^ { a \times b } ( i = 1 , 2 , . . . , C ; m = 1 , 2 , . . . , S )$ ，将大小为 $\boldsymbol { a } \times \boldsymbol { b }$ 的原始人脸图像下采样为 $c \times d$ 的图像 $( c < a , d < b )$ ，然后按照列的顺序拼接为一个长度为 $\scriptstyle q = c \times d$ 的一维向量 $X _ { i } ^ { m }$ ：

$$
\mu _ { i } ^ { m } \in R ^ { a \times b }  X _ { i } ^ { m } \in R ^ { q \times S }
$$

其中： $\scriptstyle q = c \times d$ 并且 $c \times d < a \times b$ ，因此类别模型 $X _ { i }$ 可表示为

$$
X _ { i } = [ x _ { i } ^ { 1 } , x _ { i } ^ { 2 } , . . . , x _ { i } ^ { p _ { i } } ] \in R ^ { q \times S }
$$

输出： $y$ 的类别。

计算过程：

a)针对每个类别模型，计算参数向量；

$$
\stackrel { \wedge } { \beta _ { i } } = ( X _ { i } ^ { T } X _ { i } ) ^ { - 1 } X _ { i } ^ { T } y ; i = 1 , 2 , . . . , C
$$

b)根据参数向量 $\hat { \beta } _ { i }$ ，计算预测向量 $\hat { \beta } _ { i } \in R ^ { q \times l }$

$$
\stackrel { \wedge } { y _ { i } } = X _ { i } \stackrel { \wedge } { \beta _ { i } } , i = 1 , 2 , . . . , C
$$

c)计算原始向量与预测向量之间的距离。

$$
{ d _ { i } } ( y ) = \left\| y - \hat { y _ { i } } \right\| _ { 2 } , i = 1 , 2 , . . . , C
$$

d)测试图像 $y$ 的类别由最近邻准则给出，若 $d _ { j } ( y )$ 满足

$$
d _ { j } ( y ) = \operatorname* { m i n } _ { i } d _ { i } ( y ) ; i = 1 , 2 , . . . , C
$$

则 $y$ 被分为第 $j$ 类

# 4实验结果

为了评估本文所提出的方法的性能，在公共人脸数据库如AR和佐治亚理工学院(GT)数据库上进行了多次实验。所提出的工作的实现平台是配备 $2 . 5 \ : \mathrm { G H z }$ Intel?B960 和2 GB DDR3RAM 的计算机，MATLAB 版本为2012a。AR 数据库由120个人的人脸数据组成，每个会话13个图像(图3)。所有人的26个面部图像样本在两个会话中被捕获，其展现出不同的照明、表情和遮挡。

![](images/55efeb2679ded2c6256c63bb25a30524853b7c1ccea7e1c43b9289e5e566e489.jpg)  
图3一个来自于AR数据库的典型样本

GT 数据库包括 50个主题，每个主题有15 张图片[19]。它描述了几个变化，如姿势、表情、杂乱的背景和照明(图4)。面部图像中存在光线条件的变化，面部表情（睁眼/闭眼，微笑/不微笑）和遮挡细节（戴眼镜/不戴眼镜）。与AR数据库中的人脸图像相比，GT数据库的图像在表情、姿势、遮挡、年龄、光照、分辨率以及背景等方面有很大的不同。

![](images/e42a8db3a4e13c60df98b5af43e88d2b726625afc7fedf9057644e18822c94e7.jpg)  
图4一个来自GT数据库的典型题材样本

在本文所提出的算法中，最初使用Viola-Jones算法将所有数据库中的图像裁剪成 $1 2 0 \times 1 2 0$ 像素尺寸，并转换成灰度图像。在AR数据库中，类别1图像编号从1\~13，类别2图像编号从14\~26。为了构建用于各种实验的120人的图像库，从AR数据库中选择类别1的1200个样本和类别2的1200个样本，并划分为表1中所列出的5个子集。

表1AR 数据库不同集合的分布  

<html><body><table><tr><td>图像变化类型</td><td>类别1图像(训练集）</td><td>类别2图像(测试集)</td></tr><tr><td>光照变化</td><td>1,5-7</td><td>14,18-20</td></tr><tr><td>表情变化</td><td>1-4</td><td>14, 15-17</td></tr><tr><td>太阳镜或围巾遮挡</td><td>8,11</td><td>21,24</td></tr><tr><td>戴围巾和光照变化</td><td>8,9</td><td>23-25</td></tr><tr><td>戴太阳镜和光照变化</td><td>12, 13</td><td>22,23</td></tr></table></body></html>

# 4.1使用AR数据库的性能比较

在本节中分析了所提出的符号建模和识别技术的准确性，并与文献[18]以及文献[19]中算提出的最新方法进行了性能比较，这些方法与本文所提出的方法相似。

文献[19]提出了一种基于局部逼近梯度与LDA（LAG-LDA）技术的人脸识别方法，并对AR数据库进行了各种实验，称为exp1到exp8。对于实验1\~4，笔者使用了类别1的从1至4编号的图像，并且对于实验5\~8，他们使用了类别1的编号从8\~13的图像用于训练并且用于测试所有AR数据库图像的不同组合。对于不同的面部表情和光照变化。在表2中展示了本文所提出的方法和LAG-LDA方法在AR数据库上的性能比较。

表2本文所提出的算法与LAG-LDA算法在AR数据库上的性能比较  

<html><body><table><tr><td rowspan="2">方法 集1)</td><td rowspan="2">光照变化（子表情变化（子 集2)</td><td rowspan="2">围巾遮挡+光 太阳镜遮挡+光照</td><td rowspan="2"></td></tr><tr><td>照变化（子集变化（子集4+子集 3） 5）</td></tr><tr><td>LAG-LDA 方法</td><td>90.13%(Exp6)91.62%(Exp1) 79.33%(Exp8)</td><td></td><td></td><td>93.03%(Exp7)</td></tr><tr><td>本文方法</td><td>96.39 %</td><td>93.93%</td><td>94.64%</td><td>95.46%</td></tr></table></body></html>

表2中的结果证明了本文所提出的方法的有效性。该方法在AR数据集上的光照变化（子集1）、表情变化（子集2）以及同时包含光照变化和遮挡影响（子集4和5）方面，实现了比LAG-LDA方法更好的性能。

另一种类似的方法，即WaqasJadoon 等人提出的扩展协同邻居表示（ECNR）技术[19]。本文方法与这一方法在AR 数据集上进行性能比较，ECNR方法在光照变化、表情变化、存在遮挡以及遮挡和光照变化同时存在的情况下对人脸图像的识别分别实现了90. $45 \%$ 、 $87 . 9 4 \%$ 、 $89 . 3 2 \%$ 和 $8 3 . 4 2 \%$ 的最佳识别率。表3中列出了本文所提出的方法和ECNR方法所在AR数据库上获得的实验结果。

从表3中同样可以得出一些结论，其中在表情变化（子集2）、光照遮挡（子集4和5）的情况下，本文所提出的方法的最佳识别率明显优于ECNR方法。在光照变化的情况下（子集1）本文得到了与ECNR方法相近的识别率。然而与ECNR方法相比，在存在遮挡（子集3）的情况下，本文所提出的技术的识别率稍低。

表3本文提出的算法与ECNR算法在AR数据库上的性能比较  

<html><body><table><tr><td colspan="4">光照变化（子表情变化（子存在遮挡（子遮挡+光照变化（子</td></tr><tr><td>方法 集1)</td><td>集2)</td><td>集3)</td><td>集4+子集5）</td></tr><tr><td>ECNR方法</td><td>90.45%</td><td>87.94%</td><td>89.32%</td><td>83.42%</td></tr><tr><td>本文方法</td><td>91.05%</td><td>93.43%</td><td>88.24%</td><td>91.36%</td></tr></table></body></html>

本文所提出方法的准确性与一些监督学习方法（如极小极大值框架）相当，后者处理一类高维 AR 图像数据集存在失真问题。为了实验目的，类似的设置已经按照文献[18]中的定义完成。即统一选择25名男性和25名女性的脸部图像，将所有图像缩小至 $3 2 \times 3 2$ 像素，并在整个数据集上使用10折交叉验证。表4列出了本文所提出的方法以及GMD（广义乘法失真）模型和文献[18]中提到的其他技术实验所得到的实验结果（结果取自文献[18]）。

表4本文提出的算法与最小最大值框架在AR数据库上的性能比较  

<html><body><table><tr><td>方法</td><td>准确率（%)</td></tr><tr><td>GMD</td><td>92.88</td></tr><tr><td>GMD(R)</td><td>98.50</td></tr><tr><td>SRC</td><td>93.29</td></tr><tr><td>RF</td><td>89.80</td></tr><tr><td>SVM(P)</td><td>38.30</td></tr><tr><td>SVM(R)</td><td>94.55</td></tr><tr><td>KNN(E)</td><td>95.64</td></tr><tr><td>KNN(C)</td><td>96.59</td></tr><tr><td>KLDA(P)</td><td>94.72</td></tr><tr><td>KLDA(R)</td><td>97.33</td></tr><tr><td>本文方法</td><td>97.51</td></tr></table></body></html>

表4显示了所提出的方法与文献[18]中提到的其他现有技术分类器：GMD、SRC、RF、GMD（R）、SVM（P）、SVM（R）、KNN（E）、KNN（C）、KLDA（P）、SVM（R)和KLDA（R）相比（除了GMD（R）分类器）的比较，本文所提出的技术在AR数据库上实现了最佳的识别准确率。

从表2和4的结果可以看出，本文所提出的用于人脸识别的符号相似度方法的识别准确度比从ECNR、LAG-LDA和极小极大值框架方法所获得的识别准确度要高，并且对光照变化、表情变化和遮挡等情况下的人脸图像识别具有一定的鲁棒性。

# 4.2使用GT数据库的性能比较

本文所提出的符号建模和相似性分析方法的性能也与文献[20]中所定义的一些类似方法进行了比较，并且也进行了类似的实验设置。将从GT数据库的原始人脸图像，使用Viola-Jones方法将人脸部分裁剪成 $1 2 0 \times 1 2 0$ 像素的大小的图像。为了进行实验，从每个人的图像中随机选择六幅图像进行训练，其余图像被用于测试阶段。表5列出了从文献[20]中提到的方法与本文所提出的方法对GT数据库的图像进行识别的实验结果。

表5本文所提出的算法与文献[20]中所提出的方法在GT数据集下进行识别的性能比较  

<html><body><table><tr><td>方法</td><td>识别率/%</td></tr><tr><td>Fisherfaces</td><td>91.80</td></tr><tr><td>Eigenfaces</td><td>87.65</td></tr><tr><td>Symbolic PCA</td><td>94.85</td></tr><tr><td>Symbolic ICA</td><td>89.15</td></tr><tr><td>SymbolicKPCA</td><td>95.45</td></tr><tr><td>Symbolic LDA</td><td>97.50</td></tr><tr><td>本文方法</td><td>98.02</td></tr></table></body></html>

表5的实验结果表明，本文所提出的方法优于Fisherfaces、Eigenfaces、符号PCA方法、符号ICA和符号KPCA以及符号

LDA方法。

# 5 结束语

本文提出了一种用于人脸识别的谱域特征提取算法，有效利用了人脸图像中的局部空间变化。最初，使用Viola-Jones算法将人脸从图像中裁剪出来，并转换成尺寸为 $1 2 0 \times 1 2 0$ 像素的灰度图像。在预处理的图像上执行2D-DFT。2D-DFT系数的主要量值是使用极性傅里叶变换技术计算的，并表示为1DP-FFT。特征值是1DP-FFT幅值中的最大值。提取的特征值用于构造表示人脸图像的符号对象。最后利用快速有效的线性回归分类算法实现分类。由于使用了极坐标FFT，所提出的方法不仅有效，而且比基于笛卡尔傅里叶变换的其他方法更精确。本文提出的符号建模方法不仅提供了表示人脸特征的新方法，还提高了识别的准确性。对AR和GT数据库所获得的实验结果进行了详细分析，并与其他一些最近报道的方法进行了性能比较，本文所提出的方法的性能令人满意。

# 参考文献：

[1]刘峰，孟凡荣，梁志贞．基于一阶和二阶信息图像表示的人脸识别[J]. 计算机应 用研究,2017,34(2):603-606.(Liu Feng,Meng Fanrong,Liang Zhizhen.Face recognition based on combining first and second derivative information of images [J].Application Research of Computers,2017,34 (2): 603-606.)   
[2] 徐梦珂，许道云，魏明俊．基于 2D-KPCA 的拉普拉斯特征映射人脸识 别[J].计算机应用研究，2017，34(7):2212-2215.(Xu Mengke，Xu Daoyun,Wei Mingjun.Laplacian feature mapping face recognition based on 2D-KPCA [J].Application Research of Computers，2017,34（7): 2212-2215.)   
[3]Sharif M,Bhagavatula S,Bauer L,et al. Accessorize to a crime: real and stealthy attacks on state-of-the-art face recognition [C]// Proc of ACM Sigsac Conference on Computer and Communications Security. 2016: 1528-1540.   
[4]Perlibakas V.Face recognition using principal component analysis of the wavelet packet decomposition [J]. Social Science Electronic Publishing, 2017,15 (15): 243-250.   
[5] Zhao Jianwei, Zhou Zhenghua,Cao Feilong.Human face recognition based on ensemble of polyharmonic extreme learning machine [J].Neural Computing & Applications,2014,24(6):1317-1326.   
[6]Klare B F,Klein B,Taborsky E,et al.Pushing the frontiers of unconstrained face detection and recognition: IARPA Janus Benchmark A [C]// Proc of IEEE Computer Vision and Pattern Recognition.2015: 1931-1939.   
[7]Anjos A,Chakka M M, Marcel S. Motion-based counter-measures to photo attacks in face recognition [J].IET Biometrics,2014,3 (3):147-158.   
[8]Ben Xianye,Meng Weixiao,Yan Rui,et al. Kernel coupled distance metric learning for gait recognition and face recognition [J]. Neurocomputing, 2013,120 (10):577-589.   
[9]杨恢先，贺迪龙，谭正华，等．融合单演特征和CS-LBP 的单样本人脸 识别[J].计算机工程与应用,2017,53(6):150-155.(Yang Huixian,He Dilong，Tan Zhenghua,et al. Face recognition based on monogenic features and CS-LBP [J]. Computer Engineering and Applications,2017, 53 (6): 150-155.)   
[10] Averbuch A,Coifman RR,Donoho DL,et al.Fast and accurate polar Fourier transform [J].Applied and Computational Harmonic Analysis, 2006,21 (2): 145-167.   
[11] Zeng Dan,Zhao Qijun,Long Shuqin,et al.Examplar coherent 3D face reconstruction from forensic mugshot database [J].Image & Vision Computing,2017,58(C): 193-203.   
[12]廖延娜，马超．基于稀疏表示的人脸识别系统设计与实现[J]．电子设 计工程,2016,24(17):153-155.(Liao Yanna,Ma Chao.The design and implementation of face recognition system based on sparse representation [J].Electronic Design Engineering,2016,24(17): 153-155.)   
[13] Marone F,Stampanoni M.Regridding reconstruction algorithm for real-time tomographic imaging [J].Journal of Synchrotron Radiation,2012, 19 (6):1029-1037.   
[14] Vatsalan D, Christen P, Verykios V S.A taxonomy of privacy-preserving record linkage techniques [J]. Information Systems,2013,38 (6): 946-969.   
[15]张宝强，蔡述庭．基于空间频率域非局部总变差的压缩磁共振图像[J]. 自动化与信息工程,2016,37(4):35-39.(Zhang Baoqiang,Cai Shuting. Compressed magnetic resonance image based on nonlocal total variation spatial-frequency domain [J].Automation & Information Engineering, 2016,37 (4): 35-39.)   
[16]Da'San M,Alqudah A,Debeir O.Face detection using Viola and Jones method and neural networks [C]//Proc of IEEE International Conference on Information and Communication Technology Research.2O15:40-43.   
[17]Meena HK, Sharma KK,Joshi SD.Face recognition under variations in illumination using the phase of fractional Fourier transform [C]//Proc of International Conference on Emerging Trends in Computing and Communication Technologies.2017:1-4.   
[18] Cheng Qiang,Zhou Hongbo,Cheng Jie,et al.A minimax framework for classification with applications to images and high dimensional data [J]. IEEE Trans on Pattern Analysis& Machine Intelligence,2O14,36 (11): 2117-2130.   
[19]Li Zhaokui,Wang Yan,Fan Chunlong,et al. Image preprocessing method based on local approximation gradient with application to face recognition [J].Pattern Analysis and Applications,2015,20 (1):1-12.   
[20] Ahmed H,Mohamed J,Noureddine Z. Face recognition systems using relevance weighted two dimensional linear discriminant analysis algorithm [J].Journal of Signal & Information Processing,2012,3(1): 130-135.