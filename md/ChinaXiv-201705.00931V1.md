# 间断有限元法求解一维矢量辐射传输

王存海　易红亮　谈和平(哈尔滨工业大学能源与科学工程学院，哈尔滨150001)

摘要采用间断有限元法（Discontinuous finite element method,DFEM）求解一维散射性介质内矢量辐射传输问题。推导了散射性介质内矢量辐射传输方程的间断有限元离散格式，空间离散采用间断有限元离散将求解域划分为相互独立的单元，角度离散在传统的均匀分段光滑近似(Piecewise Constant Approximation,PCA）角度离散基础上进行局部加密以得到关键方向上的数值解。采用两个稳态矢量辐射传输算例对间断有限元法求解矢量辐射传输方程的正确性和计算效率进行了验证，在此基础上拓展间断有限元法应用于求解散射性介质内瞬态矢量辐射传输方程，将随着时间推移过程中的瞬态辐射信息和最终的稳态结果相比较验证了本文方法的正确性。

关键词间断有限元；矢量辐射传输；瞬态辐射传输；离散格式中图分类号：TK121 文献标识码：A 文章编号:0253-231X(2017)04-0833-08

# Discontinuous Finite Element Method for One-dimensional Polarized RadiativeTransfer

WANG Cun-Hai iYI HongLiang TAN He-Ping (School of Energy Science and Engineering,Harpih Institute of Technology，Harbin 150o01,China)

AbstractThe discontinuous finite element method (DFEM) is applied to solved the polarized radiative transfer in a one-dimensignalscattering medium. The derivation in a discrete form of the polarized radiation governing eqtations is presented, in which the spatial domain is discretized into finite non-overlapped disconthuous elements,and the angular space is discretized by the Piecewise Constant Approximation (PCA） approach with a local refined modification to obtain the numerical results for key directions. Two steady cases are tested to verify theaccuracy and computational effciency of the developed DFEM. The DFEM is then extended to solve the transient polarized radiative transfer in a scattering medium,the comparisons of theCime-resolved Stokes vector with the steady ones show that the developed DFEM can handle thetransient polarized radiative transfer in a scattering medium accurately. etp

Key wordsdiscontinuous finite element method;polarized radiative transfer;transient radiative transfer;discretization scheme

htt

# 符号表

（204号 $\boldsymbol { \mathit { I } }$ Stokes 矢量， $\mathrm { W / ( m ^ { 2 } ~ \mu m ~ s }$ r) $\scriptstyle n _ { \partial K }$ 单元 $K$ 外法线单位向量 $N _ { \varphi }$ $[ 0 , 2 \pi ]$ 空间圆周角离散个数 （204号 $\varOmega$ 单位方向矢量 （20 $W$ 权重函数 $M$ 离散方向总数 （202 $s$ 源项 $\mathrm { W / m ^ { 2 } }$ （204号 $N _ { \mathrm { e l m } }$ 离散单元格数 $\theta$ 天顶角 $\boldsymbol { r }$ 空间坐标向量，m （20 $N _ { \theta }$ $[ 0 , \pi ]$ 空间天顶角离散个数 $\varphi$ （20 圆周角 $\overline { { \overline { { \beta } } } }$ 衰减系数矩阵, $\mathrm { m } ^ { - 1 }$ $\mathrm { d } \theta$ （204号 $\scriptstyle \mathrm { d } \theta = N _ { \theta } / \pi$ ，单位天顶角大小 $\mu$ （20 （204号 $\mu = \cos \theta$ ，天顶角方向余弦 $\overline { { \overline { { z } } } }$ 散射矩阵 （204号 $N _ { \mathrm { d } \theta }$ $[ \pi - \mathrm { d } \theta / 2$ ， $\pi + \mathrm { d } \theta / 2 ]$ 天顶角局部加密离散个数 $\rho$ （2 漫反射率

# 0引言

矢量辐射信息相对于标量辐射信息能够更多地反应介质参数特性。半透明介质内矢量辐射传输方程的求解开拓了辐射传输理论在新兴领域的广泛应用，例如生物光学工程[1,2]，大气辐射传输[3,4]，遥感系统[5,6]，光学成像[7]，天体物理学[8]等。近年来，研究学者们发展了若干数值方法求解半透明介质内矢量辐射传输，包括蒙特卡罗法[9-11]，离散坐标法[12-14], $F _ { N }$ 方法[15]，谱元法[16]等。但这些方法往往具有各自的局限性，因此有必要发展稳定性较好具有高阶精度和高计算效率的数值方法求解半透明介质内矢量辐射传输。

间断有限元法最初由 Reed 和 Hill[17]于 1973年提出并被成功地应用于中子输运方程的求解。间断有限元在空间上的离散单元是相互分割的，其计算区域内单元之间的信息通过边界数值通量进行连接，具有高阶精度和较好的数值稳定性。间断有限元方法的优势使其受到重视并开始应用于半透明介质内辐射传输的求解。Cui 和Li[18,19]率先采用间断有限元方法求解了半透明介质内标量辐射传输，验证了间断有限元方法求解辐射传输的可行性。刘林华[20,21]采用间断有限元法求解了梯度折射率介质内辐射传输及半透明介质内瞬态辐射传输。这些工作显示出间断有限元法求解一维及多维辐射传输间题具有很好的前景。然而，目前尚未见到间断有限元法应用于求解半透明介质内矢量辐射传输问题的文献发表。本文发展了基于Lax-Friedrichs迎风格式的间断有限元法来求解一维半透明资质内的矢量辐射传输。采用2个稳态算例对间断有限元法求解一维散射性介质矢量内辐射传输的正确性进行了检验，并在此基础上拓展了间断有限元方法求解瞬态矢量辐射传输，将不同时刻的辐射信息同稳态结果进行对比验证了间断有限元法求解半透明介质内瞬态矢量辐射传输的有效性。

# 1辐射传输方程的间断有限元离散

考虑吸收、发射和散射灰介质内矢量辐射传输，离散坐标形式的辐射传输方程可以写为

$$
\boldsymbol { \Omega } \cdot \boldsymbol { \nabla } I \left( r , \boldsymbol { \Omega } ^ { n } \right) + \overline { { \overline { { \beta } } } } I \left( r , \boldsymbol { \Omega } ^ { n } \right) = \boldsymbol { S } \left( r , \boldsymbol { \Omega } ^ { n } \right)
$$

式中， $\pmb { I } = ( I , Q , U , V ) ^ { \prime }$ 代表 Stokes 矢量， $\varOmega$ 为离散方向， $\overline { { \overline { { \beta } } } }$ 为衰减系数矩阵， $s$ 为源项：

$$
S ( r , \Omega ^ { n } ) = \overline { { \overline { { \beta } } } } I _ { \mathrm { b } } ( r ) +
$$

$$
\sum _ { n = 1 } ^ { M } \bar { \bar { Z } } ( r , \Omega ^ { n ^ { \prime } } \to \Omega ^ { n } ) I ( r , \Omega ^ { n ^ { \prime } } ) w ^ { n ^ { \prime } }
$$

对于间断有限元，由于其空间离散节点相互独立的特点，其多项式节点基函数和加权余量法权函数都定义在每个基本单元上。以任一单元 $K$ 作为研究对象，选取权函数为 $K$ ，在单元上使用高斯散度定理进行积分，为了简洁省去表示方向的上标 $n$ ，式(1）可写为：

$$
\begin{array} { c } { { - < I , \Omega \cdot \nabla W > _ { K } + ( \overline { { { \Omega I } } } \cdot n _ { \partial K } , W ) _ { \partial K } + } } \\ { { < \overline { { { \beta } } } I , W > _ { K } = < S , W > _ { K } } } \end{array}
$$

式中， ${ \mathbf { } } n _ { \partial K }$ 表示单元 $K$ 边界的外法线单位向量。算子的定义为：

$$
< f , g > _ { K } = \int _ { K } f g \ d V , \quad ( f , g ) _ { \partial K } = \int _ { \partial K } f g \ d A
$$

式中， $\overline { { \Omega I } }$ 是相邻单元间的数值通量，本文采用LaxFriedriches数值通量格式：

$$
\widehat { \pmb { \Omega } \pmb { I } } = \pmb { \Omega } \bar { \pmb { I } } + | \pmb { \Omega } | \mathbf { 1 } \pmb { I } \pmb { n } _ { \partial K }
$$

式中， $\bar { I }$ 和表示相邻单元共同边界处辐射信息的平均值和间断值：

$$
\bar { \pmb { I } } = \frac { 1 } { 2 } ( { \pmb I } ^ { + } + { \pmb I } ^ { - } ) , \quad { \pmb I } = \frac { 1 } { 2 } ( { \pmb I } ^ { + } - { \pmb I } ^ { - } )
$$

式中， $I ^ { + }$ 和 $I ^ { - }$ 分别表示单元 $K$ 与相邻单元共同边界位置处单元 $K$ 内部以及外部的辐射信息。

$$
\begin{array} { c } { { { \pmb I } ^ { + } = \displaystyle \operatorname* { l i m } _ { \delta  0 } { \pmb I } \big ( { \pmb r } _ { \partial K } - \delta { \pmb n } _ { \partial K } \big ) , } } \\ { { { \pmb I } ^ { - } = \displaystyle \operatorname* { l i m } _ { \delta  0 } { \pmb I } \big ( { \pmb r } _ { \partial K } + \delta { \pmb n } _ { \partial K } \big ) } } \end{array}
$$

把式(5）带入式(3）可以得到矢量辐射传输方程的间断有限元离散形式：

$$
\begin{array} { r l r } {  { \mathcal { Q } ^ { * } < I , \pmb { \Omega } \cdot \nabla W > _ { K } + } } \\ & { } & { \| \overset { 1 } { \underset { < } { \sum } } \{ \pmb { \mathcal { E } } \pmb { \mathcal { D } } ^ { * } \pmb { n } _ { \partial K } + | \pmb { \Omega } | ) I ^ { + } , W \} _ { \partial K } + < \overline { { \beta } } I , W > _ { K } = } \\ & { } & { \| \overset { 1 } { \underset { < } { \sum } } s , W > _ { K } - \frac { 1 } { 2 } ( ( \pmb { \Omega } \cdot \pmb { n } _ { \partial K } + | \pmb { \Omega } | ) I ^ { - } , W ) _ { \partial K } \quad } \end{array}
$$

与传统有限元法需要构造全局节点基函数不同，间断有限元法只需要在每一离散单元上构造节点基函数。选取高斯－切比雪夫积分节点并在单元 $K$ 上采用具有 $\delta$ 函数的节点基函数近似，其Stokes矢量近似为：

$$
\begin{array} { c } { { I = I ^ { n } ( r ) \approx \displaystyle { \sum _ { i = 1 } ^ { N _ { s k } } } I _ { i } ^ { n } \phi _ { i } ( r ) } } \\ { { \overline { { \beta } } I = \overline { { \beta } } ( r ) I ^ { n } ( r ) \approx \displaystyle { \sum _ { i = 1 } ^ { N _ { s k } } } \overline { { \beta } } _ { i } I _ { i } ^ { n } \phi _ { i } ( r ) } } \\ { { S = S ^ { n } ( r ) \approx \displaystyle { \sum _ { i = 1 } ^ { N _ { s k } } } S _ { i } ^ { n } \phi _ { i } ( r ) } } \end{array}
$$

式中， $\phi _ { i } ( \pmb { r } )$ 为定义在单元 $K$ 上的节点基函数， $\pmb { I } _ { i } ^ { n }$ 为第 $\mathbf { \chi } _ { i }$ 个节点在第 $\boldsymbol { n }$ 个离散方向上的矢量辐射信

息， $N _ { s k }$ 为单元 $K$ 上的节点数。将式（9）代入式(8）中，可得单元 $K$ 上的矢量辐射传输方程的间断有限元离散格式：

$$
\overline { { \overline { { K } } } } ^ { n } \overline { { \overline { { I } } } } ^ { n } = \overline { { \overline { { H } } } } ^ { n }
$$

式中

$$
\bar { \bar { \textbf { I } } } ^ { n } = [ I _ { i k } ^ { n } ] _ { i = 1 , N _ { s k } ; k = 1 , 4 } = [ ( I _ { i } ^ { n } , Q _ { i } ^ { n } , U _ { i } ^ { n } , V _ { i } ^ { n } ) ] _ { i = 1 , N _ { s k } }
$$

$$
\overline { { \pmb { K } } } = [ K _ { j i } ^ { n } ] _ { j = 1 , N _ { s k } ; i = 1 , N _ { s k } } ,
$$

$$
\overline { { \pmb { H } } } ^ { n } = [ H _ { j k } ^ { n } ] _ { j = 1 , N _ { s k } ; k = 1 , 4 }
$$

刚度矩阵 $\overline { { \overline { { K } } } } ^ { n }$ 和右边向量 ${ \overline { { \overline { { H } } } } } ^ { n }$ 表示为：

$$
\overline { { \overline { { K } } } } _ { j i } ^ { n } = - < \phi _ { i } , \Omega ^ { n } \cdot \nabla \phi _ { j } > _ { K } +
$$

$$
\frac { 1 } { 2 } \left( ( \Omega ^ { n } \cdot n _ { \partial K } + | \Omega ^ { n } | ) \phi _ { i } , \phi _ { j } \right) _ { \partial K } +
$$

$$
< \overline { { \overline { { \beta } } } } _ { i k } \phi _ { i } , \phi _ { j } > _ { K }
$$

$$
\overline { { { \overline { { H } } } } } { } _ { j k } ^ { n } = < \overline { { { \overline { { S } } } } } { } ^ { n } , \phi _ { j } > _ { K }
$$

$$
- \frac { 1 } { 2 } \left( \left( \pmb { \Omega } ^ { n } \cdot \pmb { n } _ { \partial K } - | \pmb { \Omega } ^ { n } | \right) \overline { { \overline { { I } } } } _ { i k } ^ { n , - } , \phi _ { j } \right) _ { \pmb { \mathrm { i } } }
$$

物理学报》

对于Lax-Friedrichs格式而言角度量与空间量是分离的，式（12）可以简化为：

$$
\begin{array} { c } { { { \displaystyle { \overline { { \mathbf { K } } } } _ { j i } ^ { n } = - \pmb { \Omega } ^ { n } \cdot < \phi _ { i } , \nabla \phi _ { j } > _ { K } + \frac { \llangle } { 2 } \pmb { \Omega } ^ { n } \cdot ( n \phi _ { i } , \phi _ { j } ) _ { \partial K } + } } } \\ { { { \displaystyle { \frac { 1 } { 2 } | \pmb { \Omega } ^ { n } | ( \phi _ { i } , \phi _ { j } ) _ { \partial K } + < \overline { { \overline { { \beta } } } } _ { i } \phi _ { i } , \phi _ { j } > _ { K } } } } } \end{array}
$$

算子的定义如下：

$$
\begin{array} { c } { { < f , \phi _ { j } > = \displaystyle \sum _ { i = 1 } ^ { N _ { s k } } f _ { i } < \phi _ { i } , \phi _ { j } > } } \\ { { ( f , \phi _ { j } ) = \displaystyle \sum _ { i = 1 } ^ { N _ { s k } } f _ { i } ( \phi _ { i } , \phi _ { j } ) } } \end{array}
$$

矩阵 $\overline { { \overline { { H } } } } ^ { n }$ 可以改写为：

$$
\begin{array} { c } { { \displaystyle \overline { { { \overline { { H } } } } } _ { j } ^ { n } = \sum _ { i = 1 } ^ { N _ { s k } } \overline { { { S } } } _ { i } ^ { n } < \phi _ { i } , \phi _ { j } > _ { K } - } } \\ { { { } } } \\ { { \displaystyle \frac 1 2 { \cal { 2 } } ^ { n } \cdot \sum _ { i = 1 } ^ { N _ { s k } } I _ { i } ^ { n - } \big ( n _ { \partial K } \phi _ { i } , \phi _ { j } \big ) _ { \partial K } + } } \\ { { { } } } \\ { { \displaystyle \frac 1 2 | { \cal { 2 } } ^ { n } | \cdot \sum _ { i = 1 } ^ { N _ { s k } } \overline { { { \overline { { I } } } } } _ { i } ^ { n , - } \big ( \phi _ { i } , \phi _ { j } \big ) _ { \partial K } } } \end{array}
$$

至此，矢量辐射传输方程的间断有限元离散已经完成，只需要计算得到离散单元的矩阵并在角度方向上循环迭代即可得到各节点的辐射信息。由于

式 (10)右边源项中的散射项包含其他方向的辐射信息，因此需要类似于离散坐标法的全局迭代进行收敛判断。

# 2结果及分析

本文只针对一维问题进行验证，以上公式中的方向角 $\varOmega = \mu i$ ，每个单元的节点数 $N _ { s k } = 2$ 。本文所有程序均在处理器为Intel(R)Core(TM) i7-4720 HQCPU $\textcircled { \Omega } 2 . 6 \operatorname { G H z }$ ，内存为8GB的个人计算机上运行。

# 2.1散射性平板介质中矢量辐射传输

考虑平行光入射一维散射性介质，此问题被称为经典的‘ $\scriptstyle : { \cal L } = 1 3 "$ 问题，由Garcia 和 Siewert[15]提出。模型上表面为透明界面，下表面为反射率 ${ \rho = } 0 . 1$ 的漫反射界面，界面温度为0K并忽略介质发射。平行光入射方向为 $\cos \theta _ { c } = 0 . 2 , \phi _ { c } = \pi / 2$ ，入射功率为$\pi$ 。平板间均匀分布具有米Mie 散射性质的介质，介质光学厚度 $\tau = \beta H = 1 . 0$ ，散射反照率 $\omega = 0 . 9 9$ ，不射光波长 $\lambda = 0 . 9 5 1$ ，其散射相矩阵由 Evens 和Stephen 在文献[22]中给出。

采用DFEM法对此问题进行求解，空间离散为20个均匀单元。为了将结果和和文献[15]结果进行对比，输出量 $I _ { * } , Q _ { * } , U _ { * } , V _ { * }$ 分别表示 Stokes 矢量的漫射量。首先进行网格无关性验证，位置 $z / H = 0 . 5$ 处的 Stokes 矢量 ${ { I } _ { * } }$ 和 $V _ { * }$ 在方向余弦 $\mu = [ - 1 , 1 ]$ 范围内具有显著的变化趋势，选取其作为网格无关性判断参数。图 $\Psi$ 给出了5种不同角度离散条件下$z / H = 0 . 5$ 处的 $I _ { * }$ 和 $V _ { * }$ 的分布曲线，不同角度离散条件下的计算时间如表1所示。

由图1所示结果可知，当角度离散个数达到$\backslash \mathrm { W } _ { \theta } ^ { \mathrm { } } \times N _ { \varphi } = 4 0 \times 6 0$ 时，增加角度离散个数对计算结果的影响不再显著，到达网格无关性要求。

综合考虑计算效率和精度本文选取角度离散为$N _ { \varphi } \times N _ { \theta } = 4 0 { \times } 6 0$ 计算得到了三个不同高度位置处的Stokes矢量角度分布，将计算结果与Garcia和

![](images/6f9f6558c8d204666583ecdcb156ea6dddd65d76c04acf27b2a1871128ffa8d9.jpg)

![](images/b0f26a836e55facb42f37d9df42b7686096c1be2a454129738323647925390c6.jpg)  
图1网格无关性验证Fig.1 Grid independence validation

# 表1不同角度离散条件下计算时间

Table 1 Computation time for different angular discretization schemes   

<html><body><table><tr><td>角度离散Ng×N</td><td>计算时间Time/s</td></tr><tr><td>Ne ×N=20×20</td><td>15.0784</td></tr><tr><td>Ne ×N=20×40</td><td>32.5988</td></tr><tr><td>Ne ×N=40×40</td><td>92.0667</td></tr><tr><td>Ne ×N=40×60</td><td>174.1708</td></tr><tr><td>Nθ ×N=60×100</td><td>1032.65638 学报</td></tr></table></body></html>

Siewert采用 $F _ { N }$ 方法得到的结果进行对比，如图2所示。由图2可知本文计算结果和文献结果对比吻合很好，验证了本文发展的间断有限元法求解散射性介质内矢量辐射传输问题的有效性。

文献[15]中给出了天顶角 $\mu = + 0$ 和 $\mu = - 0$ 的辐射信号值，然而由图2可以看出采用传统PCA角度离散格式所得结果曲线并不包含 $\mu = + 0$ 和 $\mu$ $= - 0$ 的辐射信息值。为了解决这一问题，本文作者在传统PCA角度均匀离散格式的基础上对角度划分进行局部加密处理，将包含 $\mu = 0 ( \theta = \pi / 2 )$ 的角度范围 $[ \pi / 2 - \mathrm { d } \theta / 2 , \pi / 2 + \mathrm { d } \theta / 2 ]$ 继续均匀划分为Nde份，这相当于角度划分总数为 $N _ { \theta } + N _ { \mathrm { d } \theta }$ ，这种处理方法在不需要大幅提高计算时间的情况下得到 $\scriptstyle \mu = 0$ 附近的Stokes矢量。取 $N _ { \mathrm { d } \theta } = 1 0$ 对上述算例进行计算，本算例所需时间为282.3374s。由图3可知采用角度局部加密方法对角度进行离散可以得到关键方向 $\mu = 0$ 处 (辐射信号有阶跃变化)的辐射信息，这对问题求解的精度具有很大的提升，这种局部加密角度离散方法对求解在某些特殊方向精度要求很高的问题具有很好的效果。

![](images/2d4faa123d9ef7d1e2ab4618149e5baae666e45fc2965d00e22fe7c074003dd4.jpg)

![](images/6aa358314a040155953ee4329da3a9bbd2ccc885aa57f16e9a73c9994fa87fea.jpg)  
图2间断有限元所得 Stokes矢量和 $F _ { N }$ 方法所得结果对比 Fig.2 Comparisons of Stokesvector components by DFEM withthose obtainedby the $F _ { N }$ method

# 2.2两层介质中矢量辐射传输

考虑Evans等在文献22中所研究的两层介质模型如图4所示，该模型上层是厚度为 $4 ~ \mathrm { k m }$ 的冰层，其衰减系数 $\beta _ { i } = 0 . 1 3 5 3 6 ~ \mathrm { k m ^ { - 1 } }$ ，散射反照率 $\omega _ { i }$ $= 0 . 9 8 1 9$ ；下层是厚度为 $4 ~ \mathrm { k m }$ 的雨层，其衰减系数

![](images/08648eab87fe4f19ebeb49051791ee80940699ecda34a46020640049b7d781be.jpg)  
Fig.4 Physical model of a two-layer medium system

![](images/72a32e70027737fdafd6d1cef7fc077e2892d41e52acc747c0fbeffd866573b8.jpg)  
图4双层介质物理模型

![](images/8ad36c10843bf8b6f3d5e3c1c815e8f15c8000fe93e1214d2e4e6fb044aae7a4.jpg)  
图3局部加密角度条件下 $z / H { = } 1$ 处 Stokes 矢量分布 Fig.3 Stokes vector component distributions at $z / H { = } 0$ with local refine angular discretization

本文采用间断有限元方法将空间离散为20个单元，采用上述局部加密方法进行角度离散，取 $N _ { \theta } =$ 4w, $N _ { \mathcal { S } } \mathcal { Q } _ { \sf { \sf { F } } } ^ { \sf { A } } \widehat { \sf { F } } \widehat { \sf { F } } \widehat { \sf { F } } \widehat { \sf { F } } , \widehat { N } { \sf { d } } \theta = 1 0$ ，所需计算时间为 $5 3 5 . 0 9 0 4 \mathrm { s } _ { \mathrm { \ell } }$ 将所得Stokes矢量输出为频率为 $8 5 . 5 \mathrm { G H z }$ 的辐射亮温，结果如图5所示。可以看出本文采用间断有限元法所得计算结果和文献[22]采用doubling-adding算法所得结果吻合得很好，最大相对误差不超过 $2 \%$ 0此外，由图示可以看出在 $\mu = 0$ 处的 Stokes 矢量具有突变或者显著的变化率，且 $z / H = 1$ 处的 $Q$ 在 $\mu$ $= 0$ 会有负值出现。本文采用的角度离散方法可以很好的捕捉到这些细微变化趋势和详细数值信息，而文献[22]中的数据并不能反映出这些特点，体现出本文采用计算方法的先进性。

# 2.3瞬态矢量辐射传输

考虑辐射传输方程中辐射强度随时间的变化，类似于式 (1)，瞬态矢量辐射传输控制方程为可写

$$
\begin{array} { l } { \displaystyle \frac { 1 } { c } \frac { \partial I ( \boldsymbol { r } , \boldsymbol { \Omega } ^ { n } , t ) } { \partial t } + \boldsymbol { \Omega } \cdot \nabla I ( \boldsymbol { r } , \boldsymbol { \Omega } ^ { n } , t ) + } \\ { \overline { { \overline { { \beta } } } } I ( \boldsymbol { r } , \boldsymbol { \Omega } ^ { n } , t ) = S ( \boldsymbol { r } , \boldsymbol { \Omega } ^ { n } , t ) } \end{array}
$$

![](images/6326dda7fdec9ef6365953168f9c36962f670467af76797a4d273628b87e9103.jpg)  
图5两层介质内矢量辐射传输

类似于稳态辐射传输方程，瞬态辐射传输方程在时刻 $\scriptstyle t = m \Delta t$ 的辐射传输方程可以整理为矩阵形式：

$$
\overline { { \overline { { K } } } } ^ { n , m } \overline { { \overline { { I } } } } ^ { n , m } = \overline { { \overline { { H } } } } ^ { n . m }
$$

$$
\overline { { { K } } } _ { j i } ^ { n , m } = - < \phi _ { i } , \pmb { \Omega } ^ { n } \cdot \phi _ { j } > _ { K } +
$$

$$
\begin{array} { c } { { \displaystyle \frac 1 2 \left( \left( \boldsymbol { \varOmega } ^ { n } \cdot \boldsymbol { n } _ { \partial K } + \left| \boldsymbol { \Omega } ^ { n } \right| \right) \phi _ { i } , \phi _ { j } \right) _ { \partial K } + \bigwedge _ { \partial K } ^ { \bar { \mathsf { S } } } \bar { \mathsf { S } } } } \\ { { \displaystyle < \overline { { \bar { \beta } } } _ { i } \phi _ { i } , \phi _ { j } > _ { K } } } \\ { { \overline { { H } } _ { j } ^ { n , m } = < \overline { { \bar { \boldsymbol { S } } } } ^ { n , m } , \underbrace { \lambda \overline { { \mathsf { S } } } ^ { \bar { \mathsf { S } } , m } } _ { \partial K } \big . } } \\ { { \displaystyle - \frac 1 2 \left( \left( \boldsymbol { \Omega } ^ { n } \cdot \boldsymbol { n } _ { \partial K } - \left| \boldsymbol { \Omega } ^ { n } \right| \right) \overline { { T } } _ { i } ^ { \prime , m , - } , \phi _ { j } \right) _ { \partial K } } } \end{array}
$$

$$
\overline { { \overline { { \beta } } } } _ { i } = \frac { 1 } { L \Delta t ^ { * } f } + \overline { { \overline { { \beta } } } } _ { i }
$$

$$
\begin{array} { c } { { \overline { { \widetilde { S } } } ^ { n , m } = \overline { { S } } ^ { n , m } ( r , \varOmega ^ { n } ) + \left( \displaystyle \frac 1 f - 1 \right) ^ { \overline { { S } } ^ { n , m - 1 } } - } } \\ { { - } } \\ { { \left( \displaystyle \frac 1 f - 1 \right) \varOmega ^ { n } \cdot \nabla \overline { { I } } ^ { n , m - 1 } - } } \\ { { \left[ \overline { { \beta } } \left( \displaystyle \frac 1 f - 1 \right) - \displaystyle \frac 1 { L \Delta t ^ { * } f } \right] \overline { { I } } ^ { n , m - 1 } } } \end{array}
$$

式中，上标 $\mathbf { \Psi } _ { n }$ 代表离散方向， $m$ 代表时刻 $\textit { t } =$ $m \Delta t ^ { * }$ ， $t ^ { * } = c t / L$ 为无量纲时间， $\boldsymbol { c }$ 为真空中光速， $\mathbf { \Psi } _ { t }$ 为时间， $L$ 为模型厚度， $f = 1 / 2$ 为Crank-Nicolson时间离散格式的调节因子。

采用类似于间断有限元法求解半透明介质内稳态矢量辐射传输方程的计算流程，在迭代过程中考虑时间项的迭代即可构造瞬态矢量辐射传输方程的计算流程。以本文3.2节双层模型算例进行验证，介质参数不变的情况下界面温度在 $t = 0$ 时刻突变为图4中所示的界面温度，介质温度为 $0 \mathrm { { K } }$ 。采用间断有限元方法进行求解，空间离散单元个数为20，角度离散个数为 $N _ { \varphi } \times N _ { \theta } = 4 0 { \times } 4 0$ 个，无量纲时间步长取为 $\Delta t ^ { * } = 0 . 1$ ，最大无量纲时间为40。

由于模型为两层介质，分界面处两侧的介质性质具有显著差异，分析其投射辐射空间分布随时间变化，选取不同时刻时投射辐射进行对比如图6所示。可以看出，开始的一段时间内，介质散射性质的差异使投射辐射 $G$ 在两种介质交界面（ $scriptstyle \langle z = 4 \mathrm { ~ k m } ,$ 两侧分布明显不同，随着时间的推移，能量分布逐渐趋于均匀，投射辐射 $G$ 的曲线逐渐变成光滑曲线并趋于稳态结果，这也进一步证明了采用间断有限元方法求解瞬态矢量辐射传输结果的正确性。

![](images/010bd7a0bf81ecfffea3ba1ed1eba80c7ef1daf1a03b9b633127f97d8dae2eff.jpg)  
Fig.5 Vector radiative transfer in a two-layer medium system   
图6投射辐射随时间变化的曲线图

e

图7所示为 $z / H { = } 0$ 和 $z / H { = } 1$ 处 Stokes矢量随时间的变化云图。由图示可知, $z / H { = } 0$ 处，Stokes 分量I 的值随着时间的推移一直在逐步增大，在无量纲时间 $t ^ { * } = 2 0$ 左右到达稳定；Stokes分量 $Q$ 的值在$\mu = [ 0 , 0 . 5 ]$ 范围内出现了先增大后减小的情况， $Q$ 也在 $t ^ { * } = 2 0$ 左右逐渐趋于稳定状态。相应的在 $z / H { = } 1$ 处，Stokes 分量 $Q$ 在 $\mu = [ 0 , 0 . 5 ]$ 范围内先增大后减小，但是幅度没有 $z / H { = } 0$ 的强烈。

![](images/9be5debcb5be76def84085a3b0d692d3d6add0c6e83034f120807afc95e7ba1c.jpg)  
Fig.6 Incident Iadiation distributions at different time

![](images/9fb6453c4f89bb16ff0a5e2b4dca1ec96ab9070cddac09cb912b11623e82aae5.jpg)  
图7两层介质中Stokes矢量的时域分布 Fig.7 Time-resolved Stokes vector components in the two-layer medium

# 3结论

将间断有限元方法(Discontinuous finite elementmethod，DFEM）应用于一维散射性介质内矢量辐射传输方程的求解。空间离散采用间断有限元离散，在每个独立单元上对辐射信息进行近似，单元之间通过包含辐射信息平均值和间断值的数值通量连接，角度离散在传统的均匀分段光滑近似(Piece-wise Constant Approximation，PCA）角度离散基础上进行局部加密以得到关键方向上的精确数值解，给出了散射性介质内矢量辐射传输方程的间断有限元离散格式。采用两个稳态算例进行对比验证，结果表明本文发展的求解散射性介质内矢量辐射传输得 DFEM有很好的精度和计算效率。相比于传统均匀PCA角度离散方法，本文采用的局部角度加密离散方法在不需要大幅增加计算时间的条件下可以得到关键方向的加密结果，这种局部加密角度离散方法对求解在某些特殊方向精度要求很高的问题具有很好的适用性和计算效率。在求解稳态矢量辐射传输的基础上本文采用 DFEM 求解了一维散射性介质内瞬态矢量辐射传输问题，将不同时刻的辐射信息和稳态时结果对比验证了DFEM求解散射性介质内瞬态矢量辐射传输问题的正确性。

# 参考文献

[1] Tuchin V V,Wang L, Zimnyakov D A.Optical Polarization in Biomedical Applications [M]. Springer Science & Business Media,2006   
[2] Bordier C,Andraud C,Charron E,et al. Radiative Transfer Model with Polarization Effects Applied to Organic Matter [J]. Physica B: Condensed Matter, 2007,394(2): 301-305   
[3]Hasekamp O P,Landgraf J.A Linearized Vector Radiative Transfer Model for Atmospheric Trace Gas Retrieval [J]. Journal of Quantitative Spectroscopy and Radiative Transfer,2002,75(2):221-238   
[4] Kokhanovsky A A,Budak V P,Cornet C,et al. Benchmark Results in Vector Atmospheric Radiative Transfer [J]. Journal of Quantitative Spectroscopy and Radiative Transfer,2010,111(12):1931-1946   
[5] Chami M,Santer R,Dilligeard E.Radiative Transfer Model for The Computation ofRadiance and Polarization in an Ocean-atmosphere System:Polarization Properties of Suspended Matter for Remote Sensing [J]. Applied Optics,2001,40(15): 2398-2416   
[6] HasekamβO P, Landgraf J. Linearization of Vector Radiative Transfer with Respect to Aerosol Properties and Its Use in Satellite Remote Sensing [J]. Journal of Geophysical Research:Atmospheres,2005,110:D04203   
[7]Jacques S L,Roman J R,Lee K.Imaging Superficial Tissues with Polarized Light [J]. Lasers in Surgery and Medicine,2000,26(2): 119-129   
[8]Hovenier J W,van der Mee C V M,Domke H. Transfer of Polarized Light in Planetary Atmospheres: Basic Concepts and Practical Methods [M]. Springer Science $\&$ （20 Business Media,2014   
[9] Kattawar G W, Plass G N.Radiance and Polarization of Multiple Scattered Light from Haze and Clouds [J].Applied Optics,1968,7(8):1519-1527   
[10]Davis C,Emde C,Harwood R.A 3-D polarized reversed Monte Carlo Radiative Transfer Model for Millimeterand Submillimeter Passive Remote Sensing in Cloudy Atmospheres [J].Geoscience and Remote Sensing,IEEE Transactions on Geoscience and Remote Sensing, 2005,43(5): 1096-1101   
[11] YI Hongliang,BEN Xun,TAN Heping. Transient Radiative Transfer ina Scattering Slab ConsideringPolarization [J].Optics Express,2013,21(22): 26693-26713   
[12] Weng F.A Multi-layer Discrete-ordinate Method for Vector Radiative Transfer in a Vertically-inhomogeneous, Emitting and Scattering Atmosphere-I.Theory [J]. Journal of Quantitative Spectroscopy and Radiative Transfer, 1992,47(1):19-33   
[13]Haferman JL，Smith T F,Krajewski W F.A Multidimensional Discrete-ordinates Method for Polarized Radiative Transfer.Part I:Validation for Randomly Oriented Axisymmetric Particles [J].Journal of Quantitative Spectroscopy and Radiative Transfer,1997,58(3):379- 398   
[14] Siewert C E.A Discrete-ordinates Solution for Radiativetransfer Models That Include Polarization Effects [J]. Journal of Quantitative Spectroscopy and Radiative Transfer,2000,64(3):227-254   
[15]Garcia R D M,Siewert C E.The $F _ { N }$ method for Radiative TransferModels ThatIncludePolarizationEffects [J].Journal of Quantitative Spectroscopy and Radiative Transfer,1989,41(2):117-145   
[16] Zhao Junming,LIU Linhua,Hsu P,et al. Spectral Element Method for Vector Radiative Transfer Equation [J].Journal of Quantitative Spectroscopy and Radiative Transfer,2010,111(3):433-446   
[17]Reed WH,Hill T.Triangular Mesh Methods for the Neutron Transport Equation [R].Los Alamos Report LA-UR73-479,1973   
[18]Cui X,Li B Q.An Unstructured Discontinuous Finite Element Method for Three-DimensionalRadiative TransferinParticipating Media [C]//ASME 2004International Mechanical Engineering Congress and Exposition.American Society of Mechanical Engineers,2004:95-103   
[19] Cui X,Li B Q.Discontinuous Finite Element Solution of 2-D Radiative Transfer with and without Axisymmetry [J].Journal of Quantitative Spectroscopy and Radiative Transfer,2005,96(3):383-407   
[20]LIU Linhua,LIU Lijun.Discontinuous Finite Element Method for Radiative Heat Transfer in Semitransparent Graded Index Medium [J].Journal of Quantitative Spectroscopy and Radiative Transfer,2007,105(3):377-387   
[21]LIU Linhua,Liu Lijun.Discontinuous Finite Element Approach for Transient Radiative Transfer Equation [J]. Journal of Heat Transfer,2007,129(8):1069-1074   
[22] Evans KF,Stephens G L.A New Polarized Atmospheric Radiative Transfer Model [J]. Journal of Quantitative Speetroscopy and Radiative Transfer，1991,46(5):413-

![](images/7d2fc3f0d03501eb47ca689ea3ef8653e56ac6f2aeb6d35a75b7e17e234d518c.jpg)