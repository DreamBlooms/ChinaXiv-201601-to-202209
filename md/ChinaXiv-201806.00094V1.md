# 基于Gabor小波和CNN的图像失真类型判定算法

李鹏程，吴涛，张善卿(杭州电子科技大学 计算机学院，杭州310018)

摘要：针对图像失真分类问题，提出了一种基于Gabor 小波和CNN（convolutional neural network，卷积神经网络）的失真类型判定新算法。该算法先利用Gabor 小波的良好特性对图像进行特征粗提取，再通过改进的CNN 进一步提取关键特征。算法步骤包括：首先对图像进行预处理（包括标签设定、样本均衡和样本扩充)；然后对预处理后的图像进行8方向的Gabor小波变换，并将不同方向的子带叠加构成输入样本；最后通过自行设计的CNN和Softmax 分类器对样本进行训练，训练的过程中采用随机梯度下降和反向误差传播的方法对卷积核参数进行优化得到最终模型。利用训练好的模型进行失真类型判定实验，在LIVE标准图像库上分类正确率达到 $9 5 . 6 2 \%$ ，表明本算法具有较高的准确性和鲁棒性。

关键词：卷积神经网络；Gabor小波；失真类型；特征学习 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2018.03.0231

# Image distortion judgement based on Gabor wavelet and CNN

LiPengcheng,Wu Tao, Zhang Shanqing† (School of Computer Science&Technology,Hangzhou Dianzi University,Hangzhou31oo18,China)

Abstract:For image distortion clasification，this paper proposes an algorithm based on Gabor wavelet and CNN (Convolutional Neural Network).Ituses thegoodcharacteristicof Gabor wavelettoextractroughfeatureof images firstly and thenuses the improved CNN to extract the key feature from rough feature.The main steps include:Images are preprocessed firstly (including labelsseting,samples balanceand samples expansion）；Then itcalculates eightdirections Gabor wavelettopreprocessedimages,andthenaddeightsub-bands toonesampleforraining;Finally,itusesaself-designed CNN and Softmax clasifier to train the final model,anduses the methods ofrandom gradientdescentand error back propagationtooptimizetheparameters ofconvolution kerels duringtraining.Thefinal modelisused todeterminethe typeof image distortion,the classification accuracy on the LIVE standard image library is $9 5 . 6 2 \%$ , it shows that the proposed method has high accuracy and robustness.

Key words: convolutional neural network; Gabor wavelet; image distortion type; feature learning

# 0 引言

图像在采集、压缩、处理和传输过程中不可避免的会出现各种类型和程度的失真。这不仅影响视觉体验，而且很有可能带来巨大的损失。因此，图像质量评价的研究越来越受到人们的重视，特别是图像不同失真类型的判定以及针对特定失真类型的评价算法。

目前，已经有一些针对特定失真类型的评价算法，如针对模糊图像的评价算法错误!未找到引用源，错误!未找到引用源。、噪声图像的评价算法错误!未找到引用源。错误!未找到引用源。在使用这些算法前，要先进行失真类型的判定。由于不同的失真类型有不同的特征，这些特征之间有的差异很明显，有的却易混淆。因此，失真类型的判定成为难点之一。为了解决此问题，已有学者提出一系列失真类型区分的方法，其大致可分为两类：第一类通过提取图像空域或频域的特征，然后利用传统的机器学习方法进行判定，如文献错误！未找到引用源。；第二类是基于深度学习的方法，如文献[7]。

第一类方法最常见的是利用图像的NSS（natural scenestatistics，自然场景统计）特征。图像的NSS特性将自然图像转到图像的DCT域或小波域提取特征，该特征用相应的数学统计模型来描述，同时这种模型的参数会随着不同的图像失真类型以及失真程度而改变错误!未找到引用源。。基于 NSS 的方法主要包括

BIQI 错误!未找到引用源。，DIVINE 错误!未找到引用源。和 BRISQUE错误！未找到引用源。等。BIQI方法首先提取失真图像小波域的统计特征，然后利用传统机器学习的方法进行失真类型分类。DIVINE方法首先对失真图像进行多尺度的小波分解，然后利用图像的NSS特性拟合混合高斯函数的参数作为该图像的特征，最后利用这些特征对图像的失真类型进行识别。BRISQUE方法首先提取空域的NSS特征，最后利用SVM分类器对图像的失真类型进行分类。

第二类方法是基于深度学习的方法。相比于传统的机器学习，深度学习更能提高评价的精度。例如文献错误!未找到引用源。中，Hou等人将含有多个隐藏层的深度信念网络(deepbeliefnetwork)用在图像质量评价。作者在文章中并没有使用回归的思想对图像的质量进行预测，而是利用深度学习分类的方法，首先将图像的质量分成几类包括“极好的”“好的”“一般”“不好”和“很差”，然后计算待测图像对应每类的后验概率，最后综合这些后验概率作为此图像的质量分数。此文献表明按图像失真程度对深度学习网络进行分类训练的方法是可行的。在文献[7]中，郭美银等首先对不同失真类型的图像进行分块，然后将这些图像块进行局部对比归一化，最后通过训练好的CNN进行失真类型判定。实验表明此方法在LIVE 错误未找到引用源·图像库中能够得到比 BIQI、DIVINE 和 BRISQUE 方法更好的效果，但准确率仍有很大的提升空间。总的来说，基于深度学习的方法一般具有更高的准确率，但已有的深度学习算法，如文献[7]，由于每种图像失真类型类内失真程度跨度较大，从而使得训练样本类内的差异大于类间的差异，最终导致出现较大的误差。

针对这些问题，本文提出一种基于Gabor小波和CNN的图像失真类型判定算法。不同于文献[7]，本文算法不仅对样本的失真类型进行了划分，还对每种失真类型按图像的失真程度进行了再次分类。为了更好对图像特征进行粗提取，在训练之前对图像进行Gabor小波变换。同时，本文使用了不同的CNN结构进行训练。实验表明改进后的网络收敛速度更快，分类结果更准确。

# 1 判定算法

失真类型判定算法主要分为四个步骤：a)预处理，包括样本扩充、样本均衡和样本标签设定等；b)8方向的Gabor小波变换对图像进行信号分解，将分解后的子带进行叠加作为输入样本；c)通过CNN 神经网络和Softmax 分类器对叠加后的样本进行训练；d)利用训练好的模型对图像的失真类型进行判定。算法的流程如图1所示。

![](images/4566faf0246ccb921b728208a8a0d82bc5efe65cd7ffafc7406de2ecf1c045ad.jpg)  
图1算法流程

# 1.1样本预处理

1.1.1样本扩充

在图像训练之前，为了尽量增加样本的数量，对所有样本进行了分块处理，具体操作为：将一张图像可重叠地分为 $\mathsf { N } { \times } \mathsf { N }$ 的图像块，每个图像块作为一个图像样本，N的值和重叠采样的步长通过实验得到。为了保证正确性，还对背景虚幻的图像做了剪切处理，如图2所示。

![](images/1cb7cbf44434869acf99b8c84db9a96368e6360c00ee4127bf134df0afc76c5b.jpg)  
图2背景虚化图像裁剪处理

# 1.1.2样本均衡化

由于不同类别的样本数量可能分布不均匀，这种情况将导致最终分类结果不准确。为了使不同类别的样本数量保持均衡，对一些图像样本进行仿射变换。均衡化过程如下所示：

a)计算各类样本数量之间的比值：

$$
\rho = \frac { N _ { a } } { N _ { b } }
$$

其中： $N _ { a }$ ， $N _ { b }$ 分别为 $a$ 类和和 $b$ 类的样本数量。当该值在一个合理的范围时，则认为样本之间是均衡的，该值的合理区间$\rho { \in } [ \sqrt { 2 } / 2 , \sqrt { 2 } ]$ 。

b)如果 $\rho$ 值不在合理区间，则需要对样本进行旋转或者缩放这两种仿射变换[7]。直到 $\rho$ 的值在合理的区间为止。

# 1.1.3样本标签设定

在设置标签的时候除了按照不同失真类型进行设定，还对每种失真类型按照失真程度进行了再分类。例如，对LIVE图像库中失真类型为高斯模糊（Gblur）和高斯白噪声（WN）的图像进行标签设定的流程为：首先按照失真类型分为两类；然后再将这些图像的DMOS(differential mean opinion score，差异主观分数)值归一化到[0,1]并等分为三个区间；最后分别按照每幅图像的DMOS值所在区间的位置再分类，具体做法如表1所示。这样进行再分类减小类内样本之间的差异，避免训练的过程中给CNN网络带来紊乱，从而提高准确率。

![](images/6647c37fdaee5f610373a3b2e1afb873fd99fbdae62bd9c89743d5c7952d67bb.jpg)

# 1.2Gabor 小波变换

在正式训练之前，使用Gabor小波对样本进行变换。Gabor小波不同于其他小波，它除了能得到图像的频域信息还能得到图像的时域信息，选用它的原因如下：a）Gabor小波具有多尺度多方向的选择特性，对图像的边缘敏感，对光照不敏感，因此具有良好的光照不变特性；b）2D-Gabor小波变换核具有优良的空间局部性，能够提取图像多尺度多方向的局部结构特征，与人眼细胞的结构和功能很类似；c）Gabor小波变换可用于图像特征提取，与其他特征提取方法相比，具有处理数据少、速度快和鲁棒性好等特点。同时，图像小波域的NSS特征对图像的失真类型敏感。图3展示了不同失真类型的图像经Gabor小波变换后子带叠加之后的直方图表示，其中的数据经过了归一化。从直方图的形状可以看出，不同的失真类型的图像经Gabor小波变换后直方图的形状大不一样，这说明图像失真类型可利用Gabor小波变换进行判定。

Gabor小波变换由式（2）来表示。

$$
I _ { p , q } ( x , y ) = \sum _ { s } \sum _ { t } f ( x - s , y - t ) \varphi _ { p , q } ^ { \prime } ( s , t )
$$

其中： $f ( x , y )$ 是进行小波变换的原图像， $x , \ y$ 为图像中像素的位置，参数 $s , \ t$ 为滤波器中元素的位置， $p = \{ 0 , 1 , . . . , P - 1 \}$ 、$q = \{ 0 , 1 , . . . , Q - 1 \}$ 为小波变换的尺度和方向。函数 $\varphi _ { p , q } ^ { \prime } ( x , y )$ 为Gabor小波变换函数 $\varphi _ { p , q } ( x , y )$ 的复共轭， $\varphi _ { p , q } ( x , y )$ 的定义和求解过程可参考文献错误！未找到引用源。。图像经8个方向上的卷积核卷积之后产生8幅不同方向的子带图像，然后通过式（3)对所有子带进行叠加得到训练样本。

$$
S = \frac { I _ { 0 , 0 } + I _ { 0 , 1 } + . . . + I _ { 0 , Q - 1 } } { Q }
$$

其中 $I _ { 0 , i }$ 为第 $i$ 个方向的子带图像。

![](images/cba20d594e512631679e7d950b0aa718a9d5a08e9d25fcf1734267bd538af239.jpg)  
图3不同失真图像及经过Gabor小波变换后子带叠加的直方图展示

# 1.3模型的设计与训练

1.3.1卷积神经网络激活函数的确定

由于使用了Gabor小波对样本进行了处理，这会产生很多稀疏特征。为了使这些数据更易于表示，同时加快收敛速度，本文使用了文献错误！未找到引用源。中LReL（leakyrectifiedlinear）激活函数，如式（4）所示，其是ReLU函数错误！未找到引用源。的一种改进版（当系数 $\scriptstyle a = 0$ 时即为ReLU函数)。这种改进不仅利于稀疏数据的处理，而且还考虑到了ReLU函数可能会使得某些神经元长期处于未激活状态的不足。

$$
h ( x ) = \left\{ \begin{array} { c } { W ^ { T } x , W ^ { T } x > 0 } \\ { a W ^ { T } x , W ^ { T } x \leq 0 } \end{array} \right.
$$

式中 $\boldsymbol { W } ^ { T }$ 为权值， $x$ 为特征值， $\boldsymbol { a }$ 为接近0的常数，其值可以通过实验得到。

# 1.3.2卷积神经网络卷积核的确定

通过最小化网络损失函数 ${ \cal L } ( W , b )$ 确定卷积神经网络中的卷积核的权值向量，本文使用的损失函数 $L$ 为平方损失函数，并加入了正则项防止过拟合，具体代价函数表示如下：

$$
J ( W , b ) { = } { \left[ { \frac { 1 } { m } } { \sum _ { i = 1 } ^ { m } } { L } ( W , b ; x ^ { ( i ) } , y ^ { ( i ) } ) \right] } { + } { \frac { \lambda } { 2 } } R ( h )
$$

$$
R ( h ) = \sum _ { l = 1 } ^ { n _ { l - 1 } } \sum _ { i = 1 } ^ { s _ { l } } \sum _ { j = 1 } ^ { s _ { l + 1 } } ( W _ { j i } ^ { ( l ) } ) ^ { 2 }
$$

其中： $m$ 为样本数量， $y$ 为预测标签， $\lambda$ 为权重衰减参数， $R ( h )$ 为正则化项， $\mathbf { \xi } _ { l }$ 为隐层序号， $i$ 为每个隐层中神经元的序号， $j$ 表示与每个神经元链接的权值的序号。

为了最小化代价函数 $\boldsymbol { J } ( W , b )$ ，采用随机梯度下降法和反向误差传播算法进行参数更新，参数 $W$ 和 $b$ 按照式（7）更新。

$$
\left\{ \begin{array} { l l } { \displaystyle W _ { i , j } ^ { ( l ) } = W _ { i , j } ^ { ( l ) } - \alpha \frac { \hat { \sigma } } { \hat { \sigma } W _ { i , j } ^ { l } } J ( W , b ) } \\ { \displaystyle b _ { i } ^ { ( l ) } = b _ { i } ^ { ( l ) } - \alpha \frac { \hat { \sigma } } { \hat { \sigma } b _ { i } ^ { ( l ) } } J ( W , b ) } \end{array} \right.
$$

其中: $\alpha$ 是学习速率，用于控制梯度下降步长，考虑到越接近最优解的时候，梯度下降的幅度越小，将固定步长改成动态变化步长，具体如下式：

$$
\alpha ^ { t } = \left\{ { \begin{array} { l l } { 0 . 5 * \alpha ^ { t - 1 } \ J ^ { t } \geq J ^ { t - 1 } } \\ { \alpha ^ { t - 1 } \ } & { J ^ { t } < J ^ { t - 1 } } \end{array} } \right.
$$

其中：上标 $t$ 为迭代数， $J$ 为代价函数的值。另外，为了防止过拟合，在全连接层还使用了Dropout方法。该方法是由Hinton等错误!未找到引用源。提出的，这样在训练的过程中以一定的概率随机忽略一些隐层神经元的影响。

# 1.3.3网络结构

本文使用的网络结构如图4所示。

全连接层SROEGEGONL采样块图像降采样层1 降采样层2 降采样层3 降采样层4卷积层1 卷积层2 卷积层3 卷积层4

卷积网络一共有11层，包括输入层、4层卷积层，4层池化层，全连接层和输出层。第一层卷积层采用32个 $5 { \times } 5$ 大小的单通道滤波器对输入图像进行卷积，然后采用MaxPooling方法进行池化，第二层卷积层采用64个 $3 { \times } 3$ 的32通道滤波器对上层池化层进行卷积，池化操作同上，第三层卷积层采用32个64通道的 $3 { \times } 3$ 滤波器进行卷积，池化方法同上，第四层是利用128个 $5 { \times } 5$ 的32维滤波器对上层池化层进行卷积，池化方法同上。全连接层是将上层池化层得到的神经元首尾连接成一维向量，然后跟2048个全连接层神经元进行计算得到2048维的特征向量，全连接层还包括Dropout层，该层是将2048维特征通过Dropout方法进行过滤得到最后的特征向量。输出层是将最后的特征向量通过Softmax分类器进行分类。

# 2 实验结果与分析

# 2.1实验环境与样本集划分

实验环境为Intel $\textsuperscript { \small | \textregistered }$ CoreTMi5CPU2.80GHZ，内存为8G,操作系统为64位Windows7旗舰版，利用Python3.6.1软件基于TensorFlow1.2.1框架进行实验。选取了LIVE 数据库中失真类型为高斯模糊（Gblur）、JEPG压缩失真（JPEG）、高斯白噪声（WN）、JPEG2000 压缩（JP2K）和快速衰退瑞利通道失真（FF)等图像作为样本，它们各自的样本数量分别为145、204、145、198和145幅。在正式训练之前，所有样本被随机划分为三个部分：训练集，验证集和测试集。本文将所有样本的 $60 \%$ 用于训练， $20 \%$ 用于验证， $20 \%$ 用于测试。

# 2.2 对比实验与分析

# 2.2.1极端样本的分类结果分析

为了验证本算法的鲁棒性，图5列出了四张不同失真类型的图像以及DMOS值（归一化后)。表2列出了不同算法对它们失真类型判定的结果。从DMOS值可看出这四张图像的质量是接近无失真图像的，对于失真类型人眼似乎很难区分，但是从本文算法判定结果来看，所提出的算法对这些失真程度均能进行准确的分类，而且还能给出图像大概失真程度。相反，对于其他算法，总存在一些错误的判定，具体参见表2。

# 2.2.2数据库整体比较

为了更好地说明本算法的准确性和鲁棒性，本文给出了如图6所示的混淆矩阵，该矩阵是检测LIVE图像库中所有图像失真类型的分类结果。混淆矩阵中的值表示不同失真类型之间的混淆程度，第i行第j列的值代表第i类失真图像被分为第j类失真图像的概率。从矩阵中可以看出，JP2K失真与FF失真有较大程度的混淆，JPEG失真与JP2K失真有一定程度的混淆。而WN、Gblur失真和其它失真类型几乎没有混淆。从整体数据来看，各种失真类型之间的混淆概率都比较低，本算法较适用于JPEG、WN和Gblur失真类型的判定。

![](images/f266685d88540bdeee26a4af07ad79fc7aa40c54f42df99a770d42740f9e1ae7.jpg)  
图4改进后的卷积神经网络  
图5不同失真类型图像  
图6在LIVE数据库上的混淆矩阵

表2图5图片的分类结果(×:错误, $\surd$ ：正确)  

<html><body><table><tr><td>编号</td><td>DMOS</td><td>BIQI</td><td>DIIVINE</td><td>BRISQUE</td><td>本算法</td></tr><tr><td>(a)</td><td>0.2131</td><td>×</td><td>√</td><td>√</td><td>√ (好的)</td></tr><tr><td>(b)</td><td>0.2555</td><td>√</td><td>×</td><td>√</td><td>√ (好的)</td></tr><tr><td>(c)</td><td>0.1997</td><td>×</td><td>×</td><td>×</td><td>√ (好的)</td></tr><tr><td>(d)</td><td>0.2179</td><td>√</td><td>√</td><td>√</td><td>√ (好的)</td></tr></table></body></html>

JP2K 0.9030 0.0120 0.0000 0.0040 0.0810 JPEG 0.0305 0.9550 0.0000 0.0145 0.0000 原店 WN 0.0000 0.0037 0.9963 0.0000 0.0000 Gblur 0.0000 0.0000 0.0000 0.9940 0.0060 FF 0.0860 0.0120 0.0140 0.0180 0.8700 JP2K JPEG WN Gblur FF 真实类型

表3列出了本文算法与其他算法在LIVE 数据库中的判定准确率，包括每类失真检测的准确率和整体准确率。从表中可以看出，除了WN失真检测的准确率要稍逊于其它几种方法之外，本文算法对失真类型判定的准确率都要好于其它算法。从整体准确率来看，本文的方法优于其他方法。

表3各类算法在LIVE 数据库中的准确率 $( \% )$   

<html><body><table><tr><td>方法</td><td>JP2K</td><td>JPEG</td><td>WN</td><td>Gblur</td><td>FF</td><td>全部</td></tr><tr><td>BIQI</td><td>86.36</td><td>88.46</td><td>92.59</td><td>68.75</td><td>66.67</td><td>80.99</td></tr></table></body></html>

<html><body><table><tr><td>DIIVINE</td><td>80.00</td><td>80.09</td><td>100.00</td><td>90.00</td><td>73.40</td><td>83.74</td></tr><tr><td>BRISQUE</td><td>82.90</td><td>88.89</td><td>100.00</td><td>96.70</td><td>83.33</td><td>88.60</td></tr><tr><td>文献[7]</td><td>88.10</td><td>90.91</td><td>100.00</td><td>97.37</td><td>84.00</td><td>92.22</td></tr><tr><td>本文方法</td><td>90.30</td><td>95.50</td><td>99.63</td><td>99.40</td><td>87.00</td><td>95.62</td></tr></table></body></html>

# 2.3参数对比实验

本算法中有很多参数，为了更好地确定参数的值，在LIVE数据库中做了交叉验证实验。

# 2.3.1数据库整体比较

为了找到图像块合适的尺寸，使用控制变量法，通过调整图像块的大小进行了实验。为了避免样本数量不均衡，采用了可重叠的图像块采样方式。由表4可知，当块的大小为 $6 4 \times 6 4$ 时，本文算法得到的总体准确率最高。

表4不同图像块尺寸的总体分类准确率 $( \% )$   

<html><body><table><tr><td>块的尺寸</td><td>28</td><td>36</td><td>64</td><td>72</td><td>80</td></tr><tr><td>准确率(%)</td><td>86.34</td><td>90.72</td><td>95.62</td><td>93.21</td><td>90.80</td></tr></table></body></html>

# 2.3.2采样的步长

当图像块大小为 $6 4 \times 6 4$ 时，为了确定最合适的采样步长，进行了不同采样步长的实验，如图7所示。图中的横坐标表示采样步长，纵坐标表示总体准确率。从图中的曲线走势可以看出当采样的步长为32时，总体准确率最高。

# 2.3.3卷积核尺寸

为了确定卷积核的大小，再次使用控制变量法进行实验。在其他条件不变的情况下，首先将每个卷积核都设计成相同的尺寸 $3 { \times } 3$ ，然后从第一个卷积核开始通过更改每层卷积核的大小，依次确定每个卷积核最合适的尺寸。具体的实验结果如表5所示，表中用黑体标注了每个卷积核对应的最高的准确率。

![](images/f6b0b1af7eee79644d1ef34764e41e3199c2613d7fcbf4666a2a35bbf4361deb.jpg)  
图7不同采样步长对应的总体准确率

表5不同尺寸的卷积核得到的总体准确率 $( \% )$   

<html><body><table><tr><td>卷积核尺寸</td><td>3*3</td><td>5*5</td><td>7*7</td><td>9*9</td></tr><tr><td>卷积核1</td><td>94.613</td><td>95.200</td><td>94.936</td><td>94.100</td></tr><tr><td>卷积核2</td><td>95.200</td><td>95.013</td><td>94.987</td><td>94.900</td></tr><tr><td>卷积核3</td><td>95.200</td><td>95.113</td><td>95.000</td><td>94.998</td></tr><tr><td>卷积核4</td><td>95.200</td><td>95.620</td><td>95.420</td><td>95.400</td></tr></table></body></html>

从表中可以看出，当第一个卷积核为 $5 { \times } 5$ ，第二个卷积核为 $3 { \times } 3$ ，第三卷积核为 $3 { \times } 3$ ，第四个卷积核为 $5 { \times } 5$ 时，整体准确率是最高的。

# 2.3.4LRel激活函数中系数a

为了确定激活函数中的常数 $a$ 的值，在保持其他参数一致

的条件下，通过调整 $a$ 的值计算不同的总体准确率。图8展示了 $a$ 的值及其对应的总体准确率之间的关系。由图8可知，当$a = 0 . 0 0 4$ 时，总体准确率最高。

# 2.4 运行时间分析

为了与其他方法进行比较，表6列出了本文算法与其他算法的运行时间。从表中可以看出，本文算法的运行速度虽然没有BIQI和BRISQUE快，但基本上可以达到实时判定的效果。

![](images/ccd2f0a49baea70ced8f50a1ee464314c28356a4bd5b3e32d5423fda5e33a410.jpg)  
图8不同 $a$ 对应的总体准确率

表6运行时间比较  

<html><body><table><tr><td>方法</td><td>BIQI</td><td>DIVINE</td><td>BRISQUE</td><td>文献[7]</td><td>本文</td></tr><tr><td>时间/s</td><td>1.2881</td><td>7.3802</td><td>0.41329</td><td>2.4194</td><td>1.5152</td></tr></table></body></html>

# 3 结束语

为了使用深度学习的方法进行图像失真类型的判定，并解决已往方法中类内差异大于类间差异的问题，本文提出一种基于Gabor小波和CNN的图像失真类型判定算法。该算法首先对样本进行不同方向的Gabor小波变换，对变换后的小波子带进行叠加作为样本；然后利用自行设计的CNN对叠加后的样本进行训练，得到最终模型；最后，利用该模型对图像进行失真类型判定。在LIVE图像库上进行了实验，实验表明新方法具有较高识别率。

# 参考文献：

[1]Wang Zhengzi,Xie Zhihua,He Cuiqun.A fast quality assessment of image blur based on sharpness [C]//Proc of International Congress on Image and Signal Processing.2010: 2302-2306.   
[2]Li Leida,Lin Weisi，Wang Xuesong，et al.No-referenceimage blur assessment based on discrete orthogonal moment [J].IEEE Trans on Cybernetics,2016,46(1):39-50.   
[3]崔光茫，冯华君，徐之海，等．基于CSF和仿射重建模型的噪声图像质 量评价[J].浙江大学学报：工学版，2016，50(1):144-150.（Cui Guangmang,Feng Huajun，Xu Zhihai,et al. No-ise image quality assessment based on CSF and affine reconstruction model [J]. Journal of Zhejiang Universit-y: Engineering Science,2016,50 (1):144-150)   
[4]Li Congli, Yang Xiushun,Chen Wenbing,et al. Study onthe IQA method for polarization image based on degreeof noise pollution [C]// Proc of International Conference on Information and Automation. 2009:

1468-1472.

[5]Moorthy AK,Bovik A C.A two-Step framework for con-structing blind image quality indices [J].IEEE SignalProcessing Letters,2010,17 (5):   
513-516. [6]Moorthy AK,Bovik A C.Blind image quality assessme-nt: from natural scene statistics to perceptual qual-ity [J].IEEE Trans on Image Processing,   
2011,20(12):3350-3364. [7]Mittal A,Moorthy AK,Bovik AC.No-reference image quality assessment in the spatial domain [J]. IEEE Tra-ns on Image Processing,2012,21 (12):   
4695-4708. [8]邬美银，陈黎，田菁．基于卷积神经网络的视频图像失真检测及分类 [J].计算机应用研究,2016,33(9):2827-2830.(Wu Meiyin,Chen Lin, Tian jing.Video image distortion det-ection and classification based on convolution neuralnetwork [J].Application Research of Computers,2016,   
33 (9): 2827-2830.) [9]Ruderman D L. The statistics of natural images [J].Network Computation in Neural Systems,1994,5 (4):517-548. [10] Hou Weilong，Gao Xinbo,Tao Dacheng，et al.Blind ima-ge quality assessment via deep learning [J]. IEEE Trans Neural Networks & Learning Systems,2017,26(6):1275-1286.   
[11]张刚，马宗民．一种采用Gabor 小波的纹理特征提取方法[J]．中国图 象图形学报,2010,15 (2): 247-254.(Zhang Gang,Ma Zongmin,A texture feature extraction method using G-abor wavelet [J]. Journal of Image and Graphics,2010,15 (2): 247-254.)   
[12]Mass AL,Hannun A Y,Ng A Y.Rectifier nonlinearitiesimprove neural network acoustic models [C]// Proc of International Conference on Machine Learning.2013.   
[13] Nair V,Hinton G E.Rectified linear units improve r-estricted boltzmann machines [C]//Proc of International Conference on International Conference on Machine Learning. Omnipress.2010: 807-814.   
[14]Hinton GE,Srivastava N,KrizhevskyA,et al.Improving neural networks by preventing co-adaptation of feature detectors [J]. Computer Science, 2012,3(4): 212-223.   
[15] Sheikh HR,Sabir MF,Bovik A C.A statistical evaluation of recent full reference image quality assessment algorithms [J].IEEE Trans on Image Processing,2006,15 (11): 3440-3451.