# 基于移不变字典学习和稀疏编码的滚动轴承故障识别算法

曲建岭1，余 路1，高 峰1，田沿平1，李俨2(1．海军航空大学青岛校区，山东 青岛 266041;2．西北工业大学 自动化学院，西安 710072)

摘要：针对现有旋转机械故障识别算法过度依赖专家先验知识的问题，提出了一种基于移不变字典学习和稀疏编码(SIDL-SC）的自适应故障识别算法。首先，将不同故障状态下的振动信号进行分段和平滑预处理以降低数据处理复杂度，接着将加入自适应惩罚因子的移不变字典学习算法用于提取不同故障状态下的移不变基函数；然后，利用高效的特征符号搜索算法求解待识别信号在不同基函数下的稀疏系数以实现对待识别信号的重构；最后，以重构残差作为对该信号故障状态识别的判断依据。滚动轴承振动数据库和实测航空发动机振动信号的实验结果表明，该算法相较于现有算法具有更高的故障识别准确率，在实际中具有较强的可行性。

关键词：移不变字典学习；稀疏编码；特征符号搜索；振动信号；故障识别 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.07.0687

# Fault recognition algorithm for rolling bearings based on shift invariant dictionary learning and sparse coding

Qu Jianling1, Yu Lu1,Gao Feng1, Tian Yanping1,Li Yan² (1.Qingdao BranchofvalAviationUniversityingdaoSandong26641,China;2.hoolofAutomationNrthste Polytechnical University,Xi'an 710072,China)

Abstract: According to currnt algorithms for rotating machines largely depending on expert prior knowledge,the paper proposedan adaptive fault recognition algorithm based onshift invariant dictionary learning and sparse coding.Firstly,it segmentedandsmoothedvibration signals todecrease thecomplexity.Then,itused shift invariantdictionary learing with adaptivepenaltyfactortolearnshiftinvariantbases indiferentfaultstates.Afterthat,itusedaneficient sparsecoeficient solver calledFeature Sign Searchforreconstructing signaltoberecognized.Lastly,residual wasanevidence todetermining fault statethe signal belonging to.Intheexperimentsofrolingbearing datasetsand vibrationsignalsofrealaero-engine demonstrate its higher accuracy than up-to-date algorithms and feasibility for practical applications.

Key Words: shift invariant dictionary learning; sparse coding; feature sign search; vibration signal; fault diagnosis

# 0 引言

对机械设备进行状态监控和故障诊断对于提高生产效率、预防事故发生具有重要的实际意义。在机械故障诊断中，对监控设备有效提取故障特征是实现故障模式识别的重要一环。然而，机械设备多样的工况和复杂的机械结构给特征提取带来了难度，基于时域和频域的特征提取算法依赖于人工特征选择，往往需要相关领域内的专家知识才能较好的完成特征提取工作[1,2]。

一直以来，研究人员针对机械振动故障特征提取做了大量的工作。其中，Harmouche等人[3利用频谱分析法研究不同轴承故障下的特征频率和包络谱，通过构建线性分类器实现不同故障的识别。但是基于频谱的分析方法依然依赖于人工经验知识，缺乏对数据自身的有效挖掘。王录雁等人[4提出了基于EMD（experiencemode decomposition）和灰色关联理论的轴承故障诊断方法，利用EMD将振动信号进行内禀模态分量(IMF)分解，建立各IMF能量分布与轴承故障状态的灰色关联模型实现故障诊断。但是EMD自身存在模态混叠现象，对于信号不同状态下的能量分布可能会产生干扰。蔡剑华[5等提出了基于高阶统计量的滚动轴承故障诊断方法，该方法的实质是将信号的高阶谱恢复为功率谱，利用功率谱提取信号的故障特征信息实现故障诊断。但是高阶统计量存在受奇异值影响较大的缺陷，

导致算法的结果并不稳定。

近年来基于字典学习的特征提取算法成为机器学习领域的研究热点，其核心思想是通过字典学习在原始数据中构建稀疏变换域，使待识别信号在该变换域下的投影具有稀疏性，Wright等人[提出了基于稀疏表示分类（sparserepresentationclassification，SRC）的人脸识别算法，首次在稀疏表示理论与模式识别之间建立了纽带，使基于稀疏表示的特征能够作为模式识别的特征向量实现对样本模式的准确识别，这给故障模式识别带来了新的思路。

字典的构建方式通常分为两种：基于数学分析的字典构建方法和自适应字典构建方法。基于数学分析的字典构建方法针对原始数据的先验知识实现稀疏化，常以正交变换基的形式实现过完备字典的构建。振动数据常以离散余弦变换[7（DFT）和傅里叶变换[8]（FFT）作为正交变换基。使用上述这些正交变换基虽然具有相对完善的算法框架，但缺乏灵活性，不能保证对应的数据类型在该变换基下是最稀疏的表示，某些信号特别是时频变化范围较广的信号在上述变换基下仍不稀疏或不够稀疏，从而影响对数据的重构精度[9。基于自适应的字典构建方法则以原始数据为训练样本，通过K-奇异值分解[10]（K-SVD）等算法实现过完备字典的构造，往往采用这种方法构造的字典对于原始数据的表达更具有稀疏性。从模式识别角度来看，越稀疏的特征往往对应着更佳的分类效果。

对于旋转机械设备而言，同一特征的出现具有循环往复性，因此本文考虑将移不变字典学习算法引入旋转机械故障识别中，以期能从原始数据中捕捉到具有时移不变性质的本质特征构成基函数，将这些特征平移来构建过完备字典，实现对机械设备故障状态的有效识别。

# 1 SIDL-SC故障识别算法理论

# 1.1移不变特征自学习算法

2006年，Smith[1]首先在《Nature》杂志上提出了移不变稀疏编码学习算法(shift invariant sparse coding，SISC)并成功应用于声信号特征提取。在形式上，SISC理论认为同一特征模式在时间序列上的移动是一个独立事件，学习到的基函数具有相对时间的移不变性。在构成学习字典的原子上，SISC学习到的基函数是信号中反复出现的本质特征，每个字典原子体现了信号的某一方面的特征。因此，SISC良好的移不变特性使其已在图像处理[12]、信号处理[13]等领域得到了应用。

SISC 使用一个包含 $M$ 个基函数的字典 $\left[ d _ { \scriptscriptstyle 1 } , d _ { \scriptscriptstyle 2 } , . . . , d _ { \scriptscriptstyle M } \right] \in \mathrm {  ~ i ~ } ^ { \scriptscriptstyle Q \times M }$ ，对于任意输入信号 $y _ { i } \in \mathfrak { i } ^ { \textit { \scriptscriptstyle N } }$ 均可由这些基函数和相应系数的卷积和来表示，基本数学模型为

$$
y _ { _ i } = \sum _ { m = 1 } ^ { M } d _ { _ m } * X _ { _ { m , k } } + \varepsilon
$$

其中：“ $*$ "表示卷积算子，用于表示基函数在所有可能位置上的移动。系数 ${ \pmb X } _ { m . k } \in \mathfrak { i } ^ { \textsc { \textsc { p } } }$ 具有稀疏性， $\boldsymbol { \varepsilon }$ 通常表示高斯白噪声。各参数满足以下关系： $Q < N \ , P < N$ 且 $P + Q - 1 = N$ 。定义目

标函数

$$
\left. d , \boldsymbol { x } \right. = \operatorname* { m i n } _ { d , \boldsymbol { x } } \sum _ { i = 1 } ^ { K } \left\| \boldsymbol { y } _ { i } - \sum _ { m = 1 } ^ { M } d _ { _ m } * X _ { _ { m , k } } \right\| _ { 2 } ^ { 2 } + \beta \sum _ { m , k } \left\| X _ { _ { m , k } } \right\| _ { 1 }
$$

其中：稀疏惩罚项 $\beta$ 用于控制稀疏化程度。通常 $\beta$ 设为固定值，但由于训练样本长度的不同，固定值往往并不能达到最优解，因此本文考虑对其进行改进以适应在不同训练样本长度下 $\beta$ 能具有较好的控制稀疏化效果。令 $\beta = \boldsymbol { \theta } \cdot \boldsymbol { L }$ ，其中 $\mathbf { \Omega } _ { L }$ 为训练样本长度， $\theta$ 定义为稀疏化尺度（通常 $0 < \theta < 0 . 1$ )，由此实现对稀疏惩罚项的改进。

字典学习阶段若同时优化基函数 $d _ { _ m }$ 和系数 $\boldsymbol { x } _ { { } _ { m , k } }$ 则该优化问题为非凸的，无法得到稳定解。因此，借鉴稀疏编码中交替优化的思想，依次更新 $d _ { _ { m } }$ 和 $\boldsymbol { X } _ { { \scriptscriptstyle m } , k }$ ，反复迭代直到目标函数收敛。优化过程分为系数求解和字典学习两部分[14]。

在系数求解部分，固定字典 $D$ 求解稀疏系数 $x$ ，则式(1)模型被分解为 $i = 1 , . . . , N$ 共 $N$ 个独立的优化问题，针对每个输入信号 $y _ { i }$ 求解得到的系数都独立于其他的输入，因此考虑单个输入$\boldsymbol { y } _ { i }$ 的系数求解优化问题。

$$
\operatorname* { m i n } _ { \boldsymbol { x } } \left\| \boldsymbol { y } _ { i } - \sum _ { j = 1 } ^ { M } \boldsymbol { d } _ { j } * \boldsymbol { X } _ { j } \right\| _ { 2 } ^ { 2 } + \beta \sum _ { j = 1 } ^ { M } \left\| \boldsymbol { X } _ { j } \right\| _ { 1 }
$$

本文采用高效的 Batch-OMP 算法[15]，在字典 $D$ 中寻找最佳的匹配原子 $x$ ，其表达式为

$$
\left\{ X ^ { \star } \right\} = \underset { \left\{ x ^ { \star } \right\} } { \arg \operatorname* { m i n } } \sum _ { k } \mathopen { } \mathclose \bgroup \left\| y _ { i } - d _ { j } X ^ { k } \aftergroup \egroup \right\| ^ { 2 } , s . t . \mathopen { } \mathclose \bgroup \left\| \alpha ^ { \star } \aftergroup \egroup \right\| _ { 0 } \leq l , \forall k
$$

在字典学习部分，固定系数 $x$ 求解字典矩阵 $D$ ，则原优化问题转换为 $L _ { _ 2 }$ 约束优化问题：

$$
\operatorname* { m i n } _ { { d } } \sum _ { i = 1 } ^ { N } \left\| y _ { i } - \sum _ { j = 1 } ^ { M } d _ { j } * X _ { i , j } \right\| _ { 2 } ^ { 2 } , s . t . \left\| \pmb { d } _ { j } \right\| _ { 2 } ^ { 2 } \leq c , \ 1 \leq j \leq M
$$

直接求解上式计算量巨大，本文在字典学习阶段借鉴时频域转换的思想，将时域计算量较大的卷积运算转换到频域，由频域的乘积运算代替时域的卷积运算，使运算复杂度由O(N)降低为 $O ( N \log N )$ ，提高了运算效率。由Parseval 定理可知，式(5)可转换为如下优化问题[14]：

$$
\operatorname* { m i n } _ { \hat { d } } \sum _ { i = 1 } ^ { N } \left\| \hat { \boldsymbol { y } } _ { i } - \sum _ { j = 1 } ^ { M } \hat { \boldsymbol { d } } _ { j } \cdot \hat { \boldsymbol { X } } _ { i , j } \right\| _ { 2 } ^ { 2 } , s . t . \left\| \hat { \boldsymbol { d } } _ { j } \right\| _ { 2 } ^ { 2 } \leq c
$$

其中： $\mathbf { \Psi } _ { c }$ 为常数， $\hat { \pmb { d } } _ { { \scriptscriptstyle j } }$ 为基函数 $d _ { { _ j } }$ 的离散傅里叶变换，相应地，$\hat { \boldsymbol { x } } _ { i , j }$ 和 $\hat { y } _ { i }$ 分别为 $\boldsymbol { x } _ { i , j }$ 和 $y _ { i }$ 的离散傅里叶变换。使用拉格朗日乘子法求解该问题，则该问题被分解为二次项求和的形式，对于每一个频域上的频率 $f$ ，构造拉格朗日函数：

$$
L \Big ( \hat { d } , \lambda \Big ) = \sum _ { f } \bigg ( \Big \| \hat { y } ^ { ( f ) } - \hat { X } ^ { ( f ) } \hat { d } ^ { ( f ) } \Big \| _ { 2 } ^ { 2 } + ( \hat { d } ^ { ( f ) } ) ^ { * } \Lambda \hat { d } ^ { ( f ) } \bigg ) - c I ^ { \prime } \lambda
$$

其中： $\lambda \in \mathfrak { i } ^ { \textbf { \scriptscriptstyle M } }$ 为对偶变量，单位向量 $\boldsymbol { I } \in \mathrm {  ~ i ~ } ^ { M }$ ，并且

$$
\begin{array} { r } { \hat { \hat { d } } _ { f } = \left( \begin{array} { c } { \hat { d } _ { 1 } ^ { ( f ) } } \\ { \mathbf { M } } \\ { \hat { d } _ { \scriptscriptstyle { M } } ^ { ( f ) } } \end{array} \right) , \hat { \pmb { y } } _ { f } = \left( \begin{array} { c } { \hat { \pmb { y } } _ { 1 } ^ { ( f ) } } \\ { \mathbf { M } } \\ { \hat { \pmb { y } } _ { \scriptscriptstyle { N } } ^ { ( f ) } } \end{array} \right) , \hat { \pmb { N } } = d i a g ( \lambda ) , \hat { \pmb { X } } _ { f } = \left( \begin{array} { c c c } { \hat { \pmb { x } } _ { ( 1 , 1 ) } ^ { ( f ) } } & { \hat { \pmb { x } } _ { ( 1 , 2 ) } ^ { ( f ) } } & { \Lambda } \\ { \hat { \pmb { x } } _ { ( 2 , 1 ) } ^ { ( f ) } } & { \hat { \pmb { x } } _ { ( 2 , 2 ) } ^ { ( f ) } } & { \Lambda } \\ { \mathbf { M } } & { \mathbf { M } } & { \mathbf { O } } \end{array} \right) } \end{array}
$$

$L \big ( \hat { d } , \lambda \big )$ 是复数函数，通过复数公式 $\left| z \right| ^ { 2 } = \left| \mathbf { R e } ( z ) \right| ^ { 2 } + \left| \mathbf { I m } ( z ) \right| ^ { 2 }$ 将复数函数转换为实函数求解，将 $\mathbf { R e } ( \hat { d } )$ 和 $\operatorname { I m } ( \hat { d } )$ 计算目标函数 $\hat { \pmb { d } } _ { \mathrm { m i n } } ^ { ( f ) } = \arg \operatorname* { m i n } _ { \hat { d } } L ( \hat { \pmb { d } } , \lambda )$ ，优化参数 $\lambda$ 可利用牛顿法求解，代入式(8)即实现对基的迭代更新。

$$
\hat { \pmb { d } } _ { \mathrm { m i n } } ^ { ( f ) } = ( ( \hat { \pmb { X } } ^ { ( f ) } ) ^ { * } \hat { \pmb { X } } ^ { ( f ) } + \Lambda ) ^ { - 1 } ( \hat { \pmb { X } } ^ { ( f ) } ) ^ { * } \hat { \pmb { y } } ^ { ( f ) }
$$

# 1.2基于特征符号搜索的系数求解算法

考虑到Batch-OMP算法需要预先设定稀疏度等参数，这在一定程度上增加了算法的计算量，如果参数选择不当很可能收敛速度较慢甚至难以收敛。考虑到待识别样本的稀疏度一般未知，因此本文在测试样本识别阶段引入特征符号搜索算法(Feature SignSearch，FS)求解待识别信号在不同基函数上的重构系数。FS算法由Lee 提出[16]，其核心思想是通过对系数符号的猜测将系数分量分为可行集（ $\Phi$ ）和0集（ ${ \bf \Pi } ( \Theta ^ { } )$ ，在0集中不断搜索梯度变化最大的分量并将其对应的下标 $i$ 放入可行集中直到算法收敛，算法具体步骤如下：

a)初始化 $\overset { \underset { \mathrm { \scriptsize ~ \ . ~ } } { } } { \boldsymbol { x } } = \overset { \underset { \mathrm { \scriptsize ~ \ . ~ } } { } } { 0 }$ ， $\theta = \stackrel { \mathbf { w } } { 0 }$ ，其中 $\theta _ { i } = \{ - 1 , 0 , 1 \}$ 表示系数分量 $x _ { i }$ 的符号。

b)在系数为零的分量中搜索梯度变化最大的分量及其下标放入可行集中。

$$
i = \arg \operatorname* { m a x } _ { i } \left. \frac { \hat { \mathcal { O } } \left. y - A x \right. ^ { 2 } } { \hat { \mathcal { O } } X _ { i } } \right. , \forall \theta _ { i } = 0 , \Phi = \Phi \cup \{ i \}
$$

若 $\left| \frac { \hat { \sigma } \big \| y - A x \big \| ^ { 2 } } { \hat { \sigma } x _ { i } } \right| > \gamma$ ，则 $\theta _ { { \scriptscriptstyle i } } = - 1$ ；若 $\left| \frac { \partial { \big \| } y - A x { \big \| } ^ { 2 } } { \partial x _ { i } } \right| < - \gamma$ ， $\theta _ { \scriptscriptstyle i } = 1$ 。

c)选取矩阵 $A$ 的子矩阵 $\hat { \boldsymbol A } ^ { \prime } \hat { \boldsymbol A }$ 中只含有与可行集中 $i$ 相对应的列向量，同样，选取与 $i$ 相应的子系数向量 $\hat { x }$ 和 $\hat { \theta }$ ，计算无约束优化方程 $\operatorname* { m i n } _ { \hat { x } } f ( x ) \equiv \left\| y - { \hat { A } } { \hat { x } } \right\| ^ { 2 } + \gamma { \hat { \theta } } ^ { r } { \hat { x } }$ ，求得最优解：

$$
\hat { X } _ { _ { n e w } } : = ( \hat { A } ^ { r } \hat { A } ) ^ { - 1 } ( \hat { A } ^ { r } y - \gamma \hat { \theta } ^ { r } / 2 )
$$

在 $\hat { x }$ 和 $\hat { x } _ { _ { n e w } }$ 之间进行线搜索，找到所有符号改变的系数向量，并将它们的目标函数与在 $\hat { X } _ { n e w }$ 的目标函数进行比较，将 $\hat { X } _ { n e w }$ 修正为使得目标函数值最小的系数向量。将 $\hat { x }$ 中系数分量为零的 $i$ 从可行集移除，并更新符号集合 $\theta$ 。

d)(a)若∀x≠0，都有y-Ax|² ${ \frac { { \hat { \sigma } } \left\| y - A x \right\| ^ { 2 } } { { \hat { \sigma } } x _ { i } } } + \gamma s i g n ( X _ { j } ) = 0$ +ysign(x)=0成立，则转条件(b)，否则转c);

(b)若∀x,=0，都有ly-Axl² ${ \frac { { \hat { \sigma } } \| y - A x \| ^ { 2 } } { { \hat { \sigma } } x _ { i } } } \leq \gamma$ ，则得到最优解 $x$ ，否则返回b)。

# 1.3基于重构残差的故障识别算法

理论上来说，与待识别信号的真实状态越接近，则由基函数及其求解的稀疏系数重构的信号与待识别信号的误差越小，因此考虑将重构残差作为故障识别的判断准则。利用FS算法求解待识别信号 $y _ { _ 0 }$ 在各个状态移不变基函数下的稀疏系数x,x。由式(11)求解基函数及其对应的稀疏系数的重构$\hat { y } _ { 1 } , . . . , \hat { y } _ { k }$ 。

$$
\hat { y } = \sum _ { j = 1 } ^ { M } d _ { j } * X _ { j }
$$

因此，SIDL-SC算法的实现分为数据预处理、移不变字典学习、重构系数求解和计算残差四部分，具体实现步骤如图1所示。

![](images/7bf1fbccdf2bcb4df521b0dd8a45706c45473483ac43e3940bad42f30759b7ed.jpg)  
图1本文故障识别算法流程图

# 2 实验

# 2.1实验设置

本文选取美国凯斯西储大学的开放轴承振动数据库进行实验[17]，使用电火花加工技术分别在轴承外圈、内圈和滚动体上设置单点故障，故障直径分别为 $0 . 1 8 \mathrm { m m }$ ， $0 . 3 6 \mathrm { m m }$ ， $0 . 5 4 \mathrm { m m }$ 。本文将不同故障数据分为两组，如表1所示。其中实验1使用数据集A中的样本进行训练和测试，实验2中采用实验1的字典学习到的基函数对 $1 { \sim } 2 \mathrm { h p }$ 负载下的样本进行测试，以检测本文算法的泛化能力。

表1实验数据集描述  

<html><body><table><tr><td>数据集</td><td>负载/hp</td><td>故障类型</td><td>故障尺寸/mm</td><td>类别标记</td></tr><tr><td>A/B</td><td>0/1~3</td><td>正常</td><td>0</td><td>1</td></tr><tr><td></td><td></td><td>内圈故障</td><td>0.18</td><td>2</td></tr><tr><td></td><td></td><td>内圈故障</td><td>0.36</td><td>3</td></tr><tr><td></td><td></td><td>内圈故障</td><td>0.54</td><td>4</td></tr><tr><td></td><td></td><td>外圈故障</td><td>0.18</td><td>5</td></tr><tr><td></td><td></td><td>外圈故障</td><td>0.36</td><td>6</td></tr><tr><td></td><td></td><td>外圈故障</td><td>0.54</td><td>7</td></tr><tr><td></td><td></td><td>滚动体故障</td><td>0.18</td><td>8</td></tr><tr><td></td><td></td><td>滚动体故障</td><td>0.36</td><td>9</td></tr><tr><td></td><td></td><td>滚动体故障</td><td>0.54</td><td>10</td></tr></table></body></html>

# 2.2 SIDL-SC 模型的建立

参数的选择影响算法的计算效率和故障识别的准确度，因此有必要根据训练样本的实际情况筛选出各个参数的最优值作为实现较高状态识别率的保证，本节考察对于建立SIDL-SC 模

型起重要作用的几个参数。

# 2.2.1稀疏化尺度

在移不变字典学习中，本文采用自适应稀疏尺度参数 $\theta$ 控制稀疏系数在目标函数中的比重，防止系数过大而基函数过小。实际表现为较大的 $\theta$ 值具有较快的收敛速度但是较高的重构误差。图2(a)以实验集A中第2类内圈 $1 8 \mathrm { m m }$ 故障样本为例，比较了不同 $\theta$ 值下移不变字典学习重构的原始信号的残差。从图中可以看出当稀疏尺度 $\theta$ 较低时，具有较低的重构误差，随着稀疏尺度的增大，重构误差呈现显著增大的趋势。但是从计算效率来说， $\theta$ 较小带来了每次迭代需要的计算量较大，从而导致收敛速度较慢。因此从重构误差和计算时间效率两方面来均衡，选择稀疏尺度为0.025是合适的。

1002．6中2422 95 小%00× 97  
R  
1. 9695.1941.2 93920.01 0.015 0.02 0.025 0.030.035 0.04 0.0450.05 40 50 60 7080 90 100 110120稀疏尺度 基函数长度(a)稀疏尺度对重构误差的影响 (b)基函数长度与识别准确率的关系

# 2.2.2基函数长度的选择

在移不变字典学习中，基函数的长度的选择影响对样本的识别率。对于滚动轴承来说，学习到的基函数应该包含轴承中至少一个完整的冲击，从实际测量来看，滚动轴承的两个相邻波峰的间隔平均在76左右。同样以上一节中的实验样本为例，不同基函数长度下的样本识别率如图2(b)所示，从图中可以看出，基函数在70\~90能够达到较高的样本识别率。而基函数长度较短时，由于每个移不变基函数不能学习到完整的信号冲击，导致正确率不能达到最佳。而基函数长度较长可能会带来信息冗余，不利于后期使用FS进行重构。因此，本文选择基函数长度为80。

# 2.2.3训练样本长度的选择

在多次实验中发现不同的训练样本长度对于故障识别的作用很大。以0hp负载下第1、2、5、8类样本为例进行训练和测试。其中每类故障状态随机选择100个样本用于测试，实验结果如图3所示。从图中可以明显看出，当训练样本长度为128和256时，在第8类故障的重构中，第2、5、8类学习到的基函数都能够以较低的残差对其重构，具体表现在这三类基函数的重构误差出现了混叠，这给样本的正确识别带来了困难。而输入样本为512和1024则较好的避免了混叠的现象，通过对比原始信号发现，训练样本长度为128和256分别包含1和3个完整冲击，而长度为512和1024包含有更多的完整冲击，从基函数自学习的角度来看，较多的冲击能使基函数学习到的特征更加显著，更有利于后期的重构分类。但训练样本长度的增加会带来每批次学习时间的增长，因此选择训练样本长度为512。

![](images/0783b5b3c99d07b77db437c553dec19b205f4653fb593bad12c86ee9c65f3d25.jpg)  
图2稀疏尺度和基函数长度对重构误差的影响  
图3训练样本长度与重构误差的关系

# 2.3实验结果

经过上一节的实验讨论，最后确定了SIDL-SC 算法中各主要参数值如表2所示。图4展示了部分学习到的移不变基函数，在实验一中分别在数据集A中每类状态随机选择200个样本用于测试，实验结果如表3所示。

从表3可以看出，本文所提出的方法在数据集A中的表现良好，大部分样本都可以达到 $100 \%$ 的正确识别率，只有部分样本存在1\~2个识别错误，随着数据集样本量的增大，本文算法可以取得更高的正确识别率。

表2SIDL-SC 各参数值  

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>训练样本长度</td><td>512</td></tr><tr><td>基函数长度</td><td>80</td></tr><tr><td>稀疏化尺度</td><td>0.025</td></tr><tr><td>基函数个数</td><td>4</td></tr><tr><td>样本重叠率</td><td>50%</td></tr><tr><td>迭代次数</td><td>60</td></tr></table></body></html>

![](images/9ad6c5d5b68a456dd9a161c1d980ab24081a15b757558c70c1812cd44c96ec0a.jpg)  
图4各状态典型振动信号及其对应的移不变基函数

(a(b).正常状态；c(d).内圈故障；(f).外圈故障；g(h).滚动体故障)

表3数据集A实验结果  

<html><body><table><tr><td>样本类别</td><td>识别正确率(%)</td><td>样本类别</td><td>识别正确率(%)</td></tr><tr><td>1</td><td>100</td><td>6</td><td>98.5</td></tr><tr><td>2</td><td>99.5</td><td>7</td><td>100</td></tr><tr><td>3</td><td>100</td><td>8</td><td>100</td></tr><tr><td>4</td><td>99</td><td>9</td><td>99.5</td></tr><tr><td>5</td><td>100</td><td>10</td><td>100</td></tr></table></body></html>

# 2.4与传统方法对比实验

为了体现SIDL-SC 算法在轴承故障识别中的优越性，本文与其他部分学者算法进行了对比实验。LIU[I8]同样在字典学习和稀疏编码框架内实现对轴承故障的识别，其未探讨参数选择问题，且将所有基函数构成冗余字典，使待识别样本由该冗余字典重构，借助LDA分类器实现故障分类。CHEN[19]采集振动信号的标准差、偏度、峭度等时、频域特征送入卷积神经网络分类器，利用LeNet5模型实现对故障的识别。将以上两种方法和本文算法都在0hp下的样本进行训练，分别在数据集B中各负载下的样本作为测试，取100次实验的平均结果如图5所示。从实验结果可以看出，采用传统时频域特征用于分类的CHEN的算法具有相对较低的识别率，而LIU的算法虽然在个别样本上的识别率较高，但总体不如本文算法的稳定性高。

![](images/c2ac2ec9cf2febbda8b154e8203652680f384a6932135c47cbe39e4785692199.jpg)  
图5不同负载下各算法样本识别率  
图6各状态典型振动信号

# 2.5实测航空发动机实验

为验证本文算法在实际装备中的可行性，将该算法应用于实测某型航空发动机故障识别。实验数据采集于该型直升机涡轴发动机多台次、多次台架试车时所测得的四种状态下发动机振动信号，即正常状态、转子不平衡故障、转子松动故障和碰摩故障，采用等弧度采样方式，每周期采集128个数据点，典型振动信号如图6所示。

利用SIDL-SC算法对不同状态下的振动信号进行移不变字典学习，参数设置如下：训练样本长度为256，基函数长度为50，稀疏化尺度为0.01，基函数个数为2，其余参数设置与表3相同。学习到的移不变基函数如图7所示。

正常状态  
融 wwwww500 1000 1500 2000 2500 3000数据点数转子不平衡>>>>>>>>>>>>>>>>>>>>>>-50500 1000 1500 2000 2500 3000数据点数转子松动  
期勤 -50 MWwW500 1000 1500 2000 2500 3000数据点数碰摩500-50500 1000 1500 2000 2500 3000数据点数

![](images/306e6715adc2571f7d3d7fcda36113f72ce2ec6bf3dd10dd1c597f8c2c83e9eb.jpg)  
图7不同状态下学习到的移不变基函数（a.正常状态；b.转子不平衡；c.转子松动；d.碰摩)

从图中可以看出正常状态下的移不变基函数波形比较平缓，故障状态下学习到的移不变基函数均不同程度的含有其各自独特的特征。对不同状态进行识别，每组实验重复进行100次，取识别准确率作为评价指标，实验结果如表4所示，并与文献[18]和文献[19]中的方法进行对比。实验结果表明，由于发动机转子不平衡故障和转子松动故障与正常状态的波形上存在一些相似之处，导致算法的识别率低于CWRU数据集，但相较于上述两种算法，本文算法仍然能保持较高的故障识别率，进一步验证了本文算法的可行性。

表4航空发动机实验识别结果  

<html><body><table><tr><td>识别率 (%)</td><td>正常状态</td><td>转子不平衡</td><td>转子松动</td><td>碰摩</td></tr><tr><td>文献[18]方法</td><td>80</td><td>78</td><td>74</td><td>86</td></tr><tr><td>文献[19]方法</td><td>76</td><td>73</td><td>74</td><td>80</td></tr><tr><td>本文算法</td><td>85</td><td>82</td><td>81</td><td>93</td></tr></table></body></html>

# 3 结束语

SIDL-SC是一种结合移不变字典学习和稀疏编码的振动信号故障识别算法，尤其是针对多工况条件下的故障识别有着较高的正确识别率。该方法以原始振动数据作为训练样本，通过特征自学习捕获反映不同状态信号本质特征的移不变基函数，以最小重构残差为准则判别故障的类别。同时对移不变字典学习中的惩罚因子进行了优化，以稀疏尺度作为前者的因变量，有效解决了不同训练样本长度下惩罚因子的设定问题。以CWRU振动数据库作为研究对象，本文详细探讨了不同参数选择对实验结果的影响，遴选出最优参数作为最终的实验参考变量。同时，将本文算法应用于实测航空发动机振动信号，并与其他部分学者的算法进行实验对比，结果表明，本文算法具有更强的泛化能力，可以更好的应用于实际振动数据的处理。

# 参考文献：

[1]朱会杰，王新晴，芮挺，等．基于频域信号的稀疏编码在机械故障诊断中的应用[J].振动与冲击,2015,34(12):59-64.

[2]Janssens O, Slavkovikj V, Vervisch B,et al. Convolutional neural network based fault detection for rotating machinery [J].Journal of Sound & Vibration,2016,377:331-345.   
[3]Harmouche J, Delpha C,Diallo D. Improved fault diagnosis of ball bearings basedonthe global spectrum of vibrationsignals[J]. IEEE Trans onEnergy Conversion,2015,30(1): 376-383.   
[4]王录雁，王强，张梅军，等．基于 EMD 的滚动轴承故障灰色诊断方法 [J]．振动与冲击,2014,33(3):197-202.   
[5] 蔡剑华，胡惟文，王先春．基于高阶统计量的滚动轴承故障诊断方法 [J].振动、测试与诊断,2013,33(2):298-301.   
[6]Wright J,Yang A,Ganesh A,et al.Robust face recognition via sparse representation [J]. IEEE Trans on Patern Analysis & Machine Intelligence, 2009,31(2): 210-227.   
[7] 张新鹏，胡笃庆，程哲，等．基于压缩感知的振动数据修复方法[J]. 物理学报,2014,63 (20): 115-124.   
[8] 郭亮，高宏力，黄海凤，等．基于压缩感知理论的时变信号压缩技术 [J]．西南交通大学学报,2015,50(3):511-516.   
[9] 彭向东，张华，刘继忠．基于过完备字典的体域网压缩感知心电重构 [J]．自动化学报,2014,40(7):1421-1432.   
[10] Aharon M,Elad M,Bruckstdin A M et al.K-SVD:an algorithm for designing overcomplete dictionaries for sparse representation [J]. IEEE Trans.on Signal Processing,2006,54 (11): 4311-4322.   
[11] Smith E C,Lewicki M S.Efficient auditory coding [J]. Nature,2006, 439 (7079): 978-982.   
[12] Morup M,Schmidt MN,Hansen LK. Shift invariant sparse coding of image and music data [R]. Technical Report, 2007.   
[13] Tang Haifeng,Chen Jin, Dong Guangming. Sparse representation based latent componentsanalysis for machinery weak fault detection [J]. Mechanical Systems & Signal Processing,2014,46 (2): 373-388.   
[14] GrosseR,Raina R,Kwong H, et al. Shift-invariant sparse coding for audio classification [C]// Proc of Conference on Uncertainty in AI. Vancouver: AUAI Press,2007: 149-158.   
[15] Rubinstein R, Zibulevsky M, Elad M. Eficient implementation of the K

SVD algorithm using batch orthogonal matching pursuit [J].CS Technion, 2011,40.

[16]Honglak L,Battle A,Raina R,et al.Efficient sparse coding algorithms [C]// Advances in Neural Information Processing Systems.20o6:801-808.   
[17] http://csegroups.case.edu/bearingdatacenter/pages/download-data-file [EB/OL].

[18]Liu Haining,Liu Chengliang,Huang Yixiang.Adaptive feature extraction using sparse coding for machinery fault diagnosis [J].Mechanical Systems and Signal Processing,2011,25 (2): 558-574.

[19] Chen Zhiqiang,Li Chuan,Sanchez R V.Gearbox fault identification and classification with convolutional neural networks [J].Shock & Vibration, 2015 (2): 1-10.