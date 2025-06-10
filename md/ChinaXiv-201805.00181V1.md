# 结构纹理分离的对比度和细节增强

尹超，郭晓金，田肖，何川(重庆邮电大学 通信与信息工程学院，重庆 400065)

摘要：针对光照不足等因素造成获取的图像质量偏低的问题，提出一种基于结构层和纹理层分离的图像增强方法。首先将图像分为结构层和纹理层两部分，对结构层用累积分布函数构造参数自适应的Gamma 校正算法，并用自适应Gamma校正算法对图像的结构层进行对比度和亮度增强，对纹理层采用提升高频分量的方法增强纹理细节，最后把增强后的结构层与纹理层结合得到增强后的图像。仿真对比实验表明，该方法能避免图像增强过程中的纹理细节丢失的问题，亮度和对比度也得到了很好的提升，增强后的图像视觉效果好，具有一定的应用价值。

关键词：结构层；Gamma校正；图像细节增强；对比度 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.07.0682

Contrast and detail enhancement based on structure and texture

Yin Chao, Guo Xiaojin, Tian Xiao, He Chuan (College ofInformation& Communication Enginering,Chongqing Universityof Posts & Telecommunications，Chongqing 400065, China)

Abstract:Targetedateimagelowerqualityduetoinsufficientshine,amethodforimageenhancementbasedontheseparation ofstructure layerandtexture layer is proposed.Firstly,break downthe image tostructure layerandtexture layer.Thenusethe cumulativedistribution function toconstruct the parameter self-adaptive Gamma corectionalgorithmforthe structure layer, andusethesame algorithmto enhance thecontrastratioandlight intensityoftheimagestructurelayerandadoptthe methodof highfrequencycomponenttonhancethe texturedetails inthetexturelayer.Finalycombinetheehaned structurelayernd texture layer andgetthe enhanced image.The simulationcontrast experiment proves thatthe method may avoid the loss of texturedetailsintheproess ofimageenhancementandimprovethe light intensityaswellasthecontrastratiotolargeextent, making the enhance image much beter in visual effect. It is certainly valuable in the application.

Key Words: structure layer; Gamma correction; image detail enhancement; contrast ratio

# 0 引言

图像增强是为了改善图像的视觉效果，有目的地突出图像的整体或局部特性，改善细节信息，提升图像质量和信息量。例如在光照不足的条件下获取的低照度图像，需要通过增强来提高图像的亮度，对于医学、红外这类图像需要增强后更加突出细节信息和局部特征。

常见的图像增强方法主要有直方图均衡[1]、小波变换法[2]、同态滤波和基于Retinex 模型[3-5]等。直方图均衡能有效提高图像的对比度，然而这类方法会导致灰度级的改变从而使图像丢失一些细节纹理特征。Pizer等人提出了自适应的直方图均衡法[6]，该方法根据图像的局部特征来自适应改变参数,对局部特征有较好的处理能力，但会导致图像的全局视觉效果降低。小波变换主要通过对图像的高频部分进行增强处理，增强后的图像容易出现失真，增强效果也有不足[7]。Retinex算法是基于人类视觉系统成像的机理而提出来的一种图像增强方法，基于该理论提出了多种方法，诸如单尺度Retinex算法[8]、多尺度Retinex算法[9]、随机路径的Retinex 算法[10]等。由于Retinex 是根据光照平缓变化所提出的理论，然而在自然环境下获取图像时难免会有光照不均的现象，这类图像通过Retinex理论增强后会在灰度变化较大的地方出现光晕伪影、图像边缘模糊等缺陷[II]。虽然针对这些问题提出了一系列的改进方法[1I-12]，主要是通过改进滤波器等措施，在光照不均或者灰度值变化较大的地方能有效抑制光晕。然而这类方法以保留反射分量作为增强后的图像，照射分量被去除，容易造成图像信息的缺失。

从目前来看，图像增强可能带来的问题主要有这几个方面：

细节缺失、增强后图像的整体或者局部亮度或者对比度不协调。为解决这些的问题，本文提出了一种图像分层模型的增强方案，将输入图像分解为结构层和纹理层两部分，并且通过图像灰度值的概率累积分布函数以及局部最大灰度值构造了一种改进的Gamma校正方案，将结构层通过改进的Gamma校正来提升图像的对比度和亮度，而纹理层则通过提升高频分量的方法使得纹理细节更加突出，最后将结构层与纹理层相结合得到增强后的图像。

# 1 结构层提取

如同Retinex 模型可以将一副图像分为入射分量和照射分量两部分，本文将图像分解为结构层和纹理层两部分，如式（1）所示。

$$
I ( x , y ) = S ( x , y ) K ( x , y )
$$

其中： $I$ 为输入图像， $s$ 和 $K$ 分别为图像的结构层和纹理层。结构层是表现图像主要性质的部分，如图像的灰度值和色彩的分布等；而纹理层主要表现图像的纹理细节，并且在频域内对应的是高频部分。人类或者计算机仅仅依靠图像的结构层就可以理解图像所表达的信息，而丰富的纹理可以使得图像的视觉效果更真实，更能突出图像的细节信息。

$\mathrm { \Delta X u }$ 和Yan等人[13]提出了将一幅图像分为结构层和纹理层两部分的方法，结构层的提取模型如式（2）所示：

$$
\arg \operatorname* { m i n } _ { s } \sum _ { q } ( S ( q ) - I ( q ) ) ^ { 2 } + \lambda ( \frac { D _ { x } ( q ) } { L _ { x } ( q ) + \varepsilon } + \frac { D _ { y } ( q ) } { L _ { y } ( q ) + \varepsilon } )
$$

其中： $S ( q )$ 是需要求取的结构层部分的像素值， $I ( q )$ 为源图像的像素值， $\boldsymbol { q }$ 表示图像的像素点索引， $( S ( q ) - I ( q ) ) ^ { 2 }$ 是输出的结构层和输入源图像的像素值大小的差异，后一项$\frac { D _ { x } ( q ) } { L _ { x } ( q ) + \varepsilon } + \frac { D _ { y } ( q ) } { L _ { y } ( q ) + \varepsilon }$ 表示像素点 $q$ 的相对总变分项， $\lambda$ 为结构层的平滑权重参数，当这个值越大时，图像的结构层部分会越模糊。因此，要获取图像的结构层即最小化式（2）所示的目标函数。

其中：

$$
D _ { x } ( q ) = \sum _ { q \in R ( p ) } g _ { p , q } \left| ( \partial _ { x } S ) _ { q } \right|
$$

该式的意义为像素点 $q$ 在 $x$ 方向上在 $R ( p )$ 窗口范围内的绝对总变化， $R ( p )$ 是以像素点 $p$ 为中心的矩形窗口范围， $p$ 表示 $R ( p )$ 窗口范围内的像素索引， $\partial _ { x } S$ 表示 $S ( q )$ 在 $x$ 方向上的偏导数， $g _ { p . q }$ 是中心像素 $q$ 与像素 $p$ 之间的空间相似度，它与式（4）所示的高斯项成正相关。

$$
g _ { p , q } \propto \exp ( - \frac { ( x _ { p } - x _ { q } ) ^ { 2 } + ( y _ { p } - y _ { q } ) ^ { 2 } } { 2 \sigma ^ { 2 } } )
$$

$\sigma$ 为空间相似度尺度参数,它能够控制纹理层尺度大小,增大 $\sigma$ 的值会使纹理层模糊。

$L _ { x } ( q )$ 是在 $R ( p )$ 窗口内的 $x$ 方向上的总变化,定义为

$$
L _ { x } ( q ) = \left| \sum _ { q \in R ( p ) } g _ { p , q } ( \hat { o } _ { x } S ) _ { q } \right|
$$

此外，式（2）中的参数 $\varepsilon$ 也是一个小正数，它的目的是为了防止 $L _ { x } ( q )$ 为0时出现分母为0的情况。对于 $D _ { \mathrm { { y } } } ( q )$ 和 $L _ { y } ( q )$ ，与 $x$ 方向上的形式一样，将（3）、（5）两式的 $x$ 替换为 $y$ 即可得到。

通过上述图像结构层提取模型，可获得图像的结构层部分，如图1所示，其中，结构层提取参数均为文献[13]所建议的参数。

![](images/c194e48dba1ac9133b53a7bacd171e525ac115a4f331c6c90248368d6502b51b.jpg)  
图1图像的结构层和纹理层

# 2 改进的Gamma 校正

Gamma校正是一种常用的亮度和对比度增强方法，在实际成像过程中，由于成像设备的固有缺陷或者不利的外界环境条件，可能会导致获得的图像的亮度和对比度偏低，这不仅降低了图像本身的视觉质量效果，而且会影响图像的进一步应用，因此需要对图像进行增强处理以便于后期的应用。本文通对图像的结构层进行Gamma校正，提高整体对比度和视觉效果。

经典Gamma校正的基本形式表示如下：

$$
T ( l ) = l _ { \mathrm { m a x } } ( \frac { l } { l _ { \mathrm { m a x } } } ) ^ { \gamma }
$$

其中：／是Gamma 校正参数，当该值大于1时，图像增强后会更加灰暗，亮度效果会变差，而该值小于1时，图像的亮度增大，一般的Gamma 校正用于图像增强中都是讨论／小于1的情况。l和 $l _ { \mathrm { m a x } }$ 分别是当前像素的灰度值和图像中的最大的灰度值， $T ( l )$ 为校正后的像素值。经典的Gamma 校正算法在全局范围内通过固定的参数重新分配图像的灰度值，这会导致图像中部分信息的丢失，并且对于每幅图像其适合的校正参数是不同的，即参数的选择要根据图像的自身性质而改变，人工设定的参数很难满足这种情况，针对这一问题，文献[14]中提出了一种根据概率累积分布函数构造的／校正参数：

$$
\gamma ( l ) = 1 - c ( l )
$$

其中： $c ( l )$ 表示输入图像灰度值的概率累积分布函数，通过概率累积分布构造的Gamma校正参数避免了人工设定固定参数带来的缺陷。但从式（6）来看，该方法采用了全局图像中的最大灰度值，这会导致图像增强后灰度值整体偏大，对比度偏低，图像的局部特征被过度平滑而造成局部信息的丢失等。考虑到这些问题，本文对某个像素点的校正采用局部最大灰度值来替代全局最大值，将参数替换为累积分布函数构造的参数后如式

（8）所示。

$$
T ( l ) = \operatorname* { m a x } ( w _ { l } ) ( \frac { l } { \operatorname* { m a x } ( w _ { l } ) } ) ^ { \gamma ( l ) }
$$

其中： $w _ { l }$ 表示以像素点 $l$ 为中心的矩形邻域范围， $\mathrm { m a x } ( w _ { l } )$ 即为这个矩形邻域内的灰度最大值，文中将在4.1小节中讨论这个矩形邻域窗口的大小对增强效果的影响。

# 2.1参数的构建

本节讨论通过概率密度函数构造改进的Gamma校正参数，对于图像中灰度值为 $l$ 的像素点，其概率密度函数可表示为

$$
P ( l ) = \frac { n _ { l } } { M N }
$$

其中： $n _ { \scriptscriptstyle { l } }$ 表示像素值为 $l$ 的像素点的个数，MN为图像中的像素点总数，根据概率分布函数，可以得到累积分布函数：

$$
C ( l ) = \sum _ { i = 0 } ^ { l } P ( i )
$$

因此，Gamma校正参数可表示为

$$
\gamma ( l ) = 1 - C ( l )
$$

对于图1中的Lena图像，通过概率累积分布函数获得的参数曲线如图2所示。

![](images/44b893f024acc58b825eaa2382e059e2614b68eb1388a1f9047826beb31ac037.jpg)  
图2自适应参数曲线

从图2曲线可发现，该方法构造的参数能够覆盖从0到1的范围，然而在灰度值较低的范围校正参数接近于1，对暗区增强效果不明显，灰度值大的区域又被过度增强。因此提出一种截断型的参数，即对参数设置上下限，设置上下限后参数可表示为

$$
\gamma _ { \boldsymbol { u } } ( { \boldsymbol { l } } ) = \left\{ { \begin{array} { l l } { k } & { \gamma ( { \boldsymbol { l } } ) < k } \\ { \gamma ( { \boldsymbol { l } } ) } & { { \ddag \mathrm { ! } \mathrm { ! } \mathrm { ! } \mathrm { ! } \mathrm { ! } \mathrm { ! } \mathrm { ! } } } \\ { c } & { \gamma ( { \boldsymbol { l } } ) \geq c } \end{array} } \right.
$$

其中： $\boldsymbol { \mathscr { c } }$ 表示要设置的上限，通过设置参数上限，能够对暗区也拥有良好的增强能力， $\mid c \mid$ 值越小则图像的亮度增强效果越明显，但太小会导致亮度过度增强的问题， $k$ 为要设置的下限，根据经典的Gamma校正的经验，文中将该上限值 $\vert c \vert$ 设为0.6,下限值 $k$ 设为0.1。将该式代入式（8）即得到改进的Gamma校正算法。

# 3 纹理层细节增强

纹理层包含了大量的纹理细节信息，细节增强的目的在于将纹理细节更大程度地体现出来，纹理细节表征图像的高频部分，若输入图像和输出图像分别为 $K$ 和 $f$ ，则可建立如下细节增强模型。

$$
f ( x , y ) = m + C ( K ( x , y ) - m )
$$

其中： $m$ 和 $c$ 分别是图像的低频部分以及增强系数，该模型是首先需要得到图像的低频部分， $K ( x , y ) - m$ 表示原图减去低频而得到的高频部分，将高频部分乘以一个增强系数再加上低频部分则得到增强后的图像，从该式来看，当系数 $c$ 为大于1的值时，高频部分得到提升，从而增强图像的高频纹理细节，反之若 $c$ 为小于1的值，则高频纹理细节部分被削弱。

图像的低频部分可以通过将图像进行平滑处理来获得，可表示为

$$
m ( x , y ) = \frac { 1 } { \left| w \right| } \sum _ { w } K ( i , j )
$$

$\left| w \right|$ 为平滑窗口 $w$ 内的像素点的总个数,由此可以得到局部方差为

$$
\sigma ^ { 2 } ( x , y ) = \frac { 1 } { \left| w \right| } \sum _ { w } ( K ( i , j ) - m ( i , j ) ) ^ { 2 }
$$

局部方差的值越大，则说明该点的高频成分越多，而局部 方差越小说明高频成分越少，将式（13）改写如下：

$$
f ( x , y ) = m ( x , y ) + ( 1 + \frac { \sigma ( x , y ) } { D } ) [ K ( x , y ) - m ( x , y ) ]
$$

$$
D = \sqrt { \frac { 1 } { M N } { \sum _ { x = 0 } ^ { M } } { \sum _ { y = 0 } ^ { N } } ( K ( x , y ) - \overline { { K } } ( x , y ) ) ^ { 2 } }
$$

$D$ 表示图像的全局均方差， $\overline { { K } }$ 为图像的灰度平均值。对于一幅图中 $D$ 为一个常量，局部方差值越大的高频部分，其增强系数越大，因而高频细节得到增强。

下图展示了不同大小的平滑窗口的细节增强对比。

![](images/bf91740cc06f221824e2591dbc4de8147e194ce8855d9eed601720e68f97f90f.jpg)  
图3不同平滑窗口下的细节增强对比

# 4 仿真实验

本文通过 MATLAB r2012b 在 IntelXeon E5 2.1GHzCPU,16GB内存的PC机上进行仿真实验，并分别讨论了Gamma校正窗口大小选择的问题，以及对所提出的方法进行比较实验。

# 4.1Gamma校正窗口的大小的选取

若中心像素点的邻域范围窗口选择过小，则窗口内的最大像素值与中心点像素值差异小，亮度增强效果较差，本文分别从窗口大小为3、5、15、25、35、45、55来对多幅图像进行测试比较，限于篇幅，这里仅展示了其中一幅图像的对比结果，如图4所示，从图可见，当窗口选择越大时，亮度增强效果越明显，但图像的局部细节会逐渐缺失。通过对比实验，当改进的Gamma校正的窗口大小为35时，增强后对多幅图像的亮度和对比度在视觉感受上能够取得较好的效果，因此在本文的实验中对改进的Gamma 校正的窗口大小均设为35。

![](images/db24152cc5d72a18d5f2e915bf685c905bc33aa3e89d8fed0f060cbe89694fec.jpg)  
图4不同窗口大小增强对比

# 4.2本文方法的对比实验

通过改进的Gamma校正后的图像能够保持较好的亮度和对比度，但由于重新分配图像灰度值后可能改变图像的纹理细节信息，使得增强后图像的纹理不清晰，细节缺失，因此通过结构层和纹理层提取的形式增强图像的纹理细节和对比度，算法步骤如下：

a)通过结构层提取算法将图像分为“结构层 $+$ 纹理层”两部分；b)对图像的结构层通过改进的Gamma校正进行亮度和对

比度的增强;

c)将图像的纹理层通过式(16)所述的方式进行细节增强。实验发现，将平滑窗口大小设为20，可以得到明显的细节增强效果；

d)将两分量结合得到增强后的图像，如图5所示。

为验证本文方法的有效性，将本文方法别与文献[15]提出的基于最大熵的直方图均衡算法、文献[16]的基于视觉模糊集的增强方法，以及文中改进的Gamma算法做比较实验，如图6所示。

![](images/043ae157128eb6ae32622c80df21ad7271ed755205ff9cad44f15d790257649b.jpg)  
图5本文方法流程

![](images/0f775b0d0591db246aebd1431e184dc73e82615463ece3d1765fe0074eabdb22.jpg)  
图6增强对比

从图6对比来看，基于最大熵的直方图均衡算法对暗区的增强效果不明显，而亮区增强后亮度偏大，特别是对于图a，增强后的亮区亮度过大。文献[16]的方法拥有较好的全局增强能力，但增强后图像的亮度仍然偏低，动态范围不理想，改进的Gamma增强后亮度得到了提升，但视觉效果仍有不足，结合结构层提取后，能在亮度、对比度和纹理细节等方面有较好的表现。

为了从客观角度评价图像质量，本文从PSNR和图像熵(H)两方面进行对比，图像的熵表明灰度分布的聚集特性，能够反映图像的细节信息[17]，熵值越大，表明图像的细节越丰富。

由上表客观数据的对比可以发现，PSNR 参数中，文献[15]的方法在图a、b上都高于本文方法，其他情况下本文方法该参数都比较好，整体看PSNR相对来说都比较稳定，没有出现特别大的偏差。而在图像熵方面，本文方法明显优于所对比的其他算法，说明在细节保持上本文方法拥有较好的优势。对于文献[15]所述的方法是通过最大化熵值作为约束条件来进行直方图均衡，虽然图像熵的改善也非常明显，对细节的保留能力好，但是忽略了亮度和对比度的保持能力。综合主客观对比来看，本文方法对图像的增强效果还是有非常明显的改善。

表1客观指标对比  

<html><body><table><tr><td colspan="2"></td><td colspan="2">图a</td><td colspan="2">图b</td><td colspan="2">图c 图d</td></tr><tr><td>指标</td><td>PSNR</td><td>H</td><td>PSNR</td><td>H PSNR</td><td>H</td><td>PSNR</td><td>H</td></tr><tr><td>原图</td><td></td><td></td><td>24.0092 6.0024 24.0156 6.6960 24.0654 6.9678 24.1513 7.2968</td><td></td><td></td><td></td><td></td></tr><tr><td>文献[15]方法 24.0832 7.4389 24.1814 7.5814 24.2674 7.6658 24.1720 7.3855</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>文献[16]方法 24.0675 7.3291 24.0831 7.3909 24.1536 7.5684 24.0796 7.3284</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>改进的 Gamma 24.0669 7.3747 24.0855 7.4578 24.2587 7.6306 24.0655 7.3215</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>本文方法</td><td></td><td></td><td>24.0813 7.4561 24.0958 7.6212 24.2730 7.7998 24.1788 7.4676</td><td></td><td></td><td></td><td></td></tr></table></body></html>

最后分析时间复杂度来考察算法的时效性，该增强算法主要分为三部分，对于结构层提取算法的复杂度，在文献[13]中已经做了详细的讨论，若一幅共含有 $n$ 个像素点的图像，其时间复杂度为 $O ( n )$ 。得到结构层和纹理层后，首先计算自适应Gamma校正参数，从式（9）、（10）、（11）来看，式（9）首先要统计图像中的每个灰度值的个数的时间复杂度为 $O ( n )$ ，然后计算每个灰度值占总的像素点的比例，这一步骤的复杂度为一个常数 $k$ ，式（10）的时间复杂度是由灰度级决定的，也是一个常数 $\boldsymbol { c }$ ，式（11）的复杂度为同样为一个常数i，因此通过这三个式子求参数的复杂度为 $O ( n ) + k + c + i$ ，根据算法复杂度表示规则，不考虑系数和常数，因而求参数时间的复杂度为$O ( n )$ 。通过相同的分析方法进行讨论，最终可得到该算法总的时间复杂度为 $O ( n )$ 。从这里的分析可以看出，自适应Gamma校正增强和本文方法的复杂度均为 $O ( n )$ ，但事实上，本文方法要比自适应Gamma校正所花费的时间多好几倍，这是由于计算机科学中时间复杂度的表示形式所导致的，没有考虑系数。为了更具体的表明时间开销，表2展示了上述4种不同算法增强图像时的时间开销。其中，为保持一致性，在计算时间开销之前将图6中的原始图像的分辨率大小均转换为 $4 5 0 ^ { * } 6 0 0$ 。由于增强所花费的时间与计算机运行的程序数量以及剩余内存大小有直接的关系，因此这些数据是在计算机重启后，未运行其他应用软件的情况下测得。

表2时间开销对比  

<html><body><table><tr><td rowspan="2"></td><td colspan="3">时间开销/s</td></tr><tr><td>图6(a)</td><td>图6(b)</td><td>图6(c) 图6(d)</td></tr><tr><td>文献[15]方法</td><td>5.8482</td><td>5.7518</td><td>5.0216 5.9319</td></tr><tr><td>文献[16]方法</td><td>0.5538</td><td>0.5586</td><td>0.5892 0.5783</td></tr><tr><td>改进的 Gamma</td><td>0.6651</td><td>0.6542</td><td>0.6607 0.6671</td></tr><tr><td>本文方法</td><td>2.2628</td><td>2.2495</td><td>2.2632 2.2658</td></tr></table></body></html>

可以看出，对于每一行数据，由于图像分辨率大小是相同的，所以同一种增强算法对不同的图像进行增强时所花费的时间是差不多的。文献[15]方法需要将最大熵条件下的的直方图均衡模型转换为图论中的最短路径问题来进行计算，而当节点数特别多时计算各个点之间的最短路径的算法是比较复杂的，如通过Dijkstra计算最短路径的时间复杂度为 $O ( n ^ { 2 } )$ ，从表2也可以看出，其执行时间最长，根据图论中的最短路径算法可知，当图像的分辨率变大时，时间复杂度会更快地增大。文献[16]的视觉模糊集方法是花费时间最少的一种方法，因为该方法主要是将图像通过隶属度函数映射到模糊域，再经过类似经典Gamma变换的方式进行模糊增强后变换回灰度域，算法较简单。文中所提的改进Gamma校正所花费的时间也相对较低。本文方法由于步骤较多，并且每个步骤都有 $O ( n )$ 的时间复杂度，因此所花费的时间是文献[16]的方法和改进Gamma校正的几倍，但是仍然比文献[15]的方法低很多。可见，本文方法是通过牺牲算法的时间复杂度来换取增强效果，因此可以用于实时性要求不高，但对图像的质量特别是纹理细节要求较高的场合。

# 5 结束语

在图像增强中，既要使得图像的对比度和亮度拥有良好的视觉效果，也要突出图像的纹理细节，使图像在视觉上更真实。由于传统Gamma 校正在全局范围内增强后对比度偏低，以及导致部分纹理细节信息的缺失的问题，本文对Gamma算法进行了改进，通过结构层提取算法将图像分为“结构层 $+$ 纹理层”两部分，对结构层进行改进的Gamma 校正来提高图像的亮度和对比度，并对纹理层进行细节增强。实验表明，该方法能避免纹理细节被平滑，增强后的图像能拥有较好的局部特征和动态范围，具有一定的应用价值。

# 参考文献：

[1]Garg R,Mittal B,Garg S.Histogram equalization techniques for image enhancement [J]. International Journal of Electronics & Communication Technology,2011,2 (1):107-11. Garg R,Mital B,Garg S. Histogram equalization techniques for image enhancement [J]. International Journal of Electronics & Communication Technology,2011,2(1):107-111.   
[2]Iqbal M Z,Ghafoor A，Siddiqui A M. Satelite Image Resolution Enhancement Using Dual-Tree Complex Wavelet Transform and Nonlocal Means [J].IEEE Geoscience& Remote Sensing Letters,2013,10 (3): 451- 455.Iqbal M Z,Ghafoor A,Siddiqui A M. Satellite Image Resolution Enhancement Using Dual-Tree Complex Wavelet Transform and Nonlocal Means [J]. IEEE Geoscience & Remote Sensing Letters,2013,10(3): 451- 455.   
[3] Lee E,Kim S,Kang W,et al. Contrast Enhancement Using Dominant Brightness Level Analysis and Adaptive Intensity Transformation for Remote Sensing Images [J]. IEEE Geoscience & Remote Sensing Leters, 2013,10 (1):62-66.Lee E,Kim S,Kang W,et al. Contrast Enhancement Using Dominant Brightness Level Analysis and Adaptive Intensity Transformation for Remote Sensing Images [J]. IEEE Geoscience & Remote Sensing Letters,2013,10 (1): 62-66.   
[4]Land EH,Mccann JJ.Lightness and Retinex Theory [J]. Journal of the Optical Society of America,1971,61(1):1-11.Land E H, Mccann J J. Lightnessand Retinex Theory[J]. Journal ofthe Optical Society of America, 1971,61 (1): 1-11.   
[5]Land EH.The Retinex theory of color vision [J].Scientific American,1977, 237 (6):108.Land E H.The Retinex theory of color vision [J].Scientific American,1977,237 (6):108.   
[6]Pizer S M,Amburn E P,Austin JD,et al.Adaptive histogram equalization and its variations [J].Computer Vision Graphics & Image Processing,1987, 39 (3):355-368.Pizer S M,Amburn E P,Austin JD,et al.Adaptive histogram equalization and its variations [J].Computer Vision Graphics & Image Processing,1987,39 (3): 355-368.   
[7] 李福文，金伟其，陈伟力，等．基于 Retinex 模型的彩色图像全局增强

算法[J].北京理工大学学报，2010,30(8):947-951．李福文，金伟其，陈伟力，等．基于Retinex模型的彩色图像全局增强算法[J].北京理工大学学报,2010,30(8):947-951.

[8]Yao K, Tian D.Shadow Removal from Images Using an Improved SingleScaleRetinex ColorRestoration Algorithm[C]//Proc of International Joint Conference on Computational Sciences and Optimization. Washington DC: IEEE Computer Society,2009:934-938.Yao K,TianD.Shadow Removal from Images Using an Improved Single-Scale Retinex Color Restoration Algorithm[C]//Proc of International Joint Conference on Computational Sciences and Optimization.Washington DC:IEEE Computer Society,2009: 934-938.

[9]WangW,LiB,ZhengJ,etal.A fast Multi-Scale Retinex algorithm for color image enhancement $[ \mathrm { C } ] / \AA$ Proc of International Conference on Wavelet Analysis and Pattern Recognition.20o8:80-85.Wang W,LiB,Zheng J,et al.A fast Multi-Scale Retinex algorithm for color image enhancement [C]// Procof International Conference on Wavelet Analysis and Pattern Recognition.2008: 80-85.

[10] Gianini G,Rizzi A,Damiani E.A Retinex model based on Absorbing Markov Chains[J].Information Sciences,2016,327(C):149-174.Gianini G,Rizzi A,Damiani E.ARetinex model based on Absorbing Markov Chains [J].Information Sciences,2016,327(C):149-174.

[11]张雪峰，赵莉．基于改进Retinex的图像增强算法[J].南京理工大学学报（自然科学版),2016,40(1):24-28．张雪峰，赵莉．基于改进Retinex的图像增强算法[J].南京理工大学学报（自然科学版)，2016,40(1):24-28.

[12]王小明，黄昶，李全彬，等.改进的多尺度Retinex 图像增强算法[J].计算机应用,2010,30(8):2091-2093．王小明，黄昶，李全彬，等．改进的多尺度Retinex 图像增强算法[J].计算机应用，2010,30(8):2091-2093.

[13]XuL,Yan Q,Xia Y,etal. Structure extraction from texture via relative total variation [J].ACM Trans on Graphics,2012,31(6):139.XuL,Yan Q,Xia Y,et al. Structure extraction from texture via relative total variation [J]. ACM Trans on Graphics,2012,31 (6):139.

[14] Huang L,Cao G,Yu L.Efficient contrast enhancement with truncated adaptive Gamma correction [C]// Proc of International Congress on Image and Signal Processing,Biomedical Engineering and Informatics.2016:189- 194.Huang L,Cao G,Yu L.Efficient contrast enhancement with truncated adaptive Gamma correction [C]// Proc of International Congress on Image and Signal Processing,Biomedical Engineering and Informatics.2016:189- 194.

[15] Niu Y,Wu X,Shi G.Image enhancement by entropy maximization and quantization resolution upconversion [C]// Proc of IEEE International Conference on Image Processing.2014: 4047-4051.Niu Y,Wu X, Shi G. Image enhancement by entropy maximization and quantization resolution upconversion [C]// Proc of IEEE International Conference on Image Processing.2014: 4047-4051.

[16] Deng H, Sun X,Liu M,et al. Image enhancement based on intuitionistic fuzzy sets theory [J].IET Image Processing,2016,10(10): 701-709.Deng H, Sun X,Liu M,etal.Image enhancement based on intuitionistic fuzzy sets theory[J].IET Image Processing,2016,10(10): 701-709.

[17]肖进胜，单姗姗，段鹏飞，等．基于不同色彩空间融合的快速图像增强算法[J]．自动化学报,2014,40(4):697-705．肖进胜，单姗姗，段鹏飞，等．基于不同色彩空间融合的快速图像增强算法[J]．自动化学报，2014,40(4): 697-705.