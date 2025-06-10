# 大型风电机组尾流效应非定常数值模拟研究

李 莉　高琳越　崔岩松刘永前(华北电力大学新能源电力系统国家重点实验室，北京102206)

摘要为了深入研究切变入流条件下大型风电机组尾流效应的非定常特性，以 NREL5MW大型海上风电机组为研究对象，建立了机组三维整机流场的全尺度结构化网格模型，基于滑移网格方法开展了风电机组额定工况下尾流效应的非定常数值模拟研究，并通过与NREL报告数据对比验证了模拟方法的可靠性。分析了风切变、机舱塔筒、叶片旋转等多种因素综合影响下风电机组性能参数的周期性变化规律，探讨了切变入流对尾流区风速分布的影响，以及尾流涡系的结构与发展情况。

关键词风电机组；尾流效应；非定常模拟

中图分类号：TK83 文献标识码：A 文章编号：0253-231X(2017)03-0541-07

# Research on Unsteady Numerical Simulation of Large-Scale Wind Turbine Wake Effect

LI Li GAO Lin-Yue CUI Yan-Song LIU Yong-Qian

StateKeyLaboratoryofAlternateElectricalPowerSystemwithRenewableEnergySources,NorthChinaElectricPower University,Beijing 102206,China)

Abstract Three-dimensional full-scale multi-block structured mesh model was established based on National Renewable Energy Laboratory (NREL） 5 MW large-scale offshore wind turbine, including the nacelle and tower. Unsteady numerical simulation of wind turbine wake under rated operating condition was carred out based on sliding mesh method,and the CFD results were validated through comparing with the NREL data. The periodic variation of wind turbine performance parameters considering influences of wind shear,nacelle,tower and blade rotation was analyzed.The effect of wind shear inflow on wind velocity distribution in wake region and the structure and development of wake vortex were discussed.

Key words wind turbine; wake effect;unsteady numerical simulation

# 0引言

尾流效应研究对于提高风能资源评估、风电场微观选址、风电场功率预测的技术水平具有重要意义。风电机组尾流效应导致两方面问题：一是尾流区风速降低，造成尾流区内风电机组发电量损失[1,2];二是尾流区湍流度增加[3,4]，影响风电机组的气动性能，增加疲劳载荷[5]，缩短机组寿命。对于海上风电机组，由于海上环境湍流强度低，尾流恢复慢，尾流效应的影响更加严重；此外，海上风电机组整体尺寸更大，垂直风切变、风轮旋转及塔筒对机组性能和尾流场的非定常影响也更明显。

数值模拟方法可以模拟机组尾流流动细节、揭示尾流机理，是目前尾流效应研究的一种主要方法。考虑到风电机组外形复杂、整机建模困难，许多学者采用不同方法对机组模型进行了简化，只对风轮进行建模仿真，忽略了机舱和塔筒的影响。对于风轮的处理，也有多种方法，如致动盘方法、致动线方法以及实体建模方法。FrancescoCastellani和AndreaVignarolib[采用致动盘方法模拟了风电场尾流，致动盘方法通过引入体积力来代替叶片，对风轮进行了很大程度简化，以牺牲准确度为代价减少了计算量，尤其是近场尾流模拟准确度。致动线方法是利用旋转线来表示叶片转动，致动线上分布有根据翼型数据和动量叶素理论得到的沿叶片展向变化的作用力[7]。Stefan[8]利用该致动线方法，分析了风轮近场尾流的速度场，较致动盘方法在近场尾流准确度有所提高，但仍无法得到叶片表面流动情况。王胜军、张明明等人[9基于致动线模型研究了切变入流风况下风力机尾流特性。根据叶片实际尺寸进行实体几何建模是更精确的方法，尤其是在近尾流区能够较准确地模拟出叶片表面流体流动情况，捕捉到更多的流动细节和现象。AbdelsalamAM等人[1o]对风轮进行实体建模，模拟了机组尾流，分析了叶片附近及尾流区详细的流动信息。但是，上述研究均对机组进行了不同程度的简化，未能够真实地反映出实际机组运行状态下风切变、机舱塔筒、叶片转动等多种因素对机组性能和尾流流动的综合影响。

为了深入研究切变入流条件下风电机组尾流效应的非定常特性，以NREL5MW大型海上风电机组为研究对象，建立了三维全尺度整机实体模型（叶片、机舱和塔筒)，采用结构化网格，开展了切变入流下风电机组自由尾流的非定常数值模拟，探讨了机组性能参数、尾流流场参数随叶片旋转的变化情况及尾流涡系结构。

# 1 非定常数值模拟方法

# 1.1风电机组几何建模

以美国可再生能源实验室(NationalRenewableEnergyLaboratory)NREL5MW大型海上机组为原型建立三维整机模型，机组主要参数如表1所示。整机几何建模主要包括叶片、轮毂、机舱和塔筒，其中准确建立叶片的几何模型最为重要。叶片由18个翼型截面和圆截面组成，叶片几何形状、采用的翼型及其所处位置如图1所示。

表1NREL5MW风电机组主要参数  
Table1 The main parameters of NREL 5 MW wind turbine   

<html><body><table><tr><td>机组参量</td><td>参数值</td></tr><tr><td>轮毂高度H/m</td><td>90</td></tr><tr><td>风轮直径D/m</td><td>126</td></tr><tr><td>轮毂高度处切入、额定、切出风速/(m/s)</td><td>3,11.4,25</td></tr><tr><td>风轮仰角0，锥角β/(°)</td><td>5,2.5</td></tr></table></body></html>

![](images/014ddcc75c381b32e825fcc33cd568cdf9afa5ae56b3194b48afda4a4ad145dc.jpg)  
图1叶片几何结构Fig.1 Blade geometry

为了模拟风电机组的真实运行状态，以1:1比例建模，且风轮建模中综合考虑了风轮仰角和锥角。基本依照实际尺寸建立了机舱和塔筒，塔筒直径从顶端 $( 3 . 8 7 ~ \mathrm { m } )$ 到底端 ${ \mathrm { ~ ( 7 ~ m ) ~ } }$ 渐变过度。最终建立的机组模型如图2所示。

![](images/2a1761cceced9ab443edd5599cfc3df1405a90af1cb7204f1fe5a65f5142fdf7.jpg)  
图2风电机组几何模型 Fig.2 Wind turbine geometric model

# 1.2计算域与网格划分

计算域如图3所示，机组轮毂中心位置与笛卡尔直角坐标系原点重合。三维计算域长度为 $3 5 D$ ，其中机组上游为 $5 D$ ，下游 $3 0 D$ ；高度为 $5 D + H$ ；宽度为 $1 0 D$ ，机组两侧各 $5 D$ 。计算域的整体尺寸能够避免边界效应的影响，并且满足尾流模拟的需要。计算域分为静止域和旋转域两部分。其中风轮所在的圆柱形计算域为旋转域，圆柱直径为 $1 . 2 D$ ，厚度为$0 . 1 D$ ，其余部分为静止域。

![](images/ebae1f88424072d46aad0e90a6170e6bb146a4dd490ba5502dfb572d051254a9.jpg)  
图3计算域Fig.3 Computational domain

对NREL5MW机组外部流场建立了全流场三维结构网格。风电机组整机结构化网格划分的难点在于几个关键部分的连接处：1)静止域中的机舱和塔筒的连接处；2)旋转域中叶片与轮毂的连接处。为解决该问题，采用了多块子域结构化网格建立方法，将整个计算域有效地分离成不同的块/区域。在机舱塔筒和叶片周围不规则区域分别建立O型块用于结构网格划分；其他规则区域同样划分为若干块，以便进行网格密度变化的控制。叶片、轮毂及机舱塔筒表面网格尺寸分别为 $0 . 0 1 \mathrm { ~ m ~ }$ 、 $0 . 1 \mathrm { ~ m ~ }$ 和 $0 . 2 \mathrm { ~ m ~ }$ ，网格总数约589万。局部网格如图4所示，叶片、轮毂、塔筒及各连接处的面网格均为规则的四边形，且通过控制节点数量和密度的变化，实现了对近壁面边界层网格的控制。

![](images/fc76f83c7771363fd0d365d25435515c56bf4cb326cee398989fd0c22381b09f.jpg)  
图4局部网格Fig.4 Section of mesh

# 1.3边界条件

入口风速为指数切变风速，如式（1）所示。式中， $Z$ 为所处高度， $U _ { \mathrm { z } }$ 为所处高度处风速， $H$ 为轮毂高度， $\alpha$ 为风切变指数，本文中为0.12对应海上风切变指数。轮毂中心位置处风速 $U _ { \mathrm { H } }$ 设定为风电机组额定风速 $1 1 . 4 ~ \mathrm { m / s }$ ，同时给定入口处均匀湍流强度 $1 3 \%$ ，与机组设计额定工况相对应。其它边界条件设置见表2。

$$
U _ { \mathrm { Z } } = U _ { \mathrm { H } } \left( { \frac { Z } { H } } \right) ^ { \alpha }
$$

# 1.4数值计算方案

尾流研究的流动问题属于黏性不可压缩三维流动，质量守恒方程、动量守恒方程和湍流模型共同组成封闭的控制方程组。湍流模型是将湍流的脉动值附加项与时均值相关联的特定关系式[11]，本算例中选取的 Standard $k { - } \varepsilon$ 模型是一种两方程的湍流模型，由Launder 和 Spalding[12] 提出，在求解大气边界层中风电机组流场分布中被广泛应用，并取得了良好的效果[13-17]。

# 表2边界条件设置

Table 2 Boundary condition settings   

<html><body><table><tr><td>边界名称</td><td>边界类型</td><td>备注</td></tr><tr><td>入口边界</td><td>速度入口</td><td>风切变指数0.12</td></tr><tr><td>出口边界</td><td>压力出口</td><td>101325Pa</td></tr><tr><td>顶面边界</td><td>速度边界</td><td>速度方向沿y轴</td></tr><tr><td>侧面边界</td><td>对称边界</td><td>二</td></tr><tr><td>底面边界</td><td>无滑移壁面</td><td>一</td></tr><tr><td>机舱、塔筒表面</td><td>无滑移壁面</td><td></td></tr><tr><td>叶片、轮毂边界</td><td>移动壁面</td><td>旋转轴为y轴， 转速12.1r/min</td></tr><tr><td>静止域与旋转 域交界面边界</td><td>内部交界面</td><td></td></tr></table></body></html>

采用有限体积法对控制方程进行离散，空间离散采用二阶迎风格式，时间项为一阶离散。采用基于压力的求解器求解控制方程，压力速度耦合算法为 SIMPLE算法。旋转区域流动的模拟选择了滑移网格(SMM)方法，该方法适合处理风轮尾迹对下游流场扰动问题，可以模拟扰动过程中的瞬态细节。采用非定常雷诺时均数值模拟方法，风轮旋转 $3 6 0 ^ { \circ }$ 为一个周期，通过对比 $2 ^ { \circ }$ ， $1 ^ { \circ }$ ， $0 . 5 ^ { \circ }$ 和 $0 . 2 ^ { \circ }$ 对应时间步长结果，最终确定 $0 . 5 ^ { \circ }$ 对应一个时间步长，其可以同时兼顾计算精度和计算成本。根据公式（2）计算得一个周期步数为720步，对应固定时间步长为$0 . 0 0 6 8 8 7 5 6 \mathrm { s } _ { \circ }$ 一个周期物理时长约 $5 \mathrm { ~ s ~ }$ ，总模拟物理时长 $3 3 0 ~ \mathrm { s } .$

$$
{ \mathrm { N u m b e r ~ o f ~ T i m e ~ S t e p s } } = { \frac { 3 6 0 } { n } }
$$

$$
{ \mathrm { T i m e ~ S t e p ~ S i z e } } = { \frac { n \times \pi } { 1 8 0 \times \omega } }
$$

式中， $\omega$ 为风轮转速， $n$ 为一个计算步对应旋转角度。

# 2模型验证

尾流研究中尾流对于机组性能的影响是重要评价指标之一，采用风轮的功率系数和推力系数两个机组性能参数验证数值计算方法可靠性。功率系数$C _ { \mathrm { P } }$ 反映来流风速和机组捕捉风能的关系，推力系数$C _ { \mathrm { T } }$ 反映风轮所承受载荷的情况，二者可分别由公式(3)，(4)计算得到。

$$
C _ { \mathrm { p } } = \frac { P } { \frac { 1 } { 2 } A V _ { \infty } ^ { 3 } \rho } = \frac { M \cdot \omega } { \frac { 1 } { 2 } A \rho V _ { \infty } ^ { 3 } }
$$

$$
C _ { \mathrm { T } } = { \frac { T } { { \frac { 1 } { 2 } } A \rho V _ { \infty } ^ { 2 } } }
$$

式中， $V _ { \infty }$ 为机组轮毂处的来流风速值， $\rho$ 为空气密度，值为 $1 . 2 2 5 ~ \mathrm { k g } / \mathrm { m } ^ { 3 }$ ， $P$ 为功率，等于风轮扭矩 $M$ 与转速 $\omega$ 的乘积， $T$ 为机组所受推力。扭矩 $M$ 和推力值 $T$ 由模拟结果中最后一个旋转周期内数据取平均获得。

相对误差定义如式(5)所示，式中， $a$ 为数值模拟结果的周期平均值， $b$ 为NREL报告中给出的额定值[18]。从表3的对比结果看出，非定常数值模拟结果与NREL5MW机组额定值之间误差较小，一定程度上验证了模型与模拟方法的可靠性，

$$
\mathrm { R e } = { \frac { \sum \left| a - b \right| } { b } }
$$

# 表3机组性能参数对比

Table3 Comparison of turbine performance parameters   

<html><body><table><tr><td></td><td>模拟计算值a</td><td>额定值b</td><td>绝对误差</td><td>相对误差</td></tr><tr><td>功率系数</td><td>0.43</td><td>0.46274</td><td>0.03274</td><td>7.6%</td></tr><tr><td>推力系数</td><td>0.74793</td><td>0.78502</td><td>0.03709</td><td>4.9%</td></tr></table></body></html>

# 3结果分析

在切变入流条件下，对额定工况运行的风电机组进行了非定常数值模拟。采用ANSYSFLUENT八核并行计算，以定常模拟收敛流场作为计算的初始流场，最后残差收敛至1E-6，各参数周期性收敛。

# 3.1机组性能参数

图5(a)、(b)分别为一个风轮旋转周期内机组推力系数、扭矩随方位角的变化。如图5所示，机组推力系数和扭矩呈现相同的周期性变化规律。在一个风轮的旋转周期内，推力系数呈现出3个周期的波动，极坐标图中呈现出类似“三叶草”形态。这是由于风电机组有3个叶片，风轮旋转导致叶片所处空间位置不断变化、同时受风切变的大气来流及塔影效应共同影响而造成的。当机组的叶片一个向正上方时 (方位角为0度)，由于风切变的影响，作用到三个叶片上的来流风速最大，机组相应的推力系数和扭矩也最大；当一个叶片旋转到最下方与塔筒重合时，一方面受塔影效应影响，另一方面切变的来流风速最小，造成推力系数和扭矩最小。

图6是将330s物理时间的推力系数和扭矩波动值去趋势之后进行快速傅里叶变换得到的功率谱。可以看出共有3个峰值，第一个为基波，其频率为$0 . 5 6 8 \mathrm { H z }$ ，正好对应于旋转频率的三倍，佐证了图 5得出的结论，其他的为谐波。

0.74 CT 0 W 0.735 330 30 0.730 300/ 60 50.73 0.72527 90 0.725 0.730 120 0.72 0.735 2 60120180 240 300 360 150 0/ 180 (a)推力系数的变化 (a) The change of thrust coefficient 3750 Torque/kN·m-1 0 30 3750 300 60 3650 270 3600 90 3650 3650 3700 240 120 3750 3600 60 120180 240300 360 3800F 210 180 150 (b)扭矩的变化 (b) The change of torque

![](images/c44a70b76f67f3cc60788a631469271d6ac1ad31aa2fb2aa9cb907aac741bfcc.jpg)  
图5一个周期内机组推力系数、扭矩随方位角变化 Fig.5 The change of thrust coefficient and torque during a rotation cycle   
图6 (a)推力系数功率谱(b)扭矩功率谱 Fig.6(a) Power spectrum of thrust coefficient(b) Power spectrum of torque

# 3.2速度场

# 3.2.1风轮处速度云图

图7为风轮位置垂直面的速度云图，反映了一个周期内3个叶片旋转一周的现象。图中“B1”代表叶片1，风轮逆时针旋转。3个叶片相同，所以(a)、(b)，(c)、(d)，(e)、(f)两两组成一个小周期，一个旋转周期内呈现出三个小周期的变化。图中红色代表高风速，蓝色代表低风速，可以清晰看到，当叶片在下方时，叶片后低速区范围更大。这是由于风切变条件下，随着高度增加风速也增大，在一个风轮旋转周期中，当叶尖从最低处旋转到最高处时风速增大 $\mathrm { 2 ~ m / s }$ 以上。这必然形成一种周期性变化的气动力作用在叶片上，最终导致叶片旋转过程受到周期性疲劳载荷。

![](images/b684694a33dd742134e94ce14c30da5beb41be1d920f27486fd3dd8f0dc342f2.jpg)  
图7一个旋转周期内风轮位置垂直面速度云图 Fig.7 Velocity contours in the $\mathbf { x z }$ plane during a rotation cycle

# 3.2.2风速垂直方向分布对比

分别在机组下游 $0 . 2 D , \ 0 . 5 D$ 和 $1 D$ 位置处沿垂直方向（ $z$ 轴)取得风速值 $\mathbf { \sigma } _ { v }$ ，计算得到6个时刻无量纲风速 $v / v _ { \infty } ( v _ { \infty } { = } 1 1 . 4 ~ \mathrm { m / s } )$ 沿垂直方向 ( $z$ 轴)的变化曲线如图 $8 ( \mathrm { a } ) \mathrm { \sim ( c ) }$ 所示。每个时间间隔内叶片旋转30度。 $z / D$ 值为0和 $\pm 0 . 5$ 位置分别代表轮毂中心和风轮扫掠面上下边界。

由图8(a）中可见， $- 0 . 5 < z / D < 0 . 5$ 区域各位置处速度值随时间的变化产生明显波动，这主要是由于叶片旋转的影响。 $z / D = 0$ 附近区域风速较低，这是由于 $Y = 0 . 2 D$ 位置处离机组较近，受到机舱的遮挡影响。由于风切变的影响， $z / D = - 0 . 5$ 区域风速明显小于 $z / D = 0 . 5$ 区域，与速度云图分析相对应，叶片旋转将受到周期性疲劳载荷。

对比图 $8 ( \mathrm { a } ) \mathrm { \sim ( c ) }$ 可见，不同时刻的速度波动变化随着机组下游距离的增加逐渐消失，说明随机组下游距离的增加，风轮旋转对速度分布的影响程度逐渐减弱。叶片旋转的作用仅对机组后方较小范围风速分布情况产生影响，远尾流区风速分布基本不受叶片旋转影响。

![](images/2e5ca807b02841901eeb74e1848623f69820bf7d3504f4671853cca18750680e.jpg)  
图8不同时刻垂直方向无量纲风速分布廓线Fig.8Vertical profiles of normalized velocityat differentmoments

# 3.3尾流涡系结构

尾迹的发生发展是尾流机理研究的重点之一，图9中所示的 $Q$ 准则等值面可体现尾迹涡系结构，等值面由 $Q = - 0 . 0 5$ ， $- 0 . 1$ ， $^ { - 1 }$ 三个等值面合成，并由流向速度着色。 $Q$ 准则是最为常用的描述尾涡结构的参数，其是通过三个方向的速度张量求解获得，如公式（6）所示。

$$
Q = { \frac { 1 } { 2 } } ( { \overrightarrow { \omega } } \times { \overrightarrow { \omega } } - { \overrightarrow { s } } \times { \overrightarrow { s } } )
$$

式中， $\overrightarrow { \omega }$ 为涡量， $\overrightarrow { s }$ 为应变率，具体如式（7）所示，分别为不同方向分量。

$$
\begin{array} { r } { \overrightarrow { \omega } = \left\{ \begin{array} { l } { \omega _ { \mathrm { y z } } = \displaystyle \frac { 1 } { 2 } \left( \frac { \partial w } { \partial y } - \frac { \partial v } { \partial z } \right) } \\ { \omega _ { \mathrm { z x } } = \displaystyle \frac { 1 } { 2 } \left( \frac { \partial u } { \partial z } - \frac { \partial w } { \partial x } \right) } \\ { \omega _ { \mathrm { x y } } = \displaystyle \frac { 1 } { 2 } \left( \frac { \partial v } { \partial x } - \frac { \partial u } { \partial y } \right) } \end{array} \right\} \mathrm { , } } \end{array}
$$

$$
\begin{array} { r } { \overrightarrow { s } = \left\{ \begin{array} { l } { s _ { \mathrm { x y } } = \displaystyle \frac { 1 } { 2 } \left( \frac { \partial u } { \partial y } + \frac { \partial v } { \partial x } \right) } \\ { s _ { \mathrm { x z } } = \displaystyle \frac { 1 } { 2 } \left( \frac { \partial u } { \partial z } + \frac { \partial w } { \partial x } \right) } \\ { s _ { \mathrm { y z } } = \displaystyle \frac { 1 } { 2 } \left( \frac { \partial v } { \partial z } + \frac { \partial w } { \partial y } \right) } \end{array} \right\} } \end{array}
$$

![](images/73b96eab25e585bfed4766ee5c90bd7584151d7c4747cace106b327465da7a48.jpg)  
图9尾流涡系结构Fig.9 Structure of wake vortex

从图9中可清晰地看到由于三维旋转作用造成的涡系结构，主要由三个叶片的叶尖涡和叶根处的涡系组成。叶尖涡呈螺旋状，旋转方向与叶片相反，随着尾迹向下游扩散，涡量逐渐减小至破碎。叶尖涡和叶根涡之间存在一定的相互干扰，并且在叶根的位置首先出现涡破裂，这时在叶根位置叶片表面应该已经出现了较为明显的流动分离。

# 4结论

本文以NREL5MW大型海上风电机组为研究对象，综合考虑风切变、塔影效应和风轮旋转效应的影响，对风电机组自由尾流进行了非定常数值模拟。通过与 NREL报告数据对比验证了模拟方法的可靠性，得到如下结论：

1）由于风切变和塔影效应的影响，机组推力系数和扭矩随风轮旋转呈现周期性变化，变化频率等于旋转频率的三倍。2）叶片旋转对尾流区风速分布的影响随距机组距离的增加而减小，远尾流区风速分布基本不受叶片旋转影响。3)尾流涡系结构主要由三个叶片的叶尖涡和叶根涡组成，叶尖涡呈与叶片旋向相反的螺旋线状，二者存在相互干扰，并在机组后方发生破裂。

# 参考文献

[1]Gonzalez-Longatt F,Wall P,Terzija V.Wake Effect in Wind FarmPerformance:Steady-State andDynamic Behavior[J].Renewable Energy, 2012,39(1):329-338   
[2]Husien W,El-Osta W,Dekam E.Effect of the Wake Behind Wind Rotor On Optimum Energy Output of Wind Farms[J].Renewable Energy, 2013,49(1):128-132   
[3] Brand J,Peinke J,Mann J. Turbulence and Wind Turbines [J]．Journal of Physics: Conference Series，2011, 318(7): 687-700   
[4] Breton S P,Nilsson K, Olivares-Espinosa H. Study of the Influence of Imposed Turbulence on the Asymptotic Wake Deficit ina Very Long Line of Wind Turbines [J].Renewable Energy, 2014,70(2):153-163   
[5]Hansen K S,Larsen G C.Dependence of Offshore Wind Turbine Fatigue Loads On Atmospheric Stratification [J]. Journal of Physics: Conference Series,2014, 524(1): 012165   
[6] Castellani F,Vignaroli A.An Application of the Actuator Disc Model for Wind Turbine Wakes Calculations [J]. Applied Energy,2013,101(1):432-440   
[7] Sorensen J N, Shen W Z. Numerical Modeling of Wind Turbine Wakes [J]. Journal of Fluids Engineering,2002, 124(2): 393-399   
[8] Ivanell S,Mikkelsen R,Sorensen JN,et al. Stability Analysis of the tip Vortices of a Wind Turbine [J].Wind Energy,2010,13(8):705-715   
[9]王胜军,张明明,刘梦亭,等.切变入流风况下风力机尾流特 性研究[J].工程热物理学报,2014,35(8)：1521-1525 Wang Shengjun, Zhang Mingming,Liu Mengting,et al. Study of Wake Characteristics of Wind Turbine Operating in Shear Inflow [J]. Journal of Engineering Thermophysics. 2014,35(8): 1521-1525   
10] Abdelsalam A M,Boopathi K,Gomathinayagam S,et al. Experimental and Numerical Studies on the Wake Behavior of a Horizontal Axis Wind Turbine [J].Journal ofWind Engineering& Industrial Aerodynamics,2014, 128(5): 54-65   
[11]Tu J,Yeoh GH,Liu C.Computational Fluid Dynamics: A Practical Approach [J].Artificial Organs,2009,33(9): 727-732   
[12]Launder BE,Spalding DB.The Numerical Computation of Turbulent Flows [J].Computer Methods in Applied Mechanics and Engineering,1974,3(2):269-289   
[13]Kasmi A E,Masson C.An Extended K-Epsilon Model for Turbulent Flow Through Horizontal-Axis Wind Turbines [J].Journal of Wind Engineering and Industrial Aerodynamics,2008,96(1):103-122   
[14]ParenteA,Gorle C,BeeckJV,et al.ImprovedK-Epsilon Model and Wall Function Formulation for the RANS Simulation of ABL Flows [J]. Journal of Wind Engineering and Industrial Aerodynamics,2011, 99(4):267-278   
[15]Balogh M O S,Parente A,Benocci C.RANS Simulation of ABL Flow Over Complex Terrains Applying an Enhanced K-Epsilon Model and Wall Function Formulation:Implementation and Comparison for Fluent and OpenFOAM [J].Journal of Wind Engineering and Industrial Aerodynamics,2012,104:360-368   
[16]Richards PJ,Hoxey R P.Appropriate Boundary Conditions for Computational Wind Engineering Models Using theK-Epsilon Turbulence Model[J].Journal of Wind Engineering and Industrial Aerodynamics,1993,46:145-153   
[17]Yan J,Gregory-SmithD,Karanjkar A.CFD Simulations of Three-Dimensional Flow in Turbomachinery Applications [C]//Proceedings of the Third International Conference on Engineering Computational Technology. CivilComp press,2002:91-92   
[18]Hand M M,Simms D A,FingershLJ,et al.Unsteady Aerodynamics Experiment Phase VI:Wind Tunnel Test Configurations and Available Data Campaigns [R].United States:National Renewable Energy Laboratory, 2001:1- 299