# 精确时延补偿的自适应旁瓣相消射电抗干扰方法研究

黄达¹，王壮¹，程翥²，董 亮³，苏瑶4．国防科技大学电子科学与工程学院ATR国防科技重点实验室，湖南 长沙410073；2.国防科技大学电子科学与工程学院电子工程所，湖南 长沙410073；3.中国科学院云南天文台，云南 昆明650011；4.西安电子科技大学，陕西 西安710071)

摘要：导航信号作为射电干扰信号影响L波段射电观测时，与雷达、通信领域的干扰不同，其功率通常小于噪声功率，使得利用干扰信号相关性的传统抗干扰方法效果不佳，且缺乏有效的评价指标。针对以上问题，依据射电信号处理流程构建了射电抗干扰系统框架，并从射电观测数据应用出发，给出了干扰抑制度和信号损失度两个指标。同时提出在精确补偿时延后利用抑制干扰子空间噪声分量的自适应旁瓣相消方法来消除导航信号的影响；仿真结果表明，本方法能有效抑制导航信号对射电观测的影响，且性能优于传统基于特征子空间的自适应旁瓣相消方法。

关键词：射电天文抗干扰；自适应旁瓣相消；导航信号；可变分数时延滤波器中图分类号：P161 文献标识码：A 文章编号：1672-7673(2016)03-0284-09

随着射电天文的发展，国际通讯联盟所划分的射电观测频段已不能满足射电天文研究的需求，观测保护频段以外的射电源，常常受到干扰信号的影响，极大限制了射电源的观测质量。导航信号是L频段射电观测的常见干扰，根据全球定位系统和北斗导航卫星的ICD 文件可知①-②，全球定位系统导航信号的主要频率是L1： $1 ~ 5 7 5 . 4 2 \pm 1 . 0 2 3 ~ \mathrm { M H z }$ 、L2: $1 ~ 2 2 7 . 6 \pm 1 0 . 2 3 ~ \mathrm { M H z }$ 等，北斗导航信号的主要频率是：B1： $1 5 5 6 . 0 9 8 \pm 2 . 0 4 6 \mathrm { M H z }$ 、B3： $1 2 6 8 . 5 2 \pm 1 0 . 2 3 \mathrm { M H z }$ 等，而这些频率与红移的分子谱线、脉冲星等射电源的观测频段重合。同时，根据ICD文件中导航信号的最小电平可以换算其功率通量谱密度为$- 1 9 6 \mathrm { \sim } - 2 0 1 ~ \mathrm { d B w / ( \mathrm { m } ^ { 2 } / H z ) }$ ，而在同样带宽下 $1 ~ \mathrm { m J y }$ 的射电信号功率通量谱密度为 $- 2 9 0 ~ \mathrm { d B w / ( \Omega m ^ { 2 } / H z ) }$ ，因此在接收时导航信号比射电信号强 $8 9 \sim 9 1 ~ \mathrm { d B }$ 。此外，天线接收系统对接收信号也有影响，由于导航信号往往从旁瓣进入射电接收机，经过放大、滤波等过程其功率通常小于噪声功率但大于射电信号功率。

通过以上分析可知，如何抑制射电观测中弱于噪声的干扰信号是本文讨论的主要问题与难点。对于导航信号这类弱于噪声的干扰信号而言，完全获取信号的先验信息难度较大，但可利用信号本身的特点来抗干扰，如空间特性和相关特性。同时，抗干扰方法的实施难免对射电信号处理有一定影响，因此抗干扰系统的建立既需要有效利用干扰信号本身的特点，同时也需尽量避免对射电信号处理的影响。进一步来说，有效地利用干扰信号的空间特性需要基于多通道接收的方式，文[1-2］利用干涉仪和相控阵天线自身多通道的特性提取干扰信号的子空间，通过正交投影的方式消除干扰信号，然而由于信号空间与干扰空间不垂直，导致对观测信号影响较大。为了利用干扰信号的相关性，借助辅助天线是常用方式。文[3-4]通过辅助天线估计更为精准的干扰子空间，并运用如正交子空间、互子空间投影和多阵列旁瓣相消等方式抑制干扰信号。对于大型单射电天线而言，要利用干扰信号的空间特性和相关性，则需要借助多个辅助天线。文[5]从雷达信号处理角度出发，基于特征子空间的自适应旁瓣相消方法，利用辅助阵列中强干扰信号的特征子空间与噪声子空间良好的垂直性，消除了接收信号中的强干扰信号。对于抑制射电观测中弱于噪声的导航信号而言，需根据射电信号处理流程重新构建抗干扰系统框架，并且改进自适应旁瓣相消方法有效抑制导航信号。同时考虑到射电观测数据应用，应给出新的评价指标来评估干扰抑制程度和信号损失程度。此外，实际情况中射电天线（主天线)口径通常较大，使架设辅助阵列离主天线较远，因此由于空间位置产生的信号时延导致导航信号相关性减少，需要考虑时延补偿的问题。

综上所述，本文首先依据射电信号处理流程构建了基于辅助天线的射电抗干扰系统框架，并从射电观测数据应用出发，给出了干扰抑制度和信号损失度两个指标。同时本文在精确补偿主天线接收信号时延后，利用抑制干扰子空间噪声分量的自适应旁瓣相消方法来抑制导航信号的影响。最后利用蒙特卡洛仿真方式，讨论了不同主天线和辅助阵列间距（即主、辅天线距离）、干扰波达角度、观测时间、辅助阵元口径和阵元数量对抗干扰性能的影响。

# 1基于辅助阵列的射电抗干扰系统框架构建

在大型单射电天线中，利用导航信号的空间特性和相关性抑制干扰，需要借助多通道的辅助天线实现，即辅助阵列。自适应旁瓣相消作为常用的抗干扰方法之一，本质是利用辅助阵列与主天线中干扰信号的相关性和干扰的空间特性获得辅助阵列的最优权矢量，使合成的天线方向图在干扰方向上产生零点，达到干扰抑制的目的。此外，为了降低抗干扰系统对射电信号处理的影响，抗干扰系统应独立于射电信号处理流程之外。根据以上分析，建立基于辅助阵列的射电抗干扰系统框架，如图1。

![](images/51ffe7dfc3229aff32bde32f9b38c85294bf1f6d1749b982805e5673fa93e257.jpg)  
图1基于辅助天线的射电抗干扰系统框架  
Fig.1Framework of the radio anti-interference based on auxiliary antenna

通常射电接收机带宽比干扰信号带宽宽得多，例如上海天文台 $6 5 \mathrm { m }$ 射电天线 $4 4 2 { \sim } 2 4 0 0 \mathrm { M H z } ^ { [ 6 ] }$ ，云南天文台 $4 0 \mathrm { m }$ 射电天线 $3 0 0 { \sim } 8 0 0 ~ \mathrm { M H z } ^ { [ 7 ] }$ ，因此需要选取包含导航信号的中频信号 $y ( t { + } \tau )$ （如图1中“1"线)为抗干扰系统输入的原始射电接收信号。值得注意的是，混频器1是补偿主天线接收机中混频器本振频率与辅助天线接收机中心频率的差异。为了降低对采集设备的性能要求，中频信号 $y ( t + \tau )$ 与辅助阵列 $( x _ { 1 } ( t ) , \cdots , x _ { k } ( t ) )$ 的信号通过带通滤波器选取存在导航信号的频带信号，在经过混频器2和低通滤波器处理后进入多路数据采集系统对信号进行采集。而由于空间位置造成的时延需要通过时延滤波器实现精确补偿，即得到时延补偿后的主天线信号 $y ( n )$ 。补偿后的 $y ( n )$ 与辅助阵列信号$( x _ { 1 } ( n ) , \cdots , x _ { k } ( n ) )$ 通过自适应旁瓣相消方法(抗干扰算法处理)得到 $\stackrel { \sim } { y } ( n )$ 。将 $\stackrel { \sim } { y } ( n )$ 进行数模转换、上变频等一系列逆向处理得到 $\{ { \stackrel { \sim } { y } } ( t )$ ，之后与通过带阻滤波器的 $y ( t + \tau )$ 信号相加得到抗干扰后的信号$\stackrel { \sim } { y } ( t + \tau )$ 。以上抗干扰过程中需要解决几个关键问题：

(1)指标构建：与雷达、通信领域不同，射电天文抗干扰中干扰信号通常小于噪声信号。因此有必要着眼于射电天文数据应用提出评价指标来评估干扰消除程度和信号损失程度。（2)时延补偿：由于射电天文望远镜口径通常较大，利用辅助天线抗干扰时，其架设位置离射电天线（主天线)位置较远，因此需要精确补偿信号时延，提高导航信号的相关性。(3)自适应旁瓣相消：完全已知所有导航卫星的先验信息难度较大，但其运行轨道相对固定易于预测，因此可利用导航信号良好的空间特性消除影响。自适应旁瓣相消方法中基于特征子空间类的方法可以在干扰较强时，有效避免估计误差的影响，获得辅助阵列的最优权矢量。然而导航信号功率通常小于噪声功率，因此需要改进此类方法。

# 2精确时延补偿的自适应旁瓣相消射电抗干扰方法

# 2. 1 评价指标

在射电抗干扰中，干扰信号功率通常小于噪声功率，传统的性能指标如相消比等，无法有效地刻画干扰和信号分量的变化程度。为解决此问题，本文从射电观测数据应用出发，以辅助天线接收信号以及先验的射电信号为标尺，分别衡量了抗干扰前后主天线接收信号中干扰信号与射电信号的相关程度，构建了干扰抑制度 $G _ { \mathrm { r } }$ 和信号损失度 $G _ { \mathrm { s } }$ 表征干扰抑制程度与信号损失程度，其定义分别为：干扰抑制度 $G _ { \mathrm { { I } } }$ ：

$$
\begin{array} { l } { G _ { \mathrm { I } } = \displaystyle \frac { \operatorname* { m a x } \left[ R _ { x y } \left( \tau _ { 1 } \right) \right] } { \operatorname* { m a x } \left[ R _ { x \widetilde { \gamma } } \left( \tau _ { 2 } \right) \right] } = \displaystyle \frac { \operatorname* { m a x } \left\{ E \left[ \gamma \left( t \right) x ^ { * } \left( t - \tau _ { 1 } \right) \right] \right\} } { \operatorname* { m a x } \left\{ E \left[ \widetilde { \gamma } \left( t \right) x ^ { * } \left( t - \tau _ { 2 } \right) \right] \right\} } } \\ { \displaystyle = \frac { \widetilde { F } \left( \theta _ { \mathrm { I } } \right) } { { F \left( \theta _ { \mathrm { I } } \right) } } \displaystyle \frac { \operatorname* { m a x } \left\{ E \left[ I \left( t \right) I ^ { * } \left( t + t _ { 0 } - \tau _ { 1 } \right) \right] \right\} } { \operatorname* { m a x } \left\{ E \left[ I \left( t \right) I ^ { * } \left( t + t _ { 0 } - \tau _ { 2 } \right) \right] \right\} } = \frac { \widetilde { F } \left( \theta _ { \mathrm { I } } \right) } { { F \left( \theta _ { \mathrm { I } } \right) } } ~ , } \end{array}
$$

同理，信号损失度 $G _ { \mathrm { s } }$ ：

$$
G _ { \mathrm { s } } = \frac { \displaystyle \operatorname* { m a x } \left[ R _ { s \gamma } ( \tau _ { 1 } ) \right] } { \displaystyle \operatorname* { m a x } \left[ R _ { s \widetilde { \gamma } } ( \tau _ { 2 } ) \right] } = \frac { \widetilde { F } ( \theta _ { \mathrm { s } } ) } { F ( \theta _ { \mathrm { s } } ) } ~ .
$$

其中， $R _ { x y } ( \tau _ { 1 } ) \ : , \ : \ : R _ { x \tilde { y } } ( \tau _ { 2 } )$ 表示抗干扰前、后辅助天线接收信号 $x$ 与主天线接收信号 $y ( \stackrel { \sim } { y } )$ 的互相关函数;$R _ { s y } ( \pmb { \tau } _ { 1 } )$ 、 $R _ { s \tilde { y } } ( \tau _ { 2 } )$ 表示抗干扰前、后参考射电信号 $s$ 与主天线接收信号 $y ( \tilde { y } )$ 的互相关函数；“\~”表示抗干扰后变化的量；max表示取最大值。通过(1)式和(2)式可知，干扰信号与射电信号相关性的变化可直接反映方向图在干扰和信号方向上的变化。

# 2.2 时延补偿

为了获取良好的滤波器通带特性，本文采用基于非迭代的加权最小二乘的可变分数时延全通滤波器实现分数时延补偿[8]，滤波器结构基于farrow结构[9]，该结构基于不同准则逼近理想的滤波器获得滤波器系数后，利用高阶分数时延的多项式近似得到滤波器系数。此方式即可将分数时延与滤波器系数分离，使整个滤波器的传递函数简化为分数时延对多个子滤波器的加权和，因此该结构大大减少了求解滤波器系数的复杂度。加权最小二乘滤波方法求解滤波器系数的主要思想是在一定通带范围和时延因子(分数时延与采样频率的乘积)范围内，使可变分数时延滤波器的频率响应与理想的分数时延频率响应函数误差最小，即

$$
\mathrm { m i n } J _ { { \cal H } } ( B ) = \mathrm { m i n } \int \displaylimits _ { 0 } ^ { \alpha \pi } \int W ( \omega , \ p ) | e _ { \cal H } ( \omega , \ p ) | ^ { 2 } \mathrm { d } \omega \mathrm { d } p ,
$$

其中， $B$ 是由滤波器系数组成的矩阵； $\boldsymbol { W } ( \boldsymbol { \omega } , \boldsymbol { p } )$ 是非负的权值函数； $\boldsymbol { e } _ { H }$ 为可变分数时延滤波器与理想分数时延频率响应的误差函数； $p$ 为除去整数部分的分数时延因子。不难发现(3)式中存在积分过程，利用泰勒级数展开可简化积分过程，即通过非迭代的方式，快速获得滤波器系数。图2（a)和图2（b)分别是分数时延因子 $p$ 变化范围为 $- 0 . 5 \sim 0 . 5$ ，归一化频率 $\omega$ 变化范围为 $0 \sim 0 . 9 \pi$ 时，基于加权最小二乘滤波的可变分数时延全通滤波器输出的相位时延和与理想的分数时延频率响应函数误差结果。

![](images/a4f480037cce654a79372be214925a7bf9f005a657fd375f1d26413f49781fa8.jpg)  
图2WLS可变分数时延滤波器结果 Fig.2Results of the WLS-VFD filter

通过结果可得，基于非迭代加权最小二乘滤波的可变分数时延滤波器能在宽频带范围下可实现精确的分数时延。

# 2.3自适应旁瓣相消

自适应旁瓣相消方法的核心问题是求解最优权值矢量。基于特征子空间的自适应旁瓣相消方法是利用干扰子空间与噪声子空间的正交特性，将权值矢量向干扰子空间投影得到最优权值矢量，可见准确估计干扰子空间十分重要。辅助阵列的接收信号主要是干扰信号和噪声信号，可通过估计辅助阵列的协方差矩阵进而获得干扰子空间和噪声子空间。假设存在 $p$ 个互不相关的窄带干扰，协方差矩阵 $\hat { R } _ { x }$ 特征分解如下式：

$$
\hat { R } _ { x } = \hat { U } _ { \mathrm { I } } \hat { U } _ { \mathrm { I } } \hat { U } _ { \mathrm { I } } ^ { \mathrm { H } } + \hat { U } _ { \mathrm { N } } \hat { D } _ { \mathrm { N } } \hat { U } _ { \mathrm { N } } ^ { \mathrm { H } } \ ,
$$

其中， $\hat { R } _ { x }$ 是由 $k ( k \geq p )$ 个辅助阵元数据长度为 $N$ 的接收信号估计的协方差矩阵； $D _ { \textup { I } }$ 和 $D _ { \mathrm { v } }$ 是分别由前 $p$ 个大特征值和后 $k { - } p$ 个小特征值构成的对角阵； $U _ { \mathrm { { I } } }$ 和 $U _ { \mathrm { { N } } }$ 分别是 $D _ { \textup { I } }$ 和 $D _ { \mathrm { v } }$ 对应特征向量构成的矩阵，其列矢量分别张成的空间为干扰子空间和噪声子空间。

在射电天文观测中消除导航信号时，导航信号功率通常小于噪声功率，使得干扰子空间受噪声的扰动较大，即前 $p$ 个大特征值和后 $k { - } p$ 个小特征值差异较小，因此无法准确地获取干扰子空间。为此本文提出改进传统的基于特征子空间自适应旁瓣相消方法，其核心思想是利用噪声的平稳特性，通过后几个特征值估计干扰子空间中的噪声分量并剔除，增强干扰子空间与噪声子空间的正交性。本文从减小噪声对干扰子空间的影响和消除时延造成导航信号相关性下降这两点出发，估计最优权值矢量 $\widetilde { \boldsymbol { w } } _ { \mathrm { o p t } }$ 的步骤为：

(1)首先根据导航信号入射方向(即波达角)和主天线与辅助阵列参考阵元间的空间位置估计信号时延 $\tau$ ;

(2)根据信号时延 $\cdot$ 和采样频率计算时延因子 $I { + } p$ ，通过补零对整数时延 $I$ 补偿，通过2.2中的可变分数时延滤波器对分数时延 $p$ 补偿;

(3)通过有限长度的快拍数估计辅助阵列的协方差矩阵和主天线与辅助阵列的相关矢量，即$\hat { R } _ { x } \mathrm { ~ , ~ } \hat { R } _ { x y }$ ;

(4)对 $\hat { R } _ { x }$ 特征分解如(4)式，取后 $k { - } p$ 个小特征的平均值 λ：估计干扰子空间的噪声分量， $\hat { R } _ { x }$ 减去该平均值构成的对角阵，得到去除噪声的 $\widetilde { R } _ { x }$ ：

$$
\widetilde { R } _ { x } = \hat { R } _ { x } - \left( \frac 1 { k - p } \sum _ { i = p + 1 } ^ { k } \lambda _ { i } \right) I \ ,
$$

（5）对 $\widetilde { R } _ { x }$ 特征分解，得到 $\smash { \widetilde { U } _ { \mathrm { I } } , \widetilde { \pmb { D } } _ { \mathrm { I } } }$ ，通过(6)式得到最优权矢量，即

$$
\widetilde { w } _ { \mathrm { o p t } } = \widetilde { U } _ { \mathrm { I } } \widetilde { D } _ { \mathrm { I } } ^ { - 1 } \widetilde { U } _ { \mathrm { I } } ^ { \mathrm { H } } \hat { R } _ { x y } \ .
$$

通过以上方式可将干扰子空间的噪声分量消除一部分，使干扰子空间与噪声子空间有更好的正交性，进而获得更优的抗干扰性能。

# 3仿真结果分析

# 3.1参数设置

本文以FAST $3 0 \mathrm { m }$ 模型脉冲星天线为主天线模型[10]。观测不同的射电信号，其信号形式有较大差异，无法用统一的形式表示射电信号，因此本文用功率谱流量密度为 $1 ~ \mathrm { m J y }$ 的随机信号代替射电信号；辅助天线是由无方向性阵元构成的均匀线阵，且阵元间距设置为 $0 . 0 9 \mathrm { m }$ 。以调制C/A码B3频点L $\left( 1 2 6 8 . 5 2 \mathrm { M H z } \right)$ )的北斗导航信号为干扰信号。

为了定量地对比时延补偿对本文方法的影响和本方法较传统的基于特征子空间自适应旁瓣相消方法性能的影响，分别对比了在时延补偿和时延未补偿情况下的本文方法与基于特征子空间的自适应旁瓣相消方法，并讨论了不同主天线和辅助阵列间距(即主、辅天线距离)、干扰波达角度、观测时间、辅助阵元口径和阵元数量对抗干扰性能的影响，参数设置如表1。此外，本文利用蒙特卡洛模拟方式消除随机误差对算法评价可靠性的影响。根据大数定理可知，在置信度 $\alpha = 0 . 0 3$ ，方差为0.0743（辅助天线噪声标准差），蒙特卡洛次数为200次时，蒙特卡洛误差为 $\varepsilon = 0 . 0 1 5 8$ ，因此蒙特卡洛次数为200次时可以满足比较算法性能的要求。

表1仿真参数对比  
Table 1 Comparison of simulation parameters   

<html><body><table><tr><td></td><td>主、辅天线距离/m</td><td>阵元直径/m</td><td>干扰波达角度(0)/o</td><td>观测时间/s</td><td>辅助阵元数量</td></tr><tr><td>图3(a)(b)</td><td>30</td><td>0.5</td><td>0~5</td><td>0.01</td><td>10</td></tr><tr><td>图4(a)(b)</td><td>30</td><td>0.5</td><td>1.5</td><td>1e-5~5e-3</td><td>10</td></tr><tr><td>图4(c)(d)</td><td>30</td><td>0.1~5</td><td>1.5</td><td>0.01</td><td>10</td></tr><tr><td>图5(a)(b)</td><td>30</td><td>0.5</td><td>1.5</td><td>0.01</td><td>3~15</td></tr><tr><td>图5(c)(d)</td><td>25~45</td><td>0.5</td><td>1.5</td><td>0.01</td><td>10</td></tr></table></body></html>

# 3.2 结果分析

3.2.1主天线与辅助阵列距离的影响

主天线与辅助阵列中参考阵元的距离远近导致接收信号的时延不同进而影响导航信号的相关性。因此本文讨论了主、辅天线距离对方法性能的影响，如图3。

结合表1和图3（a)可知，随着主天线与辅助阵列距离的增加，时延补偿的本文方法干扰抑制度比时延补偿和未补偿的自适应旁瓣相消方法高15dB 左右，同时，时延未补偿的本文方法干扰抑制度，由于时延的影响随主、辅天线距离增加而下降；另外，无论时延是否补偿，本文方法和基于特征子空间的自适应旁瓣相消方法，随着主天线与辅助阵列距离增加，信号损失度相差不大，约1dB，如图3（b）。

![](images/130f06190470b6e79cc48a94262c4b2eea4a6da4e8192233eb39625b76e483fd.jpg)  
Fig.3Performancecomparison with diferent distance betweenthe main-antennaandtheauxiliaryantennasas the variable

# 3.2.2 波达方向和阵元口径的影响

不同来向的导航信号由于方向图的影响，功率差异很大，导致干扰信号(导航信号)在主天线中干噪比差异也很大；另一方面，阵元口径影响干扰信号的接收功率。因此本文讨论了不同信号波达角$\theta$ （与主瓣轴的夹角)和阵元口径对方法性能的影响，如图4。

![](images/d074a7e5192ed562dffa159d6a25b91fe2d6b58f2867cb3d150a072ef1bc84e6.jpg)  
图3不同主天线与辅助阵列距离的方法性能对比  
图4不同波达角和辅助阵元口径的方法性能对比

Fig.4Performancecomparisonwithdirectionofarrivalasthevariableandapertureoftheauxiliaryantennasasthevariable

结合表1和图4(a)可得，随着导航信号波达角远离主瓣，其信号功率也随方向图变化而减小。时延补偿和时延未补偿的本文方法干扰抑制度也随之减小，但是时延补偿的本文方法比自适应旁瓣相消方法干扰抑制度高 ${ \boldsymbol { 7 } } \sim 2 0 \mathrm { d B }$ ，而时延未补偿的本文方法仅在信号波达角小于 $2 . 5 ^ { \circ }$ 时比自适应旁瓣相消方法干扰抑制度高；图4(b)中导航信号波达角在 $1 . 5 ^ { \circ }$ 范围内信号损失度比旁瓣方向上更大，是因为合成的方向图使主瓣零陷，零陷程度越深，信号的损失越大，因此无论时延是否补偿，本文方法信号损失度比自适应旁瓣相消方法高约 $3 \mathrm { d B }$ 。当导航信号从旁瓣甚至远旁瓣进入接收机时，旁瓣出现零陷，因此信号损失度 $G _ { \mathrm { s } }$ 逐渐趋于0。

结合表1和图4(c)可得，随着辅助阵元口径增加(等价于干噪比的增加），时延补偿的本文方法和自适应旁瓣相消方法干扰抑制度 $G _ { \mathrm { r } }$ 均不断提高，由于口径的增大使得干扰信号接收功率增大。时延补偿的自适应旁瓣相消方法在辅助阵元口径大于 $1 . 4 \mathrm { ~ m ~ }$ 时，干扰抑制度超过时延未补偿的本文方法，但其干扰抑制度比时延补偿的本文方法的 $G _ { \mathrm { r } }$ 低 ${ \boldsymbol { 7 } } \sim 1 0 ~ \mathrm { d B }$ 。随着阵元口径的增加，本文方法与自适应旁瓣相消方法的信号损失度相差 $2 ~ \mathrm { d B }$ 内，如图4(d)。

# 3.2.3 观测时间和阵元数量的影响

观测时间是指参与估计 $\hat { R } _ { x }$ 、 $\hat { R } _ { x y }$ 运算的快拍数量(即接收信号数据长度) $N$ 所对应的时间，不同的观测时间影响相关矩阵的估计精度，而阵元数量影响合成方向图在干扰来向零点的零陷程度和可消除干扰个数，因此本文讨论了不同观测时间和阵元数量对方法性能的影响，如图5。

结合表1和图5(a)可得，随着观测时间的增加，时延补偿的本文方法干扰抑制性能不断提高，干扰抑制度比自适应旁瓣相消方法高 $1 0 \sim 1 8 ~ \mathrm { d B }$ ，且比时延未补偿的本文方法干扰抑制度高 $1 0 \sim 1 2 ~ \mathrm { d B }$ 。相比自适应旁瓣相消方法，时延补偿的本文方法的信号损失度 $G _ { \mathrm { s } }$ 高约1dB，如图5(b）。

![](images/d7d47f54ecd2589fc2498c0f4bbb38acfcc07f4e24151c889eddf708cb13383b.jpg)  
图5不同观测时间和阵元数量的方法性能对比

Fig.5Performance comparison between diferent observation time and between diferent numbers ofauxiliary atenna

结合表1和图5(c)可知，随着阵元数的增加，两种抗干扰方法的干扰抑制度都会随之增加，但时延补偿的本文方法比自适应旁瓣相消方法干扰抑制度 $G _ { \mathrm { { I } } }$ 高约 $1 4 ~ \mathrm { d B }$ ，且比时延未补偿的本方法干扰抑制度高约 $4 ~ \mathrm { d B }$ 。此外，无论时延是否补偿，本文方法的信号损失度 $G _ { \mathrm { s } }$ 整体比自适应旁瓣相消方法高约1dB，如图5(d）。

# 4结论

本文针对导航信号干扰L波段射电观测这一实际情况，构建了基于辅助阵列的抗干扰系统框架，并从射电数据应用出发，提出了干扰抑制度和信号损失度两个指标。利用导航信号良好的空间特性和相关特性，改进了传统的基于特征子空间的自适应旁瓣相消方法，使其在干扰功率小于噪声功率时依然可有效地消除干扰。此外，本文考虑到由于射电天线与辅助阵列空间相对位置造成的时延导致导航信号相关性降低问题。利用基于非迭代的加权最小二乘的可变分数时延全通滤波器实现了时延的精确补偿，提高了导航信号的相关性。最后基于所提指标，通过蒙特卡洛仿真方式，对比了本文方法与自适应旁瓣相消方法，结果表明本文方法的干扰抑制度提高了 $1 0 \sim 2 0 ~ \mathrm { d B }$ ，但信号损失度增加约1dB。

# 参考文献：

[1] Hellbourg G,Trainini T，Weber R,et al.RFI subspace estimation techniques for new generationradio telescopes ［C]// Signal Processing Conference（EUSIPCO），2O12 Proceedings of the20th European.2012：200-204.  
[2] Sardarabadi A M,van der Veen A J. Subspace estimation using factor analysis [C]// SensorArray and Multichannel Signal Processing Workshop（SAM），2O12 IEEE $7 ^ { \mathrm { t h } }$ . 2012:477-480.  
[3] Helbourg G,Chippendale A P,Kesteven M J,et al. Reference antenna-based subspace trackingfor RFI mitigation in radio astronomy ［C］// 2O14 IEEE Global Conference on Signal andInformation Processing（GlobalSIP）.2014：1286-1290.  
[4] Jeffs B D,Li L，Warnick K F.Auxiliary antenna-assisted interference mitigation for radioastronomy arrays [J]. IEEE Transactions on Signal Processing，2005，53(2）:439-451.  
[5] 赵永波，王志慧，张守宏.一种基于特征空间的自适应天线旁瓣相消算法［J].航空计算技术，2004，34(1):5-8.Zhao Yongbo，Wang Zhihui， Zhang Shouhong.An eigenspace-based algorithm for adaptiveantenna sidelobe cancellation [J]. Aeronautical Computer Technique，2OO4，34(1）:5-8.  
[6] 秦顺友，李光，张立军，等.65米射电望远镜天线测量技术［C］/／中国电子科技集团公司第五十四研究所.2013年全国天线年会.2013：1-61.  
[7] 张洪波，毛佩锋，汪敏，等. $4 0 \mathrm { m }$ 口径射电望远镜［J］.天文研究与技术—国家天文台台刊，2008，5(2)：187-191.Zhang Hongbo，Mao Peifeng，Wang Min，et al.The $4 0 \mathrm { m }$ radio telescope ［J]．AstronomicalResearch & Technology———Publications of National Astronomical Observatories of China,2008,5(2) : 187-191.  
[8] Deng Tianbo. Noniterative WLS design of alpass variable fractional-delay digital filters[J].IEEE Transactions on Circuits and Systems I:Regular Papers，2006,53(2）: 358-371.  
[9] Farrow C W.A continuously variable digital delay element [J]. IEEE International Symposiumon Circuits and Systems，1988，3：2641-2645.

［10］高健健，曹洋，甘恒谦，等.FAST $3 0 \mathrm { ~ m ~ }$ 模型L-波段馈源的设计、制作和性能测试［J]．天文研究与技术—国家天文台台刊，2007，4(1)：48-52.Gao Jianjian，Cao Yang，Gan Henqian，et al. Design、manufacture and test of the L-band feedfor the FAST $3 0 \mathrm { m }$ demonstrator ［J].Astronomical Research & Technology—Publications ofNational Astronomical Observatories of China，2007，4(1）:48-52.

# Mitigation of the Radio Frequency Interference Using an Adaptive Side-Lobe Cancellation Based on Accurate Delay Compensation

Huang Da $^ { 1 }$ ，Wang Zhuang'，Cheng Zhu²，Dong Liang³，Su Yao4

(1.ATRKeyLabSchoolofElectronicSienceandEngineering，NationalUniversityofDefenseTechnologyChangsha40,in;   
2.ResearchInsitutiofElectrocEngineing，SholofElectroicSienceandEngneing，NatioalUniversitofefensToly Changsha 410073,China；3.Yunnan Observatories，Chinese Academy of Sciences，Kunming 650011,China；   
4.School of Electronic Engineering Xidian University，Xi'an 71Oo71,China)

Abstract：When navigation signals，as radio interferences，affect observation in L-band， they are diferent from other types of interferences in communication field or radar.Using the correlation interference, traditional methods are ineffective and they lack effctive evaluation indexes，too，because the power of navigation signal is normally weaker than noise power.To solve the above problems，this paper constructs a system framework of radio astronomy interference based on radio signal processng，and raises two indexes : interference suppressionand signal loss based on the application of the observation data.After accurate delay compensation，this paper proposes a method to eliminate the effects of the navigation signals，using the adaptive side-lobe cancelltion that suppresses the noise component of interference subspace.From the results of the simulation，conclusion can be drawn that the proposed method can efectively suppress the navigation signal inthe observations，and the performance is beter than thatof traditional adaptive side-lobe cancelation based in feature subspace.

Key words:：Radio astronomy interference；Adaptive side-lobe cancelltion；Navigation signal；Variable fractional delay filter