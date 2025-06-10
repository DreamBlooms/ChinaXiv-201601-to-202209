# 复杂大交通场景弱小目标检测技术

华夏1，王新晴1，马昭烨1，王东1,²，邵发明1(1．陆军工程大学，南京 210007;2．南部战区陆军第二工程科研设计所，昆明 650222)

摘要：针对现有基于大数据和深度学习的目标检测框架对于高分辨率复杂大场景中低分辨率小目标识别效果较差，多目标检测的精度和实时性难以平衡的问题,改进了基于深度学习的目标检测框架 SSD(single shot multibox detector)，提出一种改进的多目标检测框架 DRZ-SSD（DRZ)，将其专用于复杂大交通场景多目标检测。检测以从粗到细的策略进行，分别训练一个低分辨率粗略检测器和一个高分辨率精细检测器，对高分辨率图像进行下采样获得低分辨率版本，设计了一种基于增强学习的动态区域放大网络框架(DRZN)，动态放大低分辨率弱小目标区域至高分辨率再使用精细检测器进行检测识别，剩余图像区域使用粗略检测器进行检测，对弱小目标的检测与识别精度以及运算效率的提高效果明显；采用模糊阈值法调整自适应阈值策略在避免适应数据集的同时提高模型的决策能力，显著降低检测漏警率和虚警率。实验表明，改进后的DRZ-SSD 在应对弱小目标、多目标、杂乱背景、遮挡等检测难度较大的情况时，均能获得较好的效果。通过在指定数据集上测试，相比于其他基于深度学习的目标检测框架，各类目标识别的平均准确率提高了 $4 \%$ ，平均准确率均值提高了约 $9 \%$ ，多目标检测率提高 $1 3 { \sim } 3 4 \%$ ，检测识别速率达到38帧/s，实现了算法精度与运行速率的平衡。

关键词：机器视觉；深度学习；神经网络；交通场景多目标检测；增强学习；自适应 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.05.0343

# Detection of dim and small targets in complex large traffic scenes

Hua Xial, Wang Xinqingl, Ma Zhaoye1, Wang Dong1,², Shao Faming1 (1.ArmyEngineingUnversityNanjing0oina;2condInstitutefngineeingResearch&ignuh Theatre Command,Kunming 650222,China)

Abstract: Aimingatthe problems that the existing target detection frameworkbasedonbigdataand depth learning has poor recognition efectonlow-resolutionsmalltargets inhigh-resolutioncomplex large-field scenes,and theaccuracyandreal-time performanceof multi-targetdetectionaredificulttobalance,improvethesingleshotmulti-boxdetector basedondepth learning,and propose animproved multi-targetdetectionframework DRZ-SSD(dynamicregionzoom-in,DRZ),whichis dedicated tomulti-target detection incomplex large traficscenes.Thedetectioniscarriedout inacoarse-to-finestrategy, trainingalow-resolutioncoarse detectorandahigh-resolution finedetectorrespectively,downsampling the high-resolution image to obtain a low-resolution version,designing a dynamic region zoom -in network based onenhanced learning, dynamicallyenlarging thelow-resolution smal targetregiontoahigh-resolutionand thenusing thefinedetectortocarryout detectionand identification,and detecting theremaining imageregion byusing thecoarse detector,sothatthedetectionand identificationaccuracyof thesmalltargetand theimprovement efectofthe operation effciencyareobvious; Adopting fuzzy threshold method toadjust the adaptive threshold strategycannotonlyavoid adapting tothe datasetbut also improve the decision-making ability of the modeland significantlyreduce the detection missd alarmrateand false alarm rate. Experiments show thatthe improved drz-SSDcan achieve goodresults when dealing with weak targets,multi -targets, cluttered background,occlusionandother dificult detection situations.Through testingonthespecifieddata set,ompared with other target detection frameworks based on in-depth learning,the average acuracyrate of various typesof target recognition has increased by $4 \%$ ,the average accuracy rate has increased by $9 \%$ , the multi-target detection rate has increased by $13 \mathrm { { \sim } } 3 4 \mathrm { ~ \% }$ ,and the detection and recognition rate has reached 38 frames $/ \mathrm { ~ s ~ }$ ,realizing the balance between the accuracy of the algorithm and the running rate.

Keywords: machine vision；deep learning;neural network；traffic scene multi-target detection；reinforcement learning; self-adaptation

# 0 引言

域的核心技术，有着重要的研究意义[]。

交通场景中的行人、车辆目标检测与识别是目标检测技术的重要分支，是自动驾驶、机器人以及智能视频监控等研究领

深度学习为基于深层人工神经网络的学习方法，基于深度学习的目标检测算法可应用于多种检测场景，综合性强，能够同时检测和识别多类目标，主动性好。各种类型的人工神经网络结构中，深度卷积网络具有强大的特征提取能力，越来越多的用于图像分类的网络结构被提出，不断提升了深度卷积网络在特征提取方面的优势，在图像识别、图像分割、目标检测、场景分类等视觉任务中，取得了非常好的效果[2]。FasterRCNN[4]替代掉费时的 selective search方法，速度提高了，RPN产生的regionproposal质量高，准确率（mAP）也提高了，但是NPR产生的在图像边缘的region proposal 信息被丢弃了。YOLO[5]将物体检测作为回归问题进行求解，整个检测网络 pipeline 简单，且训练只需一次完成，YOLO在训练和推理过程中能"看到”整张图像的整体信息，背景误检率低,而基于region proposal 的物体检测方法（如FastRCNN）在检测过程中，只“看到”候选框内的局部图像信息,但是识别物体位置精准性差，召回率低，尤其是对小目标和密集目标检测识别效果差。

SSD，全称 single shot multibox detector[3]，是Liu Wei 在ECCV2016上提出的一种目标检测算法，截至目前是主要的检测框架之一，相比FasterRCNN[4有明显的速度优势，相比YOLO[5]又有明显的平均准确率均值（mAP）优势。SSD具有如下主要特点：从YOLO中继承了将detection 转化为regression的思路，同时一次即可完成网络训练；基于FasterRCNN中的anchor，提出了相似的priorbox；加入基于特征金字塔[6]（PyramidalFeatureHierarchy）的检测方式，相当于半个FPN[6]思路。尽管SSD在特定数据集上已经取得了较高的准确率，具有较好的实时性，但是模型的训练过程非常耗时，对训练样本的质和量依赖严重；通过图像的颜色、边缘等信息来检测目标，其对于弱小目标和大面积遮挡目标等缺乏图像信息的目标检测效果不佳；算法检测效率仍然有待提高，以满足装备运行实时性的要求。

本文针对复杂大交通场景下行人、车辆目标检测任务的特点和需求，对传统SSD算法进行了以下两点改进：1）利用增强学习和顺序搜索方法，结合大交通场景目标检测任务的特点和需求，提出了一种动态区域放大网络框架（DynamicRegionZoom-inNetwork,DRZN)，该网络框架通过下采样图像，大幅降低了运算量，同时通过动态区域放大保持了高分辨率图像中不同尺寸目标的检测精度，对低分辨率弱小目标的检测与识别精度提高效果明显，降低检测漏警率；2）针对SSD检测固定置信度阈值不够灵活的缺陷，采用模糊阈值法调整自适应阈值策略在避免适应数据集的同时提高模型的决策能力，显著降低检测漏警率和虚警率。

# 1 动态区域放大网络框架

SSD采用了特征金字塔结构进行检测，即检测时利用了conv4-3，conv-7（FC7)，conv6-2，conv7-2，conv8_2，conv9_2这些大小不同的 feature maps，在多个 feature maps上同时进行softmax分类和位置回归，对弱小目标有较好的检测精度[3]，但是在复杂大交通场景下对低分辨率弱小目标的检测效果仍然不够理想。

针对 SSD存在的复杂大场景下对于低分辨率弱小目标检测困难问题，本文提出了一种动态区域放大网络框架（DRZN)，该网络框架通过对高分辨率大场景图像进行下采样，降低了目标检测的计算量，同时通过动态区域放大保持了高分辨率图像中低分辨率弱小目标的检测精度，对弱小目标的检测与识别精度的提高效果明显。检测以从粗到细的方式进行，首先对图像的下采样版本进行检测，然后对被识别为可能提高检测精度的区域顺序放大至较高分辨率版本再进行检测。该方法建立在增强学习的基础上，由一个放大精度增益回归网络[(R-net)和一个放大区域动态选择算法（Zoom-inRegionChoose）两部分组成，前者学习粗检测和精检测之间的相关性，并预测放大区域的精度增益，后者依据前者学习和预测结果动态选择需要被放大的区域。

首先对图像的下采样版本执行粗略检测，以降低运算量提高运行效率，然后顺序地选择可能存在低分辨率小目标的区域进行放大操作然后分析来保证对低分辨率小目标的识别精度。采用强化学习方法从检测精度和计算成本两个方面对放大奖励进行建模，并动态选择一系列区域放大至高分辨率再进行分析。算法总体框架如图1所示。

![](images/a46e77480da7899178ae20ab929addbd3f905db9c189c5ef4f6eebf228900616.jpg)  
图1动态区域放大网络架构

# 1.1放大精度增益回归网络R-net

顺序搜索。处理高分辨率大场景图像的策略是避免处理整个图像，而是顺序地检测疑似目标的小区域。

强化学习（reinforcementlearning，RL）。RL是用于学习顺序搜索策略的通用机制，因为它允许模型考虑一系列动作的效果而不仅仅是单个动作的效果[8]。RL是在尝试的过程中学习到在特定的情境下选择哪种行动可以得到最大的回报。在很多场景中，当前的行动不仅会影响当前的收益，还会影响之后的状态和一系列的收益。RL最重要的三个特征在于：基本是以一种闭环的形式；不会直接指示选择哪种行动；一系列的行动和奖励信号对之后的行动都会产生较长时间的影响。RL采用的是边获得样本边学习的方式，在获得样本之后更新自己的学习模型，利用当前的模型来指导下一步的行动，下一步的行动获得收益回馈之后再更新学习模型，不断迭代重复直到学习模型达到收敛。

本算法采用由粗到细的检测策略，在低分辨率下应用粗检测器，并利用该检测器的输出结果来指导对高分辨率目标的深入搜索。虽然粗略检测器将不如精细检测器精确，但它将识别需要进一步分析的图像区域，从而仅在有希望的区域中产生高分辨率检测的运算成本。算法主要运用由两个机制组成：a）学习粗检测器和细检测器之间的统计关系的机制，以便在给定粗检测器输出的情况下预测哪些区域需要放大；b)用于在给定粗略检测器输出和需要由精细检测器分析的区域的情况下选择要以高分辨率分析区域的序列的机制。

本文策略可以被表述为马尔可夫决策过程。在每个步骤，系统先观察当前状态，估计采取不同行动的潜在成本感知回报，并选择具有最大长期成本感知回报的行动[9。要素包括:

a)动作。该算法以高分辨率依次分析具有高放大回报的区域。在此上下文中，动作对应于选择要以高分辨率分析的区域。每个动作可以由向量 $\left( { x , y , w , h } \right)$ 来表示；其中 $\left( x , y \right)$ 表示指定区域位置， $\scriptstyle { \left( w , h \right) }$ 表示指定区域的大小。在每个步骤中，该算法根据潜在的长期奖励对采取一组潜在的动作(矩形区域的列表)进行评分。

b)状态集。表示编码两种类型的信息：待分析区域的预测精度增益；以及已经以高分辨率分析的区域的历史(同一区域不应被多次放大)。本文设计了一个放大精度增益回归网络(R-net)来学习信息精度增益图(AGmap)作为状态表示。AGmap具有与输入图像相同的宽度和高度。AGmap中的每个像素的值是对输入图像中包括那个像素可以提高多少检测精度的估计。所以，AGmap 提供了用于选择不同动作的检测精度增益。在采取动作之后，对应于AG映射中所选区域的值相应地减小，因此AG映射可以动态地记录动作历史。

c)损失回报函数。状态对放大每个图像子区域的预测精度增益进行编码。为了在有限的计算量下保持高精度，定义了一个损失回报函数如式1。给定状态和动作，损失回报函数通过考虑成本增量和精度改进对每个动作(缩放区域)进行评分

$$
R { \left( s _ { t a t e s } , a _ { c t i o n s } \right) } = \sum _ { k \in a _ { c t i o n s } } { \left| g _ { k } - p _ { k } ^ { l } \right| } { - \left| g _ { k } - p _ { k } ^ { h } \right| } - \lambda _ { 2 } { \frac { b _ { 1 } } { B } }
$$

其中：动作中 $k$ 表示目标 $k$ 包含在由动作选择的区域中。 $p _ { k } ^ { l }$ 和${ p } _ { k } ^ { h }$ 表示对同一目标粗略检测器和精细检测器的目标检测分数，且 $g _ { k }$ 是对应的目标真实标签。变量 $b _ { 1 }$ 表示所选区域中的像素的总数， $B$ 表示输入图像的像素的总数。式中第一项表示检测精度的提高。第二项表示放大成本。精度和计算之间的平衡由参数 $\lambda _ { 2 }$ 控制。

放大精度增益回归网络（R-Net）基于粗略检测结果预测特定区域上放大的精度增益。R-Net在粗检测和精检测数据对上训练，以便它可以观察它们如何相互关联以学习适当的精度增益关系[7]。

由于SSD在许多计算机视觉应用中的成功，使用SSD 作为基础检测器。两个SSD分别在高分辨率精细图像组成的训练集和低分辨率粗略图像组成的训练集上进行训练，并随后用作黑盒粗略和精细检测器。将两个预先训练好的检测器应用于一组训练图像并获得两组图像检测结果：下采样图像中的低分辨率检测 $\left\{ \left( d _ { i } ^ { l } , p _ { i } ^ { l } , f _ { i } ^ { l } \right) \right\}$ 和在每个图像的高分辨率版本中的高分辨率检测 $\left\{ \left( d _ { j } ^ { h } , p _ { j } ^ { h } \right) \right\}$ 其中 $\mathbf { \nabla } _ { d }$ 是检测边界框， $p$ 是作为目标对象的概率， $f$ 表示相应检测的特征向量。使用上标 $h ( \mathrm { H i g h } )$ 和l(Low)来表示高分辨率和低分辨率（下采样）图像。

为了使模型判别高分辨率检测是否改善了整体检测结果，引入了一个匹配层，将两个检测器产生的检测结果关联起来。在该层中，如果发现下采样图像中的可能对象 $i$ 和高分辨率图像中的可能对象 $j$ 具有足够大的交集 $I o U \left( d _ { i } ^ { l } , d _ { j } ^ { h } \right)$ （ $I o U > 0 . 5 )$ ，则定义 $i$ 和 $j$ 为彼此对应。按照规则对粗检测方案和精检测方案进行匹配，并生成它们之间的一组对应关系[7]。

给定一组对应关系 $\left\{ \left( d _ { k } ^ { l } , p _ { k } ^ { l } , p _ { k } ^ { h } , f _ { k } ^ { l } \right) \right\}$ ，可以估计粗检测的放大精度增益。检测器只能处理一定范围内的对象，因此将检测器应用于高分辨率图像并不总是产生最佳精度。例如，如果检测器主要在小目标数据集上训练，则该检测器对较大目标的检测精度并不高。因此，使用 $\left| g _ { k } - p _ { k } ^ { l } \right| - \left| g _ { k } - p _ { k } ^ { h } \right|$ 来测量哪个检测结果(粗略或精细)更接近事实，其中 $g _ { k } \in \{ 0 , 1 \}$ 作为真实标签的度量。当高分辨率分数 ${ p } _ { k } ^ { h }$ 比低分辨率分数 $p _ { k } ^ { l }$ 更接近基本事实时，该函数表示此目标值得放大；否则，在下采样图像上应用粗略检测器可能产生更高的精度，因此我们应该避免放大该目标。使用相关回归(CR)层来估计目标 $K$ 的放大精度增益

$$
\operatorname* { m i n } _ { W _ { 1 } } \Big ( \big | g _ { k } - p _ { k } ^ { l } \big | - \big | g _ { k } - p _ { k } ^ { h } \big | - \phi \big ( W _ { 1 } , f _ { k } ^ { l } \big ) \Big ) ^ { 2 }
$$

其中： $\varnothing$ 代表回归函数， $W _ { I }$ 代表参数集。该层的输出是估计的准确度增益。CR层包含两个完全连接的层，第一层有4096个单元，第二层只有一个输出单元。

根据每个目标的学习准确性增益可以生成 AG map（accuracygainmap)。假设候选边框内的每个像素对其准确性增益具有同等的贡献。因此，AG map 生成为

$$
A G \big ( x , y \big ) = \left\{ \begin{array} { l r } { \displaystyle \alpha \frac { \phi \big ( \hat { W } , f _ { k } ^ { l } \big ) } { b _ { k } } } & { \displaystyle i f \left( x , y \right) i n d _ { k } ^ { l } } \\ { 0 } & { \it o t h e r w i s e } \end{array} \right.
$$

其中： $( x , y )$ 表示点 $( x , y )$ 在边界框 $d _ { k } ^ { l }$ 内， $b _ { k }$ 表示包含在$d _ { k } ^ { l }$ 中的像素数。 $\alpha$ 是一个常数。W表示CR 层的估计参数。AGmap用作状态表示，它自然包含粗略检测质量的信息。在对区域进行放大和检测后，区域内的所有值均设置为0，以防止未来在同一区域再次进行缩放。放大精度增益回归网络R-net结构图如图2所示

![](images/0453e0230865e2b7d2fddbf7c5b7be0694cd20ea287d6de4ff61dba0eb0837b4.jpg)  
图2R-Net 网络框架

# 1.2放大区域动态选择算法

通过R-net 获得了AG map，AG map 中的每个像素的值是对输入图像中包括那个像素可以提高多少检测精度的估计。所以，AG map 提供了用于选择不同动作的检测精度增益。在采取动作之后，对应于AG映射中所选区域的值相应地减小，因此 AG 映射可以动态地记录动作历史。依据 AG map 提出了一种动态放大区域选择算法，具体算法流程如图3所示。

![](images/db3e318cec97a4ea61e544aef3d24a4aaf16163291c52b04c92836fd54cdc83d.jpg)  
图3动态放大区域选择流程

首先将AGmap按照 $8 \mathrm { x } 8$ 网格划分为等额矩形区域，统计每个矩形中像素值的总和，设定阈值，选择区域中心块，每个区域中心块为中心的3x3个矩形构成放大筛选区域，同一个放大筛选区域类如有多个满足像素值阈值条件的矩形区域，取像素值最大的那个作为区域中心，如果区域中心取在大正方形的边上，通过增补同尺寸空白小正方形的方式构成3x3的放大筛选区域。在放大筛选区域内，以放大筛选区域中心点为中心，按照不同的长宽比，构造4个不同长宽比的预测包围盒，通过比较各个预测包围盒包含区域的构造指标（像素值、比例、面积）选出最佳放大区域包围盒。网格划分后的AGmap中矩形区域内 $r t g _ { i }$ 的总像素值 $s u m p \mathcal { X } i$

$$
s _ { u m p } x _ { i } = \sum _ { j \in r t g _ { i } } p x _ { j }
$$

其中 $p x _ { j }$ 代表 $r t g _ { i }$ 区域内第j个像素点的像素值， $s _ { u m p } x _ { i }$ 值越大，代表矩形区域rtgi的放大收益越大，将高放大收益的区域作为中心符合人眼对区块领域相关性的认识。通过二阶差分法自适应选取像素值阈值，完成区域中心块的初筛选。二阶差分可以表现离散数组的变化趋势大小，可用于在一组像素值中确定阈值。检测一张AGmap 默认得到64 个候选区域，

最后每个候选区域都得到1个用来表示放大收益的总体像素值 $s _ { u m p } x _ { i }$ ，故共可以得到的64x1的数组，舍去其中小于0.1的元素，判为没有目标，得到 $\boldsymbol { n } \times \boldsymbol { 1 }$ 的数组 $c$ 。设估计 $s _ { u m p } x _ { i }$ 由大减小变化趋势的函数为 $f ( g )$ ，见式5

$$
f \left( C _ { k } \right) = \frac { ( C _ { k + 1 } - C _ { k } ) - \left( C _ { k } - C _ { k - 1 } \right) } { C _ { k } } , k = 2 , 3 , \cdots , n - 1
$$

则将 $f ( C _ { k } )$ 取最大值时的 $C _ { k }$ 作为此 AG map 图像的 $s _ { u m p } x _ { i }$ 阈值。

为了减少区域放大精检测的计算量，有效提高算法的效率和实时性，同时又要保证所选区域有较好的包容度，以每个区域中心块为中心的3x3个矩形构成放大筛选区域，同一个放大筛选区域类如果有多个满足像素值阈值条件的矩形区域，取像素值最大的那个作为区域中心。

以放大筛选区域中心点为中心位置，按照不同的长宽比预测6个固定大小的预测包围盒，放大筛选区域的面积为 $S _ { Z }$ 每个预测包围盒的面积如式（6）所示

$$
s _ { k } = s _ { m i n } + \frac { s _ { m a x } - s _ { m i n } } { m - 1 } ( k - 1 ) , k = 1 , 2 , \cdots , 5
$$

其中 $s _ { m i n } { = } 0 . 1 \times S _ { Z }$ ， ${ \ s } _ { m a x } { = } 0 . 7 { \times } S _ { Z }$ ， $\scriptstyle { m = 5 }$ ，对于不同的预测包围盒赋予不同的长宽比：

$$
a _ { r } = \frac { W } { H } , a _ { r } \in \ \left\{ 1 , 2 , 3 , \frac { 1 } { 2 } , \frac { 1 } { 3 } \right\}
$$

W、 $H$ 分别表示包围盒的宽和长。则预测包围盒对应的宽和长分别为 $H _ { k } = \sqrt { \% } a _ { r }$ $W _ { k } = { \sqrt { a _ { r } \bullet s _ { k } } }$ 。

当 $a _ { r } { = } 1$ 时还有一个预测包围盒，规模为 $s _ { k } ^ { ' } = \sqrt { s _ { k } ^ { ' } \bullet s _ { k + 1 } }$ ，即一共有6个预测包围盒。

对于任一个包围盒， $b _ { l }$ ，计算盒内的像素总值 $s _ { u m p } x _ { i }$ 为

$$
s _ { u m p } x ( b _ { l } ) = \sum _ { i \in b _ { l } } p x _ { i } , l = 1 , 2 , 3 , 4
$$

区域面积 $s$ 为

$$
S \left( b _ { l } \right) = W \times L
$$

W、 $H$ 分别表示盒的宽和长。区域内高放大收益像素占比$P$ 为

$$
P \left( b _ { l } \right) = \frac { p n _ { 1 } } { p n _ { 2 } }
$$

$P n _ { I }$ 表示 $b _ { l }$ 区域内，具有放大收益的像素点（即像素值大于0.1的像素点）的总数， $P n _ { I }$ 表示 $b _ { l }$ 区域像素点总数。即每一个预测包围盒， $b _ { l }$ 存在特征向量 $( x , y , s u m p x , W , L , P )$ ， $x , \ y$ 分别

表示 $b _ { l }$ 的中心点横纵坐标。

利用人工标定的训练样本，训练了一个Logistic 分类器[10]对各个预测包围盒的框选效果进行评价。将评价结果分为两类，即能够满足放大要求的预测包围盒和不能满足放大要求的预测包围盒。

对于输入的预测包围盒， $b _ { l } ( x , y , s u m p x , W , L , P )$ ，Logistic 分类器引入权值参数 $\scriptstyle \theta = ( \theta _ { 1 } , \theta _ { 2 } , K , \theta _ { 6 } )$ ，对 $b _ { l }$ 中的属性进行加权，得到 $\theta { T } b _ { l }$ ；引入logistic函数（sigmoid函数）得到函数 $h _ { \theta } ( b _ { l } )$

$$
h _ { \theta } \left( b _ { l } \right) = \frac { 1 } { 1 + e ^ { - \theta ^ { T } b _ { l } } }
$$

即可得到概率估计函数 $P \big ( \boldsymbol { y } \mid b _ { l } ; \theta \big )$

$$
P \left( y \mid b _ { l } ; \theta \right) = \left\{ { h _ { \theta } } \left( b _ { l } \right) ; y = 1 \atop 1 - { h _ { \theta } } \left( b _ { l } \right) ; y = 0  \right.
$$

它的含义就是在给定测试样本 $b _ { l }$ 与参数 $\theta$ 时，标签为 $y$ 的概率。

由测试样本集合与训练样本集合，我们可以得到它们的联合概率密度即似然函数：

$$
\prod _ { i = 1 } ^ { n } P \big ( y ^ { ( i ) } \mid b _ { l } ^ { ( i ) } ; \theta \big ) = \prod _ { i = 1 } ^ { n } \big ( h _ { \theta } \big ( b _ { l } \big ) \big ) ^ { y ( i ) } \big ( 1 - h _ { \theta } \big ( b _ { l } \big ) \big ) ^ { 1 - y ( i ) }
$$

最大化似然函数，求出合适的参数 $\theta _ { \circ }$ 将式13变形为

$$
\ell \left( \theta \right) = \sum _ { i = 1 } ^ { m } y ^ { ( i ) } \log h _ { \theta } \left( b _ { l } \right) + \left( 1 - y ^ { ( i ) } \right) \log \left( 1 - h _ { \theta } \left( b _ { l } \right) \right)
$$

依据公式，由梯度下降法求取参数 $\theta _ { \circ }$ 先对参数 $\theta$ 求导

$$
\frac { \hat { \partial } } { \hat { \partial } \theta _ { j } } \ell \bigl ( \theta \bigr ) = \bigl ( y - h _ { \theta } \bigl ( b _ { l } \bigr ) \bigr ) b _ { l j }
$$

更新法则

$$
\theta _ { j } : = \theta _ { j } + \alpha \Big ( \Big ( y ^ { ( i ) } - h _ { \theta } \left( b _ { l } ^ { ( i ) } \right) \Big ) b _ { l j } ^ { ~ ( i ) } \Big )
$$

通过Logistic分类器对各个预测包围盒的框选效果进行评价后，对于每一个预测包围盒我们都能够获得一个对应的框选评价分数，之后，进行一个非极大值抑制得到最终的预测作为最终的放大包围盒。

在完成放大包围盒的选取后我们将放大筛选区域内的像素值全部设为0，避免重复选取造成的效率低下，同时对 AG map进行对应区域的更新，并检测AGmap上是否已经对所有高放大收益区域进行检测（AGmap 像素总值是否为0)，若果是则完成检测，否的话继续迭代进行检测过程。

把所得放大精检测候选区域的原图部分送到精细检测器检测之前，先进行双线性插值放大，放大至精细检测器检测候选区域的最小尺寸（本文设置的候选区域最小为 $1 0 \times 1 0$ ）。

# 2 置信度自适应阈值改进

在SSD用Softmax为候选区域进行分类的最后阶段，候选区域会得到属于各个类别的置信度（即属于各个类别的概率)，当属于某类的置信度高于设定阈值时则将此候选区域判为该类目标，若同一候选区域有多个类别置信度高于阈值则取最高者。

目标尺度较小或被遮挡时置信度相对较低。若采用固定阈值，设置过高会排除许多真目标，过低会混入许多假目标。通常的做法是不断调整阈值对数据集进行多次测试，计算出不同阈值下的平均准确率，取平均准确率最大的阈值作为模型最终的阈值。但这种做法有适应数据集的倾向，再庞大的数据集也无法涵盖现实中的所有情况。本文采用自适应阈值在避免适应数据集的同时提高模型的决策能力[1]。

无论固定或自适应，阈值的设定都需要参考数据集中目标得分情况。检测模型训练较好的情况下，正确的检测结果中真目标和假目标置信度常常相差一两个数量级，且真目标置信度通常在0.7以上。虽然与真目标的置信度存在差距，但假目标也会因为某些特征与目标类似而取得0.7以上的高置信度，单纯采用固定阈值无法将目标与背景区分开[II]。针对 SSD 检测固定置信度阈值不够灵活的缺陷，采用模糊自适应阈值法[12]调整自适应阈值策略降低漏警率和虚警率。

模糊程度是由模糊率函数来确定，当模糊率最低的时候，这时候分割效果最好。其中模糊率与隶属函数相关，模糊数学的基本思想是隶属度的思想。应用模糊数学方法建立数学模型的关键是建立符合实际的隶属函数[12]。

检测一张图像默认得到 $N$ 个候选区域送入SSD，最后每个候选区域都得到 $M$ 个用来表示属于 $M$ 个类别的置信度，故共可以得到的 $N$ 个 $M \times I$ 的数组。取出每个数组中的最大值并由大到小排序，舍去其中小于0.1的值(若 $N$ 个值全部小于0.1 则判为没有目标)，得到 $N { \times } I$ 的数组 $c$ 。 $\mu ( x )$ 是隶属度函数， $\mu ( C _ { k } )$ 为数组 $c$ 中置信度取Ck 的区域的隶属度。数组C 的模糊率 $\gamma ( C )$ 是对数组 $c$ 的模糊性度量，令 $h \big ( C _ { k } \big )$ 为数组C中置信度取 $\mathrm { C k }$ 的元素个数，则数组 $c$ 的模糊率 $\gamma ( C )$ 定义如式17

$$
\gamma ( C ) = \frac { 2 } { n } \sum _ { k = 0 } ^ { n - 1 } T \left( C _ { k } \right) h \left( C _ { k } \right)
$$

其中 $T \big ( C _ { k } \big ) = \operatorname* { m i n } \big \{ \mu \big ( C _ { k } \big ) , 1 - \mu \big ( C _ { k } \big ) \big \}$ ：

数组 $c$ 的模糊率 $\gamma ( C )$ 取决于隶属度函数 $\mu ( x )$ ，若取隶属度函数为 $s$ 函数，即

$$
\mu ( x ) = \left\{ \begin{array} { l l } { 0 , } & { 0 \leq x \leq q - \Delta q } \\ { \quad } \\ { \quad } \\ { \left( \displaystyle { \frac { { x - q + \Delta q } } { 2 \Delta q } } \right) ^ { 2 } , } & { q - \Delta q \leq x \leq q } \\ { \quad } \\ { \displaystyle { 1 - 2 \left[ \frac { \left( x - q + \Delta q \right) } { 2 \Delta q } \right] ^ { 2 } } , } & { q < x \leq q + \Delta q } \\ { 1 , } & { q + \Delta q < x \leq C _ { n } } \end{array} \right.
$$

则此时 $\mu ( x )$ 由窗宽 $c = 2 \Delta q$ 及参数 $q$ 决定，一旦选定了窗宽，则 $\gamma ( C )$ 就只与参数 $q$ 有关。模糊阈值法的求解过程是预先设定窗宽，根据论文前人的研究，系数常设定为0.3。通过改变 $q$ 使得隶属度函数 $\mu ( x )$ 在置信度区间 $\left[ C _ { 0 } , C _ { n - 1 } \right]$ 上滑动，通过计算模糊率 $\gamma _ { \boldsymbol { q } } ( C )$ 获得模糊率曲线，该曲线的谷点，即使$\gamma _ { \boldsymbol { q } } ( C )$ 取得极小值的 $\boldsymbol { q }$ ，也就是所求的自适应阈值。

![](images/242712af74461f285b07badfd646eef4c6107909118bbe87c133c1c8a7b4504a.jpg)  
改进后整体的检测算法框架流程如图4所示  
图4改进后算法整体框架

算法流程如下：a)输入待检测视频单帧图像，将图像进行下采样获得低分辨率版本，降低运算量；b)通过DRZN对需要在高分辨率下检测识别的目标区域进行顺序选择放大，精细检测器进行目标检测识别，获得结果 $R _ { 1 }$ ，已经检测过的区域在原低分辨率图像中像素值全取为0；c)将剩余低分辨率图像输入粗略检测器进行目标检测识别，获得结果 $R _ { 2 }$ ；d)将 $R _ { 1 }$ 和 $R _ { 2 }$ 检测结果进行融合，得到最终结果 $R _ { 3 }$ 。

# 3 实验结果与分析

# 3.1实验的基础条件与数据集库

本文实验使用DELLPrecision R7910(AWR7910）图形工作站，处理器为 Intel Xeon E5-2603 v2(1.8 GHz/10M)，采用NVIDIAQuadroK620GPU加速运算。SSD是基于深度学习框架Caffe来运行的。Caffe支持CPU和GPU的并行运算，使得计算量庞大的深度学习得以在短期内完成。

本文在 YFCC100M 收集的交通场景数据集(Web dataset）和 KITTI数据集上进行了实验。选用KITTI数据集中第1个图片集“Download left color images of object data set”和标注文件“Download training labels of object data set",其中 7 481 张训练图片有标注信息，而测试图片没有。SSD中训练脚本是基于VOC 数据集格式的，需要把KITTI数据集做成PascalVOC的格式。PascalVOC 数据集总共20个类别，本文为数据集设置3个类别‘Car’，‘Cyclist’，‘Pedestrian’，因为标注信息中还有其他类型的车和人，本文将‘Van’‘Truck’‘Tram’合并到‘Car’类别中去，将‘Person_sittng’合并到‘Pedestrian'类别中去，‘Misc’和‘Dontcare’这两类直接忽略。在测试集中选出100 张含低分辨率小目标（本文设定小目标尺寸小于 $1 0 \times 1 0$ 的图像)，构成KITTI数据集的低分辨率小目标测试集。

YFCC100M数据集包含将近1亿张图片以及摘要、标题和标签。为了更好地展示本文方法，从YFCC100M数据集收集了1000幅分辨率较高的测试图像。通过搜索关键词“行人”“道路”和“车辆”来收集图像。对于该数据集，使用至少16像素宽度和小于 $50 \%$ 遮挡对所有目标进行注释。图像在较长的一侧被重新缩放到 2000 像素，以适合GPU内存。在测试集中选出100张含低分辨率小目标（本文设定小目标尺寸小于10$\times 1 0$ 的图像)，构成WD数据集的低分辨率小目标测试集。实验中将所有的图像尺寸归一化为 $3 2 0 \times 3 2 0$ 。

# 3.2 实验的参数设置

本文选择 SSD系列中的SSD512进行改进，SSD512提供了大、中、小三个规模的深度卷积神经网络模型，本文选取中等规模的VGG_CNN_M_1024模型作为基础模型，改动与目标类别数目相关的参数（原模型需要识别20类目标而本文只有3类)。小样本数据集在一定的程度上可以代表原始数据集，通过小样本数据集训练所得的最优超参数在一定的程度上能够适应原始数据集[13]。通过小样本调参，在不使用自适应阈值时，阈值设置为0.1（默认设置为0.7)；将所有实验中经过非极大抑制留下的候选区域数量设置为100（默认设置为300)。其他设置保持默认不变，后续所有实验都在以上设置基础上进行。

# 3.3评价指标

在多目标分类器的判别中，设目标的种类数为n。对单种目标的判别仍然遵循每一种假设有两种结果的四种可能性，即

设 $D _ { i } ^ { j } \left( j = 1 , 2 , \cdots , n \right)$ 表示一种目标j选择假设 $H _ { i } ^ { j }$ 为真，任何二元假设实验问题中，作判别时要考虑4种可能性[14]:

a) $H _ { 0 } ^ { j }$ 假设为真，判别为 $D _ { 0 } ^ { j }$ ;b) $H _ { 0 } ^ { j }$ 假设为真，判别为 $D _ { 1 } ^ { j }$ ：

c） $\boldsymbol { H } _ { 1 } ^ { j }$ 假设为真，判别为 $D _ { 0 } ^ { j }$ ；d） $\boldsymbol { H } _ { 1 } ^ { j }$ 假设为真，判别为 $D _ { 1 } ^ { j }$ 。

a）和d）对目标j选择正确；b）称为第一类错误，叫做虚警（没有目标而识别为有目标)；c）称为第二类错误，叫做漏报（有目标而误判为没有目标)。除此之外，在多目标识别中将目标 $D _ { i } ^ { j }$ 识别为目标 $D _ { i } ^ { k } \left( k = 1 , 2 , \cdots , n , k \neq j \right)$ 的错误判别。

设目标 $Z ^ { j }$ 在判别域 $Z _ { 0 } ^ { j }$ 和 $Z _ { 1 } ^ { j }$ 上的概率密度函数分别为$f \left( z \middle | H _ { 0 } \right)$ 和 $f \left( z ^ { j } \left| H _ { 1 } ^ { j } \right. \right)$ ，则有

虚警率: $P _ { f } = \sum _ { j = 1 } ^ { n } P \Big ( D _ { 1 } ^ { j } \Big | H _ { 0 } ^ { j } \Big ) = \sum _ { j = 1 } ^ { n } \intop _ { Z _ { 1 } ^ { j } } f \Big ( z ^ { j } \Big | H _ { 0 } ^ { j } \Big ) d z$ 漏警率: $P _ { m } = \sum _ { j = 1 } ^ { n } P \Big ( D _ { 0 } ^ { j } \left| H _ { 1 } ^ { j } \right. \Big ) = \sum _ { j = 1 } ^ { n } \intop _ { Z _ { 0 } ^ { j } } f \left( z ^ { j } \left| H _ { 1 } ^ { j } \right. \right) d z$ 检测率: $P _ { d } = \sum _ { j = 1 } ^ { n } { P \Big ( } D _ { 1 } ^ { j } \left| H _ { 1 } ^ { j } \right. \Big ) = \sum _ { j = 1 } ^ { n } \int { f \left( { z } ^ { j } \left| H _ { 1 } ^ { j } \right. \right) } d z$ 误检率: $P _ { e } = \sum _ { j = 1 } ^ { n } \sum _ { k = 1 , j \neq k } ^ { n } P \Big ( D _ { 1 } ^ { j } \Big | H _ { 1 } ^ { j } \Big ) = \sum _ { j = 1 } ^ { n } \sum _ { k = 1 , j \neq k } ^ { n } \int _ { { \cal Z } _ { 1 } ^ { k } } f \Big ( { \cal Z } ^ { j } \Big | H _ { 1 } ^ { j } \Big ) d { \cal Z }$

目标分类中，关心的是存在的目标的识别效果，识别率一般指检测率。根据定义可知，虚警率、检测率、漏警率与误检率之和为1。在实际计算时，首先计算识别率，再计算误报率、漏报率，对于剩余系统识别出来的而实际不存在的目标种类作计数来计算分类的虚警率。对于多目标识别中的虚警率应该计算一定时间段内积累的虚警率。对于数据集，我们采用求平均的方式来计算整体的虚警率、漏警率、检测率、误检率。

深度学习通过误差的反向传播来调整神经网络权值，达到建模的目的。反向传播迭代次数从几万次逐步增加到数十万次，直到训练误差趋于收敛为止。最后通过计算模型在测试集上的平均准确率（average precision， $A P$ ）和所有类别的平均准确率均值（meanAP，mAP）来评价模型的好坏。 $A P$ 从召回率和准确率两个角度衡量检测算法的准确性。 $A P$ 是评价深度检测模型准确性最直观的标准，可以用来分析单个类别的检测效果。mAP是各个类别 $A P$ 的平均值， $m A P$ 越高表示模型在全部类别中检测的综合性能越高[1I]。

# 3.4实验设计

首先将各个策略与SSD512进行单独结合进行相应的对比实验，表明各个策略的作用；然后将所有策略与SSD512结合，对最终的改进算法进行整体测评。

用训练集训练原始 SSD512，将此模型记为M0，在 M0 基础上加入自适应阈值策略，生成模型M1；在M0 基础上加入动态局部区域放大策略，生成模型M2；最后将M0与所有策略结合在一起，生成模型M3。使用两数据库测试集对 M0,M1，M3进行测试和对比。为突出低分辨率小目标检测效果，使用构造的小目标测试集分别对M0和M2进行测试和对比。

另外本文选取了FasterR-CNN、不需要预训练模型的DSOD30o[15]（deeply supervised object detector）检测框架[26]和YOLO 系列检测框架中的升级版YOLOv2 544[16]，以及 SSD的改进模型 DSSD[17]（deconvolutional single shot detector）作为深度学习对比算法，与M3对比WebDataset 和KITTI数据集上的检测效果。对比检测框架算法使用作者发布的官方代码中的默认参数设置，与M3在相同训练集中进行训练。利用Web

Dataset和KITTI数据集中的测试集进行测试。

# 3.5 实验结果

实验结果见表1、2，分别对比了模型M0、M1、M3在KITTI和WD数据集上普通测试集的识别与检测效果。

表1各模型识别精度对比  

<html><body><table><tr><td rowspan="2">model</td><td rowspan="2">dataset</td><td colspan="3">AP(%)</td><td rowspan="2">mAP(%)</td></tr><tr><td>Person</td><td>Car</td><td>Cyclist</td></tr><tr><td rowspan="2">M0</td><td>KITTI</td><td>73.36</td><td>71.53</td><td>65.32</td><td>70.07</td></tr><tr><td>WD</td><td>71.59</td><td>69.63</td><td>62.75</td><td>67.99</td></tr><tr><td rowspan="2">M1</td><td>KITTI</td><td>77.18</td><td>72.35</td><td>68.69</td><td>72.74</td></tr><tr><td>WD</td><td>73.52</td><td>70.45</td><td>64.83</td><td>69.61</td></tr><tr><td rowspan="2">M3</td><td>KITTI</td><td>87.42</td><td>86.73</td><td>84.38</td><td>86.18</td></tr><tr><td>WD</td><td>82.92</td><td>76.34</td><td>72.63</td><td>77.31</td></tr></table></body></html>

表2各模型检测效果对比  

<html><body><table><tr><td>model</td><td>dataset</td><td>Pf(%)</td><td>Pm (%)</td><td>Pd (%)</td><td>Pe (%)</td></tr><tr><td rowspan="2">M0</td><td>KITTI</td><td>20.21</td><td>19.34</td><td>41.32</td><td>19.13</td></tr><tr><td>WD</td><td>19.25</td><td>21.38</td><td>38.83</td><td>20.54</td></tr><tr><td rowspan="2">M1</td><td>KITTI</td><td>12.31</td><td>13.29</td><td>57.84</td><td>16.56</td></tr><tr><td>WD</td><td>15.17</td><td>14.49</td><td>52.45</td><td>17.89</td></tr><tr><td rowspan="2">M3</td><td>KITTI</td><td>6.33</td><td>8.69</td><td>73.45</td><td>11.53</td></tr><tr><td>WD</td><td>9.24</td><td>10.19</td><td>70.16</td><td>10.41</td></tr></table></body></html>

对比表1、2中M0 和M3 测结果，在KITTI数据集中，各类目标检测的 $A P$ 提高了 $14 \%$ 不等， $m A P$ 提高了约$1 6 . 1 1 \%$ ，虚警率降低 $1 3 . 8 8 \%$ ，检测率提高 $3 2 . 1 3 \%$ ，漏警率降低 $1 0 . 6 5 \%$ ，误检率降低 $7 . 6 \%$ ；在WD数据集中，各类目标检测的 $A P$ 提高了 $7 \%$ 不等， $m A P$ 提高了约 $7 . 2 4 \%$ ，虚警率降低 $1 0 . 0 1 \%$ ，检测率提高 $3 1 . 3 3 \%$ ，漏警率降低 $1 1 . 1 9 \%$ ，误检率降低 $1 0 . 1 3 \%$ 。各项指标提升明显，表明本文策略总体对于弥补 SSD512缺陷的有效性。

对比表1、2中M0和M1检测结果，在KITTI数据集中，各类目标检测的 $A P$ 提高了 $1 { \sim } 4 \%$ 不等， $m A P$ 提高了约$2 . 6 7 \%$ ，虚警率降低 $7 . 9 0 \%$ ，检测率提高 $1 6 . 5 2 \%$ ，漏警率降低$6 . 0 5 \%$ ，误检率降低 $2 . 5 7 \%$ ；在WD数据集中，各类目标检测的 $A P$ 提高了 $1 { \sim } 3 \%$ 不等， $m A P$ 提高了约 $1 . 6 2 \%$ ，虚警率降低 $4 . 0 8 \%$ ，检测率提高 $1 3 . 6 2 \%$ ，漏警率降低 $6 . 8 9 \%$ ，误检率降低 $2 . 6 5 \%$ 。M1模型是在M0 基础上加入自适应阈值策略训练得到的，通过在两个数据库上的测试结果与M0对比我们可以发现，M1相较于M0，对多目标的检测率得到了较大提高，多目标检测的虚警率和漏警率降低明显，表明自适应阈值策略发挥了区分低置信度真目标和高置信度假目标的作用，能够有效降低SSD512对多目标检测的漏警率和虚警率。

表3、4对比了模型M0、M2在KITTI和WD数据集上低分辨率小目标测试集的检测效果。

表3M0和M2模型低分辨率小目标识别精度  

<html><body><table><tr><td rowspan="2">model</td><td rowspan="2">dataset</td><td colspan="3">AP(%)</td><td rowspan="2">mAP(%)</td></tr><tr><td>Person</td><td>Car</td><td>Cyclist</td></tr><tr><td rowspan="2">M0</td><td>KITTI</td><td>13.63</td><td>19.38</td><td>9.73</td><td>14.25</td></tr><tr><td>WD</td><td>8.59</td><td>16.33</td><td>8.53</td><td>11.15</td></tr><tr><td rowspan="2">M2</td><td>KITTI</td><td>77.45</td><td>80.19</td><td>58.68</td><td>72.11</td></tr><tr><td>WD</td><td>65.62</td><td>70.49</td><td>52.37</td><td>62.83</td></tr><tr><td>M0 和M2模型低分辨率小目标检测效果</td><td>表4</td><td></td><td></td><td></td><td></td></tr><tr><td>model</td><td>dataset</td><td>Pf(%)</td><td>Pm(%)</td><td>Pd (%)</td><td>Pe (%)</td></tr><tr><td rowspan="2">M0</td><td>KITTI</td><td>14.25</td><td>33.12</td><td>29.43</td><td>10.14</td></tr><tr><td>WD</td><td>11.15</td><td>34.15</td><td>30.48</td><td>6.45</td></tr><tr><td rowspan="2">M2</td><td>KITTI</td><td>10.82</td><td>10.17</td><td>60.48</td><td>18.53</td></tr><tr><td>WD</td><td>11.91</td><td>14.85</td><td>52.03</td><td>21.21</td></tr></table></body></html>

对比表3、4中M0和M2检测结果，在KITTI数据集中，各类目标检测的 $A P$ 提高了 $49 \%$ 不等， $m A P$ 提高了约$5 7 . 8 6 \%$ ，虚警率降低 $2 2 . 3 \%$ ，检测率提高 $5 0 . 3 4 \%$ ，漏警率降低$1 9 . 2 6 \%$ ，误检率降低 $8 . 7 8 \%$ ；在WD数据集中，各类目标检测的 $A P$ 提高了 $44 \sim 5 7 \%$ 不等， $m A P$ 提高了约 $5 1 . 6 8 \%$ ，虚警率降低 $2 2 . 2 4 \%$ ，检测率提高 $4 5 . 5 8 \%$ ，漏警率降低 $1 5 . 6 3 \%$ ，误检率降低 $6 . 7 1 \%$ 。M2 模型是在M0 基础上加入加入动态局部区域放大策略训练得到的，通过在两个数据库上低分辨率小目标测试集的测试结果对比我们可以发现，M2相较于M0，对多目标低分辨率小目标的识别精度和检测率得到了较大提高，检测的误检率、虚警率、漏警率降低明显，表明动态局部区域放大策略对低分辨率小目标检测和识别的有效性。由于低分辨率弱小目标类别难以判定，M2的错误检测多为分类错误造成的即误检率高，而M0多目标检测率极低，表明了SSD512深度卷积网络逐层抽取特征的同时导致低分辨率弱小目标信息丢失严重。

图5验证了M3模型中R-Net增益效果评估的有效性。第一行蓝色字体数字指示红色框是目标的置信度。c表示粗检测器检测结果，F表示精检测检测器检测结果。红色字体表示R-net的精度增益。正值和负值标准化为[0,1]和[-1,0)。通过对比可以发现对于粗略检测足够好或者优于精细检测的区域，R-net给出较低的精度增益分数（第1列和第2列)，并且对于精细检测比粗略检测好得多的区域(第3列)，R-net给出较高的精度增益分数。

利用WebDataset 和KITTI数据集中的普通测试集进行测试。检测识别效果如表5所示，其中 $F P S$ 代表算法运行的速度，帧率。

对比表5中M3和其他深度学习对比算法检测结果，在KITTI数据集中，各类目标识别的 $A P$ 提高了 $4 \%$ 不等，mAP提高了约 $9 \%$ 不等，检测率提高 $1 3 \small { \sim } 2 8 \%$ ；在WD数据集中，各类目标识别的 $A P$ 提高了 $5 \%$ 不等， $m A P$ 提高了约 $4 { \sim } 9 \%$ 不等，检测率提高 $10 \sim 3 4 \%$ 。虽然检测识别速率比不上

DSOD300、DSSD513、YOLOv2544等检测算法，但是FPS也能达到38帧/s，能够满足实时性的要求。

![](images/2042ff9acc43c7318abbbe66ad496839b501a0153442dbc07e5eb6555777d5a9.jpg)  
图5R-Net放大精度增益效果

表5各检测算法检测识别效果对比  

<html><body><table><tr><td rowspan="2">method</td><td rowspan="2">dataset</td><td colspan="2">AP(%)</td><td rowspan="2">mAP(%)</td><td rowspan="2">Pd (%)</td><td rowspan="2">FPS</td></tr><tr><td>person</td><td>car cyclist</td></tr><tr><td rowspan="2">Faster R-CNN</td><td>KITTI</td><td>83.26</td><td>74.13</td><td>75.42 77.61</td><td>45.22</td><td>13.15</td></tr><tr><td>WD</td><td>81.49</td><td>71.33</td><td>68.65 73.82</td><td>36.63</td><td>11.64</td></tr><tr><td rowspan="2">DSOD300</td><td>KITTI</td><td>77.43</td><td>72.26</td><td>68.38 72.69</td><td>58.68</td><td>58.23</td></tr><tr><td>WD</td><td>70.73</td><td>69.39</td><td>67.04 69.05</td><td>52.32</td><td>50.35</td></tr><tr><td rowspan="2">DSSD513</td><td>KITTI</td><td>75.46</td><td>69.53</td><td>68.34 71.11</td><td>59.42</td><td>46.34</td></tr><tr><td>WD</td><td>72.19</td><td>68.83</td><td>66.45 69.16</td><td>49.79</td><td>39.38</td></tr><tr><td rowspan="2">YOLOv2 544</td><td>KITTI</td><td>79.43</td><td>71.25</td><td>67.32</td><td>72.66 60.82</td><td>56.74</td></tr><tr><td>WD</td><td>73.29</td><td>69.63</td><td>68.85 70.59</td><td>54.86</td><td>49.28</td></tr><tr><td rowspan="2">M3</td><td>KITTI</td><td>87.42</td><td>86.73</td><td>84.38</td><td>86.18 73.45</td><td>37.56</td></tr><tr><td>WD</td><td>82.92</td><td>76.34</td><td>72.63</td><td>77.31 70.16</td><td>32.83</td></tr></table></body></html>

# 4 结束语

针对现有基于大数据和深度学习的目标检测框架对于高分辨率复杂大场景中低分辨率小目标识别效果较差，多目标检测的精度和实时性难以平衡的问题，改进了基于深度学习的目标检测框架SSD，提出一种改进的多目标检测框架DRZ-SSD，将其专用于复杂大交通场景多目标检测。经过实验验证，改进策略有效弥补了传统SSD的缺陷，在应对弱小目标、多目标、杂乱背景、遮挡等检测难度较大的情况时，均能获得较好的效果，实现了算法精度与运行速率的平衡。由于卷积神经网络的结构不适合处理时序信息，结合递归神经网络[21]（一类具有记忆功能的神经网络）来解决视频目标检测和跟踪问题，将是下一步工作的重点。

# 参考文献：

[1]迟晓君，孟庆春，陈鹏.基于最小风险的Bayes 决策方法在交通检测中的应用[J].计算机应用研究，2005，22(12):204-205.(Chi Xiaojun,

Meng Qingchun,Chen Peng.Application of Bayesian decision-making method based on minimum risk in trafc detection [J].Application Research of Computers,2005,22(12): 204-205.)   
[2]于凯，贾磊，陈宇强．深度学习的昨天，今天和明天[J].计算机研究 与发展，2013,50(9):1799-1804.(Yu Kai,Jia Lei,Chen Yuqiang. Yesterday, Today and Tomorrow of Deep Learning [J]. Computer Research and Development,2013,50 (9): 1799-1804.)   
[3]Liu Wei,et al. SSD: Single Shot MultiBox Detector [Cl//Proc of European Conference on Computer Vision. Cham: Springer,2O16: 21-37.   
[4]Ren Shaoqing,et al. Faster R-CNN: towards real-time object detection with region proposal networks [J]. IEEE Trans on Pattern Analysis& Machine Intelligence, 2017,39 (6): 1137-1149.   
[5]Joseph R,,et al.You only look once:unified,real-time object detection [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2016: 779-788.   
[6]Lin Tsuang Yi,et al.Feature Pyramid Networks for Object Detection [J]. arXiv preprint arXiv: 1612.03144,2016.   
[7]Gao Mingfei,et al. Dynamic Zoom-in Network for Fast Object Detection in Large Images [J].arXiv preprint arXiv: 1711.05187,2017.   
[8]Glen Berseth, Cheng Xie,et al. Progressive Reinforcement Learning with Distillation for Multi-Skilled Motion Control[J].arXiv preprint arXiv: 1802. 04765,2018.   
[9] 陈前斌，何小强，吴攀，等．基于部分可测马尔科夫决策过程业务感知 的微基站休眠时长确定策略[J].电子与信息学报，2018，40(1): 130-136.(Chen Qianbin,He Xiaoqiang,Wu Pan,et al.A strategy for determining the sleep duration of micro base stations based on service awareness in partially measurable Markov decision processes [J]. Journal of Electronics and Information Technology,2018,40(1):130-136. )   
[10]赵鹏，李大寨，王韬．基于Logistic 回归的零件图像区域提取[J].计算 机应用研究,2017,34(4):1265-1268.(Zhao Peng,LiDazhai,WangWei. Part Image Region Extraction Based on Logistic Regression [J]. Application Research of Computers,2017,34(4):1265-1268.)   
[11]冯小雨，梅卫，胡大帅．基于改进 Faster R-CNN 的空中目标检测[J]. 光学学报,2018,38(6):1-16.(Feng Xiaoyu,Mei Wei,Hu Dashuai.Aerial target detection based on improved faster R-CNN[J].Acta Optica Sinica, 2018, 38 (6): 1-16.)   
[12]陈果，左洪福．图像的自适应模糊阈值分割法[J]．自动化学报，2003, 29 (5):791-796.(Chen Guo,Zuo Hongfu.Adaptive fuzzy threshold segmentation method for images [J]. Acta Automatica Sinica,2003,29 (5): 791-796. )   
[13]胡聪，屈瑾瑾，许川佩，等．基于自适应池化的神经网络的服装图像识 别[J//OL].计算机应用,2018,1-8.(Hu Cong,Qu Wei,Xu Chuanpei, Zhu Aijun. Apparel image recognition based on adaptive pooling neural network [J//OL]. Computer application,2018,1-8.)   
[14]马春庭，郑坚，陈东根，等．地面战场侦察系统多目标识别的评价指标 [J]．探测与控制学报,2006,28(1): 6-9.(Ma Chunting,Zheng Jian,Chen Donggen,et al.Evaluation index of multi-target recognition for ground batlefieldreconnaissancesystem[J].Jouralofetection &Control,006, 28 (1): 6-9. )   
[15] Shen Zhiqiang,et al. DSOD: learning deeply supervised object detectors from scratch [C]// Proc of IEEE International Conference on Computer Vision. Washington DC: IEEE Computer Society,2017: 1937-1945.   
[16] Zhang Jianming,et al. A real-time Chinese traffic sign detection algorithm based on modified YOLOv2[J].Algorithms,2017,10 (4): 127.   
[17]Fu Chengyang,Liu Wei, Ranga A et al. DSSD: deconvolutional single shot detector [J].arXiv preprint arXiv: 1705.09587,2017.   
[18]周飞燕，金林鹏，董军．卷积神经网络研究综述[J].计算机学报，2017, 40 (6):1229-1251.(Zhou Feiyan,Jin Linpeng,Dong Jun.A review of convolutional neural networks [J]. Chinese Journal of Computers,2017,40 (6): 1229-1251. )   
[19]常亮，邓小明，周明全，等．图像理解中的卷积神经网络[J]．自动化 学报，2016,42(9):1300-1312.(Chang Liang,Deng Xiaoming，Zhou Mingquan,et al. Convolutional neural networks in image comprehension [J].Acta Automatica Sinica,2016,42 (9): 1300-1312.)   
[20] Tang Pengjie,Wang Hanli,Kwong S.G-MS2F:GoogLeNet based multi-stage feature fusion of deep CNN for scene recognition [J]. Neurocomputing,2017,225 (2): 188-197.   
[21] Munaro Matteo,et al. OpenPTrack: Open source multi-camera calibration andpeople tracking for RGB-D camera networks [J]. Robotics& Autonomous Systems,2016,75: 525-538.