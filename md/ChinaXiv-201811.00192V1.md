# 基于复合特征和动态阈值圆法的手势识别算法研究

王梅，张震，张曦，屠大维(上海大学 机电工程与自动化学院，上海 200072)

摘要：针对传统手势识别中用肤色分割手部区域效果的局限性，采用Kinect获取深度信息来分割手掌，能得到较好效果。对手掌轮廓进行多边形逼近，将凸包点作为候选指尖点。利用非零像素（白）到最近零像素的距离提取掌心，用线性回归动态调整阈值圆半径，将无用凸包点过滤，实现指尖点准确提取。在分类识别中，将图像的Hu矩和指尖点个数组合起来，作为复合手势特征，导入KNN分类器中，实现手势识别。实验证明，基于复合特征和动态阈值圆法的手势识别算法具有较好的识别率和实时性。

关键词：手势识别；几何不变矩；动态阈值圆；KNN 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.04.0491

# Gesturerecognitionthat based on combined features and dynamic threshold circle

WangMei, Zhang Zhen, Zhang Xi,Tu Dawei (College ofMechatronics Engineering&Automation,Shanghai University,Shanghai 20oo72,China)

Abstract:Forthe limitationofhandregion segmention with skincolorinthetraditional gesturerecognition,usingKinectto obtainingdepth information to segmente palmcan getbeterresults.The palm contouris polygonalapproximation,and the convex pointsareselected asthecandidate fingertip.The fingertips are distinguished accuratelyfrom theunwanted convex points byathresholdcircle.Utilizing thedistancerelationof thenon zeropixel(white)tothenearest zeropixeltoextractthe palmcenter,thethresholdcircletransformradius dynamicallybylinearregressonmethod.Intheclasificationandrecognition, combining the Hu moment and the number offingertipasthe feature of gesture,and the KNNclassifier achieve gesture recognition.Experiments showthatthegesturerecognitionalgorithmbasedoncomposite featuresanddynamic thresholdcircle method has better recognition rate and real-time performance.

Key Words: gesture recognition; geometric invariant moment; dynamic threshold circle; KNN

# 0 引言

作为新一代人机交互的重要手段，手势识别成为近年来的研究热点，在虚拟现实、远程控制和交通等领域得到广泛应用。早期研究集中于专用设备的研制，如数据手套可以提供手部各关节数据[1]，用于精确手势识别，但设备昂贵、过程繁琐制约了其应用；其后，通过在手部做标记的标记手势研究[2]发展起来，但受限于标志点位置和数量等因素，识别手势种类有限，局限性较大。因而，基于视觉的手势识别方法[3]应运而生。

基于视觉的手势识别系统主要分为基于RGB图像和基于深度图像两类。传统的RGB图像的手势分割在HSV(或YCrCb）颜色空间下，通过肤色与背景的明显差异，将手部分离出来[4]。该方法对光线、场景等要求较高，且当人体其他部位（如脸)出现时，会造成较大干扰，效果较差。在此基础上，研究者又提出了利用灰度直方图[5来进行手掌检测，灰度直方图依赖于图像灰度的阶跃变化，能够较好的分割手势，但是该过程计算较为复杂，需要花费较多时间时间。与RGB图像相比，深度图像具有物体三维特征信息，即深度信息。由于深度图像不受光源照射方向及物体表面的发射特性的影响，而且不存在阴影，不受颜色相近信号影响，所以可以更准确迅速地识别手势[6]。

基于视觉的手势识别需要经过分割、表示、识别等三个阶段[7。手势分割阶段主要是将手掌从环境中分割出，在该环节中主要解决背景对手势分割的影响。手势表示则通过一定的特征来表征人手模型，较常用的是以指尖特征和掌心特征为重要环节的轮廓特征[8]。文献[9]中将手掌分区并对不同区域设置权值来确定掌心，减少手指部分对掌心位置的影响；此方法虽可获取较好的掌心位置，但是对区域划分要求较高；文中采用基于轮廓曲率的指尖点识别方法。高晨等人[10]采用计算手掌轮廓最大内切圆的方向确定掌心位置，对于特定手势适用性有限。手势识别以特征为依据，判别人体手势含义，常用的方法有基于模板匹配法与分类算法[11-13]。

本文提出一种基于复合特征和动态阈值圆法的手势识别算法，将分别从手势分割、手势特征提取、手势分类识别等方面加以介绍。

# 1 手势分割

本文利用Kinect的彩色相机和深度传感器，获取人体信息（图1)，以完成手势识别。

![](images/3cb34df250808f6878be2d75c6ded97c9d9b394512a86c35825e20a111323a9c.jpg)  
图1Kinect相机及其获取的彩色图像与深度图像  
Fig.1Kinect camera and its acquired and depth image

利用Kinect 和OpenNI的手掌跟踪算法获取手掌心的三维坐标 $( \mathbf { \boldsymbol { x } } _ { \mathrm { H } } , \mathbf { \boldsymbol { y } } _ { \mathrm { H } } , \mathbf { \boldsymbol { z } } _ { \mathrm { H } } )$ 。利用场景中其他杂体和手掌与传感器的距离（深度）差异，以深度信息 $\mathbf { Z } _ { \mathrm { H } }$ 为标准，合理设置阈值a，可以将手掌从场景中分割出来。

由于原始的深度图像包含过多的前景和背景信息，需要对其设置感兴趣区域（Region OfInterest，ROI)，即手掌所在区域，以减少过多无关信息，提高程序运行速度。根据手掌心坐标中的 $x _ { H } , ~ y _ { H }$ ，设置感兴趣区域矩形范围： $x \in$ $[ \ { x } _ { { H } } - o f f s e t , { x } _ { { H } } - o f f s e t \ ]$ 、 $y \in [ \ { y } _ { H } - o f f s e t , { y } _ { H } - o f f s e t \ ] \mathrm { ~ } _ { \mathsf { d } }$ ，根据实际手掌大小和Kinect 的检测范围设置offse $\scriptstyle : = 1 5 0$ 。

在对手掌进行分割同时进行二值化处理，二值化的的操作同样是减少无关信息，提高图像处理速度。在本文的手掌分割中，以手掌的深度为阈值标准，手掌部分像素值设置为255（深度介于 $\left[ z _ { { \scriptscriptstyle H } } - a , z _ { { \scriptscriptstyle H } } + a \right]$ 之间)，将手掌以外的背景信息的像素值设置为0（黑）。

$$
\begin{array} { r } { H \left( x , y \right) = \left\{ ^ { 2 5 5 , ~ D \left( x , y \right) \in \left[ z _ { H } - a , z _ { H } + a \right] } _ { 0 , D \left( x , y \right) = e l s e } \right. } \end{array}
$$

$$
y \in \mathrm { ~ [ ~ } y _ { H } - o f f s e t , y _ { H } - o f f s e t \mathrm { ~ ] ~ }
$$

公式(1)中的阈值 $\mathbf { \Delta } _ { a }$ 取 $1 5 \mathrm { m m }$ ， $D ( x , y )$ 为坐标为图像坐标为

$( x , y )$ 处点的深度值， $H ( x , y )$ 为坐标为 $( x , y )$ 的点在分割并二值化后的图像中的灰度值，图像的大小为ROI所限定的范围。

经过上述操作获得如图2所示的清晰完整的手掌图像。

![](images/66ec2e35c2cc35b480ce8b97094cdc09960208dcfb3428a2cd75ae41badfede0.jpg)  
图2不同手势的深度分割图  
Fig.2Depth split diagram of different gestures

进而，采用中值滤波算法对分割出的手部图像进行滑动滤波，迭代过程中，当前窗口内的所有像素排序，保留中间值作为当前像素值。中值滤波的输出为

$$
g ( x , y ) = m e d \left\{ f \left( x - k , y - l \right) \right\}
$$

其中： $f ( x , y ) , g ( x , y )$ 分别为原始图像和处理后的图像。

中值滤波方法具有较好地抑制噪声效果。经过滤波后的图像再进行二值化，得到的图形较稳定，可以提高后续图像处理的速度。

# 2 手势特征提取

在手掌分割的基础上，通过对手势特征的分类，完成手势识别。在众多手势特征中，本文选择图像几何不变矩的四个特征和指尖点特征，共同组成复合的手势特征，作为手势识别的依据，以避免单特征误差造成的识别结果波动。

# 2.1几何不变矩特征提取

图像的几何矩是1962年由 $\mathrm { H u }$ 提出的[14]，选择出来的7个几何矩不变量经过图像旋转、平移、缩放等操作后，保持不变性。因此在图像处理中，该属性通常作为重要特征用于分类等操作。本文选择其中的4个几何矩不变量，利用其不变性，作为手势特征的一个组成部分，用于手势识别。

对于图像 $f ( x , y )$ ，其 $( p + q )$ 阶普通矩的公式为：

$$
 { \mathbf { m } } _ { \mathrm { p q } } = \iint  { \mathbf { x } } ^ { \mathrm { p } }  { \mathbf { y } } ^ { \mathrm { q } } \mathrm { f } \left(  { \mathbf { x } } ,  { \mathbf { y } } \right) \mathrm { d }  { \mathbf { x } } \mathrm { d }  { \mathbf { y } } \mathrm { \nabla } \left(  { \mathbf { p } } = 0 , 1 , 2 . . . ;  { \mathrm { q } } = 0 , 1 , 2 . . . \right)
$$

0阶矩 ${ \bf { m } } _ { 0 0 }$ 表示目标的“质量”，1阶矩（ $\mathbf { m } _ { 1 0 } , \mathbf { m } _ { 0 1 }$ ）表示目标质心，二阶矩（ $\mathbf { m } _ { 2 0 } , \mathbf { m } _ { 0 2 } , \mathbf { m } _ { 1 1 } )$ 表示旋转半径，三阶矩（ $\mathbf { m } _ { 3 0 }$ ，$\mathbf { m } _ { 0 3 } , \mathbf { m } _ { 1 2 } , \mathbf { m } _ { 2 1 }$ ）描述目标的方位和斜度。

当图像连续时，利用质心 $\mathbf { m } _ { 0 1 } , \mathbf { m } _ { 1 0 }$ 可得到中心矩：

$$
\mu = \iint x ^ { p } - \frac { m _ { 1 0 } } { m _ { 0 0 } } \Biggl ( y ^ { q } - \frac { m _ { 0 1 } } { m _ { 0 0 } } \Biggr ) f \left( x , y \right) \mathrm { d } x \mathrm { d } y
$$

$$
p = 0 , 1 , 2 , \cdots ; q = 0 , 1 , 2 , \cdots
$$

为了消除尺度变化对其影响，通常将各阶中心矩通过零阶中心矩进行归一化，得到：

$$
\displaystyle \boldsymbol { \eta } = \frac { \boldsymbol { \mu } _ { p q } } { \boldsymbol { \mu } _ { 0 0 } ^ { r } }
$$

其中 $r = { \frac { p + q } { 2 } } + 1$ 。

根据Hu矩理论，得到7个不变矩特征量。由于高阶矩计算繁琐，对噪声更敏感[15]，本文取前四个作为分类特征：

$$
\left\{ \begin{array} { c } { I _ { 1 } = \eta _ { 2 0 } + \eta _ { 0 2 } } \\ { I _ { 2 } = \left( \eta _ { 2 0 } - \eta _ { 0 2 } \right) ^ { 2 } + 4 { \eta _ { 1 1 } } ^ { 2 } } \\ { I _ { 3 } = \left( \eta _ { 3 0 } - \eta _ { 1 2 } \right) ^ { 2 } + ( 3 \eta _ { 2 1 } - \eta _ { 0 3 } ) ^ { 2 } } \\ { I _ { 4 } = \left( \eta _ { 3 0 } + \eta _ { 1 2 } \right) ^ { 2 } + ( 3 \eta _ { 2 1 } + \eta _ { 0 3 } ) ^ { 2 } } \end{array} \right.
$$

由于图像的几何不变矩之间的数量级相差较大，并且可能出现负数，为了方便后续操作，采用不变矩的自然对数对数据范围进行压缩。令

$$
 I _ { i } ^ { ' } = \ln ( ~ | ~ I _ { i } ^ { | } ~ )
$$

![](images/187c8006feb257b7380056192ac3c80d3453cea591a1cd53e3f11c97724f5beb.jpg)  
图3不同手势的几何不变矩特征提取

gestures

根据图3的手势提取几何不变矩特征，得到表1。

表1不同手势的几何不变矩特征提取  
Table 1Feature extraction of geometric invariant moment for different gestures   

<html><body><table><tr><td>手势编号</td><td>1</td><td>1</td><td>1</td><td>14</td></tr><tr><td>1</td><td>-6.80197</td><td>-14.2192</td><td>-21.7712</td><td>-22.1432</td></tr><tr><td>2</td><td>-6.47943</td><td>-14.067</td><td>-20.6139</td><td>-20.8318</td></tr><tr><td>3</td><td>-6.91585</td><td>-16.3909</td><td>-26.6766</td><td>-23.5799</td></tr><tr><td>4</td><td>-6.98353</td><td>-16.9139</td><td>-25.7383</td><td>-24.1375</td></tr></table></body></html>

从表中可以看出，手势1和2、手势3和4的几何不变矩特征分别相近，手势的方向及大小不会影响该特征。

# 2.2指尖点检测

手势通常通过手指变换来表现的，通过指尖的几何关系，可以反映当前手势。在手势识别中，指尖信息是十分重要的。因而，本文选择指尖点信息，作为手势特征的另一个组成部分，与几何不变矩的前四个特征量一起，用于手势识别。

在指尖点检测过程中，首先基于Douglas-Peucker算法进行手轮廓多边形提取，然后基于凸包算法计算候选指尖点，最后通过阈值圆分类法完成指尖点检测。其中，阈值动态调整算法

可以保证指尖提取的可靠性。

# 2.2.1手的轮廓多边形提取

为了减少轮廓数据量，加快凸包计算和阈值圆分类的运行速度，在确定指尖点之前，根据获取的手掌轮廓图，提取多边形，以逼近手掌轮廓。

手的轮廓多边形提取采用Douglas-Peucker算法，该算法主要用于曲线近似表示。算法如下：

a)在曲线首尾（A,B）连接一条直线，计算曲线上其余各点到直线的距离；

b)选择距离的最大值，与预先给定的阈值比较；如果距离最大值小于阈值时，将该直线AB作为曲线的近似，处理完毕。

c)如果距离最大值大于阈值，以最大值点C为分割点，连结AC、BC，并对这两段线重复1、2两部分的操作，重复迭代，直到曲线上所有的点到对应折线的距离均小于设定阈值。

d)处理完成后，连结各个分割点，形成的折线即为获得的近似曲线。

如图4所示，通过若干次迭代，依次搜索出分割点C、D、E，曲线AB可近似表示为折线AEDCB。

![](images/0c80839ebffc2c56ca538087511c2825d1989b6d0ae428fae6c516d5a8df7761.jpg)  
图4近似曲线提取  
Fig.4Approximate curve extraction byDouglas-Peucker algorithm

利用Douglas-Peucker算法，在手掌分割图的基础上，设置合适的阈值，得到图5中粗线条所示的几何多边形，较好地逼近手掌轮廓。

![](images/43e5119dee251f8f4dcb7862021c88b4683f19bf1078c46397fab80a0b21cdf5.jpg)  
Fig.3Feature extraction of geometric invariant moment for different   
图5手掌多边形Fig.5Palm polygon

# 2.2.2候选指尖点提取

利用凸包算法，可以得到候选指尖点。图5(a)所示手势有7个候选指尖点。基于凸包算法的指尖点筛选法，能够有效提取指尖点，避免指根点等缺陷点的误提取。但是，对于手掌轮廓边缘与小臂交界处的点、手指弯曲时残留顶点等干扰点，难以区分，因而手势轮廓多边形的凸包点并非都是指尖点，需要进一步过滤这些无关点，阈值圆法可以解决这一问题。

# 2.2.3阈值圆指尖点提取

在某一固定深度时，手部的面积在五指伸开时最大，成拳形面积最小（约为手掌去除掉五指时的面积)；此时，以掌心为圆心，设置一个合适的阈值圆，则指尖点均分布在圆外。阈值圆指尖点提取法中，掌心位置和阈值圆半径的选取将决定指尖点提取的准确性。

1)掌心计算

前述由Kinect手掌跟踪算法直接获取的手掌心三维坐标$( \mathbf { \boldsymbol { x } } _ { \mathrm { H } } , \mathbf { \boldsymbol { y } } _ { \mathrm { H } } , \mathbf { \boldsymbol { z } } _ { \mathrm { H } } )$ 是包括五指的，无法满足阈值圆指尖点提取法的应用需求。因而，提出一种基于距离变换的掌心精确计算方法，算法流程如下：

a)将手掌图像二值化，手掌设为白色，其他区域黑色，如图6(a)所示；

b)遍历图像，计算非零像素（白）到最近零像素的距离，图6(b)中颜色深浅反映该距离大小，离零像素点越远处越亮；

c)设置阈值，将距离小于阈值的像素置为黑，大于阈值则不变，得到图像6(c);

d)求处理后图像中心 $p$ ，为所有非零像素点图像矩阵位置x,y的均值。图6(d)(e)中分别显示不同手势时掌心位置，该位置将不受手指伸缩状态影响。

![](images/5a18d8acf5c108b77d83d4a43e390a8c582ad3237987ad9ca0e5f0e54f980d87.jpg)  
图6通过距离变换找到掌心  
Fig.6Find the palm by distance transformation

2)阈值动态调整算法(1)阀值调整原理

相机成像过程中，物体（长度 $L$ ）在图像中的投影长度1与物体到相机的距离depth成反比，即

$$
{ \frac { l } { L } } = { \frac { f } { d e p t h } }
$$

其中: $f$ 为深度相机焦距，depth表示深度，即手掌距离传感器

的距离。

![](images/98f44463fcac9e673849687dc7719895b098eb7623146a8802a6ed032da387ec.jpg)  
图7相机成像原理  
Fig.7 Camera imaging principles

对于手掌轮廓图像中阈值圆 $\mathbf { r }$ 与实际衡量手掌的圆R关系由上述原理可得：

$$
r = { \frac { f R } { d e p t h } }
$$

考虑到传感器误差等因素存在，设置缩放误差 $\lambda$ 和偏移误差系数 $\beta$ ，因此

$$
r = \frac { \lambda f R } { d e p t h } + \beta = \frac { \alpha } { d e p t h } + \beta
$$

其中： $\alpha = \lambda f R$ 。

则手掌成像大小与手掌到相机的距离有关。因此，阈值圆法中的阈值半径r随着距离depth动态调整遵循式(10)。

(2)系数 $\alpha$ 、 $\beta$ 回归分析

为了确定式(9)中的系数 $\alpha$ 、 $\beta$ ，通过实验方法，由Kinect采集若干组 $\mathbf { r }$ -depth对应数据，由回归分析获取 $\alpha$ 、 $\beta$ 的数值。

Kinect检测的深度范围是 $0 . 5 { \sim } 4 \mathrm { m }$ 之间，当距离太远时手掌面积太小，受噪声干扰较大，故实验主要是取区间 $5 4 0 \sim 8 0 0$ $\mathrm { m m }$ 的距离。

以深度 $5 4 0 ~ \mathrm { m m }$ 为例，由采集的五指轮廓图，计算质心点$p = \left( p x , p y \right)$ 。由轮廓多边形提取和凸包计算后得到凸包点序列，记作： $\{ p _ { 1 } , p _ { 2 } , p _ { 3 } , . . . , p _ { n } \}$ 。计算质心到所有凸包点的距离的均值：

$$
M = { \frac { \sum _ { i = 1 } ^ { n } \left( { \sqrt { \left( p _ { i } x - p x \right) ^ { 2 } + \left( p _ { i } y - p y \right) ^ { 2 } } } \right) } { n } }
$$

令阈值圆的半径 $r = 0 . 7 5 M$ 。

测量不同深度depth下，在五指伸直时，手掌阈值圆的半径 $\boldsymbol { r }$ ，得到样本数据如表2所示。

表2深度depth与手掌阈值圆半径r的对应关系  
Table 2Correspondence between depth and radius r of palm threshold circle   

<html><body><table><tr><td>depth/mm</td><td>540</td><td>560</td><td>580</td><td>600</td><td>620</td><td>.. 720</td><td>740</td><td>760</td><td>780</td><td>800</td></tr><tr><td>r</td><td>84</td><td>80</td><td>79</td><td>75</td><td>74</td><td>. 63</td><td>61</td><td>57</td><td>60</td><td>58</td></tr></table></body></html>

将表2数据代入式（8）中，通过线性回归可以获得 $\mathfrak { a }$ 、 $\beta$ 数值。回归分析结果如图8所示，则 $\alpha = 4 5 2 3 6$ ， $\beta = 0 . 4 8 3 8$ 。

在不同深度条件下，阈值圆半径根据式(9)动态调整，以消除手掌距离相机位置不同对阈值圆分类法的影响，较好的剔除无关点，提高指尖点检测的准确性，减小对手掌运动范围的限

制。

![](images/21599e54959d521e4bb7f32e16f35eb6441a96acf47765b15a4d3cd0a8b1e712.jpg)  
图8半径与深度的关系

# 2.2.4阈值圆指尖点分类

在不同深度、不同手势的情况下，通过可以动态调整的阈值圆，去除阈值圆内的无关点，保留阈值圆外的指尖点。该方法能够得到较好的分类效果。如图9所示，大圈为动态阈值圆，其外部标记点是从候选指尖点中分离出来的有效指尖点。

![](images/51326012ed93fd25de3e6ea68127fab09a72435c063237f0222d9c35d6bc4aba.jpg)  
Fig.8Relationship between radius and depth   
图9不同深度、不同手势下的阈值圆和指尖点提取  
Fig.9Threshold cycle and fingertip points extraction under differen depths,different gestures

经过几何不变矩特征量计算和指尖点提取，得到手势特征$X = \left\{ \boldsymbol { I } _ { 1 } ^ { ' } , \boldsymbol { I } _ { 2 } ^ { ' } , \boldsymbol { I } _ { 3 } ^ { ' } , \boldsymbol { I } _ { 4 } ^ { ' } , \boldsymbol { a } \right\}$ ，其中， $\dot { I _ { 1 } ^ { ' } } , \dot { I _ { 2 } ^ { ' } } , \dot { I _ { 3 } ^ { ' } } , \dot { I _ { 4 } ^ { ' } }$ 是几何不变矩的前四个特征量，a是指尖点数。手势识别在此基础上展开。

# 3 K最近邻手势识别算法

通过手势特征提取得到特征向量 $X = \left\{ \boldsymbol { I } _ { 1 } ^ { ' } , \boldsymbol { I } _ { 2 } ^ { ' } , \boldsymbol { I } _ { 3 } ^ { ' } , \boldsymbol { I } _ { 4 } ^ { ' } , \boldsymbol { a } \right\}$ ，在此基础上，利用分类算法对手势进行分类，以完成手势识别。由于需要识别的手势种类较多，且需要较高的实时性，所以采用K最近邻算法（KNN）作为分类方法。KNN分类器无须训练，无须估计参数，在多分类问题中具有较好的分类效果，是一种简单高效的分类算法。

K最近邻算法的核心思想是构建一个样本集，包括若干组标签不同的样本子集，每个样本子集是由特征向量相近的样本组成。在分类时，输入测试样本，找到样本集中前K个最相似（距离最近）的样本，其中出现次数最多的标签即为该测试样本的类别。

在手势识别中，以手掌几何不变矩和指尖点个数组成特征向量 $X = \left\{ \boldsymbol { I } _ { 1 } ^ { ' } , \boldsymbol { I } _ { 2 } ^ { ' } , \boldsymbol { I } _ { 3 } ^ { ' } , \boldsymbol { I } _ { 4 } ^ { ' } , \boldsymbol { a } \right\}$ ，作为分类依据。手势识别时采用欧氏距离d，度量样本之间的相似性。

$$
d = \sqrt { \sum _ { i = 1 } ^ { n } \left( x _ { 1 i } - x _ { 2 i } \right) ^ { 2 } }
$$

其中： $X _ { _ 1 } = [ x _ { _ { 1 1 } } , x _ { _ { 1 2 } } , x _ { _ { 1 3 } } , x _ { _ { 1 4 } } , x _ { _ { 1 5 } } ]$ 为测试样本特征向量，$X _ { _ 2 } = [ x _ { _ { 2 1 } } , x _ { _ { 2 2 } } , x _ { _ { 2 3 } } , x _ { _ { 2 4 } } , x _ { _ { 2 5 } } ]$ 为样本集特征向量， $\scriptstyle \mathtt { n } = 5$ 为手势特征向量的维度。

在KNN算法中，参数 $\mathbf { k }$ 的取值对分类准确率有较大影响。$k$ 值较大时，可以减少干扰数据的影响，但缺点是近似误差会增大；当 $k$ 值较小，会导致过度拟合。通常 $k$ 值设置为 $\sqrt { \mathrm { m } }$ ，$\mathrm { ~ m ~ }$ 为样本数量。

为防止某个特征过大或者过小，引起分类过程中各特征所起作用严重失衡，需要对数据进行归一化；同时，归一化有利于提高算法速度。在此，采用线性归一化方法。

$$
y = { \frac { x - m i n V a l } { m a x V a l - m i n V a l } }
$$

其中：maxVal、minVal分别代表全部数据样本中该维数据的最大值和最小值。 $\mathbf { x }$ 为待归一化的数值，y即为归一化结果，其值介于0\~1之间。

本文手势识别算法中，样本集由标签为“手势1”到“手势$6 ^ { \prime \prime }$ 的六个子集组成，每个子集由事先采集的15个同类手势组成。KNN手势识别算法中，通过KNN分类器，获取待测手势的标签号，完成手势识别。

# 4 算法流程

基于复合特征和动态阈值圆法的手势识别算法的流程如图10所示。

![](images/fbadbabaf0c0154dc62a860da289fa3dd106d3a27c9e614889864139ee01d317.jpg)  
图10手势识别流程图

# 5 手势识别实验

为验证基于复合特征和动态阈值圆法的手势识别算法的有效性，进行相关实验。实验基于PC平台与Kinect传感器。PC具有 $2 . 9 \mathrm { G H z }$ 的CPU与8GB的RAM；Kinect的采样图片大小为 $3 2 0 ^ { * } 2 4 0$ ，帧率30fps，能达到实时识别的硬件要求。利用OpenNI和OpenCV开源库在VisualStudio 搭建实验平台。

实验过程中，三名不同的实验者随机作出编号为1-6的6种手势，其中编号1-5的手势分别为手指伸出1到5指，编号6即为手掌为拳形的手势。手掌位置和手掌离Kinect的距离也随机变换，共计采集240组手势数据，手势识别结果如表3所示。

从表3中可以看出，在动态调节阈值圆的情况下，对于不同手势，平均识别率达到 $9 6 . 2 5 \%$ 以上。在实验过程中，其识别响应时间平均为 $0 . 6 5 \mathrm { ~ s ~ }$ ，算法具有较高的实时性。

手势5的识别率较其他手势稍差，仅为 $9 2 . 5 0 \%$ 。通过分析及实验验证，这一现象是由于大拇指较其他手指短，当其过于靠近食指时，易于造成错误识别。如图11所示，图11(a)可正确识别，图11(b)大拇指过于靠近手掌，识别已出现偏差，而图11(c）与手势4相似，导致错误识别。

Table3 Gesture recognition experiment results   

<html><body><table><tr><td>手势编号</td><td>样本数</td><td>识别正确数</td><td>识别率</td></tr><tr><td>1</td><td>40</td><td>40</td><td>100%</td></tr><tr><td>2</td><td>40</td><td>39</td><td>97.5%</td></tr><tr><td>3</td><td>40</td><td>38</td><td>95.0%</td></tr><tr><td>4</td><td>40</td><td>38</td><td>95.0%</td></tr><tr><td>5</td><td>40</td><td>37</td><td>92.5%</td></tr><tr><td>6</td><td>40</td><td>39</td><td>97.5%</td></tr><tr><td>总计</td><td>240</td><td>231</td><td>96.25%</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>(a)</td><td>(b)</td><td></td><td>(c)</td></tr></table></body></html>

针对手势5这一问题，重复采集数据，要求大拇指不得过于靠近食指，对采集的30组手势数据进行识别，识别正确的样本数为29，识别率为 $9 6 . 6 7 \%$ 。

KNN算法的主要参数是K值，K值过大或过小均可能会对结果造成影响。前文中采集90组样本集，每个手势各15个，由于K值的选择通常是奇数，因此K值从3开始到13，以相同的测试样本，改变K值，重新统计手势识别的准确率。如图12所示。

![](images/8769d5a818129f09b86f5bb6c5e3861c257307cab4434820fbd4f0b81089c7de.jpg)  
图11大拇指位置对手势5识别的影响  
Fig.11Effect of thumb position for gesture 5 recognition   
图12 $k$ 值对准确率的影响  
Fig.12Effect of $k$ value on accuracy

从图中可已看出 $k$ 值过大或者过小对准确率都有不同程度的下降，当 $k$ 介于5\~11时，准确率均能达到 $9 5 \%$ 以上。

为了与KNN算法做对比，本文引入BP神经网络和支持向量机(SVM)分类器对手势进行识别，其训练样本集与前文KNN算法样本集的相同，测试样本集也相同。

从表中可以看出KNN 算法的识别率最高。其根本原因在于BP神经网络算法和SVM算法都是需要对样本进行训练，对样本的数量和质量要求较高，样本数量过少会导致训练的模型泛化能力较差，识别效果不佳。因此本文通过增加训练样本数量将总样本数量提高到180组，SVM分类的识别率提升到了$9 6 . 6 7 \%$ ，BP神经网络的提高到了 $9 5 . 0 \%$ 。与KNN 算法相比，SVM分类器和BP神经网络均要对样本进行训练，会花费较长时间，而KNN算法无须训练，算法的流程也十分简单，因此花费时间与前两种算法相比较少，能满足本文手势实时识别的要求。

综上所述，对于不同人的手部特征，均有较好地识别效果。实验证明了基于复合特征和动态阈值圆法的手势识别算法的有效性和实时性。

表3势识别实验结果  
表4不同分类算法的手势识别结果  

<html><body><table><tr><td>分类算法</td><td>识别率/%</td></tr><tr><td>SVM分类器</td><td>90.83</td></tr><tr><td>BP 神经网络</td><td>83.33</td></tr><tr><td>KNN</td><td>96.25</td></tr></table></body></html>

# 6 结束语

本文利用深度图像，通过深度阈值分割手部区域。引入图像的几何不变矩作为分类的特征，与指尖点特征一起构成复合手势特征。提取指尖点时，动态调整阈值圆以除去噪点。最后以图像的矩和指尖点为分类特征，用最近邻算法（KNN）进行分类，实现手势识别。基于复合特征和动态阈值圆法的手势识别算法能够有效进行手势识别，识别率高、实时性好。

# 参考文献：

[1]Sturman D J,Zeltzer D,Pieper S.Hands-on interaction with virtual environments[C]//Proc ofACM GRAPH Symposium on User Interface Software and Technology.New York: ACMPress,1989:19-24.   
[2]李勇，高文，姚鸿勋．基于颜色手套的中国手指语字母的动静态识别 [J].计算机工程与应用,2002,38(17):55-58.(Li Yong,Gao Wen,Yao Hongxun.Dynamic and Static Recognition ofChinese FingerLetters Based on Color Gloves [J].Computer Engineering and Applications,2002,38(17): 55-58.)   
[3]任海兵，祝远新，徐光，等．基于视觉手势识别的研究综述[J]．电子 学报,2000,28 (2): 118-121.(Ren Haibing, Zhu Yuanxin, Xu Guangzheng et al.Research based on visual gesture recognition:a review [J].Chinese Journal of Electronics,2000,28 (2): 118-121.)   
[4]邱迪．基于HSV与YCrCb 颜色空间进行肤色检测的研究[J].电脑编 程技巧与维护,2012(10):74-75.(Qiu Di.Research on Skin color detection based on hsv and ycrcb color space [J].Computer Programming Skills and Maintenance,2012 (10): 74-75.)   
[5]李擎，唐欢，迟健男，等．基于改进最大类间方差法的手势分割方法研 究[J]．自动化学报,2017,43(4):528-537.(LiQing,Tang Huan,Chi Jianan,et al.Research on gesture segmentation based on improved maximum variance between classes [J].Automation Journal, 2017,43 (4):

# 528-537.)

[6]许凯，王敏．基于手轮廓的深度图像手势识别方法[J].计算机工程与 科学,2014,36(5): 941-946.(Xu Kai,Wang Min.Gesture recognition based on hand contour in depth image [J].Computer Engineering & Science,2014, 36 (5): 941-946. )   
[7]李瑞峰，曹雏清，王丽．基于深度图像和表观特征的手势识别[J]．华 中科技大学学报：自然科学版,2011,39(s2):88-91.(LiRuifeng,Cao Xiaoqing,Wang Li. Gesture recognition based on depth images and appearance features [J]. Journal of Huazhong University of Science and Technology: Nature Science,2011,39 (s2): 88-91.)   
[8]Yoruk E,Konukoglu E, Sankur B,et al. Shape-based hand recognition [J]. IEEE Trans on Image Processing,2006,15(7):1803.   
[9]谈家谱，徐文胜．基于Kinect 的指尖检测与手势识别方法[J].计算机 应用，2015，35(6):1795-1800.(Tan Jiapu,Xu Wensheng.Fingertip detection and hand gesture recognition method based on Kinect [J]. Journal of Computer Applications,2015,35(6): 1795-1800.)   
[10]高晨，张亚军．基于Kinect 深度图像的指尖检测与手势识别[J].计算 机系统应用,2017,26(4):192-197.(Gao Chen,Zhang Yajun.Fingertip detection and gesture recognition based on Kinect depth image [J]. Computer Systems & Applications,2017,26(4):192-197.)

[11]杨学文，冯志全，黄忠柱，等．结合手势主方向和类-Hausdorff 距离的 手势识别[J].计算机辅助设计与图形学学报,2016,28(1):75-81.(Yang Xuewen,Feng Zhiquan，Huang Zhongzhu,et al.Gesture recognition combined with gesture main direction and class-Hausdorff distance [J]. Journal of Computer-Aided Design & Computer Graphics,2016,28(1): 75- 81.）

[12] Oden C,ErcilA,Buke B.Combining implicit polynomials and geometric features for hand recognition [J].Pattern Recognition Letters,2oo3,24(13): 2145-2152.

[13]崔家礼，解威，王一丁，等．基于自适应手指分割与判别的静态手势识 别[J].计算机应用与软件,2016,33(10):181-186.(Cui Jiali,Jie Wei, Wang Yiding,et al. Static gesture recognition based on adaptive finger segmentation and discrimination [J]. Computer Applications and Software, 2016,33 (10): 181-186.)

[14]Hu MK.Visual pattern recognition by moment invariants [J].Information Theory Ire Transactions on,1962,8(2):179-187.

[15]王艳，徐诗艺，谌海云．基于特征距离加权的手势识别[J].计算机科 学,2017,44 (s1): 220-223.(Wang Yan,Xu Shiyi, Yan Haiyun. Gesture Recognition Based on Feature Distance Weighting [J]. Computer Science, 2017,44 (s1): 220-223.)