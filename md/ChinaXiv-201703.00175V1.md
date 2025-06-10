# 基于WiFi的室内定位方法及系统

# 刘军发 陈益强 赵中堂 宁琼

摘要：在现代信息化生活中，人们对室内定位的需求日益增多，对系统定位精度要求也越来越高。如机场和大型购物广场内的导航、会议指南、资源查找、井下工作人员的定位、老人与儿童的监护等。本文针对室内定位在实际应用中的多方面问题进行了深入研究。具体工作包括：基于非标定信号流形特征的定位方法研究、设备与时间迁移的定位研究、大面积接入点（AP）无缝切换定位研究、垂直空间的相同楼宇定位模型迁移研究、面向接入点缺失与稀疏条件的定位研究、基于单接入点的房间级定位研究、免标定定位方法研究以及基于WiFi定向特征的定位研究等。实验表明，基于WiFi的室内定位技术日渐成熟，其定位精度以及系统的易用性正在使该技术向低成本实用化的目标迈进。

关键词：WiFi室内定位 流形正则化 迁移学习大面积定位 垂直空间定位 接入点缺失 单接入点定位 定向接入点定位

# 1序言

随着无线通信技术及其基础设施的迅速发展与完善，定位技术与系统得到研究领域与工业界的共同关注。从基于GPS'的室外定位技术，到基于红外、超声波的短距离定位技术，再到基于WiFi信号的室内定位技术，都出现了大量研究工作及其应用系统。这些技术由于涉及到的硬件的工作机制不同，各有其使用场景与适用范围。基于卫星通信的 GPS[1,2]是目前应用最为广泛的定位技术，具有良好稳定的定位性能。其局限性在于需要与卫星保持视线可视的条件，在室内或建筑物环境中，无法定位。近十年来，室内定位涌现出了许多系统方案。如：AGPS 定位、超声波定位系统[3]、蓝牙(Bluetooth)[4]、红外线定位[5]、基站定位[]等。这些系统在应用中也都存在一定的应用范围与局限。如AGPS、基站方式需要对基础设施进行改造，成本较高；蓝牙的探测范围较小；超声波与红外线方式易受介质遮挡等等。

近年来，基于 $\mathbf { I E E E 8 0 2 . 1 1 6 } / \mathbf { g }$ 协议的无线局域网（WLAN）的信号强度定位技术日益受到重视，目前主流的PDA、笔记本等移动设备中都内置无线网卡，从设备上为该定位技术提供了便利。基于信号强度的定位技术基本原理是根据接收到的信号的强度推算信号接收器与信号源之间的距离，与基于信号到达时间（TOA）和信号到达时间差（TDOA）以及信号到达角度（AOA）的定位技术相比，它不需要添加额外的硬件设备；更为重要的是，它不易受到障碍物的干扰，不会因为室内环境过于复杂而导致定位精度剧烈下降。目前，在国外这方面的研究主要有微软研究院[7、IBM公司[8]、英特尔公司[9]、卡内基梅隆大学[10]、匹兹堡大学[11]、马里兰大学[12]等，中国研究机构则有香港科技大学[13]、台湾国立交通大学[14]以及中国科学院计算技术研究所[15，18\~24,31]、浙江大学[16]等。

室内定位技术面临的最大挑战在于环境的多样性与动态性。如小型建筑和大型建筑的不同，单层建筑和多层建筑的不同，不同建筑中接入点（Access Point,AP）的分布不同，建筑中物品的摆放对接入点信号遮挡的不同，不同时间段、不同的室内温度、湿度对信号衰减影响的程度不同，接入点信号自身的不稳定等。上述环境条件均会影响定位方法的性能。本文在这些方面分别进行了较深入的研究，并取得一定成果。

以下内容具体安排如下：第二章分别就室内定位面临的多种实际挑战问题进行研究，给出了相应的对策及实验结果；第三章介绍典型的室内定位应用场景；第四章对本文研究以及下一步工作进行总结与展望。

# 2基于WiFi信号的室内定位方法

# 2.1基于WiFi信号流形特征与正则化的定位方法

# 2.1.1背景

传统的机器学习方法只使用标定数据（特征向量/标号对）作为训练集。但是获得室内定位所需的标定数据一般比较困难，或者费时费力，甚至需要专业人员的参与，获得未标定数据却相对比较容易。而半监督机器学习算法则使用大量的未标定数据和少量的标定数据进行训练，减少工作量的同时得到更好的性能。流形正则化就是这样一种半监督机器学习算法[17],它将谱理论、流形学习和再生核希尔伯特空间（RKHS）上的正则化等概念有效地结合在一起。我们基于这个框架进一步提出了一种有效的半监督机器学习算法LapRLS，并应用该方法在 IEEE ICDM2007（IEEE International Conference on Data Mining）数据挖掘竞赛，获得第二名[32]。

# 2.1.2流形正则化用于定位问题

为了使用这一方法，需要首先对无线局域网中信号强度的分布特性进行流形分析，得到例如表1所示那样的信号强度序列矩阵。在空间上，已知位置L1和L2两点间距离小于位置L1和L3两点间距离。表中显示位置L2点采集到的信号强度相比位置L3更接近于L1点采集到的信号强度。在时间维度，同一位置点L1在不同时间点采集的三个信号样本，表中显示时间点24.859采集到的信号强度相比时间点26.359更接近于时间点24.359采集到的信号强度。空间间隔和时间间隔越小，信号强度的相似度越大。以上观察结果提示我们，构造图所采用的相似性准则应该从空间和时间两个方面的相似性进行综合考虑。从上面的分析可以看到结果近似符合流形的基本假设：潜在流形上相近的点往往也趋近于拥有相同的标号或回归值。

表1. 信号强度矩阵   

<html><body><table><tr><td>位置 时间</td><td>AP1</td><td>AP2</td><td>AP3</td><td>AP4</td><td>AP5</td><td>AP6</td></tr><tr><td>L1 24.359</td><td>-84</td><td>-92</td><td>-80</td><td>-68</td><td>-81</td><td>-81</td></tr><tr><td>L1 24.859</td><td>-84</td><td>-92</td><td>-80</td><td>-68</td><td>-81</td><td>-81</td></tr><tr><td>L1 26.359</td><td>-92</td><td>-92</td><td>-79</td><td>-68</td><td>-85</td><td>-81</td></tr><tr><td>L2 38.859</td><td>-91</td><td>(-100)</td><td>-87</td><td>-65</td><td>-86</td><td>-82</td></tr><tr><td>L2 41.859</td><td>-91</td><td>(-100)</td><td>-82</td><td>-66</td><td>-87</td><td>-83</td></tr><tr><td>L3 46.359</td><td>-92</td><td>(-100)</td><td>-85</td><td>-66</td><td>(-100)</td><td>-84</td></tr><tr><td>L3 47.359</td><td>-92</td><td>(-100)</td><td>-85</td><td>-66</td><td>(-100)</td><td>-84</td></tr></table></body></html>

和其它机器学习算法在定位问题中的应用类似，我们提出的基于流形正则化的定位算法LapRLS也包含两个阶段：离线训练阶段和在线定位阶段。

# 1．离线训练阶段

准备训练数据。训练数据包括一些由用户轨迹构成的信号序列和一些离散的信号数据，两部分数据均是部分标定的。对于无法探测到的信号，将其填充为最小值-100dBm。训练数据预处理。鉴于信号的高噪声特点，我们对信号序列进行了高斯平滑，前提假设是：用户在短时间的行走中不可能跨越太长的距离，信号也不会产生巨大的跳跃，应该是比较平滑的衰减。这种方法能够有效地剔除噪声数据，提高定位的精度。计算图的拉普拉斯矩阵 $L$ 。构造邻接矩阵 $W$ 时，综合考虑信号强度和时间上的相似性。信号强度上，对于每个信号向量 $\pmb { s } \in \pmb { S }$ ，将其和它的 $\pmb { k }$ 个最近邻居连接起来，使用的距离相似函数为明氏距离 $\left\| s _ { 1 } - s _ { 2 } \right\| p$ 。时间上，将小于一定时间间隔$\left\| \pmb { t } _ { 1 } - \pmb { t } _ { 2 } \right\| < \Delta \pmb { T }$ 的两个信号向量 $s _ { t 1 }$ 和 $s _ { t 2 }$ 连接起来。这样构造起来的邻接矩阵可以用于计算图的拉普拉斯矩阵 $\pmb { L } = \pmb { D } - \pmb { W }$ ，其中 $\pmb { D }$ 为对角矩阵，对角线上的元素对应W各行元素的和。：应用LapRLS算法。使用LapRLS算法学习出信号 $\textbf { \^ s }$ 到位置 $\iota$ 的映射关系，其中 $\boldsymbol { x }$ 和 $y$ 坐标分别对待，根据[17]得到它们的优化系数 $\alpha \pmb { x }$ 和 $\alpha \mathbf { y }$ ，进一步可以得到各自的回归函数 $f _ { \alpha x } ( s )$ 和 $\pmb { f } _ { \alpha y } ( \pmb { s } )$ 。

2．在线定位阶段

准备测试数据。测试数据是全部未标定的用户轨迹信号序列，将无法探测到的信号填充为最小值- $\cdot 1 0 0 \mathrm { d B m }$ 。测试数据预处理。采用和训练数据预处理一样的高斯平滑方法，剔除测试数据中的噪声。  
定位计算。对于测试数据中的每一个信号向量 $\hat { s }$ ，其位置为$\hat { l } = ( \hat { x } , \hat { y } ) = ( f _ { \alpha x } ( \hat { s } ) , f _ { \alpha y } ( \hat { s } ) )$ ， $f _ { \alpha x } ( s )$ 和 $\pmb { f } _ { \alpha y } ( \pmb { s } )$ 均是通过训练阶段得到。

# 2.1.3试验结果

这部分试验使用了全部测试数据（2137个样本）。训练样本则包括505个标定数据。另外我们的算法还包括附加的2691个未标定数据。图1显示了各种算法在不同距离误差下的定位准确率。可以看出我们的算法通过使用未标定数据提高了定位的精度，例如在 $1 . 5 \mathrm { m }$ 距离误差内定位的准确率比 $\mathbf { k }$ -近邻（K-Nearest-Neighbor，KNN）方法和RLS方法分别提高了 $10 \%$ 或 $2 5 \%$ 左右。

![](images/f5aa3611ca3309c9f867259b844e1e28c47bb928f5e5db17d751fbaee43a54ce.jpg)  
图1.定位准确率比较

# 2.2基于流形对齐的自适应定位算法

# 2.2.1背景

无线信号容易受到环境的影响而发生变化，已有定位模型面临信号分布变化时定位精度会急剧下降，如何只用较少的有标记数据更新模型而能保持较高的定位精度是一个难点问题。我们在论文[18]中从信号空间的流形假设出发，提出了一种流形对齐的降维方法LuMA，通过构造两种不同分布的数据集在低维空间的对齐流形，实现不同领域间的知识迁移。

# 2.2.2LuMA算法步骤

1．流形构造

将数据集看做图的顶点集，构造有权图描述数据集的局部邻接关系；计算权重矩阵W，若两点为邻居则权重非0;  
构造图的拉普拉斯矩阵：

$$
L _ { i j } = \{ \begin{array} { l l } { \displaystyle { \sum _ { j  i } W _ { i j } } } & { \displaystyle { ( \overrightarrow { \sum _ { i } } i = j ) } } \\ { \displaystyle { - W _ { i j } } } & { \displaystyle { ( \overrightarrow { + \sum _ { i } } i \sim j ) } } \\ { \displaystyle { 0 } } & { \displaystyle { \sharp \sharp / \underline { { \mathbb { H } } } } } \end{array} 
$$

定义图顶点上的实值映射函数 $f : d _ { h }  \mathbb { R }$ ;最优化的流形嵌入 $f ^ { * }$ 等价于求解优化问题：

$$
\underset { f } { \arg \operatorname* { m i n } } \ f ^ { \mathrm { T } } L f = \frac { 1 } { 2 } { \sum _ { t , j } } ( f _ { t } - f _ { j } ) ^ { 2 } W _ { i j }
$$

最优解是 $L$ 的最小的 $\pmb { d } _ { l }$ 个非零特征值对应的特征向量，构成与原始数据结构类似的低维流形嵌入。

2．流形对齐

分别定义数据集 $_ { X , Y }$ 上的映射 $f : d _ { h }  \mathbb { R }$ ;其中已知部分数据间对应关系 $x _ { i }  y _ { i } , i \in \mathbb { R }$ ：求解对齐流形等价于优化：$C ( \boldsymbol { f } , \mathbf { g } ) = \mu \underset { t \in p } { \sum } \left| f _ { i } - \mathbf { g } _ { i } \right| ^ { 2 } + \lambda _ { 1 } f ^ { T } L ^ { x } f + \lambda _ { 2 } g ^ { T } L ^ { y } g \mathrm { ~ , ~ }$ -第一项衡量 $f$ 和 $\pmb { g }$ 在对应点上的差异，后两项保证流形在低维空间上的光滑性;

当 $\mu \to \infty$ 时，等价于强制约束 $f _ { i } = g _ { i } , i \in \pmb { p }$ ;

-求瑞利（Rayleigh）商，得到 $X$ 和 $Y$ 的拉普拉斯矩阵组合成的联合拉普拉斯矩阵：

$$
\begin{array} { r } { \mathbf { { \cal L } ^ { Z } } = \left[ \begin{array} { c c c } { \lambda _ { 1 } \mathbf { { \cal L } } _ { p p } ^ { x } + \lambda _ { 2 } \mathbf { { \cal L } } _ { p p } ^ { y } } & { \lambda _ { 1 } \mathbf { { \cal L } } _ { p s } ^ { x } } & { \lambda _ { 2 } \mathbf { { \cal L } } _ { p s } ^ { y } } \\ { \lambda _ { 1 } \mathbf { { \cal L } } _ { s p } ^ { x } } & { \lambda _ { 1 } \mathbf { { \cal L } } _ { s s } ^ { x } } & { 0 } \\ { \lambda _ { 2 } \mathbf { { \cal L } } _ { s p } ^ { y } } & { 0 } & { \lambda _ { 2 } \mathbf { { \cal L } } _ { s s } ^ { y } } \end{array} \right] } \end{array}
$$

最优解为 $L ^ { z }$ 的 $\pmb { d } _ { l }$ 个非零特征值的特征向量;  
基于对齐流形建立两个数据集上点的对应关系。

# 2.2.3实验结果

在实际室内楼层中搭建无线网络环境，将实验场地划分为1米 $\times 1$ 米的方格进行数据采集，包括不同时间（上午、下午）和不同设备（笔记本、手机）的信号数据集。

我们做了三组不同的实验：首先是对不同时间段的迁移，然后是在不同设备上的迁移，最后是不同时间不同设备的迁移。对比模型分别为：只采用源领域数据建立的模型（SDM)，用来给出旧定位模型造成的定位精度下降的程度；只采用目标领域数据建立的模型（TDM)，用来给出目标领域可以达到的最好精度；采用线性迁移的模型（LSM) 1 常用的一种迁移模型。图2、图3、图4分别展示了在不同条件下的算法性能比较。

总体来说，迁移学习与只采用源领域数据建立的旧定位模型相比能够大大地提高定位的精度，并且在只有少部分目标领域数据的情况下确实能够从源领域数据中迁移知识帮助提高目标领域的定位精度，而相对于简单的线性迁移方法来说，我们的基于流形对齐的迁移学习方法更加稳定有效。

![](images/c06a372ccae059cfb8f423d5efc76230b8af9cb7be8aaa42cdca7950c100642b.jpg)  
图2.受时间影响的准确率

![](images/266191efd7ba3a65a19c12559092affd05828bccfceef83f0202038f7ec97190.jpg)  
图3.受设备影响的定位准确率

![](images/fe3219d4e3f706263d0814aaa17a6b9d997b31ef26ad19357b835b65a24b1a94.jpg)  
图4.受时间设备共同影响的定位准确率

# 2.3大面积接入点无缝切换定位研究

# 2.3.1背景

受信号衰减的影响，接入点覆盖范围有限，使得在室内大区域内检测到的接入点分布呈现比较复杂的情况。即，如果将大区域划分为多个子区域，则在不同的子区域往往检测到不同的接入点集合。因此在大面积的室内环境进行定位时，会频繁出现许多接入点在大量的子区域都检测不到的情形。

我们在中科院计算所大厅的不同位置采集到的接入点呈现不同的分布情况。发现同一个接入点,在不同的位置得到的信号强度有着不同的表现，在有的地方信号良好，在有的地方却很差甚至无法检测到。

传统的室内定位方法往往只是针对区域固定，具有固定接入点组合的情况而设计,对于极少数接入点无法探测的情况，采用将其赋值为最小（-100dbm）的方式进行处理。但如前所述，由于大区域范围这种缺失情况非常频繁，如果仍然按照已有的处理方法，将所有检测不到的接入点信号强度置为最小值，就会带来较大的误差。在论文[19]中提出了一种室内无缝定位方法LAM,即 Large-scale Area Manage。其初衷是尽可能多地利用对定位有帮助的信号，而将那些容易造成信号波动或者对定位效果有负面影响的信号尽可能去掉。在各个无线覆盖区域训练不同的定位模型来预测位置，不同的无线覆盖区域可以针对信号情况自由选择最合理的接入点组合来进行定位，互不干扰，也无需考虑选择的接入点个数的限制。本方法只需要在开始定位的时候对物体所在的无线覆盖子区域进行一次判断，并且不需要寻找整个定位区域都能检测到的接入点集合。

# 2.3.2LAM算法流程

LAM算法主要包括以下几个步骤：

步骤1. 对于每一个点 $P _ { j }$ 利用 InfoGain 算法[15]初始化 $G A P _ { j }$ ；

步骤2. 将区域分为 $N$ 个子区域（areas）;

步骤3. 计算$s A P _ { w } = \left\{ a p { \big | } a p \in G A P _ { j } \land P _ { j } \in s A _ { w } \right\}$ ,当 $1 \leq w \leq N , 1 \leq j \leq n$ ；

步骤 4. 更新 $s A P _ { w } ( 1 \leq w \leq N )$ 直到 $s A P _ { w }$ 发生变化;

步骤5． 若 $s A _ { w } \subset s A _ { w - 1 }$ ，则 $s A _ { w } = s A _ { w } \cup s A _ { w - 1 }$ 若 $s A _ { w } \subset s A _ { w + 1 }$ ，则 $s A _ { w } = s A _ { w } \cup s A _ { w + 1 }$ 。 其中 $G A P _ { j }$ 为每个标定点的可用定位信号集合， $P _ { j }$ 为标定点。

# 2.3.3试验结果

试验证明，LAM大大的提高了大范围的定位精度。如表2所示：其中，大区域内获得的定位准确率是指在整个区域采用统一定位模型获得的结果。各子区域对应的定位准确率则是是指将大区域进行划分后分别进行定位获得的结果。最后一行所有子区域的平均定位准确率代表LAM方法的定位准确率。

表2. 区域分割定位准确率比较  

<html><body><table><tr><td>区域范围</td><td>1m</td><td>2m</td><td>3m</td></tr><tr><td>大区域</td><td>0.2145</td><td>0.4188</td><td>0.5591</td></tr><tr><td>子区域1</td><td>0.7553</td><td>0.9309</td><td>0.9468</td></tr><tr><td>子区域2</td><td>0.4563</td><td>0.6865</td><td>0.8810</td></tr><tr><td>子区域3</td><td>0.7000</td><td>0.8955</td><td>0.9455</td></tr><tr><td>子区域4</td><td>0.8032</td><td>0.9574</td><td>0.9894</td></tr><tr><td>子区域5</td><td>0.7340</td><td>0.9255</td><td>0.9628</td></tr><tr><td>子区域6</td><td>0.7027</td><td>0.8311</td><td>0.9392</td></tr><tr><td>子区域7</td><td>0.5423</td><td>0.8367</td><td>0.9355</td></tr><tr><td>子区域8</td><td>0.4608</td><td>0.7108</td><td>0.8188</td></tr><tr><td>子区域平均 (LAM)</td><td>0.6443</td><td>0.8468</td><td>0.9274</td></tr></table></body></html>

# 2.4楼宇垂直空间的定位模型迁移方法

# 2.4.1背景

实际应用中，除了平面内的大区域定位需求，也有上下空间的大区域定位需求，比如在建筑内需要知道在哪一层的什么位置。但对于某一楼层的定位服务来说，其定位模型的训练，涉及到大量的数据采集与人工标定，需要很多的人力与物力。若能够在不同楼层之间尽可能共享训练数据，以减少数据采集量与标定量，则具有十分重要的现实意义。考虑到不同楼层之间具有相同或相似的物理建筑结构，我们在论文[20]中对此进行了研究，提出了一种基于迁移回归模型 TRM（TransferRegressionModel）的三维定位模型，并获得了较好定位效果。

![](images/d13a9aae26f3854042e162af8c11c93ff42c09a875f5268e08af83665c149033.jpg)  
图5.三个数据集之间的关系

# 2.4.2基于迁移回归模型TRM的三维室内定位

首先具体描述一下三个数据集的回归问题：如图5所示，两个变量（ $\scriptstyle { \mathbf { \boldsymbol { X } } }$ 和 $\boldsymbol { Y }$ ）具有函数关系即 $\mathbf { \boldsymbol { y } } = \mathbf { \boldsymbol { f } } ( \mathbf { \boldsymbol { x } } )$ ， $X$ 与 $Y$ 代表的两个训练数据集样本，数据集可能具有不同数量的元素，即二者元素并非一一对应。同时它们之间还存在中间变量即 $z$ 。 $z$ 与 $X$ 具有函数关系${ z = g ( \pmb x ) }$ ，而 $Y$ 与 $z$ 又具有函数关系 $\mathbf { \boldsymbol { y } } = \mathbf { \boldsymbol { h } } ( \boldsymbol { z } )$ 。在这两种情况下，需要回归模型 $f$ 具有两方面的特点，以尽可能获得高的回归精度，即：1）能够应用训练集中大量的未标定样本；2)能够在 $X$ 和 $Y$ 的回归训练过程中有效利用 $z$ 提供的信息。

本项目提出一种迁移回归模型 TRM，满足以上两方面特点。核心思想为，基于流形正则化框架，在优化回归函数 $\mathbf { \boldsymbol { y } } = \mathbf { \boldsymbol { f } } ( \mathbf { \boldsymbol { x } } )$ 的过程中，引入第三类数据集 $z$ 和相应的分解函数$z = g ( \pmb { x } )$ 和 $\mathbf { \boldsymbol { y } } = \mathbf { \boldsymbol { h } } ( \boldsymbol { z } )$ 。通过使函数 $\pmb { h }$ 与 $f$ 的输出结果一致来约束函数的求解。

构造优化目标：

$$
\begin{array} { l } { \displaystyle ( f ^ { * } , g ^ { * } , h ^ { * } ) = \underset { f \in H { \cal k } } { \mathrm { a r g } } \left. \frac { 1 } { l } \underset { i = 1 } { \overset { l } { \sum } } V ( x _ { i } , y _ { i } , f ) + \gamma _ { A 1 } \left\| f \right\| _ { \cal K } ^ { 2 } + \gamma _ { \Pi } \left\| f \right\| _ { \cal I } ^ { 2 } + \right. } \\ { \displaystyle \left. \frac { 1 } { l } \underset { i = 1 } { \overset { l } { \sum } } V ( x _ { i } , z _ { i } , g ) + \gamma _ { A 2 } \left\| g \right\| _ { \cal K } ^ { 2 } + \gamma _ { I 3 } \left\| g \right\| _ { \cal I } ^ { 2 } + \right. } \\ { \displaystyle \left. \frac { 1 } { l } \underset { i = 1 } { \overset { l } { \sum } } V ( z _ { i } , y _ { i } , h ) + \gamma _ { A 3 } \left\| h \right\| _ { \cal K } ^ { 2 } + \gamma _ { I 3 } \left\| h \right\| _ { \cal I } ^ { 2 } + \right. } \\ { \displaystyle \left. \frac { 1 } { l } \underset { i = 1 } { \overset { l } { \sum } } ( h ( z _ { i } ) - f ( x _ { i } ) ) ^ { 2 } \right. } \end{array}
$$

然后构造通用型回归函数形式如下：

$$
f ^ { * } ( x ) = \sum _ { i = 1 } ^ { l } \alpha _ { i } K _ { 1 } ( x _ { i } , x )
$$

最终解得：

$$
\alpha ^ { * } = ( I - A J K _ { 3 } B J K _ { 1 } ) ^ { - 1 } ( A Y + A J K _ { 3 } B Y )
$$

其中，

$$
\begin{array} { r l } & { \pmb { A } = \left( 2 \pmb { J } \pmb { K } _ { 1 } + \gamma _ { A 1 } \pmb { I } \pmb { I } + \frac { \gamma _ { I 1 } \pmb { l } } { \left( \pmb { u } + \pmb { l } \right) ^ { 2 } } \pmb { L } \pmb { K } _ { 1 } \right) ^ { - 1 } } \\ & { \pmb { B } = \left( 2 \pmb { J } \pmb { K } _ { 3 } + \gamma _ { A 3 } \pmb { I } \mp \frac { \gamma _ { I 3 } \pmb { l } } { \left( \pmb { u } + \pmb { l } \right) ^ { 2 } } \pmb { L } _ { 3 } \pmb { K } _ { 3 } \right) ^ { - 1 } } \end{array}
$$

可以看出，未标定数据以及数据集 $z$ 均参与了结果的求解，对回归函数产生了影响。本文采用 TRM 模型进行了三维定位实验，来测试TRM对定位精度的影响。如图6所示，在建筑物第四层已采集了大量数据，并进行了标定。对于在建筑物第三层的定位，我们只需要采集少量的数据和标定的点（圆点)，就可以对未知点（十字）进行定位估计。

4楼 E0标定对楼6 定位点

# 2.4.3试验结果

我们设计了两个实验进行对比：其一是不采用 TRM模型，只使用第三层采集的少量标定数据进行模型训练；其二是采用TRM模型，引入第四层的训练数据。实验结果如表3所示。其中ED为错误阈值，预测结果与实际位置之间的误差大于该阈值时，预测结果被认为是错误的。可以看出，采用了TRM模型的预测模型能够明显提高预测精度。

表3. 采用TRM的实验结果  

<html><body><table><tr><td colspan="4">定位准确率</td></tr><tr><td></td><td>EDo=1米</td><td>ED0=2米</td><td>ED0=3米</td></tr><tr><td>利用转换</td><td>65.2%</td><td>78.3%</td><td>89.6%</td></tr><tr><td>不利用转换</td><td>51.5%</td><td>66.7%</td><td>85.3%</td></tr><tr><td>准确率提高</td><td>26.6%</td><td>17.4%</td><td>5.0%</td></tr></table></body></html>

我们也把 TRM预测模型与常用的支持向量机（SVM）和反向传播（BackpropagationB-P）回归模型进行了对比，实验结果表明，当参与预测的接入点个数逐渐增多时，TRM能表现出更好的定位精度和稳定性。如图7所示。

![](images/1216c8dcb3a8acb637518e5d8800043309b77cb0eb8e13c96b7ed69c4b9a15ab.jpg)  
图7.三种方法的定位准确率比较

# 2.5面向接入点缺失与稀疏条件的定位研究

# 2.5.1背景

室内定位的难点在于环境的改变会影响定位的精度。现有的室内定位算法大多仅关注外界天气及用户设备，很少考虑信源自身的变化，均以信源稳定为定位假设前提。而此假设在实际应用中却很难满足。本节讨论实际环境中存在的动态信源问题，并提出有效的解决方法。

动态信源问题是指定位系统中某些信号源由于损耗、断电等原因发生故障而使相应接入点的信息缺失，或者分布较稀疏，从而使得室内信号场分布发生改变，导致室内定位精度下降的问题。在目前的室内定位研究中，此问题经常被忽略，或使用某固定值（如一$\boldsymbol { 1 0 0 } \mathrm { d B m } \mathrm { \cdot }$ ）对缺失的信号进行填补，这样实际上会导致测试数据与训练数据分布不一致，进而大大降低了定位精度。我们在论文[21]中从动态信源的有效恢复问题着手，研究如何增强系统鲁棒性。

![](images/9b1a2e863473d9391e23021c0ffa39f5a211bffb8d1cce8cb86d64179a354ac4.jpg)  
图8.FixMR算法流程图

# 2.5.2FixMR和FixMRT方法

为解决动态信源问题，我们采用基于流形正则化框架的FixMR方法对动态信源问题进行了研究。FixMR 方法由三部分构成，包括损失函数、控制函数复杂度的正则化项、控制函数平滑性的正则化项。FixMR方法有效地利用两阶段数据所共有的局部线性结构，构造出信源之间的回归函数，通过此函数有效计算出缺失信号值。图8为FixMR算法流程图。

在FixMR的基础上，我们又提出了具有自适应邻域选取功能的缺失信号预测算法FixMRT。FixMRT将自适应邻域选取思想引入算法当中。自适应邻域选取思想是指根据流形曲率的变换，自适应地选取邻近点从而能更精确地描述曲线结构，达到正确估计信号值的目的。图9为自适应选取邻域点流程图。

# 2.5.3试验结果：

![](images/58da2982d9a2d6e43c20c51658de4fdec3da7b6dbda7cecd72ad7042c6950451.jpg)  
图9.自适应选取邻域点流程图

持向量回归（support vector machine for regression,SVR）、RLS 做对比的实验结果图，横坐标为信号误差，纵坐标为准确率。

1.0 8888@ 86088088 风 FixMR 0.8 X o000o0 ☆ RLS 田 SVR 斑舞典 0.6 D 品 中 . 品 D 区 品8 0.4 国 田 8:9 0.2 区 中 0 0 10 20 3040 50 信号估计误差(dB)

![](images/3be2f420f57af4a4c5238f4e19d489a646b4255238002df8c9f8375c93f9c858.jpg)  
图10为FixMR与k-近邻法、支  
图10. 恢复信号准确率比较图  
图11. 未标定数据所占比例与信号估计误差关系图  
图12. 恢复信号准确率比较图  
图13. 定位准确率比较图

图11是标定数据与未标定数据的比率对信号估计精度的影响实验图，横坐标表示标定数据与未标定数据的数量比，纵坐标表示信号误差。

1.0 田 中由扭租出租出出租扭出出出由Doo0o8888@88 L 区 FixMR800.8 新 . 00000000 ☆ RLS8 □ 白 SVR甲 田密典 甲 田 □ D -- KNN0.6 + FixMRT0.邮 中品品0.4 的区0.200 10 20 30 40 50信号估计误差(dB)

1.0  
0.9  
0.8 q Fix(-100)FixMRT  
0.7 RLS.· SVR  
0.5 -田 KNN  
0.4 3 Prime  
0.3  
0.2  
0.1 2345678910距离误差（米）

如实验结果所示，FixMR 算法与 $\mathbf { k }$ -近邻法、支持向量回归、LRS方法相比，有着更高的精度。其他方法并未利用到信号在低维流形空间上的一致性，而一味地在信号空间求出回归函数，因此并未能精确反映原貌。FixMR 算法在信号恢复上的准确率在10dBm以内达到了 $8 5 \%$ 。

图12为FixMRT与其他方法实验结果对比图，横坐标表示信号误差值，纵坐标表示某一误差范围内，信号估计正确的概率。图13是定位精度比较图，横坐标代表定位误差距离，纵坐标代表某一距离内所能达到的定位准确率。图中起始曲线（Prime）表示不存在动态信源问题时的定位曲线，Fix(-100)曲线表示将异常信源信号值均统一地用一100dBm 填充而进行定位的曲线。

表4为FixMRT与其他方法在定位误差距离分别为3米和1米时的定位准确率比较表。

表4. 定位准确率比较   

<html><body><table><tr><td></td><td>Prime</td><td>FixMRT</td><td>FixMR</td><td>k-近邻法</td><td>Fix(-100)</td><td>支持向量回归</td><td>RLS</td></tr><tr><td>3m</td><td>90%</td><td>88%</td><td>82%</td><td>77%</td><td>75%</td><td>73%</td><td>67%</td></tr><tr><td>1m</td><td>49%</td><td>40%</td><td>31%</td><td>23%</td><td>22%</td><td>20%</td><td>15%</td></tr></table></body></html>

由图12可看出，FixMRT在 $1 0 \mathrm { d B m }$ 以内的信号在 $90 \%$ ，而FixMR、 $\mathbf { k }$ -近邻法、支持向量回归、RLS分别为 $85 \%$ 、 $70 \%$ 、 $55 \%$ 以及 $48 \%$ 。这正是由于FixMRT增加了自适应选取邻域点思想，因而提高了信号预测精度。由图13可看出，FixMRT 精度高于其它方法，同时逼近于用真实数据定位准确率(Prime 曲线)，在 $3 \mathrm { m }$ 以内可达到 $88 \%$ ，如表4。原因归结于，相比于FixMR，FixMRT添加了自适应邻域选取算法，因而提高了信号估计率以及定位精度。

# 2.6基于单接入点的房间级定位研究

# 2.6.1背景

传统的基于机器学习的室内定位方法往往是利用可同时接收到的多个接入点信号来进行定位，而在有些实际情况中，只能收到一个无线信号源的稳定信号。比如，游览者在博物馆参观，消费者在超市购物等等。在这类场合通常也只有很少量无线信号源的信号可稳定、持续地接收到。因此，能基于单接入点进行一定精度的定位在应用中具有重要意义。

针对上述应用环境的实际问题，我们在论文[22]中提出的基于无线本地网 WLAN 的室内定位技术，将电磁波衰减模型和基于机器学习的定位方法有效地进行结合，提出了一种基于统计与规则结合的单源室内定位方法--MuIMR算法。

# 2.6.2MuIMR算法

算法的基本思想是同时利用电磁波衰减模型方法和机器学习的定位方法分别获取与单源信号的距离信息和角度信息，由此推算出定位信息。单接入点定位的主要思想如图14所示。

在离线训练阶段，移动终端在无线覆盖区域内采集数据。对于信号强度与距离对应的样本集，依据电磁波衰减规则，利用多元线性回归模型进行参数估计，得出符合环境的无线信号发射源与移动终端接收机之间距离的衰减函数关系 $\pmb { d } = \pmb { P } ( s )$ 。对于信号强度与角度对应的样本集进行统计学习，采用基于流行正则化的机器学习方法得出信号强度与角度之间无线信号发射源与移动终端接收机之间角度的映射函数关系 $\scriptstyle { \theta = f ( s ) }$ 。这里， $\textbf { \^ s }$ 表示信号强度， $\textbf { \em d }$ 表示距离， $\theta$ 表示角度。

![](images/bab8dc44e6c65bc38ccbcd2b227e3971eef143856b23695e69bc55e93f1004cc.jpg)  
图14. 单接入点定位的主要思想

![](images/441bd7d0c1b5ed1760c457e67bce4b95aab1a34d8bfa52bcb5d15c8f9164bed2.jpg)  
图15. 多元线性回归分析曲线拟合效果图

在线定位阶段，移动终端将接收到的信号强度值作为输入，根据两个函数关系式可以计算出当前所在位置与无线信号源的距离 $\pmb { d }$ 和夹角 $\theta$ ，已知无线信号源的固定位置 $( \pmb { x } _ { 0 } , \pmb { y } _ { 0 } )$ ，然后利用三角函数关系 ${ \pmb x } = { \pmb x } _ { 0 } + d \cos ( \theta )$ ， $\mathbf { y } = \mathbf { y } _ { 0 } + \pmb { d } \sin ( \theta )$ ，就能定位出移动终端当前所在的具体位置。

表5. 三种回归分析方法的实验结果比较  

<html><body><table><tr><td>参数估 计方法</td><td>PL(d0) [dBm]</td><td>n</td><td>WAF [dB]</td><td>R</td><td>0</td><td>s2</td><td>p</td><td>F</td></tr><tr><td>线性</td><td>-52.36</td><td>6.325</td><td></td><td>0.214</td><td>6.538</td><td>42.748</td><td>-0.214</td><td>1.911</td></tr><tr><td>补偿式</td><td>-38.38</td><td>2.996</td><td></td><td>0.850</td><td>4.936</td><td>24.364</td><td>0.850</td><td>413.11</td></tr><tr><td>多元</td><td>-40.249</td><td>2.341</td><td>1.607</td><td>0.861</td><td>4.546</td><td>20.669</td><td>0.861</td><td>453.95</td></tr></table></body></html>

# 2.6.3试验结果

# 1．基于传播规则的距离估计

我们通过对一元线性回归分析、补偿式线性回归分析和多元线性回归分析3种回归方法进行数学建模，对所建立的模型进行参数估计、回归方程的显著性检验、相关系数及其显著性检验，在求出线性回归方程后，对线性回归方程同试验数据拟合的效果进行了检验。

表5比较了三种回归分析方法的实验结果。可以看出，多元线性回归方程的函数逼近效果最佳，试验数据拟合的程度也最高。图15为多元线性回归分析曲线拟合效果图。如图所示，多元线性回归分析方法比较准确、客观地描述了对数距离路径损耗模型中信号强度与距离之间的关系。

经过综合分析，MuIMR算法选择了多元线性回归分析方法。

# 2．基于流行正则化的角度预测

我们将流形正则化（ManifoldRegularization，MR）与支持向量回归、（反向传输Backpropagation，BP）神经网络两种回归方法进行比较。表6为三种方法的性能比较表。

从表6中可以看出，流形正则化方法比支持向量回归和反向传输方法的回归精度要

高，而且拟合曲线的逼近程度也最好。

经过实地验证，本节介绍的定位方法行之有效，定位精度能达到房间级，能满足一定的实际应用需求。

表6. 三种预测方法的性能比较  

<html><body><table><tr><td></td><td>验证实验</td><td>角度预测实验</td></tr><tr><td>流形正则化</td><td>0.0012</td><td>1.3983e+4</td></tr><tr><td>支持向量回归</td><td>0.0024</td><td>1.7834e+4</td></tr><tr><td>反向传输神经网络</td><td>0.0035</td><td>1.6641e+4</td></tr></table></body></html>

# 2.7免标定定位方法研究

# 2.7.1背景

传统的基于机器学习的定位算法一般分为两个阶段：离线训练阶段和在线定位阶段。在离线训练阶段，通过采集大量的标定样本，建立起信号强度空间到位置空间的映射关系（Radio Map)；在线定位阶段，利用实时采集到的信号强度和上述映射关系来得到估计的位置。而基于信号强度-空间位置映射方法的一个难题是必须采集大量的标定数据才能达到较好的定位精度。这就需要在训练阶段人工持移动设备在目标区域内各点收集接入点的信号强度，这是一项费时费力的工作。这也被公认是该类技术向实际应用推广的最大障碍之一。因此，如何避免离线的数据标定工作成为人们目前研究的热点。

# 2.7.2免标定自适应定位技术

我们针对这个问题提出了一种免标定自适应定位技术[23]。其主要思想是通过在室内环境中预设一些位置已知的参考点来提供动态反映时空变化的基准信息，同时使用从信号强度中提取的差值特征作为计算依据，使用正则化最小二乘法计算出物理位置和信号强度差值特征间的回归模型，用于移动终端的位置估计。

我们采用从任意两个接入点接收到信号强度的差值作为特征。这样，在离线训练阶段，首先需要从训练设备采集到的接收信号强度（RSS，received signal strength）提取差值特征，然后使用提取后的特征向量和对应的物理位置来建立信号强度-空间位置映射；在线定位阶段，首先采集测试设备的接收信号强度，提取差值特征向量后便可用来在信号强度-空间位置映射中进行匹配和搜索，进而根据匹配项的位置信息估计出测试设备的位置。基于信号强度-空间位置映射的技术可以分为基于决策和基于概率两大类：基于决策的技术以最近近邻算法（Nearest Neighbor，NN）为代表而基于概率的技术以贝叶斯推断算法（BayesianInference，BI）为代表。为了验证差值特征的有效性，我们分别将提取的差值特征同这两种典型的定位算法相结合，分别记为DIFF-NN 和DIFF-BI，并在实际环境中采集数据进行了实验验证。

# 2.7.3试验结果

实验环境的面积为 $2 7 \mathrm { m } { \times } 1 7 \mathrm { m }$ ，一共划分为161个格点。使用IBMR60笔记本以5HZ的频率采集了 $1 6 1 \times 2 0 0$ 组的数据，记为DataSet1。然后使用多普达O2手机以0.5HZ的频率采集了 $1 6 1 \times 1 0$ 组的数据，记为DataSet2。并选取DataSet1作为训练数据集，DataSet2作为测试数据集。使用训练数据集通过最近近邻算法和贝叶斯推断算法方法训练得到信号强度-空间位置映射，然后将其应用于测试数据集得到估计坐标。由于WLAN信号的强噪声性，在使用基于决策的技术定位时，需要对数据进行均值或中值滤波处理。而在使用基于概率的技术时，不需要进行均值处理。图16为四种方法同最近近邻算法结合得到的累积概率分布结果图。图17为四种方法同BI算法结合得到的累积概率分布结果图。从实验结果可以看出，无论使用最近近邻算法还是贝叶斯推断算法，直接使用接收信号强度进行定位的效果都是最差的， $3 \mathrm { m }$ 之内的定位准确度只有 $20 \%$ （最近近邻算法）和 $12 \%$ （贝叶斯推断算法)，这也说明了处理设备间信号差异的必要性。同时也可以看出，本文所提出的使用差值特征的算法在 $3 \mathrm { m }$ 之内的定位准确率分别达到 $62 \%$ （最近近邻算法）和 $58 \%$ (贝叶斯推断算法)，性能要优于接收信号强度算法和基于比例特征的算法（最近近邻算法： $42 \%$ ，贝叶斯推断算法：$49 \%$ )；而且性能也不低于需要额外标定数据的线性映射方法（最近近邻算法： $61 \%$ ，贝叶斯推断算法： $52 \%$ )，基于贝叶斯推断算法的差值特征算法DIFF-BI性能甚至整体上都要优于线性映射方法LINEAR-BI。

![](images/fb82c18d9dfd2d9f141c5ee9d01dfaa8416fe26a72d3227bbedda0837b9bdfc8.jpg)  
图16. 最近近邻算法系列算法得到的定位误差累积概率分布图

![](images/f7b6ebb2ec4aeec11cabcc1a6f043e3686c5fad9d4067c6e8a48ff6048ac2ddf.jpg)  
图17. 贝叶斯推断算法系列算法得到的定位误差累积概率分布图

![](images/f226b713e761945488b1816a14bc69b18e39f071931b87a21e171c958de1764b.jpg)  
图18. DataSet1 参考点分布1下的平均定位误差

![](images/586cc53d263b8a6d736ceb42b4e8b684eb590f2dcf2554fa39a19059a87480ea.jpg)  
图19. DataSet1 参考点分布2下的平均定位误差

接着我们又把该技术同参考点模型相结合，进一步完善免标定的自适应定位技术。实验场景同上，参考点分布1是指参考点基本成均匀分布，且尽量位于各房间的中心；参考点分布2是指参考点也基本成均匀分布，但是均位于各房间的角落。然后我们使用了基于传播模型的算法（PM）、基于特征提取的算法（CALIBREE）、最近邻算法（NN-DIFF）、正则化最小二乘法（RLS-DIFF）和支持向量回归（SVR-DIFF）五种算法进行位置估计。图18为在DataSet1参考点分布1下的平均定位误差的结果图，而在DataSet1，参考点分布2下的累积分布概率如图19所示。

从以上实验结果可以看出，该算法在无需额外标定数据的条件下，可以很好地适应环境的变化和保证一定的定位精度，同时对参考点分布的变化具有较好的鲁棒性。

# 2.8基于WIFI定向特征的定位研究

# 2.8.1背景

在基于信号强度的室内定位方法中，由于信号发射源也就是接入点是向四周以同心圆模

式发射信号，因而距接入点同等距离的地方信号强度相差不是太大，所以为了提高定位性能，通常需要使用多个接入点，来缩小误差范围。这给一些应急场合下的即时定位需求带来了很大挑战。

# 2.8.2定向天线定位技术

针对以上问题我们提出了一种解决思路，即将基于信号强度的方法与无线信号的定向特征结合起来[24]。定向天线就是指在某一个或某几个特定方向上发射及接收电磁波特别强，而在其它的方向上发射及接收电磁波则为零或极小的一种天线。当我们引入定向天线来发射信号后，就可以把信号的发射区域从一个圆形缩小到一个扇形，这样就可以更进一步地提高定位精度。其原理如图21所示。图21（A）使用一个全向接入点，向四周发射信号，所以估计区域是整个圆。（B）使用一个定向接入点，向某个角度发射信号，而这个角度是与定向天线的波瓣角度密切相关，所以估计区域就缩小为一个扇形。（C）使用两个全向接入点，估计区域就变成两个圆形的叠加区域，明显减小。（D）使用两个定向接入点，所以估计区域也就是是两个扇形的叠加区域，也明显减小。由于定向天线的这一特性，所以我们在试验中采用两个定向天线，即定向接入点。

此方法的基本思想是，接入点通过定向天线发射信号。WiFi设备通过接收这些信号来估算到接入点的距离，从而估计终端的位置。这个方法结合了定向天线定向的优势和信号强度方法不需要多余传感器的特点。这样就为WiFi定位提供了一种易于实施、节省开销、且可用于室内大范围的高精度的解决方案。

![](images/aaa4d7f30c0e3e20e4aaa306121450044d27f24d5be83c1af131248cd661c785.jpg)  
图20. 定向天线

![](images/e077b985b9102c42836ff8c9da66e2c7bf5ac2321474db194eb823277c101a04.jpg)  
图21. 非定向（A,C）与定向（B，D）对比图

# 2.8.3试验结果

我们的实验环境是约 $1 5 \mathrm { m } \times 2 4 \mathrm { m }$ 的区域，共划分为 75个格子。两个定向接入点，一个为放在东面正中间的AP1，另一个为放在北面正中间的 AP2。使用 Moto A3100手机采集了$7 5 \times 1 0 0$ 组的数据。其信号强度分布如图22所示，从图中可以很明显的看出，在定向天线的辐射角范围内信号强度很强，而在辐射角范围外信号强度明显减小或者没有信号。如果两个信号分布叠加，就把整个试验区域划分为一个个小的区间（如图23)。最后就可以通过k-近邻分类算法进行一系列的位置估计。结果如表7所示：

表7是在2个接入点时，训练集分别为随机取的5个点、9个点、13个点、21个点;测试集是所有的数据；第二列的数据是相应的定位准确率。

从以上实验结果可以看出，该技术在接入点数量为2的情况下也能达到比较理想的定位精度。

![](images/06a50992ab946a2464323400fdfc331fbd8b67610fb61fa08f679c93f8d1602f.jpg)  
图22. 使用了定向天线以后的信号强度分布图

表7. 训练样本的数量和定位准确率统计表  

<html><body><table><tr><td>训练样本的数量</td><td>k-近邻法</td></tr><tr><td>5</td><td>0.6892</td></tr><tr><td>9</td><td>0.8267</td></tr><tr><td>13</td><td>0.7689</td></tr><tr><td>21</td><td>0.8056</td></tr></table></body></html>

![](images/e42e6bbe217228150cf856091facb8d6c13ebe118b3176e95fbe0ec8c86fd17d.jpg)  
图23. 两接入点信号的交合示意图

# 3 室内定位应用系统

# 3.1室内定位应用系统

过去的几年中，WiFi 定位技术在研究领域日渐成熟的同时，在市场上的应用也迅速发展。因为基于WiFi标准解决方案的整个定位系统特点在于能够较好地利用已有的基础设施而不需要增加额外硬件，因此企业可以迅速安装这种系统，从而显著降低了初始成本和长期支持成本。

目前在美国和欧洲基于WiFi定位技术的RTLS系统已经成为一种主流技术，主要应用于医院追踪资产、设备和病人。及时了解和掌握关键工作人员、资产和医疗设备的实时位置信息已成为医疗保健机构的主要任务之一，这能帮助医疗保健机构降低成本、改善工作流程和提高病人护理服务质量[25\~28]。在零售店内，当消费者进门时，即被提供一个实时定位设备。在购物时，RTLS系统能够确认消费者在店内的位置，在店内的消费时间，还可以确认消费者们感兴趣的物品以及哪个位置消费者出现次数最频繁等[29]。WiFI定位也应用于互联网搜索引擎[30]。用户可以确切把握自己的位置；也可随时查询距离最近的比萨店在哪。WiFi定位技术甚至已应用于儿童监护。如在购物时可以给儿童安置一小型WiFi信号发射器，让其在玩具区玩耍，同时监护人可安心购物，随时掌握幼儿的行踪。

# 3.2基于位置的多媒体服务系统LMSS

我们在无线定位研究成果的基础上，搭建了基于位置的多媒体服务原型系统，在中科院计算所实际环境中部署应用系统LMSS[31],能够根据移动用户的位置提供定制化的视频。

LMSS的系统架构如图24所示。

LMSS包括两部分：定位和视频服务。当移动用户携带移动设备进入某个房间时，LMSS根据移动设备的不同位置智能地提供不同的视频服务。我们在笔记本和智能手机上都测试了该功能，部分客户端截图如图25和26所示。

![](images/32eef7eca371ba00e67d976e846db63ed7a2690c345d6c9679b218208a65df3e.jpg)  
图24. LMSS系统架构

![](images/99b12321c16a26160e162f986667aaa7df293db152ce81b9704907fc5a6fcff8.jpg)  
图25. LMSS的笔记本客户端效果图

![](images/da3bae1100c6d7dc206679048603a515bd5023333e3382ff283f97b698832c18.jpg)  
图26. LMSS的笔记本客户端效果图

# 4 结论与下一步工作

综上所述，基于WiFi的室内定位技术及系统得到广泛关注与应用。已有的室内定位技术和系统的开发和应用，已经极大地简化和方便了人们的工作，使信息获取更便利。随着新的定位技术和定位方法的出现，定位精度将会越来越高，应用场景也会越来越多。

目前，基于WiFi信号的室内精确定位技术主要采用机器学习的方法，即事先采集大量训练数据并进行标定，然后训练定位模型，最后投入使用。这样，人为参与的工作量非常大，给系统开发和使用带来很多困难。为克服这一缺点，必须找到能够快速建立定位模型的技术。我们今后的工作重点包括以下几个方面：

(1)．进一步研究训练数据的免标定技术，大幅度减少标定数据的工作量;  
(2)．研究接入点数量及其分布与模型精度的关系，尽可能减少参与训练模型的接入点数量;  
(3)．研究WiFi信号的衰减模型，总结影响定位精度的经验参数，探索自适应的定位算法，力图寻找通用的定位模型或无需训练的定位算法；  
(4)．研究定向天线的特性，利用其能够提供方向信息的特点，进一步提高定位精度；  
(5)．关注其他传感器器件的发展状况，研究基于多传感器融合的定位算法。

# 参考文献：

[1] 王广运，郭秉义，李洪涛等，差分GPS 定位技术与应用，北京：电子工业出版社,1996.   
[2] Enge,P.,Misra,P.,Special Issue on Global Positioning System,Proceedings of the IEEE,1997,87(1): 3\~5.   
[3] Nissanka B.Priyantha,Anit Chakraborty，and Hari Balakrishnan.The CricketLocation-Support System[C].6th ACM/IEEE Intenrational Conference on Mobileee and Networking.MobiCom2000, 08/2000, Boston.   
[4] 顾永超，一种基于蓝牙技术的室内定位子系统的设计与实现，北京大学硕士学位论文,2009，北 京。   
[5] R.Want，A.Flopper,V.Falco， andJ.Gibbons.TheActiveBadgeLocationSystem[J].ACM Transactionson In formation Systems,10 (1):91-102,Ja nuary1 99.   
[6] T Liu,P Bahl,IChlamtac，Mobility modeling,location tracking,and trajectory prediction in wireless ATM networks，IEEE Journal on Selected Areas in Communication,1998,16(6).   
[7] J. Krumm and J.C.Platt“Minimizing Calibration Effort for an Indoor 802.11 Device Location Measurement System,”technical report, Microsoft Research,2003.   
[8] Hisashi Kashima, Shoko Suzuki, Shohei Hido,Yuta Tsuboi,Toshihiro Takahashi,Tsuyoshi Ide, Rikiya Takahashi, and Akira Tajima."A Semi-Supervised Learning Approach Using Spatio-Temporal Information for Indoor Location Estimation", IEEE Intelligent Systems,2008.   
[9] Anthony LaMarca,Jeffrey Hightower,Ian Smith and Sunny Consolvo. Self-Mapping in 802.11 Location Systems, In Proceedings of Ubicomp 20o5,Tokyo, Japan. September 2005.   
[10] Lin,Hsiuping and Zhang, Ying and Griss,Martin and Landa,Iya,WASP:an enhanced indoor locationing algorithm for a congested Wi-Fi environment,MELT'o9:Proceedings of the 2nd international conference on Mobile entity localization and tracking in GPS-less environments,2009.   
[11] P.Prasithsangaree,P.Krishnamurthy,P.K.Chrysanthis,On indoor position location with wireless LANs，in: Proc. IEEE International Symposium on Personal，Indoor,and Mobile Radio Communications (PIMRC'02),Lisbon, Portugal, 2002.   
[12] M.Youssef and A.Agrawala,\Small-scale compensation for wlan location determination systems," in Wireless Communications and Networking, 2003. WCNC 2003.2003 IEEE, vol.3,March 2003, pp. 1974-1978.   
[13] Hua-Yan Wang，Vincent Wenchen Zheng，Junhui Zhao,Qiang Yang:Indoor localization in multi-floor environments with reduced effort.PerCom 2010: 244-252.   
[14]Shen-Hai Shee, Kuochen Wang,and Yi-Ling Hsieh，“Color-theory-based Dynamic Localization in Mobile Wireless,Sensor Networks.” in Proc.of Workshopon Wireles, Ad Hoc,Sensor Networks, pp. 73-78, Aug. 2005.   
[15]Y. Chen,Q. Yang,J. Yin, X. Chai ，“Power-Efficient Access-Point Selection for Indoor Location Estimation,”IEEE Transactions On Knowledge And Data Engineering,Vol.18,No.7,July 2006.   
[16]Hongbin Li, Xingfa Shen,Jun Zhao, Zhi Wang,Youxian Sun,INEMO: Distributed RF-Based Indoor Location Determination with Confidence Indicator, EURASIP Journal on Advances in Signal Processing, 2008.05.   
[17]Belkin, M., Niyogi, P.,& Sindhwani, V.(2004b)，Manifold regularization: A geometric framework for learning from examples， Technical Report TR-2004-06，University of Chicago.   
[18]Zhuo Sun, Yiqiang Chen, Juan Qi and Junfa Liu. Adaptive Localization Through Transfer Learning in Indoor Wi-Fi Environment. The Seventh International Conference on Machine Learning and Applications (ICMLA'08).   
[19] 张亚东，室内无缝三维定位技术研究，中国科学院计算技术研究所硕士学位论文，2010，北京。   
[20] Junfa Liu,yiqiang Chen, Yadong Zhang, Transfer Regression Model for 3D location Estimation. MMM 2010, Chongqing, China,2010.   
[21]朴松梅，室内定位系统鲁棒性研究，中国科学院计算技术研究所硕士学位论文，2009，北京。   
[22] 陈振宇，统计与规则结合的单源室内定位方法研究，湘潭大学硕士学位论文，2009，湘潭。   
[23] 董芳芳，环境无关的免标定自适应室内定位方法研究，中国科学院计算技术研究所硕士学位论 文，2009，北京。   
[24]zhaomi,yanghua,yiqiang Chen, junfa liu,Directional Wi-Fi Based Indoor Location System for Emergency. UIC 2010, Xi'An, China,2010.   
[25]Hub,A.,Diepstraten, J.,Ertl,T.“Augmented Indoor Modeling for Navigation Support for the Blind". Proceedings of the 2O05 International Conference on Computers for People with Special Needs,Las Vegas,Nevada,USA, 54-59,2005.   
[26]Jovanov,E.， Milenkovic，A.， Ott,C.， and de Groen,P.C.，A Wireless Body Area Network of Inteligent Motion Sensors for Computer Assisted Physical Rehabilitation. in Journal of NeuroEngineering and Rehabilitation,2(6).March 2005.   
[27]C. Oto,A. Milenkovic,C. Sanders, and E. Jovanov. System architecture of a wireless body area sensor network for ubiquitous health monitoring.Journal of Mobile Multimedia,1(4):307--326,2006.   
[28]Fry EA, Lenert LA. MASCAL: RFID tracking of patients, staff and equipment to enhance hospital response to mass casualty events.AMIA Annu Symp Proc. 2005:261-5.   
[29]Kolodziej, K. W.,& Hjelm, J. (2006). Local Positioning Systems: LBS Applications and Services. Boca Raton: Taylor & Francis Group..   
[30]1. Skyhook Wireless. Skyhook Wireles: How It Works: Wi-Fi Positioning. Last accessed: November 20,2008. Available: http://www.skyhookwireless.com/howitworks/wps.php.   
[31]孙卓，基于迁移学习的无线位置感知技术研究，中国科学院计算技术研究所硕士学位论文， 2009，北京。   
[32]htp://www.cse.ust.hk/\~qyang/ICDMDMC07/.

作者简介：

刘军发： 中科院计算所普适计算研究中心感知计算课题组 助理研究员liujunfa@ict.ac.cn赵中堂： 中科院计算所普适计算研究中心感知计算课题组博士研究生宁琼: 中科院计算所普适计算研究中心感知计算课题组硕士研究生陈益强： 中科院计算所普适计算研究中心感知计算课题组 研究员、博士生导师、副主任