# 基于高斯过程的快速人脸验证

周思洋，曹林

(北京信息科技大学 通信工程系，北京 100101)

摘要：为解决目前实现人脸验证算法所需训练样本多，运算量大，识别速度慢等问题，提出了一种在小样本空间中基于高斯过程的快速人脸验证方法。首先使用共轭梯度下降法从训练样本中学习人脸关键部位特征位置的梯度方向，从而可对待验证人脸进行特征定位；然后使用自适应尺度局部二值模式提取特征，以减小特征维度；最后，将谱混合核函数作为高斯过程的核函数对输入的人脸特征进行分类。使用LFW,FERET和 Multi-PIE人脸数据库进行训练和测试，实验结果表明使用自适应尺度局部二值模式有效的减小了特征维度，使用高斯过程模型与谱混合核相结合可大幅减少训练样本，显著提升训练速度和测试速度。

关键词：人脸验证；自适应多尺度局部二值模式；高斯过程；谱混合核函数中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2017.08.0897

# Fast face verification based on Gaussian processes

Zhou Siyang, Cao Lint (DeptofCommunication Engineering,Beijing Information Science &Technology University,Beijing 100lo1,China)

Abstract: Afastface verification method based on Gaussan processinsmallsample space was proposed to solve the problem oflargetrainingsamples,complexcomputatioandtheslowrecognition.Firstly,itusedtheconjugategradientdescenttodetect theface featurepoints,andthenusedtheadaptive multi-scalelocal binary model toextractthefeaturesatthefeature points reducedte featuredimensions.Finally,thespectralkerelfunctionisusedasthekerelfunctionoftheGaussanprocess to classifythe inputfacefeatures.Inthispaper,trainingandtestingarecarredoutusingLFW,FERETandMulti-PIEfacedatabase. The experimental results showed that the local binary model can efectivelyreduce the feature dimension.Thecombinationof the Gaussian processmodeland the spectral hybridcorecan greatlyreduce the trainingsamplesand improve thetraining speed and test speed.

Key Words: face verification; adaptive multi-scale local binary patern; Gaussian process;spectral mixture kernels

# 0 引言

人脸验证是人脸识别领域一个重要分枝，因其在监控、访问控制、图像检索、自动登录和自动支付等方面具有很重要的应用价值，几十年以来一直都是计算机视觉领域的研究热点[1-3]，并且颇具挑战性。近年来随着深度学习的发展，及其在人脸识别领域的应用[4-6]，使得人脸验证在准确度方面得到了提升。但使用深度学习进行人脸验证所需训练样本多达上亿，训练时间太长，对硬件设备要求太高，并且在实际应用中对其框架依赖性较强，不便于移植；因此在小样本空间训练人脸模型仍是研究重点，文献使用跨角度人脸识别方法取得了良好的效果，具有典型的代表性意义，本文受其启发提出了基于高斯过程的快速人脸识别方法。

在人脸验证过程中特征提取是一个关键环节，传统人脸验证算法都是使用扫描窗口进行扫描，此方法提取到的特征维度太高，会导致运算量太大；考虑到人脸面部信息呈不均匀分布，例如：人脸五官部位所含信息量较其他部位丰富，其中人眼所含信息量最大。据此，本文提出自适应多尺度征提取方法（AMLBP)，实验结果表明此方法能显著降低特征维度。

分类模型是人脸验证过程中另一个关键环节，决定两个输入特征是否属于同一个目标，目前已有一些典型的分类模型[8-10]对于分布比较简单的人脸数据能体现出较好的结果，但是当数据分布复杂时其分类效果会显著降低。本文使用高斯过程作为分类模型，高斯过程是一种非参数化的机器学习方法，能灵活适应真实环境中复杂数据分布，不需要任何启发式方法或手动调节参数，其闭式的边缘概率计算使得运算效率更高；此外，其超参数能够自动从训练数据中学习，不需要使用交叉验证等方法进行模型选择，从而减少了运算量。

在高斯过程理论中，高斯核对高斯过程模型起到了决定性作用，训练样本也是用于对其核进行训练，并且已有的国内外文献大多都使用传统径向基核函数[I训练，这会导致运算量大，可扩展性较差。据此，本文使用谱混合核取代传统高斯过程核，此核函数是通过将核的频谱密度建模为尺度位置的高斯混合而形成的，相对于径向基核，此核函数具有较强的外推能力，能适应分布更复杂的数据。

针对目前人脸验证的主要问题，本文在特征提取和分类环节进行了创新与改进，显著减少了所需训练样本，提高了训练和测试速度，使用LFW在训练后的模型上进行测试，测试准确度达到了 $9 8 . 7 \%$ 。

# 1 特征提取

人脸特征提取需要满足两个基本要求：其一，要找到最优特征，使其能够最大限度区分不同人脸。其二，提取到的特征维度要尽可能小，从而可以提高训练和测试速度。目前人脸特征提取主流算法有SIFT，LBP，HOG及Gabor。从理论上来说提取到的特征维度越大其准确度越高，文献[12]指出使用多尺度方法提取特征在一定程度上能提高算法准确度，但这会显著增加运算量，不利于工程实现。本文提出自适应多尺度特征提取方法能有效降低特征维度。

# 1.1特征定位

特征定位是特征提取的第一步，它指定了特征提取的位置，本文使用含标记人脸库[13]作为训练样本，从中学习各个标记位置的梯度方向，然后根据学习到的梯度方向可确定特征提取位置。

# 1.1.1特征定位原理分析

给定一个含 $\mathbf { \Sigma } _ { m }$ 个像素图像 $\pmb { d } \in \mathbb { R } ^ { m \times 1 }$ ，其中含有 $p$ 个手工标记，如图1(a)所示， $h$ 是一个特征提取器(在本文特指AMLBP),在训练阶段使用库中包含标记的人脸作为训练样本，设其为 $x _ { * }$ 。当检测到人脸时给定一个初始化标记 $x _ { \mathrm { { \scriptscriptstyle 0 } } }$ 称之为平均标记，如图1（b）所示，通过最小化式（1）可实现人脸特征定位。

$$
f ( x _ { 0 } + \Delta x ) = \parallel h ( d ( x _ { 0 } + \Delta x ) ) - \phi _ { * } \parallel _ { 2 } ^ { 2 }
$$

其中 $\phi _ { * } = h ( d ( X _ { * } ) )$ 表示在模板库人脸标记处的AMLBP特征值，$\Delta x$ 表示迭代步长。训练开始于 $x _ { \mathrm { { \scriptscriptstyle 0 } } }$ ，收敛于 $x _ { * }$ 。为使用梯度方法求导，将式（1）在 $x _ { \mathrm { { 0 } } }$ 处进行泰勒展开：

$$
f ( X _ { 0 } + \Delta { X } ) \approx f ( X _ { 0 } ) + J _ { f } ( X _ { 0 } ) ^ { T } \Delta { X } + \frac { 1 } { 2 } \Delta { X } ^ { T } H ( X _ { 0 } ) \Delta { X }
$$

其中 $J _ { f } ( X _ { 0 } )$ 和 $H ( x _ { 0 } )$ 是雅可比矩阵和海森矩阵。对式（2）关于$\Delta x$ 求偏导，并令其导数为零，即可得到关于 $x$ 的第一步更新：

$$
\Delta X _ { 1 } = - H ^ { - 1 } J _ { \mathrm { { \it f } } } = - 2 H ^ { - 1 } J _ { \mathrm { { \it n } } } ^ { T } ( \phi _ { 0 } - \phi _ { * } )
$$

在第一步梯度迭代过程中将上式看成 $\Delta \phi = \phi _ { \mathrm { 0 } } - \phi _ { \ast }$ 在矩阵$R _ { 0 } = - 2 H ^ { - 1 } J _ { h } ^ { T }$ 上的投影。为了避免计算海森矩阵和雅可比矩阵，将 $R _ { \mathrm { 0 } }$ 当作梯度方向，通过学习 $\Delta X _ { * } = X _ { * } - X _ { 0 }$ 和 $\Delta \phi _ { \mathrm { 0 } }$ 之间的线性回归可直接得到 $R _ { \mathrm { 0 } }$ ，将式（3）简化后可得

$$
\Delta X _ { \mathrm { 1 } } = R _ { \mathrm { 0 } } \phi _ { \mathrm { 0 } } + b _ { \mathrm { 0 } }
$$

其中 $b _ { \scriptscriptstyle 0 }$ 为偏置。对于特定的图像，使用牛顿法沿着梯度方向进行更新：

$$
\begin{array} { r } { { \boldsymbol { X } } _ { k } = { \boldsymbol { X } } _ { k - 1 } - 2 H ^ { - 1 } { \boldsymbol { J } } _ { h } ^ { T } ( \phi _ { k - 1 } - \phi _ { * } ) } \end{array}
$$

式（6）使用上一步学习到的 $\boldsymbol { R } _ { \scriptscriptstyle k - 1 }$ 和 $b _ { k - 1 }$ 确定新的迭代位置×k：

$$
\boldsymbol { X } _ { k } = \boldsymbol { X } _ { k - 1 } + \boldsymbol { R } _ { k - 1 } \boldsymbol { \phi } _ { k - 1 } + \boldsymbol { b } _ { k - 1 }
$$

![](images/6bf841154b67d6f6394b7238d0da758e41b353ed7bc7d5adf760101acdf2b796.jpg)  
图1 (a)为手工标记的人脸，(b)为使用人脸检测器初始化的标记

# 1.1.2学习梯度方向

本节主要描述如何从训练数据中学习 $R _ { k }$ 和 $b _ { k }$ 。设第 $i$ 张人脸图像为 $\lbrace d ^ { i } \rbrace$ 其相应的标记为 $\left\{ \begin{array} { l }  \boldsymbol { x } _ { * } ^ { i } \right\} \end{array}$ 。在每一步更新中式（6)会根据上一步学习到的 $\boldsymbol { R } _ { k - 1 }$ 和 $b _ { k - 1 }$ 使用 $x _ { * } ^ { i }$ 生成一对新的数据$\{ ~ \Delta x _ { * } ^ { i } , ~ \phi _ { k } ^ { i } \}$ 。 $R _ { k }$ 和 $b _ { \scriptscriptstyle k }$ 可通过最小化式（7）学习得到：

$$
\underset { { \boldsymbol { R } } _ { k } , { \boldsymbol { b } } _ { k } } { \arg \operatorname* { m i n } } \sum _ { \boldsymbol { d } ^ { i } } \sum _ { x _ { k } ^ { i } } \lVert \Delta x _ { * } ^ { k i } - { \boldsymbol { R } } _ { k } \phi _ { k } ^ { i } - { \boldsymbol { b } } _ { k } \rVert ^ { 2 }
$$

其中 $\Delta X _ { * } ^ { k i } = X _ { * } ^ { i } - X _ { k } ^ { i } \ , \phi _ { k } ^ { i } = h ( d ^ { i } ( X _ { k } ^ { i } ) )$ 。

以上的目标函数最小化问题可归结为一个无约束最优化问题，共轭梯度法是求解此问题的一种有效方法，仅需一阶导信息，从而可达到快速收敛的效果。

通过使用共轭梯度下降法求目标函数（式（7)）的最小值即可获取特征位置的梯度方向。当检测到人脸时，可根据其梯度方向定位，定位效果如图2所示。

![](images/e1f957da75a79d8a23b5debebb10fa986b78e47a2b26bc303cc5f63edb008bf6.jpg)  
图2特征定位图

# 1.2自适应尺度特征提取

考虑到人脸不同特征部位所含信息量不同，例如：眼睛所含特征最为敏感，对人脸识别贡献最大，因此在进行特征提取时此部位的特征提取尺度应该最大；反之，脸颊相对人脸识别贡献较小，所以其特征提取尺度应适当减小，从而可达到降低特征维度，但不减少信息量的效果。据此，本文提出自适应多尺度特征提取方法，此方法可根据特征敏感度对特征提取尺度进行自适应调整。

为了获取人脸特征敏感度，本文将Adaboost[12]训练出来的人脸特征与（1.1）获取到的特征进行映射，然后再根据各个弱分类器的分类错误率（本文将其视为敏感度）来确定各个特征提取尺度。实验结果（如图3所示）表明特征提取尺度为4时其分类效果能达到最佳。据此，本文将最大特征提取尺度定为4，于是将特征分为四类 $K = \{ k _ { 1 } , k _ { 2 } , k _ { 3 } , k _ { 4 } \}$ 。本文使用 Adaboost算法共训练出了200个人脸特征，并根据错误率将特征由低到高排序。将（1.2）获取到的特征归为四类，归类方法为：在待归类特征位置使用欧式距离搜索特征，距离其最近的特征所属类即为此特征所属类。式（8）（9）为具体提取方法，其中 $p ( \cdot )$ 表示特征所在位置， $D ( \cdot )$ 为欧式距离， $\boldsymbol { K } ( \cdot )$ 为 $h ( x _ { t } )$ 所对应的尺度， $p ( f ( x ) )$ 为使用(2.2)节特征定位方法获取到的特征位置，$p ( h ( x ) )$ 为 Adaboost 特征 $f$ 的位置。

$$
\operatorname* { m i n } _ { k ( h ( x ) ) } D ( p ( h ( x ) ) , p ( f ( x ) ) )
$$

$$
k ( f ( x ) ) = k ( h ( x ) )
$$

使用高斯金字塔提取多尺度特征：

$$
{ \cal L } ( x , y , s \sigma ) = G ( x , y , s \sigma ) * f ( x , y )
$$

$$
s = 2 ^ { 0 } , 2 ^ { 1 } , \cdot \cdot \cdot , 2 ^ { k _ { i } } \left( i = 1 , 2 , 3 , 4 \right)  \ , \quad G ( x , y , \sigma ) = \frac { 1 } { 2 \pi \sigma ^ { 2 } } e ^ { \frac { x ^ { 2 } + y ^ { 2 } } { 2 \sigma ^ { 2 } } }
$$

$L ( x , y , \sigma )$ 为图像高斯尺度空间，多尺度特征提取效果如图4所示。然后，在各个特征的高斯尺度空间提取其LBP特征，即可得到自适应多尺度特征。

本文使用高斯过程结合谱混合核函数对人脸分类，其特征提取尺度分别使用自适应尺度和单一尺度，并将其效果进行对比，对比结果如图5所示，从图可以分析出，随着特征提取尺度递增，其准确度也会随之增加，但其特征维度也会增加，运算效率会降低。然而，使用自适应尺度得到的分类准确度和$k = 4 \ , k = 5$ 得到的分类准确度相当，其平均尺度为2.6，显著降低了特征维度。自适应尺度映射如表一所示，其中特征标记号与图6中人脸特征标记号相对应。

![](images/515115b73721b068ad77d21be314dd07afa03c2204b0bc322f555329d14e1ecb.jpg)  
图3不同尺度提取到的特征识别效果对比

![](images/b39aca318c1a209587f7ee014370d353069265936ccd7ed0388354a31b6ae294.jpg)  
图4自适应尺度与单一尺度提取到的特征识别效果对比

![](images/2e261e7ca136bc534822d0940884942fd626c7a8fb5dcacc6d8c71fb88365429.jpg)  
图5多尺度特征提取效果

![](images/63b4f389fa80e45e11f4b8b646f53213b961b58d24f7b58f7e699c6149162d5d.jpg)  
图6人脸特征标记图

表1特征提取尺度映射  

<html><body><table><tr><td>特征点数目</td><td>特征标号</td><td>尺度</td></tr><tr><td>17</td><td>1-17</td><td>1</td></tr><tr><td>10</td><td>18-27</td><td>3</td></tr><tr><td>4</td><td>28-31</td><td>4</td></tr><tr><td>5</td><td>32-36</td><td>3</td></tr><tr><td>12</td><td>37-48</td><td>4</td></tr><tr><td>20</td><td>49-68</td><td>2</td></tr></table></body></html>

# 2 高斯过程模型

目前，人脸验证所使用的分类模型大多都是参数化分类模型[14-15]，其最大的局限性是需要预先设置好参数，参数设置好坏直接影响分类效果，并且对不同分布的人脸数据参数设置不一样，这会使得训练出来的模型在自然场景下进行人脸识别时性能表现较差[16]。

高斯过程作为一种非参数化随机过程能够适应真实场景下的复杂数据分布，不需要使用启发式方法或人工调节参数。并且，高斯过程是一种贝叶斯核机制模型，其闭式的边缘概率计算效率高，能克服过拟合，具有很强的鲁棒性。此外其超参数能自动从训练数据中学习。鉴于高斯过程模型的诸多优势，本文使用高斯过程模型作为分类器。

# 2.1高斯过程作为二分类器

设包含 $N$ 个训练样本的训练集为 $\mathbf { D } = \{ ( x _ { i } , y _ { i } ) \} _ { i = 1 } ^ { N }$ ，第 $i$ 个输入数据为 $X _ { i } \in R ^ { d }$ ，其相应的输出 $y _ { i } = \pm 1$ ，式（11）用于计算训练数据的联合概率。测试数据为 $\boldsymbol { X } _ { * } \in \boldsymbol { R } ^ { d }$ ，其相应输出为 $y _ { * }$ 。对于一个测试集中的任何一个元素 $x _ { * }$ ，其预测分布是一个 $n + 1$ 维高斯联合分布 $\mathbf { \Xi } ( \mathbf { \Lambda } _ { n } \mathbf { \Lambda } )$ 个训练样本和1个测试样本)。高斯分类核心思想是设置一个隐函数 $f ( \boldsymbol { x } )$ ，然后通过逻辑函数 $\pi ( x )$ 获取先验知识，并将回归模型输出为一个类概率（将区间 $( - \infty , \infty )$ 映射到[0,1])。预测过程共分为两个步骤：首先，计算关于测试集的隐变量布，式（14)；然后，使用隐变量分布计算概率预测值，式（15)。

$$
p ( \boldsymbol { y } \vert f ) = \prod _ { i = 1 } ^ { N } p ( y _ { i } \vert f _ { i } ) { = } \prod _ { i = 1 } ^ { N } \pi ( y _ { i } f _ { i } )
$$

$$
\pi ( x ) \triangleq p ( y = + 1 | x ) = \sigma ( f ( x ) )
$$

$$
p ( f \mid x , y ) = p ( y / f ) p ( f \mid x ) / \ p ( y / x )
$$

$$
p ( f _ { * } | x , y , x . ) = \int p ( f _ { * } | x , x . , f ) p ( f | x , y ) d f
$$

$$
\begin{array} { l } { \displaystyle \overline { { \pi } } ( x ) = p ( y _ { \ast } = + 1 \vert X , y , x _ { \ast } ) } \\ { \displaystyle \qquad = \int \sigma ( f _ { \ast } ) p ( f _ { \ast } \mid X , y , x _ { \ast } ) d f _ { \ast } } \end{array}
$$

将高斯过程作为二分类器，会使得似然函数 $p ( y | f )$ 不服从高斯分布，这会导致 $p ( f | y , x )$ 也不服从高斯分布，进而导致$p ( f _ { * } | x , y , x _ { * } )$ 不服从高斯分布，从而使得无法用积分方法计算$p ( f _ { * } | x , y , x _ { * } )$ ，于是用拉普拉斯方法对 $p ( f _ { * } | x , y , x _ { * } )$ 中的后验概率 $p ( f | y , x )$ 进行高斯逼近。

$$
q ( \boldsymbol { f } \mid \boldsymbol { X } , \boldsymbol { y } ) = N ( \hat { \boldsymbol { f } } , ( K ^ { - 1 } + W ) ^ { - 1 } )
$$

$$
\begin{array} { r } { \hat { \boldsymbol { f } } = \arg \operatorname* { m a x } _ { \boldsymbol { t } } \boldsymbol { p } ( \boldsymbol { t } | \boldsymbol { X } , \boldsymbol { y } ) , \boldsymbol { W } = - \nabla \nabla \log \boldsymbol { p } ( \boldsymbol { t } | \boldsymbol { X } , \boldsymbol { y } ) \big | _ { \boldsymbol { t } = \hat { \boldsymbol { f } } } } \end{array}
$$

从而可得到

$$
\log q ( \boldsymbol { y } | \boldsymbol { X } , \boldsymbol { \theta } ) = - \frac { 1 } { 2 } \hat { \boldsymbol { f } } ^ { T } K ^ { - 1 } \hat { \boldsymbol { f } } + \log p ( \boldsymbol { y } | \hat { \boldsymbol { f } } ) - \frac { 1 } { 2 } \mathrm { l o g } \left| \boldsymbol { B } \right|
$$

其中： $\mid B \mid = \mid K \mid \cdot \mid K ^ { - 1 } + W \mid = \mid I _ { n } + W ^ { \frac { 1 } { 2 } } K W ^ { \frac { 1 } { 2 } } \mid$ ， $\theta$ 为核函数的超参数，可通过共扼梯度算法最小化 $\log q ( \boldsymbol { y } \vert \boldsymbol { X } , \boldsymbol { \theta } )$ 获取。

# 2.1.1 高斯过程核函数

高斯过程作为一种核机制方法，其核函数完全决定了它的分类性能。对于核函数的研究目前是学术界的一大热点，平方指数核，吉布斯核，深度核[17]是目前主流核方法，但这些方法都只适用于数据量很小的训练样本，外推能力有限，并且其运算量大，对于 $n$ 个训练样本，需要 ${ \mathrm { O } } ( n \land 3 )$ 用于训练， ${ \mathrm { O } } ( n ^ { \land } 2 )$ （204号用于存储， $\ O ( n \land 2 )$ 用于预测。基于以上问题，本文将谱混合核函数用于高斯过程进行人脸验证。通过实验发现，此核函数能较好的适用于发现人脸模式并且具有较强的外推能力，在自然场景下进行人脸验证能表现出良好的性能，并且其简单的闭式形式使其可直接用于分析和推断。其简化形式为

$$
k _ { S M } ( x , x ^ { ' } | \theta ) =
$$

$$
\sum _ { q = 1 } ^ { Q } \omega _ { q } ^ { 2 } \frac { \lvert \sum _ { q } \rvert ^ { \frac { 1 } { 2 } } } { ( 2 \pi ) ^ { \frac { D } { 2 } } } \mathrm { e x p } ( - \frac { 1 } { 2 } \parallel \sum _ { q } ^ { \frac { 1 } { 2 } } ( x - \dot { x _ { \parallel } } ) \parallel ^ { 2 } ) \mathrm { c o s } \left. x - \dot { x _ { \perp } } , 2 \pi \mu _ { q } \right.
$$

文献[18]指出，此核函数包含了许多固定核，并且能以任意精度近似固定核函数。本文使用Multi-PIE人脸数据库对此核函数进行训练，并将其测试结果与传统核训练出的模型测试结果对比，对比结果如图7所示，从图可以看出：在相同虚警率条件下使用谱混合核方法进行人脸验证比其他核函数准确度要高，从而证明了此核函数的有效性。

![](images/6209e8aa68c594b0af60fdc47680113ba6de842e0bab2706ed87b7fcdd064134.jpg)  
图7谱混合核与传统核分类效果

# 3 实验与分析

实验平台配置为Intel酷睿i5处理器， $2 . 7 0 \mathrm { G H z }$ 主频，12G内存。使用 $\scriptstyle \mathbf { C } + +$ 语言编程，调用opencv2.4.9 对图像做预处理。使用3个人脸数据库进行实验，LFW，FERET和Multi-PIE（部分）人脸数据。LFW包含来自5750个人共13233张非限制场景下的人脸，其包含了人脸在自然场景下的各种姿态、表情、年龄、性别、发型以及其他参数的变化，是目前学术界公认的最具有挑战性的标准人脸库，本文将其用于测试。FERET包含21833张1040个人在同一场景，不同光照条件下的人脸灰度图，其包含了同一人脸的不同姿态和表情，是人脸识别领域应用最广泛的人脸数据库之一。Multi-PIE人脸数据库包含337个人在相同环境下不同姿态、光照和表情共750000张人脸，由于此人脸数据库未完全公开，只获取到了其中的20000张人脸，本文将其用于模型训练。

# 3.1实验流程

人脸验证流程如图8所示：a)将待验证人脸使用（2.1）节提出的方法从模板库中学习各个特征的梯度方向并将其用于特征定位；b)使用本文提出的自适应尺度方法在已定位特征处进行特征提取；c)计算所获取特征的相似度，本文使用欧式距离获取待验证特征相似度；d)将待验证特征相似度输入高斯模型即可得到分类结果。

![](images/047e97a7baecdcc1f52eec8524f6d5d9f26cefa15655161fc8c3b0b4f23f4b77.jpg)  
图8人脸验证流程

# 3.2 实验结果分析

本文使用自适应尺度对人脸进行特征提取以达到降维效果，使用高斯过程作为二分类器可显著减少训练样本，使用谱混合核取代原有平方指数核可使高斯过程模型外推能力更强，以下对各个环节进行逐一分析。

# 3.2.1自适应尺度降维效果分析

本文将自适应尺度与LE，LBP，SIFT，HOG，Gabor等特征提取算法在维度和准确度两方面进行对比，对比结果如表 2所示。从表中可知使用自适应尺度算法特征维度为 $1 . 5 ^ { * } 1 0 ^ { \wedge } 5$ ，相当于LE算法维度的1/4，但准确度比LE 算法高 $6 . 2 \%$ ；相当于Gabor算法维度的3/4,但准确度比Gabor算法高 $7 . 7 \%$ 。此实验结果有效的证明了自适应尺度方法能显著降低特征维度，但不会降低准确度。

表2特征维度对比  

<html><body><table><tr><td>特征提取方法</td><td>特征维度</td><td>准确度</td></tr><tr><td>LE</td><td>6*10^5</td><td>92.5%</td></tr><tr><td>LBP</td><td>4*10^5</td><td>92.5%</td></tr><tr><td>SIFT</td><td>5*10^5</td><td>91.9%</td></tr><tr><td>HOG</td><td>3*10^5</td><td>91.2%</td></tr><tr><td>Gabor</td><td>2*10^5</td><td>91.0%</td></tr><tr><td>MLBP</td><td>1.5*10^5</td><td>98.7%</td></tr></table></body></html>

# 3.2.2 高斯过程模型性能分析

本文使用高斯过程模型作为二分类器，将实验结果与现有的二分类器算法：SVM，逻辑回归 (LR)，以及Adaboost进行对比，对比结果如表3所示，从中可以分析出：使用高斯过程模型作为分类器，使用不同训练集进行训练其准确度能维持在$98 \%$ 以上，其他分类器准确度总体较低并且使用不同训练集进行训练其准确度存在较大波动。此实验结果能充分证明高斯过程模型能适应不同分布的数据，不需要对不同数据集针对性的设置参数。

表3不同分类器分类结果  

<html><body><table><tr><td rowspan="2">二分类器</td><td colspan="3">不同数据集（训练+测试）下的准确率</td></tr><tr><td>FERET+Multi-PIE</td><td>FERET+LFW</td><td>Multi-PIE+LFW</td></tr><tr><td>Adaboost</td><td>88.5%</td><td>75.3%</td><td>74.9%</td></tr><tr><td>SVM</td><td>90.2%</td><td>80.5%</td><td>81.6%</td></tr><tr><td>LR</td><td>83.3%</td><td>72.3%</td><td>73.5%</td></tr><tr><td>GP</td><td>98.7%</td><td>98.4%</td><td>98.6%</td></tr></table></body></html>

此外，使用高斯过程模型学习人脸特征可显著减少训练样本。为证明其有效性将其与现有主流深度学习人脸识别算法对比，对比结果如表4所示,从中可以看出使用高斯过程模型训练数据只需20K，其准确度可达到了 $9 8 . 7 \%$ ，与 facenet相比其准确度相同，但facenet所使用的数据量为 $4 9 4 \mathrm { k }$ 大约为高斯过程的 25 倍；与deepID，openface，DeepFace 等深度学习算法相比GP准确度要略高，并且大幅减少了训练样本。

表4与深度学习算法对比  

<html><body><table><tr><td>训练模型</td><td>训练集</td><td>数据量</td><td>准确度</td></tr><tr><td>Facenet[19]</td><td>CASIA</td><td>94K</td><td>98.7%</td></tr><tr><td>deepID[4]</td><td>Celeb-Faces</td><td>200K</td><td>97.27%</td></tr><tr><td>openface[20]</td><td>FaceScrub+CASIA</td><td>500K</td><td>91.9%</td></tr><tr><td>DeepFace[21]</td><td>SFC[22]</td><td>4.4M</td><td>97.5%</td></tr><tr><td>GP</td><td>FERET+Multi-PIE</td><td>20K</td><td>98.7%</td></tr></table></body></html>

# 3.2.3谱混合核函数的优越性

使用谱混合核取代原有平方指数核使得高斯过程分类器的外推能力更强。为证明此核函数在外推性能方面的优势，本文以FERET和Multi-PIE特定场景下的人脸作为训练样本，以LFW自然场景下的人脸作为测试样本，并将其与平方指数核函数进行对比。图9、10使用限制场景下的人脸作为训练样本，LFW人脸作为测试样本，从图中可以分析出使用谱混合核作为高斯核函数其准确度要显著高于平方指数核，从而表现出了谱混合核函数在外推性能方面的优越性，即：以限制场景下的人脸为训练样本，得到的模型能够在LFW自然场景下的人脸测试集中表现出较好的性能。此外，本文将LFW人脸数据分为训练和测试两部分，进行训练并测试，测试结果如图11所示，从图可以分析出使用谱混合核的效果要显著高于平方指数核。图12为谱混合核在不同训练数据和测试数据上的性能，从中可获知无论使用自然场景下的训练集还是限制场景下的训练集所训练出的模型都能获得较好的测试结果。

![](images/ab605860ac99680a08fc12dbc0ef952089d6117f1b0dcca784c264786b3c649b.jpg)  
图9 FERET训练--LFW测试

![](images/9ac7cf7202e2557310e0bcd893d0d261f96f1449da60b521c07b6fe7b06c2c4c.jpg)  
图10Multi-PIE（部分）训练--LFW测试

![](images/91e53d0101b2c103a9896614cce6eb075bf26bdd731670a648191efb9b18331b.jpg)  
图11LFW（部分）训练--LFW（部分）测试

![](images/7cac057280c58d50780de6ca942b758e947898752bc36f1b2355891aa347506e.jpg)  
图12谱混合核在不同训练集上的性能

# 4 结束语

通过以上实验验证与分析，可得出结论：a)本文提出自适应多尺度算法用于提取人脸特征，能自适应人脸面部信息呈不均匀分部的特性，此方法相对于传统方法显著降低了特征维度；b)本文使用高斯过程模型进行训练，充分利用了高斯过程的非参数化随机过程的特性，不需要根据不同的训练数据而修改其参数从而达到了在减少训练数据样本的同时增强了整个人脸验证系统的鲁棒性;c)使用谱混合核函数取代传统的径向基函数能增强高斯过程模型的外推性能，使用限制场景下的人脸样本训练出的模型对自然场景下的人脸进行测试也获得了较高的准确度。

本文所使用的人脸验证算法能够显著提高人脸验证训练速度和测试速度并且所需训练样本少，不需要依赖平台和框架便于迁移布署。

参考文献：   
[1]Kumar N, Berg A C,Belhumeur PN,et al. Atribute and simile classifiers for face verification [C]// Proc of IEEE International Conference on Computer Vision. 2010:365-372.   
[2]Huang G B.Learning hierarchical representations for face verification with convolutional deep belief networks [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2012: 2518-2525.   
[3]Milanfar HJS P.Face Verification Using the LARK Face,Representation [J].IEEE Trans on InformationForensics& Security,2011,6(4):1275-1286.   
[4]Sun Y,Wang X,Tang X.Deep Learning Face Representation from Predicting 10,0oo Classes [C]// Proc of IEEE Conference on Computer Vision and Pattrn Recognition. Washington DC: IEEE Computer Society, 2014: 1891-1898.   
[5]Sun Y,Liang D, Wang X,et al. DeepID3: face recognition with very deep neural networks [J]. Computer Science, 2015.   
[6]Sun Y,Wang X, Tang X. Deep Learning Face Representation by Joint Identification-Verification[J].2014,27:1988-1996.   
[7]Ben X,Meng W, Yan R,et al.An improved biometrics technique based on metric learning approach [J]. Neurocomputing,2012,97(1): 44-51.   
[8]Zhu Z,Luo P,Wang X,et al.Deep learning identity-preserving face space [C]// Proc ofIEEE InternationalConference on Computer Vision. 2013: 113- 120.   
[9]Sun Y,Wang X,Tang X.Hybrid deep learning for face verification [C]/ Proc of IEEE International Conference on Computer Vision.2014:1489- 1496.   
[10] Chen D,Cao X,Wang L,etal. Bayesian face revisited: a joint formulation [C]//Proc of European Conference on Computer Vision. Springer-Verlag, 2012: 566-579.   
[11] Kim S J,Magnani A,Boyd S.Optimal kernel selection in Kermel Fisher discriminant analysis [C]// Proc of International Conference on Machine Learning.2006: 465-472.   
[12] ChenD,Cao X,WenF,et al. Blessing of dimensionality: high-dimensional feature and its efficient compression for face verification[C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2013: 3025-3032.   
[13] Sagonas C,Tzimiropoulos G,Zafeiriou S,et al.30o Faces in-the-Wild Challenge: The First Facial Landmark Localization Challenge [C]/ Proc of IEEE International Conference on Computer Vision Workshops.Washington DC: IEEE Computer Society,2013:397-403.   
[14] Jones M J,Viola P.Robust Real-time Object Detection[J]. International Journal of Computer Vision,2001,57(2): 87.   
[15] Zhu Z,Luo P,WangX,etal.Deep Learning Identity-Preserving Face Space [C]//Proc ofIEEE International Conference on Computer Vision.2013: 113- 120.   
[16] Wright J,Hua G.Implicit elastic matching with random projections for posevariant face recognition [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2009:1502-1509.   
[17] Wilson A G,Hu Z,Salakhutdinov R,et al.Deep kernel learning [J]. Computer Science,2015.   
[18] Wilson AG.Covariance kernels for fast automatic pattern discovery and extrapolation with Gaussian processes [J]. University of Cambridge,2014.   
[19] SchroffF,Kalenichenko D,Philbin J.FaceNet: Aunified embedding for face recognition and clustering [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society, 2015: 815-823.   
[20] Amos B,Ludwiczuk B,Satyanarayanan M. Openface:A general-purpose face recognition library with mobile applications [J].CMU School of Computer Science,2016.   
[21] Taigman Y,Yang M,Ranzato M,et al.DeepFace:Closing the Gap to Human-Level Performance in Face Verification [C]//Computer Vision and Pattern Recognition.2014:1701-1708.   
[22] Ng HW,Winkler S.A data-driven approach to cleaning large face datasets [C]// Proc of IEEE International Conference on Image Processing. 2015: 343-347.