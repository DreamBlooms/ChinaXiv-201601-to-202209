# 地月系L2点中继星激光测距成功率的估算

李春晓²，高清鹏’²，李语强¹，李祝莲‘

(1.中国科学院云南天文台 云南 昆明650011

# 2.中国科学院大学 北京100049)

摘要：为了确定月球与即将发射到地月系 $\mathbf { L } _ { 2 }$ 点的中继星之间的位置关系进而估算中继星激光测距的成功率，按照晕轨道周期为14天左右的要求对中继星所在的晕轨道进行了计算，并建立了一个综合考虑望远镜抖动、大气抖动和预报轨道横向偏离的模型。从数值上给出了一条轨道周期为14.78天， $X$ 方向 (地月连线方向)的振幅为 $1 2 4 9 3 \mathrm { k m }$ ，Y方向为 $3 4 5 9 6 \mathrm { k m }$ ， $Z$ 方向 (垂直于地月轨道平面方向)为11916km 的周期轨道。由于晕轨道的最小振幅远大于月球遮挡的临界振幅 $4 0 0 0 \mathrm { k m }$ ，因此月球对中继星不存在遮挡问题。基于上面建立的测距成功率模型，根据昆明站 (国际编号：7820)的激光测距系统对运行在该晕轨道上的中继星进行测距成功率分析，结果表明：测距成功率随着中继星横向轨道标准差的增大呈现快速降低的趋势。对于中继星到测站的平均距离而言，当中继星没有横向偏离时，探测器产生的光电子数为0.151，成功率为 $1 4 . 0 7 \%$ ；横向偏离 $2 \mathrm { k m }$ 时，光电子数降为0.035，成功率降为 $3 . 4 6 \%$ 。对比最近距离与最远距离的情况，无横向偏移的情况下，探测器产生的光电子数从0.174降为0.139，成功率从 $1 6 . 0 1 \%$ 降为 $1 3 . 0 2 \%$ 。根据上面所有的计算结果，为后续云南天文台 $1 . 2 \mathrm { m }$ 望远镜实现中继星激光测距提供参考。

关键词：中继星激光测距；L2点晕轨道；测距成功率中图分类号:P171.3；P228.5文献标识码:A 文章编号:1672-7673(2019)

# 国家自然科学天文联合基金（u1631134);

引力波的探测不仅是检验广义相对论根基的重要途径，同时也为研究宇宙提供了一种全新的手段。继地基的 LIGO 和 Virgo 同时直接探测到由双中子星合并产生的引力波和伽马射线[]，天基的引力波探测计划也在紧锣密鼓地进行中，其中，“天琴计划”是将3个星载激光干涉仪发射到绕地近圆轨道上通过观测卫星之间的距离变化探测引力波2]。这3颗卫星组成等边三角形构型，臂长约为$1 0 5 \mathrm { k m }$ ，轨道平面面向由两颗快速绕转的白矮星组成的引力波辐射源 $\mathrm { R X J 0 8 0 6 . 3 + 1 5 2 7 ^ { [ 3 ] } } .$ 0

“天琴计划”的第1步是实现激光测月和深空卫星激光测距。为了满足即将发射的“嫦娥 4号”月球背面登陆器与地球的实时通讯，需要在地月系 $\mathbf { L } _ { 2 }$ 点附近的晕轨道上放置一个中继星实现通讯中转[]。文[5]针对地月 $\mathrm { L } _ { 2 }$ 点的中继星任务分析了发射窗口、地月转移时间、近月点高度、近月点倾角、轨道振幅等因素对地月 $\mathbf { L } _ { 2 }$ 转移轨道和使命轨道特性的影响，文[6]针对中继星转移轨道的转移时间、近月点高度和晕轨道振幅等约束条件，研究了月球近旁 $\mathbf { L } _ { 2 }$ 点转移轨道设计方法。文[7]研究了地月系 $\mathbf { L } _ { 2 }$ 点纯反射式激光测距技术和任务设计，并结合云南天文台 $1 . 2 \mathrm { m }$ 望眼镜激光测距系统给出了预期系统能接收到的单脉冲回波光子数。由于中继星的星等 (暗于17等，计算过程见附录)高于 $1 . 2 \mathrm { m }$ 望远镜光电探测的极限星等，所以有必要计算出一条假想的晕轨道并对预报精度如何影响单脉冲回波光子数做出分析，进而研究评估中继星和月球处于不同位置关系时噪声对激光测距成功率的影响。本文根据轨道对称性理论和微分改正法[计算出一条围绕地月系 $\mathbf { L } _ { 2 }$ 点运动的晕轨道，在此基础上估算了能量服从高斯分布的光斑在考虑大气抖动、望远镜抖动、中继星预报精度的情况下，单脉冲的回波光子数和测距成功率随中继星预报精度的变化。

# 1围绕 $\mathbf { L } _ { 2 }$ 点的晕轨道计算方法

中继星在地月系中的圆形限制性三体问题（Circular Restricted Three Body Problem，CRTBP）指的是地球和月球绕地月系质心作圆周运动，中继星在地球和月球共同引力作用下的动力学问题。这里仅考虑中继星围绕 $\mathbf { L } _ { 2 }$ 点的周期运动，并最终给出一条可行的晕轨道。

定义地月距离 $d$ 为基本的长度单位，地月周期 $P$ 为基本的时间单位，那么无量纲的距离单位L\*、时间单位 $t * .$ 速度单位 $\nu *$ 与正常使用的距离单位 $L$ 、时间单位t、速度单位 $\mathbf { \sigma } _ { \nu }$ 之间的转换关系如下：

$$
L ^ { * } = L / d ,
$$

$$
\nu ^ { * } { = } L ^ { * } / t ^ { * } { = } { \nu ^ { * } } P / 2 ^ { * } \pi ^ { * } d
$$

其中:

其中， $G$ 为引力常数； $M$ 为地球月球质量之和。圆形限制性三体问题在绕质心旋转坐标系下的无量纲运动方程[9]为

$$
\begin{array}{c} \begin{array} { r } { [ \dot { \hat { x } } ] } \\ { \dot { \hat { z } } } \\ { \dot { \hat { v _ { x } } } } \\ { \dot { \hat { v _ { y } } } } \\ { \dot { \hat { v _ { z } } } } \end{array}  [ \begin{array} { c } { v _ { x } } \\ { v _ { y } } \\ { v _ { z } } \\ { 2 v _ { y } + \frac { \partial U } { \partial x } } \\ { - 2 v _ { x } + \frac { \partial U } { \partial y } } \\ { \frac { \partial U } { \partial z } } \end{array} ]  \end{array}
$$

其中：

$$
\begin{array} { r c l } { { U ( x , y , z ) = ( 1 / 2 ) ^ { * } ( x ^ { 2 } + y ^ { 2 } ) + ( 1 - \mu ) / r _ { 1 } + \mu / r _ { 2 } \quad , } } \\ { { } } & { { } } \\ { { r _ { 1 } = [ ( x + \mu ) ^ { 2 } + y ^ { 2 } + z ^ { 2 } ] ^ { 1 / 2 } } } \\ { { } } & { { } } \\ { { { \bf r } _ { 2 } = [ ( x - ( 1 - \mu ) ) ^ { 2 } + y ^ { 2 } + z ^ { 2 } ] ^ { 1 / 2 } } } \\ { { } } & { { } } \\ { { \mu = m _ { 2 } / ( m _ { 1 } + m _ { 2 } ) \quad . } } \end{array}
$$

(6)式中 $\mathbf { \nabla } _ { m _ { 1 } }$ 和 $m _ { 2 }$ 分别为地球和月球的质量。圆形限制性三体问题存在一个Jacobian 积分，即$2 { \cal U } ( x , y , z ) – ( \nu ^ { 2 } { } _ { x } + \nu ^ { 2 } { } _ { y } + \nu ^ { 2 } { } _ { z } ) = \mathbf { C }$ (7)

其中C为一个常数。如果令中继星的速度为零，那么会得到零速度曲面 $2 U ( x , y , z ) = \mathrm { C }$ ，更进一步，令 $z = 0$ ，可以得到零速度曲面在 $X { - } Y$ 平面的投影，即零速度曲线 $2 U ( x , y ) = \mathrm { C }$ 。

在 $t _ { 0 }$ 时刻，取一个位于 $\mathbf { L } _ { 2 }$ 点附近的初始状态矢量 $( \mathrm { x } _ { \mathrm { 0 } } , 0 , \mathrm { Z } _ { 0 } , 0 , \mathrm { v y } _ { 0 } , 0 )$ ，那么经过半个周期 $\boldsymbol { \tau }$ 后中继星的状态矢量可以表示为

$$
\begin{array} { r } { \left[ { x ( t _ { 0 } + \tau ) } \right] ~ { \left[ \begin{array} { l } { \phi _ { 1 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { y ( t _ { 0 } + \tau ) } \\ { z ( t _ { 0 } + \tau ) } \\ { v _ { x } ( t _ { 0 } + \tau ) } \\ { v _ { y } ( t _ { 0 } + \tau ) } \\ { v _ { z } ( t _ { 0 } + \tau ) } \end{array} \right] } = \left[ { \begin{array} { l } { \phi _ { 1 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 2 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 3 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 4 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 5 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 6 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \end{array} } \right] } \end{array}
$$

其中, $\phi _ { i } ( x _ { 0 } , 0 , z _ { 0 } , 0 , \nu y _ { 0 } , 0 , \tau )$ 为一个流。从初始位置经过一个周期 $2 \tau$ 后，位置偏量定义为

$$
{ \Delta } \mathbf { r } = ( ( \mathbf { x } ( \mathrm { t _ { 0 } } + 2 \tau ) - \mathbf { x } _ { 0 } ) ^ { 2 } + ( \mathbf { y } ( \mathrm { t _ { 0 } } + 2 \tau ) - \mathbf { y } _ { 0 } ) ^ { 2 } + ( \mathbf { z } ( \mathrm { t _ { 0 } } + 2 \tau ) - \mathbf { z } _ { 0 } ) ^ { 2 } ) ^ { 1 / 2 }
$$

根据对称性原理[10]，经过半个周期 $\boldsymbol { \tau }$ 后中继星的状态矢量满足

$$
\left[ \begin{array} { l } { \phi _ { 2 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 4 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \\ { \phi _ { 6 } ( x _ { 0 } , 0 , z _ { 0 } , 0 , v _ { y _ { 0 } } , 0 , \tau ) } \end{array} \right] = \mathbf { 0 }
$$

固定 $x _ { 0 }$ ，则（10）式含有3个未知数，所以采用微分改正法求 $z _ { 0 }$ ， $\nu y _ { 0 , } \tau$

$$
\left[ { \begin{array} { l } { z _ { 0 } } \\ { v _ { y _ { 0 } } } \\ { \tau } \end{array} } \right] _ { n + 1 } = \left[ { \begin{array} { l } { z _ { 0 } } \\ { v _ { y _ { 0 } } } \\ { \tau } \end{array} } \right] _ { n } - \left[ { \frac { \partial \phi _ { 2 } } { \partial z _ { 0 } } } \begin{array} { l l l } { { \frac { \partial \phi _ { 2 } } { \partial v _ { y _ { 0 } } } } } & { { \frac { \partial \phi _ { 2 } } { \partial \tau } } } & { { \frac { \partial \phi _ { 2 } } { \partial \tau } } } \\ { { \frac { \partial \phi _ { 4 } } { \partial z _ { 0 } } } } & { { \frac { \partial \phi _ { 4 } } { \partial v _ { y _ { 0 } } } } } & { { \frac { \partial \phi _ { 4 } } { \partial \tau } } } \\ { { \frac { \partial \phi _ { 6 } } { \partial z _ { 0 } } } } & { { \frac { \partial \phi _ { 6 } } { \partial v _ { y _ { 0 } } } } } & { { \frac { \partial \phi _ { 6 } } { \partial \tau } } } \end{array}  \right] _ { n | t _ { 0 } + \tau } ^ { - 1 } \left[ { \begin{array} { l } { \phi _ { 2 } } \\ { \phi _ { 4 } } \\ { \phi _ { 6 } } \end{array} } \right] _ { n | t _ { 0 } + \tau }
$$

其中 ${ \hat { \sigma } \phi _ { 2 } } / { \hat { \sigma } z _ { 0 } } { = \varPhi ( 2 , 3 ) }$

$$
\begin{array} { r l } & { \begin{array} { r l } & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { v } y u - \widehat { \phi } ( 2 , 5 ) } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { v } _ { 1 } - \gamma _ { j } } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { v } _ { 2 } - \widehat { \phi } _ { j } } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \phi } _ { 2 } \bar { \sigma } { - } \widehat { \phi } ( 4 , 3 ) } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { \phi } \bar { v } y u - \widehat { \phi } ( 4 , 5 ) } \end{array} } \\ & { \begin{array} { r l } & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \tau } ( \bar { \tau } - 2 \nu _ { j } ) + \widehat { \Delta { \xi } } U \bar { c } x } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \tau } ( \bar { \tau } _ { 2 } - \widehat { \sigma } { + } \widehat { \theta } ( 6 , 3 ) } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \sigma } { \psi } _ { 3 } - \widehat { \phi } ( 6 , 5 ) } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \sigma } { - } \widehat { \phi } _ { j } \bar { c } ( 6 , 5 ) } \end{array} } \\ & { \begin{array} { r l } & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \tau } ( \bar { \tau } - \widehat { \sigma } { - } \widehat { \sigma } { + } \widehat { \Delta { \xi } } ) } \\ & { \widehat { \Delta { \phi } } _ { j } \bar { c } \widehat { \sigma } _ { j } - \widehat { \sigma } { + } \widehat { \Delta { \xi } } \widehat { \tau } ( \overline { { 2 } } ) } \end{array} } \end{array}
$$

其中 $\varPhi$ 为状态转移矩阵[]（关于状态转移的定义和推导见附录）。当 $n$ 为0时， $[ z _ { 0 } , \nu y _ { 0 } , \tau ] _ { ~ 0 } ^ { \mathrm { T } }$ 为 $t _ { 0 }$ 时刻的初始值，经过一次微分改正后，得到一个新的初始值 $[ z _ { 0 } , \nu y _ { 0 } , \tau ] _ { \mathrm { ~ l ~ } } ^ { \mathrm { T } }$ ，继续迭代（ $n$ 足够大）会得到满足精度要求的初始值 $[ z _ { 0 } , \nu y _ { 0 } , \tau ] _ { ~ n } ^ { \mathrm { T } }$ 。对于 $\mathrm { L } _ { 1 }$ 点用上述方法可以得到一条三维晕轨道，而对于 $\mathbf { L } _ { 2 }$ 点，用这种方法只能得到平面上的 Lyapunov 轨道，因为 $z _ { 0 }$ 总是收敛到0。为了得到三维的晕轨道，需要用前面得到的平面Lyapunov 轨道作为初始条件。固定 $z _ { 0 }$ ，使 ${ } _ { x _ { 0 } , \nu y _ { 0 } }$ ， $\boldsymbol { \tau }$ 为变量，那么（10）式含有3个未知数，因此采用微分改正法来求 $x _ { 0 }$ ， $\nu y _ { 0 }$ ，t:

$$
{ \left[ \begin{array} { l } { x _ { 0 } } \\ { v _ { y _ { 0 } } } \\ { \tau } \end{array} \right] } _ { n + 1 } = { \left[ \begin{array} { l } { x _ { 0 } } \\ { v _ { y _ { 0 } } } \\ { \tau } \end{array} \right] } _ { n } - { \left[ \begin{array} { l l l } { { \cfrac { \partial \phi _ { 2 } } { \partial x _ { 0 } } } } & { { \cfrac { \partial \phi _ { 2 } } { \partial v _ { y _ { 0 } } } } } & { { \cfrac { \partial \phi _ { 2 } } { \partial \tau } } } \\ { { \cfrac { \partial \phi _ { 4 } } { \partial x _ { 0 } } } } & { { \cfrac { \partial \phi _ { 4 } } { \partial v _ { y _ { 0 } } } } } & { { \cfrac { \partial \phi _ { 4 } } { \partial \tau } } } \\ { { \cfrac { \partial \phi _ { 6 } } { \partial x _ { 0 } } } } & { { \cfrac { \partial \phi _ { 6 } } { \partial v _ { y _ { 0 } } } } } & { { \cfrac { \partial \phi _ { 6 } } { \partial \tau } } } \end{array} \right] } _ { n | t _ { 0 } + \tau } ^ { - 1 } { \left[ \begin{array} { l } { \phi _ { 2 } } \\ { \phi _ { 4 } } \\ { \phi _ { 6 } } \end{array} \right] } _ { n | t _ { 0 } + \tau }
$$

，其中

$$
\begin{array} { r l } & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \partial ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \partial ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \partial ~ \hat { \gamma } ( \theta , \phi ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \partial ~ \hat { \gamma } ( \theta , 1 ) ~ } } \\ & { \mathrm { ~ \hat { \gamma } _ \phi Q ~ \textit { \hat { A } } \rho = ~ \partial ~ \hat { \gamma } ( \theta , 1 ) ~ } } \end{array}
$$

以 $\mathbf { L } _ { 2 }$ 为坐标原点，选取初始位置为 $( 7 4 5 2 4 . 0 , 0 , - 2 0 0 0 . 0 ) \mathrm { k m }$ ，初始速度为(0,-2763.0,0)km/day，初始半周期为6.30天。通过（1）式和（2式）进行无量纲化后,代入运动方程，并积分运动方程和状态转移矩阵，求解微分改正方程 (11)，最后得到满足一个平面 Lyapunov 轨道的初始条件(1.1817143086500759,0,3.5933035277813563× 10-22,0,-0.16170712205794957,0)。该轨道周期为14.8485511785天，位置偏量为 $1 . 5 7 8 0 1 6 3 2 0 2 4 \times 1 0 ^ { - 1 1 }$ ，Jacobian 积分常数为3.15056044173，状态转移矩阵的模为1.00000000018（接近于1），说明该轨道满足周期轨道条件。将平面Lyapunov 轨道的初始条件做一个小的改动，例如将 $\mathbf { \Delta } _ { Z _ { 0 } }$ 改动到 $1 . 5 \times 1 0 ^ { - 1 0 }$ ，其他不变。将其代入运动方程，并积分运动方程和状态转移矩阵，求解微分改正方程（13），得到一个稍微远离平面的晕轨道，然后将该晕轨道的 $\mathbf { \Delta } _ { Z 0 }$ 继续做一个小的改动，其他不变，再次代入运动方程，并积分运动方程和状态转移矩阵，求解微分改正方程（13），不断重复。最后得到一条轨道周为14.7843020586天，初始条件为(1.179549767505286,0,0.03662109375,0,-0.16319295932416145,0)的晕轨道（见图1和图2）。该轨道的位置偏量为 $1 . 5 5 5 6 3 1 2 7 5 5 9 \times 1 0 ^ { - 1 1 }$ ，Jacobian积分常数为3.14635368089，状态转移矩阵的模为0.999999999964（接近于1），说明满足周期轨道条件。

![](images/e970da489028af8eb9d448a65db64d4fa61c0836828f3de466685300eeb3c6ab.jpg)

图1地月系 $\mathrm { L } _ { 2 }$ 点的晕轨道三维轨迹图及其在3个平面的投影。图中的尺度单位为地月距离，即 $3 8 4 4 0 2 \mathrm { k m }$ ，月球大小和晕轨道尺度为等比例画出，原点位于地月系质心。

Fig1.Three-dimensional trajectory of Earth-Moon halo orbits around L2 and its projection on three   
orthogonal planes. The unit of length scale is in distance between Earth and Moon, namely $3 8 4 4 0 2 \mathrm { k m }$ ; the   
size of Moon and halo orbit are ploted in equal proportion,and the origin is located at the mass center of Earth-Moon system.

从中继星的晕轨道在YZ平面的投影可知，晕轨道距离月球的最小角距离约为 $1 . 2 4 ^ { \circ }$ ，而月球的角半径约为 $0 . 2 6 ^ { \circ }$ ，因此满月时月球的光背景可能对中继星激光测距产生一定影响。从文[6]的计算可知，当晕轨道的振幅不小于 $4 0 0 0 \mathrm { k m }$ 时即可实现月球无遮挡，本文中晕轨道的最小振幅为$2 3 8 3 2 \mathrm { k m }$ ，因此月球对该晕轨道没有遮挡。在确认满月对中继星激光测距的影响后，下面对中继星的测距成功率展开建模与分析。

![](images/57a5535ad6f9dbc028c1bec6e1a96047854f9fae9eb15b92ae4b75157ca19678.jpg)  
图2地月系 $\mathbf { L } _ { 2 }$ 点的晕轨道在 $X – Y$ 平面的投影和零速度曲线

Fig2. Projection of the Earth-Moon halo orbit around L2 and its zero velocity curve in X-Y Plar

# 2测距成功率模型

测距成功率指的是单光子探测器能够探测到至少一个光电子的概率。由于探测器探测光电子的概率服从泊松分布[12]，即

$$
P ( k ; \lambda ) = { \mathrm { e } } { - } { \lambda ^ { * } } ( \lambda ^ { k } / k ! ) ,
$$

测距成功率可以表示为

$$
\zeta = 1 { - } P ( 0 ; N ) = 1 { - } \mathrm { e } ^ { - N } ,
$$

其中, $N$ 为探测器产生的平均光电子数。光电子数越多信号越强，反之光电子数越少信号越弱。计算测距成功率的关键是计算探测器产生的平均光电子数，下文主要围绕如何计算探测器产生的平均光电子数展开讨论。

在不考虑望远镜抖动、大气抖动和中继星偏离预报轨道的理想情况下，望远镜发射的激光光斑中心理论上应该对准中继星，此时激光光斑的能量密度服从高斯分布（Gaussian Distribution），即

其中, ${ { E } _ { 0 } }$ 为光斑的总能量； $\rho$ 为光斑上任意一点到光斑中心的距离； $\rho _ { \mathrm { e } }$ 为光斑的特征半径并满足如下关系式：

取光斑的半径为1.5倍特征半径时，光斑内的能量占总能量的 $9 8 . 8 9 \%$ 。光斑半径 $\boldsymbol { r }$ 与激光发散角0，望远镜到中继星的距离 $R$ 以及望远镜有效口径 $D$ 之间的关系为

$$
r ^ { = } 1 / 2 ^ { * } ( R \theta + D )
$$

当考虑望远镜抖动、大气抖动[13]以及中继星的轨道偏离时，光斑的平均能量密 度分布可以表示为

其中,望远镜抖动 $g _ { \mathrm { t } } ( x , y ) \sim N ( 0 , \sigma ^ { 2 } _ { \mathrm { t } } \mathrm { I } )$ ；大气抖动 $\mathrm { \bf g } _ { \mathrm { a } } ( \mathrm { x } , \mathrm { y } ) \sim \mathrm { N } ( 0 , \sigma ^ { 2 } \mathrm { s I } )$ ；预报轨道偏离 $g _ { \mathrm { s } } ( x , y ) \sim \mathrm { N } ( 0 , \sigma _ { \mathrm { \ s } } ^ { 2 } \mathrm { I } )$ ; $I$ 为二阶单位矩阵；积分区域为整个光斑覆盖面 $R ^ { 2 }$ ；\*表示卷积运算[14]。对 (20)式进行推导并化简得大气抖动引起光斑中心漂移的均方差 $\sigma _ { \mathrm { ~ a ~ } } ^ { 2 }$ 表示为[15]其中； $r _ { 0 }$ 为大气相干长度； $k = 2 \pi / \lambda$ ， $\lambda$ 为激光波长。探测器探测到的光电子数 $N$ 可以表示为[1其中， $\eta _ { \mathrm { e } }$ 为望远镜发射系统的光学效率； $T _ { \mathrm { a } }$ 为大气透过率； $T _ { \mathrm { c } }$ 为卷云透过率①； $s$ 为中继星的有效反射面积； $\rho _ { \mathrm { r e f l e c t i o n } }$ 为反射器的反射率； $\scriptstyle \varOmega _ { \mathrm { r e f l e c t i o n } }$ 为中继星反射器的反射立体角， $\eta _ { \mathrm { r } }$ 为望远镜接收系统的光学效率； $\eta _ { \mathrm { q } }$ 为探测器的量子效率； $h$ 为普朗克常数； $\mathrm { ~  ~ c ~ }$ 为真空中的光速。中继星反射器的反射立体角 $\scriptstyle \varOmega _ { \mathrm { r e f l e c t i o n } }$ 与反射发散角 $\theta _ { \mathrm { r e f l e c t i o n } }$ 的关系如下

# 3结果与分析

在中继星激光测距过程中，取激光脉冲的能量 $\mathrm { E } _ { 0 }$ 为 $3 0 0 0 \mathrm { m J }$ ，测站到中继星的平均距离 $R$ 取测站到 $\mathbf { L } _ { 2 }$ 点的距离，即 $4 4 2 5 4 8 \mathrm { k m }$ ，望远镜的抖动标准差 $\sigma _ { \mathrm { t } }$ 为 $0 . 1 ^ { \mathfrak { n } }$ （乘以R换算成长度单位），大气的相干长度 $\mathbf { r } _ { 0 }$ 为 $1 0 \mathrm { { c m } }$ ，激光发射的发散角0为 $2 ^ { \circ }$ ，中继星的有效反射面积 $s$ 为 $0 . 0 2 2 7 \mathrm { m } ^ { 2 }$ ，反射器的反射率preflection为0.6，反射器的发散角 $\Theta _ { \mathrm { r e f l e c t i o n } }$ 为 $2 ^ { \circ }$ ，大气透过率Ta为0.6，卷云透过率$T _ { \mathrm { c } }$ 为0.1，望远镜发射系统的光学效率 $\eta _ { \mathrm { e } }$ 为0.4，接收系统的光学效率 $\eta _ { \mathrm { r } }$ 为 0.2，探测器的量子效率 $\eta _ { \mathrm { q } }$ 为 0.6，望远镜的有效口径 $D$ 为 $1 . 0 6 \mathrm { m }$ ，激光的波长 $\lambda$ 为 $5 3 2 \mathrm { n m } ^ { [ 1 7 ] }$ 。通过前面计算的晕轨道可知，测站到中继星的最近距离和最远距离分别为 $4 2 7 2 8 7 \mathrm { k m }$ 和 $4 5 1 8 8 9 \mathrm { k m }$ ，保持其他参数不变，预报轨道横向标准差 $\sigma _ { \mathrm { s } }$ 取 $0 \sim 5 \mathrm { k m }$ 时探测器产生的光电子数和测距成功率见图 3。

![](images/34339783a6a5f7fe61f612ca46ed292cb2a3957b9819847c5576eda370189633.jpg)  
图3光电子数（虚线）和测距成功率（实线）随中继星的横向预报轨道标准差的变化图，从左到右分别对应测站到中继星最近距离、平均距离、最远距离的情况

Fig3. Variations of the photoelectron numbers(dotted line) and the laser ranging success probability(solid line) with the transverse standard deviation of the predicted relay satelite orbit; from left to right are situations for the nearest, average,furthermost distance from station to the relay satellite.

从图 3中可看出光电子数和测距成功率随着中继星轨道横向标准差的增大而迅速减小，尤其是横向标准差位于 $1 \sim 2 \mathrm { k m }$ 时下降最快，超过 $2 \mathrm { k m }$ 后下降变缓。对于平均距离而言，当中继星没有偏离预报时，探测器产生的光电子数为0.151，成功率为 $1 4 . 0 7 \%$ ，偏离 $2 \mathrm { k m }$ 时的光电子数降为0.035，成功率降为 $3 . 4 6 \%$ ，此时光电子数和成功率分别衰减了 $7 6 . 8 \%$ 和 $7 5 . 4 \%$ ；对于最近距离而言，当中继星没有偏离预报时，探测器产生的光电子数为0.174，成功率为 $1 6 . 0 1 \%$ ，偏离 $2 \mathrm { k m }$ 时的光电子数降为0.038，成功率降为 $3 . 7 7 \%$ ，此时光电子数和成功率分别衰减了 $78 . 2 \%$ 和 $7 6 . 4 \%$ 对于最远距离而言，当中继星没有偏离预报时，探测器产生的光电子数为0.139，成功率为$1 3 . 0 2 \%$ ，偏离 $2 \mathrm { k m }$ 时的光电子数降为0.033，成功率降为 $3 . 2 9 \%$ ，此时光电子数和成功率分别衰减了 $7 6 . 2 \%$ 和 $74 . 7 \%$ 。通过对比最近距离与最远距离的情况，探测器产生的光电子数从0.174 降为0.139，成功率从 $1 6 . 0 1 \%$ 降为 $1 3 . 0 2 \%$ 。

# 4结语

本文针对即将发射到地月系 $\mathbf { L } _ { 2 }$ 点的中继星进行了晕轨道计算，根据轨道的对称性理论和微分改正法，从数值上给出了一条轨道周期为14.78天， $X$ 方向（地月连线方向）的振幅为$1 2 4 9 3 \mathrm { k m }$ ，Y方向为34596km， $Z$ 方向 (垂直于地月轨道平面方向)为 $1 1 9 1 6 \mathrm { k m }$ 的轨道。运行在该轨道上的中继星与月球的角距离约为 $1 . 2 4 ^ { \circ }$ ，而月球的角半径约为 $0 . 2 6 ^ { \circ }$ ，因此月球的光背景对中继星测距可能会产生一定的影响。另一方面，由于轨道的最小振幅远大于月球遮挡的临界振幅$4 0 0 0 \mathrm { k m }$ ，所以月球对中继星不存在遮挡问题。中继星在V波段的视星等暗于17等，已经超出了$1 . 2 \mathrm { m }$ 望远镜的极限星等，况且满月时望远镜受月光的影响，更加增加中继星可见的难度。随后在综合考虑大气抖动、望远镜抖动和中继星横向偏离预报轨道的情况下，建立了一个估算回波光电子数和测距成功率的模型。根据云台的激光测距系统对运行在该晕轨道上的中继星进行回波光电子数和测距成功率分析，结果表明光电子数和测距成功率随着中继星轨道横向标准差的增大而迅速减小，尤其是横向标准差位于 $1 \sim 2 \mathrm { k m }$ 时下降最快，超过 $2 \mathrm { k m }$ 后下降变缓。对于中继星到测站的平均距离而言，当中继星没有横向偏离时，探测器产生的光电子数为0.151，成功率为 $1 7 . 0 7 \%$ ；横向偏离$2 \mathrm { k m }$ 时，光电子数降为0.035，成功率降为 $3 . 4 6 \%$ 。对比最近距离与最远距离的情况，无横向偏移的情况下，探测器产生的光电子数从0.174降为0.139，成功率从 $1 6 . 0 1 \%$ 降为 $1 3 . 0 2 \%$ 。尽管最远距离与最近距离相差 $2 4 6 0 2 \mathrm { k m }$ ，但探测器产生的光电子数没有明显的改变，这是由于轨道的振幅相对于整个地月距离而言较小的缘故。

# 附录

# 1状态转移矩阵的定义和推导

给定一个动力学系统 $\mathrm { d X ( t ) / d t } = \mathrm { F ( X ( t ) ) }$ 和 $\mathbf { t } _ { 0 }$ 时刻的一个初始条件 $\mathrm { X ( t _ { 0 } ) }$ 以及 $\mathbf { t } _ { 0 }$ 时刻的一个微小扰动 $\mathrm { 8 X ( \ t _ { 0 } ) }$ ，随着时间的演化， $\mathrm { ~  ~ t ~ }$ 时刻该动力学系统的扰动变为SX(t)（见图4）。状态转移矩阵$\Phi ( \mathfrak { t } , \mathfrak { t } _ { 0 } )$ 描述了 $\mathbf { t } _ { 0 }$ 时刻的微小扰动 $\delta \mathrm { X ( \mathfrak { t } _ { 0 } ) }$ 与 t时刻 的微小扰动 δX(t)之间的关系，即

$$
\Phi ( \mathrm { t } , \mathrm { t } _ { 0 } ) { = } \hat { \sigma } \mathrm { X ( t ) } / \hat { \sigma } \mathrm { X ( \mathrm { t } _ { 0 } ) } ,
$$

状态转移矩阵实际上是微分方程 $\mathrm { d } \Phi ( \mathrm { t , t _ { 0 } } ) / \mathrm { d t } = \hat { \sigma } \mathrm { X ( t ) } / \hat { \sigma } \mathrm { X ( t ) } ^ { * } \Phi ( \mathrm { t , t _ { 0 } } )$ 的解，该微分方程的推导如下：因为

$$
\mathrm { d X ( t ) / d t { = } F [ X ( t ) ] } ,
$$

所以

$$
\mathrm { d } ( \mathrm { X } ( \mathrm { t } ) + \mathrm { \delta { \cal X } ( t ) ) \mathrm { d } t = \mathrm { F } } [ \mathrm { X } ( \mathrm { t } ) + \mathrm { \delta { \cal \delta X } ( t ) } ] ,
$$

一阶展开后，得到

$$
\mathrm { d } \mathrm { X } ( \mathrm { t } ) \mathrm { d } \mathrm { t } + \mathrm { d } [ \delta \mathrm { X } ( \mathrm { t } ) ] \mathrm { d } \mathrm { t } = \mathrm { F } [ \mathrm { X } ( \mathrm { t } ) ] + \hat { \sigma } \mathrm { F } / \hat { \sigma } \mathrm { X } ^ { \ast } \delta \mathrm { X } ( \mathrm { t } ) + \mathrm { O } [ \delta \mathrm { X } ( \mathrm { t } ) ] ,
$$

略去高阶项并化简得

由于

$$
\begin{array} { r } { \delta \mathrm { X ( t ) } = \Phi ( \mathrm { t , t _ { 0 } } ) ^ { * } \delta \mathrm { X ( t _ { 0 } ) } , } \end{array}
$$

将其代入上面的方程得到

$$
\mathrm { d } \Phi ( \mathrm { t , t _ { 0 } } ) / \mathrm { d } \mathrm { t } ^ { * } \delta \mathrm { X } ( \mathrm {  ~ t _ { 0 } ~ } ) = \hat { \sigma } \mathrm { F } / \hat { \sigma } \mathrm { X } ^ { * } \Phi ( \mathrm { t , t _ { 0 } } ) \delta \mathrm { X } ( \mathrm {  ~ t _ { 0 } ~ } ) ,
$$

最后化简得到

$$
\mathrm { d } \Phi ( \mathrm { t , t _ { 0 } } ) / \mathrm { d } \mathrm { t } { = } \hat { \sigma } \mathrm { F } / \hat { \sigma } \mathrm { X } ^ { \ast } \Phi ( \mathrm { t , t _ { 0 } } ) ,
$$

对该微分方程积分即可得到t时刻的状态转移矩阵 $\Phi ( \mathfrak { t } , \mathfrak { t } _ { 0 } )$ 。由定义可知 $\mathbf { t } _ { 0 }$ 时刻的 状态转移矩阵$\Phi ( \ t _ { 0 } , \ t _ { 0 } ) = \mathrm { { I } }$ ，其中I为单位矩阵。对于周期轨道有 $\Phi (  { \mathrm { \ t } } _ { 0 } { + } 2 \tau ,  { \mathrm { t } } _ { 0 } ) { = }  { }  { \mathrm { I } }$ ，其中 $\boldsymbol { \tau }$ 为半周期。

# 2中继星 $\mathbf { V }$ 波段视星等的估算

把太阳视为表面温度为5778K的黑体，那么单位面积单位波长的太阳辐射功率满足普朗克辐射 定律

![](images/99d9a4c904148fabb5abed3158273dde0892270a9be0b24c8bd834e6dd82dcfb.jpg)  
图4微小扰动随时间的演化示意图

Fig4. Evolution of the perturbation with the time by a trivial perturbation on the initial value.

其中，T为太阳表面温度； $\lambda$ 为波长；h为普朗克常数；c为光速。因为V波段的光谱范围为 $5 0 7 \mathrm { n m } \sim 5 9 5 \mathrm { n m }$ ，中心波长为 $5 5 1 \mathrm { n m }$ ，因此对 $\mathbf { M } ^ { \lambda } ( \mathrm { T } )$ 在V波段积分即可得到太阳表面单位面积的辐射功率 $\mathrm { F _ { s } }$

，

其中， $\lambda _ { 1 }$ 和 $\lambda _ { 2 }$ 为 $\mathrm { ~ v ~ }$ 波段的下限波长和上限波长。中继星接收到的太阳辐射功率 $\mathrm { F _ { R } }$ 可表示为

，

其中， ${ \sf R } _ { \mathrm { s } }$ 为太阳的半径； ${ \tt R } _ { \mathrm { E } }$ 为太阳到地月质心的距离；A为太阳帆的展开面积，此处取值为 $1 0 \mathrm { m } ^ { 2 }$ 。由中继星太阳帆反射到达测站的单位面积上的太阳辐射功率F为

，

其中， $\rho$ 为太阳帆的反射率，一般取值为1/6；R为中继星到测站的平均距离，取值为 $\mathbf { L } _ { 2 }$ 点到测站的距离，即 $4 4 2 5 4 8 \mathrm { k m }$ 。为了计算中继星在V波段的视星等，需要一个基准值，该基准值可取视星等为0的辐射源。测站单位面积接收到的辐射功率 $\mathrm { ~ F _ { 0 } ~ }$ 可表示为

，

其中， $\mathbf { v } _ { 1 }$ 和 $\mathbf { V } _ { 2 }$ 表示V波段的下限频率和上限频率； $\mathrm { F _ { v , 0 } }$ 为单位面积单位频率的功率，取值为3640Jy。最后根据星等计算公式

来求得中继星在V波段的视星等，结果为17.2。

# 3计算晕轨道的python代码

本文涉及的Python代码均可在 smellysheep.com上下载，主要包括：

·计算地月系5个平动点的位置，计算Jacobian积分常数，积分运动方程和状态 转移矩阵，求解微分改正方程，寻求 $\mathbf { L } _ { 2 }$ 点的平面 Lyapunov 轨道和三维晕轨道;

# 参考文献

[1] Abbott B P, Abbot R, Abbot T D, et al. GW170817: observation of gravitational waves from a binary neutron star inspiral[J]. Physical Review Letters,2017,119(16):161101(16pp).

[2] Luo J, Chen L S, Duan H Z, et al. TianQin: a space-borne gravitational wave detector[J]. Classical & Quantum Gravity,2015,33(3),035010(32pp).

[3] Irion R. Stellar pair whirls in a 5-minute dash[J]. Science,2002, 295(5562):1997.

[4]吴伟仁,王琼,唐玉华,等.“嫦娥 4号”月球背面软着陆任务设计 [J].深空探测学 报,2017,4(2):111-117.

Wu Weiren， Wang Qiong， Tang Yuhua,et al. Design of Chang' $\mathrm { e ^ { - 4 } }$ lunar farside soft-landing mission[J]. Journal of Deep Space Exploration,2017,4(2):111 -117.

[5]高珊,周文艳,梁伟光,等.地月拉格朗日L2点中继星轨道分析与设计[J].深空探测学报,2017,4(2):122-129.

Gao San， Zhou Wenyan, Liang Weiguang， et al. Trajectory analysis and design for relay satellite at Lagrange L2 point of Earth-Moon system[J]. Journal of Deep Space Exploration,2017,4(2) :122 -129.

[6] 孙超,唐玉华,李翔宇,等.地－月L2 点中继星月球近旁转移轨道设计[J].深空探测学报,2017,4(3):264-269+275.

Sun Chao， Tang Yuhua, Li Xiangyu,et al. Design of Earth-Moon L2 halo orbit transfer trajectory for relay satellite using lunar flybys[J]. Journal of Deep Space Exploration,2017,4(3):264-269+275.

[7]何芸,刘祺,田伟,等.地月第二拉格朗日点卫星激光测距技术研究[J].深空探测学报,2017,4(2):130-137.

He Yun, Liu Qi， Tian Wei,et al. Study on laser ranging for satellite on the second Lagrange point of Earth-Moon system[J].Journal of Deep Space Exploration,2017,4(2):130-137.

[8] Howell K C. Three-dimensional,periodic, ‘halo'orbits[J]. Celestial Mechanics,1984, 32(1):53-71.

[9]孙义燧,周济林.现代天体力学导论[M].北京:高等教育出版社,2008.

[10] Parker J S,Anderson R L. Low-energy lunar trajectory design[M].[S.1.]: John Wiley & Sons, 2014.

[11] Tapley B D, Schutz B E, Born G H. Statistical orbit determination[M].[S.1.]: Academic Press,2004.

[12] Henriksson M. Detection probabilities for photon-counting avalanche photodiodes applied to a laser radar system[J]. Applied Optics, 2005, 44(24):5140-5147.

[13]翟东升,汤儒峰,李春晓,等.实测中激光测距方程的完善[J].天文研究与技术,2017, 14(1):25-31.

Zhai Dongsheng,Tang Rufeng,Li Chunxiao， et al. An improvement of laser ranging equation in practical use [J].Astronomical Research & Technology, 2017,14(1) :25-31.

[14]Bromiley P A. Products and Convolutions of Gaussian Probability Density functions[R]// Tina Memo.2014.

[15] Yura H T. Short-term average optical-beam spread in a turbulent medium[J]. Journal of the Optical Society of America, 1973, 63(5):567-572.

[16]叶叔华,黄城.天文地球动力学[M].济南:山东科学技术出版社,2000.

[17]李祝莲,熊耀恒,何妙婵,等.云南天文台人造卫星激光测距系统原理[J].天文研究与技术—国家天文台台刊,2008,5(3):248-252.

Estimates of the success probability for relay satellite laser ranging around EM $\mathrm { L } _ { 2 }$ point LiChunxiao1²,Gao Qingpeng1,2,Li Yuqiang',Li Zhulian'   
(1.Yunnan Observatories， Chinese Academy ofSciences， Kunming 65001， China,   
Email:lcx@ynao. ac. cn; 2.University of Chinese Academy of Sciences, Beining 100o49,China)

Abstract: In order to identify the positional relationship between the Moon and the incoming relay satellite on a halo orbit around $L _ { 2 }$ of the Earth-Moon system,and then to evaluate the laser ranging success probability, in this paper we make a computation on the halo orbit with a request of about 14 days in its period,and establish a model given the tremble of the telescope,of the atmosphere and the transverse deviation from the predicted orbit. A numerical halo orbit is given with the period of 14.78 days，the amplitude of 24986km in X(along the line of Earth and Moon),69192km in Y,23832km in Z(orthogonal to the orbit plane of Earth and Moon). The minimum amplitude of the calculated halo orbit goes far beyond the Moon-sheltered critical amplitude which is generally 40ookm, thus no shade from the Moon on the relay satelite is existed. Based on the model of laser ranging success probability established previously，we make an analysis on the success probability according the laser ranging system at KUNL station(lnternational ID:782O)， the results indicating that the laser ranging success probability rapidly drops down with the increase of the orbit transverse standard deviation.For the average distance from the station to the relay satelite,the detector produces about O.151 photoelectrons within a single pulse and the corresponding success probability is $1 4 . 0 7 \%$ when there is no deviation from the predicted orbit; the number of photoelectrons drops down to 0.035 and the corresponding success probability down to $3 . 4 6 \%$ when the relay satellite transversely deviates 2km from the predicted orbit. Comparing between the nearest distance and the furthermost distance, with no deviation，the number of photoelectrons declines to 0.139 from 0.174 and the corresponding success probability down to $1 3 . 0 2 \%$ from $1 6 . 0 1 \%$ . All of the above results provide a reference for the realization of the relay satellite laser ranging with $1 . 2 \mathsf { m }$ telescope at Yunnan Observatory in the following days.

Keywords: Relay satellite Laser Ranging;Halo Orbit around $L _ { 2 }$ ; Laser Ranging success probability