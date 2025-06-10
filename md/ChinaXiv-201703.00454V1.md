# 淹没水射流流场的DES 模拟与实验研究

张伟康灿潘宸朱洋(江苏大学能源与动力工程学院，镇江 212013)

摘要为了深入分析淹没水射流流动特征，综合采用数值模拟和流场测量进行研究。数值模拟应用基于 S-A 模型的DES 方法，并通过圆柱绕流验证数值方法的有效性；流场测量采用粒子图像测速技术。研究表明：采用的数值模拟方案可以准确预测圆柱的升力系数、阻力系数和尾流中旋涡脱落的斯特劳哈数；模拟和实验获得的射流速度沿轴向和径向的衰减规律吻合；模拟获得的射流半值宽度线的斜率小于实验结果，主要是由于对剪切层厚度的预测不足所致；在垂直于射流束横截面上，涡量呈现双峰分布；射流的涡量随着射流发展呈总体衰减趋势。

关键词圆柱绕流；淹没水射流；离散涡模拟；雷诺数；喷嘴中图分类号：O358 文献标识码：A 文章编号：0253-231X(2017)03-0522-07

# DES Simulation and Experimental Investigation of Submerged Waterjet Flow

ZHANG WeiKANG CanPAN ChenZHU Yang (School of Energy and Power Engineering,Jiangsu University，Zhenjiang 2l20l3,China)

Abstract Numerical simulation and fow measurement are performed to explore the flow characteristics of submerged waterjet. The numerical simulation is based on the DES method and S-A model,and the validity of the numerical scheme is substantiated with flows around a circular cylinder. Particle image velocimetry is utilized to obtain flow velocity distribution.The results show that the lift and drag coeffcients of the cylinder and the Strouhal number of the vortex shedding in the wake are accurately predicted with the numerical technique.Regarding the waterjet, numerically obtained jet velocity attenuation in streamwise and lateral directions agrees well with the experimental results. The approximate slope of the semi-width curve numerically obtained is smaler than its counterpart associated with experiment,as is mainly ascribed to the underestimation of the shear layer thickness with numerical approach. Dual-peak distribution of vorticity arises on the cross section of the waterjet stream. Vorticity magnitude decreases with the jet progression.

Key wordsflow around a cylinder; submerged waterjet; detached eddy simulation; reynolds number; nozzle

# 0引言

淹没水射流是射流的重要类型之一。近年来，淹没水射流的工程应用范围不断延伸。从目前的相关研究来看，淹没水射流的实验研究难度较大，一是采用光学手段进行流场测量的难度较大，在介质中撒播的示踪粒子对介质的跟随性差且分布不均匀；二是流场中可能会出现空化现象，对于空化发生机理的认识、空化的瞬态发展过程和空化形态的捕捉又属于另一类难题。从淹没水射流流场中的流动特征来看，其最为明显的特征就是主流与静止的环境水体之间的相互作用，静止水体阻碍主流的发展，而主流与环境水体之间的强剪切作用又可能衍生出新的流动结构。从完整地描述淹没水射流的角度出发，数值模拟能够发挥有效的作用。

目前的湍流数值模拟方法主要有四种：基于雷诺平均Navier-Stokes方程(RANS）的模拟，直接数值模拟(DNS)，大涡模拟(LES）以及分离涡模拟(DES)。限于计算机硬件水平，DNS方法对于高雷诺数流动的数值模拟较难实现。LES方法的计算量也较大而且其对于边界层发展和分离的模拟欠准确。Spalart [1]在1997年提出了DES 方法，其基本思想是在近壁区采用RANS方法，用湍流模型模拟其中的小尺度脉动运动；在远离壁面区域，将湍流模型耗散项中的湍流尺度参数与一常数相乘，发挥与亚格子雷诺应力模型相似的作用，同时保证了近壁区流动和远离固体壁面的区域的模拟逼近物理真实。从对大尺度流动结构的捕捉来看，DES方法的适应性较强，可以作为对实验研究的有效补充。

本文首先设计了基于 Spalart-Allmaras 模型的DES数值模拟方案，在雷诺数为 $2 \times 1 0 ^ { 4 }$ 条件下对圆柱绕流流场进行模拟以验证数值模拟方案的有效性，将模拟获得的升力系数、阻力系数和斯托劳哈尔数与实验结果进行对比分析。进而采用DES方法对淹没水射流流场进行模拟，模拟中综合考虑射流的速度衰减、半值宽、涡量分布等表征射流特征的重要因素；同时采用粒子图像速度场仪辅以荧光粒子对淹没水射流流场进行测量，结合数值模拟和实验结果对淹没水射流流动进行系统性的解释，并对比数值模拟与实验结果之间的异同。

# 1数值方法

# 1.1流体控制方程

对于带有固体边界的非定常黏性流动，采用Navier-Stokes方程作为控制方程，其积分形式为：

$$
\frac { \partial } { \partial t } \int _ { \Omega } \vec { W } \mathrm { d } \Omega + \oint _ { \partial \Omega } \Big ( \vec { F _ { \mathrm { c } } } - \vec { F _ { \mathrm { v } } } \Big ) \mathrm { d } S = 0
$$

式中， $W$ ， $F _ { \mathrm { c } }$ ， $F _ { \mathrm { v } }$ 分别为守恒矢量、对流通量和黏性通量，其具体含义见文献 [2]。

# 1.2 Spalart-Allmaras 模型

S-A模型以涡黏系数 $\tilde { v }$ 为变量，它的积分形式为：

$$
\frac { \partial } { \partial t } \int _ { \Omega } \tilde { v } \mathrm { d } \Omega + \oint _ { \partial \Omega } \left( F _ { \mathrm { c , T } } - F _ { \mathrm { v , T } } \right) \mathrm { d } S = \int _ { \Omega } Q _ { \mathrm { T } } \mathrm { d } \Omega
$$

式中：

$$
F _ { \mathrm { c , T } } = \tilde { v } V _ { \mathrm { r } }
$$

$$
F _ { \mathrm { v , T } } = { \frac { 1 } { \sigma } } \left( { \frac { \mu _ { L } } { \rho } } + { \tilde { v } } \right) \left( n _ { x } { \frac { \partial { \tilde { v } } } { \partial x } } + n _ { y } { \frac { \partial { \tilde { v } } } { \partial y } } + n _ { z } { \frac { \partial { \tilde { v } } } { \partial z } } \right)
$$

$$
Q _ { \mathrm { T } } = \left( c _ { \mathrm { b 1 } } S + \varDelta \cdot V \right) \tilde { v } - c _ { \mathrm { w 1 } } f _ { \mathrm { w } } \left( \frac { \tilde { v } } { d } \right) ^ { 2 } + \frac { c _ { \mathrm { b 2 } } } { \sigma } ( \varDelta \tilde { v } ) ^ { 2 }
$$

分别为湍流涡黏系数的对流通量、黏性通量和源项，其具体含义以及计算常数参见文献[3]。

# 1.3 DES 湍流模型

Spalart通过修改Spalart-Allmaras模型中的长度量 $d$ 提出了基于S-A模型的DES方法。其微分形式为：

$$
\begin{array} { c } { \displaystyle \frac { \mathrm { D } \tilde { \boldsymbol { v } } } { \mathrm { D } t } = c _ { \mathrm { b 1 } } \tilde { S } \tilde { \boldsymbol { v } } - c _ { \mathrm { w 1 } } f _ { w } \left[ \frac { \tilde { \boldsymbol { v } } } { d } \right] ^ { 2 } + } \\ { \displaystyle \frac { 1 } { \sigma } [ \boldsymbol { \nabla } \cdot ( ( \boldsymbol { v } + \tilde { \boldsymbol { v } } ) \boldsymbol { \nabla } \tilde { \boldsymbol { v } } ) + c _ { \mathrm { b 2 } } ( \boldsymbol { \nabla } \tilde { \boldsymbol { v } } ) ^ { 2 } ] } \end{array}
$$

式中， $d$ 为空间点到固体壁面的最短距离， $\tilde { S }$ 为修改后的涡量表达式。DES方法将上式中的 $d$ 用$\tilde { d } \mathrm { = } ( d , \ C _ { \mathrm { D E S } } \varDelta )$ 来代替。其中 $\varDelta$ 为当地网格的最大尺寸， $C _ { \mathrm { D E S } }$ 为常数，取0.65。显然，在固体壁面附近有 $d { < } C _ { \mathrm { D E S } }$ ，于是 ${ \tilde { d } } = d$ ，这时候的DES 模型就是式(4)所描述的 S-A模型。当 $d { > } C _ { \mathrm { D E S } }$ 时， $\tilde { d } = C _ { \mathrm { D E S } } \varDelta$ 此时湍流涡黏系数的衰减由当地的网格尺度来确定。通过式 (4)可以得知，当湍流涡黏系数的源项和湍流涡黏系数的衰减项达到平衡时， $\tilde { v }$ 正比于 $\tilde { S } d ^ { 2 }$ ，如果$\tilde { d } = C _ { \mathrm { D E S } } \varDelta$ ，则 $\tilde { v }$ 正比于 $\tilde { S } \varDelta ^ { 2 }$ ，此即亚格子模型。

网格布置是影响DES求解结果准确性的关键。近壁区网格的最大间距和网格点到壁面的距离决定了涡黏性模型与亚格子模型的交界面位置，如果壁面附近过度加密，就会过早地引入亚格子模型，因此对边界层的分辨尤为重要。通过引入参数 $r _ { \mathrm { d } }$ 确保边界层内为涡黏性模型，将长度尺寸 $\tilde { d }$ 关系式改写为

$$
\tilde { d } = d - f _ { \mathrm { d } } \operatorname* { m a x } \left( 0 , \mathrm { d } - C _ { \mathrm { D E S } } \varDelta \right)
$$

其中:

$$
f _ { \mathrm { d } } = 1 - \operatorname { t a n h } ( ( 8 r _ { \mathrm { d } } ) ^ { 3 } )
$$

$$
r _ { \mathrm { d } } = \frac { v _ { \mathrm { t } } + v } { \sqrt { U _ { i , j } U _ { i , j } } \kappa ^ { 2 } \mathrm { d } }
$$

$f _ { \mathrm { d } }$ 在边界层内为0，在其他区域等于1, $\boldsymbol { v } _ { \mathrm { t } }$ 为运动涡黏性， $\mathbf { \sigma } _ { v }$ 为运动分子黏性， $U _ { i , j }$ 为速度梯度， $\kappa { = } 0 . 4 1$ 。通过函数关系实现亚格子应力模型和涡黏性模型的切换。

# 2数值算例验证

圆柱绕流是验证数值模拟的典型流动。李燕玲等[4]以及尹纪富等[5]都采用DES 方法对圆柱绕流问题进行了模拟，并且都取得了与实验数据相近的结果。此处为校验本文所设计的DES方案的有效性，选取雷诺数为 $2 \times 1 0 ^ { 4 }$ 的圆柱绕流为对象，模拟圆柱绕流时出现的非定常流动特征。

# 2.1圆柱绕流验证

# 1）网格划分和边界条件

坐标系定义如图1所示：坐标原点为圆柱轴线的中点， $X$ 为来流速度方向， $Z$ 为圆柱轴线方向。以圆柱直径 $D$ 为特征尺度，整个长方体计算域的尺寸为： $- 1 5 D \leqslant X \leqslant 3 5 D$ 、 $- 1 0 D \leqslant Y \leqslant 1 0 D$ 和$- 5 D \leqslant Z \leqslant 5 D$ ，如图1所示。该计算域可以保证来流的均匀性和尾流的充分发展。在靠近圆柱表面处进行网格加密，以圆柱的轴截面为中心，在 $8 D \times 8 D$ 范围内沿径向按比例逐步放大网格，如图2所示。计算域的网格总数约为159万。

所有的固体壁面处采用无滑移边界条件，计算域的入口设定均匀来流条件，出口采用压力出口边界条件，出口面上的压力梯度设为零。以均匀进口速度分布作为非定常计算的初始条件，采用SIMPLE压力速度耦合迭代方法，压力项离散采用二阶精度。根据雷诺数的量级，将时间步长设为 $\mathrm { 0 . 0 2 5 \ : s }$ 。

![](images/6e68528c72800912dc56e15f643dcebc6140d19e438aef81cc0cabeb984776e3.jpg)  
Fig.1 Computational domain for flows around a circular cylinder

![](images/e1c6f54c6461b2e0fd7436901feb6f23caa1e65794cff0eb695403ea378461f5.jpg)  
图1圆柱绕流计算域模型  
Fig.2 Mesh deployment on the cross section vertical to cylinder axis

从速度分布的形态来看，尾流基本上呈现振荡状态，且越靠近圆柱，外部流动与尾流间的速度梯度越大，这也解释了近圆柱区下游涡量值高的原因。

# 表1圆柱绕流参数对比

Table 1 Comparison of parameters associated with flows around a circular cylinder   

<html><body><table><tr><td>Re=2×104</td><td>Ca时均值</td><td>C幅值</td><td>St</td></tr><tr><td>Lu [6](RANS)</td><td>1.15</td><td>0.60</td><td>0.20</td></tr><tr><td>Sun(DNS)</td><td>1.30</td><td>0.80</td><td>0.29</td></tr><tr><td>Yokuda [7](实验)</td><td>1.20</td><td>1</td><td>0.21</td></tr><tr><td>苏铭德[8](LES)</td><td>1.22</td><td>0.80</td><td>0.23</td></tr><tr><td>本文结果</td><td>1.18</td><td>0.62</td><td>0.22</td></tr></table></body></html>

![](images/ee7c50a39c01e784d6dc1930654a1423ff86cdb3503fb86bd087329d3c014427.jpg)  
图2圆柱轴截面网格分布  
图3瞬时流场分布  
Fig.3 Instantaneous flow characteristics

# 2）圆柱绕流计算结果分析

阻力系数和升力系数反映了流体作用在圆柱表面上的载荷，而斯特劳哈数则用来描述圆柱尾流中旋涡的脱落，该3个无量纲数对于圆柱绕流问题最具代表性。在表1中，将数值计算得到的时均阻力系数 $C _ { \mathrm { d } }$ 、升力系数 $C _ { 1 }$ 和斯特劳哈数 $S _ { \mathrm { t } }$ 与文献中的实验结果和模拟结果进行了对比。可以看出，和其他方法相比，本文的模拟结果更接近实验结果。

尾流中旋涡的周期性脱落是圆柱绕流的特征现象，随着旋涡的脱落，圆柱所受到的阻力和升力会出现周期性变化。图3中表示出了垂直于圆柱轴截面上的瞬时流场结构，分别以压力等值线和速度分布表示。可以看出，尾流中形成两列上、下交替脱落的旋涡，离开圆柱的流向距离越大，旋涡强度越弱；

为深入理解圆柱绕流中涡结构的三维形态，提取了瞬时涡量等值面，并从图4所示的视角进行观察。涡量等值面表达了涡结构之间的黏连、合并与分离，并反映出涡结构的尺度与涡强度。从图4可以看出，在主流方向上存在着交替发展的涡街现象，沿圆柱轴向还出现涡结构间的相互交叉。该三维特征与已发表的实验和模拟结果相近[9,10]。随着主流向下游发展，涡结构的整体强度减弱，尤其是上下两端的涡结构逐渐崩塌，圆柱绕流的二维假设不复成立。从对大尺度流动结构的捕捉和对流场宏观参数的求解来看，本文的DES方案具有明显的优势。

![](images/82251c16e647bb7a7bf1505b018f10e8f831cb1bb792a87871e8616814133bb8.jpg)  
图4三维瞬时涡量图 Fig.4 Three-dimensional instantaneous distribution pattern of iso-vorticity elements

# 2.2淹没水射流的数值模拟方案

采用经过验证的DES方案对淹没水射流进行数值模拟。采用的射流喷嘴出口直径为 $D { = } 2 . 0 ~ \mathrm { m m }$ 整个计算域设为长方体，便于直角坐标系的应用；射流介质为常温水。在计算域入口设置速度边界条件,设定喷嘴的入口速度分别为7.0、9.5和 $1 8 . 0 ~ \mathrm { m / s }$ 业计算域的直角坐标系定义如图5所示：将喷嘴出口中心定义为坐标原点， $Z$ 方向为主流方向， $X$ 、 $Y$ 为垂直于来流的速度方向。环境水体的计算域尺寸大小为： $- 1 5 \mathrm { \ m m } { \leqslant } X { \leqslant } 1 5 \mathrm { \ m m }$ ， $- 1 5 \ \mathrm { m m } { \leqslant } Y { \leqslant } 1 5$ mm, $- 1 5 \mathrm { \ m m } { \leqslant } Z { \leqslant } 1 0 0 \mathrm { \ m m }$ 。对计算域网格进行局部加密，如图6所示。计算域的网格总数约为128万。

![](images/7688a1ada839174f9ba2fcebfed19511c05152ac1b15ebea8b9a7f5b09d94e58.jpg)

![](images/1bfb35c71123e7ea95e8a087e864ee49242504b1f107b770aa239d2f5fb60ec3.jpg)  
图5淹没水射流计算域几何模型 Fig.5 Computational domain for submerged waterjet   
图6计算域截面网格  
Fig.6 Cross-sectional view of meshes discretizing the computational domain

以进口边界条件作为计算的初始条件，采用SIMPLE压力速度耦合迭代方法，压力项离散采用二阶精度，时间步长设为0.0001s。

# 3淹没水射流光学测试方案

为了进一步评估DES数值模拟结果的有效性并补充射流信息，采用粒子图像测速技术（PIV）[11] 对淹没水射流流场进行了实验研究。根据射流压力与喷嘴出口流速之间的关系，在实验中设定与数值模拟相同的三种射流速度：7.0、9.5与 $1 8 ~ \mathrm { m / s }$ 。淹没射流实验中，由于射流与周围水体间的速度梯度较大，可能会产生空化现象，示踪粒子的物性和播洒方案极为关键。本次实验中选用罗丹明B作为示踪粒子。罗丹明B对光线最佳吸收和放射的波长分别为526nm和 $5 8 0 ~ \mathrm { n m }$ ，能合适的吸收光谱，可以很好的配合激光设备的使用。选取的罗丹明B的密度为0.79$\mathrm { g / m L }$ ，在水中的溶解度为 $1 ~ \mathrm { m g / m L }$ ，配置水溶液浓度为 $\mathrm { 1 5 ~ m g / m L }$ 。PIV测试系统的基本原理如图7所示。与一般实验不同的是，此处直接在被测流场中均匀散布示踪粒子罗丹明B，因为通过实验的内循环系统，粒子能很快地分散均匀，当流场稳定后，利用偏光镜组将脉冲激光转化为脉冲片光，入射至需要测试的流场区域，然后通过高速数码相机进行双帧双曝光图像采集，记录该时刻的粒子图像并储存，最后通过图像处理软件，采用互相关算法进行图像处理，获得瞬时流场的速度分布。

实验中采用Lavision公司生产的PIV系统，示踪粒子直径为 ${ 2 0 } { \sim } 5 0 ~ \mu \mathrm { m }$ 。图像采集系统主要包括高速数码相机、双脉冲激光器、导光及偏光镜组部件、同步器及装有采集系统软件的计算机。CCD 相机型号为ImagerProSX5M，其分辨率为 $2 4 5 6 \times 2 0 5 8$ pixel，像素尺寸为 $3 . 4 5 ~ { \mu \mathrm { m } } \times 3 . 4 5 ~ { \mu \mathrm { m } }$ ，最大帧频14.5$\mathrm { H z }$ ，双帧双曝光模式下，最小帧之间的时间间隔为

$6 0 0 ~ \mathrm { n s }$ ，镜头采用 Nikon 型号为 AF Nikkor $\mathrm { 5 0 ~ m m }$ $\mathrm { f / 1 . 8 ~ D }$ 的相机镜头；激光器采用Nd:YAG 双脉冲激光器，最高频率 $\mathrm { 1 5 ~ H z }$ ，最大能量 $7 0 ~ \mathrm { m J }$ ，光波长为 $5 3 2 ~ \mathrm { n m }$ 。图像采集及处理采用DaVis和Tecplot软件。

![](images/b6a482f80ba446a2936e1a1d7b1b7859f12821efaf97cbb07ca4382fa76412d3.jpg)  
图7PIV测试系统示意图 Fig.7 Schematic view of the PIV measurement system

# 4结果分析与讨论

# 1)速度分布

对于非淹没水射流，当射流进入自相似区后，无量纲化的速度剖面与雷诺数和距喷嘴的距离无关[12]。而对于淹没水射流，尚无相关的报道。

图8所示为射流轴线上的无量纲速度分布。在距喷嘴最近的一段轴向距离 $( Z / D < 1 0 )$ 内，由于喷嘴出口的空化现象和流束表面的反光现象，PIV测速时的采样规律性差，无法获得稳定的采样信号，所以实验结果从 $Z / D > 1 0$ 开始。从模拟结果来看，三条轴向速度衰减曲线基本重合，轴向速度衰减的相似规律明显。在近喷嘴区，模拟结果中轴线上的射流速度大小基本保持不变，该段为射流的初始段，射流的集束性强。实验获得的三条曲线不光滑是由于环境水体对射流的扰动已影响到射流轴线，这一点与非淹没射流有着明显的区别[13]。尽管如此，三条实验曲线的形态并无明显的突变，并且与淹没射流轴向速度衰减理论曲线[14]吻合较好。从模拟结果与实验结果的对比来看，速度沿流向的变化趋势较吻合，证明了淹没水射流的能量的沿程衰减规律。

图9所示为射流初始速度 $1 8 ~ \mathrm { { m / s } }$ 时，三种实验工况以及对应的三组数值模拟在距离喷嘴50$\mathrm { m m }$ 、 $6 0 ~ \mathrm { m m }$ 和 $8 0 \ \mathrm { m m }$ 处径向速度的无量纲化分布。可以发现实验与模拟的结果高度吻合，射流各断面上轴向流速的径向分布具有很强的自相似性。并且通过与已发表文献[15]中的计算结果进行对比，发现径向速度衰减曲线基本重合。因此，淹没射流径向速度衰减规律可用高斯分布描述为：

$$
U / U _ { m } = \exp ( - 0 . 7 4 ( x / y _ { 1 / 2 } ) ^ { 2 } )
$$

![](images/3027a3b4d074d4db259c72448b1c189329925cc0e7a822ccf80bbbf855b277ca.jpg)  
图8轴向速度的沿程衰减

![](images/0fd3055f89b174ae7a09cd3ed6ad425b05d806c02ddb47040c6773ddc0f362cc.jpg)  
Fig.8 Attenuation of axial velocity in streamwise direction   
图9径向流速的无量纲化分布 Fig.9 Velocity distribution in lateral direction

# 2）淹没水射流的半值宽特征

图10所示为淹没水射流的无量纲半值宽度（射流轴向流速最大值的一半点距离轴线的径向距离)分布。在不同压力条件下，模拟获得的三条半值宽线基本重合，且在近喷嘴区 $( Z / D < 1 0 )$ 半值宽大小基本保持不变，而实验获得的三条曲线也基本重叠。然而实验和数值模拟结果之间存在一定的偏差。半值宽斜率的大小表征了射流径向的扩展程度，根据前人的研究结果，淹没射流半值宽斜率大小约为0.095。若对模拟和实验的结果进行线性拟合，则实验数据线的斜率明显大于模拟结果，且实验的速度半宽扩展率近似为0.095。从速度分布的角度来看，射流速度自轴线沿径向逐渐减小，在模拟结果中反映这一趋势较为平缓且速度梯度较小；在实验结果中，在射流束与环境水体交界面附近，出现剧烈的速度下降即较高的速度梯度，所以导致图10所示的差异。从另一角度考虑，数值模拟中对于淹没水射流受到环境水体的阻力预测不足。

![](images/a85a39deaf6c54d05272597272acc0703b9999b969d02c277e4ec055d1c44f21.jpg)  
图10半值宽的无量纲化处理

# 3)射流场中的涡量分布

图11所示为射流初始速度 $1 8 ~ \mathrm { m / s }$ 时数值模拟和实验获得的径向涡量分布。图中以喷嘴直径为轴向距离的无量纲基准，以径向涡量最大值为纵坐标的无量纲化基准。从涡量图可以看出，在不同截面上DES数值模拟与实验的平均涡量分布相近，在射流轴线上，涡量的绝对值近似为0，自射流轴线沿径向至射流两侧边界，涡量先增大后减小，并且轴线两侧的涡量值具有明显的对称性。这是因为轴线为射流的核心区，轴向射流主要受到水流的阻力影响,受到的两侧水体扰动作用很小，而在核心区外的射流与周围水体间存在较大的速度梯度，从而产生较高的涡量，因此射流与环境水体间的剪切和掺混导致剧烈的能量传递与耗散。

图12所示为PIV实验获得的瞬时涡量分布，在射流上下两侧涡量矢量方向相反，上侧为顺时针方向，下侧为逆时针方向，并且其大小呈对称性分布，轴线上涡量值近似为0。在近喷嘴区，涡量值最大且较稳定，这是因为在射流的初始段，射流束保持了较高的初始动能，集束性强。随着射流的发展，射流与周围水体发生相互作用，能量逐渐耗散，同时涡量值沿流向减小，上下涡对之间的时序性减弱，自涡量集中区的边缘衍生出更小尺度的涡，直观的反映出了淹没水射流的涡量变化特征。从涡量分布的演化过程也可以推知，淹没水射流空化的发生与涡量密切相关，只可能出现在近喷嘴区。

![](images/b9d796e830b7d558a8ff3d4277605e95ab22a06855310589755fbf36fa4ab4f4.jpg)  
图11射流场中的涡量分布Fig.11 Cross-sectional vorticity distribution

![](images/a2f0e1c30aea9a2a8eb5e11f19db9768abf1e3b1aeb237a9c63a6fc7940fc6a8.jpg)  
Fig.1O Variation of semi-width with jet development   
图12瞬时涡量分布  
Fig.12 Temporal vorticity distribution

# 5结论

1）通过高雷诺数圆柱绕流验证了DES数值方案的有效性，所预测的升力系数、阻力系数和斯特劳哈数较已有文献结果更接近于实验测量值，并且DES数值模拟获得了圆柱绕流的展向流动结构形态及非均匀特征。

2)DES数值模拟得到的淹没水射流中轴向速度和径向速度分布规律与PIV实验获得的结果吻合度高。对于淹没水射流的半值宽分布规律，数值模拟结果较实验结果的斜率小，说明射流与环境流体间的剪切效应剧烈，数值方法难以准确预测剪切层厚度和速度梯度。

3）从涡量分布来看，射流束轴心线两侧涡量值呈轴对称分布，射流束轴心线处出现涡量的最小值。

随着射流向下游发展，流束不断沿径向扩展，涡量总体呈衰减趋势，空化发生的可能性降低。

# 参考文献

[1]SpalartPR,JouWH,Strelets M,et al.Comments on the Feasibility of LES for Wings,and ona Hybrid RANS/LES Approach [R].USA,Louisiana:Advances in DNS/LES, 1997,4-8   
[2]Blazek J.Computational Fluid Dynamics:Principles and Applications [M].Butterworth-Heinemann,2015:7-27   
[3] ZHANG Qiang，Yang Yong.A New Simpler Rotation/curvature Correction Method for Spalart-Allmaras Turbulence Model [J].Chinese Journal of Aeronautics, 2013,26(2):326-333   
[4]李燕玲，苏中地.高雷诺数下单圆柱绕流的 DES 三维数值 模拟[J].中国计量学院学报，2013,24(4)：364-369 LI Yanling，SU Zhongdi. 3D Numerical Simulation of Flow Over a Circular Cylinder at High Reynolds Numbers Using DES Method [J].Journal of China University of Metrology,2013,24(4):364-369   
[5]尹纪富,李巍,尤云祥,等.亚临界雷诺数下电磁力控制圆柱 体绕流场特性的脱体涡模拟[J].水动力学研究与进展：A 辑,2013,28(4):495-506 YIN Jifu,LI Wei,YOU Yunxiang. The DES Simulation for Flow Control Around a Circular Cylinder Using the Electromagnetic Force at a Subcritical Reynolds Number[J].Chinese Journal of Hydrodynamics,Ser.A,2013, 28(4):495-506   
[6] Lu X Y,Dalton C.Calculation of the Timing of Vortex Formation From an Oscillating Cylinder [J].Journal of Fluids and Structures,1996,10(5):527-541   
[7]Yokuda S,RamaprianBR.The Dynamics of Flow Around a Cylinder at Subcritical Reynolds Numbers [J].Physics of Fluids A: Fluid Dynamics,1990, 2(5):784-791   
[8] 苏铭德，康钦军．亚临界雷诺数下圆柱绕流的大涡模拟[J]. 力学学报,1999,31(1)：100-105 SU Mingde,KANG Qinjun.Large Eddy Simulation of the Turbulent Flow Around a Circular Cylinder at Subcritical Reynolds Numbers [J]．Acta Mechanica Sinica, 1999,31(1):100-105 [9]战庆亮，周志勇,葛耀君. $\mathrm { R e } { = } 3 9 0 0$ 圆柱绕流的三维大涡模 拟[J].哈尔滨工业大学学报，2015,47(12)：75-79 ZHAN Qingliang， ZHOU Zhiyong，GE Yaojun. 3- Dimensional Large Eddy Simulation of Circular Cylinder at $\mathrm { R e } { = } 3 9 0 0$ [J]. Journal of Harbin Institute of Technology, 2015,47(12): 75-79   
[10] Zhao M,Thapa J,Cheng L,et al. Three-dimensional Transition of Vortex Shedding Flow Around a Circular Cylinder at Right and Oblique Attacks [J].Physics of Fluids,2013,25(1),014105:1-20.   
[11]刘超,李龙国,李乃稳.利用 PIV技术对淹没射流瞬时流场 特性的研究[J]．南水北调与水利科技，2015，13(3)：471- 475 LIU Chao, LI Longguo,LI Naiwen. Research on Instantaneous Flow Characteristics of the Falling Submerged Jet in a Pool Based on PIV Technique [J].South-to-North Water Transfers and Water Science & Technology,2015, 13(3): 471-475   
[12]George W K,Abrahamsson H,Eriksson J,et al.A Similarity Theory for the Turbulent Plane Wall Jet Without External Stream [J].Journal of Fluid Mechanics,2000, 425:367-411   
[13]胡坤,郭群,胡金铜，等.非自由淹没水射流CFD 仿真研究 [J].石油机械,2010,38(11):41-44 HU Kun,GUO Qun,HU Jintong,et al. Study on CFD Simulation of Non-free Submerge Water Jet [J].China Petroleum Machinery, 2010,38(11): 41-44   
[14] Geller S,Uphoff S,Krafczyk M. Turbulent Jet Computations Based on MRT and Cascaded Lattice Boltzmann models [J]. Computers & Mathematics with Applications, 2012,65(12): 1956-1966   
[15]槐文信,李炜.径向射流的相似分析[J].水利学报,1992(8): 50-58 HUAI Wenxin,LI Wei.Similarity Analysis of Radial Jets [J].Journal of Hydraulic Engineering,1992(8): 50-58