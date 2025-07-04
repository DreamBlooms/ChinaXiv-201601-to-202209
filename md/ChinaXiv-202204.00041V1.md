# 运动想象脑电信号的跨域特征学习方法

韦泓妤‘，陈黎飞ab,c†，罗天健ab

(福建师范大学a 计算机与网络空间安全学院;b.数字福建环境监测物联网实验室;c.福建省应用数学中心,福州 350108)

摘要：运动想象脑电信号采集成本高且个体差异大，跨个体域构建脑电信号模式识别模型属于典型的小样本跨域学习任务。针对该任务，提出了一种运动想象脑电信号的跨域特征学习方法。该方法首先选择最优度量方法对齐协方差并提取共同空间模式特征；其次，在该特征基础上采用领域自适应方法学习目标域的最优跨域特征。为验证所提出方法的可行性与有效性，采用经典模型识别跨域特征，在两个公开的数据集上进行对比实验。实验结果表明，通过所提出方法学习到的跨域特征，在运动想象模式识别中，明显优于现有方法学习到的特征。此外，还详细对比了跨域特征学习方法的各项参数设置、性能及效率。

关键词：运动想象；脑电信号；跨域特征学习；领域自适应；协方差对齐 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.01.0016

Cross-domain feature learning method for motor imagery EEG signals

Wei Hongyua, Chen Lifeia,b,ct, Luo Tianjiana, b (a.CollgeofComputer&CyberSecurityb.DigitalFujianEnvironmentalMonitoringInteretofThingsLaboratoryc.Fujian Applied Mathematics Center,FujianNormal University,Fuzhou 350108,China)

Abstract:MotorimageryEEGsignalsrequiresahighcostforrecording,ndthereisalargedifferenceforindividual'ssignals. Cross-subject motorimageryEEG signalsrecognition task belongs toatypical cross-domain learning problemwithasmal samples set.To solve this problem,this paper proposed a cross-domain feature learning method for motor imagery EEG signals to improve the recognition performance.The proposed method first selected the optimal measurement to align the covarianceofEEG signals,and then extractedcommonspatialpaterns(CSP)from thealignedEEG trials.Second,basedon the CSP features,anoptimal domain adaptation algorithm was selected to learn theoptimal cross-domain features for the targetdomain.Tovalidate thefeasibilityandeffctivenessoftelearnedcross-domainfeatures,classcalmodelwasadopted to recognize the learned cros-domain features,andthecomparative experiments wereconducted on two public datasets. Experimentalresultsshow thatthe learned cross-domain featuresareobviously beter than state-of-the-arts methods in recognition performance.In adition, this paper also compared the parameters seting,performance and eficiency for the proposed method.

Key words: motor imagery; EEG signal; cross-domain feature learning; domain adaptation; covariance alignment

# 0 引言

脑机接口(BCI)[1,2]技术绕过肌肉系统，允许大脑与外部设备之间建立直接的通路，实现神经系统和外部设备间的直接信息通信。BCI技术分为三个主要步骤：收集大脑信号，分析并解码大脑信号，再根据解码结果向外部设备输出控制命令。头皮脑电(EEG)是 BCI最常用的脑电信号类型之一，该信号采用非侵入方式记录大脑活动的电生理现象。基于EEG的BCI主要包括三种方式：运动想象(MI)，稳态视觉电位(SSVEP)、事件相关电位(ERP)。其中，MI属于主动BCI模式，因此基于EEG的MI-BCI是最常使用的BCI范式，也是本文的研究对象[3]。

在MI-BCI中，用户根据提示想象自己身体部位的运动，此时会在对应的大脑皮层区域引起感知运动节律，产生大脑相关皮层区域的脑节律调制，从而在EEG信号中编码不同的运动想象规律和特性。因此，不同运动动作的想象可以产生不同的空间局部化解码，从而识别出不同的运动感知节律模式，最终可根据模式识别结果的映射关系控制外部设备。早期MI-BCI已经应用至医学领域，用于帮助严重瘫痪的患者在没有肌肉系统参与的情况下控制轮椅[4]。近年来，MI-BCI已经帮助中风患者做康复训练以改善其运动功能[5.6],并且MI-BCI的娱乐性应用已经扩展至健康人群。然而，EEG信号记录人脑头皮层的微弱信号变化，易受噪声影响，常用的特征提取方法为共同空间模式(CSP)。CSP是应用非常广泛的一种空域滤波特征提取算法[7.8]，在运动想象任务的特征提取与分类中有不错的效果，该方法能够从多通道的EEG信号中提取出每个类别的最优空间分布成分。在CSP特征基础上，一般可采用线性判别分析(LDA)或支持向量机(SVM)等模型完成运动想象任务的模式识别。

实际上，由于EEG信号采集的成本较高，通常单个被试者的EEG样本数量较少，并且每个被试者的EEG信号分布存在个体差异性，无法将跨被试的全体EEG信号直接用于构建高性能模式识别模型。因此，一些研究者希望通过迁移学习的方法降低EEG信号特征分布的个体差异性[9]，并在全体跨被试者的EEG信号上构建高性能模式识别模型。迁移学习中最常见的任务为领域自适应，经典的领域自适应方法包括Yang 等提出的迁移成分分析(TCA)[1o]、Long 等提出的联合分布适配方法(JDA)[II]、以及考虑稀疏特征选择的迁移联合匹配改进方法(TJM)[12]，还包括 Wang 等提出的动态分布自适应(BDA)[13]。在解决领域自适应的方法中，其基本目标是降低源域和目标域的特征分布差异，以保证源域和目标域的特征分布能共同用于训练分类器，这些方法可拓展至MI-BCI的CSP特征之上，用以提升模式识别的性能[14,15]。

在基于MI-BCI的迁移学习中，一些研究者[6结合核共同空间模式(KCSP)[17]和迁移核学习(TKL)[18]提出了迁移核共同空间模式方法(TKCSP)，并应用于跨被试者的脑电信号处理中。Jayaram[19]等研究者提出了一种不需要目标域标记数据的跨被试者迁移学习的多任务学习框架，并证明该方法对一名肌肉萎缩患者的迁移效果不错。Azab[20]等研究者对上述方法做了进一步的改进，提出MI分类中对跨被试者利用Kullback-Leibler散度进行加权迁移学习。在集成迁移学习中，Hossain[2I]等研究者提出了多类MI分类中跨被试迁移的集成学习方法。

在数据对齐方面，Zanini[22]等研究者提出了一种黎曼距离对齐方法(RA)，并采用改进的MDRM[23]分类器验证了该方法的有效性。Yair[24]等研究者提出了一种在SPD矩阵的锥流形上，通过平行输运解析表达式的领域自适应方法，并证明该方法在跨被试者运动想象分类、睡眠阶段分类和心算识别方面有不错的效果。He 和 $\mathrm { W u } ^ { [ 2 5 ] }$ 在RA的基础上做了改进，提出了一种欧式距离对齐方法(EA)，该方法在欧氏空间上将不同被试者的EEG信号协方差矩阵对齐到单位矩阵上，比RA方法更方便、高效。此外，Rodrigues[2]等研究者提出了黎曼Procrustes分析(RPA)方法，用于对齐跨被试者的EEG信号，该方法在跨被试MI、ERP和SSVEP分类中有着不错的效果。

在流形迁移学习中，Zhang 和 $\mathrm { W u } ^ { [ 2 7 ] }$ 在黎曼流形协方差矩阵对齐基础上，提出了一种在切空间上的流形知识迁移方法(MEKT)。Singh[28]等研究者提出了一种样本选择的迁移学习方法，该方法从少量的目标域样本中估计MDRM分类器使用的样本协方差矩阵。另外，基于深度学习的MI-BCI迁移学习[29]也获得了不错的效果。Wu 等研究者[30]提出了一种应用于MI-BCI分类的并行多尺度滤波器(CNN)，提升了分类结果在迁移上的性能。

运动想象EEG信号具有非平稳特性且易受噪声影响，获取个体域记录的信号代价高且特征分布差异大，跨个体域构建脑电信号模式识别模型属于典型的小样本跨域学习任务。从现有研究的综述中可以看出，目前的研究集中在样本协方差对齐、流形特征自适应或模式识别模型的迁移[31]。为了在个体域之间学习稳定、可靠的跨域特征，本文提出了一种运动想象脑电信号的跨域特征学习方法，用于提升跨个体域脑电信号模式识别性能。首先，该方法选择最优的协方差矩阵距离度量方法，在个体域之间将样本集协方差对齐至单位矩阵。其次，在对齐后的样本集上提取CSP特征，并引入TCA、JDA、BDA和TJM四种不同的领域自适应方法，在待识别的目标域上学习最佳的跨域特征。本文在两个公开数据集上验证了所提出跨域特征学习方法的可行性与有效性，并且从参数设置、模式识别性能和效率上进行了详细对比实验分析。

现有面向运动想象脑机接口的跨域特征学习方法仅针对样本对齐角度或CSP特征跨域自适应角度，跨域的特征学习能力不够，导致运动想象模式识别性能不足。本文同时针对样本角度和CSP特征角度构建跨域特征学习方法，为个体域脑电信号样本集选择最优的样本对齐度量方法，以及CSP特征跨域自适应方法，并在两个公开的脑电数据集上验证了所提出方法的模式识别性能及效率。

# 1 最优协方差矩阵样本对齐

在跨个体域的EEG信号样本对齐中，本文选用欧式距

离对齐方法(EA)[25]。由于该方法需将样本对齐至协方差中心，因此本文将协方差中心计算扩展至不同距离度量方法，并为不同个体选择最优的协方差中心度量方法。

# 1.1协方差矩阵中心对齐方法

协方差矩阵中心可作为多维时间序列分布的度量方式。假设 $X _ { i }$ 是被试者进行运动想象任务获得的第 $i$ 个样本，每个被试者拥有 $n$ 个EEG样本，则个体域的EEG信号样本协方差矩阵中心 $\displaystyle \overline { { R } }$ 为： $\bar { R } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } X _ { i } X _ { i } ^ { r }$ 。该中心采用算法平均值表达，在经典的EA算法中使用欧式距离度量。随后，根据协方差矩阵中心，对每个EEG样本进行对齐操作：

$$
\tilde { X } _ { i } = \overline { { R } } ^ { - \frac { 1 } { 2 } } X _ { i }
$$

经过 $n$ 次对齐后，所有被试者的EEG 样本的平均协方差矩阵都等于单位矩阵，因此来自不同被试者的协方差矩阵分布会更为相似。

# 1.2最优协方差矩阵中心距离度量方法

由于不同任务、不同被试者对EEG信号样本的分布都有影响，在实际个体域的对齐中，需根据每个个体域的样本分布情况，灵活选择合适的协方差中心度量方法。除了欧式距离以外，本文将采用如下7种均值度量方法：

(1)黎曼均值：

$$
\bar { X } = a r g m i n \biggl ( \sum _ { i } \delta _ { R } \left( X , X _ { i } \right) ^ { 2 } \biggr )
$$

其中： $\delta _ { R }$ 表示黎曼空间上两个协方差矩阵的距离。采用梯度下降法，在黎曼空间上进行迭代的均值求解。

(2)对数欧式均值：

$$
\bar { X } = \exp \left( \frac { 1 } { n } { \sum _ { i } \log X _ { i } } \right)
$$

(3)对数det均值：

$$
\overline { { X } } = \left( \sum _ { i } \left( 0 . 5 X + 0 . 5 X _ { i } \right) ^ { - 1 } \right) ^ { - 1 }
$$

(4)Wasserstein 均值：

$$
K = \left( \sum _ { i } ( K X _ { i } K ) ^ { 1 / 2 } \right) ^ { 1 / 2 }
$$

其中： $K = \bar { X } ^ { - 1 / 2 }$ 。根据Wasserstein度量方式，初始化迭代次数，不断更新 $\boldsymbol { \kappa }$ ，直到迭代次数停止。

(5)AJD对数均值：

$$
\bar { X } = A ^ { T } e x p \Bigg ( \sum _ { i } \log B ^ { T } X _ { i } B \Bigg ) A
$$

其中：矩阵 $\textbf {  { B } }$ 是基于Pham 算法的近似联合对角化， $\boldsymbol { A }$ 是 $\textbf {  { B } }$ 的逆矩阵。

(6)调和均值：

$$
\bar { X } = \left( \frac { 1 } { n } \sum _ { i } X _ { i } ^ { - 1 } \right) ^ { - 1 }
$$

(7)KL散度均值，计算方式为

$$
\bar { X } = ( \frac { 1 } { n } \sum _ { i = 1 } ^ { n } X _ { i } ) ^ { 1 / 2 } \Biggl [ ( \frac { 1 } { n } \sum _ { i = 1 } ^ { n } X _ { i } ) ^ { - 1 / 2 } \Biggl ( \frac { 1 } { n } \sum _ { i } X _ { i } ^ { - 1 } \Biggr ) ^ { - 1 } \Biggr ] ^ { 1 / 2 } ( \frac { 1 } { n } \sum _ { i = 1 } ^ { n } X _ { i } ) ^ { 1 / 2 }
$$

实际上，该均值是算术平均值和调和平均值之间的几何平均值。

实际实验中，本文将根据不同个体域EEG样本分布情况，采用trial-and-error的方式选择最优的度量方式，计算协方差矩阵中心算术平均值，并采用式(1)对齐不同个体域的EEG信号样本集。

# 2 EEG信号的跨域CSP特征学习

在迁移学习方法中，领域自适应是常见的基于核空间的方法。其本质是最小化源域特征分布和目标域特征分布的距离，最常使用衡量源域特征分布和目标域特征分布的距离为

MMD[32]。在EEG信号的跨域CSP特征学习中，本文的目标是在多个源域和目标域CSP特征最小化MMD距离。

# 2.1迁移成分分析方法

迁移成分分析方法(TCA)为基于边缘分布的自适应[0]方法。假设用源域和目标域的边缘分布采用 $P ( X _ { s } )$ 和 $P ( X _ { t } )$ 表示，TCA方法的目的是减小 $P ( X _ { s } )$ 和 $P ( X _ { t } )$ 之间的差异。TCA的目的是最小化MMD距离，其优化目标为

$$
\begin{array} { c } { \operatorname* { m i n } _ { \nu } { t r \big ( A ^ { T } X L X ^ { T } A \big ) } + \mu \big \| A \big \| _ { F } ^ { 2 } } \\ { s . t . ~ A ^ { T } X H X ^ { T } A = I } \end{array}
$$

其中， $\textbf { \em A }$ 是最小化MMD的映射矩阵， $\textbf {  { H } }$ 是中心矩阵，${ \cal H } = I _ { n _ { 1 } + n _ { 2 } } - 1 / \left( n _ { 1 } + n _ { 2 } \right) 1 1 ^ { r } , L$ 即为MMD 距离。采用拉格朗日乘子法即可求得 $A$ 的最优解为 $\left( X L X + \mu I \right) ^ { - 1 } X H X$ 最大的 $m$ 个特征值对应的特征向量。最终，通过映射 $A$ 变换源域和目标域特征。

# 2.2联合分布自适应

联合分布自适应方法 (JDA)[I]的目标是减小源域和目标域的联合概率分布的距离。用 $P ( X _ { s } )$ 和 $P ( X _ { t } )$ 之间的距离、以及 $P ( Y _ { s } | X _ { s } )$ 和 $\textstyle P ( Y _ { t } \mid X _ { t } )$ 之间的距离来近似表达。由于目标域没有标记数据，所以无法直接求解 $\textstyle P ( Y _ { t } \mid X _ { t } )$ 。JDA方法通过迭代的方式在源域特征和样本上训练简单的分类器，并在目标域特征上预测伪标签 $\mathbf { y } _ { t } ^ { \prime }$ 。形式地，JDA的优化目标为

$$
\operatorname* { m i n } _ { A } \sum _ { c = 0 } ^ { C } t r \big ( A ^ { T } X M _ { c } X ^ { T } A \big ) + \lambda \| A \| _ { F } ^ { 2 }
$$

$$
A ^ { \boldsymbol { \tau } } X H X ^ { \boldsymbol { \tau } } A = I
$$

其中： $A ^ { \boldsymbol { \tau } } \boldsymbol { X } \pmb { H } \pmb { X } ^ { \boldsymbol { \tau } } \pmb { A } = \pmb { I }$ ， $\textbf {  { H } }$ 是中心矩阵， $\textbf { \textit { I } }$ 是单位矩阵， ${ M } _ { c }$ 表示由源域样本和标签，以及目标上样本和预测伪标签计算的 $M M D$ 。通过同样计算方法，获得映射矩阵 $\boldsymbol { A }$ ，用于变换源域和目标域特征。

# 2.3 动态分布自适应

JDA方法将边缘分布和概率分布的重要性视作同等，然而，由于不同BCI任务和不同人群，其重要性并不始终相等。针对JDA的不足之处，动态分布自适应方法(BDA)设置平衡因子 $\mu { \in } [ 0 , 1 ]$ 动态调整边缘分布和条件分布的重要性[13]。形式地，BDA的优化目标为

$$
\operatorname* { m i n } _ { A } t r \Bigg ( A ^ { T } X \Bigg ( ( 1 - \mu ) M _ { \theta } + \mu \sum _ { c = 1 } ^ { C } M _ { c } \Bigg ) X ^ { T } A \Bigg ) + \lambda \| A \| _ { F } ^ { 2 }
$$

$$
s . t . ~ A ^ { T } X H X ^ { T } A = I , 0 \leq \mu < 1
$$

其中：BDA方法采用A-distance估计。需要指出的是，BDA方法每轮迭代后，利用伪标签和A-distance计算新的 $\mu$ 值。同样地，获得的映射矩阵用于变换源域和目标域特征。

# 2.4迁移联合匹配

无论是JDA还是BDA,都将源域中所有的特征整体用于计算MMD，从而获得最优特征映射矩阵 $A$ 。实际上，源域中只有一些有迁移特征意义的特征，对计算MMD能够起到决定作用，而另一些是存在负迁移的特征，则会对MMD 计算造成反作用。因此，TJM方法[12]在计算放射矩阵时，将源域的放射矩阵添加稀疏正则化 $\left\| A _ { s } \right\| _ { 2 , 1 }$ ，而保证目标域的放射矩阵为二范数不变 $\left. A _ { t } \right. _ { F } ^ { 2 }$ 。通过系数正则化的选择，即可在优化过程中从源域中选择更具代表性的特征，用于计算MMD，从而提升特征迁移的性能[33]。因此，在TCA基础上TJM的定义可写为

$$
\operatorname* { m i n } _ { A } t r \big ( A ^ { T } K M K ^ { T } A \big ) + \lambda \big ( \big \| A _ { s } \big \| _ { 2 , 1 } + \big \| A _ { t } \big \| _ { F } ^ { 2 } \big )
$$

$$
s t . A ^ { T } K H K ^ { T } A = I
$$

其中： $\lambda$ 为正则项的系数。由于上述优化目标具有非凸的特征，因此需要通过迭代的方式求解。最终，由 $\pmb { A } = \left[ \pmb { A } _ { s } , \pmb { A } _ { t } \right]$ 构建稀疏映射矩阵，在变换源域和目标域特征的同时保证稀疏性，提取最具代表性特征。

# 3 运动想象EEG信号跨域特征学习方法

# 3.1 共同空间模式

共同空间模式(CSP)[34]针对二分类任务，从多通道 EEG信号中提取可区分特征。假设 $X _ { \iota }$ 和 $X _ { 2 }$ 分别为两类不同运动想象任务的EEG信号，首先，计算各域对齐后EEG信号样本集的平均协方差矩阵 $C _ { i }$ 1 $( i = 1 , 2 )$ ；其次，寻找一个最优的空间滤波器 $w$ ,使得类别1的方差最大，类别2的方差最小，其优化目标为[34]：

$$
C _ { I } w = \lambda ( C _ { I } + C _ { 2 } ) w
$$

其中： $\lambda$ 和 ${ \pmb w }$ 分别为广义特征值和特征向量，然后利用${ \cal Z } _ { M x N } = W _ { M x M } X _ { M x N }$ 将EEG信号进行空域滤波获得特征向量 $z$ u随后，选择特征向量 $z$ 的前 $m$ 行和后 $m$ 行 $( 2 \mathrm { m } < M )$ ，形成的特征向量作为分离后的空域滤波特征。对于EEG信号 $X _ { i }$ ，CSP算法最终提取到的特征 $f _ { i }$ 为： $f _ { i } = l o g \left( \boldsymbol { Z } \boldsymbol { Z } ^ { T } \right)$ 。

# 3.2 线性判别分析

线性判别分析(LDA)[35]是MI-BCI中常用的分类器，对提取到的CSP特征分类后，完成运动想象任务的模式识别。给定特征集合 $D = \{ ( x _ { i } , y _ { i } ) \} _ { i = 1 } ^ { m } , y _ { i } \in \{ 0 , 1 \}$ ， $X _ { i } , \mu _ { i } , \Sigma _ { i }$ 分别表示第 $i \in \{ 1 , 2 \}$ 类运动想象EEG信号提取到的跨域特征，均值向量和协方差矩阵。首先，LDA分别计算为"类内散度矩阵” $\boldsymbol { S } _ { b }$ 和"类间散度矩阵” $\boldsymbol { S } _ { v }$ ，并保证 $\boldsymbol { S } _ { b }$ 足够大且 $\boldsymbol { S } _ { v }$ 足够小，其优化目标为

$$
a r g m a x J ( w ) = \frac { W ^ { T } S _ { b } W } { W ^ { T } S _ { w } W }
$$

采用拉格朗日乘子法，即可求解出最优的投影向量：$\pmb { w } ^ { * } = S _ { w } ^ { - I } \left( \pmb { \mu } _ { 0 } - \pmb { \mu } _ { I } \right)$ 。在实际的运动想象模式识别中，本文将学习到的跨域特征投影至最优方向，并采用LDA方法进行模式识别。

# 3.3运动想象EEG信号跨域特征学习方法流程

本文提出的基于MI-BCI的EEG信号跨域特征学习方法流程图如图1所示。该方法步骤如下：

(1）根据不同个体域的EEG样本分布情况，采用trial-and-error方法选择最优的协方差距离度量方法；随后，将不同个体域的EEG信号样本对齐至单位阵，使得个体域的EEG信号样本分布更相似；

(2）针对每个域对齐后的EEG信号样本提取CSP特征，在此基础上将其中某个被试者的CSP特征作为目标域，余下所有被试者的CSP特征作为源域，在源域和目标域间执行领域自适应方法，使得CSP特征之间的MMD最小化；具体来看，从TCA，JDA，TJM和BDA方法中选择最优的领域自适应方法，从多个源域中学习到最适合目标域的跨域特征。

(3）采用LDA 模型用于跨域特征分类，完成运动想象EEG 信号的模式识别。

# 4 实验与结果分析

# 4.1 实验初始化

为了验证本文提出的跨域特征学习方法的可行性与有效性，本文选择2008BCICompetitionIV中的两个公开的MI-BCI数据集[36.37]，MI1和MI2a。该两个数据集基本实验范式如图2所示：被试者舒服坐在椅子上，面对屏幕开始实验。$\scriptstyle 1 = 0$ 时，屏幕出现十字架集中注意力，伴随短暂提示音开始本次实验； $\scriptstyle \mathbf { t } = 2$ 时，屏幕将随机出现指导运动想象方向的箭头，被试者根据箭头指导的方向进行运动想象任务； $\scriptstyle 1 = 6$ 时，被试者结束运动想象且箭头消失；此后，短暂停顿休息后进入下一次实验。

数据集MI1：该数据集采集了7名健康被试者运动想象的EEG数据。采集到的数据包含59个通道，采样率为 $1 0 0 \mathrm { H z }$ 0本文实验从三个运动想象任务中提取左手和右手类别，分别标记为Class1和Class2，每个用户的每个类别有100个样本。

数据集 $\mathbf { M I } \ 2 \mathbf { a }$ ：该数据集采集了9名健康被试者运动想象的EEG数据。采集到的数据包含22个通道，采样率为

$2 5 0 \mathrm { { H z } }$ 。本文实验从四个运动想象任务中提取左手和右手类别，分别标记为Class1和Class2，每个用户的每个类别有72个样本。

![](images/39fda1d788b1ec8bac975a644bdf83cdb97a6201db49879c79eaf0a4a80fed9b.jpg)  
Fig.1Cross-domain feature learning flow chart

在跨域特征学习和模式识别实验中，首先在Matlab 上对两个数据集进行预处理，将运动想象提示箭头后的[0.5,3.51秒之间的采样点数作为一个运动想象样本。因此，MI1数据集每个样本采样时间点数为300；MI2a数据集每个样本采样时间点数为750。

实验硬件配置为Intel(R)Core(TM)i7-9700 CPU $@$ $3 . 0 0 \mathrm { G H z }$ ，8GB内存，运行64位Windows10系统、MatlabR2017b以及Python3.7.4。协方差矩阵中心对齐方法采用代码：https://github.com/hehe91/EA，领域自适应方法代码则使用代码：https:// github.com/ jindongwang/ transferlearning／tree/master/code。针对JDA、BDA和TJM的迭代过程中，都将迭代次数设置为10，其他参数则针对实际数据集的测试结果设置最佳参数。本文取所有迭代结果中的最佳性能作为最终的分类结果。

![](images/d11dcbf2cf1b9bffe1adc80f7db549aa2d4971b7cf331b45a121e03bca759893.jpg)  
图1跨域特征学习流程图  
图2运行想象范式流程  
Fig.2The flow chart of motor imagery paradigm

# 4.2协方差矩阵中心对齐方法实验结果分析

为了验证不同均值度量计算的协方差矩阵中心对齐方法在不同数据集上的对齐效果，分别记录数据集上平均准确率最高的均值度量，以及每个被试者域最佳的均值度量，在后续实验中分别验证两种情况下的最佳跨域特征学习结果。表1和表2是分别给出了数据集MI1和MI2a的实验结果。其中，每行表示使用8种不同均值对应的同一被试者的分类准确率，每列表示不同被试者在同一均值计算的协方差矩阵中心对齐下的分类准确率，最后一行为平均结果。从表1和表2 的实验结果中可以看出：

针对MI1数据集，分类效果最好的是欧式均值,效果最坏的是KL散度均值。由于调和平均值对单个低于平均值的值特别敏感，而本质上KL散度均值是算数和调和均值之间的几何平均值，在KL散度均值下第1个被试者和第4个被试者的分类结果表现都很差，导致对整个平均效果变差。在MI2a数据集下的测试结果中，分类效果最好的是KL散度均值，分类效果最坏的是调和均值。与MI1数据集的分析过程相同，第2个被试者在调和均值下的分类准确率仅有$50 . 6 9 \%$ ，是8种均值下表现最差的，因此导致最后的平均结果较差。在KL散度均值下表现最差的分类准确率是 $54 . 8 6 \%$ 5比其他均值下的最差表现都要好，单个最差值对KL散度均值的影响最小，因此KL散度均值的效果最好。

表1MI1数据集的不同均值下的分类准确率

Tab.1Classification accuracy under different mean values ofMI1 datase   

<html><body><table><tr><td></td><td>mean</td><td>riemann</td><td>logeuclid logdet</td><td></td><td>wasserstein</td><td>ale</td><td>harmonic</td><td>kullback_sym</td></tr><tr><td>1</td><td>77.5</td><td>71.5</td><td>68</td><td>71.5</td><td>73.5</td><td>75.5</td><td>64</td><td>67</td></tr><tr><td>2</td><td>77.5</td><td>74.5</td><td>76.5</td><td>73.5</td><td>80.5</td><td>74</td><td>71.5</td><td>73</td></tr><tr><td>3</td><td>75.5</td><td>71.5</td><td>70.5</td><td>74</td><td>70</td><td>73</td><td>71</td><td>70</td></tr><tr><td>4</td><td>75</td><td>77.5</td><td>80</td><td>81.5</td><td>82.5</td><td>84</td><td>81</td><td>68</td></tr><tr><td>5</td><td>92.5</td><td>90</td><td>90.5</td><td>92</td><td>91.5</td><td>89</td><td>91.5</td><td>85.5</td></tr><tr><td>6</td><td>75.5</td><td>77</td><td>76.5</td><td>77</td><td>73.5</td><td>77.5</td><td>75</td><td>74.5</td></tr><tr><td>7</td><td>85</td><td>86.5</td><td>84.5</td><td>86</td><td>85</td><td>82.5</td><td>85</td><td>86.5</td></tr><tr><td>Acc 79.79</td><td></td><td>78.36</td><td>78.07</td><td>79.36</td><td>79.5</td><td>79.36</td><td>77</td><td>74.93</td></tr></table></body></html>

表2MI2a数据集的不同均值下的分类准确率

Tab.2Classification accuracy under different mean values ofMI 2a dataset   

<html><body><table><tr><td></td><td>mean</td><td>riemann</td><td>logeuclid logdet</td><td></td><td>wasserstein</td><td>ale</td><td>harmonic</td><td>kullback_sym</td></tr><tr><td>1</td><td>87.5</td><td>84.72</td><td>84.03</td><td>84.03</td><td>84.72</td><td>83.33</td><td>81.94</td><td>85.42</td></tr><tr><td>2</td><td>56.25</td><td>52.78</td><td>53.47</td><td>54.17</td><td>54.17</td><td>53.47</td><td>50.69</td><td>58.33</td></tr><tr><td>3</td><td>98.61</td><td>97.92</td><td>97.92</td><td>97.92</td><td>97.92</td><td>97.92</td><td>96.53</td><td>97.92</td></tr><tr><td>4</td><td>73.61</td><td>69.44</td><td>70.14</td><td>69.44</td><td>70.83</td><td>70.14</td><td>70.14</td><td>72.22</td></tr><tr><td>5</td><td>50</td><td>54.17</td><td>54.86</td><td>56.25</td><td>51.39</td><td>54.86</td><td>56.94</td><td>54.86</td></tr><tr><td>6</td><td>64.58</td><td>65.97</td><td>66.67</td><td>65.97</td><td>65.97</td><td>65.28</td><td>65.97</td><td>65.28</td></tr><tr><td>7</td><td>68.75</td><td>69.44</td><td>69.44</td><td>70.14</td><td>68.75</td><td>68.75</td><td>70.14</td><td>68.06</td></tr><tr><td>8</td><td>89.58</td><td>90.97</td><td>90.28</td><td>90.28</td><td>90.97</td><td>91.67</td><td>91.67</td><td>89.58</td></tr><tr><td>9</td><td>72.92</td><td>75.69</td><td>75.69</td><td>75.69</td><td>76.39</td><td>77.78</td><td>76.39</td><td>75.69</td></tr><tr><td>Acc 73.53</td><td></td><td>73.46</td><td>73.61</td><td>73.77</td><td>73.46</td><td>73.69</td><td>73.38</td><td>74.15</td></tr></table></body></html>

# 4.3跨域特征学习实验结果分析

针对不同域对齐后的EEG样本，分别提取CSP特征，并使用LDA获得分类识别准确率。由于样本数量较少，分别对每一个数据集选用交叉验证法，即采用留一法依次选出目标域样本和源域样本，每轮实验依次选择一个被试者的样本集为目标域，余下的样本集为源域，每一个被试者都会被选择为目标域，最终使用分类的平均正确率作为实验结果的度量。

# 4.3.1实验结果

在上文的协方差矩阵中心对齐方法实验结果基础上，本文分别在两个数据集上继续测试样本对齐对领域自适应特征学习分类性能的提升效果。本节单独对四种领域自适应方法进行实验，以及在样本对齐后提取的CSP特征基础上，分别进行TCA、BDA、JDA、TJM四种领域自适应方法和协方差矩阵中心对齐的对比实验。为了更加明显的分析在协方差矩阵中心对齐方法下四种领域自适应方法的优劣，所有对比均在欧式均值对齐获取到的CSP特征上进行，表3和表4分别给出了两个数据集在不同特征学习方法上的实验结果。从表3和表4中的结果可以看出，在平均分类准确率方面：

(1）在四种领域自适应特征学习方法的对比下，跨域特征学习的准确率高于领域自适应特征学习的准确率，实验结果充分说明协方差矩阵中心对齐方法对领域自适应特征学习方法有着至关重要的作用以及对降低个体分布差异的有效性。

(2）不管跨域特征学习方法选择哪种核函数，本文可以发现在MI1的数据集上TJM的方法最优，在MI2a的数据集上JDA的方法最优。所以在欧式距离样本对齐基础上，TJM方法更适合MI1数据集的样本分布，JDA方法更适合MI2a数据集的样本分布。

(3）与缺少样本对齐的领域自适应特征学习方法相比，在协方差矩阵中心对齐方法的预处理条件下，四种领域自适应特征学习方法均得到了提升。其中，在MI1数据集上采用 $\operatorname { E A + T J M }$ 方法提高了 $1 4 . 3 5 \ \%$ ，在MI2a数据集上采用$\mathrm { E A + J D A }$ 方法提高了 $3 . 0 9 \%$ 。

表3MI1数据集在不同方法下的平均准确率

Tab.3Average accuracy of MI1 dataset at different methods   

<html><body><table><tr><td rowspan="2">Kernel-</td><td colspan="2">样本对齐(%) 领域自适应(%)</td><td colspan="3">跨域特征学习(%)</td></tr><tr><td>EA</td><td>TCA BDA JDA TJM EA+TCA</td><td>EA+BDA</td><td>EA+JDA</td><td>EA+TJM</td></tr><tr><td>RBF</td><td></td><td>66.2966.14 67.5 68.86</td><td>81.21 81.00</td><td>82.43</td><td>83.21</td></tr><tr><td>Linear</td><td></td><td>66.5 65.21 67.71 67.93</td><td>81.21 80.35</td><td>82.28</td><td>82.93</td></tr><tr><td>Primal</td><td>79.79</td><td>66.3666.71 67.36 68.21</td><td>81.57 79.64</td><td>83.00</td><td>83.14</td></tr><tr><td>Sam</td><td></td><td>66.7166.7167.43 68.79</td><td>81.07 81.21</td><td>82.5</td><td>82.79</td></tr></table></body></html>

表4MI2a数据集在不同方法下的平均准确率

Tab.4Average accuracy of MI 2a dataset at different method:   

<html><body><table><tr><td rowspan="2">Kernel</td><td>样本对齐(%)</td><td>领域自适应(%)</td><td colspan="4">跨域特征学习(%)</td></tr><tr><td>EA</td><td>TCA BDA JDA TJMEA+TCA EA+BDA</td><td></td><td></td><td>EA+JDA EA+TJM</td><td></td></tr><tr><td>RBF</td><td></td><td>72.00 72.92 73.61 74.07</td><td>73.99</td><td>74.46</td><td>76.70</td><td>76.47</td></tr><tr><td>Linear</td><td>73.53</td><td>72.53 73.00 73.61 73.69</td><td>74.69</td><td>74.86</td><td>76.16</td><td>75.38</td></tr><tr><td>Primal</td><td></td><td>72.2273.00 73.2373.69</td><td>74.31</td><td>74.46</td><td>75.62</td><td>76.00</td></tr><tr><td>Sam</td><td></td><td>72.00 72.92 74.15 74.31</td><td>74.38</td><td>74.77</td><td>76.08</td><td>76.62</td></tr></table></body></html>

从两个数据集总体跨域特征学习的结果可以看出，本文提出方法在每个数据集上均取得了比单一跨域特征学习角度更好的运动想象模式识别性能。为了探索单个个体域特征学习的最佳方法，本文针对每个个体域选择最优的样本对齐度量方法和CSP特征跨域特征方法，通过实验获得个体最优的运动想象模式识别结果。表5和表6分别给出了两个数据集个体域最优运动想象识别性能的方法。

表5MI1数据集每个个体域最优跨域特学习准确率及方法

Tab.5Optimal accuracy of each subject in MI 1 dataset for the cross-subject feature learning method   

<html><body><table><tr><td>subjects</td><td>均值对齐</td><td></td><td>准确率/%特征域迁移准确率/%</td><td></td><td>最优参数</td><td>运行时间</td></tr><tr><td>1</td><td>mean</td><td>77.5</td><td>BDA</td><td>79</td><td>Dim=5,lambda=0.7</td><td>3.76s</td></tr><tr><td>2</td><td>wasserstein</td><td>80.5</td><td>JDA/TJM</td><td>84.5</td><td>Dim=2,lambda=0.7</td><td>3.60s</td></tr><tr><td>3</td><td>mean</td><td>75.5</td><td>TJM</td><td>79</td><td>Dim=1,lambda=0.5</td><td>3.63s</td></tr><tr><td>4</td><td>ale</td><td>84</td><td>BDA/JDA</td><td>86.5</td><td>Dim=6,lambda=0.4</td><td>3.73s</td></tr><tr><td>5</td><td>mean</td><td>92.5</td><td>TJM</td><td>95</td><td>Dim=1,lambda=0.5</td><td>3.81s</td></tr><tr><td>6</td><td>ale</td><td>77.5</td><td>BDA</td><td>78.5</td><td>Dim=6,lambda=0.4</td><td>3.60s</td></tr><tr><td>7</td><td>kullback_sym/ riemann</td><td>86.5</td><td>TJM</td><td>88.5</td><td>Dim=2,lambda=0.1</td><td>3.51s</td></tr></table></body></html>

表6 $\mathrm { M I } 2 \mathrm { a }$ 数据集每个个体域最优跨域特学习准确率及方法 Tab.6Optimal accuracy of each subject in MI 2a dataset for the cross-subject feature learning method   

<html><body><table><tr><td>subjects</td><td>均值对齐</td><td>准确率/%特征域迁移准确率/%</td><td></td><td></td><td>最优参数</td><td>运行时间</td></tr><tr><td>1</td><td>mean</td><td>87.5</td><td>JDA//TJM</td><td>92.36</td><td>Dim=1,lambda=0.5</td><td>3.0s</td></tr><tr><td>2</td><td>kullback_sym</td><td>58.33</td><td>JDA</td><td>60.42</td><td>Dim=4,lambda=0.1</td><td>2.96s</td></tr><tr><td>3</td><td>mean</td><td>98.61</td><td>JDA</td><td>99.31</td><td>Dim=1,lambda=0.4</td><td>2.93s</td></tr><tr><td>4</td><td>mean</td><td>73.61</td><td>JDA/TJM</td><td>77.78</td><td>Dim=2,lambda=0.1</td><td>2.78s</td></tr><tr><td>5</td><td>harmonic</td><td>56.94</td><td>JDA</td><td>59.03</td><td>Dim=3,lambda=0.9</td><td>3.1s</td></tr><tr><td>6</td><td>logeuclid</td><td>66.67</td><td>TJM</td><td>72.22</td><td>Dim=3,lambda=0.1</td><td>2.74s</td></tr><tr><td>7</td><td>loget/harmonic</td><td>70.14</td><td>TJM</td><td>70.83</td><td>Dim=1,lambda=0.2</td><td>2.84s</td></tr><tr><td>8</td><td>ale/harmonic</td><td>91.67</td><td>JDA/TJM</td><td>95.14</td><td>Dim=3,lambda=0.2</td><td>2.75s</td></tr><tr><td>9</td><td>ale</td><td>77.78</td><td>JDA</td><td>84.72</td><td>Dim=2,lambda=0.1</td><td>2.89s</td></tr></table></body></html>

从表5和表6中的结果中可以看出：

(1）经过最优度量方式对齐后的样本，其CSP特征能够在最优域自适应方法和参数下获得再次提升，平均提升幅度为 $2 . 4 3 \%$ 和 $3 . 4 0 \%$ ·

(2）针对不同数据集的不同个体域，样本对齐的度量方式对最终识别准确率有较大影响，花费一定时间代价获取最优的识别准确率能够极大的提升模式识别性能；

(3）实验结果充分说明，本文提出的方法对个体分类性能的提升，面向个体域数据分布差异灵活选择合适的方法，随着算法的发展在实际应用可保证高性能和鲁棒性。

为了对比分析本文提出算法在模式识别性能上的提升，本文针对两个数据集中每个被试者对比如下种情况的运动想象识别准确率：(1)非跨域的识别方法( $\mathrm { C S P + L D A } ,$ ；(2)不经过样本对齐而直接使用领域自适应方法 $( \mathrm { C S P + D A + L D A } )$ ；(3)经过最优均值度量样本对齐后的识别方法 $\mathrm { ( E A + C S P + L D A ) }$ ：(4)本文提出的最优跨域特学习方法 $\mathrm { ( E A + C S P + D A + L D A ) }$ 。图3分别给出了两个数据集在上述四种情况下的运动想象识别准确率对比。从图3中的结果可以看出，针对每个个体域的最优跨域特征学习方法的识别准确率均高于对比的三个方法。此外，最优度量样本对齐效果基本由于经典域自适应方法。对比非跨域识别方法和本文提出的最优跨域特征学习方法，运动想象识别准确率得到了明显提升。例如MI1数据集的 subject4，最优跨域特征学习方法比非跨域识别提升了$3 6 . 5 \%$ 。

同时，如图4所示，本文还分析了在样本对齐下参数dim对四种域自适应特征学习方法的影响。从图4的结果中可以看出，参数dim 的选择对实验影响较大。当dim 较小时，所能承载的可迁移CSP特征较少，因此造成了识别准确率的降低。随着dim的提升，总体识别准确率先上升后下降，在 $\mathrm { d i m } { = } 4$ 时获得了最佳的分类性能。

随后，本文联合跨域特征学习的实验，选择rbf核函数，验证在它们共同作用下对分类性能的影响，MI1和MI2a数据集上的实验结果分别如图5所示。从图中本文可以看出：

(1)从分类整体情况可以看出，MI1数据集使用欧式均值作为距离度量的领域自适应方法效果最佳，使用KL散度均值作为距离度量的效果最差。MI2a数据集使用对数欧式均值作为距离度量的效果比较好，对比协方差矩阵中心对齐方法获得的分类准确率都有了一定的提升，使用调和均值的效果整体比较差。

(2)MI1数据集中经过样本对齐的四种领域自适应方法中效果最好的是TJM，MI2a数据集中效果最好的是JDA。由此可看出，采用欧式均值和TJM领域自适应的特征学习方法更适合MI1的样本分布，采用对数欧式均值和JDA域自适应的特征学习方法更适用于MI2a数据集的样本分布。

![](images/f7ca012a83354617af6e175c032fc00cdb6926d3e1d53ff5110add37efb95f08.jpg)  
图3四种不同情况下每个被试者的运动想象识别准确率对比

Fig.3ComparisonofMIrecognition acuracyofeach subject under fourdifferent situationsonMI1and MI2a datasets

![](images/6d2ebe0eee27c3dcdb53c9d7df0a6a8c3edb7ffb29e982720a7c3a5543dabe7b.jpg)  
图4MI1和MI2a数据集在不同dim值下四种领域自适应方法准确率对比

![](images/1ceaed71c14bcd89593873f5f8644b3ca9ec861ffca3a5073387d5b3ddc14d79.jpg)  
Fig.4Comparison of accuracyof four domain adaptive methods in MIl and MI 2a data sets under different dim values   
图5MI1和MI2a在不同均值计算下四种领域自适应方法对比

Fig.5Comparison offour domainadaptive methods for MI and MI2adataset under different mean calculations

在实验采用的四种领域自适应方法中，TCA方法为无监督方式且不需要多次迭代，而BDA、JDA和TJM三种算法均需迭代获得伪标签以及求解系数矩阵。因此，图6给出了不同迭代次数BDA、JDA和TJM三种方法在不同核函数下的迭代准确率对比。从图中的结果可以看出，算法的效果随着迭代的次数变得更好。此外，虽然迭代对比实验中将最大迭代次数设置为10次，实际上绝大多数情况仅需5次迭代即可获得与最终迭代下匹配的平均准确率。在实际脑机接口应用场景，本文采用提出的跨域特征学习方法，仅需少量的迭代次数即可获得较好的识别准确率。

# 4.3.2特征可视化

为了更直观的观察跨域特征学习对EEG 样本和特征的变化，本文对四种领域自适应特征学习方法做了可视化处理。本文选择展示MI1数据集中第4个被试者以及MI2a数据集中第8个被试者的EEG信号跨域特征学习方法的可视化结果。可视化采用t-SNE，将特征投影至2维空间并展示，图7和图8给出了数据可视化结果，图中的红色和蓝色圆点分别代表两个不同类别。

从图7中可以看出，进行样本对齐之后，红色圆点和蓝色三角相互之间交错比较多，说明分类的效果不是很好，但采用经过样本对齐的领域自适应方法后，红色圆点和蓝色三角的间隔变小了，交错也少了，能比较明显的区分出样本的两个类别。

从图8本文可以看出，在样本对齐之前，红色圆点和蓝色圆点也有比较好的分类效果，但经过样本对齐的预处理后，图中红色圆点和蓝色三角的交错点明显少了，在采用跨域特征学习方法后，红色圆点和蓝色蓝点的区分度也有了一定程度的提升。

从上面的结果可以看出：协方差矩阵中心对齐方法可将不同类别的数据分布的边缘分布差异减小，保证分类器不受不同被试者 EEG 信号样本的边缘分布影响。此外，TCA 方法可在协方差矩阵中心对齐方法基础上，将相同被试者不同类别信号的边缘分布差异减小，而JDA和BDA方法则不但减小边缘分布，更减小了标签参与的条件分布差异，因此能够更好的提升平均识别准确率。TJM方法保证了特征选择的稀疏性，因此在可视化的结果上，可以被选择后的特征具有稀疏性，且让不同类别的特征分离的差异更大。

![](images/99fca7d54555cd521bd5fae09f79224d4b1a6d8407200b31f0e7589d0cf5c0ac.jpg)  
图6MI1和MI2a数据集中不同迭代次数的准确率变化图 Fig.6The diagram ofaccuracy variation under different iterations

![](images/bad408ca67bf184fee3bc937ed759bdfce81dae86038e77b9de4b1b2993a54d1.jpg)  
图7MI1数据集中第4个被试者经过T-SNE的可视化结果

Fig.7MI1 dataset represents the visualization results of the fourth subject through T-SNE

![](images/6cb831bf0236f4a3859048fadadf0a77956ad54b65ec10a7c390ec3ba1934787.jpg)  
图8MI2a数据集中第8个被试者经过T-SNE的可视化结果  
Fig.8MI 2a dataset represents the visualization results of the fourth subject through T-SNE

# 4.4时间复杂度分析

图9给出了本文方法的运行时间复杂度对比结果。其中，图9(a)展示了不同均值度量平均运行时间。从该柱状图的结果可以观察到，两个MI数据集中在欧式均值度量下的运行时间最短，而基于AJD的对数欧式均值运行时间最长，前者快2\~10倍。此外，MI1数据集数据量更大，运行时间更久。

![](images/bf014b4d68cf50b08f77894725e901c07860cd09c8c3fbf0dac98cad66a2131f.jpg)

![](images/a6dee6a9c2e8605197e580e52da6de96b588fe64739ca1a7e04f172c2dc57758.jpg)

图9八种均值和四种域自适应方法的运行时间对比 Fig.9Running time comparisonof eightmean and four domain adaptive methods

以欧式均值度量为基础，图9 (b)(c)给出了不同域自适应方法运行时间。在BDA、JDA和TJM三种算法中迭代次数为5次时已经接近最优解，从图8(b)(c)中结果可以看出，TCA的运行时间最短，相对而言BDA、JDA和TJM的运行时间相差不大，且均在1.5 秒以内。因此，所提出对脑电信号识别方法的响应时间足以应对运动想象刺激范式的流程，可应用于在线脑机接口。上述结果表明，最优跨域特征学习方法的平均时间复杂度在可接受范围内，同时在实际的MI-BCI应用中使用跨域特征学习方法时，需根据实际情况同时考虑准确率和时间复杂度，选择适合场景的协方差中心均值度量及领域自适应方法。

目前，现有脑机接口系统(如外骨骼辅助康复)遭遇新被试者时，往往采集大量样本训练模式识别模型。从图2可看出，单个样本至少需要4秒时间，且通常需要200-300个样本才能稳定识别。采用本文提出的跨域特征学习方法，新的被试者仅需采集少量样本(100 个以内)，即可通过跨域特征学习使用已有使用者的脑电信号样本集，且随着使用者增多，可使用的脑电信号样本集也越多，对模式识别的效果也越好。此外，新的被试者所采集少量样本的最优选择，即可使用现有样本集获得更高的模式识别性能，其时间代价在可接受范围内。

# 5 结束语

针对运动想象个体域EEG信号获取代价高且特征分布差异大的特性，本文提出了一种运动想象脑电信号的跨域特征学习方法，用于提升跨个体域脑电信号模式识别性能。该方法首先选择最优的协方差距离度量方法，对齐各域样本集并提取CSP特征。其次，在CSP特征基础上，选择合适的领域自适应方法，从多源域中学习出最适合目标域的跨域特征，最后采用LDA分类完成模式识别任务。实验结果表明所提出的方法明显可提升模式识别准确率。跨域特征学习能够极大的提升BCI应用中的样本数量和质量，提升控制外部设备的性能，然而现有方法存在一个缺点：采用离线方式进行。在实际应用中，源域样本或许能够长期积攒，但是目标域样本不断产生，无法直接计算协方差矩阵中心以及CSP特征。今后的工作集中在：探索迭代式协方差计算方法，设计增量迭代式的跨域特征学习方法，并将迭代式跨域特征学习应用至在线MI-BCI中。

# 参考文献：

[1]Lance B J,Kerick S E,Ries A J,et al.Brain-computer interface technologies in the coming decades [J].Proceedings of The IEEE,2012, 100 (1): 1585-1599.   
[2]Wolpaw JR,Birbaumer N,Mcfarland D J,et al.Brain-computer Interfaces for Communication and Control[J]. Clinical Neurophysiology, 2002,113 (6): 767-791.   
[3]周鹏．基于运动想象的脑机接口的研究[D]．天津：天津大学,2007.   
[4]PfurtschellerG,Müeller-Putz,Gernot R,et al.Rehabilitation with BrainComputer Interface Systems [J].COMPUTER,2008,41 (10): 58-65.   
[5]Hashimoto Y,Kakui T, Ushiba J,et al.Development of Rehabilitation System with Brain-Computer Interface for Subacute Stroke Patients [C]// Proc of the IEEE International Conference on Systems Man and Cybernetics Conference Proceedings.Miyazaki: IEEE Press,2018:51- 56.   
[6]Kasashima-Shindo Y,Fujiwara T,Ushiba J,et al.Brain-Computer Interface Training Combined with Transcranial Direct Current Stimulation in Patients with Chronic Severe Hemiparesis:Proof of Concept Study[J].Journal ofRehabilitation Medicine,2015,47(4): 318- 324.   
[7]Blankertz B,Tomioka R,Lemm S,et al. Optimizing Spatial Filters for Robust EEG Single-Trial Analysis [J]. IEEE Signal Processing Magazine, 2008,25 (1): 41-56.   
[8]He He,Wu Dongrui. Transfer Learning Enhanced Common Spatial Pattern Filtering for Brain Computer Interfaces (BCIS):Overview and A New Approach [C]// Proc of the 24th International Conference on Neural Information Processing. Guangzhou: ICONIP Press,2017: 811-821.   
[9]庄福振，罗平，何清，等．迁移学习研究进展[J].软件学报，2015, 26(1):26-39.(Zhuang Fuzhen,Luo Ping,He Qing,et al. Survey on Transfer LearningResearch [J].Journal of Software,2015,26(1):26-39.)   
[10]Pan SJ,Tsang IW,Kwok JT,et al.Domain Adaptation via Transfer Component Analysis [C]// Proc of the 21st International Joint Conference on Artificial Intelligence.Pasadena:IJCAI Press,2009: 1187-1192. Learning with Joint Distribution Adaptation [C]// Proc of the IEEE Intermational Conferenceon Computer Vision. Sydney: IEEEPres,2013: 2200-2207.   
[12] Long Mingsheng, Wang Jianmin, Ding Guiguang,et al. Transfer Joint Matching for Unsupervised Domain Adaptation [C]// Proc of the 27th IEEE Conference on Computer Vision and Pattern Recognition. Columbus:IEEE Press,2014:1410-1417.   
[13] Wang Jindong,Chen Yiqiang,Hao Shuji,et al. Balanced Distribution Adaptation for Transfer Learning [Cl// Proc of the 17th IEEE International Conference on Data Mining. New Orleans: IEEE Press, 2017: 1129-1134.   
[14]李晶晶，孟利超，张可，等．领域自适应研究综述[J].计算机工程, 2021,47(06):1-13.(Li Jingjing,Meng Lichao,Zhang Ke,et al.A Review of Domain Adaptation Research [J]. Computer Engineering, 2021,47 (06): 1-13.)   
[15]田磊，唐永强，张文生．两阶段领域自适应学习[J].模式识别与人 工智能，2019,32(09):773-784.(Tian Lei,Tang Longqiang,Zhang Wensheng.Two-Stage Domain Adaptive Learning [J]. Pattern Recognition and Artificial Inteligence,2019,32 (09):773-784.)   
[16] Dai Mengxi,Zheng Dezhi, Liu Shucong,et al. Transfer Kernel Common Spatial PatternsforMotor Imagery Brain-Computer Interface Classification [J/OL]. Computational and Mathematical Methods in Medicine,2018,2018 (9): Article ID 9871603.(2018-04-17) [2022-01- 15]. https://doi.org/10.1155/2018/9871603.   
[17] Albalawi H, Song Xiaomu.A Study of Kernel Csp-based Motor Imagery Brain Computer Interface Classification [C]// Proc of the IEEE SignalProcessing in Medicine and Biology Symposium,New York: IEEE Press,2012: 1-4.   
[18] Long Mingsheng,Wang Jianmin, Sun Jiaguang,et al. Domain Invariant Transfer Kernel Learning [J].IEEE Trans on Knowledge and Data Engineering,2015,27 (6): 1519-1532.   
[19] Jayaram V,Alamgir m,Altun Y,et al.Transfer Learning in BrainComputer Interfaces [J]. IEEE Computational Intelligence Magazine, 2015,11 (1): 20-31.   
[20] Azab AM,Mihaylova L,Ang KK,et al. Weighted Transfer Learning for Improving Motor Imagery-Based Brain-Computer Interface [J].IEEE Trans on Neural Systems and Rehabilitation Engineering,2O19,27 (7): 1352-1359.   
[21] Hossain I,Khosravi A,Hettiarachchi I,et al.Multiclass Informative Instance Transfer Learning Framework for Motor Imagery-Based BrainComputer Interface [J].Computational Intelligence and Neuroscience, 2018,2018 (9):Article ID 6323414.(2018-02-22) [2022-01-15]. https://doi.org/10.1155/2018/6323414.   
[22] Zanini P,Congedo M, Jutten C,et al. Transfer Learning: A Riemannian Geometry Framework with Applications to Brain-Computer Interfaces [J]. IEEE Trans Biomed Eng,2017,65 (5): 1107-1116.   
[23] Barachant A,bonnet S,Congedo M,et al.Multiclass brain-computer interface classification by Riemannian geometry [J]. IEEE Trans on Biomedical Engineering,2012,59 (4): 920-928.   
[24] Yair O,Dietrich F,Talmon R,et al.Domain Adaptation with Optimal Transport on the Manifold of SPD matrices [J]. IEEE Trans on Signal Processing,2019,67(7): 1797-1811.   
[25] He He,Wu Dongrui. Transfer Learning for Brain-Computer Interfaces: A Euclidean Space Data Alignment Approach [J].IEEE Trans on Biomedical Engineering,2020,67 (2): 399-410.   
[26] Rodrigues PLC,Jutten C,Congedo M. Riemannian Procrustes Analysis: Transfer Learning for Brain-Computer Interfaces [J].IEEE Trans on Bio Medical Engineering,2018,66 (8): 2390-2401.   
[27] Zhang Wen,Wu Dongrui. Manifold Embedded Knowledge Transfer for Brain-Computer Interfaces [J].IEEE Trans on Neural Systems and Rehabilitation Engineering,2020,28 (5): 1117-1127.   
[28] Singh A,Lal S,Guesgen H W. Small Sample Motor Imagery Classification Using Regularized Riemannian Features [J]. IEEE Access, 2019, 7 (1): 46858-46869.   
[29] Wu Dongrui, Xu Yifan,Lu Bao-liang. Transfer Learning for EEG-Based Brain-Computer Interfaces: A Review of Progress Made Since 2016 [J]. IEEE Trans on Cognitive and Developmental Systems,2020,2020 (16): Article ID9134411.(2020-07-07)[2022-01-15]. https://eeexplore.ieee. org/document/9134411.   
[30] Wu Hao，NiuYi,LiFu，etal.A Paralel Multiscale Filter Bank Convolutional Neural Networks for Motor Imagery EEG Classification [J].Frontiers in Neuroscience,2019,13(1): 1-9.   
[31] Wang Peitao,Lu Jun,Zhang Bin,et al.A Review on Transfer Learning for Brain-Computer Interface Classification [C]// Proc of the 5th International Conference on Information Science and Technology. Changsha:ICIST Press,2015:315-322.   
[32] Ren Jiangtao,Liang Zhou,Hu Shaofeng.Multiple Kernel Learning Improved by MMD [C]// Proc of the 6th International Conference on Advanced Data Mining and Applications. Chongqing:ADMA Press, 2010: 63-74.   
[33]赵鹏，吴国琴，刘慧婷，等．基于特征联合概率分布和实例的迁移学 习算法[J].模式识别与人工智能,2016,29(08):717-724.(Zhao Peng, Wu Guoqin,Liu Huiting. Transfer Learning Algorithm Based on Feature Joint Probability Distribution and Instance [J].Pattern Recognition and Artificial Intelligence,16,29(08):-74.)   
[34] Mishuhina V, Jiang Xudong.Feature Weighting andRegularization of Common Spatial Patterns in EEG-Based Motor Imagery BCI [J]. IEEE Signal Processing Letters,2018,25 (6): 783-787.   
[35] Subasi A, Gursoy MI. EEG signal classification using PCA, ICA,LDA and support vector machines [J].Expert Systems with Applications,2010, 37 (12): 8659-8666.   
[36] Tangermann M,Muller KR,Aertsen A,et al. Review of the BCI Competition IV[J]. Frontiers of Neuroscience,2012,6(1) .(2012-07- 13）[2022-01-15].hps://ww.frontiersi.org/articles/10.3389/fns. 2012. 00055/full   
[37] Ang KK,Chin ZY,Wang CC,et al.Filter Bank Common Spatial Pattern Algorithm on BCI Competition IV Datasets 2a and 2b[J].Frontiers of Neuroscience,2012,6(1).(2012-03-29)[2022-01-15]. https: //www frontiersin.org/articles/10.3389/fnins.2012.000 39