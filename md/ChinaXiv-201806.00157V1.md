# 基于噪声相关性的惩罚加权最小二乘算法在低剂量数字乳腺层析成像中的应用

陈美玲1,²,陶熙1,2，李华勇1²，陈武凡1²，张华1,2  
南方医科大学'生物医学工程学院，广东省医学图像处理重点实验室，广东广州 510515

摘要：目的对投影数据方差的精确建模并结合DBT平板探测系统的噪声相关性构建精准噪声模型下的基于噪声相关性的惩罚加权最小二乘算法在低剂量乳腺层析成像图像中的应用。方法 首先对投影数据进行量子噪声和电子噪声建模，使以往常用的近似噪声模型精准化，然后构建基于噪声相关性的惩罚加权最小二乘算法用于投影数据恢复；最后对处理后的投影数据采用滤波反投影算法进行重建。结果对不同剂量下ACR标准体模数据进行处理得到的重建结果噪声明显降低，细节对比度提高。恢复投影数据的重建图像与原始数据重建图像相比,CNRs和LSNRs提升了约3.6倍。结论 对投影数据噪声抑制效果明显，重建DBT图像质量有很大的提升。

关键词：数字乳腺层析成像；低剂量；噪声相关性；加权最小二乘

# Low-dose digital breast tomosynthsis imaging via noise correlation based penalized weighted least-squares algorithm

CHENMeiling1²,TAO $X i ^ { \ i , 2 }$ ,LIHuayong1²,CHENWufan12,ZHANGHua,2   
DepartmentofiomedicalEngineeingGuangdongroncalKeybatorofedicalIagerocesingSouenMedicliy   
Guangzhou,510515,China

Abstract: ObjectiveToachievelow-dose digital breast tomosynthsis (DBT)projection recovery using penalized weighted least squarealgorithmincorporatingaccuratemodelingof thevarianceof the projection dataand noisecorelationinthflatpanel detector.Methods Models were established for thequantal noiseand electronic noiseintheDBT system toconstruct the penalized weightedleastsquaresalgorithmbasedonnoisecorelationfor projectiondatarestoration.Thefiterbackprojection algorithm was then used for DBT image reconstruction.Results The reconstruction results of the ACR phantom data at difrent dose levels sowed a good performance of the proposed method in noise suppressionand detail preservation. CNRs andLSNRs ofthe reconstructed images fromtherestored projections were increased byabout3.6times compared tothose of reconstructed images from the original projections. Conclusion The proposed method can significantly reduce noise and improve the quality of DBT images.

Keywords: digital breast tomosynthesis; low-dose; noise correlation; weighted least squares algorithn

近年来，乳腺癌的发病率一直呈现上升趋势[,乳腺筛查成为了降低乳腺癌死亡率的重要手段[2-3]。

X线乳腺摄影技术4对微小病灶具有高度敏感性，但传统的全视野数字乳腺X摄影(FFDM)由于平面二维成像的组织重叠效应在乳腺肿瘤的检测中存在一定程度的检出失败率[5,同时，由正常组织重叠而产生的假阳性肿瘤会误导医生的诊断。近年来，数字乳腺层析成像(DBT)逐渐在临床中得到广泛应用[-8],DBT成像利用传统的X线源，以平板探测器为旋转中心采集一定数量的投影数据，并通过有限数量的投影数据进行三维重建，实现了乳腺的三维成像。数字乳腺层析成像很大程度上解决了二维成像组织重叠所导致的检出失败和假阳性误诊的问题。同时，相对于CT成像技术，DBT成像很大程度上降低了患者的辐射剂量[10],但乳腺作为一个对X射线敏感器官],其辐射危害仍然不容小。为进一步降低辐射剂量，可以通过降低X射线球管电流(mAs)来实现超低剂量DBT成像[12]，但超低剂量扫描条件下的重建图像噪声水平较高，导致低对比度病灶及微小钙化点难以识别。

为抑制DBT图像噪声，提高病灶检出率，本文借鉴低剂量CT成像中的投影数据降噪理论[13-16]对投影数据进行恢复后重建，并在噪声模型构建和恢复算法设计两个方面做了改进，以此提升投影数据恢复效果和重建图像质量。在噪声模型构建方面，Ma等在对投影数据的方差分析过程中发现低剂量扫描条件下电子噪声的忽略会使测量投影数据的方差估计与真实值产生较大差距，并提出和验证了精确化的噪声模型，本文基于这一理论将常规的近似噪声模型做了精确化处理,用于低剂量DBT投影数据恢复。同时，我们发现基于平板探测器获取的投影数据存在噪声相关性[18]。基于上述,本文充分利用DBT平板探测器的数据统计特性，在对DBT投影数据进行精确噪声建模(对投影数据进行方差特性统计)的基础上，结合噪声相关性构建惩罚加权最小二乘算法对投影图像进行数据优化。最后利用改进的FBP算法进行图像重建，以提升DBT图像质量。

# 1方法

# 1.1投影数据噪声建模

对于图像噪声的准确建模，探测器响应的数据统计尤为重要。Whiting等人对能量积分型探测器数据校正以及数据采集的随机过程进行理论建模，得出校正后数据满足复合泊松分布的结论[19-20],透射光子分布函数将量子噪声与背景电子噪声结合，定义为：

$$
\widetilde { I } _ { i } \sim \sum _ { k } G ( E _ { k } ) P o i s \ \mathrm { s o n } \{ \widetilde { \lambda _ { i } } ( E _ { k } ) \} + N o r m a l \{ d _ { i } , { \sigma _ { e , i } } ^ { 2 } \} \ (
$$

$i$ 表示探测单元序列编号，参数 $k$ 表示X光能量级，$G ( . )$ 表示能谱概率，Possion $\{ . \}$ 表征数据的泊松统计特性，其中λ代表穿过测量体后的光子平均数，即探测器实际接收到的信号。公式(1)的第二项表征电子噪声，服从均值为 $d _ { i }$ ，方差为 ${ \sigma _ { e , i } } ^ { 2 }$ 的高斯分布，电子噪声的参数可以通过暗电流数据测量。对于复合泊松分布，目前还还缺闭合、准确的似然函数，本文忽略X光多能特性，将X线光子分布函数简化为：

$$
\widetilde { I } _ { i } \sim P o i s \mathrm { s o n } \{ \lambda _ { i } \} + N o r m a l \{ d _ { i } , { \sigma _ { e , i } } ^ { 2 } \}
$$

利用朗伯比尔定律对探测器数据进行对数变换，可以得到探测单元 $i$ 对应路径上的线性衰减系数线积分数据：

$$
p _ { i } = \mathrm { l n } \frac { I _ { o _ { i } } } { \widetilde { I _ { i } } } = \mathrm { l n } I _ { o _ { i } } - \mathrm { l n } \widetilde { I _ { i } }
$$

式(3)中， $I _ { o _ { i } }$ 为入射(没有经过测量体之前)光子数目，可以通过空扫描进行测量； $\widetilde { I } _ { i }$ 表示探测器接收到的透射光子量的随机变量，分布函数如公式(2)所示。忽略 $I _ { o _ { i } }$ 的随机特性， $p _ { i }$ 是一个随机变量,其均值、方差可以通过计算求取。本文线积分投影数据方差模型[17]：

$$
{ \sigma _ { p i } } ^ { 2 } = \mathrm { v a r } ( p _ { i } ) = \frac { 1 } { \lambda _ { i } } ( 1 + \frac { { \sigma _ { e , i } } ^ { 2 } - 1 . 2 5 } { \lambda _ { i } } )
$$

式中 $\lambda _ { i } = I _ { o _ { i } } \exp ( - \overline { { p _ { i } } } )$ 。式(4)给出了投影数据方差和光子平均数、电子噪声方差的关系,保留了量子噪声和电子噪声对方差特性的影响。

1.2基于噪声相关性的惩罚加权最小二乘算法在DBT投影数据恢复中的应用

基于先前对平板探测器的噪声相关性的研究，在同

一扫描条件下，对大量重复的平板探测器投影数据统计分析，得出相邻投影数据之间存在着噪声相关性的结论，不同路径积分数的噪声相关性可由相关因子 $\beta _ { i j }$ 描述：

$$
\rho _ { i j } = \frac { \mathrm { c o v } ( p _ { i } , p _ { j } ) } { \sigma _ { i } \sigma _ { j } } = \frac { \mathrm { c o v } ( p _ { i } , p _ { j } ) } { \sqrt { \mathrm { v a r } ( p _ { i } ) } \sqrt { \mathrm { v a r } ( p _ { j } ) } }
$$

基于式(5)中测定的相关系数，利用式(4)中对投影数据噪声方差的估计，我们可以获得$\operatorname { c o v } ( p _ { i } , p _ { j } ) = \sigma _ { i j } = \rho _ { i j } \cdot { \sqrt { \operatorname { v a r } ( p _ { i } ) } } \sqrt { \operatorname { v a r } ( p _ { j } ) }$ ,由此构建投影数据噪声协方差矩阵 $\Sigma$ ,该矩阵是带宽为 $B { + } 1$ 实对称对角矩阵,即：当 $i { = } j$ ， $i - j = \pm 1$ ， $\scriptstyle i - j = \pm B$ ， $i - j = \pm ( B \pm 1 )$ 时,矩阵 $\scriptstyle \sum$ 的元素 $\sigma _ { i j }$ 为非零值,矩阵的其他元素均取值为零，当采取逐列方式重排数据时， $B$ 等于列维度，当采用逐行重排时， $B$ 等于行维度。基于噪声相关特性，利用加权最小二乘算法(PWLS)以投影数据建立能量函数，估计最佳线积分值：

$$
\Phi ( p ) { = } ( \hat { y } - p ) ! { \sum } ^ { - 1 } ( \hat { y } - p ) + \beta R ( p )
$$

式(6)中第一项为数据保真项,其中 $\hat { y }$ 表示探测器直接测量值对数变换后的数据， $p$ 表示待估计的最佳线积分值, $\textstyle \sum$ 为线积分投影数据的协方差矩阵。公式(6)中第二项为惩罚项,其中 $\beta$ 为调节保真项和惩罚项比例的参数，惩罚项设置如下：

$$
R ( p ) = \sum _ { j } R ( p _ { j } ) = \sum _ { j } \sum _ { k \in S _ { j } } w ( k , j ) ( p _ { j } - p _ { k } ) ^ { 2 }
$$

$S _ { j }$ 指在二维投影数据中与像素 $j$ 最相邻的4个像素，本文中4个像素的权 $w ( k , j )$ 取相同值。通过最小化代价函数(6)可以得到优化的线积分投影数据：

$$
\begin{array} { l } { \displaystyle \hat { p } = \arg \underset { \mu \geq 0 } { \operatorname* { m i n } } ( \hat { y } - p ) ! \sum ^ { - 1 } ( \hat { y } - p ) + } \\ { \displaystyle \beta \sum _ { j } \sum _ { k \in S _ { j } } w ( k , j ) ( p _ { j } - p _ { k } ) ^ { 2 } } \end{array}
$$

本文中协方差矩阵的非负对称特性以及惩罚先验项 $R { \big ( } p { \big ) }$ 的二次平滑设计使得式(8)中的代价函数为凸函数。由凸函数的性质,我们可以将对 $\Phi ( p )$ 的最优化转化为求解 $\nabla \Phi { \big ( } p { \big ) } = 0$ 的极值问题,且该解理论上是唯一的。将 $\nabla R ( p )$ 改写为 $\nabla R ( p ) = \nabla \bigl \| p \bigr \| ^ { 2 } = A p$ 。 $A$ 为与数据协方差矩阵结构类似的五对角矩阵，满足：

$$
\begin{array} { r } { A _ { i , j } = \left\{ \begin{array} { l l } { 4 , \qquad i = j } \\ { - 1 , \quad i - j = \pm 1 o r i - j = \pm B } \\ { 0 , \qquad o \mathrm { t h } e r w i s e } \end{array} \right. } \end{array}
$$

因此代价函数的梯度形式可以通过下式改写：

$$
\begin{array} { r } { \nabla \Phi ( p ) = \nabla ( ( y - p ) ^ { T } { \sum } ^ { - 1 } ( y - p ) ) + \beta \nabla R ( p ) = 0 } \end{array}
$$

$$
\Rightarrow \sum ^ { - 1 } ( p - y ) + \beta A p = 0
$$

由此,我们可以通过解 $\Sigma ^ { - 1 } ( p - y ) + \beta A p = 0$ 最优化求解式(8)。

为了充分利用矩阵 $\scriptstyle \sum$ 和 $A$ 的稀疏结构，我们可以利用LSQR算法进行迭代求解。对 $\Sigma ^ { - 1 } ( p - y ) + \beta A p = 0$ 迭代求解过程如下：

0.初始化 $p ^ { ( 0 ) }$ ，并设定迭代终止条件 $\boldsymbol { \varepsilon }$ ·，

1.求解线性方程 $\scriptstyle \sum b = y - p ^ { ( n ) }$ ，以更新 $b$   
2.对步骤1求解得到的 $\boldsymbol { \mathrm { \textbf { b } } }$ 值，求解线性方程 $\beta A p ^ { ( n + 1 ) } = b$ ，得到 $p ^ { ( n + 1 ) }$ ;  
3.当满足|p"-p"|<ε停止迭代,否则返回步骤1;  
\*其中 $b$ 为中间变量

1.3恢复投影数据重建

对恢复后的投影数据，本文利用三维的滤波反投影(FBP)算法进行重建[21-22]。重建算法基于滤波反投影，为实现乳腺的最佳成像效果改进滤波设计，同时采用距离坐标变换后再进行反投影(距离驱动反投影,DDBP)[23],这样的方式相比传统的对整个图像基于路径的反投影缩短了计算时间，从精度的角度出发，距离坐标变换反投影考虑了图像像素和探测器的宽度问题，可以忽略将投影数据的锥形束近似平行束处理时对重建的影响。

# 2结果

# 2.1实验数据获取

本文主要采用DBT实验原型机采集的ACR标准体模投影数据进行图像重建。ACR标准体模是乳腺成像所使用的标准测试体模，体模内部包含与乳腺结构相似衰减系数的物质，对应于乳腺的腺体、纤维组织、钙化点、囊肿等结构，ACR标准体模结构信息参见图1。

![](images/5365b65c37548f23f8ea12bf7b8e1fcda3f16dadea2b72f277b905c46aa369ed.jpg)  
图1乳腺成像标准体膜ACR体模内部结构信息及实物图Fig.1 Internal structure and appearance of anACR standard phantom

数据采集系统为Analogic公司AXS-2430平板探测器，投影数据的采集参数为：管电压 $3 0 \mathrm { k V }$ ，管电流分别是 $4 0 . 6 0 , 8 0 , 1 0 0 \mathrm { m A }$ 。探测器以与X线源曝光相同的时序采集25个投影，X线源在 $\dot { \pm } 2 4 ^ { \circ }$ 范围内每隔 $2 ^ { \circ }$ 曝光1次。数据采集的过程中，X线源到探测器的距离为$6 5 0 \mathrm { m m }$ ，旋转中心到探测器的距离为 $2 5 ~ \mathrm { m m }$ 。原始投影数据大小为 $3 5 8 4 \times 2 8 1 6$ ，像素大小为 $0 . 0 8 5 ~ \mathrm { m m } \times$ $0 . 0 8 5 \mathrm { m m }$ 。

# 2.2评价参数

为定量评价算法性能，本文中我们选用局部信噪比和对比度信噪比作为图像质量的评估指标，其中，局部信噪比(LSNR)和对比度信噪比(CNR)分别定义为：

$$
L S N R { = } \bar { f } / \sigma _ { f }
$$

$$
C N R = \frac { 2 \Big | \bar { f } - \bar { b } \Big | } { \sigma _ { f } + \sigma _ { b } }
$$

式(11)和(12)中， $\bar { f } , \bar { b }$ 分别表示感兴趣区域(ROI)和背景区域内的像素均值， $\sigma _ { f } , \sigma _ { b }$ 为感兴趣区域(ROI)和背景区域内的标准差。

# 2.3投影图像恢复前后比较

本文的方法实现过程中，首先通过暗扫描对电子噪声方差进行估计，再结合公式(4)进行投影数据的方差估计。图2给出了0角度下利用基于噪声相关性的惩罚加权最小二乘法恢复前后的投影图像。其中图2中A、B的扫描参数为 $3 0 \mathrm { k V } { \cdot } 4 0 \mathrm { m A }$ ，C、D的扫描参数为 $3 0 \mathrm { k V }$ $6 0 ~ \mathrm { m A }$ ，图A和图C为被噪声污染的投影图像，图B和图D为利用本文算法恢复后图像。

对比不同剂量下的投影图像，可以看出低剂量扫描会导致投影数据存在严重的噪声，利用基于噪声相关性的惩罚加权最小二乘算法，低剂量投影图像的噪声得到有效的抑制，投影图像无失真。

图3展示了 $3 0 \mathrm { k V } , 4 0 \mathrm { m A }$ 剂量下的0角度投影数据在参数 $\beta = 1 2 0 0$ 时本文算法迭代的收敛情况，横轴表示迭代步数,纵轴量 $\left\| \mu _ { n } - \mu _ { n - 1 } \right\| ^ { 2 }$ 可以表征第 $n$ 步与第$n - 1$ 步迭代后投影数据结果之间的差异，从图中可以看出本文算法收敛速度较快，10步迭代即可获取稳定结果。

本文中，我们对0角度下的投影数据进行了LSNR对比分析，图4中折线图展示了不同剂量投影图像恢复前后的LSNR值，从图中我们可以看出，基于噪声相关性的惩罚加权最小二乘算法可以有效地抑制DBT投影图像噪声，提高投影图像的信噪比。

![](images/7306ee45edf56ea2cbdf97bdf372397e8d3f179200977c26599fb5b32cb68362.jpg)  
图2 $3 0 \mathrm { k V p } { \cdot } 4 0 \mathrm { m A }$ 和 $3 0 \mathrm { k V p . 6 0 \ m A }$ 剂量下0角度投影数据恢复前后的图像. Fig.2 OriginalandrestoredprojectionimagesatangleOwithdiferentsansetings.A:Originalprojectionimageobtanedat30 $\mathsf { k V } \mathsf { p }$ and $4 0 ~ \mathrm { m A } .$ B:Restored projection image obtained at $3 0 \mathrm { k V }$ and $4 0 \mathrm { m A }$ ; C: Original projection image obtained at $3 0  { \mathrm { k V } }$ and $6 0 \mathrm { m A }$ ; D: Restored projection image obtained at $3 0 \mathrm { k V }$ and $6 0 \mathrm { m A }$

![](images/dd4ca229ce4e6bd6cd9f9dfc5683af87774a29b92bec4d431bb82a1a7722c893.jpg)

![](images/fb0ab03ab8c5a22329914e37ac039b534f3e861d63506b03f5f45051c6e4f250.jpg)  
图30角度实验数据在 $3 0 \ \mathrm { k V p } . 4 0 \ \mathrm { m A }$ 剂量下，参数 $\beta =$ 1200时，PWLS算法的收敛测试图Fig.3 Convergence of PWLS algorithm at $3 0  { ~ \mathrm { k V } \mathrm { p } }$ and 40mAat the angle of O with $\scriptstyle { \beta = 1 2 0 0 }$ #  
图40角度下 $4 0 { \mathord { \cdot } } 6 0 { \mathord { \cdot } } 8 0 { \mathord { \cdot } } 1 0 0 \mathrm { m A }$ 四个剂量的投影数据恢 复前后局部信噪比折线图 Fig.4 Local SNRs calculated from projection data at angle O andat the dose levels of 40, 60,80 and $\mathrm { 1 0 0 ~ m A }$ before and after denoising.

# 2.4重建结果比较

利用距离驱动反投影(DDBP)算法对恢复后投影图像进行重建，我们可以得到如图5所示的重建图像。图5A\~H分别给出了 $4 0 , 6 0 , 8 0 , 1 0 0 \mathrm { m A }$ 四个剂量下原始投影数据重建图像和恢复投影数据重建图像。

从重建结果中我们可以看出，利用原始投影数据重建图像中含有大量噪声，点状细节被噪声淹没无法识别，同时图像的对比度也十分有限;而利用恢复投影数据重建的图像中，噪声水平较低，点状细节得到凸显。相对于图A和C，图B和D中第三级点状结构可以很好的重建并显现出来，相对于图E和G，图F和H中第四级点状结构可以很好的重建并显现出来；由此可见，利用基于噪声相关性的惩罚加权最小二乘算法可以实现低剂量DBT图像的有效去噪，提高DBT图像的对比度。

为展示本文算法的有效性，我们采用BM3D(BlockMatching3-Dimension)滤波算法[24-25]用于投影数据恢复，然后对恢复数据进行FBP重建。图6中展示了 $4 0 ~ \mathrm { m A }$ 剂量下BM3D及本文方法重建的DBT图像，可以看出图6B中点状结构清晰度明显优于图6A对应级数点状结构。此实验结果说明，本文的算法在图像细节结构保持方面有上佳表现。

为进一步说明方法的有效性，我们分别计算了四个剂量下本文算法重建图像与图7所示的相同感兴趣区的LSNRs和CNRs。表1和表2分别给出了不同剂量下投影数据恢复前后的重建图像的LSNR及CNR值。从表格中数据可以看出，随着剂量的升高，重建DBT图像的LSNR及CNR值变高；相对于原始投影数据重建结果，利用PWLS算法恢复投影数据重建图像有更高的LSNR和CNR。

# 3讨论

乳腺筛查的重大需求决定了数字乳腺层析成像这一新兴X射线成像技术在临床应用上的重要意义。然而，噪声的存在可能掩盖某些低对比度的病灶区域，在图像断层重建的去噪研究中，基于最小二乘算法的去噪方法得到了广泛关注[16,26]。本方法借鉴了前人成果低剂量CT成像中的投影数据降噪算法，但采用了更加精确地噪声模型并结合噪声相关性构建惩罚加权最小二乘算法对投影图像进行数据优化，对于噪声模型的改进，Liang等人在对投影数据的方差分析过程中发现，噪声分布模型的正态拟合与实际情况存在一定差距[17],在扫描剂量较高的情况下，探测器系统所导致的电子噪声对探测器测量的投影数据影响极低，因此可以忽略不计，但是在低剂量扫描条件下，忽略电子噪声会使测量值的方差估计与真实值产生较大差距，本方法针对低剂量DBT投影数据的噪声进行恢复，噪声模型的精确化无疑使降噪效果更加显著。

![](images/bc7d5da31b6c83b17b21fb23e9e91e5f1ddbf5030f8d0cb48516fa7267bbfc9f.jpg)  
图）不问剂里投影数据恢发前后时里建结禾

![](images/d5689e4a3ae26434a0bd09d8e59c873c6f986465b2297b14f89debffa33cdd76.jpg)  
Fig.5Reconstructionresults beforeandafter projection datarecoveryat diferent doses.A:The image reconstructed from original projections at $3 0 \mathrm { k V p }$ and $4 0 \mathrm { m A }$ ; B: The image reconstructed from the restored projections at $3 0 \mathrm { k V p }$ and $4 0 ~ \mathrm { m A }$ C: The image reconstructed from original projections at $3 0  { ~ \mathrm { k V } _ { \mathrm { P } } }$ and $6 0 ~ \mathrm { m A }$ ; D: The image reconstructed from the restored projections at $3 0 \mathrm { k V p }$ and $6 0 ~ \mathrm { m A }$ ;E: The image reconstructed from original projections at $3 0 \mathrm { k V p }$ and $8 0 ~ \mathrm { m A }$ ；F: The image reconstructed from the restored projections at $3 0 \mathrm { k V p }$ and $8 0 ~ \mathrm { { m A } }$ ;G: The image reconstructed from original projections at 30 $\mathsf { k V } \mathsf { p }$ and $1 0 0 \mathrm { m A }$ ; H: The image reconstructed from the restored projections at $3 0 \mathrm { k V } \mathrm { p }$ and $\mathrm { 1 0 0 \ m A }$   
图6不同算法对 $4 0 ~ \mathrm { m A }$ 投影数据处理后的重建图像 Fig.6 Reconstructed images from restored projection data( $\mathrm { ^ { 4 0 } \ m A }$ ）using different algorithms.A: BM3D;B: the proposed method.

将噪声相关性推论得到的数据方差特性用于最小二乘算法中可以优化数据恢复结果。DBT成像所用的球管及管电压相对CT成像略有不同2，但单一角度下

DBT投影数据与CT投影数据的产生机制并无本质差异。在数据采集过程中，DBT采用了平板探测器，不同探测器单元上的投影数据可能相互影响。本文对投影数据进行方差特性统计，并结合噪声相关性构建惩罚加权最小二乘算法对投影图像进行数据优化，利用改进的FBP算法重建，以提升DBT重建图像质量。参照CT成像中噪声模型构建方法，将电子噪声和量子噪声结合构建加权最小二乘算法来对噪声进行去除。通过合理的代价函数优化及选取合适的参数，投影图像恢复结果及重建DBT结果均显示，基于噪声相关的惩罚加权最小二乘算法在低剂量DBT成像中有着上佳表现，不同剂量图像的局部信噪比和对比度信噪比提升约3.6倍。同时，为进一步说明算法的有效性，实验中我们加入了BM3D滤波算法[24-25]对投影数据进行去噪处理，而后进行基于FBP的DBT重建。重建结果显示，在图像细节结构保持方面，本文算法优于BM3D算法。

![](images/1f85a9fb1777c1cc6559f5d25a064230a3947fc02f4c0cc6a2097f6eb1b85187.jpg)  
图7局部信噪比(LSNR)和对比度信噪比(CNR)感兴 趣区域图 Fig.7 Analysis of LSNR and CNR in the region of interest (ROI).The red and blue boxes indicate the ROIs for LSNR and CNR analysis,respectively.

本文对恢复后的投影数据采用了距离驱动反投影(DDBP)算法进行重建，DDBP算法相比传统的对整个图像基于路径的反投影缩短了计算时间[24]，与此同时，从精度的角度出发，DDBP算法考虑了图像像素和探测器的宽度问题，可以忽略将投影数据的锥形束近似平行束处理时对重建的影响。

总体来说，通过对不同剂量下的乳腺体模数据的研究对比显示，基于噪声相关性的惩罚加权最小二乘算法可以用于低剂量DBT成像投影数据降噪，该应用使低剂量的乳腺层析图像不再妥协于低图像质量，为乳腺层析技术的进一步发展提供了技术支持。

表1不同剂量下投影数据恢复前后的重建图像对比度信噪比(CNR) Tab.1 CNRs calculated from the reconstruction results before and after projection data recovery atdifferent doses   

<html><body><table><tr><td rowspan="2">CNR</td><td colspan="4">Dose (mA)</td></tr><tr><td>40</td><td>60</td><td>80</td><td>100</td></tr><tr><td>Before denoising</td><td>0.15</td><td>0.21</td><td>0.22</td><td>0.25</td></tr><tr><td>After denoising</td><td>0.63</td><td>0.91</td><td>1.06</td><td>1.29</td></tr></table></body></html>

# 表2不同剂量下投影数据恢复前后的重建图像局部信噪比(LSNR)

Tab.2LSNRs calculated from the reconstruction results before and after projection data recoveryatdifferentdoses   

<html><body><table><tr><td rowspan="2">LSNR</td><td colspan="4">Dose (mA)</td></tr><tr><td>40</td><td>60</td><td>80</td><td>100</td></tr><tr><td>Before denoising</td><td>4.69</td><td>5.37</td><td>6.24</td><td>6.85</td></tr><tr><td>After denoising</td><td>18.55</td><td>24.79</td><td>30.40</td><td>35.49</td></tr></table></body></html>

# 参考文献：

[1］陈万青,郑荣寿.中国女性乳腺癌发病死亡和生存状况[J].中国肿瘤 临床，2015,42(13):668-74.   
[2]Poplack SP,Tosteson TD，Kogel CA，et al． Digital breast tomosynthesis: initial experience in 98 women with abnormal digital screening mammography[J]． Am J Roentgenol,2007,189 (3): 616-23.   
[3]Alhajj M，Wicha MS,Benitohernandez A，et al.Prospective identification of tumorigenic breast cancer cells[J].P Natl Acad Sci USA,2003,100(7):3983-8.   
[4]曹厚德,蒋 琴.乳腺X线摄影若干技术要素的研究[J].中华放射学杂 志,2000,34(3): 155-8.   
[5]Van Engeland S,Snoeren PR,Huisman H,et al.Volumetric breast density estimation from full-field digital mammograms[J].IEEE T Med Imaging,2006,25(3): 273-82.   
[6]张 莉,洪常华.DBT与FFDM对致密型乳腺病变诊断对比分析[J].

医学影像学杂志,2016,26(8):1536-8.

[7]Skaane P,Gullien R,Bjorndal H,et al.Digital breast tomosynthesis (DBT):initial experience in a clinical setting [J].Acta Radiol,2012,53(5): 524-9.   
[8]Chen SC,Carton AK,Albert M,etal. Initial clinical experience with contrast-enhanced eigital breast tomosynthesis [J]. Acad Radiol,2007,14(2): 229-38.   
[9]Svahn TM.Letter to the Editor re:Diagnostic accuracy of digital breast tomosynthesis versus digital mammography for benign and malignantlesionsinbreasts:ameta-analysis[J]. Eur Radiol,2014,24(4): 928-9.   
[10]Karellas A,Lo JY, Orton CG.Cone beam x-ray CT willbe superior to digital x-ray tomosynthesis in imaging the breast and delineating cancer[J].Med Phys,2008,35(2): 409-11.   
[11] Sakurai T,Kawamata R,Kozai Y,et al． Relationship between radiationdosereductionandimagequalitychangein photostimulable phosphor luminescence X-ray imaging systems[J]. Dentomaxillofac Rad,2010,39(4): 207-15.   
[12]Gur D,Zuley ML,Anello MI,et al.Dose reduction in digital breasttomosynthesis(DBT）screeningusingsynthetically reconstructed projection images:an observer performance study[J]. Acad Radiol,2012,19(2): 166-71.   
[13]Manduca A,Yu L, Trzasko JD,et al. Projection space denoising with bilateral filtering and CT noise modeling for dose reduction in CT[J].Med Phys,2009,36(11): 4911-9.   
[14]Liao Z,Hu S,Li M,et al．Noise Estimation for single-slice sinogram of low-dose X-ray computed tomographyusing homogenous patch[J].Math Probl Eng,2011,2012(2): 208-12.   
[15]田秀梅,黄 静,林嘉慧.投影数据恢复方法在低剂量脑灌注CT成像 中的应用[J].南方医科大学学报,2017,37(4):470-4.   
[16]Wang J,Li T,Lu H,et al.Penalized weighted least-squares approach to sinogram noise reduction and image reconstruction for low-dose X-ray computed tomography [J]. IEEE T Med Imaging,2006,25(10):1272-83.   
[17]Ma J,Liang Z,Fan Y,et al.Variance analysis of $\mathbf { \sigma } _ { \mathbf { X } }$ -ray CT sinograms in the presence of electronic noise background[J].Med Phys,2012,39(7):4051-65.   
[18] Zhang H,Ouyang L，Ma J，et al.Noise correlation in CBCT projection data and its application for noise reduction in low-dose CBCT[J].Med Phys,2014,41(3): 1-10.   
[19]Whiting BR,Massoumzadeh P,Earl OA,et al.Properties of preprocessed sinogram data in x-ray computed tomography[J].Med Phys,2006,33(9):3290-303.   
[20]Huang SY, Yang K,Abbey CK,et al.A semiempirical linear model of indirect, flat-panel x-ray detectors[J].Med Phys,2012,39:2108- 18.   
[21]Wu T,Moore RH,Rafferty EA，et al．A comparison of reconstruction algorithms for breast tomosynthesis [J].Med Phys, 2004,31(9):2636-47.   
[22]Park Y,Park C,Cho H,et,al.Image reconstruction for digital breast tomosynthesis (DBT） by using projection-angle-dependent filter functions[J].JKorean Phys Soc,2014,65(5): 763-9.   
[23]De Man B,Basu S.Distance-driven projection and backprojection in three dimensions[J].Phys Med Biol,2004,49(11): 2463-75.   
[24]Danielyan A,Katkovnik V,Egiazarian K O,et al.BM3D frames and variational image deblurring|J].IEEET Image Process,2012, 21(4): 1715-28.   
[25] Yang FQ,Zhang DH,Huang KD,et,al. Image artifacts and noise reductionalgorithm forcone-beam computed tomography with lowsignal projections[J].JX-Ray Sci Technol,2017(9):1-14.   
[26]Liu Y,Ma J, Zhang H, et al.Low-mAs X-ray CT image reconstruction byadaptive-weightedTV-constrained penalized re-weighted leastsquares[J].JX-Ray Sci Technol,2014,22(4): 437-57.   
[27] Gong X,Glick SJ,Liu B,et al.A computer simulation study comparing lesion detection accuracy with digital mammography, breast tomosynthesis and cone-beam CT breast imaging[J]. Med Phys,2006,33(4):1041-52.