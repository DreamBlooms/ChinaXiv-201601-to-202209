# 基于CMAES-SVR的WLAN室内定位算法研究

饶华，王忠，李欣(四川大学 电气信息学院，成都 610065)

摘要：针对传统WLAN指纹定位算法中存在的定位精度低、稳定性差、实时性不高等问题，提出一种基于CMAES-SVR的WLAN室内定位算法。该算法首先对接入点（AP）的接收信号强度（RSS）进行统计分析，采用高斯滤波对信号进行预处理，然后利用K-means聚类算法将原始指纹数据库中的定位区域进行聚类分块；其次采用协方差矩阵自适应进化策略（CMAES）优化支持向量回归机（SVR）参数，从而建立CMAES-SVR室内定位学习模型，通过该模型分别构建各定位子区域中 RSS信号与物理位置非线性映射关系；最后判断测试点所属类簇，根据该类簇中训练好的CMAES-SVR模型进行回归预测。实验结果表明，与WKNN、传统 SVR以及PSO-SVR算法相比，该算法在定位精度、稳定性以及实时性方面均有所提高。

关键词：室内定位；位置指纹；聚类分析；协方差矩阵自适应进化策略；支持向量回归中图分类号：TP393 doi: 10.3969/j.issn.1001-3695.2018.07.0408

# Research on WLAN indoor positioning algorithm based on CMAES-SVR

Rao Hua, Wang Zhong, Li Xin (SchoolofElectrical&Information Engineering Sichuan University,Chengdu 6loo65,China)

Abstract:Aiming atthe problemsof low precision,poor stabilityand lowreal-time performance in traditional WLAN fingerprint positioning algorithm,this paper proposeda WLANindoorpositioning algorithmbasedon CMAES-SVR.Firstly, thealgorithmstatisticallyanalyzedthereceivedsignalstrength (RSS)ofacesspoint (AP)andusedthe Gausianfiltertopretreat the RSS signal. It adopted the $\mathbf { k }$ -means clustering algorithm to partition the location area of original fingerprint database; Secondly,thecovariance matrix adaptive evolutionary strategy(CMAES)optimized the support vector regression (SVR) parameters so as to establishthe CMAES-SVRindoorpositioning learning model.This modelconstructed thenonlinear mapping relationshipbetweenRSSsignalandphysicallocationineachsublocation.Finaly,thealgorithmdeterminedtheclusterofthe test points andcarredouteregressionpredictionaccordingtothetrained CMAES-SVRmodel.Theexperimentalresultsshow thatcompared with WKNN,traditionalSVRandPSO-SVRalgorithm,thealgorithmimproves locationaccuracy,stabilityand real-time performance.

Key Words:indoor position; location fingerprint; cluster analysis; CMAES; SVR

# 0 引言

移动智能终端的广泛应用和无线网络的迅速发展与普及，促进了基于位置服务应用需求的大幅增长，在定位导航、医疗救护、物流货运等生产生活领域均展示出了基于位置服务的巨大发展潜力和应用前景错误未找到引用源。。而如何确定用户的位置信息是基于位置服务的核心问题。由于室内环境复杂多变，全球定位系统（global positionsystem，GPS）不能满足人们对于室内定位精度的要求。目前室内定位技术依据不同的介质可分为基于特定设备的定位方法基于WLAN信号的定位方法，以及基于移动传感器的定位方法。而基于WLAN的室内定位方法以其低成本、易部署、高精度、高普适成为目前室内定位技术中的研究热点。

基于WLAN室内定位方法主要有基于测距的定位方法以及基于指纹的定位方法，其中位置指纹法具有算法灵活、定位精度高等特点。典型的WLAN指纹定位算法主要有最近邻法（nearest neighborhood，NN）错误!未找到引用源，、最大似然估计法错误!未找到引用源。、核函数法错误；未找到引用源。、人工神经网络法错误！未找到引用源，以及支持向量回归法（support vector regression，SVR）错误!未找到引用源。等。其中SVR综合考虑学习函数的VC维和训练误差，寻找实际风险最小化的学习函数，提高泛化能力，同时通过核函数映射，建立RSS信号与位置坐标之间的可靠非线性映射关系，定位精度得到极大提高。大量学者对此进行了深入研究，文献错误！未找到引用源。提出基于PCA-LSSVR定位算法，采取主成分分析法对信号进行数据降维和去相关处理，利用最小二乘支持向量回归机（LS-SVR）建立指纹特征数据与位置的非线性关系。文献错误！未找到引用源。提出卡尔曼滤波与SVR融合的定位算法，该算法通过利用前后位置之间的关系修正移动轨迹，改善定位结果。文献错误！未找到引用源。提出一种基于SVR的定位误差修正算法，该算法利用SVR建立RSS的定位结果与定位误差之间的非线性关系，并利用计算出的定位误差修正定位结果。文献错误！未找到引用源。提出一种基于改进支持向量回归算法，通过引入校正坐标来降低单独构建 $x$ 与 $y$ 坐标的误差，提高二维位置信息与RSS的关联性。这些算法在一定程度上能够减小定位误差，但均未考虑SVR超参数对其泛化性能的影响，因此在复杂室内定位环境中，影响定位精度。目前，粒子群、蚁群和遗传算法等在SVR参数优化上表现出了对目标函数类型不敏感以及其强大的随机寻优能力等优点，但是受种群大小的影响，存在时间复杂度较高、效率偏低、易早熟等问题错误!未找到引用源。\~错误!未找到引用源。

针对上述问题，本文提出了一种基于CMAES-SVR的室内定位算法。该算法在离线阶段，首先对接入点的接受信号强度进行统计分析，采用高斯滤波模型进行数据预处理从而增强数据的稳定性，利用 $\mathbf { k }$ -means聚类算法将原始指纹数据库中的定位区域划分为若干子区域，采用协方差矩阵自适应进化策略（covariance matrix adaptation evolution strategy,CMAES）优化SVR参数，从而建立CMAES-SVR室内定位学习模型。利用该模型对各子区域的参考点进行训练，建立RSS与物理位置非线性映射关系的离线指纹数据库；在线阶段，实时采集测试点RSS信号，经高斯滤波预处理后，判断其所属类簇，利用训练后的CMAES-SVR模型估测测试点的位置信息。通过实验仿真分析可知，CMAES在SVR参数寻优过程表现出全局性好且寻优效率高的优点，CMAES-SVR定位算法的具有较高的定位精度。

# 1 CMAES-SVR室内定位算法

# 1.1指纹数据库聚类分块

对于复杂多变的室内环境，基于指纹数据库的室内定位方法所需要的指纹数据库比较庞大，这就导致在实时定位算法运算量较大，易出现过学习。因而，本文提出对指纹数据库进行聚类从而减少在线定位解算时间。在对原始指纹数据库进行聚类之前，对单个参考点（reference point，RP）单个AP采集到的RSS信号进行统计分析，发现信号因环境因素波动很大，为了去除冗余数据，建立稳定可靠的定位模型，首先需对信号进行预处理。

在定位区域按照一定的间隔选取 $L$ 个RP, $R P _ { i }$ 的位置坐标为 $P _ { i } ( x _ { i } , y _ { i } )$ ，部署 $M$ 个可靠 AP。对某一参考点 $i$ 的第 $j$ 个AP进行 $\mathrm { ~  ~ N ~ }$ 次采样，得到RSS 信号 $r s s _ { i , j } = \left[ r s s _ { i , j , 1 } , r s s _ { i , j , 2 } , \cdots , r s s _ { i , j , N } \right]$ 服从高斯分布，即

$$
r s s _ { i , j } \sim N ( \mu , \sigma ^ { 2 } )
$$

$$
\mu = \frac { 1 } { N } \sum _ { k = 1 } ^ { N } r s s _ { i , j , k } \mathrm { ~ , ~ } \sigma = \sqrt { \frac { 1 } { N } \sum _ { k = 1 } ^ { N } \biggl ( r s s _ { i , j , k } - \frac { 1 } { N } \sum _ { k = 1 } ^ { N } r s s _ { i , j , k } \biggr ) ^ { 2 } }
$$

选取区间 $\left[ \mu - 1 . 6 5 \sigma , \mu + 1 . 6 5 \sigma \right]$ 作为高概率保留区域，滤除该区间以外的小概率冗余数据。再对该区域进行均值滤波，得到预处理后的 RSS 特征向量 $R _ { i } = [ r s s _ { i , 1 } , \cdots r s s _ { i , j } , \cdots r s s _ { i , M } ]$ ，与位置坐标组成指纹特征 $[ P _ { i } , R _ { i } ] , R _ { i } \in R ^ { N }$ 。然后采用 $\mathbf { k }$ -means聚类算法错误!未找到引用源·对具有指纹特征的原始指纹数据库进行划分，将相似度较高的RP归为一类。

K-mean聚类算法利用各数据到各中心点的距离大小进行聚类。随机选取 $R ^ { N }$ 中的 $k$ 个数据 $c _ { j } \in R , \left( j = 1 , 2 , \cdots , k \right)$ 作为需要的 $k$ 个聚类初始中心，计算各数据到 $k$ 个中心的距离，则聚类可表示为

$$
C _ { j } = \{ r s s _ { i } \mid j = \arg \operatorname* { m i n } \Big \| r s s _ { i } - c _ { j } \Big \| \}
$$

其中： $C _ { j }$ 表示第 $j$ 个聚类， $\left\| \boldsymbol { r } \boldsymbol { s } \boldsymbol { s } _ { i } - \boldsymbol { c } _ { j } \right\|$ 表示二者的欧氏距离。随后重新计算每个聚类的中心，即

$$
{ c _ { j } } ^ { n e w } = \frac { 1 } { N _ { c _ { j } } } \sum _ { i \in C _ { j } } r s s _ { i }
$$

其中： ${ c _ { j } } ^ { n e w }$ 为该聚类的新中心，重复计算直到聚类中心不再改变或者小于给定阈值。

通过聚类算法将原始指纹数据库分为 $k$ 个定位子区域，具体步骤如下：

a)初始化聚类中心。在指纹数据库中选取 $k$ 个指纹特征作为初始聚类中心（为了避免随机选择的初始聚类中心造成的聚类分散或集中的情况，在定位子区域均匀选取 $k$ 个初始聚类中心，保持与物理空间的一致性）。

b)计算各指纹特征对应的RSS值与 $k$ 个聚类中心的欧式距离，按照距离最近进行分配。

c)执行完所有指纹后，获得新的聚类，并更新聚类中心。

d)重复步骤b)c)，直到 $k$ 个聚类中心不再变化或小于给定阈值，终止迭代，输出 $k$ 个聚类中心和对应指纹特征集合。

通过K-means聚类算法对指纹特征进行聚类，形成 $k$ 个定位子区域，分别对 $k$ 个定位子区域进行模型训练，得到RSS信号与物理位置之间的映射关系，形成新的指纹数据库。在线阶段，对实时采集到的RSS信号，经过预处理后，比较其与各个子定位区域聚类中心的欧式距离，找到最近的聚类中心，并将其定位至该聚类中心所在的定位子区域，即

$$
i ^ { * } = \arg \operatorname* { m i n } \left\| r s s - w _ { i } ^ { c e n t e r } \right\|
$$

室内定位系统的指纹数据库学习算法在第 $i ^ { * }$ 个聚类里完成。

# 1.2 SVR定位模型

将原始指纹数据库划分为 $k$ 个定位子区域后，利用SVR 算法构建出对应于接收信号强度和位置坐标之间的非线性关系。通常SVR为单输出，而参考点位置坐标为二维 $P ( x , y )$ ，所以采用以多输出代替单输出的方式，来实现多输出 SVR回归错误!未

找到引用源。

首先，通过非线性映射函数 $\Phi : R ^ { N } \to F$ ，将 $R ^ { N }$ 映射到高维核特征空间 $F$ 中，然后，在高维空间分别构造 $x$ 坐标和 $y$ 坐标的线性回归函数。以构造 $x$ 坐标回归函数为例。在 $F$ 空间中构建位置坐标和接收信号强度的最优线性回归估计函数为

$$
x = w ^ { T } \cdot \Phi ( R ) + b
$$

其中： $w$ 为权重系数， $b$ 为偏置常量， $\Phi ( R )$ 为将输入的指纹数据RSS信号映射至高维空间中的非线性映射函数。

SVR算法根据结构风险最小化原则，求解凸二次优化问题，即

$$
\operatorname* { m i n } J ( w ) = \frac { 1 } { 2 } \big \| w \big \| ^ { 2 } + c \sum _ { i = 1 } ^ { N } ( \xi _ { i } + \xi _ { i } ^ { * } )
$$

$$
\left\{ \begin{array} { l l } { x - w ^ { T } - b \leq \varepsilon + \xi _ { i } } \\ { w ^ { T } - b - x \leq \varepsilon + \xi _ { i } ^ { * } , i = 1 , 2 , . . . , n } \\ { \xi _ { i } \geq 0 , \xi _ { i } ^ { * } \geq 0 } \end{array} \right.
$$

其中： $\xi _ { i }$ 和 $\boldsymbol { \xi } _ { i } ^ { * }$ 为松弛因子，满足条件 $\xi _ { i } \ge 0 , \xi _ { i } ^ { * } \ge 0$ ， $\varepsilon$ 为不敏感损失函数，用来控制回归误差， $\boldsymbol { \mathbf { \mathit { c } } }$ 为惩罚因子，满足条件 $c > 0$ 。经验风险大小由 $\textstyle \sum _ { i = 1 } ^ { N } ( \xi _ { i } + \xi _ { i } ^ { * } )$ 来决定， $\left\| \boldsymbol { w } \right\| ^ { 2 }$ 决定 VC 维进而影响置信范围大小。

在凸二次优化问题中引入拉格朗日多项式，有

$$
\begin{array} { l } { { \displaystyle { \cal L } = \displaystyle \frac { 1 } { 2 } \big \| w \big \| ^ { 2 } + c \sum _ { i = 1 } ^ { N } ( \xi _ { i } + \xi _ { i } ^ { * } ) - \sum _ { i = 1 } ^ { N } ( \eta _ { i } \xi _ { i } + \eta _ { i } ^ { * } \xi _ { i } ^ { * } } } \\ { ~ } \\ { { \displaystyle ~ - \sum _ { i = 1 } ^ { N } \alpha _ { i } ( \varepsilon + \xi _ { i } - x + w ^ { T } \cdot \Phi ( R ) + b ) } } \\ { { \displaystyle ~ - \sum _ { i = 1 } ^ { N } \alpha _ { i } ^ { \prime } ( \varepsilon + \xi _ { i } - x + w ^ { T } \cdot \Phi ( R ) - b ) } } \end{array}
$$

其中： $\alpha _ { i } \setminus \alpha _ { i } ^ { * }$ 是拉格朗日乘数，满足条件： $\alpha _ { i } , \alpha _ { i } ^ { * } \geq 0$ ， $\xi _ { i } , \xi _ { i } ^ { * } \ge 0$ ，i=1,2.,.,n。

SVR模型中通过核函数来避免维数灾难，本文选择高斯核函数作为SVR模型的核函数，即

$$
k ( R _ { i } , R ) = \exp ( - \frac 1 { 2 \delta ^ { 2 } } \big \| R _ { i } - R \big \| ^ { 2 } )
$$

最终可以得到对应SVR定位函数为

$$
w = \sum _ { i = 1 } ^ { N } ( \alpha _ { i } - \alpha _ { i } ^ { * } ) \Phi ( R _ { i } )
$$

$$
x = \sum _ { i = 1 } ^ { N } ( \alpha _ { i } - \alpha _ { i } ^ { * } ) k ( R _ { i } , R _ { j } ) + b
$$

离线阶段分别通过相应的样本训练和参数搜索，得到两个独立、分别输出 $x$ 坐标和 $y$ 坐标的SVR定位函数。

# 1.3协方差矩阵自适应进化策略(CMAES)

CMAES算法是一种用于解决复杂的非线性、非连续的凸优化问题的进化策略类算法，在求解全局优化问题中表现出良好的寻优性能，具有收敛速度快、鲁棒性强、旋转不变优点误！未找到引用源·。CMAES 算法的基本步骤如下：

a)参数设置及初始化。种群中父代个体数 $\mu$ 以及子代个体数 $\lambda$ ，且 $\mu < \lambda$ ，重组权值为 $\omega _ { i = 1 , 2 , \cdots , \mu }$ ，自适应调整时所需要的常量 $c _ { \sigma }$ ， $d _ { \sigma }$ ， $c _ { c }$ ， $c _ { 1 }$ 以及 $c _ { \mu }$ （见参考文献错误!未找到引用源。），初始值 ${ m ^ { ( 0 ) } \in \boldsymbol { R } ^ { N } }$ ， $N$ 为求解问题的维度， $\boldsymbol { \sigma } ^ { ( 0 ) } \in \boldsymbol { R } ^ { + }$ ， $P _ { \sigma } ^ { ( 0 ) } = 0$ ，

$P _ { c } ^ { ( 0 ) } = 0$ ， $C ^ { ( 0 ) } = { \cal I } \in { \cal R } ^ { N \times N }$ ， $g ^ { ( 0 ) } = 0$ ，最大迭代次数 $G$ 。

b)采样操作。通过高斯分布 $N ( m , \sigma ^ { 2 } C )$ 在优化问题解空间进行样本采集，生成由 $\lambda$ 个个体 $x$ 组成的种群分布，这些样本即对应优化算法中的种群。

$$
\begin{array} { c } { { { x _ { j } } ^ { \scriptscriptstyle ( g + 1 ) } = m ^ { ( g ) } + \sigma ^ { ( g ) } N _ { j } ( 0 , C ^ { ( g ) } ) \ ( j = 1 , 2 , \cdots , \lambda ) } } \end{array}
$$

其中： ${ x _ { j } } ^ { ( g + 1 ) }$ 为第 $g + 1$ 代种群中的第 $j$ 个个体； $m ^ { ( g ) }$ 为第 $g$ 带种群的分布均值； $\boldsymbol { \sigma } ^ { ( g ) }$ 为第 $g$ 带种群全局步长； $C ^ { ( g ) }$ 为第 $g$ 代种群分布的协方差矩阵，各参数关系为

$$
C ^ { ( g ) } = B ^ { ( g ) } ( D ^ { ( g ) } ) ^ { 2 } ( B ^ { ( g ) } ) ^ { T }
$$

其中： $B ^ { ( g ) }$ 为正交矩阵，其列向量是 $C ^ { ( g ) }$ 的特征向量正交基，用于种群分布超椭球面的旋转； $D ^ { ( g ) }$ 为对角矩阵，对角线元素为 $C ^ { ( g ) }$ 特征向量的平方根，与 $B ^ { ( g ) }$ 的各个列向量对应，用于种群分布超椭球面的尺度缩放。

c）评价与选择。对子代个体逐个进行适应度评价并排序，进行 $( \mu , \lambda )$ 阶段选择组成当前最优子代种群。对新产生的解计算对应的适应度函数值 $f ( x _ { i } )$ ，并对这些目标函数值排序，即

$$
f ( x _ { 1 : \lambda } { } ^ { ( g + 1 ) } ) \leq f ( x _ { 2 : \lambda } { } ^ { ( g + 1 ) } ) \leq \cdots \leq f ( x _ { \lambda : \lambda } { } ^ { ( g + 1 ) } )
$$

d)参数更新

(a)均值更新。

$$
{ m ^ { ( g + 1 ) } = \sum _ { i = 1 } ^ { \mu } \omega _ { i } x _ { \mathrm { l } : \lambda } { ( g + 1 ) } }
$$

$$
\sum _ { i = 1 } ^ { \mu } \omega _ { i } = 1 \quad ( \omega _ { 1 } \ge \omega _ { 2 } \ge \cdots \ge \omega _ { \mu } \ge 0 )
$$

式中： $\omega _ { i }$ 为设定的权重； ${ x _ { 1 : \lambda } } ^ { ( g + 1 ) }$ 为第 $( g + 1 )$ 代的 $\lambda$ 个个体中第$i$ 个最优个体。

(b)协方差矩阵自适应。先对协方差矩阵进行路径 $p _ { c }$ 更新，然后自适应调整协方差矩阵 $C$ 。

$$
p _ { c } ^ { { \tiny { ( g + 1 ) } } } = ( 1 - c _ { c } ) p _ { c } ^ { { \tiny { ( g ) } } } + h _ { \sigma } ^ { { \tiny { ( g + 1 ) } } } \cdot \sqrt { c _ { c } ( 2 - c _ { c } ) } \sqrt { \mu _ { e f f } } \cdot \frac { m ^ { ( g + 1 ) } - m ^ { ( g ) } } { \sigma ^ { ( g ) } }
$$

$$
\begin{array} { l } { { \displaystyle { \cal C } ^ { ( g + 1 ) } = ( 1 - c _ { 1 } - c _ { \mu } ) C ^ { ( g ) } + c _ { 1 } [ p _ { c } ^ { ( g + 1 ) } ( p _ { c } ^ { ( g + 1 ) } ) ^ { T } + \delta ( h _ { \delta } ^ { ( g + 1 ) } ) C ^ { ( g ) } ] } } \\ { { \displaystyle ~ + c _ { \mu } \sum _ { i = 1 } ^ { \mu } \omega _ { i } y _ { i ; \lambda } ^ { ~ ( g + 1 ) } ( y _ { i ; \lambda } ^ { ~ ( g + 1 ) } ) T } } \end{array}
$$

其中：y(8+1) = $y _ { i ; \lambda } { } ^ { ( g + 1 ) } = { \frac { ( x _ { i ; \lambda } { } ^ { ( g + 1 ) } - m ^ { ( g ) } ) } { \sigma ^ { ( g ) } } }$ $\sqrt { \mu _ { e f f } } = \frac { 1 } { \displaystyle \sum _ { i = 1 } ^ { \mu } \omega _ { i } ^ { 2 } }$ ， $c _ { c }$ 为 $p _ { c }$ 的更新学习速率； $c _ { 1 }$ 和 $c _ { \mu }$ 分别为 $C$ 的“秩 $1 ^ { \prime \prime }$ 和“秩 $\mu$ ”的更新学习速率。

(c)步长更新。先更新步长进化路径 $p _ { \sigma }$ ，再对累计步长自适应调整。

$$
p _ { \sigma } ^ { \mathrm { \tiny ~ ( g + 1 ) } } = ( 1 - c _ { \sigma } ) p _ { \sigma } ^ { \mathrm { \tiny ~ ( g ) } } + \sqrt { c _ { \sigma } ( 2 - c _ { \sigma } ) } \cdot \sqrt { \mu _ { e f f } } C ^ { \frac { 1 } { 2 } } \frac { m ^ { ( g + 1 ) } - m ^ { ( g ) } } { \sigma ^ { ( g ) } }
$$

$$
\sigma ^ { ( g + 1 ) } = \sigma ^ { ( g ) } \exp \left( \frac { c _ { \sigma } } { d _ { \sigma } } \left( \frac { \left\| p _ { \sigma } ^ { ~ ( g + 1 ) } \right\| } { E \left( \left\| N ( 0 , I ) \right\| \right) } - 1 \right) \right)
$$

其中： $c _ { \sigma }$ 为 $p _ { \sigma }$ 的更新学习率。

e)是否达终止条件？若是，停止并输出最优解以及最优值，否则返回b)。

由于CMAES在求解全局优化问题中表现出良好的寻优性

能，本文采用CMAES对室内定位中指纹信息与位置坐标的SVR学习算法参数进行寻优，具体步骤如下：

a)参数设置及初始化。CMAES参数设置，最大迭代次数$G$ ，SVR主要设置惩罚参数 $\scriptstyle { \begin{array} { l } { c } \end{array} }$ 、核函数参数 $\delta$ 以及敏感因子 $\varepsilon$ 的上下界范围。

b)取第 $i ( i = 1 , 2 , \cdots , k )$ 个定位子区域的数据作为训练集。

c)种群采样。采样多维正态分布产生由 $\lambda$ 个个体 $( c , \delta , \varepsilon )$ 组成的种群分布，以及个体取值范围。

d)分别计算种群个体的适应度。将 $( c , \delta , \varepsilon )$ 作为训练参数，利用训练集训练SVR模型，将平均定位误差作为个体的适应度值，即

$$
A \nu g E r r = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \sqrt { \left( x _ { i } - x _ { i } ^ { \ast } \right) ^ { 2 } + \left( y _ { i } - y _ { i } ^ { \ast } \right) ^ { 2 } }
$$

比较个体的适应度值大小，选择适应度值最小的 $\mu$ 个个体组成当前最优子群。

e)参数更新。更新均值 $m$ ，协方差矩阵 $C$ 和步长 $\sigma$ 。

f)判断是否达到最大迭代次数 $G$ ，若是，则停止，输出最优个体 $( c ^ { * } , \delta ^ { * } , \varepsilon ^ { * } )$ 以及最优适应度值AvgErr，否则，返回c)。

g)分别对 $k$ 个定位子区域进行CMAES-SVR模型训练。

![](images/b6b4c955166622c02af9f7f6150f1020b409a71f101feb9281ac2ee4037ff75f.jpg)  
基于CMAES-SVR室内定位模型如图1所示。

# 2 实验结果及分析

# 2.1实验场景

本文实验场景为四川大学基础教学楼B座二楼。实验局部平面图如图2所示。在区域A和区域B均匀部署30个参考点，每个参考点的距离为3米，随机选取20个测试点。整个实验场景选取10个较为稳定的AP点。使用华为Nova移动终端进行RSS数据采集，在3天不同时段分别进行RSS信号采集，采样间隔1s，每个参考点及测试点连续采集40次为一组数据，共采集5组数据，由此，每个AP点共采集RSS信号200次。初始种群均值为 $m ^ { ( 0 ) } = \left( c , \delta , \varepsilon \right) ^ { ( 0 ) }$ ， $\mathrm { ~  ~ c ~ }$ 与 $\delta$ 均设置为[0.01,100]， $\varepsilon$ （20设为 $1 \times 1 0 ^ { - 5 }$ ，为了使适应度函数AvgErr能以较快速度达到收敛且具有更好的收敛性能。最大迭代次数设置为100。

![](images/a67adc05147f18ef03432f8078d1ac5d205916ff47fd91790eb56f95ca805fc4.jpg)  
图2实验场景平面图

# 2.2 实验结果分析

本文对参考点以及测试点大量实测数据进行统计分析，单个RP同一AP采集的RSS信号呈现出近似高斯统计特性。图3给出了某个RP同一AP的RSS信息200 次采样的概率分布直方图。

![](images/c22416c624f474d4b2d570ac312e2d3a7d92a14ca98b4ebdb4c137fda27a03ed.jpg)  
图3采样200次时的接收信号强度概率分布直方图

因此，先采取高斯滤波滤除小概率与大干扰的数据，减小RSS 信号的方差，增强指纹数据的稳定性以及可靠性，然后对信号进行均值滤波。如图4所示，通过高斯滤波后，偏差较大的小概率数据被滤除，曲线波动变小。

![](images/eaa4133f1f16532501344da954946b20d294f66e67e6372afacf24f04083f505.jpg)  
图1CMAES-SVR室内定位模型图  
图4高斯滤波后RSS信号曲线

RSS信号经预处理后，与物理位置构成原始指纹数据库，对于指纹数据库的聚类分块， $k$ 值的选取对定位精度影响较大，$k$ 值较小容易出现每个聚类中的信息相似度不高， $k$ 值过大，定位子区域增加，每个子区域对应的范围减小，导致类之间的相似度增加，降低定位精度。为了能够有效分割指纹数据库定位子区域，本文比较 $k$ 取区间[1,10]时，系统的平均定位误差。采用传统SVR定位算法对位置信息进行学习预测。如图5是平均定位误差随 $k$ 值变化曲线图。

![](images/c1b54fbbccb61b4b5f42af54b689599fb801aad1996534daf1d617bf6c363ea0.jpg)  
图5平均定位误差随k值变化

通过分析，当 $k$ 值取5时，系统的平均定位误差达到最小，$k$ 值大于5后，平均定位误差逐渐增大。所以，离线阶段对原始指纹数据库进行分区时， $k$ 取值为5，再分别对每个定位子区域进行CMAES-SVR模型训练。为了验证CMAES-SVR算法的有效性，采用WKNN( $K = 6$ )、传统 SVR 算法与PSO-SVR 算法进行对比分析。PSO-SVR初始惯性权重设为0.8，终止惯性权重设为0.3，学习因子c1、c2分别设为1.7和1.5，最大迭代次数均设为100，三种算法采用相同定位子区域的指纹数据，几种算法定位效果如图6所示。

![](images/e464bc7147cdeb385b3c13cef681249393f44f37af09649754143f808eaa3ee6.jpg)  
图6几种定位算法平均定位误差对比

从图4可以看出，在采样次数为80时，CMAES-SVR的平均定位误差为 $1 . 6 8 \mathrm { m }$ ，而WKNN、传统 SVR、PSO-SVR定位误差分别为 $2 . 5 3 \mathrm { m }$ 、 $2 . 3 8 \mathrm { m }$ 、 $2 . 2 1 \mathrm { m }$ ，当采样次数大于90时，CMAES-SVR的平均定位误差以及小于其他几种算法采样次数为150时的平均定位误差。

图7为RSS信号采样次数为100时，几种定位算大的平均定位误差累计概率分布曲线图。当平均定位误差小于等于 $2 \mathrm { m }$ 时，CMAES-SVR、PSO-SVR、传统 SVR以及WKNN 算法的定位误差累计概率分别为 $7 6 . 8 \%$ 、 $71 . 2 5 \%$ 、 $6 4 . 8 \%$ 、 $6 2 . 1 6 \%$ 。平均定位误差小于等于 $3 \mathrm { m }$ 时，各算法的累计概率分别为 $91 . 2 \%$ ，$8 7 . 3 6 \%$ 、 $8 3 . 1 \%$ 、 $7 7 . 6 \%$ 。此外，通过比较几种算法的定位误差标准方差，本文提出的CMAES-SVR算法方差为1.16，小于其它几种算法，由此可得，在相同实验环境下，CMAES-SVR 算

法具备较高的定位准确率。

![](images/2dd807214f75a4957c468939e0a57aa1c1e6e6771534e448ecdd40cf878d5363.jpg)  
图7几种室内定位算法平均定位误差累计概率分布

为了分析聚类分块对算法计算复杂度的影响，比较几种定位算法的在线计算复杂度。对于WKNN匹配型算法，其计算复杂度与指纹数据库大小成正比，聚类分块将在线阶段需匹配的位置指纹由整个指纹数据库中30个参考点变为平均6个参考点的，有效的减小算法的搜索匹配空间，使得匹配计算量降低了约 $78 . 6 \%$ 。对于CMAES-SVR以及PSO-SVR学习型算法，在线定位计算量由SVR算法决定，而聚类分块算法使RSS信号模式更加集中，简化了SVR学习函数的映射关系，从而大大减少了支持向量个数，SVR定位函数的在线计算复杂度降低约为 $6 5 . 6 \%$ 。此时，WKNN算法的计算复杂度最低，但是其定位精度较差，而本文提出的CMAES-SVR定位算法在提高定位精度的基础上能够降低在线计算复杂度。

表1不同算法的定位误差  

<html><body><table><tr><td rowspan="2">算法</td><td colspan="3">平均定位<3m的定位70%定位</td><td rowspan="2">90%定位 误差/m</td><td rowspan="2">定位误差 标准方差</td></tr><tr><td>误差/m</td><td>误差/%</td><td>误差/m</td></tr><tr><td>WKNN</td><td>2.35</td><td>77.6</td><td>2.61</td><td>4.56</td><td>1.29</td></tr><tr><td>传统 SVR</td><td>2.11</td><td>83.1</td><td>2.65</td><td>4.33</td><td>1.31</td></tr><tr><td>PSO-SVR</td><td>2.16</td><td>87.36</td><td>2.31</td><td>3.55</td><td>1.25</td></tr><tr><td>CMAES-SVR</td><td>1.74</td><td>91.2</td><td>2.18</td><td>3.31</td><td>1.16</td></tr></table></body></html>

# 3 结束语

本文针对复杂室内环境中 RSS信号存在冗余以及噪声问题，指纹数据库数据量庞大带来的学习效率低、计算复杂度高的问题，以及SVR超参数对定位精度影响较大的问题，提出了基于CMAES-SVR的WLAN室内定位算法。该算法首先对RSS信号概率分布进行分析，采用高斯滤波对信号进行预处理，去除小概率大干扰数据，从而减小信号方差。采用K-means算法将指纹数据库分块，从而减小搜索空间，有效避免了SVR学习算法过度学习问题，降低了算法计算复杂度。采用CMAES对SVR参数进行寻优，分别对各个定位子区域进行模型训练，从而构建出更优的具有RSS信号与物理位置信息的非线性映射关系的SVR模型。通过实验结果对比分析，CMAES-SVR算法相较于WKNN 算法、传统SVR 算法以及PSO-SVR 算法，具有更高的定位精度以及稳定性。

# 参考文献：

[1]席瑞，李玉军，侯孟书．室内定位方法综述[J].计算机科学,2016,43 (4):1-6,32.(Xi Rui,Li Yujun,Hou Mengshu. Survey on indoor localization [J].Computer Sicence,2016,43 (4): 1-6,32.)   
[2]Belay AA,Yayeh Y,Berie G,et al. Indoor localization using K-nearest neighbor and artificial neural network back propagation algorithms [C]// Proc of the 27th Wireless and Optical Communication Conference. [S. I. ] : IEEE Press,2018: 1-2.   
[3]Ilyas M,Bayat O,Ileri O.Indoor location estimation by using MLE based algorithm on smallell networks [C]// Proc of the 23nd Signal Processing and Communications Applications Conference.[S.I.] : IEEE Press, 2015: 690-693.   
[4]Kong Yongping, Zhong Zhiming, Yang Guanglong,et al. A non-parametric kernel method for CDMA20o0 network indoor localization using multiple observations [C]//Proc of International Conference on Information Network. Piscataway,[S.I.] : IEEE Press,2012: 97-101.   
[5]Gharghan S.K,Nordin R,Ismail M,et al.Accurate wireless sensor localization technique based on hybrid PSO-ANN algorithm for indoor and outdoor track cycling [J].IEEE Sensors Journal,2016,16 (2): 529-541.   
[6]Mao Rui, Xiang Peng, Zhang Dian. Precise transceiver-free localization in complex indoor environment [J].China Communications,2016,13 (5): 28- 37.   
[7] 张勇，黄杰，徐科宇．基于PCA-LSSVR 算法的WLAN 室内定位方法 [J].仪器仪表学报,2015,36(2):408-414.(Zhang Yong,Huang Jie,Xu Keyu.Indoor positioning algorithm for WLAN based on principal component analysis and least square support vector regression [J]. Chinese Journal of Scientific Instrument, 2015,36 (2): 408-414.)   
[8]Zhang Yu,Dong Lian,LaiLei,et al. Study of indoor positioning method based on combination of support vector regression and kalman filtering [J]. International Journal of Future Generation Communication and Networking, 2016,9 (3): 201-214.   
[9] 郭建，刘全景，赵志凯．一种基于 SVR 的定位误差修正算法[J].计算 机应用研究,2017,33(8):1-4.(Guo Jian,Liu Quanjing,Zhao Zhikai. Positioning error correction algorithm based on SVR [J].Application Research of Computers,2017,33 (8): 1-4.)   
[10]姚英彪，毛伟勇，姚瑞丽，等．基于改进支持向量回归的室内定位算法 [J].仪器仪表学报,2017,38(9):2112-2119.(Yao Yingbiao,Mao Weiyong, Yao Ruili,et al. Indoor positioning algorithm based on improved support vector regression [J].Chinese Journal of Scientific Instrument,2017,38 (9): 2112-2119. )   
[11] Munlin M,Anantathanavit M.New social-based radius particle swarm optimization [C]// Proc of the 12th IEEE Conference on Industrial Electronics and Applications.[S.I.] : IEEE Press,2017: 838-843.   
[12] Dai Chunni. SVM visual classification based on weighted feature of genetic algorithm $[ \mathrm { C } ] / \AA$ Proc of the 6th International Conference on Intelligent Systems Design and Engineering Applications.[S.I.]: IEEE Press, 2015: 786-789.   
[13] Hansen N,Ros R,Mauny N, et al. Impacts of invariance in search: when CMA-ES and PSO face il-conditioned and non-separable problems [J]. Applied Soft Computing,2011,11(5): 1667-1679.   
[14] Chen Yingying, Yang Jie,Trappe W,et al. Detecting and localizing identitybased attacks in wireless and sensor networks [J]. IEEE Trans on Vehicular Technology,2010,59 (5): 2418-2434.   
[15] Fang S H,Lin T N.A dynamic system approach for radio location fingerprinting in wireless local area networks [J].IEEE Trans on Communications,2010,58 (4): 1020-1025.   
[16]黄亚飞，梁昔明，陈义雄．基于适应性均衡模型的CMAES 约束优化算 法[J].中南大学学报：自然科学版,2012,43(09):3478-3484.(Huang Yafei,Liang Ximing, Chen Yixiong. Constrained evolutionary optimization of CMAES based on adaptive tradeoff model[J]. Journal of Central South University: Science and Technology,2012,43 (09): 3478-3484.)   
[17] Kovitz J.M, Yahya.R S.A comparative study between CMA evolution strategies and Particle Swarm Optimization for antenna applications [C]// Proc of US National Commite of URSI National Radio Science Meeting, [S.I.] : IEEE Press,2013.