# 与活动区AR11158中的一个X2.2级耀斑相关的视向电流密度的计算

杨丽平1,2，梁红飞1.2，刘继宏3.4,王楠1.2，孙霞1.2，李子涵1.2(1.云南师范大学物理与电子信息学院，云南昆明650500；2.云南省高校高能天体物理重点实验室云南昆明650500;3.中国科学院云南天文台云南昆明650216；4.石家庄学院物理学院机电学院 河北石家庄050035）

摘要：太阳高能活动爆发与活动区内的电流结构有着密切的联系，安培（Ampere）定律 $\scriptstyle j _ { z } = { \frac { 1 } { \mu _ { 0 } } } ( \nabla \times { \boldsymbol { B } } ) _ { z }$ 是测量活动区内视向电流密度的理论基础。由于实测的矢量磁场中不可避免地存在随机噪声，因此，应用安培定律的不同形式计算的电流密度存在显著的差异。为了比较不同形式计算结果的差异并从中探索一种实用的电流计算方法，基于太阳动力学天文台(Solar Dynamic Observatory,SDO)/HMI(Helioseismic and Magnetic Imager)在2011年2月15日测量的活动区AR11158的矢量磁图，运用安培定律的微分算法和积分算法分别计算了活动区内视向电流密度的分布图。结果显示，微分算法获得的视向电流密度 $j _ { z }$ 分布图受随机噪声的影响要远比积分算法获得的结果大，电流分布图中的电流结构没有积分算法获得的结果清晰。另外，在扩大积分环路半径的情况下，所计算的电流分布图里的噪声信号快速降低，从而使计算的视向电流分布图中的电流结构更清晰。但是当继续扩大积分环路半径时，在获得清晰电流分布图的同时，电流分布图的部分精细结构也随之失真。该研究结果论证了适当扩大积分环路计算视向电流分布图可以降低计算结果受随机噪声的影响从而获得清晰真实的视向电流分布图，但是积分路径的半径过大在消除噪声影响的同时会丢失电流分布中的一些精细结构。因此在实际计算电流的过程中，应该利用高分辨率的矢量磁图，选定合适的积分路径运用安培定律的积分算法来计算活动区的视向电流，从而帮助我们探索耀斑爆发与活动区内电流结构的关系。

关键词：活动区；耀斑；矢量磁场；电流密度；安培定律中图分类号：P182文献标识码：A 文章编号：1672-7673（2021）02

太阳耀斑是太阳大气中发生的高能爆发现象，其爆发过程中常伴随日冕物质抛射（CoronalMass Ejection，CME）现象并向行星际释放大量的高能粒子流和磁云，成为引起灾害性空间天气的主要因素[1]。因此，研究耀斑爆发机制对有效预防空间灾害性天气有非常重要的意义。研究表明，磁流浮现和对消[2]、黑子旋转[3-4]、剪切运动[5]是触发大耀斑爆发的3 种主要机制，在对活动区AR12673多个耀斑（包含一个X9.3级大耀斑）的研究中[提出了一种新的耀斑爆发的触发机制，即由先前存在的磁场的阻挡引发的爆发模型。活动区AR12673在2017年9月4日至10日，产生了包括4个X级耀斑、27个M级耀斑和57个C级耀斑在内的88个耀斑，强度最大的两个耀斑分别发生在9月6日（X9.3级）和9月10日（X8.2级)，X9.3

级耀斑是第24个太阳活动周中最强的耀斑，其爆发会产生很强的地球物理效应。因此，人们对该活动区进行了大量研究，相关研究结果表明，剪切运动和黑子旋转在触发两个连续的X 级耀斑和日冕物质抛射中具有重要作用[7]，耀斑能量释放发生在中性线上方的低剪切磁环区域，光球的增量是由于耀斑产生的高能粒子轰击光球产生的。在耀斑爆发过程中，磁重联被认为是能量快速释放的有效机制[9]，磁重联通常发生在剪切程度高的磁场区域[10]。在磁重联过程中，磁拓扑结构发生改变，磁能转化为加热等离子体的热能和加速粒子的动能。通常认为，磁重联最初的能量释放主要发生在日冕中，耀斑的爆发主要由磁重联释放的自由磁能驱动。自由磁能是指总磁能与势场磁能之间的差值，爆发耀斑的活动区磁位形偏离势场越大，活动区的总磁能与势场磁能的差值就越大，活动区的非势性就越强，储存的自由磁能就越多，耀斑产生的几率就越大[。光球及光球下方磁力线的剪切和扭绞，新浮现的磁流等都会形成活动区磁场的非势性[12。由于磁中性线处的磁场梯度较大，磁场的纵向分量无明显变化，但水平磁场高度剪切，在磁压力的作用下产生大量的自由磁能，所以多数耀斑趋向于产生在磁中性线附近[13-14]。对5个X级耀斑的研究[15]发现沿磁中性线的磁场剪切在耀斑之后有明显增强。最近一些基于高分辨率观测获得的矢量磁图的研究表明,在沿其主要磁中性线有强剪切的活动区中存在大量净电流[16]。文[17]对活动区电流分布的研究表明，能够驱动日冕物质抛射和耀斑的活动区与生俱来具有大量净电流，与最近的观测结果一致，而且耀斑带的位置和形态与光球层强电流带有密切关系，在耀斑演化过程中，耀斑带的形态改变可能与电流带相关[18]。太阳活动区中电流密度较高的区域[19]与 $H _ { \alpha }$ 耀斑核块及具有极大剪切的磁场区域相重合[20]，这个结果支持了耀斑是由强电流引起的等离子体的不稳定性触发的理论[21]。这些研究都证实了电流可能在耀斑爆发之前就已存在，并在耀斑爆发中起重要的作用，活动区中电流带与耀斑带之间密切相关。因此，计算活动区磁中性线两侧强磁场中的电流分布对于预测耀斑爆发的位置和形态具有重要意义。

随着观测仪器的时间和空间分辨率不断提高，人类对太阳爆发活动机制有了比较深入的了解，其中，准确的矢量磁场测量对研究太阳爆发活动的触发机制非常重要。太阳矢量磁场的测量是基于塞曼效应进行的，由于来自日冕、过渡区等太阳大气的偏振信号非常弱，因此，这些区域的矢量磁场目前还很难获得，目前唯一能够精确测量磁场的区域只有光球层。基于测量的光球层磁场结构，人们以此为边界条件运用非线性无力场(NLFFF)2模型进行外推获得三维空间矢量磁场的可能结构。由于无法准确测量日冕层的矢量磁场，也就几乎不可能准确计算日冕中的电流分布。基于精确测量的光球矢量磁图，我们可以运用安培定律计算光球层的视向电流密度分布。由于观测仪器在测量矢量磁场的过程中不可避免地受到系统误差和随机误差的影响，其中，系统误差主要来源于对太阳大气的相关参数所做的假设和简化、仪器散光和镜片的非正常反射、系统的相干。随机误差主要由大气视宁度、观测仪器电噪声等引起[23]。系统误差可以在某种程度上从原始数据中消除或采用如暗场处理、平场处理等方法减小它们对结果的影响，无法消除的那部分系统误差在整个视场是连续可导函数，它们对电流的影响也有一定规律。而随机误差在不同的空间格点上随机变化，它们不能从原始数据中消除，通常服从正态分布。这给我们运用安培定律微分算法计算视向电流密度带来很大的障碍。文[24]通过在矢量磁场中引入随机噪声，研究了随机噪声产生的影响和空间分辨率之间的关系，并分析微分法、小环路积分法和大环路积分法得到的结果，他们发现当忽略高阶项时，沿一个大环路的安培定律的积分形式计算电流密度分布得到的结果最好。为了进一步验证梁红飞等人的结果，并检验耀斑带和电流带的对应关系，我们利用 SDO/HMI在 2011年 2月15日观测到的活动区AR11158的矢量磁场，运用安培定律的4种形式（微分形式、小环路积分、中环路积分、大环路积分）计算该活动区的视向电流分布，将积分法的积分环路扩大到适当的大小进行比较。我们还考察了计算结果的电流密度极值与耀斑带的位置和形态的对应关系，以检验计算电流密度方法的有效性和合理性。

# 1数据来源和计算方法

# 1.1数据来源

SDO(Solar Dynamics Observatory） [25]/HMI (Helioseismic and Magnetic Imager)[26]、大气成像组件（Atmospheric Imaging Assembly，AIA）[27]以及远紫外辐照变化探测（EUVVariability Experiment，EVE）是搭载在 SDO卫星上的3台仪器。通过 SDO/HMI可以获得太阳光球层的矢量磁场、光球强度以及多普勒速度等相关数据。2011年2月15日位于太阳西南方向（S20W12）的活动区AR11158具有 $\beta \gamma$ 结构的复杂磁位型，在1:44UT-02:06UT 期间该活动区爆发了一个持续了约 $2 2 \mathrm { m i n }$ 的X2.2级耀斑，有关该活动区的研究可参考文[28-29]，在本文中，我们通过 SDO/HMI 获得其在耀斑爆发期间观测的磁场数据，空间分辨率为0.5角秒/像素，时间分辨率为45秒/帧。矢量磁场的测量是基于塞曼效应运用偏振辐射转移方程获得，获得矢量磁场数据的具体过程见文[30]，SDO/HMI利用斯托克斯（Stokes）矢量的快速反演技术 VFISV(Very Fast Inversion of the Stokes Vector）3得出矢量磁图。矢量磁图的时间分辨率为12 分种/帧。由于以偏振辐射转移方程为理论基础求解矢量磁场的过程中往往存在方位角 $1 8 0 ^ { \circ }$ 不确定性问题，给太阳磁场的测量带来很大的障碍，为了解决这个问题，势场校准法[32]、无力场近似法[344]、最小能量法[35]、磁荷法[36]、连续性方法[37]等先后提出并得以完善，从而很好地解决了太阳磁场测量中的方位角 $1 8 0 ^ { \circ }$ 不确定性问题，在利用 SDO/HMI测量的活动区偏振信号反演矢量磁场的过程中，SDO 团队利用能量最小法对矢量磁场数据进行预处理,解决了矢量磁图中的方位角 $1 8 0 ^ { 0 }$ 不确定性问题[35，使得太阳磁场的相关研究得以顺利进行。

SDO/AIA 是用于观测不同高度的太阳大气层的仪器，可以同时提供10个不同波段的太阳大气信息。这10个波段包括7个极紫外波段（EUV）、2个紫外波段（UV）和1个可见光波段（连续谱 $4 5 0 ~ \mathrm { n m }$ )。其中EUV 波段包括 $3 0 . 4 { \mathrm { n m } }$ ， $1 7 . 1 \mathrm { n m }$ ，19.3 nm,21.1 nm,33.5 nm, 9.4nm, $1 3 . 1 \mathrm { n m }$ ;UV波段包括 $1 7 0 \mathrm { n m }$ 和 $1 6 0 ~ \mathrm { { n m } }$ 。各波段在大气中对应的谱线及观测区域在文[38]中进行了详细介绍。AIA 图像的空间分辨率为0.6 角秒/像素,时间分辨率分别为 12 秒/帧(EUV波段)，24秒/帧（UV波段)。本文所用SDO/AIA数据是 $1 7 0 \mathrm { n m }$ 波段和 $3 0 . 4 \mathrm { n m }$ 波段，其中， $1 7 0 \ \mathrm { n m }$ 波段的观测区域为温度极小区、光球层， $3 0 . 4 \ \mathrm { n m }$ 波段的观测区域为色球层、过渡区。

# 1.2计算方法

图1(a)为活动区AR11158在2月15日02:00:00UT时刻的纵向磁图，其中白色为正极磁场，黑色为负极磁场，黑色框所围区域内存在一对极性相反的磁极，红色箭头所指位置为正负磁极分界的磁中性线如图（a）和（b）中黄色虚线）位置，磁中性线的上方为一个椭圆形负磁极，下方为一个半月形的正磁极，在磁中性线附近磁场的梯度非常大。通常磁中性线也称作纵向磁场的极性变换线，是正负极磁场的分界线。图1（b）为活动区在2月15日$0 2 : 0 0 : 0 0 \mathrm { U T }$ 时刻 SDO/HMI观测到的矢量磁图，为了能够清晰地看出矢量磁场的结构，图中以纵向磁场为背景，叠加在纵向磁场上方的小箭头表示横向磁场，其中蓝色箭头覆盖区域为正极磁场，红色箭头覆盖区域为负极磁场，箭头长度表示横向磁场的大小，箭头方向表示横向磁场的方向，灰度图与图1（a）完全相同，均表示纵向磁场的大小。从表示横向磁场的箭头簇不难看出，横向磁图具有旋涡状的结构，这种结构意味着活动区内可能存在比较强的电流，我们利用这些矢量磁图运用安培定律的不同形式计算活动区内的电流密度分布，并比较和分析不同方法计算结果的差异，从而挑选一种最优的电流密度计算方法。太阳动力学天文台除了提供该活动区的矢量磁图外，还在不同波段采集到了活动区的单色像。图1（c)和（d）为SDO/AIA分别利用谱线 $1 7 0 \ \mathrm { n m }$ （01:58：08UT）和 $3 0 . 4 \mathrm { n m }$ （01:58:12UT）观测到的2011年2月15日在活动区AR11158产生的 X2.2级耀斑的单色像图。从图中可以看出，耀斑带主要在黑色方框区域内，部分结构位于方框的右上沿，对比图1（a)，（c）和（d)不难发现，耀斑主要位于磁中性线附近。

![](images/6d70a7852c48c0fb293047697e5eb37262ec8bce989374fcc3ad14f434933dd9.jpg)  
图1活动区AR11158的纵向磁图，矢量磁图和 $1 7 0 \ \mathrm { n m }$ 波段， $3 0 . 4 \mathrm { n m }$ 波段的单色像图  
Fig.1 TheLongitudinal magnetogram，vector magnetogram and monochromatic image of the active region AR11158 acquired at $1 7 0 \ \mathrm { n m }$ and $3 0 . 4 \ \mathrm { n m }$ wavelength.

研究表明，在太阳活动区内可能存在空间尺度相对较小但物质密度很高的片状电流结构，目前已获得这些片状电流结构大量的观测数据，特别是耀斑爆发期间的观测数据，但是电流结构内的电流强度以及具体的电流密度分布特征目前还很难准确测量到[39-41]。我们利用来自HMI的光球矢量数据计算光球表面的视向电流密度 $j _ { z }$ 。针对矢量磁图数据都是离散的特点，通常情况下运用安培定律 $\scriptstyle j _ { z } = { \frac { 1 } { \mu _ { 0 } } } ( \nabla \times { \pmb B } ) _ { z }$ 的差分形式

$$
( j _ { z } ) _ { i , j } \mathrm { = } \frac { 1 } { \mu _ { 0 } } ( \frac { \partial B y } { \partial x } - \frac { \partial B _ { x } } { \partial y } ) _ { i , j }
$$

计算视向电流密度 $j _ { z }$ ，其中， $\mu _ { 0 }$ 为真空中的磁导率。如图2，利用 $B _ { \mathrm { x } } , B _ { \mathrm { y } }$ 在最里面的小正方形4条边上的中点 $A \left( _ { X ^ { + } } \Delta _ { X } , _ { Y } \right)$ 、 $B ( _ { X } , _ { Y ^ { + } } \Delta _ { Y } )$ 、 $C ( _ { X ^ { - } } \Delta _ { X , \ Y } )$ 、 $D ( _ { X } , _ { Y } - \Delta _ { { Y } } )$ 的值进行计算，差分公式变为

$$
\begin{array} { r } { ( j _ { z 0 } ) _ { i , j } \approx \frac { 1 } { \mu _ { 0 } } \left[ \frac { \left( B _ { y } \right) _ { i + 1 , ~ j } - \left( B _ { y } \right) _ { i - 1 , ~ j } } { 2 \Delta x } - \frac { \left( B _ { x } \right) _ { i , j + 1 } - \left( B _ { x } \right) _ { i , ~ j - 1 } } { 2 \Delta y } \right] } \end{array}
$$

其中， $j _ { z 0 }$ 为运用差分法计算的视向电流密度。由（2）式可以看出，空间分辨率越高，空间格点宽度（ $\Delta { } _ { X }$ 和 $\Delta { y } \dot { }$ ）越小，计算的电流密度结构越精细。由于实际所测磁场 ${ \pmb B } _ { t } ^ { \prime }$ 往往受随机噪声影响而引起误差矢量 $\delta \pmb { B }$ ，用 $\boldsymbol { B } _ { t }$ 表示活动区内磁场的真实值与系统误差之和，实际所测磁场可以表示为 ${ B _ { t } } ^ { \prime } \mathrm { { = } } { B _ { t } } \mathrm { { + } } \delta B$ ，所计算的视向电流密度 ${ j _ { z 0 } } ^ { \prime }$ 为真实的视向电流密度 $j _ { z o }$ 与随机噪声产生的误差电流密度 $\delta _ { j z o }$ 之和，即

$$
\begin{array} { r } { { j _ { z 0 } } ^ { \prime } { = } \frac { 1 } { \mu _ { 0 } } \Big ( \frac { \Delta B _ { y } } { \Delta x } - \frac { \Delta B _ { x } } { \Delta y } \Big ) + \frac { 1 } { \mu _ { 0 } } \Big ( \frac { \Delta \delta B _ { y } } { \Delta x } - \frac { \Delta \delta B _ { x } } { \Delta y } \Big ) = j _ { z o } + \delta _ { j z 0 } \ . } \end{array}
$$

由（3）式可知，当随机噪声 $\delta B _ { x }$ 和 $\delta B _ { y }$ 不变时， $\Delta { _ { X } }$ 和 $\Delta y$ 随着空间分辨率的提高而减小，最终导致视向电流密度增加并将真实电流密度淹没，所以我们通常用安培定律的积分形式

$$
\scriptstyle j _ { z } = \frac { 1 } { \mu _ { 0 } } \oint _ { l } B _ { t } \cdot d t / \mathrm { d } s
$$

计算视向电流密度，其中， $\boldsymbol { B } _ { t }$ 为实测横向磁场， $\pmb { { B } } _ { t } = e _ { i } \mathrm { { B } } _ { \mathrm { { x } } } + e _ { j } \mathrm { { B } } _ { y }$ ， $e _ { i } , e _ { j } , B _ { x } , B _ { y }$ 分别是 $x , y$ 方向的单位矢量及实测横向磁场的两个分量；ds 为积分路径t所围的面积，通常选择边长为$n \Delta x$ 的正方形为积分路径， $n$ 为空间格点数，则 $\scriptstyle \Delta s = n ( \Delta x ) ^ { 2 }$ 。由（4）式可知， $\Delta x$ 随着矢量磁场空间分辨率的变化而变化，分辨率越高环路需要扩得越大，分辨率越低环路需要扩得越小，通过分辨率的高低来选择适当大小的积分环路可以快速降低随机噪声对计算结果的影响。通常根据分辨率的大小来定义小环路、中环路、大环路。

![](images/391beb3a8ecb05d16f1ba7fdef04f2ecde6048453520f1d3866a3b856cd01d14.jpg)

图2安培定律积分形式的积分路径：内部最小的正方形为积分路径 $\cdot C _ { 1 }$ ，由内向外第2个正方形为积分路径 ${ \bf \nabla } \cdot { \cal C } _ { 2 }$ ，第3个正方形为积分路径 ${ \bf \cal C } _ { 3 }$ 。位于 ${ \bf \nabla } \cdot { \bf { { C } } } _ { 1 }$ 上的4个有星号的点对应于安培定律的差分形式，即基于横向磁场 $\mathbf { \nabla } _ { \mathbf { \left| \boldsymbol { B } _ { t } \right| } }$ 在 $\mathbb { A } \left[ \mathrm { x } { + } \Delta \mathrm { x } \right.$ ，y]、 $\mathrm { B } \mathrm { [ _ { X } }$ ， $\mathrm { y + } \Delta \mathrm { y } ]$ 、 $\mathrm { C } \left[ \mathrm { x } { - } \Delta \right.$ X，y]、D[x， $\mathrm { y } { - } \Delta \mathrm { y } ]$ 点的值可通过Ampere 定律的差分形式计算 $[ \mathrm { x }$ ，y]处的视向电流密度值。

Fig.2The integration paths of the Ampere’slaw integral form：The smallest square is the integration path $C _ { 1 }$ from the inner to the outside， the second square is the integration path $C _ { 2 }$ ，and the third square is the integration path $C _ { 3 }$ . The four‘star’points which locating in the $C _ { 1 }$ are corresponding to the differential form of Ampere’s law.That is,based on the value of transverse magnetic field $\pmb { B } _ { t }$ at $\mathbb { A } \left[ \mathrm { x } ^ { + } \Delta \mathrm { x } \right.$ ，y]， $\mathrm { B } \mathrm { [ x }$ ， $\mathrm { y + } \Delta \mathrm { y } ]$ ， $\mathrm { C } \left[ \mathrm { x } { - } \Delta \mathrm { x } \right.$ ，y]，D[x，y$\Delta \mathrm { y } ]$ ，the vertical electric current density value at $[ \mathrm { x } , \ \mathrm { y } ]$ can calculate by using the differential form of Ampere's

如图2，环路积分法是利用横向磁场 ${ \bf \nabla } \cdot { \bf B } _ { t }$ 在积分路径上的值计算积分环路所围面积内的平均电流密度，得出积分环路中心 $O \ ( \chi , \ y )$ 点的电流密度，所得电流密度为积分区域的平均电流密度。积分路径沿逆时针方向，积分环路以 $O \ ( \chi , \ y )$ 为中心由小到大 (或由内向外)依次称为小环路（以 $2 \Delta { x }$ 为边长的正方形，积分路径为 $C _ { 1 }$ ）、中环路（以 $4 \Delta { x }$ 为边长的正方形，积分路径为 $C _ { 2 }$ ）和大环路（以 $6 \Delta { _ { X } }$ 为边长的正方形，积分路径为 ${ C } _ { 3 }$ ）。其中，小环路的积分路径是沿点（ $\ b { \mathrm { X } } ^ { + } \ b { \Delta } \ b { \mathrm { X } }$ ， $\mathrm { y + } \Delta \mathrm { y }$ ），（ $\langle x ^ { - } \Delta x$ ， $\mathrm { y + } \Delta \mathrm { y }$ ），（ $\big . \mathrm { x } - \Delta \mathrm { x }$ ， $\mathrm { y - } \Delta \mathrm { y }$ ）和（ $\cdot x ^ { + } \Delta x$ ，$\mathrm { y - } \Delta \mathrm { y } )$ 所在正方形边缘，积分路径为 $C _ { 1 }$ ，对应的视向电流密度为 $j _ { z _ { 1 } }$ 。由（3）式可得小环路的计算公式为

$$
\begin{array} { r l } & { \mathfrak { j } _ { i , j } = \frac { 1 } { \mu _ { 0 } } \oint _ { c 1 } B _ { t } \cdot d / / \mathrm { d } \mathrm { s } } \\ & { \quad \approx \frac { 1 } { 4 \mu _ { 0 } \Delta x \Delta y } ( \sum _ { n = i } ^ { i + 1 } \frac { ( B _ { x } ) _ { n - 1 , j - 1 } + ( B _ { x } ) _ { n , j - 1 } } { 2 } \Delta \mathrm { x } + \sum _ { n = j } ^ { j + 1 } \frac { ( B _ { y } ) _ { i + 1 , n - 1 } + ( B _ { y } ) _ { i + 1 , n } } { 2 } \Delta \mathrm { y } } \\ & { \quad \quad - \sum _ { n = i } ^ { i + 1 } \frac { ( B _ { x } ) _ { n - 1 , j + 1 } + ( B _ { x } ) _ { n , j + 1 } } { 2 } \Delta x - \sum _ { n = j } ^ { j + 1 } \frac { ( B _ { y } ) _ { i - 1 , n - 1 } + ( B _ { y } ) _ { i - 1 , n } } { 2 } \Delta y ) } \end{array}
$$

其中， $\mathrm { d } \mathrm { s } { = } 2 \Delta \mathrm { x } { * } 2 \Delta \mathrm { y }$ 。

中环路的积分路径是沿点 $\mathbf { \Phi } ^ { \prime } ( \mathbf { x } + 2 \Delta \mathbf { x } , \mathbf { y } + 2 \Delta \mathbf { y } )$ ，（x-2△x, $\scriptstyle { y + 2 \Delta y } .$ ），（x-2△x,y-2△y）和（20 $( \mathrm { x } + 2 \Delta \mathrm { x } , \mathrm { y } { - } 2 \Delta \mathrm { y } )$ 所在正方形的边缘，积分路径为 $C _ { 2 }$ 对应的视向电流密度为 $j _ { z 2 }$ 。由（3）式可得中环路的计算公式为

$$
\begin{array} { r l } & { \quad ^ { r ^ { * _ { 0 } } } } \\ & { \approx \frac { 1 } { 1 6 \mu _ { 0 } \varDelta x d y } ( \sum _ { n = i - 1 } ^ { i + 2 } \frac { ( B _ { x } ) _ { n - 1 , j - 2 } + ( B _ { x } ) _ { n , j - 2 } } { 2 } \Delta x + \sum _ { n = j - 1 } ^ { j + 2 } \frac { ( B _ { y } ) _ { i + 2 , n - 1 } + ( B _ { y } ) _ { i + 2 , n } } { 2 } \ \Delta y } \\ & { \quad - \sum _ { n = i - 1 } ^ { i + 2 } \frac { ( B _ { x } ) _ { n - 1 , j + 2 } + ( B _ { x } ) _ { n , j + 2 } } { 2 } \Delta \mathrm { x } - \sum _ { n = j - 1 } ^ { j + 2 } \frac { ( B _ { y } ) _ { i - 2 , n - 1 } + ( B _ { y } ) _ { i - 2 , n } } { 2 } \Delta y ) } \end{array}
$$

其中， $\mathrm { d } \mathrm { s } { = } 4 \Delta \mathrm { x } { * } 4 \Delta \mathrm { y }$ 。

大环路的积分路径是沿点 $( \mathbf { x } + 3 \Delta \mathbf { x } , \mathbf { y } + 3 \Delta \mathbf { y } )$ ，（x-3△x, $\tt y + 3 \Delta y )$ ），（x-3△x,y-3△y）和（204号 $( { \bf x } + 3 \Delta { \bf x } , { \bf y } { - } 3 \Delta { \bf y } )$ 所在正方形的边缘，积分路径为 ${ C } _ { 3 } ,$ 对应的视向电流密度为 $j _ { z 3 }$ 。由（3）式可得大环路的计算公式为

$$
\begin{array} { r l } { { 3 } ) _ { i , j } } & { = \frac { 1 } { \mu _ { 0 } } \oint _ { c 3 } B _ { t } \cdot d l / d s } \\ & { \approx \frac { 1 } { 3 6 \mu _ { 0 } \Delta x \Delta y } ( \sum _ { n = i - 2 } ^ { i + 3 } \frac { ( B _ { x } ) _ { n - 1 , j - 3 } + ( B _ { x } ) _ { n , j - 3 } } { 2 } \Delta x + \sum _ { n = j - 2 } ^ { j + 3 } \frac { \left( B _ { y } \right) _ { i + 3 , n - 1 } + \left( B _ { y } \right) _ { i + 3 , n } } { 2 } \Delta y } \\ & { \quad - \sum _ { n = i - 2 } ^ { i + 3 } \frac { ( B _ { x } ) _ { n - 1 , j + 3 } + ( B _ { x } ) _ { n , j + 3 } } { 2 } \Delta x - \sum _ { n = j - 2 } ^ { j + 3 } \frac { ( B _ { y } ) _ { i - 3 , n - 1 } + ( B _ { y } ) _ { i - 3 , n } } { 2 } \Delta y ) } \end{array}
$$

其中， $\mathrm { d } \mathrm { s } { = } 6 \Delta \mathrm { x } { * } 6 \Delta \mathrm { y }$ 。

# 2结果

图3是分别运用安培定律的微分法和环路积分法所计算出的耀斑爆发期间（02:00:00 UT）

的视向电流密度分布图。图中用“Dif”表示差分法，用“Int”表示积分法，“1C”表示小环路，“2C”表示中环路，“3C”表示大环路。图中白色和黑色分别表示正负电流密度分布，对应的视向电流密度值分别为 $+ 0 . 0 5 \mathrm { A } \cdot \mathrm { m } ^ { - 2 }$ 和 $- 0 . 0 5 \mathrm { ~ A ~ } \cdot \mathrm { m } ^ { - 2 }$ 。为了便于比较和分析，我们在微分法和积分法中所取的视向电流密度阈值相同，均为 $\pm 0 . 0 5 \mathrm { \textrm { A } } \cdot \mathrm { m } ^ { - 2 }$ 。图3（a)，（b）分别是运用安培定律的微分法和积分法（小环路）计算的视向电流密度分布图，图3（c)，(d）是扩大积分环路时计算的视向电流密度分布图。其中（c）为中环路的计算结果，（d)为大环路的计算结果，由于所测矢量磁图中的横向磁场不可避免地受随机噪声的影响，微分法计算的电流密度分布（如图3（a)）受噪声信号影响较大，相比之下，小环路的积分法（如图3（b)）计算的电流密度分布受随机噪声的影响相对较小。当把积分环路扩大到两个（中环路，如图3（c)）时，得到的电流密度分布图比小环路积分法计算的噪声信号更小。当把积分环路扩大到三个（大环路，如图3（d)）时，虽然计算的噪声信号更小，但电流密度分布中的部分精细结构明显失真。因此，在考虑随机噪声的情况下，我们选择扩大积分环路的方法，并将积分环路扩大到两个，即利用中环路的积分方法计算视向电流密度更好。

![](images/f3bd4579bb0a79bb2aa646ee2482158ce3efe8a1e9f90267b886ed362d287537.jpg)  
图3安培定律的微分算法和积分算法所计算出的视向电流密度分布图，

Fig.3 The distribution of vertical current density calculated by using the differential algorithm and integral algorithm of Ampere’s law.

由图3（c）和图1（a）可以看出，强电流主要产生于磁中性线附近的强磁场区域，与强磁场有很好的对应关系。由图1（a)，（c）和（d）可以看出，耀斑带可能出现在磁中性线附近的区域，由此说明，电流带与耀斑带在位置上可能具有某种对应关系。如图4，我们通过做投影改正将中环路积分法（如图3（c)）计算的视向电流密度分布与相同耀斑时刻的$1 7 0 \mathrm { n m }$ 波段和 $3 0 . 4 \mathrm { n m }$ 波段的单色像图(图1(c)和（d）)对齐，图中绿色和蓝色等高线分别表示正负电流带,对应的视向电流密度分别为 $+ 0 . 0 2 \mathrm { ~ A ~ } \cdot \mathrm { m } ^ { - 2 }$ 和 $- 0 . 0 2 \mathrm { ~ A ~ } \cdot \mathrm { m } ^ { - 2 }$ 。结果显示，耀斑带大致出现在电流较强的位置，此处的自由磁能多，释放的能量也多，而且耀斑带与电流带具有相似的形态。

![](images/ef0c16d319bea7536839d72e2e9bf269a8eed50b16013a75a73f758b827cad02.jpg)  
图4电流带与耀斑带的对应关系，左图为AIA170mm波段在2011年2月15日01:58:08UT时刻活动区的单色像图，右图为AIA30.4nm波段在2011年2月15日01:58:12UT时刻活动区的单色像图，图中的绿色等高线和蓝色等高线分别表示正极和负极电流带，对应的视向电流密度值分别为 $+ 0 . 0 2 \mathrm { ~ A ~ } { \cdot } \mathrm { ~ m } ^ { - 2 }$ 和 $- 0 . 0 2 \mathrm { ~ A ~ } \cdot \mathrm { m } ^ { - 2 }$ 。

Fig.4 The corresponding relationship between the current ribbons and flare ribbons.The left panel is the 1700A imageof theactive region observedat O1:58:08UTon February15,2011and the right panelis the 304A image of the active region observed at O1:58:12UT on February 15,2011.The green and blue contour lines in the panels represent the positive and negative current values respectively,and the corresponding vertical electric current density values are $+ 0 . 0 2 \mathrm { ~ } \mathrm { A } \cdot \mathrm { m } ^ { - 2 } \mathrm { a n d } \mathrm { ~ } - 0 . 0 2 \mathrm { ~ } \mathrm { A } \cdot \mathrm { m } ^ { - 2 }$ respectively.

# 3讨论与结论

太阳耀斑究竟在什么位置爆发？其形态是什么样的？如何寻找一种有效预测太阳耀斑爆发位置和形态的方法一直是太阳物理中的一个前沿课题。耀斑爆发与活动区电流有着密切的联系，活动区的电流主要表现为由矢量磁图中横向磁场的变化产生的视向电流。因此，选择一种有效计算活动区视向电流的方法显得尤为重要。在不考虑随机噪声的情况下，随着空间分辨率的提高，利用安培定律的微分形式和积分形式计算的视向电流密度都比较接近。在考虑随机噪声的情况下，利用安培定律的微分形式计算视向电流密度，虽然计算量小，但随着空间分辨率的提高（空间格点宽度 $\Delta x$ 和 $\Delta .$ y变小)，由随机误差引起的电流密度的离散度变大，计算的视向电流密度的不确定性也在增加[42。即使将视向电流密度分布图进行平滑处理，在消除噪声信号的同时也会把原来噪声信号覆盖下的电流信号消除。而运用安培定律的积分形式计算视向电流密度，虽然比微分形式计算量大，但可以降低测量值的离散度，使计算结果受随机误差的影响变小，若扩大积分环路，矢量磁场的空间分辨率降低（空间格点宽度$\Delta \mathrm { x }$ 和 $\Delta \mathrm { y }$ 变大)，可以快速降低测量值的离散度，使所得结果更准确。运用安培定律积分形式计算视向电流密度的方差比微分形式计算的电流密度的方差更小[43]。当积分路径超过所研究矢量磁图的最小空间分辨率结构的线性大小时，所得电流密度分布的部分精细结构就会失真。基于高分辨率矢量磁图寻找一种合适的积分路径计算视向电流密度，能在去除噪声信号的同时保留原有的电流信号，所得结果更准确。

基于此理论，本文通过比较计算视向电流密度的几种方法，即安培定律的微分算法、小环路积分法、中环路积分法和大环路积分法（如图3)，最终得出这样的结论：在考虑随机噪声的情况下，选择安培定律的积分算法，并将积分环路扩大到第二个环路积分时计算的视向电流密度分布图更清晰，而且电流精细结构不失真。由图4可以看出，耀斑带与电流带的爆发位置和形态极其相似，所以，计算的视向电流密度分布对于准确预测耀斑爆发的位置和形态具有非常重要的意义。为了从理论上分析积分路径是否合适，模拟时可以在矢量磁场中设定一个电流密度的真实值，但本文中的数据是通过空间采样所获得的观测数据，由于受随机噪声的影响无法确定电流密度的真实值，所以文中是用实际观测的数据验证[24]模拟方法的准确性，即用扩大积分环路（本文中为中环路）的方法得到的电流密度分布图效果最好。同时我们可以利用所计算的视向电流密度分布预测耀斑爆发的可能位置和形态，也验证了计算视向电流密度的方法的有效性和可靠性。未来我们将利用AIA其它波段的观测数据对多个活动区的耀斑带和电流带进行研究，以检验该方法的合理性和普适性。

考文献：   
[1]GoslingJT,Mccomas DJ,PhilipsJL,etal.Geomagneticactivityassociatedwitharthpassageof interplanearyock disturbances and coronal mass ejections[J]. Journal of Geophysical Research Space Physics,1991,96(A5).   
[2] Zirin,H,Wang. Narrow lanes of transverse magnetic field in sunspots[J]. Nature,1993.   
[3] Yan XL,QuZQ.Rapidrotationofasunspot assciated withflares[J].Astronomy&Astrophysics2,468(3):108-1088.   
[4]YanXL,QuZQ,KongDF.RelationshipbetweenrotatingsunspotsandflareproductivityJ].MonthlyNoticesoftheRoyal Astronomical Society,2010,391(4):1887-1892.   
[5]MeunierN,KosovichevA.Fastphotosphericflows and magneticfields inaflaring activeregion[J].Astronomy& Astrophysics, 2003,412(2):541-553.   
[6]YangSH,ZhangJ,ZhuXS,etal.Block-inducedcomplexstructuresbuilding theflare-productivesolaractiveregion673.The Astrophysical Journal Letters,2017,849: L21(7pp)   
[7]YanXL,WangJC,PanGM,etal.Succesive X-class Flaresand Coronal Mass Ejections DrivenbyShearingMotionand Sunspot Rotation in Active Region NOAA 12673[J].The Astrophysical Journal,2018,856(1):79.   
[8]SharykinIN,KosovichevAG.OnsetofPhotospheric Impactsand Helioseismic Waves in X9.3 SolarFlareofSeptember6, 2017[J]. The Astrophysical Journal,2018,864(1).   
[9]MasudaS,KosugiT,HaraH,etal.Alo-topardX-aourceiompactsolarfareasvidencefoagneticecoctio[J]. Nature,1994,371(6497):495-497.   
[10] 周团辉，季海生，王俊锋．太阳耀斑环的收缩和剪切[J].天文研究与技术,2012(04):357-362. Zhou Tuanhui,Ji Haisheng,Wang Junfeng. Contractionand Shearing of Solar Flare Rings[J]. Astronomical Research and Technology,2012(04):357-362.   
[11]林元章.太阳物理导论[M].北京：科学出版社， 2000. Lin Yuanzhang. Introduction to Solar Physics[M]. Beijing: Science Press,2000.   
[12] Sakurai T, Magnetic field structures and flares[J]. 1993,13(9):109-117.   
[13]Sun X, Hoeksema JT,Liu Y,et al. ERRATUM: "EVOLUTION OF MAGNETIC FIELD AND ENERGY IN A MAJOR ERUPTIVE ACTIVE REGION BASED ON SDO /HMI OBSERVATION"(2012,APJ,748,77)[J]. The Astrophysical Jourmal, 2016, 828(1):65.   
[14] 罗葆荣，侯叔明.AR6659光球色球的磁场速度场的演化特征及其与大耀斑的关系[J]．云南天文台台刊,1994. Luo Baorong,Hou Shuming.The evolution characteristics ofthe magnetic field velocity fieldof AR6659 photosphere chromosphere and its relationship with large flares[J].Journal of the Yunnan Observatory,1994.   
[15]WangHwell,Z,etalVectorageticfelgesoiatedwith-csfaes[J].strosicalJoual994, 424(1).   
[16]RavindraB,VenkatakrishnanP,Tiwari SK,etal.EvolutionofCurrentsofOppositeSignsinteFareProductiveSolarActive Region NOAA 10930[J]. Astrophysical Jourmal,2011,740(1):1441-1458.   
[17]T.Torok,J.E.Leake,V.S.Titov,et al. DISTRIBUTION OFELECTRICCURRENTS INSOLAR ACTIVE REGIONS[J].The Astrophysical Journal,2014.   
[18]JanvierM,ulanierG,ommierV,eal.Electricuetsinfarebbons:Obervatiosndthree-dimensioalstadard model[J]. Astrophysical Journal,2014,788(1):60.   
[19]HagyardMJObserednonpotentialagneticfeldsdthiferrdflowofelectriccurrentsatalocatioofrepeatedfaring[J] Solar Physics,1988,115(1):107-124.   
[20]林元章,Gaizauskas V.太阳耀斑核块中的电流[J].中国科学(a辑 数学 物理学 天文学 技术科学),1987,30(11):1184-190. Lin Yuanzhang,Gaizauskas V.Electric currentinthe solarflare nuclei[J]. Science of China (Series A Mathematics Physics Astronomy Technical Science),1987,30 (11):1184-1190.   
[21]WilkisoLKslieGrGeraledurtsineolarooa[J].estrocaloal9().   
[22]Wiegelmann,Thomasakuraiakashi.SolarForce-freeagneticFields[J].LivingReviewsinSolarPhysics,,9(1):5.   
[23]Klimchuk,JA,Cafield,R.,hoads,JE.,TheracticalApcatiooftheagneticVirialeoremJ].TheAstroical Journal,1992,385,327.   
[24]Liang HF,MaL,ZhaoHJ,etal.Electriccurent densitycalculationanderoranalysisofsolaractiveregions[J].New Astronomy,2009,14(3):294-301.   
[25]PesnellWD,ThompsonBJ,ChamberlinPC.TheSolarDynamicsObservatory[J].SolarPhysics,2l2,275(-):3-15   
[26]SchouJ,ScherrerPH,AkinDJ,etal.DesignandGroundCalibrationoftheHelioseismicandMagnetic Imager(HMI) Instrument on the Solar Dynamics Observatory (SDO)[J]. Solar Physics,2012,275(1-2):229-259.   
[27]James R.Lemen,AlanM.Title,David J. Akin,et al.The Atmospheric Imaging Assembly(AIA)on the SolarDynamics Observatory (SDO)[J].Solar Physics,2012.   
[28]CHHAB,CHWA,CYYA,etal.Chiralityandmagneticconfigurationassociatedwithtworibbonsolarflares:A0930 versus AR11158[J].Advances in Space Research,2020,65(12):2828-2845.   
[29]PetrieGJD.Aspati-temporaldescriptionoftheabruptchangesinthephotospheric magneticandLorentz-force vectors during the2011February15X2.2 flare[J].Solar Physics,2013,287(1-2):41-440   
[30] Sebastien Couvidat,SchouJ,ShineRA,etal. Wavelength Dependenceof the Helioseismicand Magnetic Imager (HMI) Instrument onboard theSolarDynamicsObservatory (SDO)[J].Solar Physics,2012,275(1-2):p.285-325.   
[31]BorreroJM,TomczykS,KuboM,etal.VFV:VeryFastInversionoftheStokesVectorfortheHelioseismicandagetic Imager[J]. SolarPhysics,2011,273(1):267-293.   
[32] Sakurai T,Makita M,ShibasakiK.Observationof magneticfield vectorinsolaractiveregions.MPARp,1985,26:24   
[33]KrallKR,SithJJB,HagyardMJ,etal.Vectormagneticfieldevolutioneergystorageandasociatedphotosphericeloity shear withina flare-productive active region [J] Solar Physics,1982,79: 59   
[34]王华宁，林元章．确定太阳横向磁场方位角的综合方法[J].天体物理学报,1994,014(002):196-196. Wang Huaning,Lin Yuanzhang.AComprehensive Method for Determiningthe Azimuth of the Sun’s Transverse Magnetic Field[J]. Chinese Journal of Astrophysical Sciences,1994,014(002):196-196.   
[35]MetcalfTR.Resolvingthe18O-degreeambiguityinvectormagneticfield measurements: The'minimum'energysolution[J]. 1994, 155(2):235-242.   
[36]GaryGA,ooreRLagyardJetal.NonpotentialfeaturesoservedinthemagneticfieldfanactieregionJ].A1987.   
[37]AlyJ,omepropertiesofthesolutionsofanon-linearboundaryvalueproblemforaforce-freefieldinaninfinitegionof space.I- Energy estimates[J].Astronomy & Astrophysics,1988,203:183-188.   
[38]LemenJR,TitleAM,AkinDJ,etal.TheAtmosphericImaging Asembly(AIA)onthSolarDynamicsObservatory(O)[J]   
[39]Ciaravell,RaymondJC,LiJ,etal.ElementalAbundanceandPost-CoronalMassEjectionCurrentSeeinVerHot Active Region[J]. Astrophysical Journal,2002,575(2):116.   
[40]Savage SL,MckenzieDE,Reeves K K,etal.RECONNECTIONOUTFLOWSANDCURRENT SHEETOBSERVED WITH HINODE/XRTIN THE 2008 APRIL9 "CARTWHEEL CME"FLARE[J].Astrophysical Jourmal,2010,722(1):329-342.   
[41]YanXL,YangLH,XueZK,etal.SimultaneousObservationofaFluxRopeEruptionandMagneticReconnectionduringan X-class SolarFlare[J]. The Astrophysical Journal,2018,853(1): L18.   
[42] K.D,LekaA,Skumanich. On the value of αAR' from vector magnetograph data[J]. Solar Physics,1999.   
[43]梁红飞．太阳黑子矢量磁场的测量及视向电流密度的计算[D].中国科学院研究生院（云南天文台）,2006. Liang Hongfei.Measurementof vectormagneticfieldandcalculationof electriccurrntdensityofthesunspot [D]. Graduate School of Chinese Academy of Sciences (Yunnan Observatory),2006.

# The Calculation of Vertical Electric Current Density Associated with An X2.2 Flare in Active

# Region AR11158

Yang Liping'’²，Liang Hongfei²,Liu Jihong³,Wang Nan²， Sun Xia2，Li Zihan2 (1.Schoolofphysicsandelectroicinformation,YunanNormalUniversity,Kunming6o5oo,Yunnan;2.KeyLaboratoryofHigh EnergyAstropsicsofUniversityofYunnanProvince,Kunming6oo,Yunnan;3YunnanObservatory,ChieseAcademyofieces, Kunming 65O16,unan;4cholofechanicalandElectricalEngieing,ijazuangClge,ShijaangOo,Hbei)

Abstract: The explosion of energic solar activity is closely related to the current structure in the active region, Ampere's law $\scriptstyle j _ { z } = { \frac { 1 } { \mu } } ( \nabla \times { \pmb B } ) _ { z }$ is the theoretical basis for measuring the current density in the active region.Due to the random noise inevitably exist in the measured vector magnetic field,so the current density calculated by using the different form of Ampere's law will be significantly different. In order to compare the differences between the calculated results of different form and explore one of the most practical current calculation methods,this article is based on the vector magnetogram in activity region AR1158 which measured by SDO (Solar Dynamic Observatory)/HMI (Helioseismic and Magnetic Imager） on February 15，2011. Calculating the distribution of the vertical electric current density in the active region by using differential algorithm and integral algorithm of Ampere's law. The results demonstrate that the distribution of vertical electric current density $j _ { z }$ which obtained by the differential algorithm is much more affected by random noise than the result obtained by the integral algorithm, the current structures in the current distribution diagram obtained by the integral algorithm is much clearer than the former.In addition,the noise signal of the calculated current distribution map will decrease sharply,as enlarging the radius of the integral loop,the current structure in the obtained current distribution map willbecome clear. However, when the radius of the integral loop continue to expand, part of the fine structures of the current distribution map will also be distorted when obtaining a clear current distribution diagram. The result of this study demonstrates that the map of current distribution which calculated by expanding the integral loop properly can reduce the effect on calculation results from random noise,and obtaining a clear and true vertical electric current distribution map. Though the noise is eliminated if the radius of the integral path is too large,some fine structures in the current distribution will be lost. Therefore,during the course of actual calculating electric current. We should use high-resolution vector magnetogram and use the integral algorithm of Ampere's law to calculate the vertical electric current in the active region by selectingan appropriate integration path, which can help us to explore the relationship between the eruptive flares and the structures of current in the active region.

Keywords: active region; flare; vector magnetic field; electric current density; Ampere's law