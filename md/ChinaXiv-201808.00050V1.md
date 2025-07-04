# 基于ORB-SLAM2的实时网格地图构建

陆建伟，王耀力

(太原理工大学 信息与计算机学院，太原 030024)

摘要：针对目前视觉 SLAM系统只能输出相机的运动轨迹图，而不能生成用于路径规划和导航的地图的缺点，提出了一种基于ORB-SLAM2的网格地图实时构建算法。首先,建立了一个适用于视觉SLAM的逆传感器模型(inverse sensormodel，ISM)；其次，针对 ISM模型，重新编排了网格地图算法的构建机制，并对其进行详细的推导；最后，介绍了ORB-SLAM2网格地图构建的具体实施方案。通过实验，对ISM模型和网格地图模型进行分析，确保了算法的可行性；用单目相机和RGB-D 深度相机进行实时实验，实现了网格地图的实时构建，且能够清晰地显现出障碍物位置，验证了所提算法的有效性。

关键词：ORB-SLAM2；逆传感器模型；网格地图；RGB-D相机 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.05.0338

# Real-time occupancy grid mapping using ORB-SLAM2

Lu Jianwei,Wang Yaoli† (College of Information & Computer Science,Taiyuan University ofTechnology,Taiyuan O30024,China)

Abstract: Curentlythe visual SLAMsystemcanonlyoutputthecamera's motion trajectory,but itcannot generate maps for path planningand navigation.In order to solve this problem,this paper proposes areal-time grid map algorithmbased on ORB-SLAM2.Firstly，the paper establishes an inverse sensor model (ISM） for visual SLAM.Secondly，the paper rearranges theconstructionmechanismof the gridmapalgorithmforISMmodeland thenderives itindetail.Finaly,tepaper introduces the specific implementation scheme of ORB-SLAM2 grid map construction.Through experiments,the algorithm shows itsfeasibilty basedontheanalysisoftheISMmodeland the grid map model.Furthermore,thereal-time experiments using monocularcamera and RGB-D camera can realize thereal-timeconstruction of the grid mapand clearly show the positions of obstacles,which verifies the effectiveness of the algorithm.

Key words: ORB-SLAM2; inverse sensor model; grid map; RGB-D camera

# 0 引言

同时定位与地图构建（simultaneouslocalization andmapping，SLAM)）是机器人和自动导航中一个十分重要的领域。它是在没有环境先验信息的情况下，通过自身的传感器，在运动过程中建立环境模型，同时估计自身运动。在智能领域中，从简单的扫地机器人，到复杂的自驾汽车，SLAM都是一个必不可少的组件。无论是自主四旋翼无人机探索恶劣环境，还是自动驾驶汽车，自动导航和建图已成为诸多应用的基础支撑。所以，一个高效的机器人导航和地图构建是科研人员一直追求的目标。尤其是最近几年，这已成为一个快速发展的领域，并取得了许多重大的进展。目前，虽然有用LiDAR作为3D 传感器的SLAM系统I，而且在室内环境应用已不具任何挑战，但是这种高成本传感器限制了其不能够在低成本系统中应用。

因此，在SLAM领域分化出了一个新的区域一一V-SLAM。在V-SLAM 中，比较流行的系统有MSCKF[2]、ROVIO[3-4]、OKVIS[5]、ORB-SLAM2[6-7]、VINS-mono[8]等，但是这些SLAM系统并没有在真正意义上实现建图功能，只是简单地输出一个相机运动轨迹图，而在实践中，相机的运动轨迹图并不能够用于机器人导航和避障。

Santana等人[9]在2011年介绍了一种基于单目相机使用平面信息（单应矩阵）构建2D地图的方法，该方法在分割步骤通过判断图像特征点是否在同一平面来快速判断是否有障碍物，但是由于单目视觉没有尺度信息，所以建立的2D网格地图并不适用于现实中机器人的定位和导航。Dia等人[o]介绍了一种新型的用于占有网格地图的逆传感器模型，然而并没有SLAM方面的应用。Hull[介绍了一种基于LSD-SLAM的实时占有网格建图，与文献[9]类似，实现的单目SLAM的构建占用网格地图算法，它是通过把点云图投影的方式实现了网格地图的构建。Gregorio等人[I2]介绍了一个高效的机器人导航建图框架，是一种3D的占用网格地图构建算法，但是其计算量太大，对于以SLAM为底层支撑的机器人系统来说，并不希望其占用太多的资源。

ORB-SLAM2是一个比较流行的V-SLAM系统，该系统能够创建相对简单的3D点云图，但是这个点云地图并不能够用于机器人的路径规划和导航。因此，针对ORB-SLAM2存在不能够生成用于导航和路径规划的地图的缺点，利用关键帧、地图点以及姿态 $\textbf { \em x }$ 生成可用于机器人路径规划和导航的2D占用网格地图。

# 1 建立逆传感器模型

移动机器人处在未知环境中，通过自身的传感器建立考虑噪声和不确定因素的概率分布模型来估计外部环境，这个模型称做传感器模型（sensormodel，SM）。在观测到外部环境信息数据后，通过这些数据建立外部环境地图的模型称做逆传感器模型（inverse sensor model，ISM）。

在建立ISM模型前，需要做适当的马尔可夫（Markov）假设。

假设1：地图网格间相互独立；

假设2：传感器观测数据时引入的噪声为高斯噪声。

Markov假设对于ISM模型是合理的，因为不存在因果关系的占用状态不同的单元格，并且从工程的较大来看也合理的，由此产生的模型是足够完成用于应用中所需要的任务范围；同时，零阶Markov假设的计算简单，而且允许发展为灵活的感知系统。

ISM模型的目的是用传感器观测数据来表示占用网格地图单元格是否被占用的概率。从传感器的角度分析，网格单元征收与障碍物间的关系都可以用一个概率值来表示其是否被占用的二进制状态。在网格地图中， $m _ { i }$ 表示其相应网格单元是否被占用的随机变量，其中OCC表示占用，EMP表示空闲，且

$$
p ( m _ { i } = O C C ) + p ( m _ { i } = E M P ) = 1
$$

因此每个单元格的是否被占用的概率可以通过传感器观测数据估计得到。在构建一个机器人环境地图时，会涉及到两个处理阶段：a)利用随机传感器模型对传感器观测范围r进行解释，这个模型是有 $p ( r | z )$ 的概率分布函数定义的， $\textbf { z }$ 是被检测到的实际距离；b)用传感器观测数据更新网格单元的状态。

为了确定如何通过传感器观测数据来估计占用网格地图单元的状态，对于每个单一的网格单元 $m _ { i }$ 应用贝叶斯法则：

$$
\begin{array} { l } { p { \big ( } m _ { i } = O C C | r { \big ) } } \\ { \displaystyle = \frac { p { \big ( } r | m _ { i } = O C C { \big ) } p { \big ( } m _ { i } = O C C { \big ) } } { \sum _ { m _ { i } } p { \big ( } r | m _ { i } { \big ) } p { \big ( } m _ { i } { \big ) } } } \end{array}
$$

需要注意的是，式（2)中的 $p ( r | m _ { i } )$ 与传感器模型中的 $p ( r | z )$ （204号并不一致，因为后者隐含地将范围的读取与单个物体表面联系在一起，换而言之，传感器模型可重写为

$$
p ( r | z ) = p ( r | m _ { i } = O C C \land m _ { i } = E M P )
$$

考虑 $m _ { i }$ 存在的所有可能的状态，可得

$$
\begin{array} { l } { { \displaystyle p \big ( r \big | m _ { i } = O C C \big ) = } } \\ { { \displaystyle \sum _ { \big \{ M _ { m _ { i } } \big \} } \big ( p \big ( r \big | m _ { i } = O C C , M _ { m _ { i } } \big ) \times p \big ( M _ { m _ { i } } \big | m _ { i } = O C C \big ) \big ) } } \end{array}
$$

其中： $M _ { m _ { i } } = \left( m _ { 1 } , . . . m _ { i - 1 } \right)$ 表示 $m _ { i } = O C C$ 的所有网格单元， $\left\{ M _ { m _ { i } } \right\}$ 表示所有地图网格单元集合。同理可得

$$
\begin{array} { l } { { \displaystyle p \big ( r \big | m _ { i } = E M P \big ) = } } \\ { { \displaystyle \sum _ { \big \{ M _ { m _ { i } } \big \} } \big ( p \big ( r \big | m _ { i } = E M P , M _ { m _ { i } } \big ) \times p \big ( M _ { m _ { i } } \big | m _ { i } = E M P \big ) \big ) } } \end{array}
$$

式（4）（5）中 $p \big ( { M } _ { m _ { i } } \vert m _ { i } \big )$ 的概率有单元格的先验概率决定，选择用最大熵的先验，可能会出现两种状态概率相等的情况：

$$
p \big ( m _ { i } = O C C \big ) = p \big ( m _ { i } = E M P \big ) = \frac { 1 } { 2 }
$$

为了更好地陈述ISM模型，首先考虑理想传感器。假设其概率分布函数为 $p ( r | z ) = \delta ( r - z )$ ，这里 $\delta$ 是 Kronecker delta,此时,可得理想ISM模型函数 $g \left( r \right)$ 为方程(2)的封闭解，且 $g \left( r \right)$ 为

$$
g \left( r \right) = \left\{ \begin{array} { c } { { r < z - \displaystyle \frac { L } { 2 } } } \\ { { } } \\ { { 1 } } \\ { { 0 . 5 } } \\ { { } } \end{array} \right. \ z - \displaystyle \frac { L } { 2 } \leq r < z + \displaystyle \frac { L } { 2 }
$$

其中： $\mathrm { ~ \bf ~ r ~ }$ 表示传感器观测范围；L为传感器观测的缓冲区域宽度，且L大小为网格单元两个角之间的对角线距离。在$r < z - \frac { L } { 2 }$ 区间g(r)=0表示没有障碍物，z- ≤r<z+区间$g \left( r \right) = 1$ 表示有障碍，else $r > 0$ 区间 $g \left( r \right) = 0 . 5$ 表示传感器不能够观测区域，即未知区域。注意，一个单元的中心用于计算传感器的距离，这个距离用于评估传感器模型的更新值。然而z的峰值可能完全错过了，如果单元格的中心有一个从z轻微的偏移量。虽然可以从单元格边界用积分找到的平均价值，但因为处理许多单元格和许多测量光束这种方法计算过于昂贵。所以，引入了一个参数L，它表示一个r值的频带，它接收到与肯定占据的概率相对应的概率。在理想 ISM 模型函数 $g ( r )$ 中并没有把概率值1指定为r上，而是在r附近的一组宽度L上，这是为了确保障碍物落下的单元接收到的值为1。

实践中的ISM模型是由理想条件下的逆传感器模型和高斯噪声进行卷积得到的。通过理想逆传感器模型 $g \left( r \right)$ 与高斯噪声模型 $f ( r )$ 卷积能够得到实践中的ISM 模型：

$$
f \left( r \right) = \frac { 1 } { \sigma \sqrt { 2 \pi } } e ^ { \frac { - \left( r - 0 \right) ^ { 2 } } { 2 \sigma ^ { 2 } } }
$$

$$
{ \bigl ( } f * g { \bigr ) } ( r ) \int _ { - \infty } ^ { \infty } g ( \tau ) f ( r - \tau ) d \tau
$$

从 $g \left( r \right)$ 的表达式能够看出，其为分段函数， $g \left( r \right)$ 与 $f ( r )$ （204号进行卷积时，可以进行分段卷积，重写卷积方程为

$$
( f * g ) ( r ) = k F ( a , b )
$$

这里 $( a , b )$ 为观测值 $\textbf { z }$ 和范围 $\mathrm { ~ \bf ~ r ~ }$ 上的间隔； $k \in \left\{ 0 , 0 . 5 , 1 \right\}$ 是$p ( m )$ 的取值，其与网格单元状态变量的概率是一致的。可以得到

$$
F ( a , b ) = { \frac { 1 } { \sigma { \sqrt { 2 \pi } } } } \int _ { a } ^ { b } e ^ { \frac { - ( r - \tau ) ^ { 2 } } { 2 \sigma ^ { 2 } } } d \tau
$$

![](images/5e768e2dcb4dc28e320e83ee254e4af3c699429d4ee43e5332c73d4de5c1c30f.jpg)  
图1ISM模型建立过程

式（9）中，令 $u = \frac { r - \tau } { \sigma \sqrt { 2 } }$ r-τ，可以重写为

$$
F ( a , b ) = { \frac { - 1 } { \sqrt { \pi } } } \int _ { \frac { r - a } { \sqrt { 2 \sigma ^ { 2 } } } } ^ { \frac { r - b } { \sqrt { 2 \sigma ^ { 2 } } } } e ^ { - u ^ { 2 } } d u
$$

为了方便计算，用误差函数表示式（10）：

$$
F ( a , b ) = - \frac { 1 } { 2 } e r f \left( \frac { r - b } { \sqrt { 2 \sigma ^ { 2 } } } \right) + \frac { 1 } { 2 } e r f \left( \frac { r - a } { \sqrt { 2 \sigma ^ { 2 } } } \right)
$$

其中：误差函数 $e r f ( x )$ 为

$$
e r f \left( x \right) = \frac { 2 } { \sqrt { \pi } } { \int _ { 0 } ^ { x } e ^ { - t ^ { 2 } } d t }
$$

由于 $( a , b )$ 为观测值 $\mathbf { z }$ 和范围 $\mathbf { r }$ 上的间隔，为了方便ISM模型的推导，假设a=-o，所以可重新定义F(ab)：

$$
F ( - \infty , b ) = \operatorname* { l i m } _ { a \to \infty } { \frac { 1 } { \sigma { \sqrt { 2 \pi } } } } \int _ { a } ^ { b } e ^ { \frac { ( r - \tau ) ^ { 2 } } { 2 \sigma ^ { 2 } } } d \tau
$$

根据 $g \left( r \right)$ 的分段区间与 $f ( r )$ 进行卷积积分可得

$$
= - \frac { 1 } { 2 } e r f { \left( \frac { r - b } { \sqrt { 2 \sigma ^ { 2 } } } \right) } - \frac { 1 } { 2 }
$$

$$
\begin{array} { r l r } & { } & { - \ g _ { \mathrm { A } } ^ { \prime } ( x ) = \langle n _ { \mathrm { e } } ^ { \prime } ( x - x ) ^ { 2 } \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } | \mathrm { i } n _ { \mathrm { i } } ^ { \prime } | x - \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } \rangle } \\ & { } & { \quad + \ \sin \left( \frac { \pi \sqrt { 2 } } { 2 } \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } \right) } \\ & { } & { - \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - 2 \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } } { 2 \sqrt { 2 } } \right) + \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - 2 \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } } { 2 \sqrt { 2 } } \right) } \\ & { } & { - \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - 2 \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } } { 2 \sqrt { 2 } } \right) + \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - 2 \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } } { 2 \sqrt { 2 } } \right) } \\ & { } & { - \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - 2 \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } } { 2 \sqrt { 2 } } \right) + \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - 2 \frac { n _ { \mathrm { e } } ^ { \prime } } { 2 } } { 2 \sqrt { 2 } } \right) } \\ & { } & { - \frac { 1 } { 4 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - x ^ { 2 } } { 2 \sqrt { 2 } } \right) + \frac { 1 } { 2 } \mathrm { e } ^ { \prime } \left( \frac { n _ { \mathrm { e } } ^ { \prime } - x ^ { 2 } } { 2 \sqrt { 2 } } \right) } \\ & { } & { 1 , \ldots , } \end{array}
$$$$
- { \frac { 1 } { 4 } } e r f \left( { \frac { - z } { \sigma { \sqrt { 2 } } } } \right)
$$

高斯噪声 $f ( r )$ 与理想ISM模型 $g \left( r \right)$ 卷积的到实际中应用的ISM模型，其卷积前后图形变化如图1所示。

# 2 建立网格地图模型

网格地图是把环境划分为许多个等尺度的单元格，通过网格单元表示部分环境并存储该单元格是否有障碍物的信息，即该单元格状态是占用、空闲还是未知。在占用情况下，它能够表示出障碍物的边界，能够用于路径规划和机器人导航。在空闲情况下表示该单元格没有障碍物，而未知情况下则表示传感器不能够观测到该单元格状态，即是否有障碍物情况未知。占用网格地图的尺度问题是通过其分辨率表示的，如用1cm表示$5 \mathrm { ~ m ~ }$ 等。在占用网格地图中，通过数值0、1、0.5的概率来表示其单元格的状态，其中0表示空闲，1表示被占用，0.5则表示状态未知。

由于在传感器观测外界环境数据时会引入噪声和不确定性因素，所以需要把噪声和不确定性因素的影响加入到网格地图模型中。如果用 $m _ { i }$ 表示地图中第i个单元格，其状态可以用二进制占用变量表示（占用或空闲）。理想情况下，从时间1：t的传感器观测数据 $\textbf { z }$ 和机器人姿态 $\textbf { \em x }$ 已知，对于地图单元格 $\mathrm { ~ m ~ }$ 的后验概率可以表示为

$$
p ( m | z _ { 1 : t } , x _ { 1 : t } )
$$

对于传感器的观测数据 $\textbf { z }$ 以及对应机器人姿态 $\textbf { \^ { x } }$ ，假设其都在世界坐标系下，所以地图单元格 $\mathrm { ~ m ~ }$ 的后验概率又可写做：

$$
p ( m | z _ { 1 : t } )
$$

如果把地图 $\mathbf { m }$ 划分成 $\mathrm { ~ i ~ }$ 个相同尺度的网格，每个网格的下标索引为i，有 $m = \{ m _ { i } \}$ 。根据网格单元是否被占用，用$p ( m _ { i } = 1 )$ 表示被占用， $p ( m _ { i } = 0 )$ 表示空闲， $p ( m _ { i } = 0 . 5 )$ 表示未知状态，其中：

$$
p ( m _ { i } = 0 ) = p \big ( \overline { { m _ { i } } } \big ) = 1 - p ( m _ { i } = 1 )
$$

如果有1000个单元格，那么地图就有 $2 ^ { 1 0 0 0 }$ 种可能，所以对于实际建图来说，这并不是一个切实可行的方案。根据前面所做的Markov假设,每个单元格概率 $p ( m _ { i } | z _ { 1 : t } )$ 是统计独立的,那么N个独立的网格单元概率可表示为

$$
p ( m _ { 1 } , m _ { 2 } , . . . , m _ { N } \mid z _ { 1 : t } , x _ { 1 : t } ) = \prod _ { i } ^ { N } p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } )
$$

随着时间的推移，把第i个单元格被占用与否的概率加入到地图 $\mathrm { ~ m ~ }$ 的概率分布中，最终实现地图的不断更新。为了实现这一机制，采用二进制贝叶斯滤波器算法。对于静态环境，传感器观测数据与地图单元格间是相互独立的，应用贝叶斯法则可得

$$
\begin{array} { c } { p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } \\ { { { } } } \\ { { { } ^ { B a y e s } \underbrace { p \left( z _ { t } \mid m _ { i } , z _ { 1 : t - 1 } , x _ { 1 : t } \right) p \left( m _ { i } , z _ { 1 : t - 1 } , x _ { 1 : t } \right) } } } \\ { { p \left( z _ { t } \mid z _ { 1 : t - 1 } , x _ { 1 : t } \right) } } \\ { { { } ^ { M a r b o v } \underbrace { p \left( z _ { t } \mid m _ { i } , x _ { t } \right) p \left( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } \right) } } } \\ { { { } = \underbrace { p \left( z _ { t } \mid z _ { 1 : t - 1 } , x _ { 1 : t } \right) } } } \end{array}
$$

有Bayes 法则可得：

$$
p ( \boldsymbol { z } _ { t } \mid m _ { i } , \boldsymbol { x } _ { t } ) = \frac { p ( m \mathbin { \mathrm { ~ } } _ { i } \mathbin { | \boldsymbol { z } _ { t } , \boldsymbol { x } _ { t } ) } p ( \boldsymbol { z } _ { t } \mathbin { | \boldsymbol { x } _ { t } ) }  } { p ( m _ { i } \mathbin { | \boldsymbol { x } _ { t } ) } }
$$

带入方程(19)，所以 $p ( m _ { i } | z _ { 1 : t } , x _ { 1 : t } )$ 可化为

$$
\begin{array} { c } { { p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } } \\ { { { } } } \\ { { = \displaystyle \frac { p ( m _ { i } \mid z _ { t } , x _ { t } ) p ( z _ { t } \mid x _ { t } ) p ( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) } { p ( m _ { i } \mid x _ { t } ) p ( z _ { t } \mid z _ { 1 : t - 1 } , x _ { 1 : t } ) } } } \\ { { { } } } \\ { { { } \ } } \\ { { { \stackrel { M a r k o r } { = } } \displaystyle \frac { p ( m _ { i } \mid z _ { t } , x _ { t } ) p ( z _ { t } \mid x _ { t } ) p ( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) } { p ( m _ { i } ) p ( z _ { t } \mid z _ { 1 : t - 1 } , x _ { 1 : t } ) } } } \end{array}
$$

对于概率 $p \big ( \overline { { m _ { i } } } | z _ { 1 : t } , x _ { 1 : t } \big )$ ，应用相同的原理可得

$$
p \big ( \overline { { m _ { i } } } | \boldsymbol { z } _ { 1 : t } , \boldsymbol { x } _ { 1 : t } \big )
$$

$$
= \frac { p \left( \overline { { m _ { i } } } \mid z _ { t } , x _ { t } \right) p \left( z _ { t } , x _ { t } \right) p \left( \overline { { m _ { i } } } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } \right) } { p \left( \overline { { m _ { i } } } \right) p \left( z _ { t } \mid z _ { 1 : t - 1 } , x _ { 1 : t } \right) }
$$

为了减少无味的计算，把式（21）（22）作商，化简可得

$$
\frac { p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } { p \big ( \overline { { { m _ { i } } } } \mid z _ { 1 : t } , x _ { 1 : t } \big ) }
$$

$$
= { \frac { p \left( m _ { i } \mid z _ { t } , x _ { t } \right) p \left( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } \right) p \left( { \overline { { m _ { i } } } } \right) } { p \left( { \overline { { m _ { i } } } } \mid z _ { t } , x _ { t } \right) P \left( { \overline { { m _ { i } } } } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } \right) p \left( m _ { i } \right) } }
$$

$$
= { \frac { p ( m _ { i } \mid z _ { t } , x _ { t } ) } { 1 - p ( m _ { i } \mid z _ { t } , x _ { t } ) } } { \frac { p ( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) } { 1 - p ( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) } } { \frac { 1 - p ( m _ { i } ) } { p ( m _ { i } ) } }
$$

通过对式（23)分析可知，P(m|z,x) 为地图单元格 $m _ { i }$ 在t时刻的后验分布； $\frac { p ( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) } { 1 - p ( m _ { i } \mid z _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) }$ 为递归项；是 $m _ { i }$ 在t-1时刻地图的后验分布； $\frac { 1 - p ( m _ { i } ) } { p ( m _ { i } ) }$ 是地图的先验分布。

为了避免概率在0或1附近数值的不稳定，通常用Logit函数对式（23）取对数，可得

$$
\log \left( \frac { p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } { 1 - p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } \right) = \log \left( \frac { p ( m _ { i } \mid z _ { t } , x _ { t } ) } { 1 - p ( m _ { i } \mid z _ { t } , x _ { t } ) } \right)
$$

$$
+ \log \left( \frac { p ( m _ { i } \mid \varsigma _ { 1 : t - 1 } ) } { 1 - p ( m _ { i } \mid \varsigma _ { 1 : t - 1 } , x _ { 1 : t - 1 } ) } \right) + \log \left( \frac { 1 - p ( m _ { i } ) } { p ( m _ { i } ) } \right)
$$

$L ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) = \log \left( { \frac { p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } { 1 - p ( m _ { i } \mid z _ { 1 : t } , x _ { 1 : t } ) } } \right)$ 式（24）可简化为

$$
L ( m _ { i } \mid { z } _ { 1 : t } , x _ { 1 : t } ) = L ( m _ { i } \mid { z } _ { t } , x _ { t } ) + L ( m _ { i } \mid { z } _ { 1 : t - 1 } , x _ { 1 : t - 1 } )
$$

$$
- L ( m _ { i } )
$$

对式（25）进行分析可知， $L ( m _ { i } \mid z _ { t } , x _ { t } )$ 实质上就是逆传感器模型（ISM）函数， $L ( m _ { i } | z _ { 1 : t - 1 } , x _ { 1 : t - 1 } )$ 为前一时刻的ISM 函数,即递归项， $L ( m _ { i } )$ 是地图的先验信息。为了更加清晰地表达网格地图构建机制，重写上式为

$$
l _ { t , i } = I S M \left( m _ { i } , z _ { t } , x _ { t } \right) + l _ { t - 1 , i } - l _ { 0 }
$$

根据上面的占用网格地图算法的推导，更为清晰地算法表达为：

for all grid cells $m _ { i }$ do

$$
l _ { t , i } = \log ( p ( m _ { i } ) ) - \log ( 1 - p ( m _ { i } ) )
$$

endfor

$/ { ^ * } \mathbf { g } \mathsf { r i d }$ calculation using logit function $^ { * } /$

for all time steps t from 1to T do

for all grid cells $m _ { i }$ in the perceptual range of $z _ { t }$ do

$$
l _ { t , i } = l _ { t - 1 , i } + I S M \left( m _ { i } , z _ { t } , x _ { t } \right) - l _ { 0 }
$$

endfor

endfor

/\*recovery of occupancy probabilities\*/ for all grid cells $m _ { i }$ do

$$
p ( m _ { i } \mid z _ { t } , x _ { t } ) = 1 - { \frac { 1 } { e ^ { l _ { t , i } } } }
$$

endfor

在时间 $\mathfrak { t }$ 时刻，机器人的姿态为 $x _ { 1 : t }$ ，传感器的观测数据为$\boldsymbol { z } _ { 1 : t }$ ，当前所有网格单元为 $\{ m _ { i } \}$ ，每个单元格的后验概率为$p ( m _ { i } | z _ { 1 : t } , x _ { 1 : t } )$ ，按照最大后验概率（MAP）建图，有

$$
m * = \underset { m } { \arg \operatorname* { m a x } } p \big ( z _ { 1 } , z _ { 2 } , . . . , z _ { t } \mid m , x _ { 1 } , x _ { 2 } , . . . , x _ { t } \big )
$$

$$
= \underset { m } { \arg \operatorname* { m a x } } \prod _ { t = 1 } ^ { T } p \big ( \boldsymbol { z } _ { t } | m , \boldsymbol { x } _ { t } \big )
$$

# 3 ORB-SLAM2生成网格地图模型

ORB-SLAM2 生成网格地图是通过在ROS中发布ORB-SLAM2中生成的所有关键帧和地图点以及机器人姿态$x _ { t }$ ，然后订阅其发布信息给ISM模型，作为传感器观测数据 $z _ { t }$ 和机器人姿态 $x _ { t }$ ，进而通过网格地图模型生成所需要的网格地图。其算法流程如图2所示。

![](images/930c3cbe6b778b37bbec546fcc1bfa12428c423f00dc6dfceee813cb4ec69dc4.jpg)  
图2ORB-SLAM2 生成 grid map 算法框图

# 4 实验

# 4.1L值的选取

在讨论L值对ISM影响时，采用固定变量的策略。首先，固定z值和固定的高斯噪声模型，通过改变L值的大小，观测ISM模型的变化。L值对ISM模型影响如图3所示。

![](images/d6b0c41ae26dc9477fa1520b18a90e7c627a9b00f19a5b9d738d982c8f93fb46.jpg)  
图3L值对ISM模型影响

通过对图3的分析可以看出，随着L的取值的不断变大，ISM模型网格单元概率不断地增大，这说明随着L的增大，将会有更多的网格单元被判断为有障碍物；与之相反，网格地图中的空闲的单元格将会减少，当L的取值超过一定的界限是，会出现大量的误判，即现实环境中本没有障碍物的地方会被误判为有障碍物。通过实验得到，当L的取值为网格单元对角线的长度时，出现的误判几率最小。

# 4.2不确定性因素和观测范围z的影响

由于在传感器的观测过程中会引入噪声和一些不确定性因素，而这些噪声和不确定因素同样会对地图的构建造成影响，首先讨论加入不确定性因素的ISM模型的影响。 $\sigma$ 值对ISM模型影响图4所示。

![](images/cfc49bf8128c387b76cd4776130cbdee937874cb3f7d02b63f2818c2ed6f4bbd.jpg)  
图4 $\sigma$ 值对 ISM 模型影响

从图4可以看出，不同的 $\sigma$ 值对ISM模型的影响。随着 $\sigma$ 值的不断变大，表示不确定性因素和噪声的影响越来越大，随之而来的是ISM模型的网格单元的后验概率越来越小，这表示将会有更多的网格单元被判断为空间，然而事实并非如此。

![](images/e1e4cc0aef0e619207e1174d7a06ac0cfd4eff853dc8da693a5b42c1716ea36b.jpg)  
图5 $\textbf { z }$ 值对ISM模型影响

对于不同观测范围 $\textbf { z }$ ，同样会影响ISM模型（图5）。通过对图5的分析可以看出，随着观测范围 $\textbf { z }$ 的不断增大，机器人的观测范围会越来越大；同时在越来越大的范围内，机器人对地图网格单元的判断也就越来越不准确。

# 4.3 室内实时实验

对于室内的实时测试选取在在实验室内和走廊。所用的实验设备是一个XBOX360 的深度相机和Logitech 的USB摄像机。

首先用USB摄像机作实验室室内实验。通过实验可以看出，用单目相机做实验时，在生成的网格地图中，对障碍物的标注不够清晰，而且对于实验室中轴线上的办公桌等障碍物无法标注出来。这是由于单目相机是没有尺度信息的，在生成地图点云图的过程中会把中间的关键帧、特征点等信息错误地划分到实验室的边缘上。这导致了在生成网格地图的过程中不能够成功地标注出实验室中轴线上的障碍物，最终生成错误的网格地图。真实室内环境和单目相机生成室内网格地图如图6所示。

![](images/81b2451c7a035d7df071bba6f9b587cb30f6003774ea0f265607ddd37560b952.jpg)  
图6真实室内环境和单目相机生成室内网格地图

为了克服单目相机没有尺度信息致使生成错误的网格地图，用具有尺度信息的RGB-D相机做室内实验。通过RGB-D实验结果与单目相机的实验结果作对比可以发现，用RGB-D相机产生的网格地图相比于单目相机有两个优点：a)RGB-D相机具有尺度信息，其生成的地图点云图能够正确地生成网格地图，对于室内中轴线上的障碍物也能够标注出来；b)其生成的网格地图相比于单目相机生成的网格地图更加清晰，对于室内的障碍物能够清晰地显示出来，而且能够标准出障碍物的相对位置，并不像单目相机那样把所以的障碍物都归一于一个平面上。图7为RGB-D相机的运动轨迹点云图。从图中能够看到相机运动一周其生成的室内环境稀疏点云图，即其运动轨迹。图8为RGB-D相机在其运动过程中生成的网格地图。图中网格地图是参差不齐的，这是因为如图6中的真实场景所示，由于室内存在桌凳等不规则障碍物造成的。

![](images/96bde71c1274607c18bcf6dc9140bb4338bd8b7dfcf8c35a477b69b4cce988a3.jpg)  
图7RGB-D运动轨迹点云图

![](images/883c020e58dcf4e1fc1579ef914046b297f32d5abef4735df4dd1431c9fa9d34.jpg)  
图10RGB-D相机走廊网格地图

# 5 结束语

初

![](images/e6474bb4f837a17068197ec48b81d4b2eb0b14ee73bc1502f0bdbfbd39b17fed.jpg)  
图9走廊场景和运动轨迹点云图  
图8RGB-D相机生成室内网格地图

走廊场景和运动轨迹点云图如图9所示。在完成室内小场景的实验后，用RGB-D相机在走廊做大场景实验（图10）。通过实验结果可以看出，对于走廊环境，生成的网格地图能够清晰看到走廊两边的墙壁和实验室的门槛等事物，其中突出较大部分非走廊旁边的电梯口，能够很好地反映出走廊环境，并标注出走廊中的障碍物。

针对以往视觉SLAM系统生成地图不能用于机器人导航和路径规划的缺点，本文在ORB-SLAM2 的基础上，提出一种网格地图实时构建算法。该算法建立了适合用于视觉SLAM的逆传感器模型（ISM），并对模型进行了定性分析，确定了切实可用的ISM模型，详细推导了网格地图构建机制，并利用算法框图清晰地解释了ORB-SLAM2生成网格地图的具体流程。通过实验，对单目相机和RGB-D相机的实验结果进行分析，实验表明ISM模型和网格地图算法的有效性以及本文算法具有较强的实用性，能够实时生成用于机器人导航和路径规划的地图。

# 参考文献：

[1]Cadena C,Carlone L,Carrillo H,et al.Past,present,and future of simultaneous localization and mapping: Toward the robust-perception age [J].IEEE Trans on Robotics,2016,32(6):1309-1332.   
[2]Mourikis AI,Roumeliotis S I.A multi-state constraint Kalman filter for vision-aided inertial navigation [C]//Proc ofIEEE International Conference on Robotics and Automation．Roma,Italy: Institute of Electrical and Electronics Engineers Inc,2007: 3565-3572.   
[3]Bloesch M,Omari S,Hutter M,et al.Robust visual inertial odometry using adirect EKF-based approach [C]// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.Hamburg，Germany: Institute of Electrical and Electronics Engineers Inc,2O15: 298-304.   
[4]Bloesch M,Burri M,Omari S,et al. Iterated extended Kalman filter based visual-inertial odometry using direct photometric feedback [J]. The International Journal of Robotics Research,2017,36 (10):1053-1072.   
[5]Leutenegger S,Lynen S,Bosse M,et al.Keyframe-based visual-inertial odometry using nonlinear optimization [J].The International Journal of Robotics Research,2015,34(3): 314-334.   
[6]Mur-Artal R,Montiel JMM,Tardos JD.ORB-SLAM:a versatile and accurate monocular SLAM system [J].IEEE Trans on Robotics,2015,31 (5): 1147-1163.   
[7]Mur-Artal R,Tardos JD.Orb-slam2:an open-source slam system for monocular, stereo,and rgb-d cameras [J].IEEE Trans on Robotics,2017, 33 (5): 1255-1262.   
[8]Qin Tong,Shen Shaojie.Robust initialization of monocular visual-inertial estimation on aerial robots [C]// Proc of the IEEE//RSJ International Conference on Intelligent Robots and Systems.Vancouver,BC,Canada: Institute of Electrical and Electronics Engineers Inc,2O17:24-28.   
[9]SantanaAM,AiresKRT,VerasRMS,etal.An approach for 2Dvisual occupancy grid map using monocular vision [J].Electronic Notes in Theoretical Computer Science,2011,281:175-191   
[10]Dia R,Motin J,Rakotovao T,et al.Evaluation of occupancy grid resolution through a novel approach for inverse sensor modeling [J]. IFAC-Papers OnLine,2017,50(1):13841-13847.   
[11] Hull G. Real-time occupancy grid mapping using LSD-SLAM [D].[S. 1.] : Stellenbosch: Stellenbosch University,2017.   
[12]De Gregorio D,Di Stefano L. SkiMap:an efficient mapping framework for robotnavigation[C]//ProcofIEEEInternationalConference on Robotics and Automation． Singapore:Institute of Electrical and Electronics Engineers Inc,2017: 2569-2576.   
[13] Levine M P. System and method of drawing anti-aliased lines using a modified bresenham line-drawing algorithm:U.S.Patent 5,815,162 [P]. 1998-09-29.

[14]侯荣波，魏武，黄婷，等．基于ORB-SLAM 的室内机器人定位和三维

稠密地图构建[J].计算机应用,2017,37(5):1439-1444.(Hou Rongbo, Wei Wu,Huang Ting，et al. Indoor robot localization and 3D dense mapping based on ORB-SLAM[J].Journal of Computer Applications. 2017,37 (5): 1439-1444.)   
[15]王权，胡越黎，张贺．基于ROS与Kinect 的移动机器人同时定位与 地图构建[J].计算机应用研究,2017,34(10):3184-3187.(Wang Quan Hu Yueli, Zhang He,Mobile robot simultaneous localization and mapping based on ROS and Kinect [J].Application Research of Computers,2017, 34 (10): 3184-3187.)   
[16]王巍，浦云明，李旺．一种基于CI因子图的多机器人2D 地图融合 算法[J].机器人,2017,39(6):872-878.   
[17](Wang Wei，Pu Yunming,Li Wang.A multi-robot 2D map fusion algorithm based on CIfactor graph [J].Robot,2017,39 (6): 872-878.)   
[18]罗元，傅有力，程铁凤．基于改进Rao-Blackwellized 粒子滤波器的同 时定位与地图构建[J].控制理论与应用,2015,32(2):267.(Luo Yuan, Fu Youli,Cheng Tiefeng， Simultaneous localization and mapping implementation based on the improved rao-blackwellized particle filter [J]. Control Theory& Applications,2015,32(2): 267.)