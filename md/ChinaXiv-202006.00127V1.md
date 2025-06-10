# 基于Sentinel-1A合成孔径雷达数据和全卷积网络的城市建设用地监测方法研究

卢文路¹,²，刘志锋1,²，何春阳1,²，夏沛1,2（1北京师范大学地表过程与资源生态国家重点实验室,人与环境系统可持续研究中心,北京100875；2北京师范大学地理科学学部自然资源学院,北京100875)

摘要：Sentinel-1A合成孔径雷达数据不受云、雾等天气条件的影响并具有丰富的纹理信息，为提取城市建设用地信息提供了一种新的数据源。本文发展了一种基于Sentinel-1A合成孔径雷达数据和全卷积网络的城市建设用地监测方法。该方法的优势主要在于可以有效复合不同极化方式下的 Sentinel-1A合成孔径雷达数据和综合集成多尺度特征。在甘肃省张掖市甘州区的应用表明，该方法的提取结果总体精度为 $9 2 . 5 0 \%$ ,Kappa系数为0.85。与现有方法“KTH-Pavia城市提取器”相比,Kappa系数提高了 $3 7 . 1 0 \%$ ，总体精度提高了 $1 1 . 5 0 \%$ 。因此，该方法具有良好的应用潜力。

关键词：Sentinel-1A；哨兵数据；合成孔径雷达；城市建设用地；全卷积网络；深度学习文章编号：

城市建设用地是指包括居住用地、商业服务业设施用地、工业用地、道路交通设施用地和公用设施用地在内的城市土地[1]。伴随着经济的高速发展与城市人口的持续增长，中国正在经历大规模的城市建设用地扩展过程[2-3]。该过程一方面促进了社会发展并提高了城市居民的人类福祉，另一方面也带来了水资源短缺、空气污染和城市热岛效应等一系列问题[4-8]。及时、准确地提取城市建设用地信息是理解并评价城市扩展过程对生态环境影响的基础,对于促进区域可持续发展具有重要意义[9-10] 。

光学遥感数据是当前获取城市建设用地信息的主要数据源。包括Landsat数据、中巴资源卫星数据和高分系列卫星数据等中高分辨率遥感数据，以及 MODIS（Moderate Resolution Imaging Spectroradi-ometer)数据、DMSP-OLS（Defense Meteorological Sat-elliteProgram's Operational Linescan System）夜间灯光数据和NPP-VIIRS（NationalPolar-orbitingPartner-ship's Visible Infrared Imaging Radiometer Suite）夜间灯光数据等中低分辨率遥感数据在内的光学遥感数据已被广泛用于城市建设用地的提取[11-13]。例如,刘纪远等[2]以Landsat 数据为主要数据源,获取了中国20世纪80年代～2010年的城市建设用地信息。HE 等[5]复合 MODIS 数据以及DMSP-OLS、NPP-VIIRS夜间灯光数据获取了中国1992—2012年城市建设用地信息。但光学遥感易受云、雾等天气条件影响，同时其所包含的城市地物纹理信息不足，在用于获取城市建设用地信息时仍受到限制。

合成孔径雷达（synthetic aperture radar，SAR）数据为提取城市建设用地信息提供了一种新数据源。SAR是一种高分辨率微波成像雷达，主要原理是通过小孔径雷达天线沿直线不断移动，在不同位置上接收同一地物的回波信号并通过数据处理合成，从而等效为一个大孔径天线，实现高分辨率成像[14]。SAR有着全天候、全天时工作能力,雷达天线所接收的雷达波为后向散射信号。在城市中，平顶建筑、街道等对雷达波产生镜面反射，相较周围地物呈暗色调，建筑物的立体结构则会产生“角反射器”效应增强回波信号，从而在影像上表现出丰富的纹理特征[15]。此外,数据的多极化类型可以反映散射体结构。因此，雷达数据适合用于城市建设用地的提取[16-17]。已有相关研究所采用的 SAR 数据主要包括 Radarsat $2 ^ { \left[ 1 8 - 1 9 \right] }$ 、ENVISAT[20-21]、ERS-$1 / - 2 ^ { [ 2 2 - 2 3 ] }$ 和 TeraSAR- $\cdot \mathrm { X } ^ { [ 2 4 - 2 5 ] }$ 。但 $\mathrm { E R S } - 1 / - 2$ 、ENVISAT等早期卫星已停止工作,TeraSAR-X、Ra-darsat-2等获取的数据价格昂贵，限制了SAR数据的进一步应用[26]

Sentinel-1A数据因具有免费、便捷获取等优势，已成为一种被广泛应用的 SAR 数据源[27]。2014 年4月3日发射的Sentinel-1A卫星搭载了C波段合成孔径雷达,重访周期为 $1 2 ~ \mathrm { d } ^ { [ 2 8 - 2 9 ] }$ 。Sentinel-1A 数据包含多种极化类型，能以较大幅宽实现全球陆地覆盖，兼有重返周期短和免费获取等突出优势，在城市建设用地提取研究中被广泛应用[30-32]。例如,BAN等[33]以 Sentinel-1A为主要数据源,在全球范围内提取了十个代表性城市的建设用地信息。但基于Sen-tinel-1A数据提取城市建设用地的现有方法还存在明显不足[34-35]。例如，GAMBA等[36-37]采用的KTH-Pavia城市建设用地提取方法主要通过复合空间自相关指数与灰度共生矩阵提取城市建设用地信息，该方法未能充分融合Sentinel-1A数据的不同极化类型和不同尺度的纹理信息，阈值的选取也比较主观，提取效果有较大提升空间。

全卷积网络提供了提取城市建设用地信息的新途径。全卷积网络是LONG 等[38]于2015 年在卷积神经网络基础上发展出的一种采取“像元到像元”图像识别模式的深度学习网络结构。全卷积网络主要由卷积层和激活层组成，继承了卷积神经网络的基本结构。其中，卷积层能够识别图像局部特征，激活层可以有效表达非线性特征[39-40]。通过多个卷积层和激活层交替传递信息，全卷积网络能有效复合多源信息，综合集成多尺度特征，从而对地物进行准确分类[41-43]。近年来,已有研究人员利用全卷积网络开展了基于光学遥感影像的城市建设用地提取研究,且取得了良好的效果。例如,FU等[44]利用全卷积网络和GF-2数据提取了北京东北部城市建设用地；ZHANG等[45]利用全卷积网络和WorldView高分影像数据获取了北京市海淀区与西城区城市建设用地信息。但利用全卷积网络和Sentinel-1A数据提取城市建设用地信息的研究方法仍待探索。

本文旨在发展一种利用全卷积网络的城市建设用地监测方法，基于Sentinel-1A合成孔径雷达数据实现城市建设用地的有效提取。该方法不仅能充分发挥Sentinel-1A合成孔径雷达数据的优势，同时具

备良好的应用潜力。

# 研究区概况

研究区位于中国甘肃省张掖市甘州区，地理位置为 $1 0 0 ^ { \circ } 2 2 ^ { \prime } 1 5 ^ { \prime \prime } \sim 1 0 0 ^ { \circ } 3 2 ^ { \prime } 2 0 ^ { \prime \prime } \mathrm { E }$ ? $3 8 ^ { \circ } 5 4 ^ { \prime } 3 1 ^ { \prime \prime } \sim 3 8 ^ { \circ } 5 8 ^ { \prime }$ ${ 5 4 ^ { \prime \prime } \mathrm { N } }$ （图1）。研究区地物中的裸地与城市建设用地光谱特征相近，易导致混分问题。而张掖市是中国绿洲城市土地利用/覆盖变化研究的热点城市[46]在"西部大开发”等政策的推动下，随着经济和人口规模的高速增长，该区域近年来经历了快速的城市建设用地扩张过程[47-49]。综上,研究区适于开展基于Sentinel-1A合成孔径雷达数据的城市建设用地提取方法研究。

# 2数据

所使用的Sentinel-1A合成孔径雷达数据来源于欧洲航空局哥白尼全球对地观测项目公开发布的Sentinel-1A 数据集（https://scihub.copernicus.eu/）。Sentinel-1A合成孔径雷达包括4种工作模式，分别是条带模式（StripMapMode，SM）、干涉宽幅模式（InterferometricWideSwath,IW）超宽幅模式（ExtraWide Swath,EW）、波模式（Wave Mode,WV）[29]。根据数据的可获取性与空间分辨率，选择使用IW模式数据,该模式为卫星默认的对地观测模式，幅宽$2 5 0 ~ \mathrm { k m }$ ,空间分辨率为 $5 \mathrm { ~ m ~ } \times 2 0 \mathrm { ~ m ~ }$ ，极化方式包括VH(交叉极化)与VV(垂直同极化)2种[27]。数据获取时间为2018年2月5日，空间分辨率重采样为$1 0 \mathrm { ~ m ~ } \times 1 0 \mathrm { ~ m ~ }$ 。参考BAN等[37]的研究,经过辐射校正、斑点噪声抑制和几何校正等预处理后，将DV值标准化到 $0 \sim 2 5 5$ 之间。合并2种极化方式为双波段影像数据，VH极化数据作为第一波段，VV极化数据作为第二波段。

用于获取训练样本和精度评价的高分辨率遥感影像数据来源于GoogleEarth平台提供的DigitalGlobe 数据（http://www.digitalglobe.com/）,空间分辨率约为 $7 . 4 \mathrm { ~ m ~ }$ ,影像拍摄时间为2018年3月7日。基于高分影像数据进行人工目视解译分类出城市与非城市训练样本。为确保精度，于2018年7月1\~2日对研究区开展了实地调查，结合调查结果对目视解译结果进行修正。最终获得的地面真值用于全卷积网络的训练和提取结果的精度评价。

![](images/c6dee910befc8a3c212973e8ba1ba420d7a133113ec57b10ea52262450cefbcd.jpg)  
图1 研究区

![](images/105512bfff3ecd2e0df1c2018f90831b519a6d9137b8f28d22efa1e742658390.jpg)  
Fig.1The study area   
图2技术路线Fig.2Flowchart

# 3方法

# 3.1构建全卷积网络

参考LONG 等[38]和 SZEGEDY 等[50]的研究,构建了一个全卷积网络用以提取城市建设用地信息（图2）。该网络的基本思路是利用输入层复合不同极化方式的 Sentinel-1A数据,而后利用基于Inception 结构[50]的卷积层、激活层和连接层获取不同尺度的纹理特征，最后通过分类器提取出城市建设用地信息（图2a）。

为了确定卷积核的大小和卷积层的层数，利用验证集对基于不同大小卷积核和不同层数卷积层构建的网络进行了测试，根据分类精度和运行效率，最终选择使用由五个Inception 结构组成的深度全卷积网络结构（图2b）。模型的输入层接收包括VH和VV2种极化方式的Sentinel-1A数据。卷积层的3种卷积核大小分别为 $1 \times 1 . 3 \times 3$ 和 $5 \times 5$ ,用于获取不同尺度的特征信息。卷积层与输入层的关系可用下式表示。

$$
C o n v _ { i , j } ^ { l , r } = \sum _ { I } ^ { N _ { 0 } } \sum _ { j } ^ { K _ { r } \times K _ { r } } ( \mathbf { \boldsymbol { W } } _ { I , i } ^ { l , r } \times I n p \mathbf { \boldsymbol { u } } t _ { I , j } ^ { l } ) + B i a s _ { i } ^ { l , r }
$$

式中： $C o n v _ { i , j } ^ { l , r }$ 表示第 $l$ 个卷积层的第 $\boldsymbol { r }$ 种卷积核中第$i$ 个波段第 $j$ 个像元的 $D N$ 值； $I n p u t _ { I , j } ^ { l }$ 表示第 $l$ 层输入数据中第 $I$ 个波段第 $j$ 个像元的 $D N$ 值; $\boldsymbol { W } _ { I , i } ^ { l , r }$ 表示该卷积层的权值; $B i a s _ { i } ^ { l , r }$ 表示偏置项; $N _ { \mathrm { o } }$ 表示输人数据的波段数； $K _ { r }$ 表示第 $\boldsymbol { r }$ 种卷积核的大小。连结层用于融合上一个卷积层中3种卷积核所提取的信息，连结层的输出结果作为下一个卷积层的输入数据。连结层与上一层卷积层的关系可用下式表示。

$$
\begin{array} { r l r } & { \ f ( \ C o n v _ { i , j } ^ { l , 1 } ) } & { i \leqslant m } \\ & { \ } & \\ { C o n c _ { i , j } ^ { l } = } & { \ f ( \ C o n v _ { i - m , j } ^ { l , 2 } ) } & { m < i \leqslant m + n } \\ & { \ } & \\ & { \ f ( \ C o n v _ { i - m - n , j } ^ { l , 3 } ) } & { m + n < i \leqslant m + n + k } \end{array}
$$

式中： $C o n c _ { i , j } ^ { l }$ 表示第 $l$ 个连结层中第 $i$ 个波段第 $j$ 个像元的 $D N$ 值； $m , n , k$ 分别代表该层三种卷积核的数量 $\smash { \operatorname { \mathrm { : } } f ( x ) }$ 表示激活函数，所使用的激活函数是标准的修正线性单元（RectifiedLinearUnit,ReLu），可表示为：

$$
f ( x ) = \operatorname* { m a x } ( 0 , x )
$$

设置多个Inception结构的目的是增大有效感受野，提高全卷积网络对多尺度特征信息的识别能

力。最后两个卷积核获得各像元被分类为城市和非城市的概率，可用下式表示。

$$
U r b a n _ { j } = \left\{ \begin{array} { c c } { { 1 , } } & { { O u t p u t _ { j } ^ { u r b a n } > O u t p u t _ { j } ^ { n o n - u r b a n } } } \\ { { } } & { { } } \\ { { 0 , } } & { { O t h e r w i s e } } \end{array} \right.
$$

式中： $U r b a n _ { j }$ 表示输出层中第 $j$ 个像元是否为城市建设用地，1为城市建设用地，0为非城市建设用地;$O u t p u t _ { j } ^ { u r b a n }$ 表示第 $j$ 个像元为城市建设用地的概率；$O u t p u t _ { j } ^ { n o n - u r b a n }$ 表示第 $j$ 个像元为非城市建设用地的概率，可通过下式计算。

$$
O u t p u t _ { j } ^ { u r b a n } \ = f ( \ \sum _ { i } ^ { m + n + k } ( \boldsymbol { W } _ { i } ^ { u r b a n } \times C o n c _ { i , j } ^ { 5 } ) \ +
$$

$$
B i a s ^ { u r b a n } )
$$

$$
O u t p u t _ { j } ^ { n o n - u r b a n } \ = f ( \ \sum _ { i } ^ { m ^ { + n + k } } ( \ W _ { i } ^ { n o n - u r b a n } \ \times { C o n c _ { i , j } ^ { 5 } } ) \ +
$$

$$
B i a s ^ { n o n - u r b a n } )
$$

式中： $\mathbb { W } _ { i } ^ { u r b a n }$ 和 $\boldsymbol { W } _ { i } ^ { n o n - u r b a n }$ 表示权值; $B i a s ^ { u r b a n }$ 和$B i a s ^ { n o n - u r b a n }$ 表示偏置项。上述全卷积网络的构建依托Convolutional Architecture forFast Feature Embed-ding(Caffe）深度学习平台实现[51] 。

# 3.2 训练全卷积网络

训练全卷积网络的目的是求算所构建的全卷积网络中权值的全局最优解。基本原理是以损失函数最小为求解目标，利用优化算法迭代求解最优权值。步骤主要包括选择训练样本、确定损失函数和设置优化算法、迭代参数三个基本步骤。首先，以GoogleEarth高分影像数据为基础，通过目视解译提取出城市与非城市训练样本图像，并结合野外调查进行修正。将整个训练样本图像裁剪为 $3 2 \times 3 2$ 像素大小的图像块，共计1534 块。按照 $8 : 2$ 比例随机划分训练集与验证集，获得训练集1226块，验证集308块。

其次,参考LONG等[38]的研究,在全卷积网络的输出层后加入用于计算损失函数的SoftmaxWith-Loss 层。损失函数可用下式表示[51]

$$
l ( \boldsymbol { y } , \boldsymbol { z } ) = \log \sum _ { \mathrm { j } } \mathrm { e } ^ { z _ { j } } - z _ { y }
$$

式中： $z$ 表示SoftmaxWithLoss层的输入; $l ( \boldsymbol { y } , \boldsymbol { z } )$ 表示$z$ 的损失函数; $z _ { j }$ 表示第 $j$ 个类别的预测结果； $y$ 表示训练样本中 $z$ 的类别。

最后,参考LONG 等[38]的研究,确定了优化算法与迭代参数。优化算法使用小批次随机梯度下降法（mini-batch Stochastic Gradient Descent）,即在每次迭代中使用不同的小批次训练数据计算后向传播梯度，并在迭代过程中不断减小参数修正值直到将损失降至最低。超参数是根据经验值和模型实际训练效果获取,初始学习率(base_lr)设为 $8 \times 1 0 ^ { - 9 }$ ,批次大小（batchsize)设为8,学习率下降方式(lr_poli-cy）为“step”,迭代步长（stepsize）设为5O00，衰减量（Gamma）设为0.99，动量（Momentum）设为0.99。利用训练后的全卷积网络，基于Sentinel-1A数据提取出了研究区2018年城市建设用地信息。

# 4结果

为检验本方法的提取效果,参考JANSSEN 等[52]的研究，采用分层随机抽样的样本点检验方法，在整个研究区分别选取了100个城市样本点和100个非城市样本点，结合同期高分辨率遥感影像，通过构建混淆矩阵并计算Kappa系数、总体精度、制图精度和用户精度等主要评价指标对提取结果进行精度评价（表1)。结果表明，基于全卷积网络提取的城市建设用地Kappa系数达到0.85，总体精度、制图精度与用户精度均在 $9 0 \%$ 以上，说明提取结果可以准确、可靠

# 表1基于全卷积网络的城市建设用地提取结果的精度评价

Tab.1Accuracy assessment of urban construction land extraction result based on fully convolutional network   

<html><body><table><tr><td colspan="2">参考图像</td></tr><tr><td colspan="2">城市建设 非城市建设 总和 用地(像元) 用地(像元) （像元）</td></tr><tr><td>城市建设用地(像元)</td><td>96 4 100</td></tr><tr><td>非城市建设用地(像元) 11 分类图像</td><td>89 100</td></tr><tr><td>总和(像元) 107</td><td>93 200</td></tr><tr><td colspan="2">总体精度=92.50% Kappa=0.85</td></tr><tr><td colspan="2">制图精度(漏分误差)</td></tr><tr><td colspan="2">城市建设用地 89.72%(10.28%)</td></tr></table></body></html>

地反映研究区城市建设用地的空间格局。

提取结果表明，张掖市甘州区2018年建设用地面积为 $4 ~ 0 0 6 ~ \mathrm { h m } ^ { 2 }$ ,约占区域总面积的 $20 \%$ （图3）。城市建设用地斑块的面积总体处于 $0 . 0 1 \sim 1 ~ \mathrm { h m } ^ { 2 }$ 之间,数量约占斑块总量的 $70 \%$ （图3b）。面积低于$0 . 0 1 \ \mathrm { h m } ^ { 2 }$ 和超过 $1 0 \ \mathrm { h m } ^ { 2 }$ 的斑块较少,数量占比均低于 $10 \%$ （图3b)。城市建设用地主要分布在正西和东北方向，面积均超过了 $8 0 0 \ \mathrm { h m } ^ { 2 }$ ;而在正北与正南方向较少，均低于 $3 0 0 \ \mathrm { h m } ^ { 2 }$ （图4b）。距离城市中心$2 \sim 4 ~ \mathrm { k m }$ 的圈层是城市建设用地分布最集中的区域,超过 $6 5 0 \ \mathrm { h m } ^ { 2 }$ ;而距离 $9 ~ \mathrm { k m }$ 以外的圈层城市建设用地的面积很少（图4c）。

![](images/1edc8ef8cebc5254d69ac8110843313d3a212a4b8c30700b49229e01c8d222ed.jpg)  
(a)城市建设用地提取结果  
图3基于全卷积网络的城市建设用地提取结果  
Fig.3Urban construction land extraction result based on fully convolutional network

![](images/6ae035c0f064e3ea852d43b6869f52d50369229c3550d10589370651e83b9026.jpg)  
Fig.4Spatial patterns of urban construction land in Ganzhou district，Zhangye in 2018

![](images/352219bf62ef7a321253ed901741a0954a08a709c66c7c6f367f96990b11ce69.jpg)  
图42018年张掖市甘州区建设用地空间分布特征  
图5基于KTH-Pavia方法的城市建设用地提取结果  
Fig.5Urban construction land extraction result based on KTH-Pavia urban extractor

# 5讨论

# 5.1新方法的优势和特点

在现有方法中,GAMBA等[36-37]发展的 KTH-Pavia方法是基于Sentinel-1A数据提取城市建设用地信息的最常用方法。为比较全卷积网络与现有方法的提取效果，首先基于Sentinel-1A数据，使用KTH-Pavia方法提取出了研究区内的城市建设用地（图5），然后在提取结果中对城市建设用地与非城市建设用地像元进行分层随机抽样，两类像元各抽取了100个验证点进行精度评价，最后通过构建混淆矩阵后计算了精度评价指标（表2）。

利用全卷积网络提取的城市建设用地结果在空间形态上更接近真实地物。提取结果形态完整，可以清晰、准确地描绘城市建设用地外部轮廓，能够很好地反映城市建设用地的整体形态（图3a，图6a5）。

# 表2基于KTH-Pavia方法的城市建设用地提取结果的精度评价

Tab.2Accuracy assessment of urban construction land extraction result based on KTH-Pavia urban extractor   

<html><body><table><tr><td rowspan="2"></td><td colspan="2">参考图像</td></tr><tr><td>城市建设 用地(像元)</td><td>非城市建设 总和 用地(像元) (像元)</td></tr><tr><td rowspan="4">分类图像</td><td>城市建设用地(像元) 93</td><td>7 100</td></tr><tr><td>非城市建设用地(像元） 31</td><td>69 100</td></tr><tr><td>总和(像元) 124</td><td>76 200</td></tr><tr><td colspan="2">总体精度=81.00% Kappa=0.62</td></tr><tr><td></td><td>制图精度(漏分误差)</td><td>用户精度(错分误差)</td></tr><tr><td>城市建设用地</td><td>75.00%(25.00%)</td><td>93.00%(7.00%)</td></tr><tr><td>非城市建设用地</td><td>90.79% (9.21%)</td><td>69.00%(31.00%)</td></tr></table></body></html>

城市内部建成区集中连片的分布形态得到了清晰反映，提取结果空间结构紧凑、完整（图6b5）。利用KTH-Pavia方法得到的提取结果较为零散，城市建设用地轮廓不清晰，该问题在西部区域尤为明显，大量城市建设用地未被有效提取（图5，图6a7）。且

![](images/b980278b4bd28dd5e9a2db249dc2539b127f590c6b449c1b2f7e6794745c299e.jpg)  
卢文路等：基于 Sentinel-1A合成孔径雷达数据和全卷积网络的城市建设用地监测方法研究  
图6结果对比Fig.6Results comparison

注：范围为图1中A、B两个缩放窗口。al和bl为真彩色合成影像;a2和b2为合成孔径雷达VH极化数据;a3 和b3为合成孔径雷达 VV极化数据;a4 和b4 为目视解译获取的真值;a5和b5为全卷积网络提取结果,a6和b6是全卷积网络提取结果与真值的对比;a7和b7为 KTH-Pavia提取结果,a8 和b8是KTH-Pavia 提取结果与真值的对比

城市建设用地内部空间结构松散，漏分问题严重，不能有效反映地物的真实空间格局（图6b7）。利用全卷积网络提取的城市建设用地分类精度更高（表1，表2）。利用全卷积网络得到的城市建设用地提取结果Kappa系数达到O.85，利用KTH-Pavia方法提取的城市建设用地Kappa系数为0.62，前者比后者高出约 $3 7 \%$ 。同时，全卷积网络提取结果的总体精度达到 $9 2 . 5 0 \%$ ，比KTH-Pavia方法提取结果的总体精度 $8 1 . 0 0 \%$ )高出 $1 1 \%$ 以上。全卷积网络提取结果的制图精度达到 $8 9 . 7 2 \%$ ，而KTH-Pavia方法仅为$7 5 . 0 0 \%$ ,前者比后者高出近 $1 5 \%$ 。

基于全卷积网络的城市建设用地提取结果拥有更高精度的主要原因，是全卷积网络在融合和提取Sentinel-1A数据多极化类型与多尺度纹理信息方面有着明显优势。

首先，全卷积网络支持不同层数和大小的数据输入，可在提取过程中充分融合不同极化方式数据所体现的地物散射特征，因此提取结果更加接近实际地物（图2b，图6a1、6a4、6a5、6a6）。而KTH-Pavia在图像信息提取过程中无法对数据的不同极化方式的进行融合，导致局部提取结果仅反映单一极化方式的纹理特征，从而无法较好地抑制漏分问题（图6a2、6a3、6a7、6a8）。

其次，全卷积网络包含多层卷积结构，能够在不同尺度上对纹理信息进行提取，可充分发挥Senti-nel-1A数据纹理信息丰富的优势（图2b）。受散射体结构影响，雷达数据会在局部出现异常值（如建筑物的“角反射器”效应会产生极端高值），而全卷积网络对多尺度信息的充分融合减弱了异常值引发的负面影响，从而有效抑制了漏分问题(图6）。卷积核的作用等效于“激活”与其结构相似的图像特征，多尺度卷积核的使用有效提高了边缘信息与纹理特征对分类结果的贡献[53]。经过充分训练后，全卷积网络可以有效表征城市地物不同尺度的纹理特征,充分抑制局部异常值影响。相比之下，KTH-Pavia方法则依赖灰度共生矩阵提取单一尺度纹理信息，导致提取结果趋于破碎并出现明显的漏分问题(图6)。

# 5.2展望

本研究发展的全卷积网络不仅能够充分发挥Sentinel-1A数据在城市建设用地提取方面的应用潜力，并且具备深度学习方法的迁移学习能力，可以应用于不同传感器和不同分辨率的数据，在基于诸如

TerraSAR-X、Radarsat-2等不同SAR数据源的城市建设用地提取方面具有很好的应用潜力。但目前的网络结构仍略显简单，且所使用的训练样本数量有限，使得模型在应用于不同地区的城市建设用地提取时可能尚不具有理想的泛化能力。

未来应根据不同地区的Sentinel-1A数据特点对全卷积网络结构进行适当微调，输入不同代表性区域的样本对网络进行训练，以提高该网络的泛化能力，籍此则可利用调整后的网络在更大尺度上实现城市建设用地的快速、高效提取。

# 6结论

本文通过构建并训练全卷积网络发展了一种基于Sentinel-1A合成孔径雷达数据监测城市建设用地的新方法，使用该方法提取了张掖市甘州区2018年的城市建设用地。提取结果总体精度为 $9 2 . 5 0 \%$ ，Kappa系数为0.85。与现有方法中应用最广泛的KTH-Pavia方法相比,Kappa系数提高了 $3 7 . 1 0 \%$ ，总体精度提高了 $1 1 . 5 0 \%$ 。方法的优势主要在于使用全卷积网络充分融合Sentinel-1A数据的不同极化方式和多尺度特征，从而提高分类精度。

提取结果表明研究区2018年城市建设用地面积为 $4 0 0 6 \mathrm { h m } ^ { 2 }$ ,斑块面积集中于 $0 . 0 1 \sim 1 ~ \mathrm { h m } ^ { 2 }$ 之间。城市主要分布在正西和东北方向，距离城市中心 $2 \sim 4$ $\mathrm { k m }$ 的圈层是城市建设用地分布最集中的区域。

本文所发展的方法不仅适用于Sentinel-1A数据，对于不同的SAR数据源均具有良好的应用潜力。此外，通过补充训练数据和微调参数，即可迁移到不同研究区使用，拥有较强的可迁移性。

# 参考文献（References）

[1］国家统计局.中国城市统计年鉴2017[M].北京：中国统计出 版社,2O17.[National Bureau of Statistics of the People's Republic of China.China city statistical yearbook 2O17[M].Beijing: China Statistics Press,2017.]   
[2]刘纪远,匡文慧,张增祥,等.20 世纪80 年代末以来中国土地 利用变化的基本特征与空间格局[J].地理学报,2014,69（1)： 3-14.[LIUJiyuan,KUANG Wenhui,ZHANG Zengxiang,et al. Spatiotemporal characteristics，patterns and causes of land use changes in China since the late $1 9 8 0 \mathrm { s } [ \mathrm { J } ]$ .Acta Geographica Sinica,2014,69(1) :3-14.]   
[3］匡文慧,刘纪远,陆灯盛.京津唐城市群不透水地表增长格局 以及水环境效应［J].地理学报，2011，66（11）：1486-1496.[ KUANG Wenhui,LIU Jiyuan,LU Dengsheng.Pattern of impervious suface cangeanditsefecton water environmentinthe BeijingTianjin-Tangshan metropolitan area[J].Acta Geographica Sinica, 2011,66(11) :1486 -1496.]   
[4］王静,周伟奇,许开鹏,等.京津冀地区城市化对植被覆盖度及 景观格局的影响[J].生态学报,2017,37（21）：7019-7029.[ WANG Jing,ZHOU Weiqi,XUKaipeng,etal.Spatiotemporalpattern of vegetation cover and its relationship with urbanization in Beijing-Tianjin-Hebei megaregion from 2000 to 2010[J].Acta Ecologica Sinica,2017,37(21):7019-7029.]   
[5]HEC Y,LIU ZF,TIAN J,et al. Urban expansion dynamics and natural habitat loss in China:A multiscale landscape perspective [J].Global Change Biology,2014,20(9）:2886-2902.   
[6］陆大道,陈明星.关于"国家新型城镇化规划（2014—2020）"编 制大背景的几点认识[J].地理学报,2015,70（2）：179－185. [LU Dadao,CHEN Mingxing.Several viewpoints on the backgroundof compiling the“National newurbanization planning （2014-2020)"[J].Acta Geographica Sinica,2015,70（2）:179 -185.]   
[7]LIU ZF,DING M H,HEC Y,et al. The impairment of environmental sustainability due to rapid urbanization in the dryland region of northern China[J].Landscape and Urban Planning,2019, （187）,165 -180.   
[8]LIU ZF,HE C Y,ZHOU Y Y,et al. How much of the world's land hasbeen urbanized,reallya hierarchical framework for avoiding confusion[J].Landscape Ecology,2014,29(5）:763-771.   
[9］杜培军.城市遥感的研究动态与发展趋势——“城市遥感"专 栏导读[J].地理与地理信息科学,2018,34（3):1-4.［DU Peijun.Progress and trends of urban remote sensing:Reading guidance for the special column on urban remote sensing[J]. Geography and Geo-Information Science,2018,34(3）:1 -4.]   
[10]WU JG.Urban ecology and sustainability:The state-of-the-science and future directions[J].Landscape & Urban Planning,2014,125 (2) :209 -221.   
[11］何春阳,史培军,陈晋,等.北京地区土地利用/覆盖变化研究 [J].地理研究,2001,（6）:679-687,772.［HE Chunyang,SHI Peijun,CHEN Jin,et al.A study on land use/cover change in Beijing area[J].Geographical Research,2001,(6):679 -687,772.]   
[12］宋金超,李新虎,吝涛,等.基于夜晚灯光数据和Google Earth 的城市建成区提取分析[J].地球信息科学学报,2015,17(6)： 750 -756.[SONG Jinchao,LI Xinhu,LIN Tao,etal.A method of extracting urban built-up area based on DMSP/OLS nighttime data and Google Earth[J].Journal of Geo-information Science,2O15,17 (6) :750 -756.]   
[13］卓莉,李强,史培军,等.基于夜间灯光数据的中国城市用地扩 展类型[J].地理学报,2006,（2）:169-178.[ZHUO Li,LI Qiang,SHI Peijun,et al.Identificationand characteristics analysis of urban land expansion types in China in the 199Os using DMSP/ OLS data[J].Acta Geographica Sinica,2006,(2):169178.]   
[14］黄世奇.合成孔径雷达成像及其图像处理[M].北京;科学出 版社,2015.[HUANG Shiqi. Synthetic aperture radar imaging and image processing[M].Beijing:Science Press,2015.]   
[15］张风丽,邵芸.城市目标高分辨率 SAR 遥感监测技术研究进展 [J].遥感技术与应用,2010,25（3）:415-422.[ZHANG Fengli,SHAO Yun. Urban target monitoring using high resolution SAR data[J].Remote Sensing Technology and Application,2010,25 (3) :415 -422. ]   
[16］张庆君,韩晓磊,刘杰.星载合成孔径雷达遥感技术进展及发 展趋势［J]．航天器工程,2017,26（6）：1－8.[ZHANG Qingjun,HANXiaolei,LIUJie.Technologyprogressanddevelopment trend of spaceborne synthetic aperture radar remote sensing [J].Spacecraft Engineering,2017,26(6）:1 -8.]   
[17]ZHANG H S,LIN H,WANG YP.A new scheme for urban impervious surface classification from SAR images[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2018,（139）:103-118.   
[18］车美琴,阿里木·赛买提,杜培军,等.利用旋转不变特征提取全 极化 SAR 影像人工地物[J].遥感学报,2016,20(2）:303-314. [CHE Meiqin,SAMAT A,DU Peijun,et al. Urban man-made target extraction from quad-polsar imagery with roll-invariant parameters [J]. Journal of Remote Sensing,2016,20(2）:303 -314.]   
[19]NIU X,BAN Y. Multitemporal RADARSAT-2 polarimetric sar data for urban land cover clasification using object-based support vector machine and rule-based approach[J]. International Journal of Remote Sensing,2012,34(1) :1 -26.   
[20］张鸿生,林殷怡,王挺,等.融合光学与雷达遥感数据的城市不 透水面提取方法[J].地理与地理信息科学,2018,34（3）：39 - 46,129.[ZHANG Hongsheng,LIN Yinyi,WANG Ting,et al. Fusing optical and SAR remote sensing data for urban impervious surface estimation[J].Geography and Geo-Information Science, 2018,34(3) :39 -46,129.]   
[21] SANTORO M,ASKNE JI H,WEGMILLER U,et al. Observations,modeling,and applications of ERS-ENVISAT coherence over land surfaces[J].IEEE Transactions on Geoscience and Remote Sensing,2007,45(8） :2600 - 2611.   
[22]DEKKER R J. Texture analysis and clasification of ERS SAR images for map updating of urban areas in the Netherlands[J]. Geoscience & Remote Sensing IEEE Transactions,2003,41(9）:1950 - 1958.   
[23]DEL FRATE F,PACIFICI F,SOLIMINI D. Monitoring urban land cover in Rome,Italy,and its changes by single-polarization multitemporal SAR images[J]. IEEE Journal of Selected Topics In Applied Earth Observations and Remote Sensing,2008,1（2） :87 - 97.   
[24］王纬华,江涛,张永红,等.基于高分 SAR 影像的城市用地变化 检测[J].测绘与空间地理信息,2016,39（7）：141-143,147. [WANG Weihua,JIANG Tao,ZHANG Yonghong,et al. Detection of urban land use changes based on high resolution SAR images [J].Geomatics & Spatial Information Technology,2016,39（7）: 141 -143,147. ]   
[25]GENG J,WANG HY,FAN JC,et al. Deep supervised and contractive neural network for SAR Image classification[J]. IEEE Transactions on Geoscience and Remote Sensing,2017,55（4）: 2442 - 2459.   
[26］陈筠力,李威.国外 SAR卫星最新进展与趋势展望[J].上海 航天,2016,33（6）:1-19.[CHEN Junli,LI Wei.Recent advancesand trends of SAR satelites in foreign countries[J].Aero space Shanghai,2016,33(6):1 -19.]   
[27］欧阳伦曦,李新情,惠凤鸣,等.哨兵卫星 Sentinel-1A数据特性 及应用潜力分析［J].极地研究,2017,29（2）：286－295.[ OUYANG Lunxi,LI Xinqing,HUIFengming,et al.Sentinel-1A data products’characteristics and the potential applications[J].Chinese Journal of Polar Research,2017,29(2）:286 -295.]   
[28］杨魁,杨建兵,江冰茹.Sentinel-1卫星综述［J].城市勘测, 2015,(2):24-27.[YANG Kui,YANG Jianbing,JIANG Bingru. Sentinel-l satelite overview[J].Urban Geotechnical Investigation & Surveying,2015,（2）:24 -27.]   
[29]TORRES R,SNOEIJ P,GEUDTNER D,et al. GMES Sentinel-1 mission[J].Remote Sensing of Environment,2012,120(6）:9 - 24.   
[30］李成绕,薛东剑,张露,等.基于 Sentinel-1A卫星 SAR 数据的水 体提取方法研究[J].地理空间信息,2018,16（1）:38－40,7. [LI Chengrao,XUE Dongjian,ZHANG Lu,et al. Research on water extraction method based on Sentinel-1A satelite SAR data[J]. Geospatial Information,2018,16(1） :38 -40,7.]   
[31］汤玲英,刘雯,杨东,等.基于面向对象方法的 Sentinel-1A SAR 在洪水监测中的应用[J].地球信息科学学报,2018,20（3）： 377-384.[TANG Lingying,LIU Wen,YANG Dong,et al.Flooding monitoring application based on the object-oriented method and Sentinel-1A SAR data[J]. Journalof Geo-information Science,， 2018,20(3) :377 -384.]   
[32］向海燕,罗红霞,刘光鹏,等.基于Sentinel-1A极化 SAR 数据与 面向对象方法的山区地表覆被分类[J].自然资源学报,2017, 32（12）:2136 -2148.[XIANG Haiyan,LUO Hongxia,LIU Guangpeng,et al.Land cover clasification in mountain areas based on Sentinel-1A polarimetric SAR data and object oriented method [J].Journal of Natural Resources,2017,32(12）:2136-2148.]   
[33]BANYF,WEBBERL,GAMBAP,et al.EO4Urban:Sentinel-1A SAR and Sentinel-2A MSI data for global urban services[C]// Urban Remote Sensing Event. IEEE,2017:1-4.   
[34]HEIKO B ,BETH C,CHRISTIAN T,et al. Mapping CORINE land cover from Sentinel-1A SAR and SRTM digital elevation model data using random forests[J]. Remote Sensing,2015,7(11）:14876 -14898.   
[35] CAO H,ZHANG H,WANG C,et al. Operational built-up areas extraction for cities in China using Sentinel-1 SAR data[J].Remote Sensing,2018,（10）:874.   
[36]GAMBA P,ALDRIGHI M,STASOLLA M. Robust extraction of urban area extents in HR and VHR SAR images[J].IEEE Journal of Selected Topics inAped Erth Observations &RemoteSesing, 2011,4(1) :27 -34.   
[37]BAN Y F,JACOB A,GAMBA P.Spaceborne SAR data for global urban mapping at $3 0 \mathrm { m }$ resolution using a robust urban extractor [J]. ISPRS Journal of Photogrammetry and Remote Sensing,2015, 103(5) :28 -37.   
[38]LONG J,SHELHAMER E,DARRELL T.Fully convolutional networks for semantic segmentation[J]. IEEE Transactions on Pattern Analysis & Machine Inteligence,2014,39(4）:640 -651.   
[39]LECUN Y,BENGIO Y,HINTON G.Deep learning[J]. Nature, 2015,521(7553) :436.   
[40] LECUN Y L,BOTTOU L,BENGIO Y,et al. Gradient-based learning applied to document recognition[J].Proceedings of the IEEE, 1998,86(11) :2278 -2324.   
[41］刘文涛,李世华,罩驭楚.基于全卷积神经网络的建筑物屋顶 自动提取[J].地球信息科学学报,2018,20（11）:1562－1570. [LIU Wentao,LI Shihua,QIN Yuchu.Automatic building roof extraction with fully convolutional neural network[J]. Journal of Geoinformation Science,2018,20(11) :1562-1570.]   
[42]潘旭冉,杨帆,潘国峰.采用改进全卷积网络的"高分一号"影 像居民地提取[J].电讯技术,2018,58（2）：119－125.［PAN Xuran,YANGFan,PAN Guofeng.Extraction of residential areas in GF-1 remote sensing images based on improved fully convolutional network[J].Telecommunication Engineering,2018,58（2）:119- 125.]   
[43]HE C Y,LIU Z F,GOU S Y,et al. Detecting global urban expansion over the last three decades using a fully convolutional network [J].Environmental Research Letters,2019,14（3）:doi:10.1088/ 1748 -9326/aaf936.   
[44]FU G,LIU C J,ZHOU R,et al. Classification for high resolution re mote sensing imagery using a fully convolutional network[J].Remote Sensing,2017,9(5） :498.   
[45]ZHANG PB,KE Y H,ZHANG Z X,et al. Urban land use and land cover classification using novel deep learning models based on high spatial resolution satellite imagery[J]. Sensors（Basel）, 2018,18(11) :3717.   
[46］王一航,夏沛,刘志锋,等.中国绿洲城市土地利用/覆盖变化 研究进展[J].干旱区地理,2019,42（2）:341-353.[WANG Yihang,XIA Pei,LIU Zhifeng,et al.Research progress of urban land use/cover change in the oasis cities of China[J].Arid Land Geography,2019,42(2） :341-353.]   
[47］李骞国,石培基,魏伟.干旱区绿洲城市扩展及驱动机制一 以张掖市为例[J].干旱区研究,2015,32（3）：598-605.［LI Qianguo,SHI Peiji,WEI Wei.Research on urban expansion and drive mechanism in an oasis town of arid region：A case of Zhangye City[J].Arid Zone Research,2015,32(3):598-605.]   
[48］梁峰,李骞国,石培基,等.张掖城市主要功能用地演变特征及 其动因分析[J].干旱区地理,2019,42（2）:414-422.[LIANG Feng,LI Qianguo,SHI Peiji,et al. Evolution characteristics and driving factors of urban functional land in Zhangye City,the Hexi Corridors,northwest China[J].Arid Land Geography,2019,42 (2) :414 -422.]   
[49］冯斌,陈晓键.西北中小城市建设用地增长的特征、动因及其 分类引导[J].干旱区地理,2019,42（2）:376-384.[FENG Bin,CHEN Xiaojian. Characteristics,motivation and classification guidance of urban construction land growth of the small and medium-sized cities in northwest China[J].Arid Land Geography, 2019,42(2) :376 -384.]   
[50]SZEGEDY C,LIU W,JIA Y,et al. Going deeper with convolutions [C]// IEEE Conference on Computer Vision and Pattrn Recognition（CVPR).IEEE,2015.

[51]JIAY,SHELHAMERE,DONAHUEJ,etal.Caffe:Convolutional architecture for fast feature embedding[C]//Priceeding of the 22nd ACM international Conference on Multimedia.Orlando,USA： Acm，2014:675-678

derived land cover data:A review[J].Photogrammetric Engineering&Remote Sensing,1994,60（4）:419-426. [53］斋藤康毅.深度学习入门：基于Python 的理论与实现[M].北 京：人民邮电出版社,2018.［KOKI Saitoh.Deep learning from scratch[M].Beijing:Posts and Telecommunications Press,2018.]

# A new method for detecting urban construction land based on Sentinel-1A synthetic aperture radar data and fully convolutional network

LU Wen-lu²，LUZhi-feng²，HEChun-yang²，XIA Pei $^ { 1 , 2 }$ (1Center for Human-Environment System Sustainabity（CHESS）,StateKey LaboratoryofEarth SurfaceProceses and Resource Ecology（ESPRE）,Facultyof Geographical Science,Beijing Normal University,Beijing 10o875,China; 2Schoolof NaturalResources,Facultyof Geographical Science,BeijingNormal University,BeijingOo875,hina)

Abstract：Timelyand accurate extraction of urban construction land is essential for assessing the impacts of urban expansion onthe environment.Opticalremote sensing is susceptible to weather conditions and contains insufficient informationon the textureof urban features,and is thusnotconducive tourbanconstruction land extraction.Synthetic aperture radar（SAR）is unique initspotential to beused inallweatherconditions and at any time.Furthermore,its backscattering and polarimetric information issensitive to the dielectricand geometric properties of the urban land surface,providing a new means for rapid and accurate extraction of urban construction land.Among existing SAR data,the Sentinel-1A SARdata is widelyused due toits free acssNonetheless,existing methodsare poorly adapted to fullyutilize the Sentinel-1A SAR data,therebylimiting itsapplication.Thefullyconvolutional network isadep learning network developedonthe basis of theconvolutional neural network,which adopts“pixel to pixel”image recognitionand has become an efective method for extracting urban construction land.This paper aims to develop a method for detecting urban construction land based on Sentinel-1A SAR data,and thus a fullyconvolutional network.Firstly, a fuly convolutional network consisting offive Inception modules wasdeveloped with reference to GoogleNet.Each Inception module includes three convolutional layers with convolutional kernel sizes of $1 \times 1 { , } 3 \times 3$ ,and $5 \times 5$ respectively,three correspondingactivation layers,and aconcatenation layer.The Ganzhou District in Zhangye City,Gansu Province,China,where urban constructionland andbare land show similar spectrum features,was used as acase study area to verifyour fully convolutional network.The extraction results showthat the area ofconstructionland in the Ganzhou District was 4,006 hectares in 2018,accounting for about $20 \%$ of the total area. The patch area of urban constructionland wasgenerally found tobe between O.Oland1 hectare.Urbanconstructionland was mainly distributed in the west and northeast,and the circle of $2 - 4 ~ \mathrm { k m }$ from the city center exhibited the most concentrated urban construction land. Our accuracy assessment shows an overall accuracy of $9 2 . 5 0 \%$ and a Kappa coefficient of O.85.By comparing our results to extraction results using the“KTH-Pavia”method（the most widely used method for extractingurbanconstruction land from SARdata）,it was found that extraction results basedon the fullyconvolutional network arecloserto thereal urbanconstructionland in spatial paterns.Furthermore,the overallaccuracyand Kappa coefficient were,respectively, $11 \%$ and $37 \%$ higher than the“KTH-Pavia”method.The principal reason for this higher accuracyis thatthefullyconvolution network can beter integrate multi-polarizationand multi-scale texture information from SAR data.Furthermore,the fully convolutional network contains multiple convolutional structures and supports multi-sourcedata inputs.The method developed in this study hasboth greater accuracy than existing methods and isapplicable tourban construction landextraction based on diferent SAR data in diferent regions.Ittherefore has potential for widespread application.

KeyWords:Sentinel-1A；Sentinel data；synthetic aperture radar；urbanconstruction land；fully convolutional network ； deep learning