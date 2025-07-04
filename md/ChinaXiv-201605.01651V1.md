# 有效载荷分离释放弹簧的设计与计算

郑龙飞¹²,杨萱}，杨华（1．中国科学院空间科学与应用研究中心北京100190;2．中国科学院大学北京100049;3．内蒙古电子信息职业技术学院电子工程系,内蒙古 呼和浩特010011)

摘要：在弹簧作为航天任务中有效载荷的推进装置的优化设计中，为保证载荷的释放速度以及弹簧质量最轻,结合几何约束、可靠性与稳定性的要求建立非线性约束优化模型将Matlab求得的理论解带入商业软件Adams进行仿真运算,得到理论速度与仿真速度的拟合关系。利用拟合关系和用Matlab优化工具箱即可求得满足仿真分离速度的弹簧设计参数。利用上述方法对分离推力弹簧进行设计与计算，并利用虚拟样机技术进行验证减少了弹簧设计重复试算的过程弹簧质量缩减率在 $3 0 \%$ 以上满足释放速度要求得到满意的优化设计结果。

关键词:有效载荷;弹簧设计;分离释放;非线性拟合中图分类号：V411.8 文献标识码：B

# Design and Calculation of Compression Spring of Releasing Payload

ZHENG Long -fei1 ² YANG Xuan1 YANG Hua³

(1.Center for Space Science and Applied Research,Chinese Academy of Science,Beijing 100190,China;   
2.University of Chinese Academy of Sciences ,Beijing 10oo49,China;   
3.Department of Electronic Engineering,Inner Mongolia Electric Information Vocational Technical College， Hohhot Inner Mongolia O10011,China)

ABSTRACT: Springs canbe used to provide release rate for payload in space missions.In order to guarantee the precise releasing velocity of payload and the minimum mass of springs,a nonlinear constrained optimization model wasbuilt with geometricconstraints,reliabilityand stability.The theorysolutionofMATLAB was brought into Adams for simulation,which can work outthefiting relationship between theoryand simulation.The spring design parameters wereobtained byusingthe fiting relationshipandcalculation of MATLAB.Theresult wasverified by Virtual Prototype Technology and perfect performance of design parameters was achieved.

KEYWORDS:Payload; Design of spring; Release; Nonlinear fitting

# 1引言

随着科学技术的不断发展，人类空间科学探测的研究领域大为拓展空间物理探测已到了多点、多尺度的时代这就需要多颗小卫星或多个有效载荷进行协同观测。载荷分离释放技术是影响有效载荷初始状态和编队飞行的重要因素。航天飞行器上有效载荷的分离机构一般由火工品或形状记忆合金提供释放速度。但火工品存在安全性较差，可能会对有效载荷中的科学设备造成污染，工作时产生较大的冲击，只能一次性使用，不能重复测试性能等缺点;而形状记忆合金具有成本较高作用时间长，需要供电加热消耗大量能源等缺点[1]因此利用机械弹簧所储存的弹性势能为低速有效载荷提供初始速度就具有明显的实用性和可靠性。

弹簧作为一种机械结构中的常用部件在各行各业中广泛利用。在车辆工程、机械设计等研究领域中主要考虑弹簧的应力、应变、基频和工作载荷等结构性能参数[2-5],研究方法主要有:优化设计理论[6-7]、可靠性优化理论[8-9]、多目标稳健优化设计[10]、多目标模糊优化设计[1]、基于区间算法的优化设计[12]、基于Matlab优化算法的优化设计[13]、基于有限元法的优化设计[14-15],上述研究均未考虑弹簧的动力学性能及运动过程，而在有效载荷（以下简称“载荷")分离释放技术中分离推力弹簧(以下简称“弹簧"）所能提供的分离速度是首要的性能参数。对于单载荷释放任务，文献[16]基于多岛遗传算法对卫星的释放装置进行优化设计,并对其进行运动仿真与实验。对于多载荷协同编队任务，为保证释放后载荷能顺利进行姿态控制和轨道控制弹簧所提供的释放速度必须为精确值，且由于安装空间有限弹簧的几何尺寸必须满足空间限制。然而文献[16]所采用的方法只能保证载荷的释放速度限定在某一区间中而无法保证释放速度为某一精确值，且未对弹簧进行空间限制，因此该方法不适用于需要保证精确释放速度的多载荷协同编队任务。

此外由于在实际分离过程中不可避免地存在阻力和其它扰动理论分析无法准确得到载荷的实际释放速度，为保证载荷分离速度的精确性还需对分离过程进行Adams运动学仿真计算。然而在目标速度确定的情况下需要试验多组数据才能得到满足要求的弹簧性能参数，时间周期较长，并且设计结果无法保证质量最轻的设计目标。因此为减小航天任务中的运载成本保证载荷的顺利编队和弹簧的力学性能对多载荷分离释放弹簧进行理论分析与仿真计算相结合的优化设计显得尤为重要。本文以两端固定、不磨平的螺旋圆柱弹簧为例根据性能约束、几何约束、弹簧可靠性与稳定性的要求建立了非线性约束优化模型，利用Matlab优化工具箱求得弹簧的理论最优解将理论最优解带入Adams中进行运动学仿真得到理论速度与仿真速度的拟合关系，从而对于航天分离释放任务所要求的目标速度，利用拟合关系得到Matlab中所对应的理论速度进而通过Matlab优化工具箱求得满足特定仿真释放速度的分离释放弹簧设计参数的最优解。

# 2设计原理过程

# 2.1 设计变量

选取三个独立设计参数为设计变量：簧丝直径 $d$ 弹簧中径 $D$ 弹簧有效卷数 $n ^ { [ 1 7 ] }$ ,故令设计向量 $\boldsymbol { X } = \left[ \boldsymbol { d } ~ , \boldsymbol { D } ~ \boldsymbol { n } \right] ^ { T } =$ ${ \left[ \begin{array} { l l l } { x _ { 1 } } & { x _ { 2 } } & { x _ { 3 } } \end{array} \right] } ^ { T }$ 式中： $\textit { D } \boldsymbol { \mathscr { d } }$ 为连续变量 $, n$ 仅取整数或小数部分为0.5其余参数设为定值。

# 2.2 目标函数

在有效载荷释放任务中，为减轻整体质量，提高运载能力以弹簧质量 $M$ 最小为优化目标。可得[5]

$$
{ \cal M } = \frac { 1 } { 4 } \pi ^ { 2 } \rho N { \cal D } d ^ { 2 } ( n + 2 ) = \frac { 1 } { 4 } \pi ^ { 2 } \rho x _ { 1 } ^ { 2 } x _ { 2 } ( x _ { 3 } + 2 ) { \cal N }
$$

# 2.3 约束条件

2.3.1 自由长度

弹簧自由长 $H _ { 1 } = p _ { 1 } n + 3 d = \left( \begin{array} { l } { n + 3 } \end{array} \right) d + \delta _ { 1 } n$ 根据弹簧安装的空间要求得： $H _ { 1 } \leqslant H$ 即

$$
g _ { 1 } ( \ X ) = H - \left( \ x _ { 3 } \ + \ 3 \right) x _ { 1 } \ - \delta _ { 1 } x _ { 3 } \geqslant 0
$$

式中： $p _ { 1 }$ 为自由状态下弹簧的节距 $\delta _ { 1 }$ 为自由状态下弹簧簧丝之间的距离 ${ } , { \cal H }$ 为几何空间约束下所允许的弹簧最大长度。

# 2.3.2 装载长度

与弹簧自由长类似 弹簧的装载长度 $h = ( n + 3 ) d + \delta _ { 0 } n$ 1又因弹簧压并高度 $H _ { b } = \left( n + 3 \right) d$ 可得

$$
g _ { 2 } ( \ X ) \ = h - ( x _ { 3 } + 3 ) x _ { 1 } \geqslant 0
$$

# 2.3.3 外径

因弹簧外径不得超出安装空间故 $D + d \leqslant A$ 其中 $A$ 为安装空间所允许得最大外径。可得

$$
g _ { 3 } ( \ X ) = A - x _ { 1 } - x _ { 2 } \geqslant 0
$$

# 2.3.4弹簧指数

弹簧指数 $c = { \frac { D } { d } }$ 因弹簧指数减小会导致局部应力过大。另外弹簧指数较大或较小时,加工性也成为问题。热轧成型时弹簧指数可在4一15的范围内选择即 $4 \leqslant c \leqslant 1 5$ 1可得

$$
g _ { 4 } ( \ X ) = \frac { x _ { 2 } } { x _ { 1 } } - 4 \geq 0
$$

$$
\begin{array} { r } { g _ { 5 } ( \ X ) = 1 5 - \displaystyle \frac { x _ { 2 } } { x _ { 1 } } \geqslant 0 } \end{array}
$$

# 2.3.5 纵横比

纵横比 $a = \frac { H _ { 1 } } { D }$ 纵横比较大的压缩弹簧，在轴向载荷达到一定程度就会产生侧向弯曲而失去稳定性。为保证使用稳定，对于两端固定的压缩弹簧纵横比一般选为： $0 . 8 \leqslant a <$

5.3即 $0 . 8 { \leqslant } \frac { H _ { 1 } } { D } { < } 5 . 3$ 即

$$
\begin{array} { r l } { \displaystyle g _ { 6 } \big ( \mathrm { \Delta } X \big ) } & { = \mathrm { \Delta } h + \big ( \delta _ { 1 } - \frac { \mathrm { \Delta } h - \big ( \mathrm { \Delta } x _ { 3 } + 3 \big ) \mathrm { \Delta } x _ { 1 } } { x _ { 3 } } \big ) \mathrm { \Delta } x _ { 3 } - 0 . 8 x _ { 2 } \geqslant 0 \big ( } \\ { \displaystyle g _ { 7 } \big ( \mathrm { \Delta } X \big ) } & { = - \mathrm { \Delta } h - \big ( \delta _ { 1 } - \frac { \mathrm { \Delta } h - \big ( \mathrm { \Delta } x _ { 3 } + 3 \big ) \mathrm { \Delta } x _ { 1 } } { x _ { 3 } } \big ) \mathrm { \Delta } x _ { 3 } + 5 . 3 x _ { 2 } > 0 } \end{array}
$$

# 2.3.6 有效卷数

如果有效圈数为3以下弹簧特性则会变得不稳定因此应将弹簧有效卷数设定为3以上即 $n \geqslant 3$ 结合式(3)得:$d { \leqslant } \frac { h } { 6 }$

即

$$
g _ { 8 } ( \ X ) = \frac { h } { 6 } - x _ { 1 } \geqslant 0
$$

# 2.3.7 应力约束

弹簧中的应力

$$
\ \tau = { \frac { 8 K D F } { \pi d ^ { 3 } } }
$$

式中： $K$ 为曲度系数由下式计算 $K = { \frac { 4 c - 1 } { 4 c - 4 } } + { \frac { 0 . 6 1 5 } { c } } \ , F$ 为工作载荷。

最大工作载荷

$$
F _ { _ \mathrm { m a x } } \ = \ k ( \ H _ { _ 1 } \ - \ h )
$$

式中：弹簧刚度 $k = \frac { G d ^ { 4 } } { 8 D ^ { 3 } n } \ , G$ 为材料的剪切弹性模量。则最大应力

$$
\tau _ { _ { \mathrm { m a x } } } = \frac { 8 K D F _ { _ { \mathrm { m a x } } } } { \pi d ^ { 3 } } = \frac { G d ( { \cal H } _ { 1 } - h ) } { \pi D ^ { 2 } n } \Big ( \frac { 4 c - 1 } { 4 c - 4 } + \frac { 0 . 6 1 5 } { c } \Big ) \leqslant \frac { \tau _ { p } } { S _ { p } }
$$

式中： $\tau _ { { \scriptscriptstyle p } }$ 为弹簧材料的许用切应力 $\mathbf { \nabla } _ { \mathcal { S } _ { p } }$ 为许用安全系数因弹簧要求精度较高 取 $S _ { p } = 1 . 3 \sim 1 . 7$ 。即

$$
g _ { 9 } \left( \ X \right) = \frac { \tau _ { p } } { S _ { p } } -
$$

$$
\frac { G x _ { 1 } [ ( x _ { 3 } + 3 ) x _ { 1 } + \delta _ { 1 } x _ { 3 } - h ] } { \pi x _ { 2 } ^ { 2 } x _ { 3 } } \bigg ( \frac { 4 x _ { 2 } - x _ { 1 } } { 4 x _ { 2 } - 4 x _ { 1 } } + \frac { 0 . 6 1 5 x _ { 1 } } { x _ { 2 } } \bigg ) \gtrless 0
$$

# 2.3.8 性能约束

为保证载荷释放时达到所需的速度根据能量守恒得

$$
{ \frac { N } { 2 } } k ( H _ { 0 } - h ) ^ { 2 } = { \frac { 1 } { 2 } } ( m _ { 0 } + m _ { 1 } ) v ^ { 2 } + \mu T s
$$

式中： $m _ { 0 }$ 为载荷的质量 ${ m } _ { 1 }$ 为弹簧与载荷之间挡板的质量，$\boldsymbol { v }$ 为载荷的释放速度 $\mu$ 为摩擦系数 ${ } , { } T$ 为载荷所受到得预紧力 $\mathbf { \Delta } , \mathbf { \vec { \mathbf { \sigma } } } ,$ 为载荷从静止到释放所做的位移。

即

$$
\begin{array} { l } { { \displaystyle g _ { 1 0 } ( \chi ) = \frac { G x _ { 1 } ^ { 4 } N } { 1 6 x _ { 2 } ^ { 3 } x _ { 3 } } [ ( x _ { 3 } + 3 ) x _ { 1 } + \delta _ { 1 } x _ { 3 } - h ] ^ { 2 } } } \\ { { \displaystyle ~ - \frac { 1 } { 2 } ( m _ { 0 } + m _ { 1 } ) v ^ { 2 } - \mu T s = 0 } } \end{array}
$$

# 2.4 建立数学模型

令 $X = \left[ \begin{array} { l } { d } \end{array} \right. , D \ n \left] ^ { T } = \left[ \begin{array} { l } { x _ { 1 } } \end{array} \right. , x _ { 2 } \ x { \times } _ { 3 } \right] ^ { T }$ ,得到以圆柱螺旋压缩弹簧的质量为目标函数的非线性约束优化模型

$$
\left\{ \begin{array} { l l } { \displaystyle \operatorname* { m i n } f ( \chi ) = \frac { 1 } { 4 } \pi \rho x _ { 1 } ^ { 2 } x _ { 2 } \mathfrak { C } _ { \displaystyle 3 } + 2 ) N } \\ { \displaystyle \quad g _ { i } ( \chi ) \geqslant 0 \quad \mathfrak { C } _ { i } = 1 \ 2 \ , \cdots \ 9 ) } \\ { \displaystyle \quad g _ { 1 0 } ( \chi ) = 0 } \end{array} \right.
$$

# 3设计计算

# 3.1 设计前提

将载荷在地面实验时受到的重力等效为实际分离时的预紧力故预紧 $T = m _ { 0 }  { g }$ 。在载荷分离过程中，不考虑除摩擦阻力之外其余阻力对载荷运动过程的影响。优化计算所涉及的其它参数如表1所示。

表1弹簧设计相关参数  

<html><body><table><tr><td>弹簧参数</td><td>参数值</td></tr><tr><td>材料</td><td>不锈弹簧钢</td></tr><tr><td>弹性模量E/GPa</td><td>193</td></tr><tr><td>剪切模量 G/Gpa</td><td>71.6</td></tr><tr><td>许用剪切应力τp/MPa</td><td>533</td></tr><tr><td>密度p/(kg/m³)</td><td>7.93 ×10³</td></tr><tr><td>载荷质量mo/kg</td><td>10</td></tr><tr><td>载荷尺寸/mm</td><td>100 ×200×300</td></tr><tr><td>弹簧装载空间/mm</td><td>100 ×200</td></tr></table></body></html>

<html><body><table><tr><td>弹簧参数</td><td>参数值</td></tr><tr><td>弹簧与载荷之间的挡板尺寸/mm</td><td>3×100×100</td></tr><tr><td>自由状态簧丝间距8/mm</td><td>7</td></tr><tr><td>弹簧最大自由长H/mm</td><td>385</td></tr><tr><td>挡板质量m1/g</td><td>475.8</td></tr><tr><td>滑轨摩擦系数μ</td><td>0.004</td></tr><tr><td>重力加速度g/(N/kg)</td><td>9.8</td></tr><tr><td>安全系数Sp</td><td>1.3</td></tr><tr><td>容许速度误差</td><td>5%</td></tr></table></body></html>

# 3.2 计算过程

# 3.2.1 Matlab优化计算

对于单弹簧设计方案，为保证运算速度，优化设计结果，采用 Matlab 优化工具箱中的有效集算法[10],对于不同的分离速度得到相应的设计参数如表2所示。

表2不同理论分离速度对应的设计参数  

<html><body><table><tr><td></td><td>理论分离速 度v1(m/s)</td><td>线径 d( mm)</td><td>中径 D( mm)</td><td>弹簧 卷数n</td><td>装载力 F( N)</td><td>弹簧刚度 k( N/mm)</td></tr><tr><td>1</td><td>0.5</td><td>2.7</td><td>25.1</td><td>13</td><td>103.62</td><td>2. 1598</td></tr><tr><td>2</td><td>0.6</td><td>2.8</td><td>26.8</td><td>13</td><td>119. 02</td><td>2.3136</td></tr><tr><td>3</td><td>0.7</td><td>3.4</td><td>28.2</td><td>11</td><td>189.42</td><td>4. 7936</td></tr><tr><td>4</td><td>0.8</td><td>3.6</td><td>30.2</td><td>11</td><td>213.00</td><td>5.01</td></tr><tr><td>5</td><td>0.9</td><td>4.3</td><td>36.8</td><td>10</td><td>259. 11</td><td>6. 1951</td></tr><tr><td>6</td><td>1</td><td>4.3</td><td>33.9</td><td>10</td><td>314. 65</td><td>7.72</td></tr><tr><td>7</td><td>1.1</td><td>5</td><td>42.5</td><td>9.5</td><td>346.25</td><td>7. 978</td></tr><tr><td>8</td><td>1.2</td><td>5</td><td>48.4</td><td>11</td><td>280.62</td><td>4.5161</td></tr><tr><td>9</td><td>1.3</td><td>5.3</td><td>52.6</td><td>11</td><td>300. 63</td><td>4.5</td></tr><tr><td>10</td><td>1.4</td><td>5.6</td><td>56.2</td><td>11</td><td>322.81</td><td>4. 5535</td></tr><tr><td>11</td><td>2</td><td>6</td><td>52</td><td>11</td><td>561. 68</td><td>7.13</td></tr></table></body></html>

# 3.2.2Adams 仿真计算

建立如图1所示的设计模型。

![](images/ee9dff5b6345988cb800db1d2a1cdc4d338db48a4cf7c682b52071a1af7143cb.jpg)  
图1分离释放装置的简化结构图

将表1中的装载力和弹簧刚度参数带入Adams模型中，进行仿真计算，以理论分离速度 $\mathrm { { v } } _ { 1 } = 0 . 6 \mathrm { { m } / \mathrm { { s } } }$ 为例,得到如图2、图3所示的载荷位移曲线与速度曲线。

如图2所示横坐标为运动时间t，纵坐标为载荷质心相对于分离装置后挡板的位置s载荷初始位置为 $2 4 0 . 5 \mathrm { m m }$ 由

![](images/c3890f7bf3decce92089667c44bdef6f05e1f4c751791749040c44f66c1d0595.jpg)  
图2理论分离速度 $\mathbf { v _ { 1 } } = \mathbf { 0 } . 6 \mathbf { m } / \mathbf { s }$ 时载荷的时间一位置曲线

![](images/192bcc3b51e76560246273f3a7f48f090af837be73cf07bcee0bb4176d033f81.jpg)  
图2可得：位移随着时间的增大而增大，根据分离装置的设计尺寸，可得载荷在 $\mathrm { s } = 5 4 0 . 5 \mathrm { m m }$ 时与释放装置分离此时运动时间 $\mathrm { t } = 0 . 5 1 9 5 \mathrm { s }$ 。

如图3所示横坐标为载荷的运动时间t纵坐标为载荷的速度 $\mathbf { v }$ ，根据图2中载荷与释放装置分离时的时间 $\mathbf { t } = \mathbf { \partial }$ 0.5195s得到载荷的仿真分离速度 $\mathbf { v } _ { 2 } = 0 . 5 3 3 \mathrm { m / s }$ 。以此类推得到11组理论分离速度 $\mathbf { v } _ { 1 }$ 及其所对应的仿真分离速度$\mathbf { v } _ { 2 }$ 如表3所示。

表3Matlab理论分离速度与Adams仿真分离速度  

<html><body><table><tr><td></td><td>v1 /(mm/s)</td><td>V2/(mm/s)</td><td>相对误差</td></tr><tr><td>1</td><td>500</td><td>436</td><td>12. 84%</td></tr><tr><td>2</td><td>600</td><td>533</td><td>11. 17%</td></tr><tr><td>3</td><td>700</td><td>613</td><td>12. 43%</td></tr><tr><td>4</td><td>800</td><td>716</td><td>10.51%</td></tr><tr><td>5</td><td>900</td><td>816</td><td>9.31%</td></tr></table></body></html>

<html><body><table><tr><td></td><td>v1/(mm/s)</td><td>V2/( mm/s)</td><td>相对误差</td></tr><tr><td>6</td><td>1000</td><td>906</td><td>9.45%</td></tr><tr><td>7</td><td>1100</td><td>1000</td><td>9.09%</td></tr><tr><td>8</td><td>1200</td><td>1127</td><td>6.08%</td></tr><tr><td>9</td><td>1300</td><td>1229</td><td>5.48%</td></tr><tr><td>10</td><td>1400</td><td>1330</td><td>5%</td></tr><tr><td>11</td><td>2000</td><td>1912</td><td>4.41</td></tr></table></body></html>

# 3.2.3 拟合计算

因载荷在释放过程中，挡板与载荷之间存在接触与碰撞分离过程存在能量损失，所以仿真释放速度小于理论释放速度。由表3可得，利用Matlab计算所得到的理论值与Adams仿真值之间的误差在速度小于 $1 . 4 \mathrm { m / s }$ 时，相对误差均大于 $5 \%$ 超出了弹簧设计的性能要求。因此，为保证弹簧性能在合理的误差范围内将表3中的数据利用Matlab 进行四次多项式拟合,得到理论分离速度 $\mathbf { v } _ { 1 }$ 与仿真分离速度 $\mathbf { v } _ { 2 }$ 之间的拟合多项式：

v= 0.1318v-0.4469v +0.4063v² + 0.9647v + 0.0331对式(16)作图如图4所示横坐标为仿真分离速度 $\mathbf { v } _ { 2 }$ 纵坐标为理论分离速度 $\mathbf { v } _ { 1 }$ 离散点均匀分布在曲线两侧拟合精度较高。

![](images/d197c41b30bd73e6dae94d23687154790f2de7fac5e03eee868dc93628607e4a.jpg)  
图3理论分离速度 $\mathbf { v _ { 1 } } = \mathbf { 0 } . 6 \mathbf { m } / \mathbf { s }$ 时载荷的时间一速度曲线  
图4散点图与多项式拟合曲线

根据式(16)中拟合计算的结果，可以求出满足特定分离速度条件下载荷所需达到的理论释放速度，进而利用Mat-lab有效集算法反求出弹簧的最优设计参数。

# 3.3算例

在多载荷协同编队探测过程中所规定的载荷释放速度共有三组分别为： $0 . 5 9 3 \mathrm { m / s } . 0 . 7 9 9 \mathrm { m / s } . 0 . 9 2 \mathrm { m / s }$ 。原始的设计参数如表4所示。

表4分释放弹簧的原始设计参数  

<html><body><table><tr><td>组数</td><td>目标速度 vo /( mm/s)</td><td>线径 d/mm</td><td>中径 D/mm</td><td>弹簧质 量m/g</td><td>真实仿真速度 V3/(mm/s)</td></tr><tr><td>1</td><td>593</td><td>5.01</td><td>63</td><td>390</td><td>593.6</td></tr><tr><td>2</td><td>799</td><td>5.59</td><td>61.86</td><td>430</td><td>799.3</td></tr><tr><td>3</td><td>920</td><td>5.89</td><td>60.44</td><td>450</td><td>919.6</td></tr></table></body></html>

以目标速度 $\mathrm { v _ { 0 } } = 0 . 7 9 9 \mathrm { m / s }$ 为例假定有效载荷最终的释放速度与Adams的仿真结果相同，即另 $\mathbf { v } _ { 2 } = \mathbf { v } _ { 0 }$ ,根据式(16)得载荷理论分离速度 $\mathrm { v } _ { 1 } = 0 . 8 8 9 \mathrm { m / s }$ ，利用Matlab优化工具箱中的有效集算法得到：装载力 $\mathrm { F } = 2 3 7 . 1 8 2 5 \mathrm { N }$ 刚度 $\mathbf { k }$ $= 5 . 2 9 1 5 \mathrm { N / m m }$ ,线径 $\mathrm { d } = 3 . 8 \mathrm { m m }$ 中径 $\mathrm { D } = 3 1 . 9 \mathrm { m m }$ 弹簧有效卷数 ${ \bf n } = 1 1$ .将上述参数带入Adams模型中进行仿真，得到载荷的实际仿真分离速度 $\mathrm { v } _ { 3 } = 0 . 8 0 5 \mathrm { m } / \mathrm { s }$ 同理对于其它两组目标速度得到如表5所示的速度和质量对照表。

表5载荷分离速度与质量对照表  

<html><body><table><tr><td></td><td>目标速 度vo</td><td>理论速 度v1</td><td>仿真速 度v3</td><td>相对 误差</td><td>优化 质量</td><td>原始 质量</td><td>质量缩 减率</td></tr><tr><td>1</td><td>593</td><td>671.1</td><td>606.9</td><td>2.3%</td><td>73.4</td><td>390</td><td>81.2%</td></tr><tr><td>2</td><td>799</td><td>889.0</td><td>805.0</td><td>0.8%</td><td>117. 3</td><td>430</td><td>72.7%</td></tr><tr><td>3</td><td>920</td><td>1010.9</td><td>927.4</td><td>0.8%</td><td>143.5</td><td>450</td><td>68.1%</td></tr></table></body></html>

由表5可得实际仿真速度与规定速度的误差均在 $5 \%$ 以内满足弹簧设计的性能要求，且弹簧质量有明显的缩减，满足优化设计的要求。

# 4结论

航天任务的特殊性要求弹簧采用最优化设计并且载荷在释放过程中不可避免地存在能量耗散，理论分析无法准确得到载荷的实际释放速度。同时仿真计算存在收敛速度慢时间周期长，无法进行优化设计等缺点。本文利用最优化理论建立了关于弹簧推进释放速度的理论分析模型，然后利用Matlab拟合计算与Adams仿真计算建立理论释放速度与仿真释放速度的关系式再利用Matlab优化工具箱反求出满足设计要求的弹簧最优化设计方案。本文的设计过程具有运算速度快精确度高 参数优化等优点，减少了仿真次数提高了释放速度的精确性在以弹簧作为推进装置的其它机构中也具有重要的参考价值。

# 参考文献:

[1]高滨．形状记忆合金在航天器分离机构上的应用[J]．航天返回与遥感，200526(1)：48-52.  
[2]IPollänen,H Martikka.Optimal Re -design of Helical Springs U-sing Fuzzy Design and FEM[J]．Advances in Engineering Soft-ware,2010 41:410-414.  
[3]L E Becker,GG Chassie,WL Cleghorn.On the Natural Fre-quencies of Helical Compression Springs [J]. International Journalof Mechanical Sciences ,2002 44:825- 841.  
[4]GG Chassie,LE Becker,WL Cleghorn.Mech.On the Bucklingof Helical Springs Under Combined Compression and Torsion [J].International Journal of Mechanical Sciences,1997,39(6) :697-704.  
[5]金旭星．基于约束随机法的气门弹簧设计[J]．小型内燃机与摩托车， $2 0 1 0 \ 3 9 ( \mathrm { ~ 3 } ) : \ 6 4 - 6 6 .$ （204号  
[6]张涛．圆柱螺旋弹簧的参数化设计及分析[D]．燕山大学,2012.  
[7]钱学毅．多股螺旋弹簧优化设计[J]．机械研究与应用,2005，18(4) :80 -81.  
[8]王冬冬 侯文英．可靠性优化理论在圆柱螺旋弹簧设计中的应用[J]．Equipment Manufacturing Technology,20O9-4:64 -66.  
[9]曾祥璞．圆柱螺旋弹簧的可靠性优化设计[J]．机械制造与研究,2005-5:12-15.  
[10]贾云海 张文明．螺旋弹簧多目标稳健优化设计[J]．北京科技大学学报,2009 31(6)：788-791.  
[11]马贵飞．圆柱螺旋压缩弹簧的多目标模糊优化设计[J]．机械设计与制造,2003-5:55-57.  
[12]M Paredes,M Sartor,C Masclet.An Optimization Process forExtension Spring Design[J].Computer Methods in Applied Me-chanics and Engineering,2001,191:783 -797.  
[13] Taktaka Mohamed ,et al．Dynamic Optimization Design of A Cylin-drical Helical Spring[J]．Applied Acoustics,2014,77:178-183.  
[14]Fakhreddine Dammak,et al.Finite Element Method for the StressAnalysis of Isotropic Cylindrical Helical Spring[J]．EuropeanJournal of Mechanics A/Solids,2005 24:1068-1078.  
[15]石丽娜 曾红,刘淑芬．基于ANSYS 的变刚度螺旋弹簧优化设计[J]．辽宁工业大学学报(自然科学版）,2009 29(1):44-47.  
[16]Hu Xingzhi,et al.Optimization Design of Satelite SeparationSystems Based on Multi - Island Genetic Algorithm[J]．Ad-vances in Space Research ,2014 53:870-876.  
[17]侯顺强 ,张丽丽．螺旋圆柱压缩弹簧优化设计[J]．煤矿机械,2006 27(2):202 -204.

![](images/46158522538112c52fb3b66a747a5bad6778731f8d53b9274fe0f20dc7ded924.jpg)

# [作者简介]

郑龙飞(1990-）男(汉族）,山东济南人，硕士研究生主要研究领域为飞行器设计。  
杨萱(1959-）女(汉族）北京人 研究员主要研究领域为飞行器设计。  
杨华(1962-）男(汉族）北京人 副教授,主要

研究领域为计算机辅助设计教学。