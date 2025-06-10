# 未知主点条件的相机焦距自标定方法

唐荣富」，邓宝松1，赵竹新²

(1．军事科学院 国防科技创新研究院，北京 100071;2.北京遥感研究所，北京 100192)

摘要：相机自标定是计算机视觉中的一个基础性研究领域。对于双目相机焦距自标定，当前的研究方法均假定相机主点位置已知，而相机主点在实际中却通常是未知的。提出一种主点和场景均未知的条件下相机焦距自标定的新方法，通过严格的数学分析表明相机的坐标系尺度对焦距标定具有重要影响，并在坐标系尺度影响的定量分析的基础上提出了一种选择合适的坐标系尺度的算法。模拟和实际实验都验证了坐标系尺度的重要性，且本方法较传统方法可获得更好的标定精度。

关键词：计算机视觉；相机自标定；焦距；坐标系尺度中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.09.0776

Focal length self-calibration with unknown principal point from two views

Tang Rongful,Deng Baosongl†, Zhao Zhuxin² (1.National Innovation Instituteof Defense Technology,Academyof Military Sciences,Beijing l071,China;2.Beijing Remote SensingInstitute,Beijing10o192,China)

Abstract: Cameraself-calibration isafundamentalresearch topicincomputer vision.Itis known thatfocal lengthcan be recovered fromtwo views when other intrinsic parameters are fixed.This paper presented a more practical work to calibrate focal length from two views with unknown principal point (neither structure nor motion is known a priori).The mathematical analyses show that the scaleof camera coordinates plays acrucial role in such calibration circumstance.A heuristic algorithm was thus proposed to selectappropriate scale factor forcalibrating focal length.Both simulated and practical tests confirm the significance ofscale factorand the good performance of the proposed algorithm,which obtains more accurate focal length calibration than those with no account of scale factor.

Key words: computer vision; camera self-calibration; focal length; coordinate scale

相机自标定是计算机视觉中一个重要的基础研究领域。相机自标定首先由Faugeras等人[1提出，它不依赖相机和三维场景的任何先验知识，因此极为灵活并应用广泛，如在相机内/外定向、图像三维重建等方面具有非常重要的应用。相机自标定的主要研究内容是从多视图中计算相机的四个内参数，即焦距（focal length）、主点（principal point）、纵横比(aspect ratio）[3\~5]；此外，焦距作为相机最重要的内参数，从较弱条件下进行焦距自标定也引起了众多关注。

焦距自标定方法可分为三类。第一类单视图条件下采用特殊的特征图案进行焦距标定[6\~8]。第二是双视图条件下，利用基本矩阵（fundamentalmatrix，或等价地利用Kruppa方程[3]）的标定方法。对于左右视图一致的焦距，自标定方法有解析方法[9,0]、最小解（minimum solution）方法[1]、隐变量方法[12]；对于左右不一致的焦距，自标定问题可转换为泛化特征值问题进行求解[13]。José等人[14]进一步提出单向径向标定（one-sideradialcalibration）方法，即给定一个已标定的相机（左相机或右相机)，求解另一个相机的焦距及径向畸变参数 $\mathrm { K } _ { 1 }$ 共两个参数。这些标定方法可运用于双目重建[15]及双目校正[16]。第三类方法是多视图标定方法。Cheng等人[17]利用相机内参约束，提出一种多视图焦距标定的线性方法;Bujnak等人[18]采用区间分析方法对对偶二次问题进行求解焦距标定；Bocquillon等人[19]提出权重核投票（weightedkernelvoting）的多视图标定方法。此外，反射折射相机（catadioptriccamera）的多视图焦距标定也受到关注[20]。

需要指出的是，以上所有的方法都必须假定除焦距以外的其他相机内参数为已知。在实际中，纵横比可由像素尺寸信息获得，但是主点位置是未知的、且往往并不处于图像中心[3]。因此，主点已知的假定在实际中常常是无法满足的，从而不可避免对焦距标定引入误差。事实上，假定主点未知的焦距自标定问题要复杂得多。

本文试图解决主点未知条件下的焦距标定问题。本文主要有两方面的贡献。首先，本文发现图像坐标系尺度对焦距标定具有重要影响：图像坐标系尺度在主点已知的情况下并无显著影响，但在主点未知情况下是必须考虑的。其次，本文提出了一种（近似）最优的坐标系尺度的选择算法。通过选择合适的坐标系尺度，该算法可以获得比传统经典方法更加精确的焦距标定结果。

# 1 问题数学描述

本文采用最常用的针孔（pinhole）相机投影模型（projective model)[3]。由于假定歪曲参数（skew parameter)为0，针孔相机的数学模型可表示为

$$
\begin{array} { r } { K = \left( \begin{array} { c c c } { f } & { 0 } & { x _ { \circ } } \\ { 0 } & { \alpha f } & { y _ { \circ } } \\ { 0 } & { 0 } & { 1 } \end{array} \right) } \end{array}
$$

其中: $f$ 为焦距， $\alpha$ 为纵横比， $x _ { \mathrm { { 0 } } }$ 和 $y _ { \mathrm { 0 } }$ 为主点。

图像点的齐次坐标表示为 $\mathbf { \boldsymbol { x } } = \mathbf { \boldsymbol { \left( x , y , l \right) } } ^ { r }$ 。记 $\mathrm { ~  ~ x ~ }$ 和 $\mathrm { ~ x ' ~ }$ 分别为左右相机同名点，其满足

$$
\mathbf { x } ^ { \prime _ { T } } \mathbf { F } \mathbf { x } = 0
$$

其中：F是秩为2的基本矩阵。在左右相机未标定时，基本矩阵是对极几何（epipolargeometry）的完全代数表示。当左右相机已知时，对极几何可进一步由本质矩阵（essentialmatrix）表示。本质矩阵满足以下约束：

$$
2 \mathrm { E E } ^ { \mathrm { T } } \mathrm { E } \cdot t r ( \mathrm { E } ^ { \mathrm { T } } \mathrm { E } ) \mathrm { E } = 0
$$

$$
\mathbf { E } = \mathbf { K ^ { \prime \mathrm { T } } F K }
$$

其中: $t r ( \bullet )$ 表示矩阵的迹， $\kappa$ 和 $\mathbf { \nabla } \mathbf { K ^ { \prime } }$ 分别为左右相机矩阵。

本文的研究目标即为假定 $\mathbf { K } ^ { \prime } = \mathbf { K }$ ， $\alpha = 1$ ，主点 $x _ { 0 }$ 和 $y _ { \mathrm { 0 } }$ 未知，求解焦距 $f$ （即标定）。

# 2 焦距自标定

# 2.1数学推导

记F的SVD分解为 $\mathbf { F } = \mathbf { U S } \mathbf { V } ^ { \mathrm { r } }$ 且

$$
\begin{array} { r } { \mathrm { U } = ( u _ { i j } ) , \mathrm { V } = ( \nu _ { i j } ) , i , j = 1 , 2 , 3 } \\ { \mathrm { S } \triangleq \left( \begin{array} { l l l } { s _ { 1 } } & { 0 } & { 0 } \\ { 0 } & { s _ { 2 } } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right) } \end{array}
$$

由于 $t r ( A B ) = t r ( B A )$ ，由式(3)和(4)可得

$$
2 K ^ { T } F K K ^ { T } F ^ { T } K K ^ { T } F K - t r ( K ^ { T } F ^ { T } K K ^ { T } F K ) K ^ { T } F K = 0
$$

$$
\begin{array} { r l } & { 2 S V ^ { T } K K ^ { T } V S U ^ { T } K K ^ { T } U S - t r \big ( S V ^ { T } K K ^ { T } V S U ^ { T } K K ^ { T } U \big ) S } \\ & { \qquad \triangleq 2 S N S M S - t r \big ( S N S M \big ) S = 0 } \end{array}
$$

其中:

$$
\begin{array} { l } { { { \bf { M } } = { \bf { M } } ^ { \mathrm { { T } } } = { \bf { U } } ^ { \mathrm { { T } } } { \bf { K } } { \bf { K } } ^ { \mathrm { { T } } } { \bf { U } } \triangleq \left( { m _ { i j } } \right) } } \\ { { { \bf { N } } = { \bf { N } } ^ { \mathrm { { T } } } = { \bf { V } } ^ { \mathrm { { T } } } { \bf { K } } { \bf { K } } ^ { \mathrm { { T } } } { \bf { V } } \triangleq \left( { n _ { i j } } \right) } } \end{array} \ i , j = { 1 , 2 , 3 }
$$

记

$$
T \triangleq S N S M S = { \left( t _ { i j } \right) } , i , j = 1 , 2 , 3 .
$$

那么，易证明 $T$ 具有以下形式:

$$
{ \mathrm { T } } = { \left( \begin{array} { l l l } { t _ { 1 1 } } & { t _ { 1 2 } } & { 0 } \\ { t _ { 2 1 } } & { t _ { 2 2 } } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right) }
$$

且

$$
\begin{array} { r l } & { t _ { 1 1 } = s _ { 1 } \left( s _ { 1 } ^ { 2 } m _ { 1 1 } n _ { 1 1 } + s _ { 1 } s _ { 2 } m _ { 1 2 } n _ { 1 2 } \right) } \\ & { t _ { 1 2 } = s _ { 2 } \left( s _ { 1 } ^ { 2 } m _ { 1 2 } n _ { 1 1 } + s _ { 1 } s _ { 2 } m _ { 2 2 } n _ { 1 2 } \right) } \\ & { t _ { 2 1 } = s _ { 1 } \left( s _ { 2 } ^ { 2 } m _ { 1 2 } n _ { 2 2 } + s _ { 1 } s _ { 2 } m _ { 1 1 } n _ { 1 2 } \right) } \\ & { t _ { 2 2 } = s _ { 2 } \left( s _ { 2 } ^ { 2 } m _ { 2 2 } n _ { 2 2 } + s _ { 1 } s _ { 2 } m _ { 1 2 } n _ { 1 2 } \right) } \end{array}
$$

$$
t r ( \mathrm { S N S M } ) = \frac { t _ { 1 1 } } { s _ { 1 } } + \frac { t _ { 2 2 } } { s _ { 2 } }
$$

将矩阵 $T$ 代入式(4)，可以推导得到以下三个方程：

$$
\begin{array} { c } { { s _ { 1 } ^ { 2 } m _ { 1 1 } n _ { 1 1 } - s _ { 2 } ^ { 2 } m _ { 2 2 } n _ { 2 2 } = 0 } } \\ { { { } } } \\ { { s _ { 1 } m _ { 1 2 } n _ { 1 1 } + s _ { 2 } m _ { 2 2 } n _ { 1 2 } = 0 } } \\ { { { } } } \\ { { s _ { 1 } m _ { 1 1 } n _ { 1 2 } + s _ { 2 } m _ { 1 2 } n _ { 2 2 } = 0 } } \end{array}
$$

式(5)\~(7)是本文方法的基本约束方程，分别称为约束方程1、约束方程2、约束方程3，记为 $C _ { i } ( f , x _ { 0 } , y _ { 0 } ) ( i = 1 , 2 , 3 )$ 或者一般性地记为 $C ( f , x _ { 0 } , y _ { 0 } )$ 。三个约束方程是两两独立的，对应着基本矩阵的秩为2。

三个约束方程包含 $m _ { i j }$ 和 $n _ { i j } \ ( i , j = 1 , 2 )$ ，其中 $m _ { i j }$ 可表示为

$$
\begin{array} { c }    \begin{array} { c } { { m _ { 1 1 } - \left( u _ { 1 1 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 1 } ^ { 2 } \right) f ^ { 2 } + u _ { 3 1 } \left( u _ { 1 1 } + 2 u _ { 1 1 } u _ { 3 } \right) } } \\ { { 2 u _ { 3 1 } u _ { 2 1 } ^ { 3 } y _ { 0 } + 2 u _ { 1 1 } u _ { 2 1 } \lambda u _ { 3 1 } ^ { 3 } + u _ { 1 1 } ^ { 2 } x _ { 1 } ^ { 2 } + u _ { 2 1 } ^ { 2 } y _ { 0 } ^ { 2 } = } } \\ { { \left( u _ { 1 1 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 1 } ^ { 2 } \right) f ^ { 2 } + \left( u _ { 3 1 } + u _ { 1 1 } x _ { 0 } + u _ { 2 1 } y _ { 0 } \right) ^ { 2 } } } \\    \begin{array} { c } { { { } } } \\ { { } } \\ { { } } \\ { { m _ { 1 2 } - m _ { 2 1 } = \left( u _ { 1 1 } u _ { 1 2 } + \alpha ^ { 2 } u _ { 2 1 } u _ { 2 2 } \right) f ^ { 2 } + u _ { 3 1 } u _ { 3 2 } + \left( u _ { 1 2 } u _ { 3 1 } + u _ { 1 1 } u _ { 2 1 } \right) x _ { 0 } + } } \\  { { } } \\ { { } } \\ { { \left( u _ { 2 2 } u _ { 3 1 } + u _ { 2 1 } u _ { 3 2 } \right) y _ { 0 } + \left( u _ { 2 1 } u _ { 1 2 } + u _ { 1 1 } u _ { 2 1 } \right) x _ { 1 } y _ { 0 } } } \\  { { } } \\ { { \left( u _ { 1 1 } u _ { 2 1 } + \alpha ^ { 2 } u _ { 2 1 } u _ { 2 1 } \right) f ^ { 2 } + \left( u _ { 1 1 } + u _ { 1 1 } x _ { 0 } + u _ { 2 1 } y _ { 0 } \right) \left( u _ { 2 1 } + u _ { 1 1 } u _ { 3 2 } + u _ { 2 1 } u _ { 2 2 } \right) y _ { 0 } ^ { 2 } = } } \\  { { } } \\ { { m _ { 2 2 } - \left( u _ { 1 2 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 2 } ^ { 2 } \right) f ^ { 2 } + u _ { 2 1 } \left( u _ { 2 2 } + 2 u _ { 2 1 } \right) x _ { 0 } } } \\ { { 2 u _ { 3 1 } u _ { 2 1 } } } \\ { { 2 u _ { 3 2 } \left( u _ { 2 1 } ^ { 2 } + 2 u _ { 2 1 } ^ { 2 } \right) f ^ { 2 } + u _ { 2 2 } \left( u _ { 2 2 } + 2 u _ { 2 1 } x _ { 0 } \right) } } \\  { { } } \\   \begin{array} { c }    \end{array} \end{array} \end{array} \end{array}
$$

同理， $n _ { i j }$ （204号 $( i , j = 1 , 2 )$ 可类似推导得到，只需将式(8)-(10)中的 $u _ { i j }$ 替代为 $\nu _ { i j }$ 。

从上述数学推导可见，焦距标定显然受未知主点 $x _ { 0 }$ 和 $y _ { \mathrm { 0 } }$ 的影响。

# 2.2 坐标系尺度

本节主要分析坐标系尺度因子（scalefactor）对焦距标定的影响。这里先给出数学分析的两个主要结果，一个是定性分析结果：约束方程1比约束方程2和3在数值上更为稳定，故更适用于焦距标定估计；一个是定量分析结果为坐标系尺度对焦距标定具有显著影响。

首先，当主点 $x _ { 0 }$ 和 $y _ { 0 }$ 未知时，需要对 $m _ { i j }$ 进行近似（类似地对 $n _ { i j }$ 近似)

$$
\left( u _ { 3 1 } + u _ { 1 1 } x _ { 0 } + u _ { 2 1 } y _ { 0 } \right) ^ { 2 } \approx u _ { 3 1 } ^ { 2 }
$$

$$
\left( u _ { 3 2 } + u _ { 1 2 } x _ { 0 } + u _ { 2 2 } y _ { 0 } \right) ^ { 2 } \approx u _ { 3 2 } ^ { 2 }
$$

$$
\big ( u _ { 3 1 } + u _ { 1 1 } x _ { 0 } + u _ { 2 1 } y _ { 0 } \big ) \times
$$

$$
\left( u _ { 3 2 } + u _ { 1 2 } x _ { 0 } + u _ { 2 2 } y _ { 0 } \right) \approx u _ { 3 1 } u _ { 3 2 }
$$

显然，近似式(11)和(12)比近似式(13)数值上更加稳定，因为式(13)可能会改变近似左右两边的符号，而式(11)和(12)的近似总是保持两边符号一致（ $\scriptstyle \geq 0 \ )$ 。因此，本文使用数值稳定的近似式(11)和(12)进行焦距自标定；等价地，使用只包含 $m _ { 1 1 }$ 和 $m _ { 2 2 }$ 的约束方程1（式(5)）来估计焦距，从而有

$$
\begin{array} { c } { { s _ { 1 } ^ { 2 } \left[ \left( u _ { 1 1 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 1 } ^ { 2 } \right) f ^ { 2 } + u _ { 3 1 } ^ { 2 } \right] \left[ \left( \nu _ { 1 1 } ^ { 2 } + \alpha ^ { 2 } \nu _ { 2 1 } ^ { 2 } \right) f ^ { 2 } + \nu _ { 3 1 } ^ { 2 } \right] - } } \\ { { s _ { 2 } ^ { 2 } \left[ \left( u _ { 1 2 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 2 } ^ { 2 } \right) f ^ { 2 } + u _ { 3 2 } ^ { 2 } \right] \left[ \left( \nu _ { 1 2 } ^ { 2 } + \alpha ^ { 2 } \nu _ { 2 2 } ^ { 2 } \right) f ^ { 2 } + \nu _ { 3 2 } ^ { 2 } \right] = 0 } } \end{array}
$$

利用近似式(11)\~(13)，约束方程2和约束方程3也分别近似为式(15)和(16)如下：

$$
\begin{array} { r l } & { s _ { 1 } \big [ ( u _ { 1 1 } u _ { 1 2 } + \alpha ^ { 2 } u _ { 2 1 } u _ { 2 2 } ) f ^ { 2 } + u _ { 3 1 } u _ { 3 2 } \big ] \times } \\ & { \qquad \big [ ( v _ { 1 1 } ^ { 2 } + \alpha ^ { 2 } v _ { 2 1 } ^ { 2 } ) f ^ { 2 } + \nu _ { 3 1 } ^ { 2 } \big ] + } \\ & { \qquad s _ { 2 } \big [ ( u _ { 2 1 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 2 } ^ { 2 } ) f ^ { 2 } + u _ { 3 2 } ^ { 2 } \big ] \times } \\ & { \qquad \big [ ( \nu _ { 1 1 } \nu _ { 1 2 } + \alpha ^ { 2 } \nu _ { 2 1 } v _ { 2 2 } ) f ^ { 2 } + \nu _ { 3 1 } v _ { 3 2 } \big ] = 0 } \\ & { \qquad \quad s _ { 1 } \big [ ( u _ { 1 1 } ^ { 2 } + \alpha ^ { 2 } u _ { 2 1 } ^ { 2 } ) f ^ { 2 } + u _ { 3 1 } ^ { 2 } \big ] \times } \\ & { \qquad \big [ ( \nu _ { 1 1 } v _ { 1 2 } + \alpha ^ { 2 } \nu _ { 2 1 } v _ { 2 2 } ) f ^ { 2 } + \nu _ { 3 1 } v _ { 3 2 } \big ] + } \\ & { s _ { 2 } \big [ ( u _ { 1 1 } u _ { 1 2 } + \alpha ^ { 2 } u _ { 2 1 } u _ { 2 1 } ) f ^ { 2 } + \nu _ { 3 1 } u _ { 3 2 } \big ] \times } \\ & { \qquad \big [ ( \nu _ { 1 2 } ^ { 2 } + \alpha ^ { 2 } \nu _ { 2 2 } ^ { 2 } ) f ^ { 2 } + \nu _ { 3 2 } ^ { 2 } \big ] = 0 } \end{array}
$$

下面将可以看到，近似约束式 (15)和(16)尽管不用于标定估计，但会用于评价标定结果。

其次，从近似约束式(14)可知，数值近似不仅受未知主点 $x _ { 0 }$ 和 $y _ { 0 }$ 数值的影响，同样也受 $u _ { i j }$ 和 $\nu _ { i j }$ $( i , j = 1 , 2 , 3 )$ 数值的影响。而 $x _ { 0 }$ 、 $y _ { 0 }$ 、 $u _ { i j }$ 和 $\nu _ { i j }$ （由基本矩阵推导出）都与坐标系尺度有关系，且这种关系是强非线性的，因此在近似式(14)中必须考虑不同坐标系尺度因子（scalefactor）的影响。也就是说，坐标系尺度的影响在 $x _ { 0 } = y _ { 0 } = 0$ 时并不显著(无须近似)，但在$x _ { 0 }$ 、 $y _ { 0 }$ 未知的条件下则至关重要。

为行文方便，本文先给出一个经验性的坐标系尺度因子集合 $\mathcal { L }$ 为

$$
\begin{array} { c } { { \mathcal { L } = \{ l _ { i } \} = \{ 1 , 1 { \times } 1 0 ^ { - 1 } , 1 { \times } 1 0 ^ { - 2 } , } } \\ { { 1 { \times } 1 0 ^ { - 3 } , 1 { \times } 1 0 ^ { - 4 } , 1 { \times } 1 0 ^ { - 5 } , 1 { \times } 1 0 ^ { - 6 } \} } } \end{array}
$$

后面将会进一步解释尺度经验集合 $\mathcal { L }$ 0

# 2.3数值分析

为定量描述坐标系尺度对焦距自标定的影响，本文进行了大量的数值模拟，其中一个典型的样例结果如图1所示。在这个模拟样例中，焦距真值 $f = 2 0 0 0$ ，噪声标准差为0.5像素，主点的偏移中心量约为150像素，左右图像大概有 80个同名点（correspondingpoint)。图1反映了几个重要的结果。

![](images/b2544addb74e39e7222e369309db838aa406c1052e3a228acc75b4c789df8467.jpg)  
图1不同坐标系尺度的焦距自标定结果

a)未知主点对焦距自标定具有重要影响。当主点已知时，自标定结果为1996（未在图1中显示)；而当主点未知时，自标定结果为1880，明显差于主点已知的标定结果。可见，未知主点对焦距自标定的影响极为明显，过于简化的主点已知假设可能会导致较差的标定结果，因此必须通过一定对数学方法处理来减少未知主点的影响。

b)坐标系尺度因子对焦距自标定具有重要影响。应用经典方法[10]时（即尺度因子为1)，自标定结果为1880；而通过选择合适的尺度因子，自标定结果为2026。显然，通过选择合适的尺度因子，可以获得精度高得多的焦距标定结果。

c）图1表明对于处于区间 $1 0 ^ { - 6 } \leq l \leq 1 0 ^ { - 4 }$ 的尺度因子，自标定结果是几乎相同的(2026)；同样，对于处于区间 $1 0 ^ { - 2 } \leq l \leq 1$ ，自标定结果也几乎是相同的（1880)；唯一的变化出现在区间$1 0 ^ { - 4 } \leq l \leq 1 0 ^ { - 3 }$ 。这个现象在大量模拟中是普遍出现的。这是坐标系尺度影响的一个非常重要的性质，它允许采用有限的尺度因子集合，而不需要对所有尺度因子进行穷尽，这也是本文采用经验尺度的有限集合 $\mathcal { L }$ （式(17)）的原因。这个性质也保证了从集合 $\mathcal { L }$ 选择合适的尺度因子可以获得很高的自标定精度。

# 2.4焦距自标定算法

根据以上的理论分析和数值模拟结果，本文提出一个新的自标定算法，通过从尺度集合 $\mathcal { L }$ （式(17)）选择最佳尺度因子，获得焦距自标定结果（这个结果或许不是最优的，但在绝大多数情况下式近乎最优的；另一方面，最优标定结果要求更多的采样遍历且不易获得)。算法包含以下步骤。

a)坐标尺度变化,将同名点坐标 $\mathrm { ~  ~ x ~ }$ 和 $\mathrm { ~ \bf ~ x ~ } ^ { \prime }$ 乘以尺度因子 $l _ { i } \in \mathcal { L }$ ：

b)利用八点法计算基本矩阵（必要的话，应用RANSAC去除野值点(outlier));

c）计算基本矩阵的 SVD分解；

d)获得约束方程1、约束方程2、约束方程3,如式(5)\~(7)所示；

e）三个约束方程可转换为

$$
a ( l _ { i } * f ) ^ { 4 } + b ( l _ { i } * f ) ^ { 2 } + c = 0 , \mathrm { w h e r e \quad } a \ne 0
$$

及

$$
f ^ { 4 } + \frac { b } { a } \frac { 1 } { l _ { i } ^ { 2 } } f ^ { 2 } + \frac { c } { a } \frac { 1 } { l _ { i } ^ { 4 } } = 0 , \mathrm { w h e r e \quad } a \neq 0
$$

f)利用约束方程1（式(17)）求解两个解，记为 $f _ { i 1 }$ 和 $f _ { i 2 }$ ：g)接受正解（即要求 $f _ { i 1 } > 0$ 及 $f _ { i 2 } > 0$ ）；  
h)对所有 $l _ { i } \in \mathcal { L }$ ，重复步骤1)-7);

i)记所有正解的集合为 $\left\{ f _ { m } \right\} _ { m = 1 } ^ { M }$ ，所有约束方程为$\left\{ C _ { n 1 } , C _ { n 2 } , C _ { n 3 } \right\} _ { n = 1 } ^ { N }$ （ $N$ 为集合 $\mathcal { L }$ 的尺度因子个数， $\mathbf { \Omega } _ { M }$ 为正解个数，显然 $M \leq 2 N$ ）；

j)对所有 $\left\{ f _ { m } \right\} _ { m = 1 } ^ { M }$ ，计算估计误差如下：

$$
e ( f _ { m } ) = \sum _ { n = 1 } ^ { N } \mathrm { m i n } ( C _ { n 1 } ( f _ { m } ) , C _ { n 2 } ( f _ { m } ) , C _ { n 3 } ( f _ { m } ) )
$$

k）选择最优自标定结果如下：

$$
f ^ { * } = \underset { f _ { m } } { \mathrm { a r g m i n } } e ( f _ { m } )
$$

# 3 实验与分析

# 3.1模拟实验

在模拟实验中，本文采用不同的未知主点和噪声水平对本文焦距自标定算法进行测试，并与经典方法[10]进行比较。在模拟实验中，焦距真值 $f = 2 0 0 0$ ，左右图像大概有100个同名点（correspondingpoint）。为获得较好的统计结果，每组模拟测试重复100次。

在第一类模拟实验中，固定噪声标准差为0.5像素，测试不同偏移主点的焦距标定结果。标定误差结果如图2所示其中圆形标志数据为本算法的结果，方形标志数据为Sturm方法[10]（该方法不做任何坐标系尺度变换，直接采用像素坐标，故标志为“不选择SF")。实验表明两个方法的标定误差均随主点偏移量增大而增大，但本文方法明显优于Sturm 方法。在未知主点的偏移值为50像素时，本文算法的标定误差为86.1像素，而Sturm方法的误差为97.3像素；当未知主点偏移值为150像素时，点偏移量增大而增大。在未知主点的偏移值为50像素时，本文算法的标定误差为259.3像素，而Sturm方法的误差为357.9像素。这个实验也再一次表明选择合理的坐标系尺度因子可显著提升焦距标定结果。

![](images/63cdd1ee5df50cb690fbf26209267feea9e89c5162345e5736dee75982fdb066.jpg)  
Fig.1Focal length calibration results with respect to different scale factors of image coordinates   
图2不同主点偏移量的焦距自标定结果  
Fig.2Focal length calibration results with respect to principal point shifts

在第二类实验中，固定未知主点的偏移量为50像素，测试不同噪声水平下的焦距标定结果，如图3所示。两个方法的焦距标定误差均随噪声增大而增大。当噪声标准差大于0.5像素时，两个方法的标定结果具有显著差异。对于0.8像素和1像素的噪声，本文方法的误差分别为69和86像素，而Sturm方法的误差分别为96和120像素。这个实验也表明了坐标系尺度的重要性。

所有模拟实验都表明了坐标系尺度对焦距自标定的显著影响。本文方法通过选择合理的尺度因子，比经典方法[10]

显著提升了焦距自标定精度。

![](images/f56752aefcba05cacdae2407d313f4ebe6f38d9a69b8a1191020fb6a2fb725e2.jpg)  
图3不同噪声水平的焦距自标定结果

# 3.2 实际实验

本文采用EPFL的多视图数据[21进行实际测试。同名点采用SIFT特征进行提取，基本矩阵采用八点法及RANSAC方法。测试数据如图4所示，测试结果见表1。

从表1中可知，本文方法在所有测试数据上都明显优于Li方法[12]和 Sturm方法[10]。此外，Li方法[12]表现较差，可能是由于该方法对噪声比较敏感。

表1不同方法的实际测试结果（单位：像素)  
Table 1Practical results of different calibration methods (unit: pixel)   

<html><body><table><tr><td>数据</td><td>真值</td><td>Li [12]</td><td>Strum [10]</td><td>本文方法</td></tr><tr><td>(a)</td><td>2761.82</td><td>2819</td><td>2805.83</td><td>2742.33</td></tr><tr><td>(b)</td><td>2761.82</td><td>2691</td><td>2738.66</td><td>2770.75</td></tr><tr><td>(c)</td><td>1341</td><td>1399</td><td>1328.43</td><td>1328.43</td></tr><tr><td>(d)</td><td>1341</td><td>1410</td><td>1353.35</td><td>1345.35</td></tr></table></body></html>

![](images/f03b9db6a56faa38163001fc4d8d84f92034311c72c017f1136082b2eb266d7c.jpg)  
Fig.3Focal length calibration results with respect to noise levels   
图4EPFL 实际测试数据  
Fig.4EPFL dataset for practical tests

# 3.3 讨论

本文详细叙述了本文方法的数学过程，在严格的数学分析基础上提出了新的焦距自标定方法，并进行了详细的模拟和实际测试。理论分析和测试结果都表明了：在主点未知的条件下，坐标系尺度对焦距自标定具有显著影响。

本文所提出算法的核心思想是基于式(11)\~(14)，即通过选择不同的尺度因子来减少未知主点对焦距标定的不利影响。理论分析表明尺度因子在主点已知时对焦距标定影响很小，但在主点未知时影响显著。在实际中，主点通常不是位于图像中心且其位置是未知的，故本文提出的方法具有重要的实际应用价值。

本文给出了一种基于最小平均误差思想的选取合适坐标系尺度因子的方法。这种方法是根据尺度因子的数值特征进行设计的，因而也是启发式的和解析的，并且通常可以得到近似最优的标定结果。

# 4 结束语

本文在严格的数学分析基础上提出了主点未知条件下焦距自标定的一种新方法。由于相机主点在实际中通常是未知的，因此本方法相比于假定主点已知的已有方法更具有实际意义。

本文的主要贡献是首次证明了坐标系尺度对焦距自标定的显著影响，并提出了一个选取合适尺度因子的解析式算法。由于选取了合适坐标系尺度因子，从而可以获得更佳的焦距标定结果，并通过仿真和实际实验验证了本文算法的有效性。下一步研究包括进一步提升自标定算法的精度。

# 参考文献：

[1]Faugeras O D,Luong Q T,Maybank S J.Camera Self-Calibration: Theory and Experiments [C]//Proc of European Conference on Computer Vision.Heidelberg :Springer-Verlag,1992:321-334.   
[2]Bocquillon B,Bartoli A,Gurdjos P,et al.On Constant Focal Length Self-Calibration From Multiple Views [C]//Proc of International Conference on Computer Vision and Pattern Recognition .Washiongton DC:IEEE Computer Society,2008:1-8.   
[3]Hartley R,Zisserman A.Multiple view geometry in computer vision [M].2nd ed. Cambridge: Cambridge University Press,2003.   
[4]Sturm P,Ramalingam S,Tardif JP,et al.Camera models and fundamental conceptsused in geometric computer vision [J]. Foundations & Trends in Computer Graphics & Vision,2011,6(1): 1-183.   
[5]赵漫丹，刘烨斌，吴高昌，等．强约束条件下环绕式相机标定方法 [J].计算机应用研究，2017,34(11):3463-3467.(Zhao Mandan,Liu Yebin,Wu Gaochang,et al. Surrounding-camera calibration with strong restritive constraints [J].Application Research of Computers,2017,34 (11): 3463-3467).   
[6]Workman S,Greenwell C, Zhai Mei,et al.DEEPFOCAL:a method for direct focal length estimation [C]//Proc of IEEE International Conference on Image Processing.Piscataway,NJ:IEEE Press,2015: 1369-1373.   
[7]Duan Huixian,Mei Lin,Shang Yanfeng,et al.Calibrating focal length for paracatadioptric camera from one circle image [C]//Proc of International Conference on Computer Vision Theory and Applications. New York:IEEE,2015:56-63.   
[8]Liu Ruizhi,Zhang Hongran,Lu Jian,et al.Extrinsic parameters and focal length calibration using rotation-symmetric patterns [J].IET Image Processing,2016,10(3):189-197.   
[9]Lao Weilun，Cheng Zhaolin，Kam Alvin，et al.Focal length self-calibration based on degenerated Kruppa's equations:method and evaluation [C]//Proc of International Conference on Image Processing. NewYork:IEEE,2004:3391-3394.   
[10] SturmP,Cheng Zhaolin,Chen Peter,et al.Focal length calibration from two views:method and analysis of singular cases [J].Computer Vision &Image Understanding,2005,99(1):58-95.   
[11] Stewenius H,NisterD,KahlF,et al.A minimal solution for relative pose with unknown focal length [C]//Proc of International Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2005:789-794.   
[12] Li Hongdong.A simple solution to the six-point two-view focal-length problem [C]//Proc of European Conference on Computer Vision. Heidelberg :Springer, 2006:200-213.   
[13] Akos P,Hajder L.Automatic focal length estimation as an eigenvalue problem [J].Pattern Recognition Letters,2013,34(9):1108-1117.   
[14]Brito JH, Zach C,KoserK,et al.One-sided radial fundamental matrix estimation [C]//Proc of British Machine Vision Conference.2012:1-12.   
[15] Kanatani K,Nakatsuji A,Sugaya Y. Stabilizing the focal length computation for 3-D reconstruction from two uncalibrated views [J]. International Journal ofComputer Vision,2006,66 (2):109-122.   
[16] Fusiello A， Irsara L.Quasi-Euclidean epipolar rectificationof uncalibrated images [J].Machine Vision and Applications,2011,22(4): 663-670.   
[17] Cheng Zhaolin,Lao Weilun,Kam Alvin,etal.A linear self-calibration approach for camera focal length estimation [C]//Proc of Control, Automation,Robotics and Vision Conference.20o5:717-722.   
[18] Bujnak M,Kukelova Z,Pajdla T.Robust focal length estimation by Votinginmulti-viewscenereconstruction.[C]//ProcofAsian Conference on Computer Vision.2009:13-24.   
[19] Bocquillon B,Bartoli A,Gurdjos P,et al.On constant focal length self-calibration frommultipleviews[C]//Procof International Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society, 2008:1-8.   
[20]Duan Fuqing,Wu Fuchao,Zhou Mingquan,et al.Calibrating effective focal length for central catadioptric cameras using one space line.[J]. Pattern Recognition Letters,2012,33(5): 646-653.   
[21] Strecha C,Hansen WV,GoolL V,et al.On benchmarking camera calibration and multi-view stereo for high resolution imagery [C]/Proc ofInternational Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society,2008:1-8.