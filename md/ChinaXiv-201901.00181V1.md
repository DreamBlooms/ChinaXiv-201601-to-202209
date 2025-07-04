# 基于PSO模式搜索的跌倒检测算法研究

任晓奎，李锋，程琳(辽宁工程技术大学 电子与信息学院，辽宁 葫芦岛 125105)

摘要：针对粒子群算法存在后期趋同性严重、收敛速度缓慢以及易陷入局部极小点等缺点，将模式搜索算法引入粒子群算法，对支持向量机参数进行优化，应用于跌倒检测中。首先，使用穿戴式设备收集跌倒检测数据集，将初始数据进行均值滤波以消除噪声的影响；然后，滤波后的数据特征提取，将提取的多维数据使用奇异值分解算法进行降维；最后，降维后的数据将用来检验粒子群模式搜索算法的优劣。通过与支持向量机算法和支持向量机算法加粒子群算法进行对比，粒子群模式搜索算法在跌倒检测中特异性和灵敏度都得到了提高。

关键词：跌倒检测；粒子群算法；模式搜索；降维；支持向量机中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.09.0747

Research on fall detection algorithm based on pso pattern search

Ren Xiaokui, Li Feng, Cheng Lin (SchoolofElectronics &InformationEngineering,LiaoningTechnical UniversityHuludaoLiaoningl251o5,China)

Abstract: Aiming at the shortcomings of particle swarm optimization (PSO)such as serious convergence,slow convergence and easy to fallinto local minimum,it introduced the patern search algorithm into PSO tooptimize theparameters of supportvector machine (SVM)and applied tofalldetection.Firstly,itused a wearabledevice tocollectthefallto the detectiondataset,andflteredthe initial datatoeliminate the influenceof noise.Secondly,itextractedthefiltereddata featureand reduced the dimensionality of theextracted multi-dimensional data by Singular value decomposition algorithm(SVD).Finally,itwilluse thedimensionality-reduceddatatotestthePSO patersearchalgorithm.Compared with support vector machine (SVM) and support vector machine (SVM) plus particle swarm optimization (PSO），it improved the specificity and sensitivity of PSO in fall detection.

Key words: fall detection; particle swarm optimization; patern search; dimension reduction; support vector

# 0 引言

据联合国世界卫生组织统计，全世界每年估计有64.6万起致命跌倒事故发生，跌倒是造成意外伤害导致死亡的重要原因之一。当跌倒时，除了部分轻度跌倒的老人可以自救，其他严重摔伤的老人如果不能及时得到帮助，很可能导致严重后果，甚至对生命造成威胁。

因此，跌倒检测一直是人们的研究热点[1]。目前，跌倒检测基本可以划分成三类：a)摄像头视频检测[2.3]，分析视频图像中人体的轮廓、姿态等特征；b)专设场所环境变化检测[4-6]，使用超声波阵列，分析跌倒对地面的冲击状况等；c)可穿戴式传感器佩戴检测[7.8]，安装特定传感器，提取运动特征，并通过模式识别方法执行人体跌倒检测。然而由于视频检测涉及到用户隐私，专设场所受特定环境影响太大，且检测过程复杂、成本太高、范围有限，而基于可穿戴的设备凭借体积小、方便携带、保护隐私等优点，受到了大力发展。忽丽莎等人[9通过一篇综述来对穿戴式跌倒检测进行介绍，总结近些年的一些研究成果。

支持向量机在分类问题上显示出优秀的性能，而跌倒检测问题恰好可以视为二分类问题，但由于参数的设置会导致支持向量机性能的差别。粒子群算法是一种全局并行寻优算法，相比较于其他优化算法，具有进化时间短、寻优精度高等优点，因此在跌倒检测问题上PSO_SVM算法往往达到很好的效果。孙晓雯等人[10]先进行阈值判别，然后再使用PSO_SVM 进行二次判决。裴利然等人[I使用基于径向基函数的SVM，并用PSO算法对SVM参数进行优化。麻文刚等人[12]使用共轭梯度法对数据进行优化，采用阈值判定和PSO_SVM算法进行二级判决。

由于各种原因产生的噪声干扰会影响分类效果，所以要对数据进行预处理。麻文刚等人[12]使用共轭梯度法降低了非线性误差。王荣等人[13]使用卡尔曼滤波对姿态角进行了纠正。何坚等人[14]使用卡尔曼滤波对姿态角进行纠正，配合KNN算法对跌倒检测也达到了不错的效果。

在特征提取的过程中，特征向量越多，对行为的描述就越详细，但很可能导致维数灾难，这就需要降维处理。白勇等人[15]同过SVD 的方法提高了跌倒检测的灵敏度。李雷[16]则是改进KPCA算法达到了很好的效果。

虽然粒子群算法（PSO）应用广泛，但传统的PSO算法存在收敛速度慢、容易陷入局部极小值等缺点。为此，王喜宾等人[I7]将模式搜索算法引入PSO算法，得到很好的效果。

本文参考文献[17]，引入PSO模式搜索算法，将改进的粒子群算法应用跌倒检测中。首先，在算法初始阶段，对数据进行预处理，采用均值滤波对原始数据进行优化；接着，使用SVD算法[I6进行降维；然后，使用PSO模式搜索算法对SVM参数进行优化；最后，使用降维后的数据作为数据集，使用SVM算法进行跌倒检测。

# 1 SVM基本原理

支持向量机（support vector machine，SVM）在 20 世纪90年代由Vapink等人提出。SVM可以很好地应用于解决实际问题。其基本思想是利用核函数将输入样本空间映射到高维特征空间，在高维空间中实现最优的分类。

给定数据集： $T = \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) . . . ( x _ { n } , y _ { n } ) \}$ ， $i \in [ 1 , n ]$ 其中$x _ { i } \in R ^ { n }$ 为第 $i$ 个特征向量。 $\{ x _ { i } , y _ { i } \}$ 为样本点, $y _ { i } \in \{ - 1 , 1 \}$ 为 $x _ { i }$ 的标签。其中：分类超平面就是求函数，即

$$
\varphi ( w ) = \frac { 1 } { 2 } \left\| w \right\| ^ { 2 }
$$

s.t.

$$
y _ { i } [ w x _ { i } + b ] \geq 1 , i = 1 , 2 , \ldots l
$$

其中： $w$ 是法向量； $b$ 是常数项； $x _ { i }$ 为训练样本； $y _ { i }$ 为样本的类别。利用Lagrange 法并满足KKT条件，得到最优分类函数为

$$
\begin{array} { c } { { f ( x ) = s i g n \{ w ^ { * } x + b ^ { * } \} } } \\ { { = s i g n \{ \displaystyle \sum _ { i = 1 } ^ { k } \alpha ^ { * } y _ { i } ( x _ { i } \cdot x ) + b ^ { * } \} } } \end{array}
$$

其中: $\alpha ^ { * }$ 、 $b ^ { * }$ 为超平面的参数； $( x _ { i } \cdot x )$ 为向量的点积。当线性不可分时，在约束中引入松弛变量，并在目标函数中加入惩罚函数。最终演化成求下列函数的极小值：

$$
\phi ( w , \xi ) = \frac 1 2 ( w \cdot w ) + c ( \sum _ { i = 1 } ^ { l } \xi _ { i } )
$$

其中： $\mid c \mid$ 是惩罚系数，用于控制错误样本的惩罚。将核函数引入SVM，最常用的为径向基函数：

$$
K ( x _ { i } , x _ { j } ) = e ^ { - \gamma \left| x _ { i } - x _ { j } \right| ^ { 2 } } \ : , \ : r \ : > 0
$$

其中:参数 $\gamma$ 影响着SVM分类算法的复杂程度。

# 2 PSO 搜索算法

# 2.1 PSO 算法

粒子群算法(particle swarm optimization,PSO)的思想源于模拟鸟群的捕食行为，Eberhart和Kennedy于1995年提出。鸟群通过自己的经验和种群之间的交流来调整其搜索路径，以找到食物最多的地方。每只鸟的位置/路径是独立变量的组合，每个到达点的食物密度是函数值。在PSO算法中，根据各粒子或群体的经验更新速度和位置，从而找到最优解。

在 $D$ 维空间中，有 $N$ 个粒子，粒子 $i$ 位置为 $x _ { i }$ ，适应函数为 $f ( x _ { i } )$ ，粒子 $i$ 速度为 $\nu _ { i }$ ，粒子 $i$ 个体经历过的最好位置为 $p _ { b e s t }$ ，种群所经历过的最好位置为 $g _ { b e s t }$ 。第 $\boldsymbol { d }$ 维的位置变化和速度变化范围分别为 $[ x _ { \mathrm { m i n } , d } , x _ { \mathrm { m a x } , d } ]$ 和 $[ - \nu _ { m a x , d } , \nu _ { \mathrm { m a x } , d } ]$ ，若 $\nu _ { i d }$ 或 $x _ { i d }$ 超出了边界值，则限制为该边界值。

其迭代过程为

$$
\nu _ { \mathrm { i d } } ^ { \mathrm { k } } = w \nu _ { \mathrm { i d } } ^ { \mathrm { k } \cdot 1 } + c _ { 1 } r _ { 1 } ( p b e s t _ { i d } - x _ { i d } ^ { k - 1 } ) + c _ { 2 } r _ { 2 } ( g b e s t _ { d } - x _ { i d } ^ { k - 1 } )
$$

$$
x _ { i d } ^ { k } = x _ { i d } ^ { k - 1 } + \nu _ { i d } ^ { k - 1 }
$$

其中： $\nu _ { i d } ^ { k }$ 和 $x _ { i d } ^ { k }$ 分别为第 $k$ 次迭代粒子 $i$ 飞行速度和位置矢量的第 $^ d$ 维分量； $c _ { 1 }$ 和 $c _ { 2 }$ 是调节学习步长的常数； $r _ { \mathrm { i } }$ 和 $r _ { 2 }$ 是[0,1]的随机数，增加搜索随机性； $w$ 用来调节解空间的搜索范围。

设定阈值 $\varepsilon$ 以及最大迭代次数，若满足阈值或最大迭代次数，则迭代终止。此时 $g _ { b e s t }$ 为最优解，SVM最优参数为当前粒子位置。

$$
\left| \frac { f ( x _ { i d } ^ { k } ) - f ( x _ { i d } ^ { k - 1 } ) } { f ( x _ { i d } ^ { k } ) } \right| \leq \varepsilon
$$

# 2.2PSO 模式搜索算法

模式搜索算法也称为Hooke-Jeeves方法。该算法从初始基点开始，交替地进行轴向搜索和模式搜索。从坐标轴的方向进行轴向搜索以确定新的基点和函数下降的方向；沿着两个基点之间的线进行模式搜索使函数下降得更快。模式搜索算法具有较强的局部搜索能力，但迭代次数多、计算量大，容易使目标函数陷入局部极小，全局搜索能力差。PSO算法具有更短的进化时间和更高的精度。因此，将模式搜索算法与粒子群优化算法相结合，充分利用了粒子群优化算法和模式搜索算法的优点，进行PSO模式搜索算法。

# 3 PSO模式搜索算法

# 3.1数据预处理

将传感器安置于腰部，通过人体活动产生传感器信号进行数据处理，判断人体是否跌倒。由于加速度和角速度的变化是实时的、连续不断的，所以对数据流的处理非常困难。利用加速度传感器采集的人体姿态加速度数据依次记为$a _ { x } ( t ) \ , a _ { y } ( t ) \ , a _ { z } ( t )$ ，陀螺仪的数据记录为 $m _ { x } ( t )$ 、 $m _ { y } ( t )$ 、， $m _ { z } ( t )$ 因此采集的原始数据为

$$
\left\{ \begin{array} { l l l l l } { a _ { x } ( t _ { 1 } ) } & { a _ { x } ( t _ { 1 } ) } & { \ldots } & { a _ { x } ( t _ { n } ) } \\ { a _ { y } ( t _ { 1 } ) } & { a _ { y } ( t _ { 1 } ) } & { \ldots } & { a _ { y } ( t _ { n } ) } \\ { a _ { z } ( t _ { 1 } ) } & { a _ { z } ( t _ { 1 } ) } & { \ldots } & { a _ { z } ( t _ { n } ) } \\ { m _ { x } ( t _ { 1 } ) } & { m _ { x } ( t _ { 1 } ) } & { \ldots } & { m _ { x } ( t _ { n } ) } \\ { m _ { y } ( t _ { 1 } ) } & { m _ { y } ( t _ { 1 } ) } & { \ldots } & { m _ { y } ( t _ { n } ) } \\ { m _ { z } ( t _ { 1 } ) } & { m _ { z } ( t _ { 1 } ) } & { \ldots } & { m _ { z } ( t _ { n } ) } \end{array} \right.
$$

由于传感器采集的数据受到噪声的干扰，所以在对采集的数据进行分析之前，需选择有效的方法去噪，以提高跌倒检测精度。这里使用均值滤波方法，可以消除传感器数据中的毛刺部分，既能保持原有信息，又能去除噪声的干扰。

# 3.2特征提取与降维

在特征提取的过程中，特征向量越多，对行为的描述就越详细，但很可能导致维数灾难。既要保证对行为的刻画，又要使数据处理变的不是过于复杂，就需要对特征向量进行降维。

在穿戴式跌倒检测中，由于利用穿戴式设备获取的都是信号源，无法形成有效的数据集直接用于训练分类方法，所以提取合理的跌倒特征向量集[18]是必需的。常见的时域特征统计量如表1所示。

表1常见统计特征向量  
Table1 Common statistical feature vectors   

<html><body><table><tr><td>特征值</td><td>符号</td><td>特征值</td><td>符号</td></tr><tr><td>均值</td><td>avg</td><td>相关系数</td><td>r</td></tr><tr><td>标准差</td><td>Sd</td><td>最大值</td><td>Max</td></tr><tr><td>偏度</td><td>Sk</td><td>最小值</td><td>Min</td></tr><tr><td>峰度</td><td>Ku</td><td>均值趋势</td><td>avgT</td></tr><tr><td>加速度幅度面积</td><td>SMA</td><td>标准差趋势</td><td>sdT</td></tr><tr><td>能耗</td><td>E</td><td>最大差值</td><td>△</td></tr></table></body></html>

基于SVD算法能够较好地分离出有用的特征信息，利用SVD降维能够保留大部分有用信息且维度降低。

$$
A _ { m \times n } = U _ { m \times n } \times \Lambda _ { m \times n } \times V _ { _ { m \times n } } ^ { T }
$$

其中： $A _ { m \times n }$ 表示 $m$ 个样本，每个样本对应 $n$ 个特征值； $U$ 和 $\Lambda$ 为正交阵； $\boldsymbol { V }$ 为非负对角阵。

根据SVD思想，对应于前 $\mathbf { \xi } _ { l }$ 个主成分包含的信息最大，因此，提取前 $\mathbf { \xi } _ { l }$ 个主成分作为新的降维数据。

$$
A _ { _ { m \times l } } ^ { \prime } = U ( : , 1 : l ) \times \Lambda _ { _ { l \times l } }
$$

其中： $A _ { _ { m \times I } } ^ { ' }$ 为新的特征空间； $U ( : , 1 : l )$ 为前 $\mathbf { \xi } _ { l }$ 列对应的矩阵； $\Lambda _ { l \times l }$   
为前 $\mathbf { \xi } _ { l }$ 个特征值对应的对角阵。

由于SVD与PCA基本类似，根据主成分分析法，当奇异值越大，所包含的信息越多，所以当使用SVD进行降维得

到新的特征空间 $A _ { _ { m \times I } } ^ { ' }$ ，能够最大可能地保有原来的信息，但使用新的特征集可以明显地降低运算量。因此，新的特征集都是有用的特征信息。

# 3.3PSO 模式搜索算法对SVM参数优化

PSO 模式搜索的算法步骤：

a）读取跌倒检测数据样本，并随机产生(c,y)作为粒子的初始位置 $x _ { i }$ 。

b）计算各粒子适应度函数值，以分类误差作为粒子的适应度评价函数。

分类误差公式为

$$
\displaystyle {  1 - \frac { 1 } { n } \sum _ { i = 1 } ^ { n } | \frac { T _ { i } } { T _ { i } + F _ { i } } | }
$$

其中： $T _ { i }$ 和 $F _ { i }$ 分别是正确分类样本数和错误分类样本数。

c）根据式（5）和（6）更新粒子的位置和速度。

d）令式（3）得到的 $g b e s t = p b e s t _ { k } \in ( c , \gamma )$ 作为模式搜索的初值，并给定单位向量 $e ^ { j }$ 。初始步长 $\gamma ^ { 0 } { = } ( \gamma _ { 1 } ^ { 0 } , \gamma _ { 2 } ^ { 0 } , { \ldots } , \gamma _ { n } ^ { 0 } ) ^ { T } > 0$ ，加速度系数 $a > 0$ ，收缩系数 $\lambda \in ( 0 , 1 )$ ，精度 $\varepsilon$ ，置$k { = } 0$ ， $y = p b e s t _ { k }$ ， $j { = } 1$ 。

e）从 $y$ 出发，依次做平行单位矢量 $e ^ { j }$ 的轴向探测移动：

(a)若 $f ( y + \gamma _ { j } ^ { k } e _ { j } ) < f ( y )$ ，则令 $\scriptstyle y = y + \gamma _ { j } ^ { k } e _ { j }$ ，否则转b）；

(b)若 $f ( y - \gamma _ { j } ^ { k } e _ { j } ) \geq f ( y )$ ，则令 $\scriptstyle y = y - \gamma _ { j } ^ { k } e _ { j }$ ，否则 $y { = } y$ 。

f）令 $p b e s t _ { k + 1 } = y$ ,若 $f ( p b e s t _ { k + 1 } ) < f ( p b e s t _ { k } )$ ，则对 $p b e s t _ { k + 1 }$ 沿着 $p ^ { k } = p b e s t _ { k + 1 } - p b e s t _ { k }$ 做模式移动，令 $y { = } p b e s t _ { k + 1 } + a p ^ { k }$ ， $\gamma ^ { k + 1 } = \gamma ^ { k }$ ，$k = k + 1$ ，转步骤e），否则转到步骤 $\mathbf { g }$ ）。

g）若 $\vert \gamma ^ { k } \vert < \varepsilon$ ，则停止迭代，输出结果；否则当$p b e s t _ { k + 1 } \neq p b e s t _ { k }$ 时，令 $\scriptstyle y = p b e s t _ { k }$ ， $k = k + 1$ ，转步骤e）；当$p b e s t _ { k + 1 } { = } p b e s t _ { k }$ 时，令 $\scriptstyle y = p b e s t _ { k }$ ， $\gamma ^ { k + 1 } = \lambda \gamma ^ { k }$ ， $k = k + 1$ ，转步骤e）；若达到最大迭代次数时 $\left| \gamma ^ { k } \right| > \varepsilon$ ，则转到步骤b）。

最终优化的结果输出 $( c , \gamma )$ 。

将结果带入SVM算法，通过练数据集得到训练模型，测试数据集作为分类模型的输入进行预测，判定跌倒和日常行为。

# 3.4算法流程 (图1)

![](images/300588c7b752cd1a0c9db05d9d27b503aed377f081d5128c4c1b6deddacbb8ca.jpg)  
图1跌倒检测流程  
Fig.1Flow chart of fall detection

# 4 实验结果及分析

# 4.1实验方案

本文实验数据由6人采集，其中男女各3人，将设备安置在腰上，共采集数据1000 组，其中跌倒 400 组（前向、后向跌倒，左侧和右侧跌倒各100组），正常活动采集600组（向前行走、向后行走、慢跑、蹲然后站起、弯腰、平躺各100组），采样频率为 $2 5 ~ \mathrm { H z }$ 。将300组跌倒样本和500组正常活动样本作为训练集，其余的用于SVM测试。以正常行走和向前跌倒为例，当发生跌倒时，加速度和姿态角会发生剧烈变化。为了消除噪声的影响，需进行均值滤波。经过滤波后发现，数据曲线消除不少毛刺，使图线显示平滑。

将滤波后的数据按照表的样式提取多维数据，按照SVD降维方法提取主成分进行降维，降维后的数据为后续算法提供支持。

为了验证PSO模式搜索算法的有效性和正确性，以SVM作为分类算法，以初始的PSO 算法和PSO 模式搜索算法的分类性能做比较。

方案如下：

方案1：特征集 $+ { \cal S } { \sf V } { \bf M }$ 算法。  
方案2：特征集 $\cdot +$ 初始PSO算法 $+ { \cal S } { \sf V } { \bf M }$ 。  
方案3：特征集 $+ \mathrm { P S O }$ 模式搜索算法 $+ S \mathbf { V } \mathbf { M }$ 。

# 4.2实验方案

本文选用准确率 Ac（accuracy）、特异度 Sp(specifity)以及敏感度Se(sensitivity)作为实验中算法好坏的评估标准。参数说明如表2所示。

$$
A c = { \frac { T P + T N } { T P + F N + T N + F P } }
$$

$$
S e = { \frac { T P } { T P + F N } }
$$

$$
S p = { \frac { T N } { T N + F P } }
$$

表2参数说明

Table 2Parameter specification   
表3三种方案对比   

<html><body><table><tr><td>参数</td><td>说明</td></tr><tr><td>Ac</td><td>accuracy样本中准确区分出的概率</td></tr><tr><td>Se</td><td>specifity 跌倒样本中被检测出的跌倒的概率</td></tr><tr><td>Sp</td><td>sensitivity非跌倒数据中识别出非跌倒的的概率</td></tr><tr><td>TP</td><td>true positive 跌倒样本中被检测出的跌倒样本数</td></tr><tr><td>FN</td><td>false negative 跌倒样本中被检测为非跌倒的样本数</td></tr><tr><td>TN</td><td>true negative 非跌倒数据中识别出非跌倒的样本数</td></tr><tr><td>FP</td><td>false positive非跌倒样本中检验出跌倒的样本数</td></tr></table></body></html>

Table 3Comparison of three schemes   

<html><body><table><tr><td>方案</td><td>组合</td><td>准确度</td><td>灵敏度</td><td>特异度</td><td>计算时间/s</td></tr><tr><td>1</td><td>特征集+SVM算法</td><td>0.80</td><td>0.73</td><td>0.81</td><td>213.27</td></tr><tr><td>2</td><td>特征集+初始 PSO 算 法+SVM算法</td><td>0.83</td><td>0.75</td><td>0.82</td><td>114.12</td></tr><tr><td>3</td><td>特征集+PSO 模式搜 索算法+SVM算法</td><td>0.89</td><td>0.80</td><td>0.87</td><td>92.32</td></tr></table></body></html>

根据式（12）～（14），可以得出实验数据，填入表3中。通过对比，方案1直接利用SVM算法，性能最低；方案2和3都加入了PSO 算法对SVM的参数进行了优化。方案2对比方案1的准确率提高0.07，提高率为 $4 \%$ ；方案3相比方案1，准确度提升0.09，提升率为 $1 1 \%$ ，相比方案2，准确度提升0.06，提升率为 $7 \%$ 。通过对比发现，灵敏度和特异度方面也有所提升。

从算法时间上分析，由于方案1的SVM参数需要使用网格法进行遍历寻找，所以消耗的时间最长；而方案2由于加入了PSO算法寻优，所以大大减少了SVM参数寻优的时间；而方案3在方案2的基础上，由于加入了模式搜索算法，使算法不会陷入局部最优解，所以在提升了准确率的同时，消耗的时间最少。

# 5 结束语

本文将PSO模式搜索算法引入跌倒检测分类问题。利用穿戴式设备采集数据，使用均值滤波进行去燥，然后依据SVD进行降维，将模式搜索引入PSO算法，对SVM的参数进行优化，利用SVM算法对跌倒和日常活动进行分类，经过实验，提高了跌倒检测的精度，并减少了算法的运行时间。

# 参考文献：

[1]Xu Tao,Zhou Yun,Zhu Jing.New advances and challenges of fall detection systems:a survey [J].Applied Sciences，2O18,8(3）， 418-429.   
[2]杨任兵，程文播，钱庆，等．红外图像中基于多特征提取的跌倒检测 算法研究[J]．红外技术，2017,39(12):1131-1138.(Yang Renbing, Chen Wenbo,Qian Qing,et al.Fall detection algorithm based on multi feature extraction in infrared image [J]. Infrared Technology,2017,39 (12):1131-1138.)   
[3]瞿畅，孙杰，王君泽，等．基于Kinect体感传感器的老年人跌倒自动 检测[J].传感技术学报,2016,29(3):378-383.(Qu Chang,Sun Jie, Wang Junze,et al.Automatic fall detection for the elderly using kinect sensor [J].Chinese Journal of Sensors and Actuators,2O16,29 (3): 378-383.)   
[4]Nadee C,Chamnongthai K.Octagonal formation of ultrasonic array sensorsfor fall detection [C]//Proc of Asia-Pacific Signal and InformationProcessingAssociationAnnualSummit and Conference .2016:1-4.   
[5]Nadee C,Chamnongthai K.Multi sensor system for automatic fall detection [C]l//Proc of Asia-Pacific Signal and Information Processing Association Annual Summit and Conference.2O15: 930-933.   
[6]Litvak D,Zigel Y,Gannot I. Fall detection of elderly through floor vibrations and sound [C]//Proc of the 3Oth Annual International Conference of the IEEE Engineering in Medicine and Biology Society. 2008: 4632-4635.   
[7]屠碧琪．基于多传感融合的老人跌倒检测算法研究[D].杭州：浙江 理工大学,2017.(Tu Biqi. Research on fall detection algorithm for the elderly based on muti-sensor fusion [D].Hangzhou: Zhejiang Sci-Tech University,2017.)   
[8]宋佳花．跌倒检测关键技术研究[D]．济南：山东大学,2017.(Song Jiahua. The research on the key technologies of fall detection [D]. Jinan:Shandong University,2017.）   
[9] 忽丽莎，王素贞，陈益强，等．基于可穿戴设备的跌倒检测算法综述 [J//OL].浙江大学学报：工学版,2018 (9):1-11.(Hu Lisha,Wang Suzhen，Chen Yiqiang，et al．Fall detection algorithms based on wearable device: a review [J//OL]. Journal of Zhejiang University : Engineering Science ,2018 (9):1-11.）   
[10]孙晓雯，孙子文，秦昉．基于阈值与 PSO-SVM的人体跌倒检测研究 [J]．计算机工程，2016,42(5):317-321.(Sun Xiaowen,Sun Ziwen, Qin Fang.Research on human fall detection based on threshold and PSO-SVM[J]. Computer Engineering,2016,42 (5): 317-321.)   
[11]裴利然，姜萍萍，颜国正．基于支持向量机的跌倒检测算法研究[J]. 光学精密工程,2017,25(1):182-187.(Pei Liran,Jiang Pingping,Yan Guozheng. Research on fall detection system based on support vector machine [J].Optics and Precision Engineering,2017,25(1): 182-187.)   
[12]麻文刚，王小鹏，吴作鹏．基于人体姿态的PSO-SVM特征向量跌倒 检测方法[J].传感技术学报，2017，30(10)：1504-1511.(Ma Wengang,Wang Xiaopeng,Wu Zuopeng. PSO-SVM feature vector fall detection algorithm based on human postures [J]. Chinese Journal of Sensors and Actuators,2017,30 (10):1504-1511.)   
[13]王荣，章韵，陈建新．基于三轴加速度传感器的人体跌倒检测系统 设计与实现[J].计算机应用，2012,32(5):1450-1452,1456.(Wang Rong,Zhang Yun, Chen Jianxin. Design and implementation of fall detection system using tri-axis accelerometer [J]. Journal of Computer Applications,2012,32(5): 1450-1452,1456. )   
[14]何坚，周明我，王晓懿．基于卡尔曼滤波与k-NN 算法的可穿戴跌倒 检测技术研究[J]．电子与信息学报，2017,39(11):2627-2634.(He Jian,Zhou Mingwo,Wang Xiaoyi.Wearable method for fall detection based on kalman filter and k-NN algorithm [J].Journal of Electronics & Information Technology,2017,39 (11): 2627-2634.)   
[15]李雷，张帆，施化吉，等．穿戴式跌倒检测中特征向量的提取和降维 研究[J/OL].计算机应用研究,2019(1):1-3.(Li Lei,Zhaang Fan, Shi HuaJi,et al. Research on feature vector extraction and dimension reduction of wearable fall detection,2019 (1):1-3.)   
[16]白勇，孙晓雯，秦昉，等．基于 SVD 特征降维和支持向量机的跌倒 检测算法[J].计算机应用与软件,2017,34(1):247-251.(Bai Yong, Sun Xiaowen,Qin Fang,et al. THE falling detection algorithm based on svd feature dimension reduction and SVM [J]. Computer Applications and Software,2017,34(1): 247-251.)   
[17]王喜宾，张小平，王翰虎．基于粒子群优化模式搜索的支持向量机 参数优化及应用[J].计算机应用，2011，31(12):3302-3304,3326. (Wang Xibin,Zhang Xiaoping,Wang Hanhu. Parameter optimization of support vector machine and application based on particle swarm optimization mode search [J]. Journal of Computer Applications,2011, 31 (12): 3302-3304,3326.)   
[18] Pannurat N,ThiemjarusS,Nantajeewarawat E.Automaticfall monitoring:a review [J].2014,14(7),12900-12936.