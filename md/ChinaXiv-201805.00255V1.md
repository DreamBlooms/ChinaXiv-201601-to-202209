# 基于分类和模糊滤波的×光图像椒盐噪声滤除算法

袁桂霞‘，周先春²

(1.江苏开放大学 信息与机电工程学院，南京 210017；南京信息工程大学 电子与信息工程学院，南京 210044)

摘要：为了解决当前椒盐噪声滤除算法对X光图像滤除效果不佳且运算效率不高的问题，提出了一种融合多级分类和自适应模糊滤波的椒盐噪声滤除方法，主要包括像素点多级分类和自适应模糊滤波两个部分。在像素点多级分类阶段，先结合先验知识设计快速的一级粗分类，将像素点分为椒盐噪声、信号和可疑噪声三类。对于可疑噪声，再提取区域内的直方图分布特征，设计 BP神经网络分类器进行精确分类，最终将图像中的所有像素点分为信号和椒盐噪声两类。在自适应模糊滤波阶段，针对三种模糊集合分别创建模糊隶属度函数，计算模糊隶属度值，通过模糊加权求和恢复像素点亮度。实验结果表明，所提方法的像素点分类正确率高，滤波后图像的峰值信噪比高，平均滤波耗时少。

关键词：椒盐噪声；滤波；神经网络；隶属度；模糊滤波 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.07.0892

# Salt and pepper noise filtering algorithm for X-ray images with multi-level classification and fuzzy filtering

Yuan Guixia1, Zhou Xianchun² (1.Schoolofformation&MechanicalElectricalEnineeringJangsuOpenUniversityNanjingol7,China;2.oolof Electronic&InformationEnginering,Nanjing UniversityofInformationScience&Technology,Nanjing10044,China)

Abstract: Inordertosolve theproblemthatecurentsaltandpeppernoisefilteringalgorithmsforX-rayimagesare ineffective andlow eficiency,this paper proposed asalt and pepper fitering algorithm with multi-levelclassificationand adaptive fuzzy fltering,which included twoparts:pixels’multi-levelclasificationandadaptivefuzzyfilterng.Intheprocessofmulti-level classification,itdsignedarapidroughclasificationaccording toprioriknowledge,todividethepixelsintothreecategories: salt and pepper noise,signalandsuspicious noise.For thesuspicious noise,it extracted the histogram distribution features in theregion,anddesignedtheBneuralnetworkclasifiertoclassfythepixels,andfinallylassiedallthepixelsinteimage intotwo kindsofsignalandsaltandpeppernoise.Intheprocess ofadaptivefuzyfiltering,itcreatedfuzzymembershipfunction forthree fuzzysets,and calculated fuzzy membership value,andrestored pixel brightnessby fuzzy weighted summing.The experimentalresultsshowthatthenewmethodhashighaccuracyofpixelclasification,highpeak signaltonoiseratiooffiltered image,and less average time-consuming of filtering.

Key Words: salt and pepper noise; filtering; neural network; membership degree; fuzzy filtering

# 0 引言

椒盐噪声是数字图像采集或者传输过程中引入的一种常见噪声，呈黑白杂点分布，对图像的质量影响较大[1。为了滤除图像中存在的椒盐噪声，学者们提出了许多有意义的方法。对于受椒盐噪声污染程度小的图像，通常可以采用标准中值滤波、极值中值滤波、递归开关中值滤波等方法。这些方法的复杂度较低，运算效率高，但是对于受椒盐噪声污染程度稍大的图像，滤波效果不佳，而且可能造成图像模糊[2-6]。在滤波过程中，为了保护图像的细节信息，有学者提出先对图像中的像素点进行分类，区分信号和椒盐噪声，然后针对不同属性的像素点设计不同的滤波方法，从而保证在滤除噪声的同时不破坏原有信号[7\~10]。例如文献[7]提出了一种提出一种面向高密度椒盐噪声的图像滤波算法，该方法利用直方图形状特征对像素点进行分类，检测椒盐噪声的位置。采用多方向加权均值滤波方法进行噪声的滤除。文献[8]提出了一种基于模糊转换的加权均值滤波方法来去除图像中的椒盐噪声，主要包含噪声检测和噪声去除两个阶段。在噪声检测阶段，提出了一种相邻处理过点的绝对差分和方法对像素点进行分类。在噪声去除阶段，采用一种距离相关的模糊转换加权均值滤波方法滤除噪声。这两种方法的运算效率都较高，但是像素点分类和噪声滤除效果的适应性不强，对于X光图像等灰度层次不丰富的图像噪声滤除效果欠佳。为提高像素分类正确率，文献[9]提取了图像的预测误差、核均值等多个特征，并采用支持向量机方法进行学习和分类，可以实现像素点的精确分类。针对不同类别的像素点，设计了自适应的滤波方法，可以有效去除椒盐噪声。文献[10]提出了一种基于支持向量机椒盐噪声去除方法，通过分类运算识别噪声像素，通过回归运算滤除噪声。这两种方法在像素点分类方面性能提高明显，滤波效果也有较大提高，但运算效率偏低。

为了兼顾滤波效果和运算效率，本文提出了一种融合像素点多级分类和自适应模糊滤波的椒盐噪声滤除方法。该方法的主要创新在于两个方面，一是在像素点多级分类阶段，为了提高运算效率，本文设计了一种快速的一级粗分类步骤，结合先验知识区分明显的椒盐噪声和信号，对于不易区分的可疑噪声，采用机器学习方法进行精确分类，提高分类正确率；二是在自适应模糊滤波阶段，通过三种模糊集合的模糊隶属度加权求和，自适应恢复像素点亮度，滤波效果好。

# 1 椒盐噪声模型

椒盐噪声模型是由两个固定的脉冲模型构成的，一类脉冲噪声的值很大，在256级灰度图像中脉冲噪声的灰度值达到最大值255，通常称此类噪声为"盐"噪声；另一类脉冲噪声的值很小，在256级灰度图像中脉冲噪声的灰度值达到最小值0，通常称此类噪声为"胡椒"噪声。令 ${ \boldsymbol { p } } _ { 1 }$ 表示在图像中“胡椒"噪声的出现概率， $p _ { 2 }$ 表示在图像中“盐"噪声的出现概率，那么图像中椒盐噪声的出现概率为 ${ p } _ { 1 } + { p } _ { 2 }$ 。在椒盐噪声模型中，用""表示“胡椒"噪声，因为其值最低（如 $l = 0$ )，用"h"表示"盐"噪声，所以其值最高（如 $h = 2 5 5$ )。令 $\tilde { x } _ { i }$ 表示受椒盐噪声污染的图像中的第 $i$ 个像素的灰度值，那么椒盐噪声模型[9可以表示为

$$
\tilde { x } _ { i } = \left\{ \begin{array} { r l } { l } & { , \mathrm { H B } \mathrm { H } \frac { - 2 \mathrm { e } } { 2 \mathrm { e } } \mathcal { H } p _ { 1 } } \\ { h } & { , \mathrm { H B } \mathrm { H } \frac { - 2 \mathrm { e } } { 2 \mathrm { e } } \mathcal { H } p _ { 2 } } \\ { x _ { i } } & { , \mathrm { H B } \mathrm { H } \frac { - 2 \mathrm { e } } { 2 \mathrm { e } } \mathcal { H } p _ { 3 } } \end{array} \right.
$$

其中： $p _ { 3 } = 1 - p _ { 1 } - p _ { 2 }$ ， $x _ { i }$ 是像素点的真实像素值，也即受椒盐噪声污染之前的像素值。

图1为图像受椒盐噪声污染的示例。其中，图1(a)为原始的胸部 X 光图像，(b)为原始图像受 $10 \%$ 噪声污染的图像，(c)为原始图像受 $20 \%$ 噪声污染的图像，(d)为原始图像受 $30 \%$ 噪声污染的图像，(e)为原始图像受 $40 \%$ 噪声污染的图像，(f)为原始图像受 $50 \%$ 噪声污染的图像。可见，椒盐噪声在图像中以黑色或白色杂点的形式出现，当噪声污染程度较小时，可以看到图像中大部分像素点的真实灰度值得以保留；但当噪声污染程度较大时，图像中大部分像素的真实亮度被椒盐噪声填充。

# 2 本文方法

# 2.1算法框架

为了滤除椒盐噪声，增强X光图像质量，本文设计了一种融合多级分类和自适应模糊滤波的椒盐噪声滤除方法，实现流程如图2所示。该方法主要包括两个部分，首先是对图像中的各个像素点进行分类，判别像素点是真实信号还是椒盐噪声。在分类时，本文综合考虑运算效率和分类性能两个方面的问题，先结合椒盐噪声和真实信号的明显差异进行一次快速的粗分类，粗分类阶段将像素点分为三类：椒盐噪声、信号和可疑噪声。对于属性为可疑噪声的像素点，再提取区域内的直方图分布特征，设计BP神经网络分类器进行精确分类，最终将图像中的所有像素点分为两类：即信号和椒盐噪声。接着，设计一种自适应的模糊滤波方法，针对不同类别的像素点进行不同的滤波处理，目标是在滤除椒盐噪声的同时尽可能保持图像较高的信噪比，避免造成图像模糊。

![](images/436ff1cc5ff587b4d32523c928620c6ec5cc6a348cb6f6f38245bc32cf4dde47.jpg)  
图1受不同程度椒盐噪声污染的图像

# 2.2像素点多级分类

区分图像中的真实信号和椒盐噪声，有助于有针对性地设计自适应的滤波方式，保护真实信号的亮度分布不被破坏。因此，在滤除图像中的椒盐噪声之前，本文先对图像中的所有像素点进行分类，辨别每一个像素点的属性（即信号还是椒盐噪声)。在像素点分类方面，基于学习的方式通常可以取得较高的分类准确度，但时运算效率一般较低。本文为了兼顾像素点分类正确率和运算效率，设计了一种多级分类策略。首先依据受椒盐噪声污染图像的特性设计一级快速的粗分类步骤，区分明显为信号或者椒盐噪声的像素点。然后针对余下那些不易区分的像素点，采用BP神经网络分类器进行精确分类。具体描述如下。

![](images/2baee4ff8a33ddd7422b7edb26ff155da4926166c5b5516235bdd1c8b89b37e1.jpg)  
图2实现流程

（1）一级粗分类

对于受椒盐噪声污染的图像而言，通常存在以下特性：

第一，图像中只有部分像素点受到污染，而其他像素点的亮度保持不变；

第二，椒盐噪声的亮度值处于图像中整体亮度值的两端，也即，要么最大，要么最小。

基于这两个特性，本文设计的一级粗分类步骤为：

Step1：遍历图像中的每一个像素点，统计图像中像素点亮度的最大值和最小值，分别记为 $h$ 和 $l$ ，有

$$
\left\{ \begin{array} { l l } { { l = \operatorname* { m i n } \left( \tilde { x } _ { i } \right) } } \\ { { h = \operatorname* { m a x } \left( \tilde { x } _ { i } \right) } } \end{array} \right.
$$

其中， $\tilde { x } _ { i }$ 表示受污染图像中的第 $i$ 个像素点的亮度值。

Step2：再次遍历图像中的每一个像素点，记 $c ( \widetilde { \boldsymbol { x } } _ { i } )$ 表示第 $i$ 个像素点的属性， $c ( \tilde { x } _ { i } ) { = } 0$ 表示第 $i$ 个像素点为信号， $c ( \tilde { x } _ { i } ) { = } 1$ 表示第 $i$ 个像素点为椒盐噪声， $c ( \tilde { x } _ { i } ) { = } 2$ 表示第 $i$ 个像素点为可疑噪声。这里，粗分类可以细分为两个步骤：

Step2-1：如果当前像素点的亮度值不等于 $h$ 或l，则判定该像素点为信号。

Step2-2：如果当前像素点不是信号点，则统计其邻域像素点的亮度值，如果其邻域像素点的亮度值都不等于当前像素点的亮度值，则判定该像素点为椒盐噪声。

上述两个子步骤可以用公式表示为

$$
\begin{array} { r } { c ( \tilde { x } _ { i } ) = \displaystyle \{ 0 \quad , \tilde { x } _ { i } \neq h \mathrm { H } \tilde { x } _ { i } \neq l \ } \\ { 1 \quad , \ \tilde { x } _ { i } \neq R \{ \tilde { x } _ { i } \} } \end{array}
$$

其中： $R \{ \tilde { x } _ { i } \}$ 表示第 $i$ 个像素点的周围邻域像素点的亮度值集合，本文采用8邻域方式，也即 $R \{ \tilde { x } _ { i } \}$ 表示第i个像素点的周围8邻域内的8像素点的亮度值。

这样，一级粗分类通过简单的统计运算将像素点的类别分为三类：信号、椒盐噪声和可疑噪声。对于可疑噪声，其类别属性还不明确，本文在二级细分类步骤中进行最终划分。

# （2）二级细分类

对于可疑噪声，本文采用机器学习方法进行细分类。首先，提取可疑噪声周围邻域像素点的亮度分布直方图，表示为

$$
H \left\{ \tilde { x } _ { i } \right\} = \frac { n _ { j } } { n } , j = 0 , 1 , \cdots , 2 5 5
$$

其中： $n$ 表示第 $i$ 个可疑噪声周围邻域 $R \{ \tilde { x } _ { i } \}$ 的像素点总数， $n _ { j }$ 表示 $R \{ \tilde { x } _ { i } \}$ 中灰度值为 $j$ 的像素点的数量。本文将该直方图作为第 $i$ 个可疑噪声点的特征向量。

然后，将其送入已经训练好的BP神经网络分类器进行特征分类，输出像素点属性的分类结果。BP神经网络分类器是一种常用的分类器，本文使用三层BP神经网络分类器[II]，输出结果只有两种：0和1。0表示信号，1表示椒盐噪声。BP神经网络分类器可以通过大量样本训练得到，本文采用的训练方法是：

Step1：选择10幅没有污染的X光图像，分别对其添加 $10 \%$ 、$20 \%$ 、 $30 \%$ 、 $40 \%$ 和 $50 \%$ 五种程度的椒盐噪声；

Step2：采用前述的一级粗分类方法将图像中的像素点分为三类，并只保留属性为可疑噪声的像素点；

Step3：对于属性为可疑噪声的像素点，提取邻域 $R \{ \tilde { x } _ { i } \}$ 的亮度分布直方图特征。这里，不统计边界像素点特征。

Step4：对于属性为可疑噪声的像素点，比较该像素点亮度与原图（也即未受椒盐噪声污染的图像）对应像素点的亮度是否相同，如果相同，则标记该像素点的特征向量的标签为0，否则标记该像素点的特征向量的标签为1。

Step5：将特征向量和对应的标签送入三层BP神经网络，学习神经网络的参数，构建BP神经网络分类器。

# 2.3 自适应模糊滤波

前面对图像中的像素点进行了分类，对于分类为信号的像素点，其亮度值在滤波后不变。对于分类为椒盐噪声的像素点，其亮度值采用自适应模糊滤波方法复原。下面详细介绍自适应模糊滤波方法的实现过程。

首先，构建三个模糊集合：Dk、Md和Br。其中，Dk是针对偏暗像素的模糊集合，Br是对偏亮像素的模糊集合，而Md是对中间亮度像素的模糊集合，具体地，

$$
\begin{array}{c} \begin{array} { r l } & { ( \mathrm { D } \mathbf { k } = \{ \widetilde { x } _ { i }  l \leq \widetilde { x } _ { i } < \displaystyle \frac { h + l } { 3 } \}  } \\ & {  \{ \mathrm { M d } = \{ \widetilde { x } _ { i }  \displaystyle \frac { h + l } { 3 } \leq \widetilde { x } _ { i } \leq \displaystyle \frac { 2 ( h + l ) } { 3 } \}  } \\ & {  [ \mathrm { B r } = \{ \widetilde { x } _ { i }  \displaystyle \frac { 2 ( h + l ) } { 3 } < \widetilde { x } _ { i } \leq h \}   } \end{array}   \end{array}
$$

针对这三个模糊集合分别创建模糊隶属度函数。本文采用钟形隶属度函数，定义为

$$
m _ { j } \left( \tilde { x } _ { i } \right) = \left( 1 + \left( \frac { \tilde { x } _ { i } - b _ { j } } { a _ { j } } \right) ^ { 2 } \right) ^ { - 1 } , \tilde { x } _ { i } \in R \left\{ \tilde { x } _ { i } \right\} , j = \mathrm { D k , M d , B r }
$$

其中： $a _ { j }$ 和 $b _ { j }$ 为第 $j$ 个模糊集合的参数，可以依据受污染图像（包括非噪声像素点和噪声像素点）的直方图和噪声像素值来计算。记 $\dot { H } \{ \tilde { x } _ { i } \}$ 表示受污染图像的直方图， $\ddot { H } \{ \tilde { x } _ { i } \}$ 表示图像中噪声像素灰度值分布的直方图，那么模糊直方图可以表示为

$$
\ddot { H } \left\{ \tilde { x } _ { i } \right\} = \frac { \dot { H } \left\{ \tilde { x } _ { i } \right\} - \ddot { H } \left\{ \tilde { x } _ { i } \right\} } { \displaystyle \sum _ { \tilde { x } _ { i } = 0 } ^ { 2 5 } \left( \dot { H } \left\{ \tilde { x } _ { i } \right\} - \ddot { H } \left\{ \tilde { x } _ { i } \right\} \right) }
$$

概率密度函数可以表示为

$$
p _ { j } \left\{ \tilde { x } _ { i } \right\} = \frac { \displaystyle \ddot { H } \left\{ \tilde { x } _ { i } \right\} } { \displaystyle \sum _ { \tilde { x } _ { i } \in j } \ddot { H } \left\{ \tilde { x } _ { i } \right\} } , j = \mathrm { D k , M d , B r }
$$

于是，第 $j$ 个模糊集合的参数可以表示为

$$
\left\{ \begin{array} { l } { \displaystyle \boldsymbol { a } _ { j } = \frac { \sum _ { \widetilde { x } _ { i } \in j } \overleftrightarrow { \boldsymbol { H } } \left\{ \widetilde { x } _ { i } \right\} } { \sum _ { \widetilde { x } _ { i } \in \left[ 0 , 2 5 5 \right] } \overleftrightarrow { \boldsymbol { H } } \left\{ \widetilde { x } _ { i } \right\} } _ { , j = \mathrm { D k , M d , B r } } } \\ { \displaystyle b _ { j } = \sum _ { \widetilde { x } _ { i } \in j } \widetilde { x } _ { i } p _ { j } \left\{ \widetilde { x } _ { i } \right\} } \end{array} \right.
$$

在滤波过程中，将每一个输入像素的灰度值视为一个模糊变量，分别计算该模糊变量对三个模糊集合的隶属度值。输入像素的隶属度可以归一化为

$$
w _ { j } \left( \tilde { x } _ { i } \right) = \frac { \displaystyle \sum _ { \tilde { x } _ { i } \in R \left\{ \tilde { x } _ { i } \right\} } \tilde { x } _ { i } } { \displaystyle \sum _ { \tilde { x } _ { i } \in R \left\{ \tilde { x } _ { i } \right\} } m _ { j } \left( \tilde { x } _ { i } \right) } , j = \mathrm { D k , M d , B r }
$$

对像素点邻域的灰度值进行模糊加权求和，可以表示为

$$
s _ { j } = \sum _ { \tilde { x } _ { i } \in R \left\{ \tilde { x } _ { i } \right\} } w _ { j } \left( \tilde { x } _ { i } \right) \tilde { x } _ { i } , j = \mathrm { D k } , \mathrm { M d } , \mathrm { B r }
$$

对像素点邻域内信号像素点的灰度值求平均，得

$$
\overline { { \boldsymbol { x } } } _ { i } = \frac { \widetilde { \boldsymbol { x } } _ { i } \in R \{ \widetilde { \boldsymbol { x } } _ { i } \} , c \left( \widetilde { \boldsymbol { x } } _ { i } \right) = 0 } { \displaystyle \sum _ { \widetilde { \boldsymbol { x } } _ { i } \in R \left\{ \widetilde { \boldsymbol { x } } _ { i } \right\} } \left( 1 - c \left( \widetilde { \boldsymbol { x } } _ { i } \right) \right) }
$$

那么，采用自适应模糊滤波复原的像素点灰度值可以表示为

$$
x _ { i } = s _ { j } , j = \arg \operatorname* { m i n } _ { j = \mathrm { D k } , \mathrm { M d } , \mathrm { B r } } \left( \left| s _ { j } - \overline { { x } } _ { i } \right| \right)
$$

这样，采用自适应滤波算法，可以根据像素点邻域直方图的灰度分布自适应求解最优的复原结果。

# 3 实验与分析

本文的实验主要从两个方面来评价算法性能。一是对比不同方法对受不同程度椒盐噪声污染的图像的像素点分类正确率；二是对比不同方法对受不同程度椒盐噪声污染的图像进行复原之后的峰值信噪比（PSNR）和滤波耗时。参与对比的方法是近五年性能相对较优的椒盐噪声滤波方法，见文献[7\~10]。

实验1像素点分类正确率对比

对比文献所述方法和本文方法在对受椒盐噪声污染的图像进行滤波之前，都需要先对像素点的属性进行分类。像素点分类的正确率越高，则后续滤波的性能越好。因此，先对不同方法的像素点分类正确率进行评价。为了评价不同方法的鲁棒性，本文选择受不同程度椒盐噪声污染的图像进行实验。如图1所示，选择五幅受椒盐噪声污染的图像，污染程度分别为 $10 \%$ 、$20 \%$ 、 $30 \%$ ， $40 \%$ 和 $50 \%$ 。并对这五幅图像中各个像素点的属性进行标记，方法是：对受污染图像中的任一像素点，比较该像素点亮度与原图（也即未受椒盐噪声污染的图像）对应像素点的亮度是否相同，如果相同，则标记该像素点的属性为信号，否则标记该像素点的属性为椒盐噪声。然后，采用本文方法与四种对比方法分别对五幅图像进行像素点分类，测试像素点分类正确率，也即属性分类正确的信号点和噪声点总数与图像中像素点总数的比值，统计结果如图3所示。由图3可见，本文方法对不同污染程度的图像都能得到最高的像素点分类正确率指标，文献[9]所述方法次之。该方法使用的是多特征融合与支持向量机分类器的方法进行像素点分类，其中多特征融合运算复杂度较高，而且没有像本文这样采用快速的一级粗分类步骤，运算效率偏低，这将在下一个实验中对比测试。文献[10]所述方法尽管也用到了机器学习方法进行分类，但该分类器对小样本的学习能力偏多，当图像受椒盐噪声污染程度超过 $30 \%$ 之后，像素点分类正确率有比较明显的下降。文献[7]和[8]方法的像素点分类正确率明显偏低，尤其是受椒盐噪声污染程度较大时。这是因为此类方法没有采用学习的方式，而设计的经验规则适应能力不强。

![](images/575586c486155fa1044a5d750e6a48c310ff7339021a457010665cbec857eea4.jpg)  
图3像素点分类正确率对比

实验2峰值信噪比和滤波耗时对比

峰值信噪比（PSNR）是反映图像中噪声强度的重要指标，峰值信噪比越大，说明图像受噪声污染的程度小，图像质量越好。图4给出了上述五种方法对受不同程度椒盐噪声污染的图像进行滤波之后图像的PSNR对比情况。由图4可见，本文方法对不同污染程度的图像都能得到最高的PSNR指标，文献[9]所述方法次之，文献[10]所述方法的PSNR指标也较好，但文献[7]和[8]所述方法的PSNR 指标随着椒盐噪声污染程度的增大下降明显。这说明本文方法对受不同程度椒盐噪声污染的图像的滤波效果最好，而且鲁棒性强。

![](images/403fdc920884dc36d7bf5e348ae02a6b94efcf17c0d7256f7cb4b71b75b1a804.jpg)  
图4峰值信噪比对比

为了更直观地对比不同方法的性能，下面对比不同方法的图像滤波结果。限于篇幅，仅给出了五种方法对椒盐噪声污染程度为 $50 \%$ 的X光图像的滤波效果，如图5所示。其中，图5(a)为受污染图像， $( \mathsf { b } \mathord { \sim } \boldsymbol { \mathrm { f } } )$ 分别为文献[7\~10]和本文方法的滤波结果。

![](images/ce89f2a901c665c9fced3edcff94f3e00b71510b14f9807676f490d49df8f024.jpg)  
图5滤波结果对比

由图5可见，主观上评价，本文方法以及文献[9]和[10]所述方法的滤波之后椒盐噪声去除明显，滤波效果明显优于文献[7]和[8]所述方法的滤波效果。仔细对比，可以发现本文方法的滤波结果中残余的椒盐噪声最少，说明本文方法的滤波效果最优。

滤波耗时反映了算法的运算效率，本文在IntelI7CPU、16GB 内存的计算机上进行仿真实验，对比不同方法的滤波耗时。表1给出了对比结果。其中，滤波耗时是指上述五幅图像滤波的平均耗时。由表1可见，本文方法的滤波耗时最少，文献[9]所述方法的滤波耗时最长。其原因从理论上分析如下：

首先，文献[9]和[10]所述方法与本文方法一样都采用了像素点分类步骤。但是本文方法在像素点分类阶段采用多级分类策略，而且第一级分类采用简单的统计运算进行分类，运算效率非常高，而且第一级分类可以区分大部分像素点属性，因此总体而言本文方法在像素点分类阶段所耗时的时间明显下降，整体滤波耗时也得以降低。

其次，本文在滤波阶段采用自适应模糊滤波方法，一次滤波就可以得到最终结果。而文献[7]和[8]所述方法需要通过多次迭代才能得到滤波结果，滤波耗时理论上高于本文方法。

因此，总体而言，本文方法的平均滤波耗时最少，说明本文方法的运算效率最高。

表1滤波耗时对比  

<html><body><table><tr><td>方法</td><td>平均耗时/ms</td></tr><tr><td>文献[7]方法</td><td>17</td></tr><tr><td>文献[8]方法</td><td>13</td></tr><tr><td>文献[9]方法</td><td>37</td></tr><tr><td>文献[10]方法</td><td>29</td></tr><tr><td>本文方法</td><td>11</td></tr></table></body></html>

# 4 结束语

椒盐噪声是图像采集过程时经常会遇到的一种噪声，尤其是在X光成像过程中，椒盐噪声对图像的质量影响较大。本文提出了一种融合多级分类和自适应模糊滤波的椒盐噪声滤除方法，可以有效去除图像中的椒盐噪声，而且对受不同程度椒盐噪声污染的图像的适应能力强。另外，本文方法的运算效率高，可以实时进行图像的滤波处理，实用性强。

# 参考文献：

[1]Zhang P,LiF.A New adaptive weighted mean filter for removing salt-andpepper noise [J].IEEE Signal Processing Letters,2014,21(10): 1280-1283.   
[2]Karthik B,Kumar TK,Dorairangaswamy MA,et al.Removal of high density salt and pepper noise through modified cascaded filter [J]. Middle East Journal of Scientific Research,2014,20 (10): 1222-1228.   
[3]Lu C T, Chou TC.Denoising of salt-and-pepper noise corrupted image using modified directional-weighted-median filter[J].Pattern Recognition Letters,

2012,33(10): 1287-1295.

[4]Esakkirajan S,Veerakumar T,SubramanyamAN,etal.Removal of high density salt and pepper noise through modified decision based unsymmetric trimmed median filter [J]. IEEE Signal Processing Letters,2013,18 (5): 287-290.   
[5]王贵君，杨永强．基于高概率椒盐噪声的模糊滤波器在图像恢复中的 算法设计[J].电子学报,2015,43(1):24-29.   
[6]白中浩，焦英豪，白芳华．基于主动形状模型及模糊推理的驾驶疲劳检 测[J].仪器仪表学报,2015,36(4):768-775.   
[7]江巨浪，章瀚，朱柱，等．高密度椒盐噪声的多方向加权均值滤波[J]. 计算机工程与应用，2016,52(6):204-208.   
[8]王义，王江云，宋晓，等．基于模糊转换的图像椒盐噪声检测和去除

[J]．电子测量与仪器学报,2017,31(4):211-216.

[9]Roy A,Singha J,Devi S S,et al.Impulse noise removal using SVM classification based fuzzy filter from gray scale images [J].Signal Processing,2016,12(8):262-273.   
[10] Gómezmoreno H,Giljiménez P,Lafuentearroyo S,et al.A"salt and pepper"noise reduction scheme for digital images based on support vector machines classification and regression [J]. The scientific world journal, 2014,20 (14): 826405.   
[11] Wu B,Han S,Xiao J,et al.Error compensation based on BP neural network for airborne laser ranging [J].Optik-International Journal for Light and Electron Optics,2016,127(8): 4083-4088.