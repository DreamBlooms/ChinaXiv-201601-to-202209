# 离焦像差对激光测距回波光子数的影响分析

赵闯闯"²，翟东升1\*，李语强（中国科学院云南天文台，云南昆明650216;2中国科学院大学，北京100049）

摘 要卫星激光测距中，为满足不同距离目标的测距要求，需要调整激光光束发散角。通常利用离焦式扩束系统改变两透镜间距离调整发散角会产生离焦像差，影响激光光束质量和系统测距能力。因此，研究离焦像差对激光光束质量和系统测距能力的影响具有重要意义。首先，分析扩束系统对基模高斯光束的变换作用，得到发散角和离焦量的关系。其次，基于基模高斯光束的传播理论，得到离焦像差对光束能量密度空间分布的影响。最后，对于不同距离的卫星，计算存在离焦像差和无离焦像差时激光测距系统接收的回波光子数。仿真结果表明：发散角和离焦量近似服从线性关系，离焦量变化 $1 \mathrm { m m }$ ，发散角变化1μrad；离焦像差影响光束的能量密度分布，使光斑弥散；对于不同距离的卫星，在不同角放大率下无离焦像差时测距系统接收到的回波光子数约为存在离焦像差时的2倍，可有效提高系统的测距能力。

关键词：离焦像差；泽尼克多项式；能量密度空间分布；回波光子数中图分类号P228.5 文献标志码A

# 1引言

激光测距技术通过精确测定激光脉冲在地面观测站和目标间的往返时间间隔，并根据光速来计算地面观测站和目标间的距离[1]。作为目前最精确的测量手段，其测距目标主要有合作目标（携带角反射器）、空间碎片和月球，其观测数据对天文地球动力学、月球物理和引力理论等诸多科学研究有着重要的价值。

在激光测距中，不同高度的目标受到的摄动影响不同，其轨道的预报精度也不相同，高轨道目标的预报精度要好于低轨道目标[2]。对于低轨目标，可以通过增大发散角增加激光到达目标表面时的光束面积，有利于目标的搜索；而对于高轨目标，则应减小发散角，以增加激光到达目标表面时的能量密度，有利于提高目标探测成功概率。因此，为满足不同距离目标的测距要求，需要采用扩束系统调整激光发散角。

目前，云南天文台及国内大部分激光测距台站采用倒置的伽利略式望远镜扩束系统调整光束发散角。通过移动扩束系统中的凹透镜调整两透镜间的距离改变发散角，称为离焦式扩束系统，距离的调整量称为离焦量。该方式调整发散角时，系统不再是共焦状态，光束波前不再是平面波，存在波前畸变，会产生离焦像差，影响光束质量，降低回波信号强度，进而影响系统的测距能力。因此，研究离焦像差对回波光子数的影响具有重要意义。鲜浩等[3]研究了不同类型波像差和斯特列尔比之间的关系，并建立了拟合关系式。季小玲等[4研究了光束控制系统热效应和球差对远场激光光束质量的影响，结果表明传输通道的热效应和正球差使远场光强分布扩展，可聚焦能力下降，光束质量变差。李新阳等[5研究了光学系统的波像差与对应的光束质量 $\beta$ 因子间的关系，用数值计算方法建立了各种泽尼克多项式的波像差均方根值（RMS）与 $\beta$ 因子间的拟合关系式。

综上，像差对激光光束质量如 $\beta$ 因子、斯特列尔比和聚焦性等有很大的影响，但光束质量对系统测距能力的影响研究未见相关文献报道。本文采用光束能量密度空间分布描述光束质量，利用激光测距回波光子数表示测距系统的测距能力，研究离焦像差对光束质量和系统测距能力的影响，具有重要的理论价值。

# 2 理论模型

# 2.1基模高斯光束的传播及其基本性质

![](images/ac0bd1776222b58daeb1c94206d3cc89b10792d2ed2377e0d11f18a7406fe794.jpg)  
图1基模高斯光束的传播   
Fig.1Propagation of fundamental mode Gaussian beams

由激光谐振腔衍射理论知识可知，在均匀的透明介质中，基模高斯光束沿 $z$ 轴方向传播的复振幅为[6-8]：

$$
A ( x , y , z ) = \sqrt { \frac { 2 E _ { 0 } } { \pi } } \frac { 1 } { \omega ( z ) } \mathrm { e x p } \left[ - \frac { x ^ { 2 } + y ^ { 2 } } { \omega ^ { 2 } ( z ) } \right] \mathrm { e x p } \left\{ - \mathrm { i } \left\{ k \left[ \frac { x ^ { 2 } + y ^ { 2 } } { 2 R ( z ) } + z \right] - \varPhi \left( z \right) \right\} \right\}
$$

式（1）中各项参数表达式为[6]：

$$
\omega \big ( z \big ) = \omega _ { 0 } \left[ 1 + \left( \frac { \lambda z } { \pi \omega _ { 0 } ^ { 2 } } \right) ^ { 2 } \right] ^ { \frac { 1 } { 2 } } = \omega _ { 0 } \left[ 1 + \left( \frac { z } { Z _ { 0 } } \right) ^ { 2 } \right] ^ { \frac { 1 } { 2 } }
$$

$$
R \left( z \right) = z \left[ 1 + \left( \frac { \pi \omega _ { 0 } ^ { 2 } } { \lambda z } \right) ^ { 2 } \right] = z \left[ 1 + \left( \frac { Z _ { 0 } } { z } \right) ^ { 2 } \right]
$$

$$
\begin{array} { r } { \Phi \Big ( z \Big ) = \arctan \Big ( z / Z _ { 0 } \Big ) } \end{array}
$$

上述各式中， $E _ { 0 }$ 为激光单脉冲能量， $\lambda$ 为光束波长， $k = 2 \pi / \lambda$ 为波数。 $\omega ( z ) , \ R ( z )$ 和 $\boldsymbol { \varPhi } \big ( \boldsymbol { z } \big )$ 分别为基模高斯光束的截面半径、波面曲率半径和位相因子，是基模高斯光束复振幅分布的三个重要参数。当 $z = 0$ 时， $\omega _ { \scriptscriptstyle 0 } = \omega \big ( 0 \big )$ 是光束截面最小处的光束截面半径，称为光束的束腰半径。 $Z _ { 0 } = \pi \omega _ { 0 } ^ { 2 } / \lambda = 0 . 5 k \omega _ { 0 } ^ { 2 }$ ，称为瑞利长度或共焦参数。

基模高斯光束的远场发散半角 $\theta _ { 0 }$ 是双曲线的渐近线与光束对称轴的夹角，可用下式定义为[7]：

$$
\theta _ { \scriptscriptstyle 0 } = \operatorname* { l i m } _ { z \to \infty } \frac { \omega \left( z \right) } { z }
$$

结合式（2)，式（5）求极限得：

$$
\theta _ { 0 } = \frac { \lambda } { \pi \omega _ { 0 } }
$$

# 2.2扩束系统对基模高斯光束的变换作用

基模高斯光束经过扩束系统后，其束腰半径和束腰位置将改变。由式（1）知，束腰半径影响光束的复振幅分布。因此，需要求出光束经扩束系统后的束腰半径。可基于矩阵光学，求出光束经扩束系统后的束腰半径和束腰位置。

![](images/8b9e847bffdd6c71d86587798348c09303fc0cf8a25bfb06474362708e048eea.jpg)  
图2基模高斯光束经扩束系统后的变换   
Fig.2Transformation of fundamental mode Gaussian beam through beam expanding system

图2所示为基模高斯光束经扩束系统后的变换。假设 $s _ { 1 }$ 为束腰 $\omega _ { 1 }$ 与透镜 $M 1$ 间的距离，由透镜 $M 1$ 指向束腰 $\omega _ { 1 }$ ，从左向右值为正，反之为负。 $s _ { 2 }$ 为透镜 $M 2$ 与束腰 $\omega _ { 2 }$ 间的距离，由透镜 $M 2$ 指向束腰 $\omega _ { 2 }$ ，从左指向右其值为正，反之为负。透镜 $M 1$ 、 $M 2$ 间的距离为$l = f _ { 1 } ^ { \prime } + f _ { 2 } ^ { \prime } - \Delta l$ ，由 $M 2$ 指向 $M 1$ ，从左指向右其值为正，反之为负。其中， $f _ { 1 } ^ { \prime }$ 、 $f _ { 2 } ^ { \prime }$ 分别为 $M 1$ 、 $M 2$ 的像方焦距。 $\Delta l$ 为离焦量，由 $F _ { 2 }$ 指向 $F _ { 1 } ^ { \prime }$ ，取值规则同上。设放大率$M _ { \scriptscriptstyle T } = \left| f _ { 2 } ^ { \prime } / f _ { 1 } ^ { \prime } \right|$ ，则扩束系统的变换矩阵为[7]:

$$
\pmb { m } = \left[ \begin{array} { c c } { { M _ { T } + \frac { \Delta l } { f _ { 1 } ^ { \prime } } } } & { { l } } \\ { { } } & { { } } \\ { { - \frac { \Delta l } { f _ { 1 } ^ { \prime } f _ { 2 } ^ { \prime } } } } & { { \frac { 1 } { M _ { T } } + \frac { \Delta l } { f _ { 2 } ^ { \prime } } } } \end{array} \right]
$$

束腰 $\omega _ { 1 }$ 到束腰 $\omega _ { 2 }$ 的变换矩阵为：

$$
\begin{array} { r } { M _ { \omega _ { 1 } , \omega _ { 2 } } = \left[ { \displaystyle \sum _ { 0 } } \imath \quad s _ { 2 } \right] \left[ { \displaystyle M _ { T } + \frac { \Delta l } { f _ { 1 } ^ { \prime } } } \imath \quad \quad l \quad } \\ { { \displaystyle - \frac { \Delta l } { f _ { 1 } ^ { \prime } f _ { 2 } ^ { \prime } } } \quad \frac { 1 } { M _ { T } } + \frac { \Delta l } { f _ { 2 } ^ { \prime } } \right] \left[ { \displaystyle \sum _ { 0 } } \imath \quad 1 \right] } \end{array}
$$

当离焦量 $\Delta l = 0$ 时，其束腰位置 $s _ { 2 }$ 、 $\omega _ { 2 }$ 和 $\omega _ { 1 }$ 间关系为[7]:

$$
\begin{array} { c } { { s _ { 2 } = - M _ { _ T } \left( f _ { 1 } ^ { \prime } + f _ { 2 } ^ { \prime } \right) - M _ { _ T } ^ { 2 } s _ { 1 } } } \\ { { { } } } \\ { { \omega _ { 2 } = M _ { _ T } \omega _ { 1 } } } \end{array}
$$

当离焦量 $\Delta l \neq 0$ 时，略去 $\Delta l$ 的二级小量。其束腰位置公式 $\boldsymbol { s ^ { \prime } } _ { 2 }$ 、 $\omega _ { \mathrm { ~ } _ { 2 } } ^ { \prime }$ 和 $\omega _ { \mathrm { 1 } }$ 间关系为[7]:

$$
{ s _ { 2 } } ^ { \prime } = { f _ { 2 } } ^ { \prime } - M _ { T } ^ { 2 } \left( s _ { 1 } - f _ { 1 } ^ { \prime } \right) + M _ { T } ^ { 2 } \Delta l \Biggl [ \left( 1 - { \frac { s _ { 1 } } { f _ { 1 } ^ { \prime } } } \right) ^ { 2 } - \left( { \frac { Z _ { 1 } } { f _ { 1 } ^ { \prime } } } \right) ^ { 2 } \Biggr ]
$$

$$
{ \omega _ { 2 } } ^ { \prime } = \omega _ { 1 } \sqrt { \frac { \left( \Delta l \right) ^ { 2 } } { M _ { T } ^ { 2 } { f _ { 1 } ^ { \prime } } ^ { 2 } } + \frac { 2 \Delta l } { f _ { 1 } ^ { \prime } M _ { T } ^ { 2 } } + \frac { 1 } { M _ { T } ^ { 2 } } }
$$

定义角放大率为高斯光束经扩束系统后与经扩束系统前光束发散角的比值，由式（6)可知，高斯光束的发散角与束腰半径成反比。当离焦量 $\Delta l = 0$ 时，由式（10）得其角放大率 $\boldsymbol { a }$ 为：

$$
\alpha = \frac { \theta _ { 2 } } { \theta _ { 1 } } = \frac { \omega _ { 1 } } { \omega _ { 2 } } = \frac { 1 } { M _ { T } }
$$

当离焦量 $\Delta l \neq 0$ 时，由式（12）得其角放大率 $\boldsymbol { a ^ { \prime } }$ 为：

$$
\alpha ^ { \prime } = \frac { { \theta _ { 2 } } ^ { \prime } } { { \theta _ { 1 } } ^ { \prime } } = \frac { \omega _ { 1 } } { { \omega _ { 2 } } ^ { \prime } } = \frac { 1 } { \sqrt { \displaystyle { \frac { \Delta l ^ { 2 } } { M _ { T } ^ { 2 } { f _ { 1 } } ^ { \prime } } } + \frac { 2 \Delta l } { f _ { 1 } ^ { \prime } M _ { T } ^ { 2 } } } + \frac { 1 } { M _ { T } ^ { 2 } } }
$$

2.3存在离焦像差时光束的能量密度空间分布

调整离焦量后，扩束系统不再是共焦状态，光束波前存在畸变，影响光束能量密度空间分布。波面上的光程总是相等的，波像差就是实际波面和理想波面之间的光程差。波像差一般没有解析数学表达式，常用有限项泽尼克多项式进行近似表达，离焦像差可用泽尼克多项式表示为[9]：

$$
\begin{array} { r } { W _ { 4 } \left( x , y \right) = a _ { 4 } Z _ { 4 } \left( x , y \right) = a _ { 4 } \left( 2 \sqrt { 3 } x ^ { 2 } + 2 \sqrt { 3 } y ^ { 2 } - \sqrt { 3 } \right) } \end{array}
$$

式（15）中， $W _ { 4 } \left( x , y \right)$ 为离焦像差函数。 $a _ { 4 }$ 为泽尼克多项式系数（单位为波长λ），表示像差的标准差，即波前均方根值 $R M S$ 。 $Z _ { 4 } \left( x , y \right)$ 为泽尼克多项式的项，可表示为$2 \sqrt { 3 } x ^ { 2 } + 2 \sqrt { 3 } y ^ { 2 } - \sqrt { 3 } \ 。$ （204号

在调整光束发散角时，离焦量是一个重要参数，它与离焦像差产生的波前峰谷差 $P V$ 值之间的关系为[10]:

$$
\Delta l = 8 \delta { \left( \frac { F M _ { \it { T } } } { D } \right) } ^ { 2 } = 8 \delta { \left( \frac { F } { D \alpha } \right) } ^ { 2 }
$$

式中 $\Delta l$ 为离焦量， $\delta$ 为离焦像差产生的 $P V$ 值。 $F$ 为望远镜的有效焦距， $D$ 为望远镜主镜口径， $\boldsymbol { a }$ 为角放大率。

离焦像差的泽尼克多项式系数 $a _ { 4 }$ 与离焦像差产生的峰谷差 $P V$ 值 $\delta$ 满足以下关系[10]：

$$
\delta = 2 \sqrt { 3 } a _ { 4 } \lambda = \frac { \Delta l } { 8 } { \left( \frac { D \alpha } { F } \right) } ^ { 2 }
$$

由式（16）、式（17）得泽尼克多项式系数 $a _ { 4 }$ 与离焦量 $\Delta l$ 关系为：

$$
a _ { 4 } = \frac { \delta } { 2 \sqrt { 3 } \lambda } = \frac { \Delta l } { 1 6 \sqrt { 3 } \lambda } { \left( \frac { D \alpha } { F } \right) } ^ { 2 }
$$

由式（18）可知，在望远镜主镜口径 $D$ 和有效焦距 $F$ 确定后，泽尼克多项式系数 $a _ { \scriptscriptstyle 4 }$ 与离焦量 $\Delta l$ 对应。

由于扩束系统的衍射效应和离焦像差的存在，激光经过扩束系统后不仅发生衍射，而且与未发生衍射的光（直射光）相互干涉，影响光斑的能量密度分布[。存在离焦像差时，高斯光束在垂直于 $z$ 轴的平面内的复振幅分布为：

$$
I \left( x , y \right) = \frac { 1 } { \omega \left( z \right) } \sqrt { \frac { E _ { 0 } } { 2 \pi } } \exp \Biggl [ - \frac { x ^ { 2 } + y ^ { 2 } } { \omega ^ { 2 } \left( z \right) } \Biggr ] \exp \Biggl \{ - \mathrm { i } \Biggl \{ k \left[ \frac { x ^ { 2 } + y ^ { 2 } } { 2 R \left( z \right) } + z \right] - \phi \left( z \right) \Biggr \} \Biggr \} \left\{ 1 + \exp \left[ \mathrm { i } k W _ { 4 } \left( x , y \right) \right] \right\}
$$

当不存在离焦像差时，离焦量 $\Delta l = 0$ 。多项式系数 $a _ { 4 } = 0$ ，则像差项 ${ \cal W } _ { 4 } \left( x , y \right) = 0$ ，

$\mathrm { e x p } \big [ \mathrm { i } k W _ { \mathrm { 4 } } \big ( x , y \big ) \big ]$ 这项值恒为1。此时，式（19）等价于式（1)，光束的复振幅符合理想高斯分布。当存在离焦像差时，离焦量 $\Delta l \neq 0$ 。由式（18）可知，多项式系数 $a _ { 4 }$ 随离焦量 $\Delta l$ 的增大而增大（结果见表1)，影响光束的复振幅分布。

光束能量密度为：

$$
E d \left( x , y \right) = I { \bigl ( } x , y { \bigr ) } \cdot I ^ { * } \left( x , y \right)
$$

式中 $\boldsymbol { I } ^ { * } ( x , y )$ 为 $I { \big ( } x , y { \big ) }$ 的共轭。

测距目标接收到的激光能量为：

$$
E = \underset { S } { \iint } E d \left( x , y \right) d S
$$

式中 $S$ 为测距目标的有效反射面积。

# 2.4激光测距回波光子数

以卫星为探测目标，假设 $n$ 是探测器接收到的回波光子数。 $N = \lambda /$ hc为每焦耳激光能量所含光子数，式中 $\lambda$ 是激光波长，h为普朗克常量，c是真空中光速。 $\rho$ 为卫星角反射器的反射率， $A _ { \mathrm { s } }$ 是卫星角反射器的有效反射面积， $A _ { \mathrm { r } }$ 为望远镜有效接收面积。 $\eta _ { \mathrm { t } }$ 是激光发射系统光学效率， $\eta _ { \mathrm { r } }$ 为测距系统接收效率。 $T$ 是单程大气光学透过率， $\eta$ 为探测器量子效率。$\beta$ 是衰减因子（大气抖动、湍流等影响)， $R$ 为地面测距台站距卫星距离。 $\theta _ { \mathrm { e } }$ 是发射激光发散半角， $\theta _ { \mathrm { { m } } }$ 为激光经卫星角反射器反射后的发散半角。在激光测距中，探测器接收到的回波光子数 $n$ 为[11-12];

$$
n = \frac { E \cdot N \cdot \rho \cdot A _ { \mathrm { r } } \cdot A _ { \mathrm { s } } \cdot \eta _ { \mathrm { t } } \cdot \eta _ { \mathrm { r } } \cdot T ^ { 2 } \cdot \eta \cdot \beta } { \pi ^ { 2 } \cdot R ^ { 4 } \cdot \theta _ { \mathrm { e } } ^ { 2 } \cdot \theta _ { \mathrm { m } } ^ { 2 } }
$$

式（22）即为激光测距回波光子数方程。

# 3结果分析与讨论

# 3.1角放大率和离焦量关系

云南天文台 $5 3 \mathrm { c m }$ 望远镜激光测距系统中一级扩束系统的凹透镜像方焦距 $f _ { 1 } ^ { \prime } { = } { - } 7 3 \mathrm { m m }$ 凸透镜像方焦距 $f _ { 2 } ^ { \prime } { = } 4 9 8 . 7 9 \mathrm { m m }$ 。改变离焦量 $\Delta l$ ，变化范围为 $- 5 7 1 . 9 \mathrm { m m } \sim 4 2 5 . 7 9 \mathrm { m m }$ 。把上述参数代入式（14)，得到角放大率和离焦量的关系，如图3和表1所示。由图3可知，角放大率关于 $\Delta l = - 7 3 \mathrm { { m m } }$ 对称分布。随着离焦量的增大，角放大率逐渐增大。当离焦量为 $- 7 3 \mathrm { m m }$ 时，角放大率为最小值，其最小值趋于无穷小。此时，凹透镜位于凸透镜物方焦点处。由式（14）知，离焦量 $\Delta l$ 不能等于 $- 7 3 \mathrm { m m }$ ，故角放大率不可能为0。对表1中的数据进行线性拟合，结果表明：角放大率和离焦量近似符合线性关系，离焦量每增加lmm角放大率增加0.002。

![](images/18e5deacc2f68b923882fa1fb1962d1299ded5e691a4af26d86eb5a70b69d09a.jpg)  
图3角放大率和离焦量关系  
Fig.3Relationship between angle magnification and defocusing amount

# 表1角放大率与相应的离焦量调整值

Tab.1Angle magnification and corresponding defocusing adjustment values

<html><body><table><tr><td>Angle magnifica tion α</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td><td>0.9</td></tr><tr><td colspan="9">Defocusing amount</td></tr><tr><td>△l / mm</td><td>26.8</td><td>76.7</td><td>126.6</td><td>176.4</td><td>226.3</td><td>276.2</td><td>326.1</td><td>376.0</td></tr><tr><td>Aberration standard</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>deviation</td><td>1.2</td><td>7.6</td><td>22.4</td><td>48.6</td><td>89.9</td><td>149.3</td><td>230.2</td><td>336.0</td></tr><tr><td>a4/2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 3.2离焦像差对能量密度的影响

测距系统中发射激光波长 $\lambda = 5 3 2 \mathrm { n m }$ ，光束束腰半径 $\omega _ { \mathrm { 0 } } = 7 . 5 \mathrm { m m }$ ，激光发散半角$\theta _ { 0 } = 0 . 5 \mathrm { m r a d }$ 。假设卫星与测距台站间距离 $R = 1 0 0 0 \mathrm { k m }$ ，卫星角反射器的有效反射区域为边长1m的正方形，光束中心和卫星角反射器有效反射区域中心重合。把上述参数代入式(19)，得到不同角放大率下光束在 $1 0 0 0 \mathrm { k m }$ 处的能量密度分布，结果见图4和图5。图中激光发散角为激光经过扩束系统后的发散角，由角放大率乘以入射激光发散角求得，光斑半径由式（2）求得。由图可知，光束经过扩束系统后，随着激光发散角的增大，光斑半径逐渐增大。当不存在离焦像差时，光斑半径仅发生尺度变化，能量密度分布符合高斯分布。当存在离焦像差时，光斑半径不仅发生尺度变化，而且其形状更加弥散。能量密度分布也不再是

高斯分布，变得更为复杂。

![](images/bf05b7d209ad8da38a281e735740b1bbbaf44db6ab7a047a8176bb5935ffb811.jpg)  
图4存在离焦像差时光束能量密度分布

（a）发散角 $\theta = 0 . 1 5 \mathrm { { m r a d } }$ ，光斑半径 $r = 6 . 7 8 \mathrm { m m }$ ；（b）发散角 $\theta = 0 . 2 \mathrm { m r a d }$ ，光斑半径 $r = 9 . 0 4 \mathrm { { m m } }$ ：（c）发散角 $\theta = 0 . 2 5 \mathrm { { m r a } }$ ，光斑半径 $r = 1 1 . 2 9 \mathrm { { m m } }$ ；（d）发散角 $\theta = 0 . 3 \mathrm { { m r a d } }$ ，光斑半径 $r = 1 3 . 5 7 \mathrm { m m }$

Fig.4 Beam energy density distribution in the presence of defocusing aberrations （a）divergence angle $\theta = 0 . 1 5 \mathrm { { m r a d } }$ ，spot radius $r = 6 . 7 8 \mathrm { m m }$ ；（b）divergence angle $\theta = 0 . 2$ mrad，spotradius $r = 9 . 0 4 \mathrm { { m m } }$ · （c）divergence angle $\theta = 0 . 2 5 \mathrm { { m r a } }$ ，spot radius $r = 1 1 . 2 9 \mathrm { { m m } }$ ；（d）divergence angle $\theta = 0 . 3 \mathrm { { m r a d } }$ ，spot radius $r = 1 3 . 5 7 \mathrm { m m }$ （a）发散角 $\theta = 0 . 1 5 \mathrm { { m r a d } }$ ，光斑半径 $r = 6 . 7 8 \mathrm { m m }$ ；（b）发散角 $\theta = 0 . 2 \mathrm { m r a d }$ ，光斑半径 $r = 9 . 0 4 \mathrm { { m m } }$ ： （c）发散角 $\theta = 0 . 2 5 \mathrm { { m r a } }$ ，光斑半径 $r = 1 1 . 2 9 \mathrm { { m m } }$ ；（d）发散角 $\theta = 0 . 3 \mathrm { { m r a d } }$ ，光斑半径 $r = 1 3 . 5 7 \mathrm { m m }$ （a）divergence angle $\theta = 0 . 1 5 \mathrm { { m r a d } }$ ，spot radius $r = 6 . 7 8 \mathrm { m m }$ ；（b）divergence angle $\theta = 0 . 2 \mathrm { m r a d }$ ，spot radius $r = 9 . 0 4 \mathrm { { m m } }$ （c） divergence angle $\theta = 0 . 2 5 \mathrm { { m r a } }$ ，spot radius $r = 1 1 . 2 9 \mathrm { { m m } }$ ；（d） divergence angle $\theta = 0 . 3 \mathrm { { m r a d } }$ ，spot radius $r = 1 3 . 5 7 \mathrm { m m }$

![](images/6f251ef21b02bdbf2f08793c46288ed71732654035f08d945e2bea5e67155d7f.jpg)

![](images/f109996347daec2f34b8c61a4ecb21bf1b2f261fe7a4ee069315b792591fc842.jpg)  
图5无离焦像差时光束能量密度分布  
Fig.5Energy density distribution of beam without defocusing aberration

利用式（21）计算当卫星距测距台站距离 $R = 1 0 0 0 \mathrm { k m }$ 时，卫星在不同角放大率下接收到的能量，结果如表2所示。表2中 $E _ { \scriptscriptstyle 1 }$ 为存在离焦像差时卫星接收的能量， $E _ { 2 }$ 为无离焦像差时卫星接收的能量。由表2中数据可知，在不同角放大率下， $E _ { 2 }$ 值均大于 $E _ { \mathrm { { l } } }$ 值。因此,离焦像差影响激光光束能量密度分布，进而影响卫星接收到的能量。

# 表2不同角放大率下卫星接收到的能量

<html><body><table><tr><td>Angle magnification α</td><td>0.2001</td><td>0.3001</td><td>0.4002</td><td>0.5000</td><td>0.6001</td><td>0.7001</td><td>0.8001</td><td>0.9002</td></tr><tr><td>Energy E/mJ</td><td>45.9</td><td>20.9</td><td>11.7</td><td>7.5</td><td>5.2</td><td>3.8</td><td>2.9</td><td>2.3</td></tr><tr><td>Energy E2/mJ</td><td>92.0</td><td>41.3</td><td>23.3</td><td>14.9</td><td>10.4</td><td>7.6</td><td>5.8</td><td>4.6</td></tr></table></body></html>

Tab.2Energy received by target at different angular magnification

# 3.3不同角放大率下的回波光子数

云南天文台 $5 3 \mathrm { c m }$ 望远镜激光测距系统参数如下：激光单脉冲能量 $E _ { 0 } = 3 \mathrm { J }$ ，每焦耳激光能量所含光子数 $N { = } 2 . 7 { \times } 1 0 ^ { 1 8 }$ （激光波长 $\lambda = 5 3 2 \mathrm { { n m } }$ )。卫星角反射器反射率 $\rho { = } 0 . 8$ ，卫星角反射器有效反射面积 $A _ { \mathrm { s } } = \ln ^ { 2 }$ 。望远镜有效接收面积 $A _ { \mathrm { r } } = 0 . 2 0 4 3 \mathrm { m } ^ { 2 }$ 。激光发射系统光学效率 $\eta _ { \mathrm { { t } } } = 0 . 5$ ，测距系统接收效率 $\eta _ { \mathrm { r } } = 0 . 5$ 。单程大气光学透过率 $T = 0 . 6$ ，单光子雪崩二极管探测器量子效率 $\eta = 0 . 2$ 。衰减因子 $\beta = 0 . 1$ ，地面测距台站距卫星距离 $R$ 的范围为 $5 0 0 { - } 1 0 0 0 \mathrm { k m }$ ，距离间隔为 $1 0 0 \mathrm { k m }$ 。激光光束经卫星角反射器反射后的发散角$\theta _ { \mathrm { { m } } } = 0 . 5 \mathrm { { m r a d } }$ 。把上述参数代入式（22）计算回波光子数，结果如图6、表3和表4所示。图6为距离 $R = 1 0 0 0 \mathrm { k m }$ 时不同角放大率下的回波光子数， $n _ { \mathrm { { } _ { 1 } } }$ 为存在离焦像差时的回波光子数， $n _ { 2 }$ 为无离焦像差时的回波光子数。如图6所示，对于距离 $R = 1 0 0 0 \mathrm { k m }$ 处的卫星，随着角放大率的增大，测距系统接收到的回波光子数迅速衰减。因此对于不同距离的目标，需要选择适当的激光发散角。表3和表4为卫星与测距台站间距离 $R$ 为 $5 0 0 \sim 1 0 0 0 \mathrm { k m }$ 时测距系统接收到的回波光子数。由表3和表4可知，当激光发散半角相同时，卫星距测距台站距离越近，测距系统接收回波光子数越多。对于同一距离的卫星，激光发散半角越小，测距系统接收的回波光子数越多。对于不同距离的同一颗卫星，在不同角放大率下， $n _ { \mathrm { { } _ { 1 } } }$ 值均小于 $n _ { 2 }$ 值，前者约为后者的 $50 \%$ 。回波光子数越多，目标的探测成功概率就越高。

![](images/743cd005a532785fec7f70f5e94c6450896035a6f6a8767ab7bc8a1f7946f04c.jpg)  
图6激光测距回波光子数  
Fig.6 The number of echo photons in laser ranging

表3距离 $R$ 为 $5 0 0 - 7 0 0 \mathrm { k m }$ 时的回波光子数  
Tab.3the number of echo photons when the distance $R$ is $5 0 0 - 7 0 0 \mathrm { k m }$   

<html><body><table><tr><td rowspan="2">Angle magnification</td><td colspan="2">R= 500km</td><td colspan="2">R = 600km</td><td colspan="2">R = 700km</td></tr><tr><td>aberration</td><td>no aberration</td><td>aberration</td><td>no aberration</td><td>aberration</td><td>no aberration</td></tr><tr><td>a</td><td>n</td><td>n2</td><td>n</td><td>n2</td><td>n</td><td>n2</td></tr><tr><td>0.2001</td><td>89907.6</td><td>180277.9</td><td>30715.2</td><td>61579.1</td><td>12324.1</td><td>24715.0</td></tr><tr><td>0.3001</td><td>18644.9</td><td>36969.6</td><td>6299.6</td><td>12488.9</td><td>2519.0</td><td>4978.5</td></tr><tr><td>0.4002</td><td>5943.2</td><td>11835.0</td><td>1997.6</td><td>3982.8</td><td>793.6</td><td>1583.9</td></tr><tr><td>0.5000</td><td>2464.1</td><td>4887.1</td><td>826.7</td><td>1641.4</td><td>328.2</td><td>652.2</td></tr><tr><td>0.6001</td><td>1178.6</td><td>2362.9</td><td>397.3</td><td>794.6</td><td>157.9</td><td>315.7</td></tr><tr><td>0.7001</td><td>638.9</td><td>1277.9</td><td>214.9</td><td>429.8</td><td>85.3</td><td>170.7</td></tr><tr><td>0.8001</td><td>373.3</td><td>749.9</td><td>125.7</td><td>251.4</td><td>49.4</td><td>99.7</td></tr><tr><td>0.9002</td><td>233.9</td><td>467.8</td><td>78.5</td><td>156.9</td><td>31.1</td><td>62.2</td></tr></table></body></html>

表4距离 $R$ 为 $8 0 0 - 1 0 0 0 \mathrm { k m }$ 时的回波光子数  
Tab.4the number of echo photons when the distance $R$ is 800-1000km   

<html><body><table><tr><td rowspan="2">Angle magnification a</td><td colspan="2">R = 800km</td><td colspan="2">R = 900km</td><td colspan="2">R = 1000km</td></tr><tr><td>aberration n</td><td>no aberration n2</td><td>aberration n</td><td>no aberration n2</td><td>aberration n</td><td>no aberration</td></tr><tr><td>0.2001</td><td>5576.9</td><td>11177.4</td><td>2761.8</td><td>5543.2</td><td>1474.7</td><td>n2 2955.8</td></tr><tr><td>0.3001</td><td>1134.5</td><td>2244.6</td><td>560.1</td><td>1109.3</td><td>298.8</td><td>590.5</td></tr><tr><td>0.4002</td><td>357.2</td><td>712.5</td><td>176.5</td><td>351.7</td><td>94.1</td><td>187.3</td></tr><tr><td>0.5000</td><td>148.4</td><td>293.0</td><td>73.0</td><td>144.5</td><td>38.6</td><td>76.7</td></tr><tr><td>0.6001</td><td>70.7</td><td>141.4</td><td>34.9</td><td>69.8</td><td>18.6</td><td>37.2</td></tr><tr><td>0.7001</td><td>38.5</td><td>76.3</td><td>18.8</td><td>37.6</td><td>10.0</td><td>20.0</td></tr><tr><td>0.8001</td><td>22.1</td><td>44.7</td><td>11.0</td><td>22.1</td><td>5.8</td><td>11.7</td></tr><tr><td>0.9002</td><td>14.0</td><td>27.9</td><td>7.0</td><td>13.8</td><td>3.7</td><td>7.3</td></tr></table></body></html>

在实际应用中，若通过切换伽利略式望远镜扩束系统中凹透镜的方式调整激光光束发散角，此时系统中两透镜处于共焦状态，离焦量 $\Delta l$ 为0，离焦像差值为0，不存在离焦像差。当不存在离焦像差时，假设探测目标与测距台站距离 $R$ 范围为 $5 0 0 \sim 1 6 0 0 \mathrm { k m }$ ，探测目标参数同上。探测器的光敏面产生光电子的概率服从泊松分布，当回波光子数为 $n$ 时，至少产生一个光电子的概率为[14]：

$$
P ( \geq 1 ) = 1 - \mathbf { e } ^ { - n }
$$

式（23）也称为探测成功概率。

由式（22）和式（23)，可计算目标探测成功概率。结果见表5，表头行数据表示角放大率，表头列数据表示探测目标与测距台站间的距离，单位为 $\mathrm { k m }$ 。由表5可知，当角放大率为 $0 . 1 0 \sim 0 . 5 0$ 时，探测成功概率均为 $100 \%$ 。但是，探测成功概率受很多因素影响，例如望远镜的跟踪精度、激光能量波动和大气湍流等，会导致实际情况和理论结果有差别。此外，探测成功概率为 $100 \%$ 仅说明探测成功概率较高，在实际激光测距中也不可能每次都能探测到目标。测距系统中发射激光光束直径为 $1 5 \mathrm { m m }$ ，望远镜副镜有效通光口径为 $4 8 \mathrm { m m }$ 。为充分利用望远镜口径，光束的最大扩束倍率为副镜有效通光口径与光束直径之比，为3.2倍，即角放大率为0.31,因此扩束系统的角放大率最好不小于0.31(扩束倍率与角放大率成反比)。综合以上分析，针对探测距离为 $5 0 0 \sim 1 6 0 0 \mathrm { k m }$ 的目标，扩束系统的角放大率为0.3、0.4和0.5。

表5目标探测成功概率  
Tab.5Probability of success of target detection   

<html><body><table><tr><td>Angle magnification</td><td>0.10</td><td>0.20</td><td>0.30</td><td>0.40</td><td>0.50</td><td>0.60</td><td>0.70</td><td>0.80</td><td>0.90</td></tr><tr><td>Distance 500</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td></td></tr><tr><td>600</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00 0.98</td></tr><tr><td>700</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.99</td><td>0.95</td></tr><tr><td>800</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.98</td><td>0.90</td></tr><tr><td>900</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.99</td><td>0.94</td><td>0.83</td></tr><tr><td>1000</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.98</td><td>0.90</td><td>0.78</td></tr><tr><td>1100</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.96</td><td>0.85</td><td>0.70</td></tr><tr><td>1200</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.99</td><td>0.94</td><td>0.80</td><td>0.63</td></tr><tr><td>1300</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.99</td><td>0.91</td><td>0.75</td><td>0.59</td></tr><tr><td>1400</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.98</td><td>0.86</td><td>0.70</td><td>0.55</td></tr><tr><td>1500</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.96</td><td>0.83</td><td>0.63</td><td>0.50</td></tr><tr><td>1600</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.94</td><td>0.80</td><td>0.59</td><td>0.45</td></tr></table></body></html>

# 4总结

通过理论分析，研究了离焦像差对光束能量密度分布和激光测距回波光子数的影响。数值仿真结果表明：离焦像差使光斑形状变的弥散，降低目标接收到的能量，影响测距系统接收到的回波光子数。对于不同距离处的同一颗卫星，在不同角放大率下，无离焦像差时测距系统接收到的回波光子数约是存在离焦像差时的2倍。由表1可知，通过改变扩束系统中两透镜间距离调整发散角时，离焦量越大，离焦像差的波前均方根值RMS 越大，严重影响光束的能量密度分布。但是又需要通过改变离焦量调整发散角，两者之间存在矛盾，因此这种发散角调整方式存在问题。

# Analysis of the influence of defocus aberration on the photon number of laser ranging echo

Zhao Chuangchuangl,2, Zhai Dongshengl\*,Li Yuqiang1 (lYunnan Observatory, Chinese Academy of Sciences, Kunming Yunnan 650216, China 2 University of Chinese Academy of Sciences, Beijing 100049, China)

Abstract: In satelite laser ranging, in order to meet the ranging requirements of different range targets, it is necessary to adjust the divergence angle of laser beam. Usually, the defocused beam expander system is used to change the distance between two lenses and adjust the divergence angle, which will produce defocused aberration and affect the laser beam quality and the ranging ability of the system. Therefore, it is important to study the influence of defocusing aberration on laser beam quality and system ranging ability. Firstly, the transformation effect of the beam expander system on the fundamental mode Gaussian beam is analyzed,and the relationship between the angular magnification and the defocusing amount is obtained. Secondly, based on the propagation theory of fundamental mode Gaussian beam, the influence of defocusing aberration on the spatial distribution of beam energy density is obtained. Finally,for satelites with different distances, the number of photons received by the laser ranging system with and without defocusing aberrations is calculated. The simulation results show that the angular magnification and defocusing amount obey a linear relationship approximately， the defocusing amount changes $1 \mathrm { m m }$ and the divergence angle changes lμrad ； The defocusing aberration affects the energy density distribution of the beam and makes the spot diffuse; For satellites with different distances, the number of photons received by the ranging system without defocusing aberrations at different angular magnification is about twice that of the system with defocusing aberrations, which can effectively improve the ranging capability of the system.

Key words: Defocused aberration; Zernike polynomial; Spatial distribution of energy density: Jumber of echo photons

# 参考文献

[1]李语强,伏红林,李荣旺,等.云南天文台月球激光测距研究与实验[J].中国激 光,2019,46(1):0104004.   
LI Yuqiang, FU Honglin, LI Rongwang, et al. Research and Experiment of Lunar Laser Ranging in Yunnan Observatories[J]. Chinese Journal of Lasers,2019, 46(1): 0104004.   
[2]项清革,卫志斌,程伯辉,等.卫星激光测距仪发散角系统的设计[J].测绘科 学,2004(05):44-46+4.   
XIANG Qingge, WEI Zhibin, CHENG Bohui, et al. Design of divergence angle system of satelite laser rangefinder [J]. Surveying and Mapping Science, 2O04 (05): $4 4 { - } 4 6 + 4$   
[3]鲜浩,姜文汉.波像差与光束质量指标的关系[J].中国激光,1999(05):32-36.   
XIAN Hao JIANG Wenhan. The Relation between Wavefront Aberration and the Beam Quality Factor[J]. Chinese Journal ofLasers,1999, 26(5): 32-36.   
[4]季小玲,陶向阳,吕百达.光束控制系统热效应与球差对激光光束质量的影响.物理学报, 2004,53(3):952-960.doi:10.7498/aps.53.952.   
JI Xiaoling,TAO Xiangyang,LV Baida. The influence of thermal effect and spherical aberration of beam control system on laser beam quality. Acta physics Sinica,2004,53(3):952-960.Doi: 10.7498/aps.53.952. [5]李新阳,鲜浩,王春鸿,等.波像差与光束质量 $\beta$ 因子的关系[J].中国激光,2005(06):798-802. LI Xiangyang, XIAN Hao, WANG Chunhong, et al. Relationship between wavefront aberration and beam quality $\beta$ factor[J]. China laser,2005 (06): 798-802.   
[6]郁道银,谈恒英.工程光学.[M].4版.北京:机械工业出版社,2016:179-181.   
YU Daoyin, TAN Hengying. Engineering optics. [M]. 4th Edition. Beijing: China Machine Press, 2016:179-181.   
[7]吕百达.激光光学:激光束的传输变换和光束质量控制[M].3版.四川:四川大学出版社, 1992:98-145.   
LV Baida. Laser optics: transmission transformation and beam quality control of laser beam[M].3rd Edition. Sichuan: Sichuan University Press,1992:98-145.   
[8]李俊昌.激光的衍射及热作用计算[M].1版.北京:科学出版社,2002:220-222.   
LI Junchang. Calculation of laser difraction and thermal interaction [M]. 1st edition. Beijing: Science Press,2002:220-222.   
[9]史广维．基于矢量波像差理论的反射望远系统装调研究[D].长春：中国科学院研究生院 （长春光学精密机械与物理研究所）,2011:27-33.   
SHI Guangwei. Research on the installation and adjustment of reflective telescope system based on vector wave aberration theory [D]. Changchun: Graduate School of Chinese Academy of Sciences (Changchun Institute of optics, precision machinery and Physics), 2011: 27-33.   
[10]于学刚,刘忠,金振宇,等.波前相位差法探测器的设计[J].天文研究与技术,2010,7(01):55-59. YU Xuegang,LIU Zhong, JIN Zhenyu, et al. Design of wavefront phase diference detector [J]. Astronomical research and technology, 2010,7 (01): 55-59.   
[11]熊耀恒.月球激光测距的新技术方法研究[D].昆明:中国科学院云南天文台,2001:6-8. XIONG Yaoheng. Research on new technology of lunar laser ranging [D]. Kunming: Yunnan Observatory, Chinese Academy of Sciences, 2001: 6-8.   
[12]伏红林.激光测距中激光性质的研究及其在实测中的应用[D].昆明:中国科学院研究生院 （云南天文台）,2003:5-6.   
FU Honglin. Study of laser properties in laser ranging and its application in measurement [D]. Kunming: Graduate School of Chinese Academy of Sciences (Yunnan Observatory), 2003:5-6. [13]万凡,汤儒峰,翟东升,苏向泽,赵闯闯,李语强.激光光斑特性测量方法研究[J].天文研究与 技术,2020,17(04):463-470.   
WAN fan, TANG Rufeng, ZHAI Dongsheng, et al. Study on measurement method of laser spot characteristics [J]. Astronomical research and technology,2020,17 (04): 463-470.   
[14]高清鹏,李春晓,李荣旺，等．鹊桥卫星激光测距时间窗口及测距成功概率分析[J]．天文 研究与技术,2019,16(4): 422-430.   
GAO Q P, LI C X, LI R W, et al. Magpie bridge satellite laser ranging time window and distance probability analysis[J].Astronomical Research & Technology, 2019,16(4): 422-430.