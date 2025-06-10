# 基于CAPS、BDS和GPS的组合卫星定位精度分析

傅圣友²，李圣明²，王兆瑞²(1．中国科学院大学天文与空间科学学院，北京100049)(2．中国科学院国家天文台，北京100101)

摘要：随着GPS、GLONASS、Galileo和BDS等全球卫星定位系统的建设和完善，同时采用两个或两个以上定位系统信号进行多系统组合定位成为导航领域研究的热点。相比传统的单系统定位，多系统组合具有更好的定位、测速、授时性能以及更强的环境适应性。通过CAPS、BDS和GPS三个系统的静态单点联合定位解算，实现了转发式定位系统与直发式定位系统的联合定位，验证了中国区域定位系统参与多系统GNSS定位的可行性，并分析了组合定位的性能与定位精度。分析表明，中国区域定位系统参与多系统联合定位解算是完全可行的，单点定位精度优于 $3 \mathrm { m }$ ，且还有提高的空间。中国区域定位系统的加入，丰富了GNSS系统的选择，对提高GNSS联合定位的多样性、改善联合定位性能具有研究意义及应用价值。

关键词：全球导航卫星系统；中国区域定位系统；组合定位中图分类号：P228.1文献标识码：A 文章编号:1672-7673(2018)

全球导航卫星系统（Global Navigation Satellite System,GNSS)经过几十年的飞速发展，美国的全球定位系统（GlobalPosiring System，GPS）、俄罗斯的GLONASS、中国的北斗卫星导航系统（BeiDou NavigtinSatelie System，BDs）、欧洲的伽利略（Galileo）均已建成并投入使用。在亚太区域内，全球定位系统单点定位精度大约为 $6 { \cdot } 1 0 \mathrm { m }$ ，北斗卫星导航系统由于可见卫星数量较多且卫星高度角更高，单点定位结果略优于全球定位系统，精度大约为 $4 { \cdot } 8 \mathrm { m } ^ { [ 1 ] }$ 。

为了能够得到比单系统单点定位更高的定位精度，采用多个导航系统的信号实现联合定位导航是现今导航接收机的一种发展趋势。相比单一导航系统的定位，多系统联合定位可用的卫星数量显著增多，可以通过星座优化选择几何布局更佳、信号强度更好的卫星实现组合定位解算，能有效提高定位的连续性、准确性和稳定性。

中国区域定位系统（Chinese Area Positioning System,CAPS）是中国科学院发明的转发式卫星导航定位系统，是中国二代卫星导航系统的重要组成部分。系统利用现有的C频段通信卫星组建导航星座，并建立了一套与导航相关的地面设施。由地面导航主控站的原子钟提供精确的时间基准，并生成导航电文和测距码，上行至通信卫星。通信卫星上的信号转发器转发导航主控站生成的导航信号，向系统覆盖区域内的用户接收机播发导航信号，使接收机能实时测量、解算，从而获得用户接收终端的位置、速度和时间信息。为卫星定位方法的研究提供了新的思路和实验平台[2]。

本文开展了转发式卫星导航试验系统CAPS与BDS、GPS的组合定位解算，采用分立的BDS/GPS和转发式CAPS导航接收机分别采集各系统的导航电文和码伪距观测量。通过对三系统卫星的优选构成导航星座，并消除系统间钟差，然后进行组合定位解算。最后通过统计，获得了有CAPS信号参与定位情况下的组合定位精度，并与BDS/GPS双系统接收机定位结果进行了分析比较。

# 1联合定位方法

BDS、GPS 和CAPS 三系统联合定位原理图如图1，三系统的导航卫星共同组成空间GNSS 星座。由专用的GNSS接收机平台接收三个系统全部可见卫星的导航电文，测量码伪距，并将原始定位数据保存到计算机。最后在计算机中进行离线数据处理，采用最小二乘法进行位置解算。得到联合定位结果，实现三系统联合卫星定位，并对定位精度进行分析。

![](images/4ba447f24ff725cafc224c02e634d517cd8fbe0d714a4a2b735c48dde80efcfd.jpg)  
图1三系统卫星定位原理图  
Fig.1Positioning schematic of three systems

在联合定位解算时,CAPS系统是对传统卫星定位系统GPS和BDS的补充和增强。CAPS系统由于其转发式定位的特色，使用通信卫星实现定位。因此可以为多系统联合定位提供卫星数量、卫星空间布局、灵活性和抗干扰等方面的优势。CAPS系统的加入，可以增加卫星星座的有效卫星数量，优化星座的空间布局，减小位置精度因子值。此外，CAPS 系统导航信号采用码速率为10.23Mcps 的测距码，相比于GPS 粗码1.023Mcps 和 BDS 的 2.046Mcps码速率，CAPS 更高的码速率可以得到更精确的伪距测量值。而且CAPS 的系统时间统一由地面站高精度原子钟提供，没有卫星间的钟差，也能提高定位精度。

# 1.1观测方程及线性化

令卫星 $k$ 和接收机i之间的几何距离为 $\rho _ { i } ^ { k }$ ， $c$ 表示光速， $\scriptstyle d t ^ { k }$ 表示卫星 $k$ 的时间相对其系统时之间的时钟偏差， $d t _ { i }$ 表示接收机时钟偏差， $e _ { i } ^ { k }$ 表示伪距的测量误差，包括电离层延迟、对流层延迟、测量噪声等， $d t _ { S }$ 表示系统间钟差，包括 $d t _ { B }$ 或 $d t _ { C }$ ，分别为系统时BDT和CAPST相对于GPST的时间差。则伪距 $L _ { i } ^ { k }$ 的基本观测方程为：

$$
L _ { i } ^ { k } = \rho _ { i } ^ { k } + c ( d t _ { i } - d t _ { S } - d t ^ { k } ) + e _ { i } ^ { k } ,
$$

其中，卫星和接收机之间的几何距离 $\rho _ { i } ^ { k }$ 可由下式计算：

$$
\rho _ { i } ^ { k } = \sqrt { ( X ^ { k } - X _ { i } ) ^ { 2 } + ( Y ^ { k } - Y _ { i } ) ^ { 2 } + ( Z ^ { k } - Z _ { i } ) ^ { 2 } } ,
$$

代入基本观测方程(1)中，得到：

$$
L _ { i } ^ { k } = \sqrt { ( X ^ { k } - X _ { i } ) ^ { 2 } + ( Y ^ { k } - Y _ { i } ) ^ { 2 } + ( Z ^ { k } - Z _ { i } ) ^ { 2 } } + c ( d t _ { i } - d t _ { S } - d t ^ { k } ) + e _ { i } ^ { k } ,
$$

其中，卫星位置 $( X ^ { k } , Y ^ { k } , Z ^ { k } )$ 及卫星时钟偏差 $d t ^ { k }$ 可由卫星星历获得[3-5]。

解算时，对于BDS 和CAPS系统，将接收机钟差与系统钟差合并解算，即共有6个未知数 $X _ { i } , Y _ { i } , Z _ { i } , d t _ { i } , ( d t _ { i } - d t _ { B } )$ 和 $( d t _ { i } - d t _ { C } )$ 。当组合系统接收到信号的卫星数不小于系统数加3时（即单系统至少4颗卫星，双系统至少5颗卫星，三系统至少6颗卫星)，就可实现组合定位[]。

(3)式对于接收机位置 $( X _ { i } , Y _ { i } , Z _ { i } )$ 是非线性的，所以在使用最小二乘法之前，此方程必须线性化。式中非线性部分如下：

$$
f ( X _ { i } , Y _ { i } , Z _ { i } ) = \sqrt { ( X ^ { k } - X _ { i } ) ^ { 2 } + ( Y ^ { k } - Y _ { i } ) ^ { 2 } + ( Z ^ { k } - Z _ { i } ) ^ { 2 } } ,
$$

需要选择一个接收机的初始位置 $\left( { { X } _ { i , 0 } } , { { Y } _ { i , 0 } } , { { Z } _ { i , 0 } } \right)$ 开始线性化，此处选择初始位置为地心(0,0,0)。定义增量 $\Delta X , \Delta \Upsilon , \Delta \mathrm { Z }$ 如下，用于更新近似的接收机坐标， $p$ 为迭代计算次数，每次迭代计算均以前一次计算更新后的位置作为本次计算的初始位置：

$$
\begin{array} { r c l } { { } } & { { } } & { { X _ { i , p + 1 } = X _ { i , p } + \Delta X _ { i } } } \\ { { } } & { { } } & { { Y _ { i , p + 1 } = Y _ { i , p } + \Delta Y _ { i } p = 0 , 1 , 2 \cdots , } } \\ { { } } & { { } } & { { Z _ { i , p + 1 } = Z _ { i , p } + \Delta Z _ { i } } } \end{array}
$$

将(4)式在每次迭代计算的初始位置 $\left( { { X } _ { i , p } } , { { Y } _ { i , p } } , { { Z } _ { i , p } } \right)$ 处泰勒展开，得到：

$$
\begin{array} { r } { f \big ( X _ { i , p + 1 } , Y _ { i , p + 1 } , Z _ { i , p + 1 } \big ) = f \big ( X _ { i , p } , Y _ { i , p } , Z _ { i , p } \big ) + \frac { \partial f \big ( X _ { i , p } , Y _ { i , p } , Z _ { i , p } \big ) } { \partial X _ { i , p } } \Delta X _ { i } + \frac { \partial f \big ( X _ { i , p } , Y _ { i , p } , Z _ { i , p } \big ) } { \partial Y _ { i , p } } \Delta Y _ { i } } \\ { + \frac { \partial f \big ( X _ { i , p } , Y _ { i , p } , Z _ { i , p } \big ) } { \partial Y _ { i , p } } \Delta Z _ { i } , ( \Delta Y _ { i } , Y _ { i } , Z _ { i , p } \big ) \Delta Z _ { i } , } \end{array}
$$

其中，偏导数为

$$
\begin{array} { r } { \frac { \partial f \left( { X } _ { i , p } , { Y } _ { i , p } , { Z } _ { i , p } \right) } { \partial { X } _ { i , p } } = - \frac { X ^ { k } - { X } _ { i , p } } { \rho _ { i } ^ { k } } } \\ { \frac { \partial f \left( { X } _ { i , p } , { Y } _ { i , p } , { Z } _ { i , p } \right) } { \partial { Y } _ { i , p } } = - \frac { Y ^ { k } - { Y } _ { i , p } } { \rho _ { i } ^ { k } } ( } \\ { \frac { \partial f \left( { X } _ { i , p } , { Y } _ { i , p } , { Z } _ { i , p } \right) } { \partial { Z } _ { i , p } } = - \frac { Z ^ { k } - { Z } _ { i , p } } { \rho _ { i } ^ { k } } } \end{array}
$$

至此，(3)式变为一阶线性观测方程：

$$
L _ { i } ^ { k } = \rho _ { i , p } ^ { k } - \frac { X ^ { k } - X _ { i , p } } { \rho _ { i , p } ^ { k } } \Delta X _ { i } - \frac { Y ^ { k } - Y _ { i , p } } { \rho _ { i , p } ^ { k } } \Delta Y _ { i } - \frac { Z ^ { k } - Z _ { i , p } } { \rho _ { i , p } ^ { k } } \Delta Z _ { i } + c ( d t _ { i } - d t _ { s } - d t ^ { k } ) + e _ { i } ^ { k } ( 8 )
$$

其中， $\rho _ { i , p } ^ { k }$ 为由接收机近似位置解算的距离：

$$
\rho _ { i , p } ^ { k } = \sqrt { ( X ^ { k } { - } X _ { i , p } ) ^ { 2 } + ( Y ^ { k } { - } Y _ { i , p } ) ^ { 2 } + ( Z ^ { k } { - } Z _ { i , p } ) ^ { 2 } } \quad \ .
$$

# 1.2最小二乘法

最小二乘法通常用于解决线性方程组中方程数大于未知数时，方程无解的情况[3]。对于一个无解的方程 $\pmb { A } \pmb { x } = \pmb { b }$ ，其中A有 $\textmu m$ 行 $n$ 列， $m > n$ 。即方程中观测值 $b _ { 1 } , \cdots , b _ { m }$ 的个数大于参数 $\cdot x _ { 1 } , \cdots , x _ { n }$ 的个数。此方程误差向量为 $\widehat { \pmb { e } } = \pmb { b } - \pmb { A } \widehat { \pmb { x } }$ ，其平方值 $\| e \| ^ { 2 } = ( b - A x ) ^ { \mathrm { T } } ( b - A x )$ 是 $m$ 个分立误差的平方和，为得到使误差向量长度最小的最优解 $\widehat { \pmb { x } }$ ，最小化该二次方程得到：

$$
\begin{array} { r } { \pmb { A } ^ { \mathrm { T } } \pmb { A } \pmb { \widehat { x } } = \pmb { A } ^ { \mathrm { T } } \pmb { b } \oiiint \pmb { \operatorname { \widehat { x } } } \pmb { \operatorname { \widehat { x } } } = ( \pmb { A } ^ { \mathrm { T } } \pmb { A } ) ^ { - 1 } \pmb { A } ^ { \mathrm { T } } \pmb { b } \ \mathrm { ~ . ~ } } \end{array}
$$

于是，(8)式可重新写为矢量形式，即

$$
L _ { i } ^ { k } = \rho _ { i , p } ^ { k } + \left[ - \frac { X ^ { k } - X _ { i , p } } { \rho _ { i , p } ^ { k } } \quad - \frac { Y ^ { k } - Y _ { i , p } } { \rho _ { i , p } ^ { k } } \quad - \frac { Z ^ { k } - Z _ { i , p } } { \rho _ { i , p } ^ { k } } \quad 1 \right] \left[ \begin{array} { c } { \Delta X _ { i } } \\ { \Delta Y _ { i } } \\ { \Delta Z _ { i } } \\ { \qquad \mathstrut } \end{array} \right] - c d t ^ { k } + e _ { i } ^ { k } .
$$

再将其整理成最小二乘问题 $\pmb { A } \pmb { x } = \pmb { b }$ 的常规表达式，即

$$
[ - \frac { X ^ { k } - X _ { i , p } } { \rho _ { i , p } ^ { k } }   - \frac { Y ^ { k } - Y _ { i , p } } { \rho _ { i , p } ^ { k } }   - \frac { Z ^ { k } - Z _ { i , p } } { \rho _ { i , p } ^ { k } }  1 ] X _ { k } = L _ { i } ^ { k } - \rho _ { i , p } ^ { k } + c d t ^ { k } - e _ { i } ^ { k } .
$$

从以上单一方程中得不到唯一解，故令 $b _ { i } ^ { k } = L _ { i } ^ { k } - \rho _ { i , p } ^ { k } + c d t ^ { k } - e _ { i } ^ { k }$ ，联立观测的各导航系统卫星方程组成方程组，则最终解可由(13)式获得，其中系数矩阵 $\pmb { A }$ 的前 $m$ 行对应为GPS卫星，$( X ^ { G } , Y ^ { G } , Z ^ { G } )$ 为GPS卫星坐标；中间 $n$ 行对应为BDS卫星， $( X ^ { B } , Y ^ { B } , Z ^ { B } )$ 为BDS卫星坐标；最后l行对应CAPS卫星， $( X ^ { C } , Y ^ { C } , Z ^ { C } )$ 为CAPS卫星坐标。

$$
\Delta x = [ \begin{array} { c c c c c c c } { - \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Y ^ { ( a ) } - Y _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Z ^ { ( a ) } - Z _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { 1 } & { 0 } & { 0 } \\ { - \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Y ^ { ( a ) } - Y _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Z ^ { ( a ) } - Z _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { 1 } & { 1 } & { 0 } \\ { - \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Y ^ { ( a ) } - Y _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Z ^ { ( a ) } - Z _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { 1 } & { 0 } & { 0 } \\ { - \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Y ^ { ( a ) } - Y _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Z ^ { ( a ) } - Z _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { 1 } & { 0 } & { 0 } \\ { \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Y ^ { ( a ) } - Y _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Z ^ { ( a ) } - Z _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { 1 } & { \frac { X ^ { ( a ) } } { \rho _ { i j } ^ { ( a ) } } } & { - \frac { Y ^ { ( a ) } } { \rho _ { i j } ^ { ( a ) } } } & { 0 } & { 1 } \\ { - \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } &  - \frac { Y ^ { ( a ) } - Y _ { i j } } { \rho _ { i j } ^ { ( a ) } } & { - \frac { Z ^ { ( a ) } - Z _ { i j } } { \rho _ { i j } ^ { ( a ) } } } & { 0 } & { 1 } & { 0 } \\ { - \frac { X ^ { ( a ) } - X _ { i j } } { \rho _ { i j } ^ { ( a ) } } } &  - \frac { Y ^ { ( a ) } - Y _ { i j } }  \rho _ { i j }  \end{array}
$$

当 $m + n + l \ge 6$ 时，有唯一解： $\Delta X _ { i , p + 1 } , \Delta Y _ { i , p + 1 } , \Delta Z _ { i , p + 1 }$ 。此解可以叠加到接收机的初始近似位置上，从而得到下一步更精确的近似位置：

$$
\begin{array} { r l } { X _ { i , p + 1 } = X _ { i , p } + \Delta X _ { i , p + 1 } } & { { } } \\ { Y _ { i , p + 1 } = Y _ { i , p } + \Delta Y _ { i , p + 1 } } & { { } \mathrm { . } } \\ { Z _ { i , p + 1 } = Z _ { i , p } + \Delta Z _ { i , p + 1 } } & { { } } \end{array}
$$

可以继续用 $X _ { i , p + 1 } , Y _ { i , p + 1 } , Z _ { i , p + 1 }$ 代替 $X _ { i , p } , Y _ { i , p } , Z _ { i , p }$ ，代入(13)式循环计算，直至 $q$ 次之后方程的解 $\cdot \Delta X _ { i , p + q } , \Delta Y _ { i , p + q } , \Delta Z _ { i , p + q }$ 达到期望的误差数量级， $\boldsymbol { q }$ 即为最小二乘迭代次数。通常，四到五次循环计算后便可符合目标。

# 2 试验方案及过程

# 2.1试验方案

基于BDS、GPS 和CAPS 的组合卫星定位试验采用静态单点定位方式。试验接收机安装在中国科学院国家天文台楼顶。由于CAPS系统工作在C频段，与其他两系统采用的L频段不同，为了改善信号接收性能，采用分立的接收天线靠近放置。导航射频信号转换到中频后，分别由CAPS 接收机和BDS/GPS 双系统单频接收机基带捕获跟踪解调，并实时同步记录三系统的卫星星历、伪距等原始定位数据，并存储到计算机。最后在计算机中采用MATLAB软件编程进行数据处理和联合定位解算，并分析试验结果，统计定位精度。定位试验系统框图如图2。

![](images/b26b02598581fd2985fb3188a5eaf8c230ff62f63c957d885a09afdb05ba1b1d.jpg)  
图2三系统卫星定位试验原理框图  
Fig.2 Schematic of combined positioning experiment

# 2.2试验过程

(1）在天文台楼顶放置一台BDS/GPS双系统定位接收机，进行 $4 8 \mathrm { ~ h ~ }$ 连续测量，取其定位解算结果数值作平均，获得静态定位参考点坐标值 $( x _ { 0 } , y _ { 0 } , z _ { 0 } )$ 为(-2173764.5307,4383137.0366, 4078283.8735)  
(2）在同一位置，分别用BDS/GPS 单频接收机和CAPS 接收机长期采集定位原始数据，包括全部可见GPS、BDS 和CAPS卫星的卫星星历、卫星钟差、电文修正信息、码伪距测量值等。  
(3）选取各系统同时段的卫星定位信息，由卫星星历计算每个历元的卫星位置坐标值，同时也采用三系统全部可观测到的卫星用最小二乘法进行定位解算。  
(4）处理定位结果数据，分析统计联合定位时定位结果的准确度和精度，与BDS/GPS双系统定位结果作对比，得出试验结论。

# 2.3数据统计方法

当设备处于正常工作状态，三系统均成功捕获跟踪信号后，连续记录 $n$ $( n > 1 0 0 0 )$ 个历元定位伪距测量数据及该期间的导航电文。对此 $n$ 个历元数据进行定位解算，得到每历元的定位解算结果。采用的计算步骤如下：

(1)对每个历元，计算各个方向的定位偏差及三维合成总误差：

$$
\left\{ \begin{array} { c } { \Delta x _ { i } = x _ { i } - x _ { 0 } } \\ { \Delta y _ { i } = y _ { i } - y _ { 0 } } \\ { \Delta z _ { i } = z _ { i } - z _ { 0 } } \\ { \Delta p _ { i } = \sqrt { { \Delta x _ { i } } ^ { 2 } + { \Delta y _ { i } } ^ { 2 } + { \Delta z _ { i } } ^ { 2 } } } \end{array} \right. i = 1 , 2 , \cdots , n
$$

其中:

$x _ { i } , y _ { i } , z _ { i }$ 为第 $i$ 个历元定位结果的三维坐标，单位为 $\mathrm { ~ m ~ }$ $x _ { 0 } , y _ { 0 } , z _ { 0 }$ 为静态定位参考点坐标，单位为 $\mathbf { m }$

(2)分别计算各个方向及三维合成总误差的误差平均值和误差标准差：

$$
{ \overline { { \Delta p } } } = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \Delta p _ { i } \qquad ,
$$

$$
S _ { \Delta p } = \sqrt { \frac { 1 } { n - 1 } \sum _ { i = 1 } ^ { n } ( \Delta p _ { i } - \overline { { \Delta p } } ) ^ { 2 } }
$$

其中：

$\overline { { \Delta p } }$ 为n个历元三维合成总误差的误差平均值，单位为 $\mathrm { ~ m ~ }$ $S _ { \Delta p }$ 为n个历元三维合成总误差的误差标准差，单位为 $\mathbf { m }$

# 3 试验结果

试验选取2017年9月11日18时19分至9月12日10时34分的测量数据，使用了全部可见的GPS、BDS 和CAPS卫星数据，每一时刻能同时接收到的卫星最少为16颗，CAPS系统所用卫星详情如表1。

表1CAPS系统用于本试验的卫星情况表  
Table 1Satellites of CAPS used in experiment   

<html><body><table><tr><td>卫星编号</td><td>卫星类型</td><td>卫星轨位</td></tr><tr><td>5</td><td>SIGSO</td><td>148E</td></tr><tr><td>6</td><td>GEO</td><td>110.5E</td></tr><tr><td>8</td><td>GEO</td><td>76.5°E</td></tr></table></body></html>

采用 MATLAB 编制CAPS/BDS/CAPS 多系统解算程序进行位置解算，解算结果画出平面散点图如图3。

![](images/8ecd5790a0f99d31013dc8b416fb062d9df764198f76b7db7cf47e56cdfde0f3.jpg)  
图3双系统/三系统定位解算误差平面散点图

双系统、三系统组合时，位置精度因子值情况如图4。

![](images/4388a934034e0809cde219f18b9a5907a4ed556fb13457c763d4c51ede692f3e.jpg)  
图4双系统/三系统定位解算卫星PDOP值变化图Fig.4PDOPvaluesofGPS/BDSandCAPS/GPS/BDS

定位精度统计结果见表2.

表2双系统/三系统系统定位精度统计表Table 2Positioning accuracy of $2 / 3$ systems  

<html><body><table><tr><td>定位系统</td><td>BDS+GPS</td><td>BDS+GPS+CAPS</td></tr><tr><td>水平定位精度/m</td><td>1.2534</td><td>1.1270</td></tr><tr><td>高程定位精度/m</td><td>1.6842</td><td>1.7603</td></tr><tr><td>三维定位精度/m</td><td>2.0994</td><td>2.0902</td></tr></table></body></html>

# 4结论

由以上结果可以看出，在静态单点定位情况下，CAPS 系统的加入，提供了更丰富的卫星选择，改善了空间卫星星座构成，减小了位置精度因子值。因此提高了定位精度，尤其是水平定位精度提高较为明显。在以后的研究中可以通过进一步精细消除误差或采用载波相位测量值参与解算，定位精度还有较大的提高空间。

# Analysis of combined positioning accuracy based on CAPS,

# BDS and GPS

Fu Shengyou1,²，LiShengming²，Wang Zhaorui² (1.Universityof Chinese Academy of Sciences，School of Astronomy and Space Science，Beijingl0049，China) (2．Chinese Academy of Sciences，National Astronomical Observatories of China，Beijingl0o0l2，China)

Abstract:Withconstructing and completingof global satellite positioning systems such as GPS,GLONASS, Galileo and BDS,using two or more than two signals ofdifferent positioning systems toachieve the combined positioning has become a hotspot in research of navigation.Compared with traditional single system positioning，multi-system combination has stronger environmental adaptability and beter performance of determining position, velocity and time.By combined static single point positioning of CAPS，BDS and GPS，we achieve the combined positioning of transponding system with straight forward system, verify the feasibility of CAPS participating in GNSS multi-system positioning， and analyze the positioning performance and accuracy.The analysis shows that CAPS are fully feasible in multi-system positioning，single point positioning accuracy is beter than 3 meters and there is room for improvement.The addition of CAPS enriches the selection of GNSS system,and has research significance and application value for improving the diversity of GNSS positioning and the positioning performance.

Key words: GNSS; CAPS; Combined positioning

# 参考文献

[1]陈立,王雷,谭周燚.BDS/GPS伪距单点定位的精度对比分析[J].现代导 航,2016,7(5):343-348.

Chen Li, Wang Lei, TanZhouyi. Precision simulation analysis of BDS/GPS pseudo-range single point positioning[J].Modern Navigation,2016,7(5):343-348.

[2]艾国祥,施浒立,吴海涛,等.基于通信卫星的定位系统原理[J].中国科学G辑：物理学力学天文学,2008(12):1615-1633.

AiGuoxiang,Shi Huli, WuHaitao, et al. The principle of the positioning system based on communication satellites[J]. Science in ChinaSeries G:Physics，Mechanics & Astron0my,2008(12):1615-1633.

[3]MisraP, EngeP. Global Positioning System:signals, measurements, and performance[M].Lincoln: Ganga-Jamuna Press,2006.

[4]魏恩岳．精密单点定位动态解的算法与实现[D].青岛：中国石油大学,2012.

[5]涂克楠.GPS精密单点定位数据处理[D].合肥：合肥工业大学,2009.

[6]马利华,韩延本,乔琪源．卫星静态定位中需要注意的问题[J].全球定位系统,2005,(4):12-14.

Ma Lihua, Han Yanben, QiaoQiyuan. Questions existing during satelites static positioning [J]. GNSS World of China,2005,(4):12-14.