# 基于神经网络的准实时单站电离层TEC反演

卢伟俊1,2，马冠－1,2

(1.中国科学院国家天文台，北京100101；2.中国科学院大学，北京100049)

摘要：使用全球导航卫星系统（GNSS）进行电离层总电子密度（TEC）反演时，单站相对于多站观测网是一种灵活简便的方法。基于人工神经网络，本文提出了一种准实时单站电离层TEC 反演的方法。在这种方法中，上一个时段的硬件偏差被作为初值并随着观测值调整，同时电离层TEC也被准实时地反演。为了对这种方法进行详细的评估，通过位于中国的单站，四天磁静日的TEC被分别采用提出的方法与经典的最小二乘球谐函数法反演，其中硬件偏差和TEC的参考值通过附近的多站网得到。在另一个测试中，通过位于欧洲的单站，一次电离层暴事件及前后平静日的TEC 也被分别通过上述方法反演。在磁静日，估计的硬件偏差在整体上相对于最小二乘球谐函数法更接近于参考值，反演的TEC也更接近于参考值。电离层暴时，两种方法反演的TEC也具有很好的一致性，神经网络法估计的硬件偏差与磁静日的硬件偏差更接近。结果表明，提出的神经网络法相比最小二乘球谐函数法具有较高的精度。

关键词：电离层；人工神经网络；总电子密度；硬件偏差；电离层暴中图分类号：P228.4 文献标识码：A 文章编号：DOI:

电离层是位于地面上约60-1000千米高度的大气区域，其中部分中性粒子被电离为自由电子和离子[1]。因此，电离层是一种色散介质并引起无线电信号的群延迟和相位超前，影响程度与信号频率及电离层电子密度有关。为了评估电离层对无线电信号传播的时延影响，一些描述电离层电子密度的理论模型或经验模型被提出[2J3]。理论模型虽然能反映电离层变化的物理机制，但在精度上还无法满足电离层延迟改正的要求。而经验模型和真实电离层之间也存在着无法忽视的偏差，只能改正部分电离层延迟。因此，通过真实观测对电离层进行建模已经成为一种必要的手段。一些观测仪器例如测高仪和非相干散射雷达已经被用于探测电离层的电子密度，然而这些仪器只能得到测站上空的电离层剖面而无法进行大规模的电离层观测。随着全球导航卫星系统（Global Navigation Satelite System，GNSS）的运行，电离层观测可以通过 GNSS多频无线电信号进行。由于GNSS 是基于倾斜轨道卫星星座连续运行的，不同的时空尺度的电离层变化都可以通过GNSS进行探测。

利用 GNSS，电离层电子密度的积分测量值即总电子含量（Total ElectronContent，TEC）被作为参数指标进行电离层反演。不同频率无线电信号通过卫星和接收机硬件通道时产生的硬件偏差作为系统误差必须被剔除，GNSS 多站观测网通常被设计用于电离层硬件偏差的估算和电离层参数的反演。尽管如此，单站电离层反演作为一种灵活简便而又低成本的方法仍然具有研究价值。单站电离层反演的算法主要有网格法、卡尔曼滤波法和多项式法[4]。多项式法中的多项式可以是二次多项式、三角级数或球谐函数[5]。一般来说二次多项式和三角级数只适合较小范围的反演，球谐函数通过改变阶数和次数能更好地描述电离层在不同空间尺度的变化。

对于电离层反演中的拟合方法，最小二乘和卡尔曼滤波通常会被采用。随着人工神经网络（ArtificialNeural Network，ANN）被提出，它很快就被用于进行电离层反演[]。一个基于误差反馈的前向传播神经网络能够以任意精度逼近一个连续的实函数。这种拟合是通过迭代的方式进行的，各参数对应的权值可以动态地调整。因此这种动态拟合适合于电离层的准实时反演。

基于人工神经网络，我们提出一种准实时的单站电离层反演方法。首先对电离层反演原理和提出的方法进行了推导。接下来利用位于北纬 $3 0 . 2 8 ^ { \circ }$ 东经 $1 0 9 . 4 6 ^ { \circ }$ 的单站在2014年春分、夏至、秋分和冬至的GNSS数据进行了实验，其中位于东经 $1 1 0 ^ { \circ }$ 子午线的18个站被作为验证站。在另一个实验中，2016年10月13日电离层暴事件的数据也被用于电离层反演，并且结果与前后磁静日的结果进行了比较。最后一部分是对文章的总结。

# 1电离层反演算法

# 1.1球谐函数拟合

GNSS卫星以两个不同的 $\mathrm { ~ L ~ }$ 波段频率播发信号，使用双频接收机，伪距和载波相位观测值可以被接收：

$$
P _ { i } = \rho + c ( \delta _ { t } - \delta _ { s } ) - I _ { i } + T + \varepsilon
$$

$$
\begin{array} { r } { \frac { c } { f _ { i } } L _ { i } = \rho + c ( \delta _ { t } - \delta _ { s } ) + I _ { i } + T + \frac { c } { f _ { i } } N _ { i } + \varepsilon } \end{array}
$$

其中 $i$ 为1或2分别对应 $f _ { 1 }$ 或 $f _ { 2 }$ 频率， $P _ { i }$ 和 $L _ { i }$ 分别对应 $f _ { i }$ 频率的伪距和载波相位观测值， $\rho$ 是卫星和接收机间的真实距离， $\boldsymbol { c }$ 表示光速； $\delta _ { t }$ 和 $\delta _ { s }$ 分别是接收机和卫星钟差，并对于伪距包含群延迟，对于载波相位包含相位超前； $I _ { i }$ 是对应 $f _ { i }$ 频率的电离层延迟， $T$ 是对流层延迟， $N _ { i }$ 为 $L _ { i }$ 的整周模糊度， $\varepsilon$ 表示观测值的残差项。

由不同频率观测值的差分，沿着传播路径的斜向 TEC（Slant TEC，STEC）可以分别通过伪距和载波相位观测值求出：

$$
\begin{array} { r } { S T E C _ { P } = \frac { ( f _ { 1 } f _ { 2 } ) ^ { 2 } } { 4 0 . 3 \left( f _ { 1 } ^ { 2 } - f _ { 2 } ^ { 2 } \right) } ( P _ { 2 } - P _ { 1 } ) } \end{array}
$$

$$
\begin{array} { r } { S T E C _ { L } = \frac { ( f _ { 1 } f _ { 2 } ) ^ { 2 } } { 4 0 . 3 \left( f _ { 1 } ^ { 2 } - f _ { 2 } ^ { 2 } \right) } ( \frac { c L _ { 1 } } { f _ { 1 } } - \frac { c L _ { 2 } } { f _ { 2 } } + \frac { c N _ { 1 } } { f _ { 1 } } - \frac { c N _ { 2 } } { f _ { 2 } } ) } \end{array}
$$

考虑到伪距包含较大观测噪声，且载波相位含有未知的整周模糊度，高精度STEC可以通过载波相位平滑伪距求得[7]：

$S T E C ( t ) = \omega _ { t } S T E C _ { P } ( t ) + ( 1 - \omega _ { t } ) [ S T E C ( t - 1 ) + S T E C _ { L } ( t ) - S T E C _ { L } ( t - 1 ) ] \quad ( t > 1 )$ (5)其中 $t$ 代表历元， $\omega _ { t }$ 表示权重并可以与卫星高度角有关。对于第一个历元，STEC 与 $S T E C _ { P }$ 相等。

电离层反演即使用 STEC得到反演区域内沿垂直方向的TEC。通常假设电离层的所有电子集中于一个无限薄的单层上，为此引入了如图1所示的电离层单层模型8。其中点S、R和O分别表示卫星、接收机和地心。卫星和接收机视线与电离层单层的交点被定义为穿刺点（Ionospheric Piercing Point，IPP），其经纬度等于对应的星下点（Sub-Ionospheric Point，SIP）的经纬度。因此TEC 可以根据图1所示的几何关系得出：

$$
\begin{array} { r l } & { T E C = ( S T E C - b _ { s } - b _ { r } ) \cdot c o s \chi } \\ & { \chi = a r c s i n ( \frac { R _ { e } \cdot c o s E } { R _ { e } + H } ) } \end{array}
$$

其中 $b _ { s }$ 和 $b _ { r }$ 分别是卫星和接收机的硬件偏差，x和 $E$ 分别是天顶角和高度角， $R _ { e }$ 是地球的平均半径， $H$ 是电离层单层的高度。

![](images/73452b4b3de11074ad2aaec047cfefeb363bdfd47efa2e468515ae7c8c2750a4.jpg)  
图1电离层单层模型 Fig.1Ionospheric single layer model

在另一方面，TEC在建立的模型中可以被认为是一个球谐函数，参数为IPP对应的余纬和日地坐标系下的经度[5];

$$
\begin{array} { r } { T E C = \sum _ { n = 0 } ^ { N } \sum _ { m = 0 } ^ { n } \big ( A _ { n m } { c o s } m \phi + B _ { n m } { s i n } m \phi \big ) P _ { n m } ( c o s \theta ) } \end{array}
$$

其中0和 $\phi$ 分别为余纬和日地坐标系下的经度；对于单站，通常取阶数和次数为5（ $N = M = 5$ ； $P _ { n m }$ 为归一化的勒让德函数； $A _ { n m }$ 和 $B _ { n m }$ 为球谐函数的系数，并可以通过最小二乘或其它拟合方法求得。

# 1.2人工神经网络

人工神经网络由许多神经元组成，这些神经元组成了一个输入层、一个输出层和若干隐藏层。通常一个隐藏层是足够的。一个基于误差反馈的多层前向传播神经网络能够以任意的精度趋近于一个连续实函数[6]。如图2所示为用于准实时电离层反演的神经网络的示意图，其中 $k$ 表示卫星和接收机的数目。由于在电离层反演时，卫星和接收机的硬件偏差需要同时被估计并被剔除，额外的网络被设计用于硬件偏差的估计。输入参数为STEC对应的余纬、日地坐标系下的经度以及高度角。输出参数为式（8）所示的球谐函数的系数以及硬件偏差，那么观测站上空的TEC可以通过球谐函数的系数求得。输入层的神经元除硬件偏差的初值外，还有 IPP 的余纬 $\phi$ 和日地坐标系下的经度 $\theta$ 以及天顶角x。输出层包括硬件偏差以及球谐函数系数。隐藏层的节点数是一个小于200的随机值。输出层的值通过动态调整的权值进行调整。权值通过梯度下降算法根据观测值与模型估计值的残差求出[9]：

$$
E = 1 / 2 \cdot [ V T E C / \mathrm { c o s } \ ( \chi ) - ( S T E C _ { o b s } - D C B ) ] ^ { 2 }
$$

根据式（9)，以每15分钟时段内的各卫星对应的STEC为训练数据集，在对神经网络进行训练的过程中不断地调整权值和输出层节点，最终使式（9）收敛。由于电离层的变化具有连续性，下一个时段可用当前时段训练的权值和输出层节点作为初始值，并继续用新的数据集进行训练，以达到快速收敛的目的。对于第一个时段，前一天的硬件偏差被作为初值，之后每一个时段都用前一个时段的硬件偏差作为初值。输入值经过非线性变换进入输入层再经过隐单元逐层处理，传向输出层，输出层判断估值与观测值的残差，大于阈值则转入反向传播，通过梯度下降算法修改各神经元的权值，直至输入满足条件。由于不同卫星对应的观测值包含非均一的观测误差[10][I]，而且电离层受到的扰动也会随着时间动态变化，因此神经网络是一种良好的准实时估计算法。

我们基于图2所示的神经网络架构使用MATLAB语言编写了准实时单站电离层反演程序。该程序每15 分钟通过实时接收到的GNSS数据进行一次电离层反演，得到一组球谐函数系数，并更新硬件偏差。使用 $3 . 4 \mathrm { G h z }$ 的CPU 和15GB的RAM的工作站测试后证实每一次电离层反演可以在一分钟左右完成，因此可以实现准实时的单站电离层反演。

![](images/b229d867319ad6feade341d5600e16fdf694cbf221845ccfcd72c79f528858d0.jpg)  
图2人工神经网络示意图Fig.2 Schematic diagramofartificial neural network

# 2磁静日数据验证

# 2.1测试观测网和数据处理方法

如图3所示为GNSS观测站的分布，其中位于北纬 $3 0 . 2 8 ^ { \circ }$ 东经 $1 0 9 . 4 6 ^ { \circ }$ 的观测站为测试站，其余位于东经 $1 1 0 ^ { \circ }$ 子午线附近的18个站为验证站。为了对提出的准实时神经网络法（RTANN）进行详细的评估，我们使用测试站的全球定位系统（GlobalPositioning System，GPS）的双频观测数据分别用准实时神经网络法和最小二乘球谐函数法（LSM）反演电离层TEC。同时，使用18个验证站的GPS 双频观测数据采用 $1 ^ { \circ }$ $\times 1 ^ { \circ }$ 的自适应网格法估计硬件偏差[12]，再使用 $2 ^ { \circ } \times 2 ^ { \circ }$ 的网格法每15分钟得到电离层TEC[13]，并将它们作为参考值与准实时神经网络法和最小二乘球谐函数法得到的结果进行比较。自适应网格法已经在文献[12]中应用于电离层暴时的硬件偏差估计，因此本文使用该方法得到硬件偏差参考值。除此之外，尽管多站网的反演结果也含有误差，但在观测站分布合理的情况下，多站网的反演结果比单站有更高的精度和更好的稳定性，因此作为参考值。在实验中，我们选择了2014年位于春分、夏至、秋分和冬至观测数据，这4天均为磁静日。历元间隔为30 秒，截止高度角选取 $2 0 ^ { \circ }$ ，电离层单层高度设为 $4 0 0 \mathrm { k m }$ 。

![](images/b996a3ca2ac8cf4e742480b0d93447771f16207d19ec130a1c6ac32c53881116.jpg)  
图3 $1 1 0 ^ { \circ } \mathrm { E }$ 子午线的GNSS观测站的分布 Fig.3Distributions of the GNSS observation stations along $1 0 0 ^ { \circ } \mathrm { E }$ meridian

# 2.2估计的硬件偏差

由于在电离层反演中，卫星和接收机的硬件偏差是作为整体耦合在一起的，我们采用零均值处理分离卫星和接收机硬件偏差，即对每一个卫星硬件偏差减去它们的均值并将均值并入接收机硬件偏差。图4为通过准实时神经网络法和最小二乘球谐函数法估计的卫星硬件偏差与参考值的差值，(a)-(d)分别为春分、夏至、秋分和冬至的结果。在这四天中，通过准实时神经网络法得到的卫星硬件偏差与参考值的差值在整体上比最小二乘球谐函数法更小。提升的原因在于神经网络的引入使得硬件偏差可以动态调整。这样减小了观测噪声以及电离层扰动对反演结果的影响。另外有极少数卫星的硬件偏差与参考值的偏差较大，这是由零均值处理造成的。还有部分卫星在测试时处于不可用状态，因此其结果在图中没有显示。经过计算，通过准实时神经网络法估计的硬件偏差在四天的均方根误差分别为0.38、0.25、0.37、0.31ns。而最小二乘球谐函数法的结果为 $0 . 8 4 , \ 0 . 6 1 , \ 0 . 6 7 , \ 0 . 6 8 \mathrm { n s }$ 。可以发现春分时的提升最为明显，这与春分时电离层TEC值较大，对硬件偏差估计的噪声干扰较大有关，这将在下文进一步分析。

![](images/a797799a33551225762e512760cfcda4c4820bb8b4d9ea5928561cece8fbe5d8.jpg)  
图4不同方法估计的卫星硬件偏差与参考值的差值 Fig. 4 Deviations between instrumental biases ofsatelites estimated by different methods and the references

# 2.3反演的TEC

图5为通过准实时神经网络法和最小二乘球谐函数法反演的北纬 $3 0 . 2 8 ^ { \circ }$ 东经 $1 0 9 . 4 6 ^ { \circ }$ 单站位置的电离层TEC，(a)-(d)分别为春分、夏至、秋分和冬至的结果。参考值是通过18个站采用网格法得到的，并且每15分钟独立反演。可以发现图5(a)中春分时的TEC明显大于另外三天，因此通过式（6）与TEC 同时估计的硬件偏差受噪声影响也更大。将单站反演的TEC与参考值对比后可以发现，通过准实时神经网络法反演的TEC 比最小二乘球谐函数法更接近于参考值，尤其是正午和午夜。正午提升较明显是因为正午时TEC 值较大，而神经网络的加入使得反演受噪声影响更小。而午夜是因为此时TEC值较小，最小二乘球谐函数法的反演结果受硬件偏差的影响较大，而准实时神经网络法估计的硬件偏差更准确。另外，准实时神经网络反演的TEC也不平滑，我们推测这可能与电离层扰动有关，因为大部分波动趋势都与参考值相对应。经计算，准实时神经网络法的均方根误差分别为2.76、1.00、0.99、1.73TECU，最小二乘球谐函数法的为3.46、2.32、0.94、1.46 TECU。因此，通过实时神经网络法反演的 TEC 比最小二乘球谐函数法更准确。

![](images/029ea4c62b89c10e8078d2ea1789a4cd32ae5c7dbe7cecc54782ae46a77e3f47.jpg)  
图5不同方法反演的北纬 $3 0 . 2 8 ^ { \circ }$ 东经 $1 0 9 . 4 6 ^ { \circ }$ 的TEC Fig. 5 TEC at $3 0 . 2 8 ^ { \circ } \mathrm { N }$ and $1 0 9 . 4 6 ^ { \circ } \mathrm { E }$ derived by different methods

# 3电离层暴数据测试

我们分别通过准实时神经网络法和最小二乘球谐函数法通过单站反演了2016年10月13日电离层暴的TEC。如图6所示为GNSS观测站的分布，其中位于北纬 $4 0 . 5 2 ^ { \circ }$ 西经 $3 . 0 9 ^ { \circ }$ 的观测站为测试站，其余位于 $0 ^ { \circ }$ 子午线和 $4 0 ^ { \circ } \mathrm { N }$ 纬线附近的7个站为验证站。根据文献[14]，暴的起始发生于12日 $2 1 0 0 \mathrm { U T }$ ，初相从$2 3 0 0 \mathrm { U T }$ 持续至13日的 $0 6 0 0 \mathrm { U T }$ ，接下来主相持续了18小时；并且使用图6的7个验证站观测到13日白天的正暴及夜间的负暴，结合测高仪观测到的电离层抬升证实了引起这个电离层暴的主要物理机制是扰动中性风。

![](images/296255cbceabf6ad6fae8f9a6e13a14c68adbd147536f8d74cbfc08d6593a2b6.jpg)  
图 $6 ~ 0 ^ { \circ }$ 子午线和 $4 0 ^ { \circ } \mathrm { N }$ 纬线的GNSS 观测站的分布 Fig.6 Distributions of the GNSS observation stations along $0 ^ { \circ }$ meridian and $4 0 ^ { \circ } \mathrm { N }$ parallel

如图7所示为不同方法估计的2016年10月8日至17日的卫星硬件偏差相对于10天日均值的均方根误差。由于10月13日发生了电离层暴，估计的硬件偏差相对于磁静日变化较大。但实际上硬件偏差取决于仪器本身以及所处的外部环境，只是由于反演过程中与TEC耦合在一起才受到了电离层变化的影响。而准实时神经网络法的均方根误差在这10天中均小于最小二乘球谐函数法，特别是在13日暴发生期间。这说明准实时神经网络法估计的硬件偏差受电离层变化的影响更小，因此优于最小二乘球谐函数法。

![](images/f0639eb56c6423941088d1d5f3ad17b9551f85247425b6076778ba1dd350e2c9.jpg)  
图7不同方法估计的卫星硬件偏差相对于日均值的均方根误差

Fig.7Root mean square eror ofinstrumental biases ofsatelites estimated by different methodsand the daily averages

如图8所示为不同方法反演的2016年10月8日至17日的TEC。相比于8-11日磁静日的TEC，13日白天的TEC表现为明显的正暴效应，TEC增大率超过了 $100 \%$ ，而从13日夜间开始表现为明显的负暴效应，并持续至15日。另外，反演的TEC与文献[14]的结果相符，并且与赤道向扰动中性风的物理机制相符。暴时的赤道向中性风可以抬升电离层，同时也会引起电离层的成分变化。白天由于电离层较低高度有光电离作用的补充使得正暴发生，而夜间光电离作用消失同时离子结合率上升使得负暴发生。另外，比较准实时神经网络法和最小二乘球谐函数法的反演结果，发现两种方法反演的TEC也具有很好的一致性。另外，准实时神经网络法能更好地反映电离层的变化，主要表现在正午和午夜，而夜间神经网络法的TEC较低也与图5的结果相符合。

![](images/ecb762f29dfb4fc6e97048c45328689226f9b401490b532cbd2bbaf147eeccd0.jpg)  
图8不同方法反演的北纬 $4 0 . 5 2 ^ { \circ }$ 西经 $3 . 0 9 ^ { \circ }$ 的TECFig. 8TEC at $4 0 . 5 2 ^ { \circ } \mathrm { N }$ and $3 . 0 9 ^ { \circ } \mathrm { W }$ derived bydifferent methods

# 4结语

我们提出了一种基于人工神经网络的准实时单站电离层反演方法。在设计的神经网络中，输入层包含作为初值的前一天的硬件偏差以及穿刺点的余纬、日地坐标系下的经度以及高度角，输出层为球谐函数系数以及硬件偏差。通过不断调整的权值，输出层可以利用梯度下降算法根据残差进行迭代。因此硬件偏差可以随着观测值动态调整并且TEC也可以被准实时地反演。在一个实验中，位于北纬 $3 0 . 2 8 ^ { \circ }$ 东经 $1 0 9 . 4 6 ^ { \circ }$ 的单站在 2014年春分、夏至、秋分和冬至的磁静日GNSS 数据被用于分别采用提出的方法与经典的最小二乘球谐函数法进行电离层反演。位于东经 $1 1 0 ^ { \circ }$ 子午线的18个站被作为参考站通过网格法获得硬件偏差和 TEC 参考值。结果显示使用提出的方法估计的硬件偏差在整体上更接近于参考值。反演的TEC 相对于最小二乘球谐函数法更接近于参考值。在另一个实验中，2016年10月13日电离层暴事件的TEC 也分别通过位于北纬 $4 0 . 5 2 ^ { \circ }$ 西经 $3 . 0 9 ^ { \circ }$ 的单站使用提出的方法和最小二乘球谐函数法被反演。两种方法反演的TEC也具有很好的一致性；基于神经网络的硬件偏差估计与磁静日的硬件偏差估计更接近。这些结果说明了提出的神经网络方法相比最小二乘球谐函数法具有较高的精度。神经网络同样适用于准实时多站电离层反演，值得进一步推广。

致谢：感谢IGS网站及中国陆态网提供GNSS实测数据。

# 参考文献：

[1] BUSTG S,MCHELLCN.Historycurent state,and future directions ofionospheric imaging[J].Reviewsof Geopysics, 2008,46(1):RG1003.doi:10.1029/2006RG000212   
[2] ANDERSOND N,BUONSANTO MJ,CODRESCU M,et al. Intercomparison of physical modelsand observations of the ionosphere[J].JournalofGeophysicalResearch:Space Physics,1998,103(A2):2179-2192.doi: 10.1029/97JA02872   
[3] LI J,WANQ,MA G,etal.Evaluationof the Klobuchar model inTaiWan[J].Advancesin SpaceResearch,2017,60 (6): 1210-1219. doi: 10.1016/j.asr.2017.05.045   
[4] LU W,MA G,WANG X,etal.Evaluation of ionospheric height assumption for single station GPS-TEC[J].Advances in Space Research,2017,60 (2): 289-294. doi: 10.1016/j.asr.2017.01.019   
[5] LIUJ, CHENR, WANG Z, ZHANG H. Spherical cap harmonic model for mapping and predicting regional TEC[J]. GPS Solutions,2011,15 (2): 109-119.doi: 10.1007/s10291-010-0174-8   
[6] MARUYAMA T.Regional reference total electron content modelover Japan based on neural network mapping techniques[J]. Annales Geophysicae,2008,25 (12):2609-2614.doi:10.5194/angeo-25-2609-2007   
[7]MANNUCCIAJ, WILSONBD,YUANDN,et al.Aglobal mapping technique forGPSderived ionospheric electroncontent measurements [J].Radio Science,1998,33 (3): 565-582.doi: 10.1029/97RS02707   
[8] BRUNINI C,AZPILICUETA F. GPS slant total electron content accuracy using the single layer model under different geomagneticregionsandionosphericconditions[J].Journal of Geodesy，2010，84(5):293-304.doi: 10.1007/s00190-010-0367-5   
[9] HAYKIN S.Neural networks - Acomprehensive foundation [M]. Macmillan Collge Publishing Company,Inc,1994.   
[10]FANJ,MAG.CharacterstcsofGPSpositioningerorithnon-uniformpseudorangeeror[J].GPSSolutions,04,18(4): 615-623.doi: 10.1007/s10291-013-0359-z   
[1]贾静怡，马冠一，范江涛，等．非均一方差的GNSS 定位误差模型检验[J]．天文研究与技术，2019，16(4)：437-446. JIA Jingyi,MA Guanyi,FAN Jiangtao,etal.Atestof GNSSpositioning errr model ofnon-uniform pseudorange rror[J]. Astronomical Research & Technology,2019,16 (4): 437-446.doi: 10.14005/j.cnki.issn1672-7673.20190403.001   
[12] ZHANG W,ZHANGDH,XIAO Z.The influence ofgeomagnetic storms onthe estimationof GPS instrumental biases[J]. Annales Geophysicae,2009,27(4):1613-1623.doi:10.5194/angeo-27-1613-2009   
[13]MAG,MARUYAMA T.Derivation of TECand estimationof instrumental biases from GEONET in Japan[J].Annales Geophysicae,2003,21 (10):2083-2093.doi:10.5194/angeo-21-2083-2003   
[14]WAN Q,LIJ, WANG X,et al.A StudyofTEC Storm on13October 2016[M]/ China Satelite Navigation Conference (CSNC) 2018 Proceedings.2018:vol 497.doi:10.1007/978-981-13-0005-9_8

# Near-real-time ionospheric TEC derivation from single station with neural network

LU Weijun1,2， MA Guanyi1,2 (1.NationalAstronomicalObservatories,ChineseAcademyofSciences,Beijing,00l01,China;2.UniversityofChinese Academy of Sciences,Beijing,100049, China)

Abstract: In derivation of ionospheric total electron content (TEC) by global navigation satelite system (GNSS),compared with a multi-station observation network,single-station derivation is a flexible and convenient method.Based on the artificial neural network (ANN), we propose a near-real-time method to derive ionospheric TEC with a single station.In this method,the instrumental biases of previous period are taken as initial values and are adjusted with the observation data.Meanwhile,the ionospheric TEC is derived in near-real-time.In order to have a detailed assessment on this method,through a single station in China,the TEC during four magnetically quiet days is derived by the proposed method and classic least square method (LSM) with spherical harmonics, respectively.The references of instrumental biases and TEC are obtained by the nearby multi-station network. In another test,through a single station in Europe,the TEC during an ionospheric storm and the quiet days before and after the event are also derived by the above methods. At the magnetically quiet days,the estimated instrumental biases are closer to the references than LSM with spherical harmonics on the whole,and the derived TEC is also closer to the references.During the ionospheric storm,the TEC derived by the two methods also have good consistency，and the estimated instrumental biases during the ionospheric storm are closer to those at magnetically quiet days.The results show that the proposed neural network method has higher accuracy than LSM with spherical harmonics.

Keywords: Ionosphere; Artificial neural network; Total electron content; Instrumental bias; Ionospheric storm