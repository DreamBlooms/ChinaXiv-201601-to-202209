# CN 53-1189/P ISSN 1672-7673

# 一种新的数据融合方法—广义融合法

魏彦飞1²，耿建平}，施浒立2,，李景景4，李林²，徐希坤'(1.桂林电子科技大学电子工程与自动化学院，广西 桂林541004；2.中国科学院国家天文台，北京 100012;3.北京日月九天科技有限公司，北京100012；4.中原工学院电子信息学院，河南 郑州450007)

摘要：数据融合的目的是合并或者综合多个数据集，成为一个完整的性能更好的数据集。基于广义延拓插值外推法提出建立两组或两组以上方程解集和数据序列融合优化的数学模型，称之为广义融合法，此方法能充分发挥数据和量测资源的潜力，运用创新的集成和互校算法，解决数据融合面临的难题。介绍了广义融合数学模型的建立和求解方法的主要步骤；对模型中权值的分配原则做了分析；最后应用于卫星导航数据处理领域。实验证明该方法实用性好，数据平稳性好，外推稳定度高，有望成为一种新的解决数据融合问题的普适求解方法。

关键词：数据融合；广义融合；广义延拓外推；模型求解；权值分配；卫星导航数据处理中图分类号：TN96 文献标识码：A 文章编号：1672-7673(2016)03-0318-08

数据融合(也叫信息融合)的概念始于20世纪70年代，至80 年代其技术取得了一定的进步和发展，到90年代不少数据融合技术的研究成果已得到实际应用，取得了理想的效果[1]。数据融合的主要原理是用多个传感器(同质或异质的)对同一对象进行描述，得到该对象的多源观测数据，将这些数据进行集成，以获得对被控对象的更好的理解[2]。

多传感器信息融合技术是近几年发展起来的一门实践应用技术，是针对一个系统使用多种传感器这一特定问题而展开的一种关于数据处理的技术[3]。对于多传感器系统，由于信息的多样化和复杂性，因此，信息融合方法的基本要求是具有强大的处理能力，以及较高的计算速度和精度。人工智能的发展使信息融合技术走向智能化、集成化。

数据融合的目的是合并或合成多个数据集，成为一个完整的性能更好的数据集。数据融合技术的实现，关键在于融合算法[4-5]。在融合求解过程中，不是仅仅把数据或解集简单地直接组合，这样做效果不会很明显，甚至最后得到的结果更差。为了能够得到良好的融合效果，应该分析各组方程解或多组数据集序列的特征。比如一些数据序列的随机误差较小但偏差较大；一些数据的随机误差较大但偏差较小[6-7]。这样就可以将随机误差较小的数据序列的相对变化量通过一定的方法融合到随机误差较大的数据序列中，能获得随机误差较小且偏差也较小的数据序列。本文基于广义延拓插值外推法8提出了一种求解一类特定的关联群方程组的多个离散数据集或最优融合估计集的方法，称之为广义融合方法。经过实验证明，该方法实用性好，数据平稳性好，外推稳定度高，已应用于卫星导航定位数据处理领域。

# 1广义延拓插值外推法

广义融合是基于广义延拓插值外推法提出的，因此，先介绍广义延拓插值外推法。广义延拓插值外推法的基本设计理念是[9]：分段实施最小二乘逼近，在每段的端点处采用插值处理，在段内采用

拟合处理，段内拟合逼近处理时，用邻近延拓域里的数据进行辅助拟合处理，从而使逼近多项式在定义域内的逼近精度升高；当分段连接后，在连接端点处过渡平滑，在整域上逼近精度比较好。广义延拓最小二乘逼近方法的外推模型兼融了插值和拟合两大功能，具有极好的逼近精度。外推示意图见图1。

假设已知历元 $t _ { n }$ 时刻的最优估计值 $\hat { x } _ { n }$ 和 $t _ { n }$ 之前的数据值( $\hat { \mathbf { \Omega } } _ { x _ { 1 } } ^ { \prime }$ ， $\hat { x } _ { 2 } , \ \cdot \cdot$ ， $\hat { x } _ { n - 1 } \mathrm { ~ , ~ }$ ），求下一时刻$t _ { n + 1 }$ 的值 $\boldsymbol { x } _ { n + 1 }$ ，这是一个典型的数据外推问题,可建立如下广义延拓插值外推模型[1]：

![](images/7a94d5abffaf06e269b699bdc8d7ccbd63e14b226e422414d82326dabe6b31ce.jpg)  
图1广义延拓外推示意图Fig.1Generalized extrapolation diagram

$$
\left\{ { \begin{array} { l } { \operatorname* { m i n } [ a _ { 1 } , \ a _ { 2 } , \ a _ { 3 } ) = \displaystyle \sum _ { i = m } ^ { n - 1 } \left[ a _ { 1 } + a _ { 2 } t _ { i } + a _ { 3 } t _ { i } ^ { 2 } - x _ { i } \right] ^ { 2 } } \\ { s . t . \quad a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 } = x _ { n } } \end{array} } , \right.
$$

其中， $\operatorname* { m i n } I ( a _ { 1 } , \textit { a } _ { 2 } , \textit { a } _ { 3 } )$ 为逼近残差极小化目标函数； $a _ { 1 } , \ a _ { 2 } , \ a _ { 3 }$ 为待求的系数；s.t.示意约束条件。求解模型(1），可以优化获得广义延拓逼近多项式的待求系数 $a _ { 1 } \mathrm { ~ , ~ } a _ { 2 } \mathrm { ~ , ~ } a _ { 3 }$ ；代入(2)式：

$$
x \dag ( t _ { j } ) = a _ { 1 } + a _ { 2 } t _ { i } + a _ { 3 } t _ { i } ^ { 2 } \dag ( i = n + 1 , \ n + 2 , \ \cdots ) ,
$$

便可以外推求解得到tn+历元的估计值xn+10

# 2广义融合方法的数学模型及其求解方法

# 2.1广义融合方法数学模型的建立

广义融合求解模型借鉴了广义延拓插值外推公式，即在 $t _ { n }$ 历元时，选用多项式 $a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 }$ 作为逼近函数。逼近时选用一段历元内的数据，其中把已获得的先验最优估计值（起始时由于没有先验最优估计值，可以先用测量值代替)作拟合逼近处理；选用当前待求历元的广义状态量的预估值与测量值的最优加权组合逼近形式作为插值约束锁定点；以逼近多项式系数 $a _ { 1 } \mathrm { ~ , ~ } a _ { 2 } \mathrm { ~ , ~ } a _ { 3 }$ 和权系数 $k _ { 1 }$ 、 $k _ { 2 }$ 等为优化求解变量；以逼近函数多项式系数 $a _ { 1 }$ $\smash { \imath _ { 1 3 } \ , \ q _ { 2 3 } \ , \ a _ { 3 } }$ ，权系数 $k _ { 1 }$ 、 $k _ { 2 }$ 以及广义状态量等待求量的区间数作为变量取值约束条件。这些约束条件把解限制在一定的范围之内，从而提高解的精度。

构造广义融合最优化求解模型，求 $\mathbf { a } _ { 1 } , ~ \mathbf { a } _ { 2 } , ~ \mathbf { a } _ { 3 }$ ，使满足：

$$
\left\{ \begin{array} { l l l } { \displaystyle \operatorname* { m i n } I _ { 1 } ( a _ { 1 } , ~ a _ { 2 } , ~ a _ { 3 } ) = \sum _ { i = n - m } ^ { n - 2 } \big [ a _ { 1 } + a _ { 2 } t _ { i } + a _ { 3 } t _ { i } ^ { 2 } - \hat { x } _ { i } \big ] ^ { 2 } } \\ { \qquad \quad + \ : k _ { 1 } \big [ a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 } - \widetilde { x } _ { n } \big ] ^ { 2 } + k _ { 2 } \big [ a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 } - x _ { n } \big ] ^ { 2 } , } \\ { \qquad \quad \ : \ : a _ { 1 } + a _ { 2 } t _ { n - 1 } + a _ { 3 } t _ { n - 1 } ^ { 2 } = \hat { x } _ { n - 1 } ; ~ k _ { 1 } + k _ { 2 } = 1 } \\ { \displaystyle a _ { 1 } \subseteq \hat { a } _ { 1 } , ~ a _ { 2 } \subseteq \hat { a } _ { 2 } , ~ a _ { 3 } \subseteq \hat { a } _ { 3 } } \end{array} \right.
$$

其中， $I _ { 1 } ( a _ { 1 } , a _ { 2 } , a _ { 3 } )$ 为待优化的目标函数，优化的目标函数既可以是线性关系也可以是非线性关系，若是非线性关系，则广义融合方法直接采用非线性求解算法求解； $x _ { i }$ 为状态量的测量值； $\hat { \boldsymbol { x } } _ { i }$ 为状态量的最优估计值； $\stackrel { \sim } { x } _ { i }$ 为由低阶状态量递推获得的状态量的预估值； $i$ 为历元序号； $k _ { 1 } , \ k _ { 2 }$ 为权系数，它们的取值大小影响它们各自的残差对目标函数的贡献，权值的分配在本文后面作详细的介绍； $\textstyle { \mathrm { ~ \mathcal { X } } } _ { n }$ 为 $t _ { n }$ 历元时状态量的测量值； $\widetilde { \boldsymbol { x } } _ { n }$ 为 $t _ { n }$ 历元时状态量的递推预估值； $\hat { x } _ { n - 1 }$ 为 $t _ { n - 1 }$ 历元时状态量的最优估计值； $\widehat { \mathbf { a } } _ { 1 } , \widehat { \mathbf { a } } _ { 2 }$ 、 $\widehat { \mathbf { a } } _ { 3 }$ 为可行区间变量 $a _ { 1 } \mathrm { ~ , ~ } a _ { 2 } \mathrm { ~ , ~ } a _ { 3 }$ 的约束区间数， $\widehat { a } _ { 1 } = \left[ \underline { { a } } _ { 1 } \mathrm { ~ , ~ } \overline { { a } } _ { 1 } \right]$ ，$\widehat { a } _ { 2 } = \left[ \underline { { a } } _ { 2 } \ 、 \overline { { a } } _ { 2 } \right]$ ， $\widehat { a } _ { 3 } = \left[ \underline { { a } } _ { 3 } \mathrm { ~ , ~ } \overline { { a } } _ { 3 } \right]$ 。广义融合模型中可以包含非线性状态方程、非线性约束方程以及其它非线性测量方程，这能够扩大应用范围，增加方程的冗余性和连续性，提高求解精度。

# 2.2广义融合方法的求解步骤

# 2.2.1 求解状态量值

建立残差极小化优化模型并加约束方程，如下式：

$$
\begin{array}{c} \operatorname* { m i n } _ { \mathbf { \theta } } I ( x _ { n } ) = \sum _ { i \mathbf { \theta } _ { 1 } } ^ { n } { \left( F ( x _ { i } ) \ - \ : Y _ { i } \right) ^ { 2 } }  \end{array}
$$

$$
\begin{array} { r l } { . . . } & { { } f ( x _ { n } ) = 0 } \end{array}
$$

其中， $F ( x _ { i } )$ 为状态量关系式，多数情况下为非线性函数关系，可以采用非线性算法直接求解； $x _ { i }$ 为函数状态变量； $Y _ { _ i }$ 为测量量； $i$ 为历元序号； $n$ 为当前历元数； $f ( x _ { n } )$ 为约束函数关系式。（4)式可以采用非线性算法求解，如单纯形法等。通过搜索、比较等步骤，使目标函数值不断逼近最优点。求解方法在优化过程中不受方程个数的限制，并且具有简单直观、适应性强、应用范围广、解决速度快等特点。

# 2.2.2求解状态量的预估值 $\stackrel { \sim } { x } _ { n }$

利用外推得到的状态方程的高阶状态量可以提高解的精度和相关性，低阶状态量可以是与状态量相关的导数值或微分值。当求解 $t _ { n }$ 历元时刻状态量的预估值 $\widetilde { \boldsymbol { x } } _ { n }$ 时，由于已经得到 $t _ { n - 1 }$ 历元时刻状态量的最优估计值 $\hat { x } _ { n - 1 }$ （在初始阶段的融合，初始状态最优估计值是未知的，可用前几个时刻状态的测量值代替），可以通过公式：

$$
\stackrel { \sim } { x } _ { n } = \hat { x } _ { n - 1 } + \dot { x } _ { n } \Delta t + { \frac { 1 } { 2 } } \ddot { x } _ { n } \Delta t ^ { 2 } + \cdots ,
$$

递推获得 $t _ { n }$ 历元时刻状态量的预估计值 $\stackrel { \sim } { x } _ { n }$ 。(5)式中 $\stackrel { \sim } { x } _ { n }$ 为 $t _ { n }$ 历元时刻状态量的预估值； $\hat { x } _ { n - 1 }$ 为 $t _ { n - 1 }$ 时刻状态量的最优估计值； $\dot { x } _ { n }$ 为 $t _ { n }$ 历元时刻状态量的一阶导数； $\Delta t$ 为相邻历元之间的时间间隔； $\ddot { x } _ { n }$ 为$t _ { n }$ 历元时刻状态量的二阶导数。

2.2.3求解状态量的最优估计值 $\hat { x } _ { n }$

经上述步骤，已经求得状态量值和状态量的预估值， $t _ { n }$ 历元时刻直接求解获得的状态量 $x _ { n }$ 和 $t _ { n }$ 历 元时刻获得的状态量的预估值 $\stackrel { \sim } { x } _ { n }$ ，现在需要把它们组合起来，求得 $t _ { n }$ 历元时刻状态量的最优估计值 $\hat { x } _ { n }$ ，即

$$
\hat { x } _ { n } = a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 } ,
$$

其中， $a _ { 1 } \mathrm { ~ , ~ } a _ { 2 } \mathrm { ~ , ~ } a _ { 3 }$ 可以由广义融合最优化求解模型(（3)式)采用直接法等优化算法求解得到。将得到的 $a _ { 1 } \mathrm { ~ , ~ } a _ { 2 } \mathrm { ~ , ~ } a _ { 3 }$ 代入(6)式可得到 $t _ { n }$ 历元时刻状态量的最优估计值 $\hat { x } _ { n }$ 。

2.2.4求解一组优化的最优估计值解

对上述4个步骤不断进行迭代、递推，直到结束，就能够得到一组优化的最优估计值解 $\hat { x } _ { i }$ ， $i = 1$ ，2, 3 . kend

# 3广义融合模型之中权值分析

在广义融合方法数学模型((3)式)中 $a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 } - x _ { n }$ 表示逼近函数与状态量之间的残差;$a _ { 1 } + a _ { 2 } t _ { n } + a _ { 3 } t _ { n } ^ { 2 } - { \overset { \sim } { x } } _ { n }$ 表示逼近函数与状态量的预估值之间的残差。它们的权系数 $k _ { 1 }$ 、 $k _ { 2 }$ 的取值大小会影响它们各自的残差对目标函数的贡献，所以权值的选择极为重要。故在确定权系数之前要分析状态量的预估值 $\widetilde { \boldsymbol { x } } _ { n }$ 、状态量的测量值 $\textstyle { \boldsymbol { x } } _ { n }$ 与逼近函数之间的残差大小比例关系；在融合数据时，要考虑被融合数据自身的精度及误差特性等诸多因素。通过改变 $k _ { 1 }$ 、 $k _ { 2 }$ 的大小可以调控广义融合最优估计值与状态量及预估值的靠近程度。

用仿真验证方法的可行性，即生成两组数据：一组数据随机误差较大但偏移较小（随机误差$- 3 - 3$ ，偏差为1)；另一组随机误差较小但有较大的偏移（随机误差-1-1，偏差为3）。数据生成后代入广义融合求解模型，选取不同的4对权值进行组合分析，所得结果如图2。

![](images/d6d3aec4854eed15638ee439f4c3e747a94f94c0b15d6a3d1aff3bff404e5f29.jpg)  
图2 (a) $k _ { 1 } = 1$ 、 $k _ { 2 } = 0$ 时最优估计值偏移；（b) $k _ { 1 } = 0 . 7$ 、 $k _ { 2 } = 0 . 3$ 时最优估计值偏移；（c) $k _ { 1 } = 0 . 3$ 、（204号 $k _ { 2 } = 0 . 7$ 时最优估计值偏移；（d) $k _ { 1 } = 0$ 、 $k _ { 2 } = 1$ 时最优估计值偏移Fig.2 (a) $k _ { 1 } = 1$ ， $k _ { 2 } = 0$ ，offset of optimal estimation；（b) $k _ { 1 } = 0 . 7$ ， $k _ { 2 } = 0 . 3$ ，offset of optimal estimation;(c） $k _ { 1 } = 0 . 3$ ， $k _ { 2 } = 0 . 7$ ，offset of optimal estimation；（d) $k _ { 1 } = 0$ ， $k _ { 2 } = 1$ ，offset of optimal estimation

从图2(a)、（b）、（c）、（d）4幅图可以看出：当 $k _ { 1 }$ 逐渐减小而 $k _ { 2 }$ 逐渐增大时，状态量的最优估计值开始远离状态测量值向预估值逼近；随着 $k _ { 1 }$ 越来越小， $k _ { 2 }$ 越来越大，这种现象更加明显。在数据处理过程中，如果有一组数据序列的某些测量量发生突跳导致数据不准确时，便可以通过改变权值组合来降低这些突跳数据对获取最优估计值的贡献，使获得的最优估计值更加平稳。

# 4广义融合方法在卫星导航中的应用及仿真与实测分析

4.1广义融合在卫星导航中的应用

以卫星定位导航为例说明采用广义融合方法的实用性：卫星导航定位解算出用户的位置坐标为x、y、 $z 3$ 个方向，本文只对一个方向的用户位置作详细分析，其余两个方向使用相同方法修正即可获得用户位置的完整坐标。

4.1.1获得 $t _ { m }$ 时刻位置最优估计值解 $\hat { x } _ { m }$ 和相应时刻的速度 $\hat { \nu } _ { { } _ { m } }$

将从初始时刻到 $t _ { { \scriptscriptstyle m } }$ 历元时刻接收机的位置量设为 $x _ { i } ( i = 1 , 2 , \cdots , m )$ 。通过对 $t _ { { \scriptscriptstyle m } }$ 历元时刻以前的位置测量量采用分段最小二乘拟合的方法(5个历元时刻点做一次拟合)对位置测量量进行处理，用处理后通过逼近多项式(6)获得的 $t _ { m }$ 时刻的值，作为 $t _ { m }$ 时刻位置的最优估计值解 $\hat { x } _ { m }$ [10]。由于在导航定

位中速度的测量值精确度较高，初始时刻的最优速度值及之后各时刻的最优速度值都直接选用对应时刻的速度测量值即可。

4. 1. 2 获取 $t _ { m + 1 }$ 时刻位置量的预估值 $\stackrel { \sim } { x } _ { m + 1 }$

由第1步已经得到了 $t _ { m }$ 时刻位置的最优估计值解 $\hat { x } _ { m }$ 和相应时刻速度的最优值 $\hat { \nu } _ { { } _ { m } }$ ，利用(5)式解算出 $t _ { m + 1 }$ 时刻位置量的预估值 $\stackrel { \sim } { x } _ { m + 1 }$ 。（5)式中 $\dot { x } _ { n }$ 为 $t _ { n }$ 历元时刻状态量的一阶导数即 $t _ { n }$ 时刻的速度值； $\ddot { x } _ { n }$ 为 $t _ { n }$ 历元时刻状态量的二阶导数即加速度值，加速度本文暂不考虑。

# 4.1.3 获得tm+1时刻最优估计值解xm+1

通过上述步骤，已经得到 $t _ { { \scriptscriptstyle m + 1 } }$ 时刻位置量的预估值，相应时刻位置量的测量值可以通过测量数据直接获得。因为实际的测量值会因为误差等因素导致最终结果不精确，所以本文在测量值与预估值之间添加一个阈值。当两者之间的绝对差值超过这个阈值时，便认为测量值已经发生了跳变，此时（3）式中的权值组合 $k _ { 1 } \approx 0$ 、 $k _ { 2 } \approx 1$ ，使最优估计值的解向预估值方向逼近；当两者之间绝对差值没有超过阈值时，认为测量数据在误差范围之内，就要选择合适的权值组合，再代入（3)式，组合求解获得最优估计值xm+10

# 4.1.4获得经优化的一组最优估计值解

上述第2、第3步不断迭代、递推、融合就能获得一组优化的最优估计值解xm+1，xm+2，…，xend 。4.2仿真

# 4.2.1广义融合对突跳数据的修正

卫星定位系统的精度主要取决于两方面：一是观测卫星在空间的分布情况，通常称为卫星分布几何衰减因子；二是各观测量的精度[11]。大气层干扰、对流层延迟改正后的残差、星历误差及多路径效应等影响导致最后的测量数据产生偏差或是突跳，而广义融合方法能够很好地修正这些误差数据。现生成一组随机误差在（-0.5-0.5)的数据，分别在第10、20、30、404个点处加上较大的偏移量构成突跳点，然后用广义融合方法对这组数据进行处理，仿真结果如图3。

由图3可以看出，广义融合法对4个突跳点的数据都做了实时修正，其结果不但在没有发生突跳的部分很好地遵循了原始测量值的变化规律，而在有突跳的时段，也能有效排除突跳的影响。

![](images/da21c02356c62d61af530ae6ab641462df0891e6dd23d2f097bbe55587a509e9.jpg)  
图3广义融合对突跳数据的修正 Fig.3Correction of the data of sudden jump with generalized fusion

# 4.2.2最小二乘拟合法与广义融合法对误差数据处理对比

在卫星数目多于4颗，各测量值之间相互独立且符合高斯正态分布的情况下，采用最小二乘算法解算接收机的三维坐标是最经典的办法。因为最小二乘算法能使各观测伪距之间的残差平方和最小，从而使获得的估计值解达到最优。但是多路径效应等因素产生的误差却时刻影响其定位精度，这导致各实际测量值之间并不是相互独立，甚至有些情况下不符合正态分布，这时若仍采用最小二乘算法就很难保证最后能获得最优估计值解[12]，而广义融合法在此种情况下依然适用。

下面通过仿真实验验证此方法的有效性。令测量值的理论值为50，这时在理论值的基础上加噪声生成一组带有随机误差的数据，作为测量仿真计算数据，为了便于体现广义融合法的优越性，分别用广义融合法和最小二乘算法对这组数据进行处理，修正后的效果如图4。

经计算，得到最小二乘拟合值的标准差为 $\sigma = 3 . 6 2 6 3 9 6 3 4 9 0 0 3 9 6 6$ ，广义融合最优估计值的标准差为 $\sigma = 0 . 7 5 8 0 6 8 1 9 3 0 4 5 7 5 6$ ，广义融合法稳定程度要比最小二乘拟合法提高大约 $7 9 \%$ （图4)；而且广义融合法的偏差也较小，误差数据的修正值更加靠近理论值。

# 4.2.3 实测数据分析

(1)2015年5月11日在中国科学院国家天文台用中科微ATGM332D卫星定位芯片的接收机做动态测试。从最终获取的接收机三维坐标中截取 $Y$ 方向上一段带有明显突跳的原始定位数据和对应时刻的原始速度值，分别用广义融合法和最小二乘拟合法对其进行处理，结果如图5。

![](images/f026348cc42e899888a456a88be2fa6fd6645d1470eb8edf3837d6ef92d3d6e4.jpg)  
图4最小二乘拟合法与广义融合法对误差数据处理的对比  
图6（a）氢钟、铯钟时频数据对比；（b）广义融合前后时频数据对比 Fig.6（a）Frequency data of hydrogen and cesium clock；（b）Comparison of time frequency before and after the generalized fusion

![](images/7e183fcc8c61cdce02e57183ef8044c3d73c555250bac3cc6172cb8276e28b81.jpg)  
图5广义融合法和最小二乘拟合法对实测数据处理的对比  
Fig.4Comparison of error data processed by the least squares fitting method and the generalized fusion method   
Fig.5Comparison of measured data processed by both the generalized fusion method and the least square fitting method

由图5可以看出最小二乘拟合法对某些突跳点并没有很好的修复作用，只是在少数点处遵循了原始数据的变化规律，但是整体数据偏离了实测数据；而广义融合法能实时修正原始数据中的坏数据，并且在没有发生突跳的部分很好地跟随原始数据的运动轨迹。

(2)当代社会对时频基准的要求越来越高，氢原子钟、铯原子钟等多种高精度时频基准已被相继研发出来。然而还可以通过另外一种方法获得更高精度和稳定度的时频基准，那就是组合处理和精细加工原子钟组的输出数据，获得性能更优良的时频输出数据。本文把氢原子钟与铯原子钟的输出数据用广义融合法融合起来。图6(a)显示了铯原子钟与氢原子钟输出的频率数据变化图，通过对比可以发现铯原子钟频率的随机误差偏大，但长期稳定度很好；而氢原子钟则不同，它随机误差的幅度很小，

X10-13 ×10-148氢钟时频数据  
0.8 铯钟时频数据 6  
0.64 wwmn  
0.4  
0.2 20 O  
-0.2 -2  
-0.4-4  
-0.6M  
-0.8 -6 铯钟时频数据广义融合后时频数据-1 -80 200 400 600 800 1000 1200 1400 1600 1800 0 200 400 600 800 1000 1200 1400 1600 180(a) (b)

但是随着时间的增长其频率出现很明显的漂移。广义融合法能把这两种原子钟的频率特性的优势组合起来，从而获得随机误差小并且长期稳定度好的时频基准。用这一方法对国家授时中心的铯原子钟和氢原子钟输出的时频数据进行融合处理，用氢钟时频的变化率修正铯钟的时频输出，处理结果见图6(b）。

# 5结论

本文针对卫星导航定位数据中出现的坏数据，尤其是突跳数据的修正，在广义延拓插值外推法的基础上提出了一种新的数据融合方法——广义融合法。通过仿真和实测数据分析，与最小二乘算法进行对比后得出：广义融合法较最小二乘拟合法更能够修复定位数据中产生的突跳数据；广义融合法比最小二乘拟合法对数据的处理可靠性更高；广义融合法实用性好，数据平稳性好，外推稳定度高，有望成为一种新的解决数据融合问题的普适求解方法。

# 参考文献：

[1] 王栋.基于数据融合的机载多传感器目标识别［D]．上海：上海交通大学，2010.  
[2] 王炯琦，周海银，吴翊.基于最优估计的数据融合理论［J].应用数学，2007，20(2)：392-399.Wang Jiongqi，Zhou Haiyin，Wu Yi. The theory of data fusion based on state optimal estimation[J].Mathematica Applicata，2007，20(2）:392-399.  
[3] 石忠，霍星．多传感器信息融合技术在INS/GPS 组合导航系统中的应用［J].渤海大学学报：自然科学版，2008，29(4)：403-407.Shi Zhong，Huo Xing.Application of multi-sensor information fusion technique in INS/GPSintegrated navigation system [J]. Journal of Bohai University：Natural Science Edition,2O08,29(4):403-407.  
[4] Shang Lin，Liu Guohua，Zhang Rui，et al.An information fusion algorithm for integratedautonomous orbit determination of navigation satelites [J].Acta Astronautica，2O13，85：33-40.  
[5] Ning Xiaolin，Fang Jiancheng.An autonomous celestial navigation method for LEO satellite basedon unscented Kalman filter and information fusion [J]. Aerospace Science and Technology,2007，11(2-3):222-228.  
[6] Tzschichholz T，Boge T，Schilling K.Relative pose estimation of satellites using PMD-/CCD-sensor data fusion ［J].Acta Astronautica，2015，109：25-33.  
[7] Wang Xinlong，Zhang Qing，Li Hengnian.An autonomous navigation scheme based on starlight,geomagnetic and gyros with information fusion for small satelltes [J].Acta Astronautica，2014,94(2) : 708-717.  
[8] 施浒立，颜毅华，徐国华．工程科学中的广义延拓逼近法［M]．北京：科学出版社，2005.  
[9] 耿建平，衣伟，刘成，等.基于广义延拓外推的单频周跳检测与修复方法［J］．天文研究与技术，2015，12(2)：174-182.Geng Jianping，Yi Wei，Liu Cheng，et al.A new method for detection and correction of single-frequency cycle slipsusing data extrapolationbased on the method of generalized extendedinterpolation ［J].Astronomical Research & Technology，2015，12(2）:174-182.  
［10]施浒立，黄康，衣伟，等.一种新的逼近滤波方法：中国，201410208791.7［P].2014-08-  
[11］何瑞珠，刘成，黄康.卫星定位中的一种分步加权解算方法［J]．天文研究与技术，2015,12(1):36-43.He Ruizhu，Liu Cheng，Huang Kang. A method of multiple-step Weighted Least-Square estimatefor satellite positioning［J].Astronomical Research & Technology，2015，12(1）：36-43.  
［12］朱丽梅，张绪春.高动态卫星接收机定位高程超差问题分析［J].海军航空工程学院学报，2010，25(2):203-207.Zhu Limei, Zhang Xuchun.Analysis of the positioning error on elevation during the high dynamicenvenoming [J]. Journal of Naval Aeronautical and Astronautical University，2O1O,25(2）: 203-207.

# A New Method of Data Fusion一 -the Generalized Fusion Method

Wei Yanfei $^ { 1 , 2 }$ ，Geng Jianping’，Shi Huli $^ { 2 , 3 }$ ,Li Jingjing4， Li Lin $^ 2$ ,Xu Xikun1 (1.Electronic Engineering and Automation Colege，Guilin Universityof Electronic Technology，Guilin 541004,China； 2.National Astronomical Observatories，Chinese AcademyofSciences，Beijing 012,China,Email；729680894@q.com; 3.Beijing Ri Yue Jiu Tian Technology Co.,Ltd,Beijing 100012,China；4.Electronic Information College, Zhongyuan University of Technology，Zhengzhou 45ooo7,China)

Abstract:The purpose of data fusion is to merge or synthesize two data sets so as to make them become a better and complete data set.Based on extended inter-polation method，generalized fusion method is a method which strives to create a mathematical model that consists of two or more sets of equation and data sets. This method is notonlyable to bring out its full potential of dataand measurement resources，butalso capable of using innovative integration and mutual algorithm to solvethe data fasion problem.After simulation and real measurement data analysis，conclusion can be drawn that compared with the least square algorithm，the generalized fusion method is more suitable for the repair of the data generated in the process of data fusion. This paper also introduces the main steps of the establishment and the solution of the generalized mathematical model,analyzes thedistribution principleof weight in the model and itsapplication in the fieldof satelite navigation data processing.Experimental resultsshow that the method is practical and stable，and it is expected to be a new method for solving the problem of data fusion.

Key words:Data fusion；Generalized fusion；Generalized extrapolation；Model solving；Weight distribution; Satellite navigation data processing