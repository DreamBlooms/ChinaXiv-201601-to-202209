# 基于复合动态模型和证据融合架构的移动物体检测与跟踪方法

程蔚1，吴海彬²，郑洪庆1

(1．闽南理工学院 电子与电气工程学院，福建 石狮 3627002;2.福州大学 机械及自动化学院，福州 350116)

摘要：在高级驾驶辅助系统的环境感知功能中，移动物体检测与跟踪的准确性至关重要。针对现有方法精度较低的缺点，提出一种基于多传感器检测分类的移动物体描述和感知方法：建立了一个包含核心对象动态特征和分类描述的复合模型，在此基础上设计了一个基于证据框架的信息感知与融合方法，通过整合动态模型和不确定性特征来实现对移动物体的检测和跟踪。为了验证所提方法的有效性，在一辆安装有雷达、激光雷达和摄像头的演示车上进行了相关实验，在不同驾驶场景下针对行人、卡车和轿车三个移动物体进行了检测与跟踪，实验结果证明所提方法具有非常高的准确性。

关键词：移动物体检测与跟踪；多传感器系统；分类算法；复合动态模型；证据融合架构 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.04.0281

# Moving object detection and tracking based on composite dynamic model andevidential fusion framework

Cheng Wei1,Wu Haibin², Zheng Hongqing1 (1.SchoolofElectronicAndElectricalEngineeing,MnnaPolytechicIstitute,ishiFujian36o,China;2stiutef Machinery&Automation,Fuzhou University,Fuzhou 350116,China)

Abstract:The accuratedetectionand trackingof moving objects isacriticalaspectof environmental perception functionin advanced driver asistance systems.In order to overcome the disadvantage of low precision in existing methods,a novel descriptionand perception method basedon multiple sensor detection and clasification is proposed:the composite model containing dynamic propertyandclasificationdescription is established,basedonthis model,perceptionandfusionethod of information based on evidential framework is devised to realize detection and tracking of moving object by integrating dynamic modeland uncertain feature.Tovalidatetheefectiveness oftheproposed method,some experiments onavehicle demonstrator with radar,lidar,and cameraarecarriedout,thedetecting and trackingof threeobjects including pedestrian, truck,andcarunder different driving scenarios is tested,andtheresults show thattheproposedmethod possesses high precision.

Key words:detectionand tracking of moving object;multiple-sensor system;clasification algorithms;composite dynamic model; evidential fusion framework

# 0引言

随着智能控制、信息通信和工业制造等技术不断进步，智能汽车已经获得了广泛研究和商业化发展[I。智能汽车系统最引人注目的特性是其具备在不确定性、动态变化的非结构化环境中稳定可靠运行。而智能汽车中的自动驾驶辅助系统则发挥着帮助司机执行复杂的驾驶任务，从而以避免危险情况发生的重要作用[2]。具体为：通过环境感知方法，在碰撞、刮擦等危险发生之前发出警告消息，触发安全装置，自动制动规避障碍物，提醒驾驶员集中注意力以避免即将发生的碰撞。

环境感知的机理[3]为通过合理选择传感器来获得外部环境的详细描述和所关注对象的准确识别。在车辆环境感知中主要包括两个任务，即时定位与地图创建(simultaneouslocalization&mapping，SLM)和运动目标检测与跟踪(movingobjectdetection&Tracking，MODT)。SLM基于给定的传感器参数实时绘制包括车辆自身及其周边环境的地图。MODT检测、跟踪车辆周围的移动物体，并对它们未来的运动进行预测。

不完整信息的管理与感知是环境感知系统中的一个重要功能需求[4。这些不完整的信息可能是由传感器的校准、硬件故障、不确定检测和异步扫描等问题产生，也可能是由遮挡、天气、对象的移动等环境扰动问题产生。在大多数的实际室外场景中，不仅需要对环境嘈杂、静态对象等非移动物体进行检测，更需要对移动物体进行跟踪和数据关联。正确地检测运动对象是运动目标跟踪系统的一个重要方面，并往往需要借助大量的传感器进行辅助配合。

通过对周边环境中的移动对象进行分类，可以使得智能汽车对当前驾驶状况获得更好的理解[5]。物体分类是MODT任务中一个独立的任务，或作为环境感知的一个输出集合信息。分类可以通过包含不同传感器提供的环境信息来丰富、充实检测结果，这些信息包括激光雷达的落点和相机提供的图像块。移动物体分类可以对目标进行区分和确认，并为数据关联提供线索。此外，移动目标的分类还有助于了解运动模型，进而对其进行跟踪。在识别初期，通过多传感器数据融合对感兴趣的目标进行分类，有助于提高检测和跟踪的性能，降低检测的假阳性率和误分类率[6]。

感知系统内包括不同的融合级别。低水平融合在SLM中进行，而检测和跟踪级融合则在MODT中进行。在检测阶段，融合是基于各传感器提供的移动目标列表来实现的。在跟踪阶段，单个传感器模块的跟踪列表用来产生最终的跟踪列表。文献[7\~10]已经对SLM进行了充分的研究，得到了较为新颖和实用性强的结果。因此，本文针对MODT，在融合激光雷达、摄像头和雷达三类传感器装置中数据的基础上，基于不同类集合质量分布的证据对其进行研究。

多传感器跟踪融合需要获得一系列传感器的跟踪列表并将它们融合成一个组合列表。文献[11\~13]通过关注不同跟踪裂变中的关系，并对相关目标进行随机组合来解决这一问题。在跟踪阶段，通过有效的融合策略，可以明显减少错误的跟踪，提高跟踪精度，并为最终输出补充分类信息。

检测阶段的目的是从传感器中收集、组合初始数据。文献[14]建议在这个级别进行融合，从而减少可能会导致跟踪失败的错误检测。其他文献注重解决主动和被动传感器的数据冗余，并按照物理条件或约束条件来提高目标检测的精度[15.16]。然而这些研究并没有充分利用所有可用的运动状态和外观信息。此外，在区别运动物体和固定物体上，传感器测量的外观信息被认为不如运动状态信息重要。

当分类被认为是感知方案内部的独立模块时，通常被用来实现单个类(如仅分类行人)或基于单个传感器的分类过程。这种方法可以排除各个传感器中数据的差别。研究表明，如果在感知的早期阶段对分类信息进行有效的管理，增强数据的关联性，可以直接增强物体的跟踪精度[17,18]。在多传感器融合方法中，最常见的是基于概率的方法[19]。然而基于证据框架的方法不仅能够对多传感器进行融合，还能够对车辆进行感知[20]。与基于概率的方法相比，基于证据框架的方法充分利用了不完整、不准确的信息，从容提高了检测精度。

在上述研究的基础上，针对传感器数据关联、基于传感器融合的目标检测与跟踪问题，提出一种新的方法。首先，建立包含核心对象动态特征和分类描述的复合模型，在此基础上设计基于证据框架的信息感知与融合方法，通过整合动态模型和不确定性特征来实现对移动物体的检测和跟踪。此外，从不同传感器加入的知识来增强对象描述的精确度：利用雷达获得的信息对移动物体进行初步检测；利用激光雷达数据对目标的距离和尺寸进行估计；利用摄像头获得的分类信息对检测到的目标进行假设。为了验证所提方法的有效性，在一辆演示车上进行了相关实验，针对行人、卡车和轿车三个移动物体进行了检测与跟踪，实验结果证明了所提方法的高准确性。

# 1证据框架与SLM简介

# 1.1证据框架概述

证据框架是贝叶斯框架主观概率的推广，可以根据现有证据得到一个相关问题的置信度，并用一组被称为识别框架 $\Omega$ 的互斥命题表示整个现实世界。

置信度函数的表述为 $m : 2 ^ { \Omega } \to [ 0 , 1 ]$ ，在实际应用中，常使用式(1)所示的基本信度函数。

$$
\left\{ \begin{array} { l l } { \displaystyle m \big ( \phi \big ) = 0 } \\ { \displaystyle \sum _ { A \subseteq \Omega } m \big ( A \big ) = 1 } \end{array} \right.
$$

其中： $A$ 为待识别数据集。

实际中，为了避免一些可能与实际情况有较大冲突的反常识性结果，需要对式(1)所示的置信度函数进行式(2)所示的规则化处理，从而使冲突值分布于识别框架的所有元素中，而不仅仅是具有组合质量的交集的元素。

$$
\left\{ \begin{array} { l } { \displaystyle m \big ( A \big ) = \sum _ { X _ { i } \cap Y _ { j } = A } m _ { 1 } \big ( X _ { i } \big ) m _ { 2 } \big ( Y _ { j } \big ) } \\ { \displaystyle m \big ( \Omega \big ) = \sum _ { X _ { i } \cap Y _ { j } = \Omega } m _ { 1 } \big ( X _ { i } \big ) m _ { 2 } \big ( Y _ { j } \big ) + \sum _ { X _ { i } \cap Y _ { j } = \phi } m _ { 1 } \big ( X _ { i } \big ) m _ { 2 } \big ( Y _ { j } \big ) } \end{array} \right.
$$

证据框架具有表达不完整证据和缺乏先验概率目标的能力，因此可以在定义识别框架时使用隐含信息。此外，折扣系数是整合多来源证据的重要机制，并可以根据传感器性能设定系数，而组合规则是整合来自不同来源证据的有效工具。然而当数量过大时，证据框架的计算复杂度会因为需要计算所有假设集的置信度会大幅增加。因此，在实际应用中，可以将 $\Omega$ 转换为精简版本。

# 1.2 SLM概述

虽然本文的主要工作集中在MODT组件上，但是需要借助SLM获取地图和车辆姿态，即利用激光雷达数据( $z _ { 1 : t }$ )填充二维贝叶斯障碍网格图 $M$ ，图中的每一个小格与物体被障碍物遮挡的概率相关。车辆位置利用极大似然估计法获得，基于形状模型 $P \big ( \omega \big | z _ { \mathrm { l } : t } \big )$ 、先前模型 $P ( \omega )$ 以及似然模型 $P { \left( z _ { \mathrm { 1 } : t } | \omega \right) }$ 来寻找最好的车辆轨迹估计 $\omega ^ { * }$ ：

$$
\boldsymbol { \omega } ^ { * } = \underset { \omega \in \Omega } { \arg \operatorname* { m a x } } P \big ( \omega | z _ { 1 : t } \big ) \mathrm { ~ f o r ~ } P \big ( \omega | z _ { 1 : t } \big ) \propto P \big ( \omega \big ) P \big ( z _ { 1 : t } | \omega \big )
$$

# 2移动目标检测与跟踪

移动目标跟踪的第一阶段为利用不同传感器(包括激光雷达、摄像头和雷达)提供的数据来检测智能车辆周边趣的移动目标。

# 2.1目标检测

基于光探测和测距的激光雷达扫描器因其较高的分辨率和障碍物检测精度，而作为移动目标检测的主传感器。激光雷达传感器的主要探测目标是获取车辆前方移动障碍物形状的精确测量数据。基于激光雷达传感器的检测原理为辨识网格图 $M$ 中空闲区和障碍区在的矛盾，具体为：如果检测到空闲区的位置被占用，那么它应该属于一个移动对象；如果检测到被占据的格子被释放，那么它就可能属于一个静态对象。基于距离聚类方法，可以明确识别属于移动对象的网格云，同时提供可能的移动目标的形状、尺寸估计以及距离等信息。

为了从摄像头拍摄的图像中获取移动物体的外观信息，需要提取具有区分度的视觉特征。方向梯度直方图方法可以较好地检测到移动的车辆和行人，因此选用方向梯度直方图作为车辆和行人可视化描述的核心，进而产生图像局部信息的视觉描述，并最终用于决定这些区域是否包含所需检测的移动目标。为了提高检测精度，提出一种重点关注图像中的特定区域的稀疏方向梯度直方图，实现了高维描述符计算量的有效降低。此外，为了加快特征计算过程，提出的方法遵循了整合图像处理方案的相关规则。

通过光雷达检测图像的特定区域获得感兴趣区域后，进一步针对每个区域提取视觉特征，然后使用分类器确定其是否在感兴趣区内。由此可知，分类器的选择对最终的处理速度和处理结果有着极为重要的影响，选用了基于一种离散增强学习算法的分类器，它通过汇集多个弱分类器形成一个强分类器，而每个弱分类器仅需要实现比随机猜测略好的分类效果即可。

针对每个待检测的移动目标(包括行人、卡车和轿车)，都需要训练一个相应的二元分类器。在这一训练阶段，可以从公共数据库和手动标注的包含分类目标的图像中获取待检测目标不同视角(如正面、背面和轮廓等)的信息。接下来，需要估计每一种目标分类的可能性。该估计遵循以下原则，即包含待检测对象的积极区域的数量越多、可信度越高，就可以确定该目标属于特定类。

雷达传感器使用内置机制检测移动障碍物或目标，并将 $n$ 个目标的列表作为感知算法的输入。列表中的每个元素包括待检测到目标的距离、方位和相对速度。雷达传感器会为每个复合特定截面的移动对象产生一个靶点。然而需要注意的是，靶点既可能对应着静态对象，也可能对应着其他移动障碍，由此会导致误检测。例如，像行人这类弱对象极有可能检测不到。

由于待检测对象有不同的动态定义，所以需要借助基于恒定速度、恒定加速度和转角模型的交互多模型对每个靶点进行跟踪。靶点间的数据关联性由非均匀多假设跟踪方法获得。

# 2.2目标分类

由3.1节分析可知，通过在检测阶段融合分类信息，可以使得提出的方案比一般方法具备更好的描述移动目标运动学特征的能力。这一方法不仅可以提高检测精度，实现移动目标运动的精确估计，还能减少跟踪的错误率。然而在检测阶段并没有足够的信息确定目标分类。因此，需要建立由运动学信息和外观信息两部分组成待检测移动物体的复合动力模型。运动学信息包括了从移动目标检测过程中推断得到的二维空间位置和形状信息。外观信息包括了所有可能假设类的证据分布 $m ( 2 ^ { \Omega } )$ ，其中 $\Omega = \{ p , b , c \}$ 表示待检测的类别集合，其中 $p$ 、 $b$ 、 $\boldsymbol { \mathbf { \mathit { c } } }$ 分别代表行人、卡车、轿车。

对于激光雷达检测到的尺寸较大的目标，可以用一个集合$\{ x , y , w , l \}$ 所描述的矩形框来表示，其中： $x$ 、 $y$ 是所述框的中心； $w$ 和 $\mathbf { \Phi } _ { l }$ 分别表示目标的宽度和长度。对于尺寸较小目标，可以用集合 $\{ x , y \}$ 所描述的点模型来表示，其中 $x \setminus y$ 表示目标的中心点。目标的位置和尺寸可以通过测量其所占用的二维网格数量获得，而目标的分类是通过可视尺寸以及后续的固定拟合模型方法推断出的。然而，由于移动目标的可视时间较短，所以并不能作出精确地分类。例如，如果一个待检测对象的宽度小于某设定的阈值 $\omega _ { s m a l l }$ ，就可能会令检测系统误认为待检测对象是行人或卡车，但却无法确定物体的实际尺寸。因此，需要基于物理尺寸分布的先验知识对所检测类的典型尺寸进行定义。为了区别于一般方法，本文对每个 $A \in \Omega$ 定义了式(4)所示的基本置信度分配 $m _ { 1 } ( A )$ ，而不是简单地作出目标仅属于某一类的决定。基本置信度分配描述了激光雷达检测到的移动目标分类的证据分布。公式中使用了一系列分类相关因子α、αb\`$\alpha _ { c }$ 描述激光雷达对检测行人、卡车和轿车的性能。此外，还使用了衰减因子 $\gamma _ { b }$ 和 $\gamma _ { c }$ 来表示激光雷达检测结论为卡车或轿车的不确定性。

由于视觉条件所限，如果检测到的移动物体是卡车，目标依然有可能是轿车的一部分。因此，处理证据时需要将 $\{ b , \ c \}$ 考虑在内。在所有的情况下，未知假设 $\Omega$ 都表示缺乏类别先验知识的情况。

$$
\begin{array} { r } { m _ { 1 } ( A ) = \left\{ \begin{array} { l } { m _ { 1 } \left( \{ p _ { 1 } ^ { ( 1 ) } \} = \alpha _ { p } \right) = p } \\ { m _ { 1 } \left( \Omega \right) = 1 - \alpha _ { p } \Bigg \} \Rightarrow p } \\ { m _ { 1 } \left( \{ b \} \right) = \gamma _ { i } \alpha _ { i } } \\ { m _ { 1 } \left( \{ b , c \} \right) = \gamma _ { p } \left( 1 - \alpha _ { s } \right) \Bigg \} \Rightarrow b } \\ { m _ { 1 } \left( \Omega \right) = 1 - \gamma _ { s } } \\ { m _ { 1 } \left( \{ c \} \right) = \gamma _ { c } \alpha _ { c } } \\ { m _ { 1 } \left( \{ c , \{ e , p \} \} \right) = \gamma _ { c } \left( 1 - \alpha _ { c } \right) \Bigg \} \Rightarrow c } \\ { m _ { 1 } \left( \Omega \right) = 1 - \gamma _ { c } . } \end{array} \right. } \end{array}
$$

利用摄像头获得移动目标图像，通过对这些图像进行处理可以得到目标类在外观上的证据分布，进而利用离线分类器进行分类。

基于摄像头的分类需要在每个待测区域中产生多个子区域，从而覆盖尽可能多尺寸的目标结构。当得到每个待测区域的对象分类后，基于式(5)所示的基本信度分配 $m _ { 2 }$ 表示图像处理过程检测到的每一个目标 $\Omega$ 的分类假设的证据分布。

$$
\begin{array}{c} \begin{array} { r } { m _ { 2 } ( A ) = ( \begin{array} { l } { m _ { 2 } ( \{ \hat { y } _ { 1 } ^ { \parallel } \} = \delta _ { r } c ,  } \\ { m _ { 2 } ( \{ \hat { y } _ { 2 } ^ { \parallel } \} ) = \delta _ { r } ( 1 - \sigma ) } \\ { m _ { 2 } ( \{ \Phi _ { 2 } ^ { \parallel } \} ) = - \delta _ { r } } \\ { m _ { 2 } ( \{ \hat { y } _ { 1 } ^ { \parallel } \} ) = \delta _ { \sigma } } \end{array} ) = p } \\ { m _ { 2 } ( A ) = ( \begin{array} { l } { m _ { 2 } ( \{ \hat { y } _ { 2 } ^ { \parallel } \} = \delta _ { r } \sigma } \\ { m _ { 2 } ( \{ \hat { y } _ { 2 } ^ { \parallel } \} ) = \delta _ { r } \sigma } \\ { m _ { 2 } ( \{ \hat { y } _ { 2 } ^ { \parallel } \} ) = \delta _ { r } \sigma } \end{array} ) = b } \\ { m _ { 2 } , } \\ { ( \{ \begin{array} { l } { m _ { 2 } ( \{ \hat { y } _ { 1 } ^ { \parallel } \} = \delta _ { \sigma } } \\ { m _ { 2 } ( \{ \hat { y } _ { 2 } ^ { \parallel } \} ) = \delta _ { r } \sigma } \\ { m _ { 2 } ( \{ \hat { y } _ { 2 } ^ { \parallel } \} ) = \delta _ { \sigma } ( 1 - \sigma ) } \\ { m _ { 2 } ( \Omega ) = 1 - \delta _ { r } } \end{array} \} } \end{array} ) = c  \end{array}
$$

其中： $\delta _ { p }$ 、 $\delta _ { b }$ 、 $\delta _ { c }$ 为置信因子； $\sigma$ 为摄像头的准确度。

雷达目标检测是初步的运动目标检测。为了获得目标的类别，使用雷达检测的目标相对速度，基于式(6)作计算雷达传感器的基本信度分配 $m _ { 3 }$ 。

$$
m _ { 3 } ( A ) = \{ \begin{array} { l l } { m _ { 3 } ( \Omega ) = \varsigma } \\ { m _ { 3 } ( \{ p , b \} ) = 1 - \varsigma ) \Rightarrow { \nu _ { t } } < { \nu _ { s } } } \\ { m _ { 3 } ( \Omega ) = 1 - \tau } \\ { m _ { 3 } ( \{ b , c \} ) = \tau ) \Rightarrow { \nu _ { t } } > { \nu _ { s } } } \end{array} 
$$

其中： $\nu _ { s }$ 为速度阈值，通过对市区机动车最慢速度进行统计学估计得到； $\nu _ { t }$ 为目标速度； $\zeta , \ \tau$ 为特定分类的置信因子。

# 2.3目标跟踪

在对每个传感器的输入进行移动目标检测并定义复合对象表示后，就可以进行融合目标检测和跟踪。本文提出一种检测级多传感器融合框架，并通过定义额外的检测模块获得更多的证据来源。

当使用多个信号源的证据时，需要确定每个传感器(证据来源)的检测列表与哪个检测目标是关联关系。由于通过检测级的信息组合可以较少传感器测量或分类模块产生的错误、不确定、不完整，以及信息冲突带来的不利影响，所以多信号源检测可以有效提高检测结果的可靠性。

考虑 $S _ { 1 }$ 和 $S _ { 2 }$ 两个证据来源，每个来源都提供了一个检测列表，分别为 $A = \left\{ a _ { 1 } , a _ { 2 } , . . . , a _ { m } \right\}$ 和 $B = \left\{ b _ { 1 } , b _ { 2 } , . . . , b _ { n } \right\}$ ，每个元素表示 $a _ { i }$ 和 $b _ { j }$ 的关联证据 $m _ { a _ { i } , b _ { j } }$ 。为了将这些不同来源的信息结合起来，需要找到表 $A$ 和 $B$ 中检测数据间的关系 $\left| A \times B \right|$ ，其中

$$
i \leq \mid A \mid , j \leq \mid B \mid
$$

根据 $a _ { i }$ 和 $b _ { j }$ 可能的关系 $P \big ( a _ { i } , b _ { j } \big )$ ，定义：1代表 $a _ { i }$ 和 $b _ { j }$ 是相同的对象；0代表 $a _ { i }$ 和 $b _ { j }$ 是不同的对象； $\Phi$ 代表 $a _ { i }$ 与 $b _ { j }$ 间关系未知； $\Lambda = \{ 1 , 0 \}$ 为表示上述命题的识别框架。

$m _ { a _ { i } , b _ { j } } \left( \left\{ 1 \right\} \right) , m _ { a _ { i } , b _ { j } } \left( \left\{ 0 \right\} \right)$ 是证据的量化，分别表示支持命题 $P \big ( a _ { i } , b _ { j } \big ) = 1$ 和 $P \big ( a _ { i } , b _ { j } \big ) = 0$ ，而 $m _ { a _ { i } , b _ { j } } \left( \{ 1 , 0 \} \right)$ 表示未知，即证据不能支持其他的命题。通过寻找 $A$ 与 $B$ 中检测目标的相似性度量来描述这些命题。

传感器 $S _ { \mathrm { 1 } }$ 和 $S _ { 2 }$ 可以提供不同类型的，基于位置、形状或外观的信息来表示的检测。能够编码所有这些检测信息的相似度 $m _ { a _ { i } , b _ { j } }$ 表示为

$$
\begin{array} { r l } & { m _ { a _ { i } , b _ { j } } \left( \left\{ 1 \right\} \right) = \theta _ { i , j } } \\ & { m _ { a _ { i } , b _ { j } } \left( \left\{ 0 \right\} \right) = \psi _ { i , j } } \\ & { m _ { a _ { i } , b _ { j } } \left( \left\{ 1 , 0 \right\} \right) = 1 - \theta _ { i , j } - \psi _ { i , j } } \end{array}
$$

其中： $\alpha _ { i , j }$ 和 $\beta _ { i , j }$ 是证据的量化，用于检测 $a _ { i }$ 和 $b _ { j }$ 支持 $\Lambda$ 中的某一命题。

定义 $m _ { a _ { i } , b _ { j } } ^ { p }$ 是不同传感器检测的位置相似度的证据度量;$m _ { a _ { i } , b _ { j } } ^ { c }$ 是外观相似度的证据度量，用来表示来源于不同检测 $a _ { i }$ （20和 $b _ { j }$ 根据位置和分类信息的相似度的证据，采用式(2)定义的组合规则，可得到

$$
\left\{ \begin{array} { l } { { \displaystyle m _ { a _ { i } , b _ { j } } \left( A \right) = \sum _ { B \cap C = A } m _ { a _ { i } , b _ { j } } ^ { p } \left( B \right) m _ { a _ { i } , b _ { j } } ^ { c } \left( C \right) } } \\ { { \displaystyle m _ { a _ { i } , b _ { j } } \left( \left\{ \Lambda \right\} \right) = m _ { a _ { i } , b _ { j } } ^ { \ast } \left( \left\{ \Lambda \right\} \right) + \sum _ { B \cap C = Q } m _ { a _ { i } , b _ { j } } ^ { p } \left( B \right) m _ { a _ { i } , b _ { j } } ^ { c } \left( C \right) } } \end{array} \right.
$$

通过构建矩阵 $M _ { _ { A , B } }$ ，可以分析每个元素的证据分布 $m _ { a _ { i } , b _ { j } }$ ，从而决定两个元素间有关联 $m _ { a _ { i } , b _ { j } } \left( \{ 1 \} \right)$ 、无关联 $m _ { a _ { i } , b _ { j } } \left( \left\{ 0 \right\} \right)$ ，或是由于噪声而无法确定关联 $m _ { a _ { i } , b _ { j } } \left( \{ 1 , 0 \} \right)$ 。

需要注意的是，传感器提供的信息数量和类型不一定是相同的。例如，雷达数据不包括目标形状的信息，激光雷达数据则提供关于目标位置和形状的信息。如果两个相关联的检测具有信息互补性，则它们会直接生成融合对象；如果两个相关联的检测信息是冗余的，那么它们会根据类型进行组合。对于位置信息，基于贝叶斯融合方法对两个检检测的协方差信息进行数据整合。对于形状信息，通常依赖于激光雷达检测，并利用式(2)所述的证据组合规则来获取。

1）位置信息相似度提取

根据 $a _ { i }$ 和 $b _ { j }$ 两种检测的位置信息，可以编码相似性证据（204号 $m _ { a _ { i } , b _ { j } } ^ { p }$ 。基于检测的位置信息，定义满足伪距离度量性质的距离函数 $d _ { a _ { i } , b _ { j } }$ 。由于马氏距离可以用来表示距离间的相关性，所以使用马氏距离作为距离度量。

较小的 $m _ { a _ { i } , b _ { j } } ^ { p }$ 表示 $a _ { i }$ 和 $b _ { j }$ 是相同的目标，而较大值则相反。所有属于识别框架 $\Lambda$ 的命题 $m _ { a _ { i } , b _ { j } } ^ { p }$ 的表达式为

$$
\left\{ \begin{array} { l } { m _ { a _ { i } , b _ { j } } ^ { p } \left( \left\{ 1 \right\} \right) = \omega \left( 1 + \mathrm { e } ^ { - d _ { a _ { i } , b _ { j } } } \right) } \\ { m _ { a _ { i } , b _ { j } } ^ { p } \left( \left\{ 0 \right\} \right) = \omega \left[ 1 - \left( 1 + \mathrm { e } ^ { - d _ { a _ { i } , b _ { j } } } \right) \right] } \\ { m _ { a _ { i } , b _ { j } } ^ { p } \left( \left\{ 1 , 0 \right\} \right) = 1 - \omega } \end{array} \right.
$$

其中： $\omega \in [ 0 , 1 ]$ 为证据折减因子。

2）分类信息相似度提取

分类并没有提供直接的证据支持命题 $P \big ( a _ { i } , b _ { j } \big ) = 1$ ，即使两个检测被识别为相同类别，也不能断定它们是同一个对象。原因在于在同一驾驶场景中，两个不同的对象可能属于同一类别。然而，如果两个检测属于不同类，那么它们很有可能属于不同的对象。因此，利用分类信息作为检测间的差异性证据 $m _ { a _ { i } , b _ { j } } ^ { c }$ 。由此，可得证据从 $\Omega$ 变换到 $\Lambda$ 中的方法：

$$
\left\{ \begin{array} { l l } { m _ { a _ { i } , b _ { j } } ^ { c } \left( \left\{ 1 \right\} \right) = 0 } \\ { m _ { a _ { i } , b _ { j } } ^ { c } \left( \left\{ 0 \right\} \right) = \displaystyle \prod _ { A \cap B = \emptyset } m _ { a _ { i } } ^ { c } \left( A \right) m _ { b _ { j } } ^ { c } \left( B \right) } \\ { m _ { a _ { i } , b _ { j } } ^ { c } \left( \left\{ 1 , 0 \right\} \right) = 1 - m _ { a _ { i } , b _ { j } } ^ { c } \left( \left\{ 0 \right\} \right) } \end{array} \right.
$$

其中： $m _ { a _ { i } } ^ { c }$ 和 $m _ { b _ { j } } ^ { c }$ 分别表示检测列表 $A$ 和 $B$ 中的分类假设。

式(10)表明，检测列表 $A$ 和 $B$ 中分类不同的大量信息可以被融合。

在使用融合算法产生的组合目标检测列表的基础上，进一步提出一种基于复合表示的滑动时间窗内最优轨迹估计方法：通过将产生的目标输入到一个考虑到所有对象动态模型、传感器模型中，并利用每个目标检测的分类证据分布，在只考虑具有重要证据的搜索空间内，可以实现所有的可能临近假设的精确检索。如果两个目标具有相同的类别属性，那么它们的分类就是相似的。

# 3实验分析与对比

为了验证所提方法的有效性，在一辆安装有雷达、激光雷达和摄像头的演示车上获得多种驾驶场景下的数据集，并进行相关实验。为了实现连续检测功能，在演示车上配备了处理单元、驾驶员交互组件以及前置传感器。摄像头用于采集黑白图像，其视场角为 $\pm 1 5 ^ { \circ }$ ；中程雷达提供有关移动目标的信息，最大探测距离为 $1 0 0 \mathrm { ~ m ~ }$ ，最大测量速度可达 $2 0 0 ~ \mathrm { k m / h }$ ，视场角为$\pm 8 ^ { \circ } \sim \pm 4 ^ { \circ }$ (近距离中等范围)，角度测量精度为 $0 . 3 ^ { \circ }$ ；激光雷达提供特征点二维列表，其最大测量范围为 $1 6 0 \mathrm { ~ m ~ }$ ，角度测量精度为 $0 . 1 5 ^ { \circ }$ ，距离测量精度为 $6 \mathrm { c m }$ ，视场角为 $9 0 ^ { \circ }$ 。图1为实验所采用的多传感器感知系统。可以从激光雷达和雷达传感器中获得移动目标的运动学信息和外观信息，并从摄像头中获取移动目标的外观信息。

由于感知系统可以为智能汽车带来持续驾驶支持、碰撞预判等功能，所以所提算法的目标是提高感知系统在目标检测和分类中的效率。图1展示了所提方法的原理，以及检测和分类模块之间的交互。融合模块的输入是从三个传感器检测到的三个对象列表：激光雷达，雷达和摄像机，每个待检测对象都是由其位置、大小和分类证据进行表示的。激光雷达和雷达数据用于实现移动物体的检测，并与图像数据相结合，共同对目标进行分类。复合对象描述的三个列表由所提融合方法生成并执行跟踪算法。融合方法的最终输出由一个目标检测列表构成，该列表用于估计移动目标的状态，产生最终的MODT解决方案的输出。

![](images/fb415e8158cb1c95ac1e0e269122a1793fdf04b2171493f2868c496ccd748a51.jpg)  
图1多传感器系统

通过配置的三个传感器，实验中从实际场景收集了三组数据，其中两组来自市区，另外一组来自高速公路。为了获得明确的参考，各组数据都经过手动标注。此外，为了验证所提方法在检测级和跟踪级的融合性能，将所提方法与文献[20]中的方法进行了比较。

在提出的MODT解决方案中，传感器数据融合操作位于检测级，首先在激光雷达传感器的测量中使用第1章提出的SLM方法检测可能的移动对象，根据检测到的二维位置状态，为每个证据类的分布定义识别框架 $\Omega = \{ p , b , c \}$ ，在每次检测中，所有可能的分类假设的个数为 $2 ^ { \Omega }$ ；其次，根据第2和3章所提出的方法，提取激光雷达、雷达以及摄像头检测的数据，从而获取待检测移动目标的表达；最后，在获得目标表达后，在检测级基于第4章的方法对表达进行融合，并根据融合列表对目标进行跟踪。

图2、3给出了市区可高速公路的场景两组基于所提方法的检测结果。由于这两种场景的车辆周围都有大量的移动对象，所以这两个场景都属于高交通流量场景。子图(a)为摄像机拍摄的图像及其识别出的移动对象；(b)为同一场景的顶视图，矩形框表示移动的物体，点表示激光雷达检测点，圆圈表示雷达检测点。

在这两组情境中，迎面而来的所有车辆都可以被很好地检测、跟踪和分类，如高速公路场景中的几辆轿车及卡车；市区场景中的轿车、卡车及行人。此外，场景中的障碍物等静态对象也被快速检测和正确识别。由于复合目标表达提供了速度和方向信息，所以移动对象的速度通过基于模型的跟踪模块进行估计。在融合的早期阶段，当移动方向已知时，雷达多普勒速度信息可以有效提高激光雷达估计目标速度的精度。此外，由于三个不同的传感器以分类分布的方式提供了不同的分类假设，进而产生了融合信息，所以可大幅度提高分类准确度。

![](images/33146b120ca31c6e0109404376bc941c97b3830878f1984169eeb4a6cce40c58.jpg)

![](images/7f7e07efcadd7f56055c54be9dbf708daee3177ec72fa83bfca43fdbcc7fe0c2.jpg)  
图2场景1实验结果

图3场景2实验结果

表1、2为所提算法在检测级的融合算法与文献[20]中提出的算法的比较结果。使用三组数据集进行实验，其中两组来自高速公路场景，另外一组来自市区场景。从实验结果可以看出，对于高速公路场景，检测级融合对于跟踪级融合并没有明显改进。然而在高速的情况下碎玉确定移动车辆是十分重要的。因此，提出的算法对于持续支持系统的实际应用是十分必要的。市区路况为现代车辆的准确预测提出了挑战，而相对于跟踪级融合，在市区中的检测级融合识别效果提升十分明显。这是由于检测级融合通过丰富的传感器监测和数据关联可以更早的检测到移动车辆。

表1b类和c类的误分类数  

<html><body><table><tr><td rowspan="2">数据集</td><td rowspan="2">移动对象数量</td><td colspan="2">车辆误分类数量与比值</td></tr><tr><td>文献[20]</td><td>本文方法</td></tr><tr><td rowspan="2">高速场景1</td><td rowspan="2">164</td><td>25</td><td>9</td></tr><tr><td>15.2%</td><td>5.5%</td></tr><tr><td rowspan="2">高速场景2</td><td rowspan="2">125</td><td>13</td><td>5</td></tr><tr><td>10.4%</td><td>4%</td></tr><tr><td rowspan="2">市区场景</td><td rowspan="2">207</td><td>32</td><td>7</td></tr><tr><td>15.4%</td><td>3.4</td></tr><tr><td></td><td>表2p和c类的误分类数</td><td></td><td></td></tr><tr><td rowspan="2">数据集</td><td rowspan="2">移动对象数量</td><td>行人误分类数量与比值</td><td></td></tr><tr><td>文献[20]</td><td>本文方法</td></tr><tr><td rowspan="2">市区场景</td><td rowspan="2">85</td><td>21</td><td>7</td></tr><tr><td>24.7%</td><td>8.2%</td></tr></table></body></html>

对于行人分类的结果，提出方法获得了和车辆检测相似的分类性能提升。然而激光雷达检测到的小移动目标并不能被识别为行人，这一问题可以通过早期融合雷达和图像数据加以解决。此外，与文献[20]相比，提出的方法对移动目标的分类需要更少的平均传感器扫描次数。这是由于在早期知识整合中探测目标的分类信息主要集中于 $m _ { a } ^ { c }$ 和 $m _ { b } ^ { c }$ 中，而这些值与简化后的形状和运动模型空间直接相关。

为了进一步验证所提方法的有效性，在城区、郊区、赛道三种路况下对所提方法和文献[20]中的方法进行了对比实验，实验数据如表3所示，实验结果如表4、5所示。

表3城区、郊区、赛道三种场景的待检测目标数量  

<html><body><table><tr><td colspan="2"></td><td colspan="3">总待测对象数</td></tr><tr><td colspan="2">场景</td><td>P</td><td>b</td><td>C</td></tr><tr><td colspan="2">城区</td><td>42</td><td>3</td><td>287</td></tr><tr><td colspan="2">郊区</td><td>18</td><td>1</td><td>55</td></tr><tr><td colspan="2">赛道</td><td>102</td><td>0</td><td>215</td></tr><tr><td colspan="2">表4</td><td colspan="3">所提方法在城区、郊区、赛道三种场景的实验结果</td></tr><tr><td rowspan="3">场景</td><td colspan="2">分类</td><td colspan="3"></td></tr><tr><td colspan="2">正确</td><td colspan="3">错误</td></tr><tr><td>p</td><td>b</td><td>C P</td><td>b</td><td>C</td></tr><tr><td rowspan="2">城区</td><td>35</td><td>2</td><td>262</td><td>7 1</td><td>25</td></tr><tr><td>83.3%</td><td>66.7%</td><td>91.3% 16.7%</td><td>33.3%</td><td>8.7%</td></tr><tr><td rowspan="2">郊区</td><td>17</td><td>1</td><td>48 1</td><td>0</td><td>7</td></tr><tr><td>94.4%</td><td>100%</td><td>87.3% 5.6%</td><td>0</td><td>12.7%</td></tr><tr><td rowspan="2">赛道</td><td>100</td><td>/</td><td>211</td><td>2 /</td><td>4</td></tr><tr><td>98%</td><td>/</td><td>98.1% 2%</td><td>/</td><td>1.9%</td></tr></table></body></html>

表5文献[20]的方法在城区、郊区、赛道三种场景的实验结果  

<html><body><table><tr><td rowspan="2">场景</td><td colspan="6">分类</td></tr><tr><td></td><td>正确</td><td></td><td></td><td>错误</td><td></td></tr><tr><td rowspan="2">城区</td><td>P</td><td>b</td><td>C</td><td>P</td><td>b</td><td>c</td></tr><tr><td>35</td><td>2</td><td>262</td><td>7</td><td>1</td><td>25</td></tr><tr><td rowspan="2">郊区</td><td>72.5%</td><td>51.8%</td><td>80.3%</td><td>27.5%</td><td>48.2%</td><td>19.7%</td></tr><tr><td>17</td><td>1</td><td>48</td><td>1</td><td>0</td><td>7</td></tr><tr><td rowspan="2">赛道</td><td>83.8%</td><td>91.4%</td><td>78.8%</td><td>16.2%</td><td>8.6%</td><td>21.2%</td></tr><tr><td>100</td><td>/</td><td>211</td><td>2</td><td>/</td><td>4</td></tr><tr><td></td><td>80.5%</td><td>/</td><td>83.1%</td><td>19.5%</td><td>/</td><td>16.9%</td></tr></table></body></html>

分类正确表示被正确分类的移动对象，分类错误表示被错误分类的移动对象。为了清楚起见，正确和错误的分类数量由百分数表示。三种移动目标被纳入考虑对象，分别为行人(p)、卡车(b)和轿车(c)。由表3\~5及相关数据可知，与文献[20]中的方法相比，提出算法的运行时间平均计算时间为 $3 0 ~ \mathrm { { m s } }$ ，完全可以满足实时平台的处理时间要求 $( 7 5 ~ \mathrm { m s } )$ ，即所提算法的动态响应速度完全满足实时处理要求。此外，所提算法的准确度也明显高于文献[20]中的方法。

在城区场景中，考虑到移动目标数目较多，界存在环境嘈杂等干扰，车辆检测和分类的正确率依然很高，但仍然存在一定的误检率。这主要是因为在高度动态和高交通流的环境中，传感器视野被迫缩小。此外，行人错分率较高的原因在于所提方法会将交通海报误判为行人。这些错误分类说明，该系统需要构建更具鲁棒性的视觉分类系统，或者提炼出更具描述能力视觉符号。不可否认，为了有效提高算法的鲁棒性，不仅需要对实验环境进行一定的选择和规划（即目前算法在相对简单的环境中错分率较低），也需要同时增强图像采集系统的灵敏度和准确率（即在算法的输入端提高输入图像的准确度）。

在郊区场景中，所提方法的处理时间小于 $2 0 ~ \mathrm { { m s } }$ ，且分类正确率均比较高，这是因为郊区场景中待测移动目标的数量较少，且环境干扰较少，便于算法充分发挥分类功能。

在赛道场景中，由于只有少数行人和车辆存在，行人和车辆的检测和识别率是近乎完美 $( 9 8 \% \sim 1 0 0 \%$ )。这一场景并不包含一些常见的驾驶情况，如多个移动物体和动态高流量等。

# 4结束语

针对智能车辆中的移动目标检测与分类，在回顾已有方法优缺点的基础上，利用分类信息作为复合对象数学模型的关键成分，这使得在检测、分类、跟踪移动目标时，可以充分融合运动信息和外观信息。进一步分析了检测级多传感器融合产生的复合对象描述，并根据激光雷达、雷达和摄像头三种主要传感器来定义、研究、测试和评估提出的融合算法。最后，将提出的完全感知方法在某实验车辆上进行了实验分析。实验结果表明，提出的检测级整合分类信息使得融合过程能够充分考虑被检测目标的证据分布，从而大幅度改进检测精度。

目前，对多传感器融合方法的研究正在逐渐深入，通过对所提方法进行合理拓展，可以设计出一种整合传感器运动感知的系统分类方法，可以使设备的计算核心在与环境进行交互时，

具备学习表达和运动控制功能。

# 参考文献：

[1]吴黎兵，范静，聂雷，等．一种车联网环境下的城市车辆协同选路方法 [J].计算机学报,2017,40(7):1600-1613.(Wu Libing,Fan Jing,Nie Lei, et al. An urban vehicle cooperative routing method under the environment of vehicle interconnection [J]. Acta Computer Science,2017,40 (7): 1600-1613. )   
[2]韩飞龙，应捷，朱丹丹．一种新的车辆辅助驾驶动态障碍物检测与分类 方法[J].计算机应用研究,2017,34(6):1909-1912.(Han Feilong,Ying Jie,Zhu Dandan.A new vehicle aided driving dynamic obstacle detection and classification method [J].Application Research of Computers,2017, 34 (6): 1909-1912.)   
[3]陈存铜，赵君峤，叶晨，等．基于共享内存的智能无人车进程间消息异 步传输机制[J]．软件学报，2017，28(5):1315-1325.(Chen Cuntong, Zhao Jun,Ye Chen,et al.Asynchronous transmission mechanism of inter process messages for intelligent unmanned vehicles based on shared memory[J]. Journal of Software,2017,28 (5): 1315-1325.)   
[4]ZhuHao,YuenKV,Mihaylova L，etal.Overview of environment perceptionforintellgent vehicles[J].IEEETranson Intelligent Transportation Systems,2017,32(9):1-18.   
[5]OuSheng，Kang Hengbin.Object detection and classification by decision-level fusion for inteligent vehicle systems [J]. Sensors,2017,17 (1): 207-218.   
[6]李彦，何琳，帅长庚，等．船舶机械低频线谱振动传递的主动控制[J]. 船舶力学,2015,19(12):1549-1563.(LiYan,HeLin,Shuai Changeng, et al.Active control of low-frequency sinusoidal vibration transmission of ship machinery[J].Journal of Ship Mechanics,2015,19 (12):1549-1563.)   
[7]Wang Xing,Zhang Chun,Liu Feng,etal.Exponentiallyweighted particle filter for simultaneous localization and mapping based on magnetic field measurements [J]. IEEE Trans on Instrumentation & Measurement, 2017, 66 (7): 1658-1667.   
[8]易群，李彩丽．机械振动主动控制技术的研究现状和发展趋势[J].机械 工程与自动化,2016,15 (3): 220-221. (Yi Qun,Li Caili. Research status and development trend of active control technology of mechanical vibration [J].Mechanical Engineering& Automation,2016,15(3): 220-221. )   
[9] Varanis M, Silva AL,Mereles A. On mechanical vibration analysis of a multi degree of freedom system based on arduino and MEMS accelerometers [J].Revista Brasileira De Ensino De Fisica,2O17,40(1): 25-32.   
[10]吴勇，关胜晓．基于无迹卡尔曼滤波器的改进SLAM问题求解方法[J]. 计算机系统应用，2017,26(3):30-36.(Wu Yong，Guan Shengxiao. Improved SLAM problem solving method based on unscented calman filter [J].Computer System Application,2017,26 (3): 30-36.)   
[11]李建坡，穆宝春．基于协同预测的无线传感器网络全移动节点定位算 法[J]．计算机应用研究,2017,34(1):186-188.(Li Jianpo,Mu Baochun. Based on collaborative prediction algorithm for all mobile nodes localization in wireless sensor networks [J].Application Research of Computers,2017,34(1):186-188.)   
[12]刘洋，杨超．多传感器基于动态时空特性软硬协作决策的目标检测研 究[J].计算机应用研究,2016,33(2):447-449.(Liu Yang，Yang Chao. Multi-sensor based on dynamic spatial and temporal characteristics of soft and hard collaborative decision making target detection research [J]. Application Research of Computers,2016,33 (2): 447-449.)   
[13] Martynowicz P. Study of vibration control using laboratory test rig of wind turbine tower-nacelle system with MR damper based tuned vibration absorber [J].Bulletin of the Polish Academy of Sciences Technical Sciences,2016,64(2):347-359.   
[14] Zhang Shengqi，Yue Xihong，Wang Zhengxue,et al.Active vibration control of a piezoelectric bonded smart cantilever beam using fuzzy logic [J]. Zhendong Gongcheng Xuebao//Journal of Vibration Engineering,2017, 30 (1): 110-117.   
[15] GarciaF,MartinD,Escalera ADL,et al. Sensor fusion methodology for vehicle detection [J]. IEEE Intelligent Transportation Systems Magazine, 2017,9 (1): 123-133.   
[16]赵伟．基于DWT 和随机森林的运动自动分类方法[J].湘潭大学自然 科学学报，2018，40(1):107-110.(Zhao Wei．Automatic motion classification method based on DWT and random forest [J]. Journal of Natural Science,Xiangtan University,2018,40(1):107-110.)   
[17] Zhao Li,He Zhen,Cao Wei,et al. Real-time moving object segmentation and classification from HEVC compressed surveillance video [J].IEEE Trans on Circuits& Systems for Video Technology,2017,32(9):14-21.   
[18]柯辉，王晓慧，张建军，等．一种三自由度支链嵌套并联机器人末端残 余振动的主动抑制[J]．中国机械工程，2016，27(12):1648-1655.(Ke Hui,Wang Xiaohui, Zhang Jianjun,et al.Active suppression for terminal residual vibration of a 3-DOF parallel robot with limbs of structures [J]. China Mechanical Engineering,2016,27(12):1648-1655.)   
[19]Yi Wen,Jiang Min,Hoseinnezhad R,et al.Distributed multi-sensor fusion using generalised multi-Bernoulli densities [J].IET Radar Sonar & Navigation,2017,11 (3): 434-443.   
[20]Xie Huan,Pu Jinlong.Research on information fusion method of multi-sensor based on dempster-shafer evidence theory [J].Electro-Optic Technology Application,2017,26 (4): 562-570.   
[21] Proenca H,Neves JC.Deep-PRWIS:periocular recognition without the iris and sclera using deep learning frameworks [J]．IEEE Trans on Information Forensics& Security,2017,34(9): 34-42.