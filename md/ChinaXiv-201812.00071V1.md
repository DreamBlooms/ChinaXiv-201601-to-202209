# 改进的Gabor小波变换特征提取算法

刘胜昔1，程春玲²

(1.中通服咨询设计研究院有限公司系统集成公司，南京 210019;2.南京邮电大学 计算机学院，南京 210003)

摘要：针对基于Gabor小波幅值与相位的人脸特征提取方法的特征级联方式使得特征向量维度较高的问题，提出了一种改进的Gabor小波变换特征提取算法。该算法计算局部幅值特征和局部相位特征，增强了每个像素的局部关联性；然后通过实验选定加权系数，将幅值特征与相位特征进行加权融合。实验结果表明，所提出的算法与改进前的算法相比，降低了特征向量的维度，且提高了最终的人脸识别率。

关键词：Gabor小波；特征提取；局部幅值特征；局部相位特征；加权融合 中图分类号：TP391.4 doi:10.19734/j.issn.1001-3695.2018.05.0570

Feature extraction algorithm based on improved Gabor wavelet transform

Liu Shengxil†, Cheng Chunling² (1.System IntegrationCompany,China InformationConsulting&Designing InstituteCo.LD,Nanjing 210ol9,China;2. College ofComputer,Nanjing University ofPosts &Telecommunications,Nanjing 21ooo3,China)

Abstract:Aiming at the problem that the featurecascading method for facefeature extraction based on Gabor wavelet amplitude and phase makes the feature vector dimension higher,this paper proposed an improved Gabor wavelet transform feature extractionalgorithm.Thealgorithmcalculated local amplitudeandlocalphase features,and enhancedthelocal correlationofeachpixel.Thenthealgorithm weighted fusion foramplitudeandphase features byweightingcoefficients which experiment selected.Experimental results show that the proposed algorithm reduces the dimension of the feature vector and improves the final face recognition rate compared with the pre improved algorithm.

Key Words: Gabor wavelet; feature extraction;local amplitude feature; local phase feature; weighted Fusion

# 0 引言

特征提取是人脸识别系统中最关键的技术之一，指的是通过计算分析人脸图像得到具有一定区分度的数据来描述人脸特征的过程。但是目前已有的人脸特征提取方法在算法对于光照与姿态等外界因素干扰的情况下，算法提取的特征的鲁棒性不高，还不能适用于一般情况。所以，如何找到一种对复杂环境有较高鲁棒性的人脸描述特征是本文需要解决的问题[1]。

随着图像采集技术的不断发展，复杂条件下采集到的图像越来越多，受到包括光照、姿态、遮挡等外界因素的影响。譬如当光照发生较大变化时，同一个人的人脸图像可能比在相同光照条件下的不同人的人脸图像的变化大很多，因为光照的变化使得处于光照较暗下的人脸的纹理信息被遮盖，所以导致同一个人的人脸特征发生较大差异。当人脸姿态变化幅度过大或者人脸部分信息被遮挡时，会导致人脸部分关键特征缺失，从而无法提取完整的人脸特征。因此，传统的特征提取算法对于此类图像的特征提取的效果不够理想。而通过研究发现Gabor小波类似于哺乳动物视觉系统中视觉神经元，在局部空间内有很好地提取信息的性能，由于Gabor小波具有良好的方向选择性、多尺度性以及对于光照、姿态等变化的不敏感性，使得Gabor小波在图像处理和模式识别中得到了广泛的应用[2-4]。

因此，为了进一步提升基于Gabor小波变换特征提取算法提取特征的表征能力，并降低特征维度，本文提出改进的

Gabor小波变换特征提取算法。该算法计算每个像素点的局部幅值特征和局部相位特征来分别代替该像素点的幅值特征和相位特征，增强每个像素点的局部关联性，采用加权融合的方式对幅值特征与相位特征进行融合，降低人脸特征向量的维度并提高人脸特征的表征能力。

# 1 相关工作

目前基于Gabor小波变换的人脸特征提取算法从图像变换区域大小上可以分为解析法和整体法[5]。

解析法即计算每一个特定标记区域的Gabor小波特征，所以该类方法需要选定一些特征域或者特征点（如眼睛、鼻子、嘴巴等)，然后求得各个标记区域的Gabor特征并将其组合成“Gaborjet"。Lades等人[最早提出Gabor小波动态连接结构并将其应用于人脸识别中，该方法将人脸表示为格状的稀疏图，用图像位置的Gabor小波变换得到的特征向量标记图的节点，用连接节点的距离向量标记图的边，根据图像中的节点与连接之间的相似性进行人脸识别，但是在图像中搜索特征点的计算量比较大。为了解决这一问题，Wiskott等人[7使用弹性图匹配方法对人脸的关键部位进行标定，然后针对关键部位进行了Gabor小波变换，最后将多个关键部位的Gabor小波特征级联。在此过程中弹性图的匹配较为耗时。因此，为了避免弹性图的构建，Kalocsai等人[8将人脸的关键特征点直接进行Gabor小波变换，再将这些特征级联起来。但是解析法都需要对人脸的关键特征点进行手工标定，其过程较为繁琐。

整体法则是将图像整体进行Gabor小波变换，不再需要对特征点进行手工标记。Liu等人[9使用多尺度与多方向的Gabor核函数对完整的人脸图像进行卷积，将提取的Gabor幅值特征作为人脸的特征向量。Shan 等人[10将Gabor 幅值特征与Boosting策略相结合，降低特征维度得到AdaGabor特征，最终通过此特征对人脸进行识别。此前的这些方法提取的都是Gabor的幅值特征，忽略了Gabor的相位特征。事实上，Gabor相位特征中含有丰富的可以用于分类识别的信息，且经过研究表明，Gabor相位特征对于光照等外界因素的变化具有较高的鲁棒性[11]。Zhang 等人[1]提出了基于Gabor小波相位信息的直方图模型，该方法使用了Gabor小波变换、空间区域直方图等，使得该方法对于外界因素的变化具有良好的鲁棒性。为了更好地提升基于Gabor小波变换的特征提取算法的鲁棒性，文献[12]提取了人脸的Gabor幅值特征与相位特征，并将两者级联获得最终人脸特征向量。但是目前基于Gabor小波幅值和相位信息的特征提取方法一方面较少考虑幅值特征的局部邻域之间的关系，使得幅值特征的局部关联性较弱；另一方面合成幅值特征与相位特征的方式大多为串联，所以使得最终的人脸特征向量的维度较高且表征能力不能达到最好。

综上所述，解析法由于需要手工标定特征，所以其过程较为繁杂。整体法中基于Gabor小波幅值信息的特征提取方法对于限定条件下的人脸特征提取有较好的效果，因为其通过滤波得到的幅值信息可以很好地反映人脸的纹理特征，然而复杂条件下的人脸局部的纹理特征可能会发生改变，所以导致基于Gabor小波幅值信息的特征提取方法对于受外界环境干扰的人脸提取的特征的表征能力不强。而基于Gabor小波幅值和相位信息的特征提取方法融入了对于光照等外界因素具有较强鲁棒性的相位信息，增强了特征的表征能力，但是两种信息的级联方式导致特征维度较高。

# 2 二维Gabor小波变换

Gabor小波是由Gabor函数经过尺度伸缩和旋转生成的一族复函数系，具有很好的视频局部化特征和多分辨性能，能够提取图像局部细微变化[13]。对于图像进行Gabor滤波，需要采用二维Gabor小波变换。二维Gabor小波核函数的定义如式(1)所示[14]。

$$
{ \bf G } _ { \mathrm { u , v } } \left( { \bf z } \right) = \frac { { \bf k } _ { \mathrm { u , v } } } { { \sigma } ^ { 2 } } \exp { \left( { - \frac { { { \bf k } _ { \mathrm { u , v } } } ^ { 2 } } { 2 { \sigma } ^ { 2 } } } \right) } \Bigg [ \exp \left( { \mathrm { i } { \bf k } _ { \mathrm { u , v } } { \bf z } } \right) - \exp \left( { - \frac { { \sigma } ^ { 2 } } { 2 } } \right) \Bigg ]
$$

其中： $\textbf { z }$ 代表图像中某个像素点在空间中的坐标值，可以用z=(x.y）表示；=） 表示滤波器的中心频率。${ \bf k } _ { \nu } = 2 ^ { \frac { \nu + 2 } { 2 } \pi } , \quad \Phi _ { u } = u \frac { \pi } { k }$ ，其中 $\mathbf { u } ( \mathbf { u { = } } 0 , 1 , 2 , . . . , 7 )$ 表示 Gabor滤波器的方向； $\mathrm { v } ( \mathrm { v } { = } 0 , 1 , 2 , 3 , 4 )$ 表示尺度； $\mathbf { k }$ 表示方向的总数目。i是复数运算符， $*$ 表示求对应值的欧氏范数， $\sigma$ 决定了高斯窗宽与波长之比，通常 $\sigma = 2 \pi$ 时实验效果最佳。

一般来说，Gabor特征图谱可以通过图像与Gabor小波的核函数进行卷积运算而获得。如图1所示，A可以看做待处理的图像，B可以看做Gabor小波的核函数。卷积运算的公式为

$$
C \left( x , y \right) = \sum _ { i } \sum _ { j } A \left( i , j \right) B \left( x - i , y - j \right)
$$

那么，将输入的人脸图像进行Gabor小波变换，则运算可以定义为

$$
F _ { \mathrm { u , v } } \left( z \right) = I \left( z \right) * G _ { \boldsymbol { u } , \nu } \left( z \right)
$$

其中： $F _ { u , \nu } ( z )$ 表示Gabor小波卷积得到的特征图像； $I ( z )$ 表示初始图像；\*表示卷积运算。

![](images/4380f8abde55a2debabae6859d01c54f90b110674f261276105a7dc0d8ab8059.jpg)  
图1二维卷积运算  
Fig.1Two dimensional convolution operation

# 3 改进的Gabor小波变换特征提取算法

# 3.1Gabor局部幅值特征

基于Gabor幅值统计特性的特征提取算法所提取的图像幅值特征信息相较于图像全局特征受外界因素的干扰要弱一些。由于二维Gabor小波 $G _ { \mathrm { u , v } } \left( z \right)$ 为复数形式，所以其实部$R e ( G _ { \mathrm { u , v } } \left( z \right) )$ 和虚部 $I \mathrm { m } ( G _ { \mathrm { u , v } } \left( z \right) )$ 分别可以表示为

$$
\mathrm { R e } \left( G _ { u , v } \left( \mathbf { z } \right) \right) = \frac { \mathrm { k _ { u , v } } } { { \sigma } ^ { 2 } } \mathrm { e x p } \left( - \frac { { \mathrm { k _ { u , v } } } ^ { 2 } } { 2 { \sigma } ^ { 2 } } \right) \left[ \mathrm { c o s } ( k _ { u , v } z ) - e x p \left[ - \frac { \sigma ^ { 2 } } { 2 } \right] \right]
$$

$$
\mathrm { I m } { \left( G _ { u , \nu } \left( \mathbf { z } \right) \right) } = \frac { \mathbf { k } _ { \mathbf { u } , \mathbf { v } } } { \mathbf { \sigma } { \mathbf { \sigma } } ^ { 2 } } \exp { \left( - \frac { \mathbf { k } _ { \mathbf { u } , \mathbf { v } } { } ^ { 2 } } { 2 \mathbf { \sigma } { \mathbf { \sigma } } ^ { 2 } } \right) } { \left[ \sin ( k _ { u , \nu } { z } ) \right] }
$$

根据第2章中式(3)，可以得到图像的Gabor特征 $F _ { \mathrm { u , v } } \left( z \right)$ ，所以 $F _ { \mathrm { u , v } } \left( z \right)$ 也为复数，其实部为 $\mathrm { R e } ( F _ { \mathrm { u , v } } \left( z \right)$ )虚部为 $\mathrm { I m } ( F _ { \mathrm { u , v } } \left( z \right) )$ ，其幅值特征为 $M _ { \mathrm { u , v } } \left( z \right)$ ，如式(6)所示。

$$
M _ { \mathrm { u , v } } \left( z \right) = \sqrt { \left( R e \left( F _ { \mathrm { } , \nu } \left( z \right) \right) \right) ^ { 2 } + \left( I m \left( F _ { \mathrm { } , \nu } \left( z \right) \right) \right) ^ { 2 } }
$$

通过卷积运算获得图像的Gabor幅值特征后，为了增强幅值特征的局部关联性，则计算每个像素点的局部幅值特征来代替该像素点的幅值特征。本文选取 $3 \times 3$ 大小的窗口，作为一个像素点的邻域，计算该窗口中周围八个像素点的平均幅值，用该平均幅值来代替窗口中心像素点的幅值。当像素点位于幅值特征图谱的边界时，邻域不在幅值特征图谱范围内的幅值补零。假设像素点 $\textbf { \em z } _ { 0 }$ ，其邻域内各像素点$z _ { i } ( i = 1 , 2 , . . . , 8 )$ 分布如图2所示，则其幅值 $M _ { u , \nu } ^ { ' } \left( z _ { 0 } \right)$ 的计算公式如式(7)所示，最后计算获得局部幅值特征图谱 $\dot { M _ { u , \nu } } \left( z \right)$ 。

$$
\ M _ { \mathrm { u } , \nu } ^ { \prime } \left( z _ { 0 } \right) = \frac { \sum _ { i = 1 } ^ { 8 } M _ { \mathrm { u , v } } \left( z _ { i } \right) } { 8 }
$$

为了能够有效地表征图像全局特征以及降低特征维度，将得到的局部幅值特征图谱进一步划分为若干个矩形不重叠且大小相等的子块，子块数记为 $K$ ，然后分别计算各子块的统计特征。统计特征选择样本均值和标准差这两个最为典型的统计量。

![](images/ff9a6a0f80133339927bfd955318ccd2b4e5602a0a6ac3463b8ae18cab97be2a.jpg)  
图2邻域内各像素点分布示意图

假设一幅图像I大小为 $m \times n$ ，针对Gabor 局部幅值特征图谱划分了 $\boldsymbol { K }$ 个大小相同的子块，每个子块图像为$I _ { \mathrm { k } }$ $\ v { U } _ { \mathrm { ~ k ~ } } ( \ v { k } \mathrm { = } \boldsymbol { 0 } , \ v { U } , \dots , \ v { K } - 1 )$ ，每个子块图像内的均值 $M _ { u , \nu , k } ^ { \mu }$ 和标准差$M _ { u , \nu , k } ^ { \sigma }$ 的计算公式分别为

$$
M _ { u , \nu , k } ^ { \mu } = \frac { \sum _ { z \in I _ { k } } { M _ { \mathrm { u , v } } ^ { \prime } \left( z \right) } } { \left( \mathbf { m } \times \mathbf { n } \right) / \mathrm { K } }
$$

$$
M _ { u , \nu , k } ^ { \sigma } = \sqrt { \frac { \sum _ { z \in I _ { k } } \left( M _ { \mathrm { u , v } } ^ { \prime } \left( z \right) - M _ { u , \nu , k } ^ { \mu } \right) ^ { 2 } } { \left( m \times n \right) / K } }
$$

则图像I的幅值特征可以表示为

$$
\left\{ \left( M _ { u , \nu , k } ^ { \mu } , M _ { u , \nu , k } ^ { \sigma } \right) \big | \mathrm { u = 0 , 1 , . . . , U , v = 0 , 1 , . . . , V , k = 0 , 1 , . . . , \mathcal { K } - 1 } \right\}
$$

其中：U和 $\mathrm { \Delta V }$ 分别表示Gabor小波核函数的方向和尺度数。

# 3.2Gabor局部相位特征

由于Gabor小波的相位特征对于光照有着很强的分辨性，所以本章根据Daugman 方法[15]提取图像经过Gabor小波变换后的局部相位特征，将其与局部幅值特征进行融合，得到对于光照具有更强鲁棒性的特征。

Daugman方法将经过二维Gabor小波变换后的图像中的每一个像素点的信息进行二进制转换，即根据每个像素点的实部信息和虚部信息的正负来确定其二进制的值，转换规则如式(11)和式(12)所示[15]。

$$
P _ { u , \nu } ^ { R e } \left( z \right) = \left\{ \begin{array} { l l } { 0 , } & { R e \left( F _ { \mathrm { u , v } } \left( z \right) \right) > 0 } \\ { 1 , } & { R e \left( F _ { \mathrm { u , v } } \left( z \right) \right) \le 0 } \end{array} \right.
$$

$$
P _ { u , \nu } ^ { I m } \left( z \right) = \binom { 0 , I m \left( F _ { \mathrm { u , v } } \left( z \right) \right) > 0 } { 1 , I m \left( F _ { \mathrm { u , v } } \left( z \right) \right) \le 0 }
$$

其中：表示图像中某个像素点坐标； $\mathtt { R e } \big ( F _ { \mathrm { u , v } } ( z ) \big )$ 、 $\mathrm { I m } \big ( F _ { \mathrm { u , v } } \left( z \right) \big )$

分别表示像素点的实部信息和虚部信息； $P _ { u , \nu } ^ { R e } \left( z \right)$ 、 $P _ { u , \nu } ^ { I m } \left( z \right)$ 分别表示像素点的实部信息和虚部信息的二进制转换值。图像中每一个像素点的实部信息和虚部信息组合成的坐标$\bigl ( \mathrm { R e } \bigl ( F _ { \mathrm { u , v } } \left( z \right) \bigr ) , \mathrm { I m } \bigl ( F _ { \mathrm { u , v } } \left( z \right) \bigr ) \bigr )$ 都可以在复坐标系内找到对应的点，如图3所示。

图中， $\theta _ { u , \nu } \left( z \right)$ 表示坐标的相位角。当 $\mathrm { R e } \left( F _ { \mathrm { u , v } } \left( z \right) \right) > 0$ 时，$\theta _ { { \boldsymbol { u } } , \nu } \left( { \boldsymbol { z } } \right)$ 位于第I或 $\mathrm { I V }$ 象限；当 $\mathrm { R e } \left( F _ { \mathrm { u , v } } \left( z \right) \right) \leq 0$ 时， $\theta _ { { \boldsymbol u } , \nu } \left( z \right)$ 位于第

ⅡI或III象限；同理可以推出 $\mathrm { I m } \big ( F _ { \mathrm { u , v } } \left( z \right) \big )$ 和 $\theta _ { { } _ { u , \nu } } \left( z \right)$ 的关系。所以式(11)和(12)可以分别变形为式(13)和(14)。

$$
P _ { u , \nu } ^ { ^ { R e } } \left( z \right) = \left\{ \begin{array} { l l } { 0 , } & { \theta _ { u , \nu } \left( z \right) \in \left\{ \mathrm { I , I V } \right\} } \\ { 1 , } & { \theta _ { u , \nu } \left( z \right) \in \left\{ \mathrm { I I , I I I } \right\} } \end{array} \right.
$$

$$
P _ { u , \nu } ^ { I m } \left( z \right) = \left\{ \begin{array} { l l } { 0 , \theta _ { u , \nu } \left( z \right) \in \left\{ \mathrm { I } , \mathrm { I I } \right\} } \\ { 1 , \theta _ { u , \nu } \left( z \right) \in \left\{ \mathrm { I I I } , \mathrm { I V } \right\} } \end{array} \right.
$$

式(13)和(14)只是分别对实部与虚部信息进行了二进制转换，并没有对实部与虚部信息之间的关系进行二进制转换。因为在复平面中，相位角 $\theta _ { { \boldsymbol { u } } , \nu } \left( { \boldsymbol { z } } \right)$ 和 $\mathbb { R e } \big ( F _ { \mathrm { u , v } } \left( z \right) \big )$ 、 $\mathrm { I m } \big ( F _ { \mathrm { u , v } } \left( z \right) \big )$ 存在式(15)所描述的关系。

$$
\tan \left( \theta _ { u , \nu } \left( z \right) \right) = \frac { \operatorname { I m } \left( F _ { \mathrm { u , v } } \left( z \right) \right) } { \operatorname { R e } \left( F _ { \mathrm { u , v } } \left( z \right) \right) }
$$

所以，由式(13)和(14)可得，当 $P _ { u , \nu } ^ { R e } \left( z \right)$ 、 $P _ { u , \nu } ^ { l m } \left( z \right)$ 相等，即$\theta _ { { \boldsymbol { u } } , \nu } \left( { \boldsymbol { z } } \right)$ 位于第I或IⅢ象限时， $\tan \left( \theta _ { \scriptscriptstyle u , \nu } \left( z \right) \right) > 0$ ；当 $P _ { u , \nu } ^ { R e } \left( z \right)$ 、 $P _ { u , \nu } ^ { I m } \left( z \right)$ 不相等，即 $\theta _ { { } _ { u , \nu } } \left( z \right)$ 位于第 $\mathrm { I I }$ 或IV象限时， $\tan \left( \theta _ { \boldsymbol { u } , \nu } \left( z \right) \right) \leq 0$ 。所以按照同样的二进制转换规则对 $\tan \mathopen { } \mathclose \bgroup \left( \theta _ { u , v } \mathopen { } \mathclose \bgroup \left( z \aftergroup \egroup \right) \aftergroup \egroup \right)$ 进行二进制编码得到 $P _ { u , \nu } ^ { t a n } \left( z \right)$ ，如式(16)所示。

$$
P _ { u , \nu } ^ { t a n } \left( z \right) = \left\{ \begin{array} { l l } { 0 , } & { \theta _ { u , \nu } \left( z \right) \in \left\{ \mathrm { I , I I I } \right\} } \\ { 1 , } & { \theta _ { u , \nu } \left( z \right) \in \left\{ \mathrm { I I , I V } \right\} } \end{array} \right.
$$

即

$$
P _ { u , \nu } ^ { t a n } \left( z \right) = P _ { u , \nu } ^ { R e } \left( z \right) X O R P _ { u , \nu } ^ { I m } \left( z \right)
$$

为了增强每个像素点与其局部邻域内像素点的相位特征的关联性，同样选定 $3 \times 3$ 大小的窗口，作为一个像素点的邻域。将窗口内其他八个位置的二进制编码与中心像素点的编码进行异或运算得到新的八个二进制编码，然后将这八个二进制编码按照顺序排列成一个8位二进制数，最后将其转换为一个十进制数来表示中心像素点的相位特征。当像素点位于相位特征图谱的边界时，邻域不在相位特征图谱范围内的相位特征编码补零。具体运算过程如图4所示。

![](images/f5541b298006e83910f54889afda8d07c457d5d7954471cd62d4b77999e87ab2.jpg)  
Fig.2Schematic diagram of distribution of each pixel in neighborhood   
图3复坐标系示意图

![](images/e2c93525ad07ffe329fa985b7c528e0b048fa18441317dd572465968f31e3ec4.jpg)  
Fig.3Schematic diagram of complex coordinate system   
图4局部相位特征运算过程  
Fig.4Operation process of local phase feature

其中， $z _ { 0 }$ 为某一像素点坐标，其邻域内各像素点$\mathsf { z } _ { i } ( i = 1 , 2 , . . . , 8 )$ ，像素点 $z _ { 0 }$ 的局部相位特征为 $P _ { \mathrm { u , v } } \left( z _ { 0 } \right)$ ，最终得到图像的局部相位特征图谱 $P _ { \mathrm { u , v } } \left( z \right)$ 。

与3.1节的局部幅值特征提取类似，为了有效地表征图像全局特征以及降低特征维度，一幅大小为 $m \times n$ 的图像I通过二维Gabor小波变换得到局部相位特征图谱 $P _ { \mathrm { u , v } } \left( z \right)$ 后，将其进一步划分为若干个矩形不重叠且大小相等的子块，子块数记为 $\kappa$ ，然后分别通过式(18)和(19)计算各子块$I _ { \mathrm { ~ k ~ } } ( \mathrm { k { = } } 0 , 1 , . . . , K - 1 )$ 的均值 $P _ { u , \nu , k } ^ { \mu }$ 和标准差 $P _ { u , \nu , k } ^ { \sigma }$ 。

$$
P _ { u , \nu , k } ^ { \mu } = \frac { \sum _ { z \in I _ { k } } P _ { \mathrm { u , v } } \left( z \right) } { \left( \mathrm { m } \times \mathrm { n } \right) / \mathrm { K } }
$$

$$
P _ { u , \nu , k } ^ { \sigma } = \sqrt { \frac { \sum _ { z \in I _ { k } } \left( P _ { \mathrm { u , v } } \left( z \right) - P _ { u , \nu , k } ^ { \mu } \right) ^ { 2 } } { \left( m \times n \right) / K } }
$$

则图像I的相位特征可以表示为

$$
\left\{ \left( P _ { u , \nu , k } ^ { \mu } , P _ { u , \nu , k } ^ { \sigma } \right) \mid \mathbf { u } = 0 , 1 , . . . , \mathbf { U } , \mathbf { v } = 0 , 1 , . . . , \mathbf { V } , \mathbf { k } = 0 , 1 , . . . , K - 1 \right\}
$$

其中：U和V分别表示Gabor小波核函数的方向和尺度数。

# 3.3特征融合

特征融合思想是对多种特征进行综合分析、评判和决策处理的过程，即通过融合得到一个使各特征对结果影响贡献最大的综合特征。目前对于Gabor小波变换的幅值特征与相位特征的融合最常采用的方式为级联，即串联法，这种融合方法是将各个特征视为一种假设的平等，认为每一个特征对于最终的识别结果具有同等的影响，这种方法并不能使各个特征对识别正确的贡献作用发挥到最大。而特征加权融合方法是为每一个特征定义权值，通过实验来确定各个特征的贡献值。令幅值特征的权值为 $W _ { M }$ ，相位特征的权值为 $W _ { { P } }$ ，设定每一个特征的权值范围为 $0 . 1 \sim 0 . 9$ ，且 $W _ { \scriptscriptstyle M } + W _ { \scriptscriptstyle P } = 1$ 。所以最终的融合特征计算公式如式(21)所示。

$$
M I X _ { u , \nu , k } ^ { \phantom { \nu } } = W _ { M } \left( M _ { u , \nu , k } ^ { \mu } , M _ { u , \nu , k } ^ { \sigma } \right) + W _ { P } \left( P _ { u , \nu , k } ^ { \mu } , P _ { u , \nu , k } ^ { \sigma } \right)
$$

其中： $\mathbf { u } = 0 , 1 , . . . , \mathbf { U }$ ； $\mathbf { v } = 0 , 1 , . . . , \mathrm { v }$ ； $\mathbf { k } = 0 , 1 , . . . , K - 1$ ；U、V和 $K$ 分别表示Gabor小波核函数的方向和尺度数以及特征图谱的分块大小。

# 3.4算法描述

改进的Gabor小波变换特征提取算法主要由四部分组成，首先需要对人脸图像进行二维Gabor小波变换，其次提取每个像素点的幅值特征并计算每个像素点局部幅值特征，然后提取每个像素点的相位特征并计算每个像素点局部相位特征，最后对局部幅值特征和局部相位特征进行加权融合。改进的Gabor小波变换特征提取算法的伪代码如算法1所示。

算法1改进的Gabor小波变换特征提取算法

输入一幅大小为 $\mathbf { m } \times \mathbf { n }$ 的人脸图像，输出人脸图像的特征向量;

1. $z _ { 0 } \gets$ 第一个像素点的坐标;

2. for $\mathrm { i }  1$ to $\mathbf { m } \times \mathbf { n }$ ·

3. $F _ { \mathrm { u , v } } \left( z _ { i } \right) \gets I \left( z _ { i } \right) { * G _ { u , \nu } \left( z _ { i } \right) }$

$$
\mathrm { R e } \left( F _ { u , \nu } \left( z _ { i } \right) \right) \gets I \left( z _ { i } \right) { * \mathrm { R e } \left( G _ { u , \nu } \left( z _ { i } \right) \right) } ;
$$

$$
\mathrm { I m } \bigl ( F _ { u , \nu } \left( z _ { i } \right) \bigr ) \gets I \left( z _ { i } \right) { * \mathrm { I m } \bigl ( G _ { u , \nu } \left( z _ { i } \right) \bigr ) } \ ;
$$

6.endfor;//对人脸图像进行二维小波变换

7. for $\mathrm { i }  1$ to $\mathbf { m } \times \mathbf { n }$ ·

$$
M _ { \mathrm { u , v } } \left( z _ { i } \right) \gets \sqrt { \left( R e \big ( F _ { u , \nu } \left( z _ { i } \right) \big ) \right) ^ { 2 } + \left( I m \big ( F _ { u , \nu } \left( z _ { i } \right) \big ) \right) ^ { 2 } } \ ;
$$

9. for $\mathrm { j }  1$ to 8;

10.

$$
M _ { \mathrm { u } , \nu } ^ { ' } \left( z _ { i } \right) \gets \frac { et { } { ' } \sum _ { j = 1 } ^ { 8 } M _ { \mathrm { u } , \mathrm { v } } \left( z _ { j } \right) } { 8 } ;
$$

11. end for;

12.endfor;//计算每个像素点的局部幅值特征

13.for $\mathrm { i }  1$ to K

$$
{ \cal M } _ { u , \nu , i } ^ { \mu }  \frac { \sum _ { z \in { \cal I } _ { k } } { \cal M } _ { \mathrm { u , v } } ^ { \prime } ( z ) } { ( \mathrm { m } \times \mathrm { n } ) / \mathrm { K } }
$$

$$
M _ { u , \nu , i } ^ { \sigma }  \sqrt { \frac { \sum _ { z \in I _ { k } } ( M _ { \mathrm { u , v } } ^ { \cdot } ( z ) - M _ { u , \nu , i } ^ { \mu } ) ^ { 2 } } { ( m \times n ) / K } }
$$

14.endfor;//计算每个子块的幅值特征的均值与标准差  
15. for $\mathrm { i }  1$ to $\mathbf { m } \times \mathbf { n }$ ·

$$
\theta _ { u , \nu } \left( z _ { i } \right) \gets \tan ^ { - 1 } \frac { \mathrm { I m } \left( F _ { \mathrm { u , v } } \left( z _ { i } \right) \right) } { \mathrm { R e } \left( F _ { \mathrm { u , v } } \left( z _ { i } \right) \right) }
$$

16. if $0 < \theta _ { u , \nu } ( z _ { i } ) < 9 0 \| 1 8 0 < \theta _ { u , \nu } ( z _ { i } ) < 2 7 0$

17. $P _ { u , \nu } ^ { t a n } \left( z _ { i } \right) \gets 0 ;$

18. end if;

19. if $9 0 < \theta _ { u , \nu } ( z _ { i } ) < 1 8 0 \| 2 7 0 < \theta _ { u , \nu } ( z _ { i } ) < 3 6 0$

20. $P _ { u , \nu } ^ { t a n } \left( z _ { i } \right) \gets 1 ;$

21. end if;

22. for $\mathrm { j }  1$ to 8;

$$
P _ { \mathrm { u , v } } ( z _ { i } )  P _ { \mathrm { u , v } } ( z _ { i } ) + ( P _ { u , v } ^ { t a n } ( z _ { i } ) X O R P _ { u , v } ^ { t a n } ( z _ { j } ) ) 2 ^ { j - 1 } ;
$$

24. end for;

25.endfor;//计算每个像素点的局部相位特征

26.for $\mathrm { i }  1$ to $\mathrm { \bf K }$

$$
P _ { u , \nu , i } ^ { \mu }  \frac { \sum _ { z \in I _ { k } } P _ { \mathrm { u , v } } ( z ) } { ( \mathrm { m } \times \mathrm { n } ) / \mathrm { K } }
$$

$$
P _ { u , \nu , i } ^ { \sigma } = \sqrt { \frac { \sum _ { z \in I _ { k } } \left( P _ { \mathrm { u , v } } \left( z \right) - P _ { u , \nu , i } ^ { \mu } \right) ^ { 2 } } { \left( m \times n \right) / K } }
$$

27.endfor;//计算每个子块的相位特征的均值与标准差  
28.for $\mathrm { i }  1$ to K;

$$
M I X _ { u , \nu , i } = W _ { M } \left( M _ { u , \nu , i } ^ { \mu } , M _ { u , \nu , i } ^ { \sigma } \right) + W _ { P } \left( P _ { u , \nu , i } ^ { \mu } , P _ { u , \nu , i } ^ { \sigma } \right) ;
$$

30.endfor;//幅值特征与相位特征的加权融合

# 4仿真及实验结果分析

# 4.1实验环境和参数设置

实验需要选取合理的图像分块数大小以及本文算法融合特征的权值参数大小。实验的评价指标为平均人脸识别率以及特征提取平均时间。将本文算法与基于Gabor幅值与相位的特征提取算法[12]、基于Gabor幅值的特征提取算法[9]作对比，比较在光照和姿态等外界因素干扰情况下算法提取的特征对于后续人脸识别率的影响，其次比较三种算法的特征提取的平均时间。实验选取Yale、YaleB、CMU-PIE三种人脸数据集来比较分析三种算法。Yale人脸数据集包含了15 个人165张人脸图像，其中包括了光照、表情和姿态的变化；YaleB人脸数据集包含了不同人种的38个人2432张人脸图像，其中包括光照与姿态的变化；CMU-PIE人脸数据集包含了68个人3332张人脸图像，其中包括了光照、表情和姿态的变化。三种人脸数据集图像示例如图5所示。

![](images/12b32914146ad0fe17fca8d2847cfbe348ee654f94cd26e831ac345afdb50fc3.jpg)  
图5三种人脸数据集图像示例

实验选取Gabor滤波器参数为 $\sigma = 2 \pi \ , \quad \mathbf { k } _ { m a x } = \frac { \pi } { 2 } \ , \quad \mathrm { f } = \sqrt { 2 }$ 并提取图像的五个尺度和八个方向上的特征信息。实验的软硬件环境为：CPU为Intel(R）Core(TM)i3-2310MCPU $@ 2 . 1 0$ GHz；内存为 $6 . 0 0 \mathrm { G B }$ ；OS：Windows 7Ultimate 64bit；实验的仿真工具：MATLAB 2014(a)。

# 4.2分块数大小的选取

针对基于Gabor小波变换的特征提取算法，合适的分块大小对于算法提取的特征的表征能力影响较大。因为分块数较小时，子块图像较大，则提取出的特征不够丰富；而当分块数较大时，子图像较小，则特征维数较高，并且容易受噪声影响。因此，针对三种不同的人脸数据集，分别通过本文算法、基于Gabor 幅值与相位的特征提取算法、基于Gabor幅值的特征提取算法进行特征提取，并采用相同的主成分分析法对提取的特征进行降维，输入到相同的支持向量机中进行识别分类，计算不同分块大小情况下的人脸识别率。采用留一交叉验证法，对不同分块大小情况下的每种算法进行20次测试，计算20次测试的平均人脸识别率。图6为不同分块大小情况下的人脸识别率的比较。

从图6中可以看出，当达到某一分块数后，本文算法与基于Gabor幅值与相位的特征提取算法使得后续的人脸识别率持续达到最高且没有下降趋势，而基于Gabor幅值的特征提取算法的后续人脸识别率波动较大。这主要是因为对于光照度较差的人脸图像而言，诸如眼睛、鼻子、嘴巴等脸部特征的影响并不明显。当分块数较大时，虽然其连贯性受到一定程度的破坏，但Gabor相位信息对光照的补偿能力很强，所以本文算法与基于Gabor幅值与相位的特征提取算法的识别率没有受到影响。从图中还可以看出，本文算法与基于Gabor幅值与相位的特征提取算法相比，较小的分块数就能使人脸识别率达到最高，这主要是因为本文算法考虑了幅值特征的局部关联性。从图6(a)中可以看出，使得识别率达到最高时，基于Gabor幅值的特征提取算法的最佳分块数为36个，基于Gabor幅值与相位的特征提取算法的分块数为32\~128个，而本文算法的分块数为16\~128个。因为分块数越多，时间代价就越大，所以三种算法的最佳分块数均取最小值。同理可以得到图6(b)中本文算法、基于Gabor幅值与相位的特征提取算法、基于幅值的特征提取算法的最佳分块数分别为32、49、64，(c)中三种算法的最佳分块数分别为25、49、64。综上，在Yale数据集下，基于Gabor 幅值的特征提取算法、基于Gabor幅值与相位的特征提取算法和本文算法的最佳分块数分别为36、32、16；在YaleB数据集下，三种算法的最佳分块数分别为64、49、32；在CMU-PIE数据集下，三种算法的最佳分块数分别为64、49、25。

![](images/fe82dad8a76ef1ab619538a55a38347297f560c6149771f0238b03849cc7f167.jpg)  
Fig.5Examples of three face data set images   
图6不同分块大小情况下的人脸识别率的比较  
Fig.6Comparison of face recognition rate under different block size

# 4.3特征融合的权重参数选取

由于本文算法需要融合Gabor幅值与相位特征，所以实验设置不同的特征权重，通过测试选定最佳权重参数。根据3.3 节可知，幅值特征权重为 $W _ { \scriptscriptstyle M }$ ，相位特征权重为 $W _ { { P } }$ ，且两者和为1，特征权重参数的范围为 $0 . 1 \sim 0 . 9$ 。将三种不同的人脸数据集，分别通过设置了不同特征权重的本文算法进行特征提取，并采用相同的主成分分析法对提取的特征进行降维，输入到相同的支持向量机中进行识别分类，计算得到人脸识别率。采用留一交叉验证法，对每一种特征权重参数的设置进行20次测试，计算20次测试的平均人脸识别率。表1为不同特征权重参数下的人脸识别率比较。

从表1可以看出，当幅值特征的权重参数 $W _ { \scriptscriptstyle M }$ 偏大，而相位特征的权重参数 $W _ { { P } }$ 偏小时，对于三种数据集的人脸识别率都相对偏低。主要是因为这三种数据集中均包含了光照变化的因素，而相位特征对于光照变化具有较好的鲁棒性，所以需要相位特征的权重参数 $W _ { P }$ 偏大一些。从图中还可以看出，当 $W _ { M } = 0 . 3$ 且 $W _ { P } = 0 . 7$ 或者 $W _ { \scriptscriptstyle M } = 0 . 4$ 且 $W _ { P } = 0 . 6$ 时，本文算法在Yale数据集上的识别率达到最高；当 $W _ { M } = 0 . 4$ 且 $W _ { p } = 0 . 6$ 时，本文算法在YaleB数据集上的识别率达到最高；当 $W _ { M } = 0 . 3$ 且$W _ { P } = 0 . 7$ 或者 $W _ { \scriptscriptstyle M } = 0 . 4$ 且 $W _ { P } = 0 . 6$ 或者 $W _ { \scriptscriptstyle M } = 0 . 5$ 且 $W _ { { P } } = 0 . 5$ 时，本文算法在CMU-PIE数据集上的识别率达到最高。为了统一起见，选定幅值特征的权重参数 $W _ { M }$ 为0.3，相位特征的权重参数 $W _ { { P } }$ 为0.7。

Table 1Comparison of face recognition rate under different feature   

<html><body><table><tr><td colspan="4">weightparameters</td></tr><tr><td>特征权重</td><td></td><td>人脸识别率/%</td><td></td></tr><tr><td>WM</td><td></td><td>WpYale数据集YaleB数据集</td><td>CMU-PIE 数据集</td></tr><tr><td>0.1</td><td>0.9</td><td>98.16</td><td>97.58 98.84</td></tr><tr><td>0.2</td><td>0.8</td><td>98.62 98.12</td><td>99.07</td></tr><tr><td>0.3</td><td>0.7</td><td>99.50</td><td>98.89 99.72</td></tr><tr><td>0.4</td><td>0.6</td><td>99.50</td><td>99.56 99.72</td></tr><tr><td>0.5</td><td>0.5</td><td>97.15</td><td>98.02 99.72</td></tr><tr><td>0.6</td><td>0.4</td><td>96.72</td><td>96.97 98.16</td></tr><tr><td>0.7</td><td>0.3</td><td>96.35</td><td>95.98 97.57</td></tr><tr><td>0.8</td><td>0.2</td><td>95.52</td><td>95.21 97.34</td></tr><tr><td>0.9</td><td>0.1</td><td>95.17</td><td>95.04 96.20</td></tr></table></body></html>

# 4.4算法提取特征的表征能力的比较

实验将三种不同的人脸数据集，分别通过本文算法、基于Gabor幅值与相位的特征提取算法、基于Gabor幅值的特征提取算法进行特征提取，并采用相同的主成分分析法对提取的特征进行降维，输入到相同的支持向量机中进行识别分类，计算得到人脸识别率。采用留一交叉验证法，对每种算法进行20次测试，计算20次测试的平均人脸识别率。表2为不同算法提取特征的表征能力的比较。

表2不同算法提取特征的表征能力的比较/%  
Table 2 Comparison of characterization capabilities for differen   

<html><body><table><tr><td colspan="4">algorithms/%</td></tr><tr><td>数据集</td><td>Gabor 幅值</td><td>Gabor幅值+相位</td><td>本文算法</td></tr><tr><td>Yale</td><td>95.06</td><td>98.25</td><td>99.50</td></tr><tr><td>Yale B</td><td>96.31</td><td>98.62</td><td>99.56</td></tr><tr><td>CMU-PIE</td><td>96.93</td><td>99.08</td><td>99.72</td></tr></table></body></html>

从表2可以看出，本文算法提取的特征具有最好的表征能力，在三种算法中具有最高的人脸识别率。本文算法的特征向量表征能力优于基于Gabor幅值与相位的特征提取算法，主要是因为本文算法考虑了幅值特征的局部关联性，而且本文算法的加权融合特征优于特征的级联融合。基于Gabor幅值与相位的特征提取算法的特征向量表征能力优于基于Gabor幅值的特征提取算法，主要是因为相位特征对于光照的变化具有很好的鲁棒性，所以相位特征的融入使得算法的鲁棒性得到了提升。综上所述，本文算法提取的特征向量的表征能力是优于其他两种算法的。

# 4.5特征提取平均时间的比较

本节实验在三种数据集下，比较本文算法、基于Gabor幅值与相位的特征提取算法、基于Gabor幅值的特征提取算法的特征提取平均时间。计算每一种算法分别在三种数据集下的特征提取平均时间。三种算法的特征提取平均时间比较如表3所示。

从表3可以看出，本文算法的特征提取平均时间略高于基于Gabor幅值与相位的特征提取算法。主要是因为本文算法在基于Gabor幅值与相位的特征提取算法中加入了局部幅值特征的计算以及加权融合特征的计算，所以增加了计算时间。显然基于Gabor幅值与相位的特征提取算法的特征提取平均时间是高于基于Gabor幅值的特征提取算法的，因为增加了相位特征的提取时间。从以上所有的实验结果可以得出以下结论，本文算法在总体表现上是优于其他两种算法的。虽然本文算法的特征提取平均时间高于基于Gabor幅值与相位的特征提取算法和基于Gabor幅值的特征提取算法，但是在最终的人脸识别率上本文算法高于这两种算法。本文算法在保证特征提取平均时间略有增加的同时，提高了在光照、姿态等外界因素干扰情况下最终的人脸识别率，很好地增强了特征的表征能力，降低了特征向量的维度。

表1不同特征权重参数下的人脸识别率比较  
表3三种算法的特征提取平均时间比较   
Table 3Comparison of average time of feature extraction of three   

<html><body><table><tr><td colspan="4">algorithms</td></tr><tr><td rowspan="2">数据集</td><td colspan="3">特征提取平均时间/s</td></tr><tr><td>Gabor 幅值</td><td>Gabor 幅值+相位</td><td>本文算法</td></tr><tr><td>Yale数据集</td><td>0.15</td><td>0.36</td><td>0.41</td></tr><tr><td>YaleB数据集</td><td>0.11</td><td>0.29</td><td>0.38</td></tr><tr><td>CMU-PIE 数据集</td><td>0.10</td><td>0.25</td><td>0.35</td></tr></table></body></html>

# 5 结束语

为了解决基于Garbor小波幅值与相位的人脸特征提取方法的级联特征融合方式使得特征向量维度较高的问题，本文提出了一种改进的Gabor小波变换特征提取算法。通过计算局部幅值特征与局部相位特征来增强特征之间的关联性；将局部幅值特征与局部相位特征加权融合相比于两者级联，降低了提取特征的维度并增强了特征的表征能力。从实验结果来看，本文提出的算法所提取的特征有较高的表征能力且特征维度较低，但是特征提取的平均时间相对较高。因此，下一步工作将会考虑降低算法的时间复杂度，减少特征提取的平均时间。

# 参考文献：

[1]Velusamy S,Gopalakrishnan V,Anand B,et al.Improved feature representation for robust facial action unit detection [C]// Proc of IEEE CCNC.Piscataway,NJ:IEEE Press,2013:681-684.   
[2]Shen Linlin，Bai Li,Fairhurst M.Gabor waveletsand general discriminant analysis for face identification and verification [J].Image & Vision Computing,2007,25 (5):553-563.   
[3]Pichler O,Teuner A,Hosticka B J.A comparison of texture feature extraction using adaptive Gabor filtering,pyramidal and tree structured wavelet transforms [J].Pattern Recognition,2006,29(5):733-742.   
[4]Wang Xuewen,Ding Xiaoqing,Liu Changsong. Optimized Gabor filter based feature extraction for character recognition [Cl// Proc of the 16th International Conference on Pattern Recognition.Washington,DC: IEEE Computer Society,2002:223-226.   
[5]Shen Linlin,Bai Li.A review on Gabor wavelets for face recognition [J].Pattern analysis and applications,2006,9 (2-3):273-292.   
[6]Lades M,Vorbruggen JC,Buhmann J,et al.Distortion invariant object recognition in the dynamic link architecture [J].IEEE Trans on computers,1993,42 (3): 300-311.   
[7]Wiskott L,Fellous JM,Kuiger N,et al.Face recognition by elastic bunch graph matching[J].IEEE Trans on Pattern Analysis&Machine Intelligence,2007,19(7): 775-779.   
[8]Kalocsai P,Malsburg C V D,Horn J.Face recognition by statistical analysis of feature detectors [J].Image & Vision Computing,2O14,18 (4): 273-278.   
[9]Liu Chengjun,Wechsler H.Gabor feature based classification using the enhanced fisher linear discriminant model for face recognition[J].IEEE Trans on Image Processing,2006,11 (4): 467-476.   
[10] Shan Shiguang,Yang Peng,Chen Xilin,et al.AdaBoost Gabor Fisher classifier for face recognition [C]// Pro of International Workshop on Analysis and Modeling of Faces and Gestures.Berlin: Springer,2005: 279-292.   
[11] Zhang Baochang,Shan Shiguang,Chen Xilin,et al.Histogram of gabor phase patterns (hgpp):a novel object representation approach for face recognition [J].IEEE Trans on Image Processing,20O7,16(1):57-68.   
[12] Xie Shufu,Shan Shiguang,Chen Xilin,et al.Fusing local patterns of gabor magnitude and phase for face recognition [J].IEEE Trans on Image Processing,2015,19 (5):1349-1361.   
[13]Fan Guojuan,Li Bo,Mu Wanquan.HOGG:Gabor and HOG-based human detection [C]//Proc of International Conference on Information Technology in Medicine and Education.Washington DC: IEEE Computer Society,2016: 562-566.   
[14] Jeong KJ,Kim D J.Face recognition by weighted multi-resolution uniform local Gabor binary patterns[C]//ProcofInternational Conference on Control,Automation and Systems.Piscataway,NJ:IEEE Press,2012:2167-2170.   
[15]Baochang Z,Zongli W,Bineng Z.Kernel learning of histogram of local Gabor phase patterns for face recognition [J].Eurasip Journal on Advances in Signal Processing,2008,2008(1): 1-8.