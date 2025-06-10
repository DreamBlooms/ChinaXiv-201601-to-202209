# 基于鸽子视顶盖神经元响应对不同颜色背景字符图像的重建研究“

王治忠‘，闫文明ʰ，王松伟a(郑州大学a.电气工程学院;b．产业技术研究院，郑州 450001)

摘要：解析脑神经元动作电位（Spike）表征的视觉信息是重要的科学问题，从 Spike信号中重建视觉刺激是解决该问题的重要途径。提供了一种从神经元Spike信号重建视觉刺激的方法，通过提取4种颜色背景下5种字符图像刺激的鸽视顶盖(OT）神经元的 Spike 发放率特征，构建线性逆滤波器和随机森林重建模型，优化模型参数，从而实现不同颜色背景的字符图像重建并分析了背景颜色对重建结果的影响。结果表明，最优参数条件下，线性逆滤波器模型对白、红、绿、蓝背景下字符图像的平均重建正确率达到 $0 . 9 2 2 5 { \scriptstyle \pm 0 . 0 2 6 8 }$ 、 $) . 9 0 2 7 { \scriptstyle \pm 0 . 0 2 0 4 }$ 、 $0 . 9 3 5 8 { \scriptstyle \pm 0 . 0 2 3 5 }$ 、 $0 . 8 1 7 0 { \scriptstyle \pm 0 . 0 3 1 3 }$ ，随机森林模型对应的图像平均重建正确率为 $0 . 9 4 9 9 { \scriptstyle \pm 0 . 0 2 5 5 }$ 、0.9228±0.0303、0.9472±0.0239、 $0 . 7 9 1 3 { \scriptstyle \pm 0 . 0 2 5 5 }$ 。方差分析发现，白色、红色和绿色背景图像重建结果无显著性差异，但这3种颜色背景图像重建结果与蓝色背景重建结果有显著性差异。

关键词：视顶盖；动作电位；发放率；重建；颜色背景；显著性差异 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.04.0489

# Research on character image reconstruction under different color backgrounds based on neuron spike signals in pigeon optic tectum

Wang Zhizhonga, Yan Wenmingb, Wang Songweia (a.SchooloflectricalEngineering;b.IndustrialTechnologyResearchInstitute,ZhengzhouUniversityhengzhou4, China)

Abstract: Itis an important scientific problem toanalyze visual informationrepresented byaction potentials (Spike)of brain neurons.Reconstructionof visual stimuli bySpike signals is an important approach to solvethis problem.This paper provides a method to reconstruct visual stimuli from Spike signals of neurons.This experiment adopted five kinds of character images under fourcolorbackgrounds tostimulate the pigeons,and then extractedthe firingrate characteristics ofSpike signals from theoptictectum(OT)neurons.Andthis experimentconstructedalinearinverse filterandarandom forestreconstructionmodel andoptimizedthe modelparameters toreconstructcharactersimages underdiferentcolorbackgrounds.Andthis paperanalyzed theefectof backgroundcolor onreconstruction results.The results show thatunder optimal parameter,the average reconstructionaccuracyofCharacterimages inwhite,red,greenandbluebackgroundsusingthelinearinverse filtermodelis $0 . 9 2 2 5 { \scriptstyle \pm 0 . 0 2 6 8 }$ ， $0 . 9 0 2 7 { \scriptstyle \pm 0 . 0 2 0 4 }$ $0 . 9 3 5 8 { \scriptstyle \pm 0 . 0 2 3 5 }$ , and the average reconstruction accuracy of character images using the random forest model is $0 . 9 4 9 9 { \scriptstyle \pm 0 . 0 2 5 5 }$ ,0.9228±0.0303, $0 . 9 4 7 2 { \scriptstyle \pm 0 . 0 2 3 9 }$ ,and $0 . 7 9 1 3 { \scriptstyle \pm 0 . 0 2 5 5 }$ . The analysis of variance shows that there is nosignificantdifferenceintheimagereconstructioresultsofwhite,red,andgreenbackgrounds,buttheimagereconstruction resultsofte threecolors backgroundsare significantlydiferent fromthereconstructionresultsoftheblue background image. Key words: the optic tectum; Spike; firing rate; reconstruction; color backgrounds; significant difference

# 0 引言

处理的载体，利用视觉相关核团神经元的Spike信号重建视觉刺激对探究神经元如何通过 Spike 信号表征视觉信息具有重要意义。本文通过提取神经元Spike 信号中的响应特征，并构建重建模型，从而实现不同颜色背景下的图像刺激重建，这不仅

脑的信息表征是神经科学、智能科学关心的重要科学问题。高频的神经元动作电位信号（Spike ${ > } 2 5 0 ~ \mathrm { H z }$ ）是脑信息传输、能为揭示视觉感知神经元信息处理回路的功能提出新视角[I]，同时也对更高效图像编码方式的探究以及仿生图像分类算法的研究提供了新思路[2]。

在生物视觉系统的研究中有很多关于基础视觉刺激解码的研究，其对本文图像刺激重建有启发性作用。2007年，Quiroga等人[3]采集人内侧颞叶区的Spike 响应信号，利用fisher 线性判别算法对视觉刺激进行了区分。2007年，Sang等人[4利用线性算法实现了on-off刺激光照强度的解码，并且解码的光照强度与真实光照强度的相关系数为0.8。2009年，Busse等人[5采用不同对比度的两个朝向光栅作为刺激模式，并用多通道电极阵列采集猫V1区神经元集群动作电位信号，实现了对比度的解码。2014年，Aubie等人采用Spike响应信号，利用最大似然估计器精确地解码出刺激的持续时间。2014年，Kuriki等人[7]研究人类的视觉皮层对正弦调制环形视觉刺激响应，发现人类视觉皮层中由亮度和颜色定义的两种神经元可以相互作用。2015年，Karimi等人[8]利用下颞叶（IT）皮层神经元的Spike响应信号实现了简单灰度刺激的解码。2017年，师黎等人[9]通过对鸽子研究也说明OT区神经元对亮度与颜色的编码不是独立的。2018年，Lazar等人[10]对V1区复杂细胞集群的稀疏功能表征进行研究，并利用该功能建模实现了对灰度视觉刺激的解码。上述文献研究结果表明：利用Spike 信号能够实现简单视觉刺激的解码，并且不同的视觉刺激属性之间存在相互影响。但神经元Spike信号能否表征字符图像等复杂刺激信息目前并不清楚，同时不同背景颜色图像刺激的重建效果是否有显著性差异也不得而知。

鸟类具有非常出色的视觉系统和颜色分辨能力，已成为研究视觉系统结构和功能特性的理想材料[II]。离顶盖通路是鸟类视觉信息处理的关键通路，视顶盖是离顶盖通路中一个及其重要的神经核团，其接收来自视网膜神经节细胞的颜色信息，并进行信息的编码和整合，然后将信息映射到丘脑圆核(thalamicnucleus rotundus)[12\~14]，因此实验选择视觉系统发达的鸽子作为实验动物。

本文研究了白色、红色、绿色与蓝色背景下黑色字符图像刺激的重建，并进一步探究了背景颜色对图像重建效果的影响。文中以4种颜色背景下的5种不同类型的字符图像（三角形、圆、十字、A、N）作为视觉刺激，采集了鸽子OT区神经元集群的 Spike 响应信号，提取了Spike信号的发放率特征，并分别构建了线性逆滤波器图像重建模型与随机森林图像重建模型。为获取较好的重建模型，需要对模型的通道个数(num)、时间窗□(bin)、刺激持续时间(T)、刺激后开始时间(delay)等参数进行优化。作为对重建质量的评估，文中用重建正确率指标对重建质量进行评价。通过实验数据分析可知：两种重建模型均能实现不同背景颜色下的图像重建，这说明Spike发放率特征能够表征图像刺激信息。进一步通过方差分析(ANOVA)发现：并非各背景颜色均对重建结果产生较大的影响，其中白色、红色和绿色背景下的字符图像重建结果之间没有显著性差异，但白色、红色和绿色背景下的字符图像重建结果均与蓝色背景下的图像重建结果有显著性差异，并且蓝色背景削弱了图像重建的质量。

# 1材料

# 1.1动物

实验动物采用专业养殖场（共创鸽业合作有限公司）的健康信鸽，体重为 $3 0 0 { \sim } 4 0 0 \ \mathrm { g }$ ，购买后在动物房饲养至少2周。每天给予动物光照、黑暗各 $1 2 \mathrm { h }$ ，动物房温度保持为 $( 2 3 \pm 2 ) ^ { \circ } \mathrm { C }$ 按时喂养，饲养和照料标准均遵循郑州大学实验动物管理规定。

# 1.2 手术

鸽子的麻醉方式为腹腔注射戊巴比妥钠 $( 1 . 5 \% , 3 . 0 \ \mathrm { m L / k g ) }$ 。在麻醉 $0 . 5 \mathrm { ~ h ~ }$ 之后将鸽子固定于立体定位仪（型号ST-5ND-B,成都仪器厂)。在鸽子左侧脑区确定视顶盖位置[15]，使用颅钻等器具进行开颅手术。利用微型操控仪 $( { \mathrm { M c } } 1 0 0 0 { \mathrm { e } } $ ，Siskiyou，SanDiego，CA，USA)将电极阵列（Clunbury Scientific，BloomfieldHills，MI，USA）植入脑区，植入深度为 $5 0 0 { \sim } 1 2 0 0 \mu \mathrm { m }$ 。所用电极为32通道，按照 $4 { \times } 8$ 的方式进行排列，行间隔为 $3 5 0 \mu \mathrm { m }$ 每行电极间隔为 $3 5 0 \mu \mathrm { m }$ ，电极阻抗为 $2 0 { \sim } 5 0 \mathrm { k } \Omega$ 。然后将电极阵列中的地线与骨螺钉相连用于接地，并使用cerebus 采集系统(美国Blackrock 公司)以 $2 ~ \mathrm { k H z }$ 采样率进行电生理信号的采集。在实验结束时用戊巴比妥钠（ $1 . 5 \%$ ， $5 . 0 \mathrm { m L / k g }$ ）对鸽子进行处死。

# 1.3视觉刺激

文中视觉刺激均采用matlab2014a软件编辑生成，刺激在CRT显示屏上进行显示，屏幕分辨率为 $1 2 8 0 \times 9 6 0$ ，屏幕刷新率为 $6 0 \mathrm { { H z } }$ ，屏幕中心与鸽子右眼的距离为 $4 0 \mathrm { c m }$ 。文中实验流程如图1(a)所示。实验主要包含两种刺激模式。一种是棋盘格刺激模式，其目的是为了测出神经元感受野的位置，如图1(b)。棋盘格刺激设计为：在灰色背景下设计 $1 5 { \times } 1 5$ 的棋盘格，在棋盘格内以 $2 0 \mathrm { H z }$ 的刷新率伪随机闪现黑色方块，重复20次。另一种刺激模式为字符图像刺激，即一幅图片按照从下到上、从右至左的顺序进行扫屏移动，一幅图片扫屏移动169次使图片所有像素块均经过感受野范围（一次循环169 帧)。对于每一帧图像刺激，本文重建位于感受野范围内的4个像素点（4个像素点相邻形成像素方块)。这种扫屏移动的优点是能克服感受野空间的不均匀分布。实验中对于每一种图像刺激均循环播放 5次，从中选用4次循环刺激和响应数据用于训练模型，剩下的1次用于图像重建。图像刺激以 $3 0 \mathrm { { H z } }$ 频率进行闪现，即每一帧图像的呈现时间为 $3 3 . 3 3 \mathrm { m s }$ ，以白色和绿色背景的三角形字符图像刺激为例，刺激播放过程如图1(c)所示，刺激图像中的红色圆代表感受野位置。

# 2 重建方法

文中所用实验信号为Spike信号，即大于 $2 5 0 \mathrm { { H z } }$ 的高频信号，它是由外界视觉刺激所引发的神经元放电活动，并且携带了能够表征视觉刺激的关键信息。利用神经元Spike信号实现字符图像重建，重建过程主要包含三个步骤：特征提取、重建模型构建、重建质量评估。

A A刺激播放重建质量评价与分析 A信号记录 重建121.41 21.45 21.49 21.53 21.57 21.61time/s(a)实验流程示意图300 ms250ms200 ms150 ms100 ms50 ms0ms(b）感受野刺激模式香 + 18.87 s18.83 s18.80 s18.77 s18.73 s18.70 s(c）图像刺激模式图1实验方法

# 2.1Spike 信号的特征提取

将每一帧刺激后神经元的响应时间 $\left( T - d e l a y \right)$ 均分为 $N$ 个时间窗 $( b i n )$ ，每个 $b i n$ 的时间长度为 $\left( T - d e l a y \right) / \textrm { N }$ ，计算每个神经元的每个时间窗内的 Spike 发放个数，构成实际刺激响应下的响应矩阵 $R$ 为

$$
\begin{array} { r } { R = \left[ { \begin{array} { l l l l l l l l l } { 1 } & { r _ { 1 , 1 } ^ { 1 } } & { r _ { 1 , 2 } ^ { 1 } } & { \dots } & { r _ { 1 , N } ^ { 1 } } & { \dots } & { r _ { 1 , 1 } ^ { \nu } } & { \dots } & { r _ { 1 , N } ^ { \nu } } \\ { 1 } & { r _ { 2 , 1 } ^ { 1 } } & { r _ { 2 , 2 } ^ { 1 } } & { \dots } & { r _ { 1 , N } ^ { 1 } } & { \dots } & { r _ { 2 , 1 } ^ { \nu } } & { \dots } & { r _ { 2 , N } ^ { \nu } } \\ { 1 } & { \dots } & { \dots } & { \dots } & { \dots } & { \dots } & { \dots } & { \dots } & { \dots } \\ { 1 } & { r _ { M , 1 } ^ { 1 } } & { r _ { M , 2 } ^ { 1 } } & { \dots } & { r _ { M , N } ^ { 1 } } & { \dots } & { r _ { M , 1 } ^ { \nu } } & { \dots } & { r _ { M , N } ^ { \nu } } \end{array} } \right] } \end{array}
$$

其中： $r _ { i , j } ^ { \nu }$ 表示在第 $i$ 个字符图像刺激时， $\mathbf { \Phi } _ { \nu }$ 通道 Spike 信号的第 $j$ 个时间窗 bin 的发放个数， $M$ 代表刺激总帧数。

# 2.2多元线性逆滤波器重建模型的构建

与上述响应矩阵所对应的刺激矩阵为 $s$ ：

$$
S = \left[ \begin{array} { c c c c c } { s _ { 1 , 1 } } & { s _ { 2 , 1 } } & { s _ { 3 , 1 } } & { s _ { 4 , 1 } } \\ { s _ { 1 , 2 } } & { s _ { 2 , 2 } } & { s _ { 3 , 2 } } & { s _ { 4 , 2 } } \\ { \ldots } & { \ldots } & { \ldots } & { \ldots } \\ { s _ { 1 , M } } & { s _ { 2 , M } } & { s _ { 3 , M } } & { s _ { 4 , M } } \end{array} \right]
$$

其中： $s _ { d , i }$ 表示第 $i$ 次刺激时，第 $d$ 个像素点处的实际值， $M$ 代表刺激的总帧数。

文中图像刺激循环5次播放（845帧)，文中选择前4次进行线性逆滤波器模型的训练，第5次循环进行重建，所以从 $R$ 矩阵中按顺序选取 $M _ { \mathfrak { l } }$ 行特征构成训练特征矩阵 $R _ { \mathrm { 1 } }$ ，其中$M _ { 1 } = 0 . 8 M$ ，并从刺激矩阵 $s$ 中对应选取 $M _ { \scriptscriptstyle 1 } \times _ { 4 }$ 维矩阵 $S _ { 1 }$ 作为训练目标变量。在获得 $R _ { 1 } \ : , \ : \ : S _ { 1 }$ 的基础上，求解权值向量 $F$ ，使得 $U _ { 1 } = R _ { 1 } \cdot F$ ，其中 $U _ { \scriptscriptstyle 1 }$ 为训练集图像重建矩阵。依据训练集中真实刺激与训练集中重建刺激间的方差 $( S _ { 1 } - U _ { 1 } ) ^ { T } ( S _ { 1 } - U _ { 1 } )$ 达到最小原则，求出逆滤波器矩阵 $F$ ， $F = ( R _ { 1 } ^ { T } R _ { 1 } ) ^ { - 1 } ( R _ { 1 } ^ { T } S _ { 1 } )$ ，其中 $F$ 的具体形式为：

$$
\begin{array} { r } { \boldsymbol { F } ^ { T } = [ a \quad f _ { 0 } ^ { 1 } \quad f _ { 1 } ^ { 1 } \quad . . . \quad f _ { N - 1 } ^ { 1 } \quad . . . \quad f _ { 0 } ^ { \nu } \quad . . . \quad f _ { N - 1 } ^ { \nu } ] } \end{array}
$$

其中： $f _ { j } ^ { \nu }$ 表示解码滤波器中神经元 $\mathbf { \Phi } _ { \nu }$ 在 $j \Delta t$ 时刻的值， $\mathbf { \Psi } _ { a }$ 代表着恒定补偿量。由于对每帧刺激的4个像素点进行重建，所以$f _ { j } ^ { \nu }$ 与 $a$ 是一个列向量 $( 4 { \times } 1 )$ 。根据上述训练得到的模型对测试数据进行图像重建，重建矩阵为

$$
\boldsymbol { U } = \boldsymbol { R _ { 2 } } \cdot \boldsymbol { F } = \boldsymbol { R _ { 2 } } ( \boldsymbol { R _ { 1 } } ^ { T } \boldsymbol { R _ { 1 } } ) ^ { - 1 } \boldsymbol { R _ { 1 } } ^ { T } \boldsymbol { S _ { 1 } }
$$

其中： $R _ { 2 }$ 为测试特征矩阵，与 $R _ { 2 }$ 对应的测试集原始图像刺激为$S _ { 2 }$ 如下：

$$
\begin{array} { r } { S _ { 2 } = \left[ \begin{array} { c c c c c } { S _ { 1 , M _ { 1 } + 1 } } & { S _ { 2 , M _ { 1 } + 1 } } & { S _ { 3 , M _ { 1 } + 1 } } & { S _ { 4 , M _ { 1 } + 1 } } \\ { S _ { 1 , M _ { 1 } + 2 } } & { S _ { 2 , M _ { 1 } + 2 } } & { S _ { 3 , M _ { 1 } + 2 } } & { S _ { 4 , M _ { 1 } + 2 } } \\ { \ldots } & { \ldots } & { \ldots } & { \ldots } \\ { S _ { 1 , M } } & { S _ { 2 , M } } & { S _ { 3 , M } } & { S _ { 4 , M } } \end{array} \right] , } \end{array}
$$

$$
U _ { 2 } = \left[ \begin{array} { c c c c } { { u _ { 1 , M _ { 1 } + 1 } } } & { { u _ { 2 , M _ { 1 } + 1 } } } & { { u _ { 3 , M _ { 1 } + 1 } } } & { { u _ { 4 , M _ { 1 } + 1 } } } \\ { { u _ { 1 , M _ { 1 } + 2 } } } & { { u _ { 2 , M _ { 1 } + 2 } } } & { { u _ { 3 , M _ { 1 } + 2 } } } & { { u _ { 4 , M _ { 1 } + 2 } } } \\ { { \ldots } } & { { \ldots } } & { { \ldots } } & { { \ldots } } \\ { { u _ { 1 , M } } } & { { u _ { 2 , M } } } & { { u _ { 3 , M } } } & { { u _ { 4 , M } } } \end{array} \right]
$$

$\boldsymbol { u } _ { d , i }$ 表示第 $i$ 个刺激时,第 $d$ 个像素点处的图像刺激重建值。

# 2.3随机森林重建模型的构建

Breiman于2001年提出随机森林(RF)算法，RF是一种统计学习理论，它是利用bootstrap重抽样方法从原始样本中进行样本抽取，对每个bootstrap样本进行决策树建模，然后组合多棵决策树的预测，通过投票得出最终预测结果[16]。随机森林具备有效处理高维度特征数据集的能力，并能获取较高分类正确率，这是文中选取随机森林（RF）算法进行图像刺激重建的主要原因。文中同样利用前4次循环的神经元响应信号特征（响应矩阵 $R _ { \mathrm { { l } } }$ ）作为RF 模型的输入特征，对应字符图像的实际矩阵 $S _ { \mathrm { 1 } }$ 作为RF 算法的训练标签来训练重建模型。在获得RF 重建模型之后，利用第5次循环的响应矩阵 $R _ { 2 }$ 作为重建数据实现

对图像刺激的重建。

在 matlab 2014a 运行环境下使用 classRF_train(X,Y,ntree,mtry)函数进行RF模型的构建。其中，X代表训练样本中的输入数据，Y代表训练样本中的训练目标变量，ntree代表RF算法模型中决策树的数目，mtry代表单个决策树特征的使用数量。随机森林算法中决策树的数目和特征的最大数量对重建结果产生影响，文中刺激图像重建中的决策树数目为500，特征的最大数量为总特征数的算术平方根，此时能对字符图像刺激较好地实现重建。

# 2.4重建结果的评估方法

为了评价重建刺激矩阵 $U _ { _ { 2 } }$ 与实际刺激矩阵 $S _ { 2 }$ 之间的相似度，文中以重建正确率作为图像重建的评估标准，并以此来量化不同参数下重建效果的影响。其评估公式为

$$
c _ { s , u } = { \frac { \sum ( S _ { 2 } = U _ { 2 } ) } { 4 ^ { * } M _ { 2 } } }
$$

其中： $M _ { 2 }$ 为测试数据集的刺激帧数， $c _ { s , u }$ 为重建正确率，是真实刺激与重建刺激矩阵相同像素点个数与图像总像素点个数的比值。 $c _ { s , u }$ 作为评价指标其取值范围为 $c _ { s , u } \subseteq [ 0 \mathrm { ~ 1 ] ~ }$ ，其值越高代表重建质量越好。 $c _ { s , u } = 0$ 代表未能重建， $c _ { s , u } = 1$ 代表对原始刺激进行了完全重建。

# 3 结果与分析

本文的实验数据来自于5只鸽子OT区（ $5 0 0 \sim 1 2 0 0 \mu \mathrm { m } )$ 内神经元集群的Spike信号，数据分析均利用MATLAB2014a软件完成。在进行图像刺激之前，首先利用棋盘格刺激确定神经元感受野位置，使得字符图像刺激均能在感受野内播放。

# 3.1重建参数的优化选择

由于利用Spike 信号对字符重建的效果与通道个数(mum)、时间窗口(bin)、刺激持续时间 $( T )$ 、刺激后不同开始时间(delay)有着密切的关系，因此需要分别对4种背景颜色下的字符重建模型选出最优模型参数。下面以线性逆滤波器算法为例对重建模型参数进行优化。

首先将基础参数选择为： $T { = } 0 . 2 5 \mathrm { s }$ ，时间窗□ $b i n { = } 5 \mathrm { m s }$ ，刺激后开始时间 $d e l a y { = } 0 \mathrm { m s }$ ，在此参数下，利用单通道对图像进行重建，并按照重建正确率降序进行通道排序。接下来按照重建正确率降序依次叠加通道进行图像重建，4种颜色背景下图像重建正确率随通道数目变化如图2(a)所示，白、红、绿、蓝各颜色背景下重建正确率变化曲线均随通道数目的增加而升高并呈现饱和趋势，选取各变化曲线饱和点作为最优通道数目，其对应的最大标准差为0.0241、0.0429、0.0324、0.0230。在选定通道数目的基础上改变bin的大小，各颜色背景下图像重建正确率变化趋势如图2(b)所示，其变化趋势随着bin 的增加而衰减，记录各颜色背景下重建正确率变化曲线最大值所对应的bin值作为最优值，白、红、绿、蓝背景对应的最大标准差为0.0272、0.0366、0.0241、0.0722。接下来，在上述最优参数的基础上改变 $T$ 的大小，各背景下的图像重建正确率如图2(c)所示，其均随着 $T$ 的增加而升高并最终达到饱和值，选取饱和值对应的T为最优值，对应的最大标准差为0.0366、0.0303、0.0262、0.0387。在进一步确定最优T后，改变delay，重建结果如图2(d)所示。从图中可以看出，各颜色背景下图像重建正确率随着delay的增加而降低，本文选取各颜色背景下正确率变化曲线上的最大值所对应的delay作为最优值，对应的最大标准差为0.0523、0.0324、0.0324、0.0293。上述各颜色背景下的最优参数如表1所示。

![](images/a0ca9d0abea83614380c2d53f3db010e5a17a55b79be64877f56907fb90d879b.jpg)  
(a)不同通道数个数参数优化过程

![](images/b92ff764bc01f2c6cac9c7a14e448241794f0a160e99d0a4d434d6418e3292d5.jpg)  
(b）不同时间窗口优化过程

![](images/be382a012790f9cda9d8a26488da9608940d149252a6e2982f2964ef6912fd48.jpg)  
(c）不同持续时间优化过程

![](images/016fcf1a20844ec65a88218f5548074eb49f2518692117e5a710bfe155027e5c.jpg)  
图2重建参数优化过程  
Fig.2Optimization process of reconstruction parameter

对于随机森林重建模型也需要进行参数的优化，其优化过程如上述一致，其各颜色背景下的最优参数如表2所示。

表1线性逆滤波器重建模型在不同背景下的最优重建参数

Table 1Optimal reconstruction parameters of linear inverse filter reconstruction model in different backgrounds   

<html><body><table><tr><td>参数</td><td>white</td><td>red</td><td>green</td><td>blue</td></tr><tr><td>num</td><td>8</td><td>9</td><td>8</td><td>9</td></tr><tr><td>bin/ms</td><td>2</td><td>4</td><td>5</td><td>3</td></tr><tr><td>T/s</td><td>0.18</td><td>0.20</td><td>0.24</td><td>0.28</td></tr><tr><td>delay/ms</td><td>0</td><td>10</td><td>0</td><td>10</td></tr></table></body></html>

表2随机森林重建模型在不同背景下的最优重建参数

Table 2Optimal reconstruction parameters of random forest reconstruction model in different backgrounds   

<html><body><table><tr><td>参数</td><td>white</td><td>red</td><td>green</td><td>blue</td></tr><tr><td>num</td><td>7</td><td>9</td><td>9</td><td>9</td></tr><tr><td>bin/ms</td><td>6</td><td>6</td><td>3</td><td>2</td></tr><tr><td>T/s</td><td>0.18</td><td>0.20</td><td>0.20</td><td>0.22</td></tr><tr><td>delay/ms</td><td>10</td><td>5</td><td>10</td><td>60</td></tr></table></body></html>

# 3.2重建结果展示与分析

实验字符图形刺激包括：三角形、圆、十字、A、N，每种图像刺激分别设计4种不同背景颜色刺激，然后分别采用最优的线性逆滤波器与随机森林重建模型实现对字符图像刺激的重建，并通过重建正确率指标对字符图像重建质量进行评估。最后以方差分析的方式分析各背景颜色下的重建结果是否存在差异性。

文中构建了线性逆滤波器与随机森林重建模型对字符图像进行重建。真实字符图像刺激如图3(a)所示，线性逆滤波器重建模型的字符图像重建结果如图3(b)所示，该模型对5种字符在各背景颜色下的重建正确率统计结果如图4(a)，随机森林重建模型字符图像重建结果如图3(c)所示，其重建正确率统计结果如图4(b)。其中白色、红色、绿色、蓝色背景下5种刺激图像利用线性逆滤波器模型的平均重建正确率能够达到$0 . 9 2 2 5 \pm 0 . 0 2 6 8 , 0 . 9 0 2 7 \pm 0 . 0 2 0 4 , 0 . 9 3 5 8 \pm 0 . 0 2 3 5 , 0 . 8 1 7 0 \pm 0 . 0 3 1 3$ 。对于随机森林重建模型，对应5种不同颜色背景下的图像平均重建正确率分别达到 $0 . 9 4 9 9 { \scriptstyle \pm 0 . 0 2 5 5 }$ 、0.9228±0.0303、$0 . 9 4 7 2 { \scriptstyle \pm 0 . 0 2 3 9 }$ 、 $0 . 7 9 1 3 { \scriptstyle \pm 0 . 0 2 5 5 }$ 。

将背景颜色视为变量因素，4种背景颜色表示该因素的4个水平，并将字符图像重建正确率作为因变量进行方差分析。文中对白色、红色、绿色、蓝色背景下的字符图像重建结果进行了显著性分析，并用多重分析方法进一步探究了哪些背景颜色的图像重建结果之间有显著性差异。

首先根据线性逆滤波器模型重建结果进行分析，计算4种颜色背景下重建结果显著性得： $\mathrm { F } _ { 1 } ( 3 , 3 6 ) { = } 2 1 . 2 7$ ， $\mathsf { p } _ { 1 } { = } 4 . 2 3 { \times } 1 0 ^ { - 8 }$ ，由于显著性水平 $\mathsf { p } _ { 1 } { < } 0 . 0 5$ ，因此4种颜色背景下的重建结果具有显著性差异。接下来通过多重比较进行分析以便获得哪些背景颜色的图像重建结果有显著性差异。通过计算发现，白色背景与红色背景的显著性为： $\mathrm { F } _ { \mathrm { w r l } } ( 1 , 1 8 ) { = } 1 . 5 1$ ， $\mathfrak { p } _ { \mathrm { w r l } } { = } 0 . 2 4$ ，由于$\mathfrak { p } _ { \mathrm { w r l } } \mathord { \left. \begin{array} { r l r } { \mathord { \left. \begin{array} { r l r } & { } \end{array} \right. } } & { } \end{array} \right. }$ ，则红色与白色背景的重建结果并没有显著性差异。此外，白色背景与绿色背景、白色背景与蓝色背景、红色背景与绿色背景、红色背景与蓝色背景、绿色背景与蓝色背景的重建结果显著性水平分别为： $\mathrm { p } _ { \mathrm { w g l } } { = } 0 . 6 9 \cdot \mathrm { p } _ { \mathrm { w b l } } { = } 3 . 3 4 { \times } 1 0 ^ { - 5 }$ ， $\mathrm { p r g 1 } { = } 0 . 0 7$ 、$\mathsf { p } _ { \mathrm { r b l } } { = } 4 . 7 0 { \times } 1 0 ^ { - 5 }$ 、 $\mathsf { p } _ { \mathrm { g b l } } { = } 8 . 4 9 { \times } 1 0 ^ { - 8 }$ ，因此可以看出：白色、红色和绿色背景下图像重建结果之间没有显著性差异，但白色、红色和绿色背景下图像重建结果均与蓝色背景图像重建结果有显著性差异，并且蓝色背景削弱了图像重建的质量。

△O+AN 合合合 十+ + AAA ++ ? AAA 1 NNNN (b)线性逆滤波器模型重建的字符图像刺激 △O+A a 去天 N NNN (c）随机森林模型重建的字符图像刺激

利用RF模型的重建正确率进行方差分析。分析得：4种颜色背景字符图像重建结果显著性水平 $\mathrm { F } _ { 2 } ( 3 , 3 6 ) { = } 4 5 . 3 3$ ，$\mathrm { p } _ { 2 } { = } 2 . 6 0 { \times } 1 0 ^ { - 1 2 }$ ，由于 $\mathtt { p } _ { 2 } { < } 0 . 0 5$ 因此在RF 模型下各颜色背景下的重建结果同样具有显著性差异。接下来进行多重比较分析，白色背景与红色背景、白色背景与绿色背景、白色背景与蓝色背景、红色背景与绿色背景、红色背景与蓝色背景、绿色背景与蓝色背景的重建结果显著性水平分别为： $\mathtt { p } _ { \mathrm { w r } 2 } { = } 0 . 1 2 \cdot \mathtt { p } _ { \mathrm { w g } 2 } { = } 0 . 9 7 .$ $\mathsf { p } _ { \mathrm { w b } 2 } { = } 5 . 7 9 { \times } 1 0 ^ { - 8 }$ 、 $\mathtt { p } _ { \mathtt { r g } 2 } { = } 0 . 1 3$ 、 $\mathsf { p } _ { \mathrm { r b } 2 } { = } 1 . 4 6 { \times } 1 0 ^ { - 6 }$ 、 $\mathsf { p } _ { \mathrm { g b } 2 } { = } 7 . 5 7 { \times } 1 0 ^ { - 8 }$ 。从中可以看出，RF重建模型对不同颜色背景重建结果的显著性结论与线性逆滤波器重建结果显著性结论保持一致。

![](images/fb001cdf5bc4afa269e5981334589de4c69852bf561f48c9aa38589204519168.jpg)  
图3真实图像与两种模型下的重建结果展示

随机森林是一种非线性建模工具[17]，而线性逆滤波器则是一种线性建模方式。两种模型对字符图像刺激均能有效实现重建，并且不同背景下图像重建结果的显著性差异存在一致性，这不仅证明以Spike发放率特征可以用于重建图像信息，同时也可以说明对不同背景刺激图像重建效果的差异性并非来源于算法本身。

(a)线性逆滤波器模型下各字符图像的重建正确率

![](images/7b4b73fcb865cce8c4db003dfaefd251765d2da3f217e25a9f19d3c2c638ac9b.jpg)  
Fig.3Real image and reconstruction results under two models   
图4不同颜色背景下两种模型对图像重建统计结果 Fig.4Image reconstruction statistical results of two models under different color backgrounds

# 4 结束语

由神经元的响应重建相应的视觉刺激是理解视觉编码的一个重要步骤。本文以4种颜色背景下的5种字符图像作为视觉图像刺激，利用神经元的Spike发放率特征，构建线性逆滤波器与随机森林两种重建模型，对白色、红色、绿色、蓝色背景下的字符图像刺激进行重建，并分析背景颜色对重建结果的影响，结果表明：a）两种图像重建模型均能利用Spike发放率特征实现字符图像刺激重建，说明Spike发放率特征能够用于表征字符图像信息；b)通过对以上两种模型的重建结果进行的方差分析表明：白色、红色和绿色背景下图像重建结果之间无显著性差异，但白色、红色和绿色背景下图像重建结果均与蓝色背景图像重建结果有显著性差异，并且蓝色背景削弱了图像重建的质量。

实验中字符图像重建的数据维度较高，文中所采用的线性逆滤波器与随机森林两种算法均具有处理高维度数据的能力，并且能对字符图像刺激以较高的正确率实现重建，但两种算法也存在着不足之处。首先，线性逆滤波器算法的噪声鲁棒性较差，当Spike信号存在一定量噪声时往往对重建结果产生影响;其次，随机森林算法在处理大数据时会导致时间复杂度明显升高，从而使运行效率降低。

在未来的研究工作中，一方面考虑使用 Spike 信号与LFP(localfieldpotential)信号的联合特征来提高图像的重建正确率[18]，另一方面也将在此研究的基础上继续对自然图像、视频等更为复杂的视觉刺激进行重建研究，这不仅能进一步为探究生物视觉系统的图像信息表征机制提供依据，同时也有助于推进图像理解技术方面的发展[19]。

# 参考文献：

[1]Stanley G B,Li Feifei,Dan Yang.Reconstruction of natural scenes from ensemble responses in the lateral geniculate nucleus [J].Journal of Neuroscience,1999,19 (18): 8036-8042.   
[2] 柳培忠，王守觉．基于视觉仿生的图像目标分类算法[J].计算机工程 与设计,2014,35 (5): 1722-1726.(Liu Peizhong,Wang Shoujue.Algorithm of image classification recognition based on vision bionic [J]. Computer Engineering and Design,2014,35 (5): 1722-1726.)   
[3]Quiroga R Q,ReddyL,Koch C,et al.Decoding visual inputs from multiple neurons in the human temporal lobe [J]. Journal of Neurophysiology,2007, 98 (4): 1997-2007.   
[4]Sang BR,Ye JH, Yong SG,et al. Optimal linear filter based light intensity decoding from rabbit retinal ganglion cell spike trains [C]/ Proc of the 3rd International IEEE EMBS Conference on Neural Engineering. Piscataway, NJ: IEEE Press,2007: 608-610.   
[5]Busse L,Wade A R, Carandini M. Representation of concurrent stimuli by population activity in visual cortex [J].Neuron,20o9,64 (6): 931-942.   
[6]Aubie B,Sayegh R,Fremouw T,et al.Decoding stimulus duration from neural responses in the auditory midbrain [J]. Journal of Neurophysiology, 2014,112 (10):2432-2445.   
[7]Kuriki I,Xie Hongfei,Tokunaga R,et al. Interaction of color-defined and luminance-defined motion signals in human visual cortex [J]. Journal of Vision,2014,14 (10): 291-291.   
[8]Babolhavaeji A,Karimi S,Ghaffari A,et al. Optimal temporal resolution for decoding of visual stimuli in inferior temporal cortex [C]//Proc of the 21th Iranian Conference on Biomedical Engineering. Piscataway,NJ: IEEE Press, 2015:109-112.   
[9]师黎，马山峰，王治忠．视顶盖神经元在不同颜色背景下的亮度解码 [J]．科学技术与工程,2017,17(29): 27-32.(Shi Li,Ma Shanfeng,Wang Zhizhong.Decoding visual luminance from different color backgrounds in the optic tectum neurons [J]. Science Technology and Engineering,2017,17 (29): 27-32.)   
[10] Lazar AA,Ukani NH, Zhou Yiyin,et al. Sparse functional identification of complex cells from spike times and the decoding of visual stimuli [J]. Journal of Mathematical Neuroscience,2018,8(1): 1-2.   
[11] Wylie DR,Gutierrezibanez C,Pakan JM,et al. The optic tectum of birds: mapping our way to understanding visual processing [J]. Canadian Journal of Experimental Psychology,2009,63 (4):328-338.   
[12] Goddard CA, Sridharan D,Huguenard JR,et al. Gamma oscillations are generated locally in an attention-related midbrain network[J]. Neuron,2012, 73 (3): 567-580.   
[13] Major DE,Luksch H,Karten HJ.Bottlebrush dendritic endings and large dendritic fields:Motion-detecting neurons in the mammalian tectum [J]. Journal of Comparative Neurology,2015,423 (2): 243-260.   
[14] Mysore S P, Knudsen E I. The role of a midbrain network in competitive stimulus selection [J].Current Opinion in Neurobiology,2011,21 (4): 653- 660.   
[15] Letelier JC,Marin G, Sentis E,et al. The mapping of the visual field onto the dorso-lateral tectum of the pigeon (Columba livia) and its relations with retinal specializations [J]. Journal of Neuroscience Methods,2oo4,132 (2): 161-168.   
[16] Breiman L. Random Forests [J]. Machine Learning,2001,45 (1): 5-32.   
[17]方匡南，吴见彬，朱建平，等．随机森林方法研究综述[J].统计与信 息论坛,2011,26 (3):32-38.(Fang Kuangnan, Wu Jianbin,Zhu Jianping, et al.Areview oftechnologies on random forests [J]. Statistics and Information Forum,2011,26 (3):32-38.)   
[18] Wang Songwei,Liu LIjun,Wang Zhizhong,et al.Luminance information decoding on the basis of local field potential sigsnals of pigeon optic tectum neurons [J].Neuroreport,2017,28 (16):1036-1042.   
[19]胡德昆．基于生物视觉感知机制的图像理解技术研究[D]．成都：电子 科技大学，2012.(Hu Dekun.The research on technology of image understanding based on biological visual perception [D] Cheng Du: University of Electronic Science and Technology,2012.）