# 基于自适应渐消无迹粒子滤波的UnscentedFastSLAM算法

王倩la，曾庆军la，张家敏la，姚金艺la，周启润』b，戴晓强la,2(1.江苏科技大学a.电子信息学院;b.计算机科学与工程学院，江苏 镇江 212003;2.江苏陋普泰克自动化科技有限公司，江苏 镇江 212003)

摘要：针对机器人导航无迹快速同步定位与地图构建（Unscented FastSLAM）算法由于重采样造成样本粒子退化，进而导致估计精度下降的问题，提出一种基于自适应渐消无迹粒子滤波的UnscentedFastSLAM算法。该算法将无迹粒子滤波与渐消滤波相融合产生自适应建议分布函数，同时将粒子根据权值进行优化组合，仅对组合后的部分不稳定的粒子进行系统重采样。通过这两方面使系统具有高度自适应性的同时保证粒子的多样性，缓解粒子的退化现象。仿真实验表明，提出算法与Unscented FastSLAM算法相比，可以用较少的粒子实现更高的 SLAM的估计精度，很大程度上降低了SLAM算法的复杂度。

关键词：同步定位与地图构建；粒子退化；自适应渐消无迹粒子滤波；自适应部分系统重采样中图分类号：TP242.6 doi:10.3969/j.issn.1001-3695.2017.11.0742

# Unscented fastSLAM algorithm based on adaptive fading unscented particle filter

Wang Qianla, Zeng Qingjunla, Zhang Jiaminla, Yao Jinyila, Zhou Qirunlb, Dai Xiaoqiangla, 2 (1.a.Schoolof Electronic&Information,b.SchoolofComputer Science&Engineering Jiangsu UniversityofScience& Technology,ZhenjiangJiangsu20,China;2.JiangsuhitekAutomationTchnologyCoLtd,ZhenjiangJangsu00, China)

Abstract:Fortheunscentedfastsimultaneous localizationand mapping(UnscentedFastSLAM)algorithm in robotnavigation, thesample particleisdegradeddue toresampling,whichleads to theproblemofreducedacuracy.Inordertosolve theproblem, this paper developed an improved UnscentedFastSLAMalgorithm based on adaptive fading unscented particle filter.The algorithm merged theunscentedparticlefilter with thefading filtertoformadaptive proposeddistributionfunction.Atthesame time,the particles wereoptimallycombinedaccording totheirweight,andonlyunstable particlesareresampled.Throughthese two aspectscould make thesystem highlyadaptive,whileensuring the diversityofparticles and mitigating thedegradationof particles.Simulationexperimentsshowthatcompared with UnscentedFastSLAMalgorithm,the proposed algorithmcanachieve higher SLAM estimation accuracy with fewer particles, which greatly reduces the complexity of SLAM algorithm.

Key words: simultaneous localizationand mapping(SLAM);particle degradation;adaptivefading unscented particle filter; adaptive partial systematic resampling

# 0 引言

同步定位与地图构建（simultaneous localization and mapping,SLAM)是实现机器人完全自主导航的关键问题。具体描述为：机器人在部分或完全未知的环境中，仅利用自身携带的传感器感知环境信息，构建环境地图的同时确定自身的位置[,2]。

解决SLAM问题的方法有很多，其中，Montemerlo等人提出的基于粒子滤波器（particle filtering，PF）的FastSLAM方法在处理非线性、非高斯系统上具有很大优势[3]。在标准FastSLAM中，粒子滤波器用于机器人位置估计，扩展卡尔曼滤波器（extended Kalman filtering，EKF）用于特征位置估计[4]。因此，FastSLAM存在由雅可比矩阵的推导和非线性函数的线性近似引起的估计不准确的问题。为了解决这些问题，文献[5]提出了UnscentedFastSLAM（UFastSLAM）方法。其中，无迹粒子滤波（unscented particle filtering，UPF）用于机器人路径估计，无迹卡尔曼滤波（unscentedKalman filtering，UKF）用于特征位置估计。通过应用无迹变换来消除雅可比计算的线性化过程，因此状态估计的准确性有显著改善[6]。

但是UFastSLAM在重采样时只复制大权值粒子，抛弃小权值粒子，导致粒子集出现贫化现象，使得被抛弃粒子中所携带的机器人位置及地图特征历史信息同时丢失[7]。针对这一过程导致估计精度下降的问题，文献[8]提出基于平方根无迹卡尔曼滤波（square root unscented Kalman filtering，SR-UKF）的FastSLAM 算法，使用SR-UKF 估计每个粒子的后验位姿建议分布，提高粒子采样精度。文献[9]提出基于迭代EKF建议分布和线性优化重采样的FastSLAM算法，使粒子分布在高观测似然区域，同时缓解粒子退化现象。

因此，本文将从建议分布和重采样两方面对UFastSLAM进行改进：一方面，引入文献 $1 0 { \sim } 1 2 ]$ 中的渐消滤波与无迹粒子滤波相结合产生参数自适应调节的建议分布函数，从而使得粒子的分布更加符合系统的后验概率分布，降低粒子的退化程度；另一方面，在重采样过程中将粒子权值按大小进行分类并优化组合，仅对部分粒子进行系统重采样，从而自适应调整重采样粒子数，增加粒子的多样性。通过以上方法提高系统的自适应性，使机器人位置和特征位置估计更加精确。

# 1 机器人UFastSLAM算法

UFastSLAM算法的基本思想是以基本的FastSLAM算法为框架，将系统的状态估计分解为对机器人运动路径的估计和对环境特征位置的估计两个部分[13]，同时使用UKF取代一阶线性化和EKF的过程，表示为

$$
p \left( s ^ { t } , \Theta \left| z ^ { t } , u ^ { t } , n ^ { t } \right. \right) = \underbrace { p \left( s ^ { t } \left| z ^ { t } , u ^ { t } , n ^ { t } \right. \right) } _ { \xrightarrow { \mathrm { w } _ { \mathrm { H G E } } \mathord { \left| z ^ { t } \right| } \mathrm { w } _ { \mathrm { m } } ^ { \mathrm { u k } } \mathrm { f i c i j i f } \left( \mathrm { U P F } \right) } } \underbrace { \prod _ { n = 1 } ^ { N } p \left( \theta _ { n } \left| s ^ { t } , z ^ { t } , u ^ { t } , n ^ { t } \right. \right) } _ { \xrightarrow { \mathrm { p } _ { \mathrm { H G P } } \mathrm { s u p s i t i c } } \mathrm { f i c i j i f } \mathrm { ( U K F ) } }
$$

其中： ${ \boldsymbol { s } } ^ { t } = \left\{ { { s } _ { 1 } } , . . . , { { s } _ { t } } \right\}$ 为机器人的路径估计， $s _ { t }$ 为 $t$ 时刻的机器人位姿； $\Theta = \{ \theta _ { 1 } , . . . , \theta _ { n } \}$ 为路标位置的合集； $\boldsymbol { z } ^ { t } = \left\{ { z } _ { 1 } , . . . , { z } _ { t } \right\}$ 和$\boldsymbol { u } ^ { t } = \left\{ u _ { 1 } , . . . , u _ { t } \right\}$ 分别为 $t$ 时刻的观测量和控制输入； ${ n } ^ { t } = \left\{ { { n } _ { 1 } } , . . . , { { n } _ { t } } \right\}$ 为数据关联表，每个 $n _ { t }$ 代表 $t$ 时刻观测到的路标的索引。

UFastSLAM算法采用一个无迹粒子滤波器对机器人路径进行估计，其中每个粒子都包含一份地图信息，再用 $N$ 个独立的路标估计来进行地图估计，每个路标都采用一个UKF 来估计。因此，假设在UFastSLAM算法中的粒子数是 $M$ 个，那么UKF的数量就是 $M \times N$ 个，则 $t$ 时刻第 $i$ 个粒子的组成表达式为

$$
{ \cal { S } } _ { t } ^ { [ i ] } = \left\{ s ^ { t , [ i ] } , \mu _ { 1 , t } ^ { [ i ] } , { \Sigma } _ { 1 , t } ^ { [ i ] } , . . . , \mu _ { N , t } ^ { [ i ] } , { \Sigma } _ { N , t } ^ { [ i ] } \right\}
$$

其中： $s ^ { t , [ i ] }$ 为第 $i$ 个粒子对机器人的路径估计； $\mu _ { 1 , t } ^ { [ i ] }$ 和 $\Sigma _ { 1 , t } ^ { [ i ] }$ 分别代表在第 $i$ 个粒子包含的地图中第 $N$ 个路标的均值和协方差。

在UFastSLAM算法中，机器人位姿通过式(3)采样得到

$$
\boldsymbol { s } _ { t } \sim \boldsymbol { q } \left( \boldsymbol { s } _ { t } \big | s ^ { t - 1 , [ i ] } , z ^ { t } , u ^ { t } , n ^ { t } \right)
$$

重要性权值 $w _ { t } ^ { [ i ] }$ 由式(4)得到

$$
w _ { t } ^ { [ i ] } = \frac { \Xi \sharp \dddot { \dot { \gamma } \mathfrak { J } } \cdot \sqrt { \mathfrak { J } } \dag \mathrm { \mu } } { \Xi \ddagger \{ \mathfrak { J } \mathfrak { J } \cdot \sqrt { \mathfrak { J } } \dag \mathrm { \mu } }  = \frac { p \left( s ^ { t , [ i ] } \mid z ^ { t } , u ^ { t } , n ^ { t } \right) } { q \left( s ^ { t - 1 , [ i ] } \mid z ^ { t - 1 } , u ^ { t - 1 } , n ^ { t - 1 } \right) q \left( s _ { t } \mid s ^ { t - 1 , [ i ] } , z ^ { t } , u ^ { t } , n ^ { t } \right) }
$$

UFastSLAM算法的最后一步就是根据粒子的权值大小对粒子进行重采样。

# 2 基于自适应渐消UPF的UFastSLAM方法

UFastSLAM算法依然存在粒子退化现象，除了重采样使得粒子退化，从根源上说，粒子退化是由于所使用的粒子并不是从后验分布中采样而来，而是从一个近似后验分布的建议分布函数中采样得到的。因此，随着算法不断迭代、重采样的不断进行，粒子退化无法避免。针对以上问题，提出基于自适应渐消UPF建议分布的UFastSLAM算法，同时采用自适应部分系统重采样方法对粒子集进行重采样。

# 2.1自适应渐消UPF建议分布

自适应渐消UPF（后文简称AF-UPF）以粒子滤波为基本框架，同时将渐消滤波与UT变换相结合产生参数可自适应调节的建议分布函数，充分利用系统最新观测信息中的有效信息，使得建议分布更加接近真实后验分布，对过程中参数变动有更好的自适应性。

考虑非线性动态系统：

$$
\begin{array} { c } { x _ { t } = f \big ( x _ { t - 1 } , w _ { t - 1 } \big ) } \\ { z _ { t } = h \big ( x _ { t } , \nu _ { t } \big ) } \end{array}
$$

其中： $x _ { t }$ 、 $z _ { t }$ 分别为 $t$ 时刻系统的状态向量和观测向量； $w _ { t }$ 、$\nu _ { { } _ { t } }$ 为具有零均值和协方差分别为 $Q _ { t }$ 和 $R _ { t }$ 的过程噪声和观测噪声。则AF-UPF算法描述如下：

a）状态增广。

$$
\boldsymbol { x } _ { t - 1 } ^ { a , i } = \left[ \begin{array} { l l l } { \boldsymbol { x } _ { t - 1 } ^ { i } } & { \boldsymbol { 0 } } & { \boldsymbol { 0 } } \end{array} \right] ^ { T } = \left[ \begin{array} { l l l l l l } { \boldsymbol { x } _ { x , t - 1 } ^ { i } } & { \boldsymbol { x } _ { y , t - 1 } ^ { i } } & { \boldsymbol { x } _ { \phi , t - 1 } ^ { i } } & { \boldsymbol { 0 } } & { \boldsymbol { 0 } } \end{array} \right] ^ { T }
$$

$$
P _ { t - 1 } ^ { a , i } = \left[ \begin{array} { c c c } { { P _ { t - 1 } ^ { i } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { Q _ { t } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { R _ { t } } } \end{array} \right]
$$

其中： $x _ { t - 1 } ^ { a , i }$ 为增广状态向量； $x _ { t - 1 } ^ { i }$ 为先验状态向量； $P _ { t - 1 } ^ { a , i }$ 为增广协方差矩阵。

b）通过对称采样得到 $L = 2 N + 1$ 个 sigma 点， $N$ 为估计向量的维数.

$$
\chi _ { t - 1 } ^ { a ( 0 ) , i } = x _ { t - 1 } ^ { a , i }
$$

$$
\chi _ { t - 1 } ^ { a ( k ) , i } = x _ { t - 1 } ^ { a , i } + \left( \sqrt { \left( N + \lambda \right) P _ { t - 1 } ^ { a , i } } \right) _ { k } \left( k = 1 , . . . , N \right)
$$

$$
{ \chi } _ { t - 1 } ^ { a \left( k \right) , i } = x _ { t - 1 } ^ { a , i } - \left( \sqrt { \left( N + \lambda \right) P _ { t - 1 } ^ { a , i } } \right) _ { k } \left( k = N + 1 , . . . , 2 N \right)
$$

其中： $k$ 为矩阵的第 $k$ 列； $\lambda = \alpha ^ { 2 } \left( N + \kappa \right) - N$ 为尺度参数，常量$\alpha { \left( 0 < \alpha < 1 \right) }$ 决定了 sigma 点在均值附近的分布， $\kappa$ 是次级尺度调节参数，一般设置为0。这些sigma 点通过非线性函数进行

传递，产生预测的sigma样本点：

$$
\overline { { \chi } } _ { t } ^ { ( k ) , i } = f \big ( \chi _ { t - 1 } ^ { ( k ) , i } \big )
$$

$$
\overline { { Z } } _ { t } ^ { ( k ) , i } = h \Big ( \overline { { \chi } } _ { t } ^ { ( k ) , i } \Big )
$$

c）对sigma样本点进行加权处理，得到输出变量的先验估计。其中系统状态的均值和协方差估计为

$$
\hat { x } _ { t | t - 1 } ^ { i } = \sum _ { k = 0 } ^ { 2 N } w _ { m } ^ { ( k ) } \overline { { \chi } } _ { t } ^ { ( k ) , i }
$$

$$
P _ { t | t - 1 } ^ { i } = \sum _ { k = 0 } ^ { 2 N } w _ { c } ^ { ( k ) } \left( \overline { { \chi } } _ { t } ^ { ( k ) , i } - \widehat { x } _ { t | t - 1 } ^ { i } \right) \left( \overline { { \chi } } _ { t } ^ { ( k ) , i } - \widehat { x } _ { t | t - 1 } ^ { i } \right) ^ { T }
$$

其中： $w _ { m } ^ { ( k ) }$ 和 ${ w _ { c } ^ { ( k ) } }$ 分别为第 $k$ 个 sigma 点的权值的均值和协方差。

观测量的均值和协方差估计为

$$
\hat { z } _ { t } ^ { i } = \sum _ { k = 0 } ^ { 2 N } w _ { m } ^ { ( k ) } \overline { { Z } } _ { t } ^ { ( k ) , i }
$$

$$
P _ { z _ { t } z _ { t } } = \sum _ { k = 0 } ^ { 2 N } w _ { c } ^ { ( k ) } \left( \overline { { Z } } _ { t } ^ { ( k ) , i } - \hat { z } _ { t } ^ { i } \right) \left( \overline { { Z } } _ { t } ^ { ( k ) , i } - \hat { z } _ { t } ^ { i } \right) ^ { T }
$$

系统状态与观测量的协方差估计为

$$
P _ { x _ { t } z _ { t } } = \sum _ { k = 0 } ^ { 2 N } w _ { c } ^ { ( k ) } \left( \overline { { \chi } } _ { t } ^ { ( k ) , i } - \hat { x } _ { t | t - 1 } ^ { i } \right) \left( \overline { { Z } } _ { t } ^ { ( k ) , i } - \hat { z } _ { t } ^ { i } \right) ^ { T }
$$

UPF的增益为

$$
K _ { t } = P _ { x _ { t } z _ { t } } P _ { z _ { t } z _ { t } } ^ { - 1 }
$$

d）利用渐消滤波思想采用一步算法计算渐消因子：

$$
\alpha _ { t } = \operatorname* { m a x } \left\{ 1 , t r \big ( N _ { t } \big ) t r \big ( M _ { t } \big ) ^ { - 1 } \right\}
$$

其中： $t r ( \mathbf { \theta } )$ 为求迹符号； $N _ { \iota }$ 和 $\boldsymbol { M } _ { t }$ 在非线性滤波中计算公式如下：

$$
\boldsymbol { N } _ { t } { = } \boldsymbol { V } _ { t } \boldsymbol { V } _ { t } ^ { T } - \boldsymbol { H } _ { t } \boldsymbol { Q } _ { t } \boldsymbol { H } _ { t } ^ { T } - \boldsymbol { R } _ { t }
$$

$$
M _ { t } = H _ { t } F _ { t } P _ { x _ { t } z _ { t } } F _ { t } ^ { T } H _ { t } ^ { T }
$$

其中： $V _ { t } = \hat { z } _ { t } - h \big ( x _ { t } \big )$ ， $H _ { t } = \frac { \hat { \partial } h \big ( x _ { t } \big ) } { \hat { \partial } x } \Bigg | _ { x = \hat { x } _ { t \mid t - 1 } } ~ , ~ F _ { t } = \frac { \hat { \partial } f \big ( x _ { t } \big ) } { \hat { \partial } x } \Bigg | _ { x = \hat { x } _ { t \mid t - 1 } } ~ \circ$

e）将渐消滤波与UPF相结合，计算出更新后状态的均值和方差：

$$
x _ { t } ^ { i } = \hat { x } _ { t \left| t - 1 \right. } ^ { i } + K _ { t } \left( \bar { Z } _ { t } ^ { ( k ) , i } - \hat { z } _ { t } ^ { i } \right)
$$

$$
P _ { t } ^ { i } = P _ { t | t - 1 } ^ { i } - \alpha _ { t } K _ { t } P _ { z _ { t } z _ { t } }
$$

得到建议分布函数 $N { \left( x _ { t } ^ { i } , P _ { t } ^ { i } \right) }$ 。由渐消因子 $\alpha _ { t }$ 对权值方差进行自适应调节，可以充分提取观测信息中的有效信息，抑制异常干扰对状态模型和观测模型的不利影响，使建议分布更加接近真实后验分布。

# 2.2自适应部分系统（APS）重采样

自适应部分系统重采样的基本思想为：若有效粒子数小于设定阈值，则根据权值大小与设定阈值相比来对粒子进行分类，权值中等的粒子不进行重采样，权值过大和过小的粒子进行优化组合，仅对组合后的部分粒子进行系统重采样，从而降低粒子的退化。具体操作步骤如下：

计算粒子集中粒子权值的大小并归一化为 $\hat { w } _ { k } ^ { i }$ ，再将有效粒子数 $N _ { \it e f f }$ 与设定阈值 $N _ { g }$ 相比，若 $N _ { e f f } < N _ { g }$ 则进行重采样，有效粒子数由式(20)计算。

$$
{ N _ { e f f } = 1 / \left( \sum _ { i = 1 } ^ { n } \left( \hat { w } _ { k } ^ { i } \right) ^ { 2 } \right) }
$$

根据有效粒子数设定两个权值的门限值 $w _ { h }$ 、 $w _ { l }$ （ $0 < w _ { l } < w _ { h }$ )，将每个粒子的权值与门限值一一比较之后优化组合为两部分，一部分为 $w _ { k } ^ { i } < w _ { l }$ 和 $w _ { k } ^ { i } > w _ { h }$ 的权值较小或者较大的不稳定粒子，另一部分为 $w _ { l } < w _ { k } ^ { i } < w _ { h }$ 的权值适中的粒子，仅对权值不稳定的那部分粒子进行系统重采样后，再与未进行重采样的粒子组成新的粒子集，通过这种分配组合能够增加粒子的多样性。

# 2.3基于AF-UPF 建议分布和APS 重采样的UFastSLAM方法

提出的基于 AF-UPF 建议分布和 APS 重采样的UFastSLAM算法，采用自适应渐消无迹粒子滤波器完成对机器人位姿的估计，可以获得更接近后验分布的建议分布函数，采用无迹卡尔曼滤波器完成对路标位置的估计，采用自适应部分系统重采样的方法对粒子进行重采样，有效降低粒子退化程度。提出算法实现过程如下：

a）初始化无迹粒子滤波器。根据先验分布获得初始粒子集，粒子集中粒子数为 $N$ ，并将其权值统一分配为 $1 / N$ 。b）重要性采样。根据AF-UPF计算出粒子的后验位置和姿态建议分布，从建议分布中采样获得新的粒子集，并计算粒子集中粒子的归一化权重。c）判断新的环境观测值是否为地图中已存特征路标。如果是已存路标，则采用单一兼容最近邻方法进行数据关联，同时更新机器人位姿和路标位置；如果不是已存路标，则将新的路标加入环境地图中。

d）重采样。在有效粒子数小于设置阈值时，采用自适应部分系统方法对粒子进行重采样。

# 3 仿真结果

为了验证提出算法的性能，利用TimBailey公开的仿真环境和MATLAB2010a仿真软件，在稀疏路标环境下对提出算法和UFastSLAM算法分别进行仿真实验并比较。仿真中用到的运动模型和观测模型如式(21)和(22)所示。

$$
\left[ \begin{array} { l } { x _ { t } } \\ { y _ { t } } \\ { \varphi _ { t } } \end{array} \right] = \left[ \begin{array} { l } { x _ { t - 1 } + V _ { t } \cdot \Delta t \cdot \cos { \left( \varphi _ { t - 1 } + \gamma \right) } } \\ { y _ { t - 1 } + V _ { t } \cdot \Delta t \cdot \sin { \left( \varphi _ { t - 1 } + \gamma \right) } } \\ { \varphi _ { t - 1 } + \displaystyle \frac { V _ { t } \cdot \Delta t } { B } \cdot \sin { \left( \gamma \right) } } \end{array} \right] + \delta _ { t }
$$

其中： $\left( x _ { t } , y _ { t } , \varphi _ { t } \right)$ 为机器人在 $t$ 时刻的位姿； $\Delta t$ 为采样时间间隔;$\boldsymbol { u } = \left[ V \quad \boldsymbol { \gamma } \right] ^ { T }$ 为控制输入，分别表示机器人在 $t$ 时刻的速度和方向角； $\delta _ { t }$ 为运动高斯噪声。

$$
\left[ \begin{array} { l } { r _ { i } } \\ { \theta _ { i } } \end{array} \right] = \left[ \begin{array} { c } { \sqrt { \left( x _ { i } - x _ { t } \right) ^ { 2 } + \left( y _ { i } - y _ { t } \right) ^ { 2 } } } \\ { \tan ^ { - 1 } \displaystyle \frac { y _ { i } - y _ { t } } { x _ { i } - x _ { t } } - \varphi _ { t } } \end{array} \right] + \varepsilon _ { t }
$$

其中： $\left( x _ { i } , y _ { i } \right)$ 为地图中已存的第 $i$ 个路标的坐标； $\left( r _ { i } , \theta _ { i } \right)$ 为传感器探测到该路标相对于机器人的距离和方向夹角； $\boldsymbol { \varepsilon } _ { t }$ 为服从高斯分布的观测噪声。

仿真实验的参数配置如表1所示。

表1仿真参数配置  

<html><body><table><tr><td>参数</td><td>值</td><td>参数</td><td>值</td></tr><tr><td>机器人轴距</td><td>2m</td><td>最大观测范围</td><td>30m</td></tr><tr><td>运动速度</td><td>3m/s</td><td>运动噪声</td><td>0.4m/s,4°</td></tr><tr><td>最大转向角</td><td>30°</td><td>观测噪声</td><td>0.2m,2°</td></tr></table></body></html>

在粒子数为50个的情况下，对UFastSLAM和本文提出算法分别进行仿真，得到的仿真结果如图1、2所示。其中蓝色线条为实际路径，红色线条为估计路径，绿色星号为实际路标，红色圆点为估计路标。可以看出，本文提出算法得到的估计路径和实际路径重合度更高，对路标的估计也更准确，都具有比UFastSLAM算法更高的估计精度。

![](images/d874f35403ac057fc87f6d6f0f7db166fa79931b576ef74ed1d8976b2d0107f9.jpg)  
图1UFastSLAM算法的仿真结果

![](images/f342c41f5e83fff8228664a31813f23b82397fab6c2798be6c5211281793188e.jpg)  
图2本文提出算法的仿真结果

# 3.150个粒子时的算法性能比较

粒子数为50个时，两种算法的机器人位姿和路标位置横、纵坐标估计误差曲线如图3、4所示。可以看出，虽然本文提出算法有小部分误差略大于UFastSLAM算法，但是对整个地图估计和机器人路径估计的准确度明显要大于UFastSLAM算法。

![](images/3a723a6440f3e76c47b87493dc25ccf1f1c51c86eb7bad51ab15e958a6e83637.jpg)  
图3两种算法的机器人位姿估计 $\mathbf { x }$ 向、y向误差

![](images/dda64d730aa65c292ceb7433c0561530ca28c23851ba5fbbc86cf0362b97abb4.jpg)  
图4两种算法的路标位置估计 $\textbf { x }$ 向、y向误差

为了更清楚地看出两种算法的估计性能，利用机器人位姿和路标位置的均方根误差（rootmean square error,RMSE）来衡量，仿真结果如图5所示。其中蓝色柱状代表本文提出算法，棕色柱状代表UFastSLAM算法。从图中可以看出，本文提出算法在机器人位姿估计和路标位置估计两方面都具有更高的估计精度。

![](images/c75174e719f0d8e651b0c2caa3d01ffa112167b196525d6e809439657f8199d2.jpg)  
图5两种算法RMSE

# 3.2粒子数不同时的性能比较

在粒子数分别为10、30、50个时，分别对本文提出算法和UFastSLAM算法进行20次仿真实验，并用20次仿真的机器人位姿估计的RMSE均值和标准差作为评价标准，实验结果如图6所示。其中柱状代表均值，线棒代表标准差。从图中可以看出，随着粒子数的增多，UFastSLAM算法估计精度有很大的提升，但是本文提出的算法RMSE均值变化不大，也就是说提出算法不是很依赖于粒子数。因此，本文提出算法有效地解决了粒子退化的问题，可以用较少的粒子达到较高的估计精度，在提高计算效率的同时保证了估计的精度。

![](images/beee158856c51f9c565fa5b8418e308683529558755ab3c762e1277c6c5d845e.jpg)  
图6不同粒子数时两种算法的RMSE

# 3.3算法复杂度的比较

算法复杂度的对比可以通过对相同粒子数时两种算法的RMSE值和运行时间作比较，以及通过比较在RMSE值差不多时两种算法所需要的粒子数来得出相应的结论。两种算法的对比分别如表2、3所示。表2显示，在粒子数相同时，提出算法在运行时间上和UFastSLAM差不多，但是对位姿估计更为准确；表3显示，在位姿估计的RMSE均值大致相同时，提出算法需要的粒子数远小于UFastSLAM。因此，运用提出算法能够降低计算的复杂度，提高算法运行效率，很好地解决了由于重采样造成的粒子退化问题。

表250个粒子时RMSE 和运行时间对比  

<html><body><table><tr><td rowspan="2">算法</td><td colspan="2">RMSE/m</td><td rowspan="2">运行时间/s</td></tr><tr><td>均值</td><td>标准差</td></tr><tr><td>提出的算法</td><td>0.7597</td><td>0.1024</td><td>172.256</td></tr><tr><td>UFastSLAM</td><td>0.9831</td><td>0.1329</td><td>176.290</td></tr></table></body></html>

表3RMSE近似相等时粒子数对比  

<html><body><table><tr><td rowspan="2">算法</td><td colspan="2">RMSE/m</td><td rowspan="2">粒子数/个</td></tr><tr><td>均值</td><td>标准差</td></tr><tr><td>提出的算法</td><td>0.8155</td><td>0.1442</td><td>30</td></tr><tr><td>UFastSLAM</td><td>0.8157</td><td>0.1301</td><td>70</td></tr></table></body></html>

# 4 结束语

文中提出的基于自适应渐消无迹粒子滤波建议分布，同时采用自适应部分系统重采样的UFastSLAM方法有效地解决了粒子的退化问题。该算法在采样过程中融入渐消滤波，通过渐消因子产生可自适应调节的建议分布函数，使其更加接近后验分布函数，在提高粒子采样效率的同时，根据粒子权重大小将粒子进行分配、优化组合后再对部分粒子进行重采样，保证了粒子的多样性，避免了粒子的贫化现象。通过仿真实验表明，与UFastSLAM相比，所提算法能够用较少的粒子较精确地实现机器人的自主定位和构图。

# 参考文献：

[1]Durrant W H, Bailey T. Simultaneous localization and mapping: Part I [J].IEEE Robotics and Automation Magazine,2006,13 (2): 99-108.  
[2]Bailey T,Durrant WH. Simultaneous localization and mapping: part I[ [J]IEEE Robotics and Automation Magazine,2006,13 (3): 108-117.  
[3]刘婕．复杂场景多特征融合粒子滤波目标跟踪[D].重庆：重庆理工大学,2015.  
[4] 丛楚滢，王从庆，丁臻极，等．一种小型无人机的 FastSLAM 算法[J].华中科技大学学报：自然科学版,2015(z1):420-423,427.  
[5]Kim C, Sakthivel R, Chung WK,et al. Unscented FastSLAM: a robust andefficient solution to the SLAMProblem [J].IEEE Robotics,2008,24 (4):808-820.  
[6]Havangi R,Taghirad H D,Nekoui M A,et al.A square root unscentedFastSLAM with improved proposal distribution and resampling [J]. IEEETrans on Industrial Electronics,2014,61(5): 2334-2345.  
[7]HaydarA,Emre O T,Fikret A,et al. Square root unscented based FastSLAMoptimized by particle swarm optimization passive congregation [C]//Procof IEEE International Conference on Mechatronics and Automation. 2013:469-475.  
[8]吕太之，赵春霞．一种基于 SR-UKF的 FastSLAM 算法[J].计算机应用研究,2012,29(10):3725-3727,3735.  
[9]王宏健，王晶，刘振业，等．基于迭代扩展 Kalman 滤波建议分布和线性优化重采样的快速同步定位与构图[J]．电子与信息学报,2014 (2):318-324.  
[10]高社生，薛丽，魏文辉．渐消自适应Unscented 粒子滤波及其在组合导航中的应用 [J]．西北工业大学学,2012,30(1):27-31.  
[11]杨柳庆，肖前贵，牛妍，等．基于渐消卡尔曼滤波器的定位系统设计[J]．南京航空航天大学学报,2012,44(1):134-138.  
[12] 刘丹，段建民，于宏啸．基于自适应渐消 EKF 的 FastSLAM 算法[J].系统工程与电子技术,2016(3):644-651.  
[13]冯晓．基于粒子滤波器的自主式水下机器人导航定位算法研究 [D]青岛：中国海洋大学,2013.