# 基于HRV分析的可穿戴心电仪精神疲劳检测

黄诗童，张威强，张朋柱(上海交通大学 安泰经济与管理学院，上海 200030)

摘要：精神疲劳是许多慢性疾病如心血管疾病、糖尿病和癌症的关键原因，然而又难以量化评估及测量，提出了一种通过智能穿戴设备检测脑力劳动者疲劳程度的工程可行性的方案。为了检测脑力疲劳程度，通过Man-WhitmeyU检验评估了HRV各项指标在判断精神疲劳状态的统计显著性，并使用随机森林进行特征选择以确定HRV各项指标的重要性；研究发现，最重要的HRV 指标分别是NN。mean，PNN50、VLF、LF和TP。最后采用 SVM、Naive Bayes、KNN和逻辑回归四种机器学习算法对进行疲劳状态进行识别，实验证明了KNN分类器最为有效，其交叉验证准确率为 $7 5 . 5 \%$ 和AUC为0.74。

关键词：精神疲劳检测；HRV；曼-惠特尼检验；随机森林；机器学习 中图分类号：TP399 doi: 10.3969/j.issn.1001-3695.2018.05.0262

# Detection of mental fatigue with wearable ECG devices based on HRV analysis

Shitong Huang, Weiqiang Zhang, Pengzhu Zhang (AntaiCollegeofEconomics&Management,Shanghai Jiao Tong University,Shanghai 2Oo030,China)

Abstract: Mental fatigueisakeycauseof manychronic diseases suchas CVD,diabetes andcancer.It isillusive and hard to measure ordetect.This research proposes afeasible acurateand cost saving method to detect fatigue level of mental workers via smart wearable devices.Inorder todetect mentalfatigue level,this paper firstly extracted HRV features,thenused ManWhitney U Test to evaluate the statistical significances of HRV features between Normal and Fatigue state.This paper used Random Forest forfeature selection to determine the importance of HRV features.The most important HRV features are NN. mean,PNN5o,VLF,LFand TPrespectively.This paper then took four machine learning algorithms on selected features to predict the state of mental fatigue.The experiments demonstrated the effectiveness of KNN classifier with $7 5 . 5 \%$ accuracy rate on cross validation and 0.74 AUC.

Key Words: mental fatigue detection; HRV; Man-Whitney U test; random forest; machine learning

# 0 引言

精神疲劳是人体疲倦的主观感受，大多数精神疲劳的定义主要集中在脑力功能表现方面[l\~3]。Grandjean 将精神疲劳描述为一种损害大脑机能的低警觉状态[1]。Staals 将精神疲劳描述为一种由于细胞容量不足而无法保持原有的警觉性的中枢神经系统状态[2]。在本文的定义中，精神疲劳是指由认知活动时间过久而导致的大脑最大认知能力暂时性降低状态，外在表现为嗜睡、昏睡或注意力减弱。国内外医学理论研究表明，过度疲劳已经成为突发性致命疾病的主要原因，并且有研究表明，中风与过劳死都与过度工作导致的精神疲劳有很强的关系[4]，高强度的工作会增加心血管疾病的发生概率[5]。除了对生理健康的损害之外，精神疲劳还对记忆力，判断力，决策能力和情绪管理有着诸多影响[2]，长期的超额工作会导致压力和紧张，并进一步导致更高的事故发生率和旷工率以及更低的生产效率[67]。

目前全球超过四分之一的脑力工作者具有面临过度劳累的风险。过度劳累导致的精神疲劳会引起睡眠质量降低、压力和焦虑等一系列症状，并间接导致心脑血管疾病、糖尿病和癌症等一系列慢病疾病风险。因此使用智能可穿戴设备，利用生理指标来检测脑力工作者的疲劳程度并防止疲劳程度进一步恶化是非常有意义的。

尽管研究精神疲劳对于脑力工作者的身心健康具有重要意义，然而精神疲劳在实际生活中难以度量。现目前，国内外精神疲劳量化方法主要分为四大类：主观量表法、客观实验法、观察法和生理指标测量法。主观量表法要求被试通过问卷调查来评估他们的精神疲劳程度，相关的量表如斯坦福嗜睡量表（SSS)，查尔德疲劳量表（CFS）和疲劳严重程度量表（FSS）等。主观量表法虽然简单高效，但由于受众自身的医学水平参差不齐，导致主观量表的客观准确度相对较低，但可以作为后续方法的参照。客观实验量化方法设计一些意识任务来评估被测试者的大脑机能表现。有些任务测量被测试者的反应时间、记忆力和决策力，如异常警觉的任务（PVT）[8]，多重睡眠潜伏期试验（MSLT）和清醒维持试验（MWT）[9]。观察法鲜少用于精神疲劳量化，通过观察被试困倦的状态，如眨眼，打哈欠等生理状态反映出被试的疲劳状态。

以上三项措施都具有侵扰性，因为用户必须停止目前的工作来完成问卷或意识任务。因此，这些方法不能用来监测日常生活中的精神疲劳。生理指标测量法可以在兼顾日常工作的同时检测人体的疲劳状态。近年，国内外学者对生理指标检测疲劳进行了许多的研究。脑电图仪（EEG）广泛用于测量疲劳驾驶。一个澳大利亚研究团队开发了基于EEG的驾驶员抗疲劳系统来监测驾驶员的精神疲劳[10;II]，利用ANOVA分析，发现不同频段波谱：delta（o）（ $\pm 0 { - } 4 \mathrm { H z } ,$ ，theta（0）（ $4 { \sim } 8 \mathrm { H z }$ ，alpha(α）（ $8 { \sim } 1 3 \mathrm { H z }$ ）在疲劳和警觉状态存在显著差异。针对EEG与疲劳关系的研究，张露等人在双耳差频声刺激下检测β波和$( \mathrm { ~ a ~ } + \mathrm { ~ } \Theta \mathrm { ~ } ) / \mathrm { ~ \beta ~ }$ ，发现其在提高注意力和警觉度、对抗脑力疲劳方面具有应用前景[12]。周佳苹等通过观看娱乐节目实验测试发现，( $\mathrm { ~ a ~ } + \mathrm { ~ } \theta$ ）/β、β/α在疲劳和正常状态下具有显著差异[13]。近年，机器学习算法也被广泛应用于疲劳驾驶研究中，Hu等人从EEG信号中提取出40个频谱特征，用SVM模型进行训练，达到 $86 \%$ 的疲劳驾驶识别准确率[14]。Hu 等人基于梯度提升决策树模型(GBDT)将EEG信号识别驾驶疲劳的准确度提升至 $94 \%$ （22个实验样本）[15]。然而，基于脑电的疲劳检测所使用的装置通常具有多个通道和电极，这并不适合在日常生活中使用，特别是在办公室或家居场景。因此非常需要一种随时监测心理精神疲劳的便携式可穿戴设备。

随着最新的卫生信息技术发展和智能手环等智能可穿戴设备的普及，实时和远程的健康监测和管理成为可能。近年来出现了许多用于连续获取生理参数的智能传感器，例如带有蓝牙无线传输功能的便携式心电仪，心率和血压传感器。其中，ECG（心电图机）是一种有前景的实时精神疲劳监测设备。相比于复杂导联体系的脑电图仪，它可以通过更便捷的方式获取心电信号。早期的研究表明，自主神经系统（ANS）与心脏节律之间具有相关性[16]。因此，可以用ECG信号来测量精神疲劳状态。国内外探索ECG与疲劳关系的相关研究主要集中于视觉疲劳和运动疲劳两方面。Yang等人利用ECG研究观看3D/2D电影产生的视觉疲劳，发现 SDNN 随疲劳产生而升高,NN.mean随之下降[17]。宋涛等人研究运动员在疲劳试验前后 HRV的变化特征，研究发现时域指标在疲劳试验后下降，而频域指标却显著升高，验证了HRV作为一项检测运动性疲劳的可靠性[18]。

王钧基于主观疲劳量表与HRV相结合对运动性疲劳进行检测，研究发现，在连续多次运动疲劳后，NN.mean、SDNN、RMSSD、PNN50值降低，HRV与血液生化指标具有较好的相关性[19]。HRV被证明可用用作检测视觉疲劳、运动疲劳，然而视觉疲劳和运动疲劳可以从表象特征观察到，而复杂脑力劳动产生的精神疲劳却鲜少能被直接观察并测量。

本文的研究主要探索如何用便携式心电仪设备检测精神疲劳。无可避免的是，单导联的便携式心电仪设备与传统多导联仪器相比，采集信号的准确度会有所降低，而本文的研究目的在于基于便携式心电仪，提出一种工程可行性方案，探索便携心电设备辅助疲劳检测进行健康管理的可行性而非为医学诊断提供依据。针对该研究问题，本文设计和进行了一项实验来测试可穿戴心电仪测量精神疲劳的可行性。

# 1 实证与分析方法

# 1.1数据准备

本次采用设备为朗朗科技公司研发的可穿戴式心电仪“LaPatch”，其采集ECG信号的芯片为德州仪器研发的ADS1292R芯片，通过蓝牙技术将数据传至移动终端。35名无心脏病史的健康大学生参与实验，其中男女比例1:1.3,年龄段分布在 $2 3 { \pm } 4$ 岁。在实验过程中，被试被要求佩戴一个"LaPatch"心电仪设备，可以实时采集被试的ECG信号。在实验开始前，被试被要求填写14项Chalder 疲劳量表[20]以表征其当前的疲劳程度，在实验工程中，被试被要求完成一套测评，其中包括30道逻辑推理题，25道记忆题，总共持续时间 $5 4 { \pm } 8 \mathrm { m i n }$ ，在测试结束后，被试被要求再次按照自身的真实感受再次填写14项Chalder疲劳量表，根据文献[20]中的3/4的最佳阈值，本次试验将问卷量表得分超过50分的标记为“疲劳”（fatigue $= 1$ )，将小于50分的标记为“正常”（fatigue $= 0$ ）。

# 1.2 HRV 指标提取

ECG信号是心脏在每个心动周期中，由起搏点、心房、心室相继兴奋而产生的生物电的变化。心率变异性（HeartRateVariability）是反映自主神经系统活性和定量评估心脏交感神经与迷走神经张力及其平衡性的一套量化指标[2I]，其通过测量连续R-R心跳间期变化的变异性来反映心率的变化过程及规律，从而用以判断其对全身器官的综合影响，包括脑力活动。用HRV指标判断人体疲劳状态，从医学理论上说，可以得到一个更加综合的评价结果。

HRV指标体系通常分为时域和频域两种。时域指标是根据RR序列间期的统计分析提取。主要指标包括正常心跳间期均值NN.mean；正常心跳间期标准差SDNN；短期平均正常心跳间期标准差；连续相邻正常心跳间期差值的均方根SDANN;全部RR间期中相邻的正常心跳间期只差大于 $5 0 \mathrm { m s }$ 的心搏数NN50；NN50除以正常心跳间期总数乘以100得到PNN50，其计算公式如表1所示。频域指标是将原始ECG时域信号通过傅里叶变换转换到频域并计算不同频段的谱密度（PSD）得到。频域指标主要分为四个频段：总功率TP（ $( 0 { \sim } 0 . 4 \mathrm { H z } )$ ；极低频段功率VLF( $0 . 0 0 3 { \sim } 0 . 0 4 \mathrm { H z }$ )；低频功率LF $\langle 0 . 0 4 { \sim } 0 . 1 5 \mathrm { H z } \rangle$ ）高频功率HF（ $( 0 . 1 5 { \sim } 0 . 4 ~ \mathrm { H z } )$ ；低频高频功率平衡比LF/HF。研究表明，VLF反映人体体温的调节能力[22]、血管舒展以及体液系统调节[23:24]；LF 反映人体对心脏交感神经与副交感神经活动的双重调控[25:26]；HF主要反映迷走神经活动的调节作用[27]。LF/HF平衡比反应交感神经和副交感神经系统的平衡。

本实验中ECG信号的采样频率为 $2 5 0 \mathrm { H z }$ 。计算HRV指标的时间窗为 $5 ~ \mathrm { m i n }$ ，本文一共计算了十个HRV指标，分别是：NN.mean,、SDNN、 SDANN、PNN50、rMSSD、TP、HF、LF、VLF以及 LF/HF。

表1HRV 时域指标公式  

<html><body><table><tr><td>指标</td><td>公式</td><td>单位</td></tr><tr><td>NN.mean</td><td>£-1(NNi) N</td><td>ms</td></tr><tr><td>SDNN</td><td>N-1 sqrt(2-(NN-mNN)2)</td><td>ms</td></tr><tr><td>SDANN</td><td>N-1 sqrt(2(N-NSm)</td><td>ms</td></tr><tr><td>rMSSD</td><td>sqrt(mean(NNi+1 -NNi)²))</td><td>ms</td></tr><tr><td>NN50</td><td>Count(INNi+1-NNi)>50ms</td><td>-</td></tr><tr><td rowspan="2">PNN50</td><td>count(INNi+1-NNil)>50ms × 100%</td><td></td></tr><tr><td>N-1</td><td></td></tr></table></body></html>

# 1.3数据分析

在剔除由于设备不稳定性以及特殊情况所导致的异常值和缺失值后，29个被试的数据被认为合格用以后续研究。本次实验全程持续 $6 0 { - } 8 0 \ \operatorname* { m i n }$ （其中测试时间 $5 4 { \pm } 8 \ \mathrm { m i n }$ )。我们选取测试开始前 $1 0 ~ \mathrm { m i n }$ 的ECG数据用以计算HRV时域和频域指标作为实验前的生理指标对应实验前的Chalder疲劳量表结果，利用测试结束前 $1 0 ~ \mathrm { m i n }$ 的ECG 数据得到HRV时域和频域指标作为实验后的生理指标对应实验后的Chalder疲劳量表结果。最终，58组带疲劳标签的样本（测试前29组 $^ +$ 测试后29组）用于后续的数据分析。

# 1.3.1指标共线性分析

考虑到多重共线性对模型表现的影响。本文用皮尔逊系数来做冗余性分析。当两个指标的相关系数超过0.7时，则认为这两个指标具有多重共线性，仅保留其中一个指标。如图1所示，SDNN与rMSSD具有明显的共线性关系；TP，LF和HF同样也具有高共线性。因此在后续建模中，SDNN和rMSSD中只能保留一个，同样TP，LF，HF由于其共线性，也只能保留一个变量。

![](images/0a064456efc274dd66de678252140e4b4f332f748db626c6d90db17d3c4660fe.jpg)  
图1HRV指标相关系数图

# 1.3.2HRV指标与精神疲劳相关分析

考虑到HRV指标通常分布不均匀，本文采用曼-惠特尼U检验来测试疲劳状态和正常状态下各个HRV指标的统计差异性。曼-惠特尼U 检验是当前应用最广泛的样本秩和检验法。其适用于当正态分布、方差齐次性等达不到T检验要求时，作为T检验的替代检验方法，通过考虑每个样本中各测定值所排的秩，以检验两个总体的均值是否有显著差异。曼-惠特尼U检验的P值，可以作为考察HRV各项指标的显著性的参考依据。

图2展示了HRV指标在疲劳与正常状态下的箱线图。从图2可以看出，PNN50是在疲劳状态下显著低于正常状态，NN.mean也是一个同样显著的指标，在疲劳状态下会有明显下降。rMSSD、TP、VLF和LF指标在疲劳状态下，与正常状态相比会有微小上升。

![](images/719449ea6b18a178d402407e367bed6c79f2ed75078bd63c343c3b41f8679abd.jpg)  
图2HRV指标在疲劳和正常状态下的箱线图

表2展示了曼-惠特尼U检验结果，在0.1的显著水平下，PNN50 指标下，疲劳状态和正常状态存在显著差异( $\scriptstyle \cdot = 0 . 0 2 \rangle$ ，NN.mean、LF 和VLF 接近显著 $\stackrel { \prime } { p } _ { m e a n } = 0 . 1 1 2$ $p _ { L F } { = } 0 . 1 6 6$ $p _ { V L F } { = }$ 0.109）。而其他指标诸如SDNN、TP、HF、LF/HF 均未通过曼-惠特尼U检验。但是曼-惠特尼U检验仅仅从均值角度检测是否存在显著性差异，而并未对于HRV指标与疲劳之间的关系进行探究。

表2曼-惠特尼U检验结果  

<html><body><table><tr><td>HRV指标</td><td>原假设H0</td><td>P值</td></tr><tr><td>NN.mean</td><td>X{fatigue = 0}= X{fatigue =1}</td><td>0.112</td></tr><tr><td>SDNN</td><td>X{fatigue = 0}= X{fatigue = 1}</td><td>0.597</td></tr><tr><td>PNN50</td><td>X{fatigue = 0}= X{fatigue = 1}</td><td>0.020 (**)</td></tr><tr><td>TP</td><td>X{fatigue = 0}= X{fatigue = 1}</td><td>0.225</td></tr><tr><td>LF</td><td>X{fatigue = 0}= X{fatigue = 1}</td><td>0.166</td></tr><tr><td>HF</td><td>X{fatigue = 0}= X{fatigue = 1}</td><td>0.335</td></tr><tr><td>VLF</td><td>X{fatigue= O}= X{fatigue = 1}</td><td>0.109</td></tr><tr><td>LF/HF</td><td>X{fatigue = O}= X{fatigue = 1}</td><td>0.312</td></tr></table></body></html>

# 1.3.3基于随机森林的HRV指标评价

随机森林分类器是一种基于随机抽取的样本信息，通过建立多个独立决策树模型分别针对预测目标建立分类模型，并通过综合所有决策树独立预测结果，基于投票方式决定待分类变量的类别。假设一共生成K颗决策树，样本的特征数为M，依据bootstrap 抽样提取子训练集，再从全部特征中随机抽取制定数目的特征建立多个决策树分类器 $\{ h ( x , \theta _ { i } ) , i = 1 , 2 , 3 \dots K \}$ ，其中 $\{ \theta _ { i } \}$ 是独立同分布的随机向量。

每一颗决策树的生长依赖于一个独立同分布的随机向量；其整体的泛化误差则取决于随机森林中单颗决策树的分类能力以及各分类树的相关程度。随机森林除了作为一种分类器以外，同时也可以用于特征选择，基于随机森林的特征评价主要有两种形式：

1)基于Gini指数的变化程度

分类树在剪枝过程中通常通过基于节点纯度最大原则判断是否进行分裂操作。节点纯度通常根据Gini指数来度量：

$$
\begin{array} { r } { G i n i ( D ) = \sum _ { k = 1 } ^ { | Y | } \sum _ { k ^ { ^ { \prime } } \neq k } p _ { k p _ { _ k ^ { \prime } } } } \end{array}
$$

# (1)

Gini指数越小，则纯度越高，依据Gini指数（式（1)）的变化，可以反映每个特征的重要性，其值越小，纯度越高，说明特征越重要[28;29]。

2)基于分类准确度下降的程度

袋外误差(out-of-bagerror,OOB)通常用来衡量分类精度，其同样可以用来衡量特征重要性。在得到每一颗决策树的OOB误差 $\left( B _ { 0 } \right)$ ，对于每一个参与决策树运算的特征变量，保持其他特征取值不变，将指定特征袋外数据取值随机打断，重新计算决策树袋外误差 $( B _ { 1 } )$ ，所有决策树两类袋外误差的差值的均值即为该特征的重要性评分VIM，对于特征 $\mathbf { M }$ ，重要性评分公式为

$$
\begin{array} { r } { V I M ( M ) = \frac { 1 } { N } \sum _ { k = 1 } ^ { K } ( B _ { 1 _ { t } } ^ { M } - B _ { 0 _ { t } } ^ { M } ) } \end{array}
$$

重要性评分VIM越大则特征重要性越高 $[ 3 0 ; 3 1 ]$ 。

图3展示了基于两种随机森林指标评价的重要性得分结果。从图中可以看出，在基于分类准确度下降的程度的评价体系中，最为重要的五个指标分别是VLF、LF、TP、NN.mean、PNN50,重要程度依次递减，而基于Gini指数的变化程度的评价体系中，最为重要的五个指标分别为NN.mean、PNN50、rMSSD、VLF、LF，重要程度依次递减，结合曼-惠特尼U检验以及随机森林的检验结果，本文将NN.mean、PNN50、TP、LF、VLF列为重要指标，作为后面分类模型的验算指标组合集合。

![](images/e036f8530a2314573689a17af4a8b0616e3f5754d6797414a13d7bf2679998d2.jpg)  
图3基于随机森林的HRV指标的重要性评价

# 1.4分类器算法理论与性能比较

# 1.4.1分类器算法理论

1)支持向量机SVM分类算法

SVM分类器学习思想是基于训练集D在样本空间中找到一个划分超平面，将不同类别的样本分开，超平面可以用如下线性方程表示：

$$
\boldsymbol { w ^ { T } } \boldsymbol { x } + \boldsymbol { b } = 0
$$

假设超平面 $( w , b )$ 能将样本正确分类，则对于 $\forall ( x _ { i } , y _ { i } ) \in \mathbb { D }$ 有

$$
y _ { i } ( w ^ { T } x _ { i } + b ) \geq 1 , i = 1 , 2 \dots , m
$$

# (4)

距离超平面最近的几个训练样本点使得等式(4)成立，被称为支持向量(supportvector)，两个异类支持向量到达超平面的距离之和为

$$
\begin{array} { r } { \gamma = \frac { 2 } { \| w \| } } \end{array}
$$

欲找到具有最大隔间(maximummargin)的划分超平面，即最大化 $\| \boldsymbol { w } \| ^ { - 1 }$ 等价于最小化 $\| w \| ^ { 2 }$ ，求解优化方程：

$$
m i n _ { \ l _ { 2 } } ^ { \ l _ { 1 } } \| w \| ^ { 2 }
$$

$$
\operatorname { s . t . } y _ { i } ( w ^ { T } x _ { i } + b ) \geq 1 , i = 1 , 2 , \ldots , m
$$

2）朴素贝叶斯分类器（naive Bayes）

朴素贝叶斯的分类思想是在贝叶斯概率框架下，在所有相关概率已知情况下，基于这些概率和误判损失来选择最优的类别标记。其判断准则是基于后验概率 $P ( c | x )$ 及误判损失，以最小化条件风险为原则的最优分类器。朴素贝叶斯分类器基于"属性条件独立性假设"：对已知类别，假设所有属性相互独立，则基于该假设，样本 $x$ 相对于类标记 $\mathbf { \Psi } _ { c }$ 的类条件概率 $P ( c | x )$ 表示为

$$
\begin{array} { r } { P ( c | x ) = \frac { P ( c ) P ( x | c ) } { P ( x ) } = \frac { P ( c ) } { P ( x ) } \prod _ { i = 1 } ^ { d } P ( x _ { i } | c ) } \end{array}
$$

其中： $d$ 表示特征类别， $x _ { i }$ 表示 $x$ 在第 $i$ 个属性上的取值。由于对于所有特征类别来说 $P ( x )$ 相同，因此最小化分类错误率的朴素贝叶斯最优分类器为

$$
\begin{array} { r } { h _ { n b } ( x ) = \underset { c \in y } { a r g m a x } P ( c ) \prod _ { i = 1 } ^ { d } P ( x _ { i | } c ) } \end{array}
$$

朴素贝叶斯分类器的训练过程就是基于训练集 $D$ 估计类先验概率 $P ( c )$ ，并根据式(8)为每个特征估计条件概率 $P ( x _ { i } | c )$ ，再根据式(7）得到样本 $x$ 相对于类标记 $\scriptstyle { \begin{array} { l } { c } \end{array} }$ 的类条件概率 $P ( c | x )$ ，将样本划分到类条件概率最大的类别。

# 3）K近邻分类器KNN

K近邻(K-nearestneighbor，KNN)分类器，给定测试样本，基于距离度量函数找出训练集中与其靠近的 $k$ 个训练样本，通常通过“投票法”，即选择这 $k$ 个样本中出现最多的类别标记作为预测结果。给定样本 $x$ ，若其最近邻样本为 $z$ ，则最近邻分类器出错概率，即 $\textbf { x }$ 与 $z$ 类别标记不同的概率可以表示：

$$
\begin{array} { r } { P ( e r r ) = 1 - \sum _ { c \in y } P ( c | x ) P ( c | z ) } \end{array}
$$

4）逻辑回归（logistics regression）

逻辑回归是一种针对二分类变量的广义的线性回归，在线性回归模型的基础上引入对数几率函数使得因变量y尽可能逼近0或1，本质在形式上仍然保留线性回归的特征，实际上求取输入空间到输出空间的非线性函数映射，逻辑回归模型表达

式如式(10)所示。

$$
\begin{array} { r } { \ln \frac { y } { 1 - y } = w ^ { T } x + b } \end{array}
$$

若将式(10)中的 $\mathbf { y }$ 视为后验概率 $p ( y = 1 | x )$ ，则式(10)可以表达为

$$
\begin{array} { r } { \ln \frac { p ( y = 1 | x ) } { p ( y = 0 | x ) } = w ^ { T } x + b } \end{array}
$$

由 $p ( y = 0 | x ) + p ( y = 1 | x ) = 1$ 得到：

$$
\begin{array} { r } { p ( y = 1 | x ) = \frac { e ^ { w ^ { T } + b } } { 1 + e ^ { w ^ { T } + b } } } \end{array}
$$

$$
\begin{array} { r } { p ( y = 0 | x ) = \frac { 1 } { 1 + e ^ { w ^ { T } + b } } } \end{array}
$$

对逻辑回归模型求最大似然函数，可以估计出 $\textstyle \mathbf { \psi } _ { w } , \mathbf { \psi } _ { b }$

$$
\begin{array} { r } { l ( w , b ) = \sum _ { i = 1 } ^ { m } l n p ( y _ { i } | x _ { i } ; w , b ) } \end{array}
$$

1.4.2分类器性能比较

本文一共对比了四种机器学习分类算法：支持向量机（SVM)，朴素贝叶斯分类器（NaiveBayes)，KNN以及逻辑回归。并通过网格搜索寻找最优参数，分类器的性能通过交叉验证进行检验，最终分类器的性能评估有交叉验证准确度和AUC决定。

表3\~6展示了四种分类模型下，考虑不同数量的指标组合，最优的分类器性能。从结果来看，KNN算法的表现明显优于其他三种分类算法，在NN.mean、TP和LF三个HRV指标组合下，交叉验证准确率达到 $7 5 . 5 \% ( \mathrm { K } { = } 3 ) \ 。 \mathrm { S V M }$ 分类器仅次于KNN算法，其最优分类器下，交叉验证准确率达到 $71 . 6 \%$ （HRV指标组合为NN.mean、PNN50)。朴素贝叶斯模型和逻辑回归模型表现略次，交叉验证算法的准确率分别为 $6 5 . 6 \%$ 和 $69 . 9 \%$ 。表7和图4分别给出了四种算法的AUC值和ROC曲线，从结果可以看出，KNN的AUC值最高，达到0.74，SVM的AUC值为0.68，NB以及LR的AUC值相对较低，仅达到0.64和0.65。从整体上我们可以得到结论，KNN分类器在应用于脑力劳动者精神疲劳分类中，具有显著有效的效果，而根据最优分类器选取的指标结果来看，用于检测脑力劳动者精神疲劳状态的最有效的指标为PNN50,NN.mean，LF，VLF以及HF，这四个指标无论是在之前的随机森林评价得分还是在最优分类器指标选择的结果上看，都是最有效的。

表3支持向量机模型表现  

<html><body><table><tr><td>指标组合</td><td>SVM交叉验证准确度</td></tr><tr><td>NN.mean</td><td>59.1%</td></tr><tr><td>PNN50</td><td>63.4%</td></tr><tr><td>NN.mean+PNN50</td><td>71.6%</td></tr><tr><td>NN.mean+PNN50+TP</td><td>64.1%</td></tr><tr><td>NN.mean+PNN50+LF+VLF</td><td>64.1%</td></tr><tr><td colspan="2">表4朴素贝叶斯模型表现</td></tr><tr><td>指标组合</td><td>Naive Bayes交叉验证准确度</td></tr><tr><td>NN.mean</td><td>60.0%</td></tr></table></body></html>

<html><body><table><tr><td>PNN50</td><td>65.6%</td></tr><tr><td>NN.mean+PNN50</td><td>64.3%</td></tr><tr><td>NN.mean+PNN50+TP</td><td>54.7%</td></tr></table></body></html>

表5K近邻模型表现  

<html><body><table><tr><td>指标组合</td><td>KNN交叉验证准确度</td></tr><tr><td>NN.mean+TP</td><td>73.5% (k=3)</td></tr><tr><td>PNN50+TP</td><td>69.7% (k=4)</td></tr><tr><td>NN.mean+PNN50</td><td>68.7% (k=9)</td></tr><tr><td>NN.mean+TP+LF</td><td>75.5% (k=3)</td></tr><tr><td>NN.mean+TP+VLF</td><td>73.5% (k=3)</td></tr></table></body></html>

表6逻辑回归模型表现  

<html><body><table><tr><td>指标组合</td><td>Logistic Regression交叉验证准确度</td></tr><tr><td>PNN50</td><td>65.6%</td></tr><tr><td>NN.mean</td><td>66.1%</td></tr><tr><td>NN.mean+PNN50</td><td>62.5%</td></tr><tr><td>NN.mean+PNN50+VLF</td><td>63.1%</td></tr><tr><td>NN.mean+PNN50+LF+TP</td><td>68.3%</td></tr><tr><td>NN.mean+PNN50+TP+LF+VLF</td><td>69.9%</td></tr></table></body></html>

<html><body><table><tr><td colspan="5">表7 四种分类算法的AUC 值</td></tr><tr><td>分类算法</td><td>SVM</td><td>NB</td><td>KNN</td><td>LR</td></tr><tr><td>AUC</td><td>0.68</td><td>0.64</td><td>0.74</td><td>0.65</td></tr></table></body></html>

![](images/02a816d544fca64e59d7796193457a0ceedd060023bd33d04a5d2329ae1b6ec6.jpg)  
图4四种分类算法的ROC 曲线

# 2 结束语

本文基于HRV分析，通过便携式心电仪设备，为脑力工作者精神疲劳检测提供了一种可行性工程方案。本研究在模拟脑力工作场景下，通过结合问卷量表和“朗朗心”便携式心电仪采集的心电数据进行疲劳状态的数据统计分析与疲劳状态识别。本文主要解决了两个问题：精神疲劳状态与哪些HRV指标相关；如何基于HRV指标体系建立疲劳状态识别模型。针对第一个问题，本文通过曼-惠特尼U检验，得到PNN50指标是显著有效的，NN.mean、LF和VLF接近显著。通过随机森林分类器，分别基于Gini指数和分类准确度两种角度，对HRV指标进行重要性评估，基于分类准确度角度，最为重要的五个指标分别是VLF、LF、TP、NN.mean、PNN50，而基于Gini指数角度，最为重要的五个指标分别为NN.mean、PNN50、rMSSD、VLF、LF，结合曼-惠特尼U检验以及随机森林的检验结果，本文将NN.mean、PNN50、TP、LF、VLF 判断为精神疲劳程度的重要指标。针对第二个问题，本文分别对四种机器学习分类器性能进行评估，研究结果显示，KNN算法的表现最佳，在NN.mean、TP 和LF三个HRV指标组合下，交叉验证准确率达到 $7 5 . 5 \% ( \mathrm { K } { = } 3 )$ 。KNN的AUC值最高，达到0.74。从整体上我们可以得到结论，KNN分类器在应用于脑力劳动者精神疲劳分类中，具有显著有效的效果。

过度疲劳对人体身心造成巨大伤害并影响人体的正常思维和工作，研究疲劳状态识别具有重大的现实意义。基于便携式心电仪识别人体疲劳状态，本文提出了一个具有工程可行性的解决方案。本文对心电信号与精神疲劳的关系进行了探索分析，对未来进一步研究精神疲劳，有效的识别、预测和干预人体脑力负荷等问题做下了研究铺垫。

# 参考文献：

[1]Grandjean E.Fiting the task to the man: an ergonomic approach [M].Taylor & Francis,1969:210.   
[2]Staal MA. Stress,Cognition,and Human Performance: A Literature Review and Conceptual Framework [J]. National Aeronautics&Space Administration,2004.   
[3]程珊，马进，惠铎铎，等．精神疲劳评价方法研究进展[J].现代生物 医学进展,2014,14(32): 6387-6390.(Cheng Shan,Ma Jin,Hui Duoduo,el al.The research advancement of objective assessment methods for mental fatigue [J]. Progress in Modern Biomedicine,2014,14 (32): 6387-6390.)   
[4]Ke D.Overwork,stroke,and karoshi-death from overwork [J].Acta Neurol Taiwan,2012,21 (2): 54-59.   
[5]Backé EM,Seidler A,Latza U,et al.The role of psychosocial stress at work for the development of cardiovascular diseases: a systematic review [J]. International Archives of Occupational & Environmental Health,2012,85 (1): 67-79.   
[6] Beer L T D,Pienaar J,Jr S R.Investigating the reversed causality of engagement and burnout in job demands-resources theory [J]. South African Jourmal of Industrial Psychology,2013,39 (1): 9-pages.   
[7] Dewa C S,Loong D, Bonato S,et al. How does burnout afect physician productivity?A systematic literature review [J].Bmc Health Services Research,2014,14(1): 1-10.   
[8]Urrila A S,Stenuit P,Huhdankoski O,et al.Psychomotor vigilance task performance during total sleep deprivation in young and postmenopausal women [J].Behavioural Brain Research,2007,180(1): 42-47.   
[9]Sangal R B,Thomas L,Mitler M M.Maintenance of wakefulness test and multiple sleep latency test.Measurement of different abilities in patients with sleep disorders [J]. Chest,1992,101(4): 898-902.

[10]Lal SK,CraigA.A critical review of the psychophysiology of driver fatigue [J].Biological Psychology,2001,55 (3):173-194.

[11]Lal SKL,CraigA.Electroencephalography activity associated with driver fatigue:Implications for a fatigue countermeasure device [J].Journal of Psychophysiology,2001,15 (3): 183-189.

[12] 张露，焦学军，高翔，等.Beta 频段双耳差频声刺激对大脑生理状态的 影响[J].载人航天,2016,22(2):254-261.(Zhang Lu,Jiao Xuejun,Gao Xiang,et al.Effects ofbeta band binaural beats onbrain physiological status [J].Manned Spaceflight,2016,22 (2): 254-261.)   
[13]周佳苹，张朋柱．基于可穿戴式脑电仪传感器的疲劳状态研究[J].计 算机应用研究,2018,35(8):.(Zhou Jiaping,Zhang Pengzhu.Study on fatigue identification based on wearable electroencephalogram [J]. Application Research of Computers,2018,35 (8): .)   
[14] Hu Shuyan, Zheng Gangtie,Peters B.Driver fatigue detection from electroencephalogram spectrum after electrooculography artefact removal [J].Iet Intelligent Transport Systems,2013,7(1):105-113.   
[15] Hu Jianfeng,Min Jianliang.Automated detection of driver fatigue based on EEG signals using gradient boosting decision tree model [J]. Cognitive Neurodynamics,2018,(12): 1-10.   
[16] Sherwood L. Human physiology: from cels to systems [M]. Brooks//Cole, Cengage Learning, 2012.   
[17] Yang Xinpan,Wang Danli,Hu Haichen,et al.P-31:visual fatigue assessment and modeling based on ECG and EOG caused by 2D and 3D displays [J].Sid Symposium Digest ofTechnical Papers,2016,47(1): 1237- 1240.   
[18]宋涛，袁春平，吴钰祥，等.HRV 应用于运动性疲劳判断实验教学的探 究[J]．实验室科学,2017,20 (2):8-11.(Song Tao,Yuan Chunping,Wu Yuxiang,et al.Research on the application of HRV in the evaluation of exercise fatigue for experimental teaching[J].Laboratory Science,2017,20 (2): 8-11.)   
[19]王钧．基于主观感觉疲劳量表和心率变异性相结合的运动性疲劳监测 [D]．武汉：武汉体育学院,2015.(Wang Jun.Research on sports fatigue detection method based on the combination of RPE and HRV [D]. Wuhan: Wuhan Sports University,2015.)   
[20] Chalder T,Berelowitz G,Pawlikowska T,et al. Development ofa fatigue scale [J]. Jourmal of Psychosomatic Research,1993,37 (2): 147-153.   
[21] Mulder L J. Measurement and analysis methods of heart rate and respiration for use in applied environments [J]. Biological Psychology,1992,34 (2-3): 205-236.   
[22] Aoki K,Stephens D P,Johnson JM.Diurnal variation in cutaneous vasodilator and vasoconstrictor systems during heat stress [J]. Am JPhysiol Regul Integr Comp Physiol,2001,281(2): R591.   
[23] Braga AN,DaSLM,DaSJ,etal.Effectsofangiotensinsonda-ght fluctuationsandstress-inducedchanges inblood pressure[J].Ajp Regulatory Integrative & Comparative Physiology,2002,282 (6): R1663- 71.

[24] JrPG,Rivkees SA.Ontogeny of humoral heart rate regulation in the

embryonic mouse [J].Ajp Regulatory Integrative & Comparative Physiology,2001,281 (281): R401-7.   
[25]LanfranchiPA,Somers VK.Arterial baroreflex function and cardiovascular Variability: interactions and implications [J].American Journal of Physiology Regul Integr Comp Physiol, 2002,283 (4): R815.   
[26] Malpas S C.Neural influences on cardiovascular variability:possibilities and pitfalls [J].American Journal of Physiology Heart & Circulatory Physiol0gy,2002,282(1):H6.   
[27]Rentero N,CividjianA,TrevaksD,etal.Activity patterns of cardiac vagal motoneurons in rat nucleus ambiguus [J].Ajp Regulatory Integrative & Comparative Physiology,2002,283 (6):R1327-34.   
[28]NunesL O,Biscainho LWP,LeeB,etal.Degradation type classifier for full band speech contaminated with echo,broadband noise，and reverberation [J]. IEEE Trans on Audio Speech & Language Processing, 2011,19(8):2516-2526.   
[29]张洪强，刘光远，赖祥伟．随机森林算法在肌电的重要特征选择中的应 用[J]．计算机科学，2013,40(1):200-202.(Zhang Hongqiang,Liu Guangyuan，Lai Xiangwei.Application of random forest algorithm in important feature selection from EMG signal[J].Computer Science,2013, 40 (1): 200-202.)   
[30]Belgiu M,Dragut L.Random forest in remote sensing:A review of applications and future directions [J].ISPRS Journal of Photogrammetry & Remote Sensing,2016,114:24-31.   
[31]刘舒，姜琦刚，马玥，等．基于多目标遗传随机森林特征选择的面向对 象湿地分类 [J]．农业机械学报,2017,48(1):119-127.(Liu Shu,Jiang Qigang,Mayue,etal. Object-oriented wetland classification based on hybrid feature selection method combining with relief f,multi-objective genetic algorithm and random forest[J].Progress in Modern Biomedicine,2017,48 (1): 119-127.)