# 中红外激光测量扩散火焰温度场

黄燕 张国勇 刘训臣 齐飞(上海交通大学机械与动力工程学院，上海 200240)

摘要本研究基于二氧化碳气体 $\mathbf { \sigma } _ { \mathbf { V } 3 }$ 基础吸收带的直接吸收光谱测量乙烯同轴扩散火焰的温度场。实验采用波长为4.17微米的室温带间级联激光器(interband cascade laser)，测量此吸收带多个吸收峰通过轴对称火焰的路径积分吸收，并通过阿贝尔逆变换方法，反演得出火焰不同高度吸收率沿火焰径向的分布，进而参考HITRAN数据库通过最小二乘法拟合实验数据得到火焰中二氧化碳的温度场分布。为了提高阿贝尔转化的精度，本文采用正则化阿贝尔转化方法，并通过数值模拟验证了正则化方法的可行性。

关键词 轴对称扩散火焰；量子级联激光；阿贝尔逆变换；温度；二氧化碳中图分类号： TK16 文献标识码：A

# Temperature Distribution of Axisymmetric Diffusion Flame Measured by

# Mid-infraredlaser

HUANG Yan ZHANG Guo-YongLIU Xun-Chen QI-Fei (School of Mechanical Engineering,Shanghai Jiao Tong University，Shanghai,2Oo240, China)

Abstract:Temperature distribution of axisymmetric ethylene-air coflow flame was measured by direct absorption spectroscopy at the v3 band of carbon dioxide.A room temperature interband cascade laser (ICL） was used to continuously scan wavelength at the bandhead region near 4.17 μm. Along the axisymmetric coflow difusion flame，the path integrated absorption signal was inversed to linear absorption coefficients through Abel inversion，which was then non-linear least square fited with HITRAN database to reconstruct the temperature and carbon dioxide distributions in the flame.In order to increase the accuracy of Abel inversion, Tikhonov regularization method was used and its feasibility was verified through numerical simulation.

Key wordsaxisymmetric coflow flame; infrared laser; Abel inversion; temperature; carbon dioxide

# 0引言

层流同轴扩散火焰作为一种标准火焰，常用于碳烟生成和燃烧化学的研究[1,2]。火焰的温度场和燃烧产物浓度信息是重要的火焰参数，决定了碳烟的生成、氧化和燃烧反应的速率。热电偶常被用于气体温度的测量。然而，对火焰采用热电偶测温时，热电偶焊点周围的辐射热传导可导致焊点与周围气体之间存在热不平衡，且用于制作高温热电偶的材料在火焰环境中的不稳定会增加辐射传热校正中相关的不确定性[3]。可调谐二极管激光吸收光谱(TDLAS)技术可实现火焰中温度和气体浓度的原位测量[4-6]。火焰中的二氧化碳在 4.17 微米的中红外波段有较强的吸收。在该波长附近，无需考虑空气中其他气体物质或火焰中的其他气体燃烧产物对激光的吸收干扰，因而便于测量且精度较高[56]。直接吸收光谱技术测量的是沿激光路径的积分信号，对于非均匀分布的火焰参数，通常需要采用层析方法对激光路径上各个位置处的火焰参数进行重构7。对于轴对称火焰，如层流平面预混火焰和层流同轴扩散火焰，温度和气体浓度等火焰参数呈轴对称径向分布，因此可通过测量距离火焰中心不同距离的路径积分信号和阿贝尔逆变换方法反演重构。

阿贝尔逆变换在科学和工程上具有广泛应用，目前已发展了许多不同的逆变换方法，其中最常用的是Onion-Peeling(下文中称 OP)和 Abel ThreePoint(下文中称 ATP)方法[8]。然而此类方法由于其相应矩阵方程的病态特性[9-11]，实验信号的微小误差在反演求解过程中会被放大，使得反演结果明显偏离真实值。Tikhonov正则化方法被证实可以有效地减少阿贝尔逆变换的误差[9-11]。正确使用Tikhonov正则化方法的关键在于确定合适的正则化参数，其中L-curve方法是常用的确定正则化参数的方法[9-11]。

使用TDLAS技术结合阿贝尔逆变换方法重建轴对称火焰温度场的工作多针对于平面火焰[6,8],还未有使用该方法对扩散火焰温度场的研究。本文通过数值模拟验证了正则化方法的适用性，并通过4.17微米波长的室温带间级联激光(ICL)测量乙烯同轴扩散火焰中二氧化碳的路径积分吸收信号，结合阿贝尔逆变换和HITRAN 数据库拟合获得了乙烯扩散火焰的温度分布。

1基本原理和数值模拟

# 1.1直接吸收光谱原理

TDLAS技术建立在比尔郎伯吸收定律的基础之上，当频率为 $\nu$ 的激光束穿过长度为 $L$ 的被测气体时，激光光强的透过率 $T _ { \nu }$ 可由沿光程的吸收率积分得到：

$$
T _ { \nu } = ( \frac { I } { I _ { 0 } } ) _ { \nu } = \exp [ - \int _ { 0 } ^ { L } \alpha ( l , \nu ) \cdot d l ]
$$

$$
\alpha ( l , \nu ) { = } \sum _ { j } \chi ( l ) \cdot S _ { j } ( T ( l ) ) \cdot f _ { j } ( ( \nu - \nu _ { 0 j } ) , T ( l ) )
$$

式中， $I _ { 0 }$ 和 $I$ 分别为入射激光强度和透过激光强度， $\chi ( l )$ 为 $l$ 位置处的被测气体的摩尔分数，$\alpha ( l , \nu )$ 为 $l$ 位置处的被测气体对频率为 $\nu$ 的激光的吸收率，吸收系数 $S _ { j }$ 是跃迁 $j$ 的谱线强度， $f _ { j }$ 是跃迁 $j$ 的线型函数， $\nu _ { 0 j }$ 是跃迁 $j$ 的中心跃迁频率。线强 $S _ { j }$ 与温度 $T$ 的关系可由下式确定：

$$
S _ { j } ( T ) = S _ { j } ( T _ { 0 } ) \frac { Q _ { j } ( T _ { 0 } ) } { Q _ { j } ( T ) } \frac { T _ { 0 } } { T } \exp [ - \frac { h c E _ { j } ^ { ~ \prime } } { k } ( \frac { 1 } { T } - \frac { 1 } { T _ { 0 } } ) ]
$$

$$
\times [ \frac { 1 - \exp ( - h c \nu _ { 0 j } / k T ) } { 1 - \exp ( - h c \nu _ { 0 j } / k T _ { 0 } ) } ]
$$

式中， $h$ 为普朗克常数， $\boldsymbol { \mathscr { c } }$ 为光速， $k$ 为波尔兹曼常数， $T _ { \phantom { } _ { 0 } }$ 为参考温度(通常为296 K)， $\boldsymbol { E } _ { j } ^ { " }$ 为吸收跃迁的低能级能量， $Q ( T )$ 是配分函数[12]。从上式可以看出，线强仅与温度有关。

本研究中的常压扩散火焰测量的光谱线型可通过Voigt线型来描述。Voigt线型由高斯线型和洛伦兹线型的卷积得到，可由下面的公式得到：

$$
V ( u , \sigma , \gamma ) { = } \int _ { - \infty } ^ { \infty } G ( u ^ { ' } , \sigma ) L ( u - u ^ { ' } , \gamma ) \mathrm { d } u
$$

其中， $u$ 为相对频率(实际频率-中心频率)， $\sigma$ 和 $\gamma$ 分别是高斯线型和洛伦兹线型的半高半宽(HWHM)，高斯线型和洛伦兹线型可分别由下式给出：

$$
G ( u , \sigma ) { = } \sqrt { \frac { \ln 2 } { \pi \sigma } } \exp ( - \frac { u ^ { 2 } \ln 2 } { \sigma ^ { 2 } } )
$$

$$
L ( u , \gamma ) { = } \frac { \gamma } { \pi ( { \gamma } ^ { 2 } + u ^ { 2 } ) }
$$

高斯线型、洛伦兹线型的半高半宽 $\sigma$ 和 $\gamma$ 可由下式给出：

$$
\sigma { = } \frac { \nu _ { \mathrm { 0 } } } { c } \sqrt { \frac { 2 \ln { 2 N _ { A } k T } } { M } }
$$

$$
\gamma \mathrm { { = } } P \cdot \gamma \mathcal { K } { \left( \frac { T _ { 0 } } { T } \right) } ^ { n _ { a i r } }
$$

其中， $N _ { _ A }$ 为阿伏加德罗常数， $M$ 为分子摩尔质量，$\gamma$ 是常温常压下的碰撞展宽的半高半宽， $n _ { a i r }$ 与温度相关的指数系数。HITRAN数据库提供了不同跃迁

的关于 $\gamma _ { a i r }$ 和 $n _ { a i r }$ 的相对准确的数据。本实验在常压下进行，因此吸收率主要取决于火焰温度和被测二氧化碳气体的浓度。

# 1.2 阿贝尔逆变换方法

图1是轴对称火焰某个高度的水平剖视图，根据比尔郎伯定律和阿贝尔积分方程，对于某一频率$\nu$ ，可以得到吸收率 $\alpha ( r , \nu )$ 的路径积分测量值$P ( x , \nu )$ 与其分布之间的关系：

$$
P ( x , \nu ) = - \ln ( \frac { I } { I _ { 0 } } ) _ { \nu , x } = 2 \int _ { x } ^ { R } \frac { \alpha ( r , \nu ) r d r } { \left( r ^ { 2 } - x ^ { 2 } \right) ^ { 1 / 2 } }
$$

$$
\nu _ { 1 } < \nu < \nu _ { 2 } , ~ - R < x < R
$$

式中 $\nu _ { \mathrm { { } _ { 1 } } }$ 和 $\nu _ { 2 }$ 分别是连续激光扫面频率的下限和上限。阿贝尔方程(10)具有解析解：

$$
\alpha ( r , \nu ) = - \frac { 1 } { \pi } \int _ { r } ^ { R } \frac { [ d P ( x , \nu ) / \mathrm { d } x ] } { ( x ^ { 2 } - r ^ { 2 } ) ^ { 1 / 2 } } \mathrm { d } x
$$

$$
\nu _ { 1 } < \nu < \nu _ { 2 } , ~ - R < r < R
$$

式中 $\mathrm { d } P ( x , \nu ) / d x$ 是测量路径积分值 $P ( x , \nu )$ 在 $x$ 轴方向上的导数。然而在实际测量中，通过有限差分方法获得 $P ( x , \nu )$ 的导数来计算 $\alpha ( r , \nu )$ 常常会放大实验值的误差，通过式(10)直接求解的方法不具有实用性[8,10,11]

![](images/c575920de8f6cfcb88f94b64530fe7758d8905bfceae5ed5e3db7e8a31fb3448.jpg)  
图1轴对称扩散火焰激光测量 Fig.1Laser measurement of axisymmetric coflow Flame

许多替代的阿贝尔算法相继被提出。OP方法将火焰水平剖面划分为 $N$ 个宽度相等的圆环，并假设在每个圆环内火焰参数相等，将阿贝尔逆变换问题转化为求解线性方程组

式中： $\underline { { \alpha } } = \left\{ \alpha _ { 0 } , \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { { N - 1 } } \right\}$ 表示从圆心向外，各个圆环内的吸收率的值， $\underline { { P } } = \left\{ P _ { 0 } , P _ { 1 } , P _ { 2 } , . . . , P _ { N - 1 } \right\}$ 表示距离圆心不同的距离的路径积分信号， $A _ { O P }$ 是尺寸为$N \times N$ 的几何关系矩阵。ATP方法转化精度更高，其考虑相邻路径的偏导[8]，并将阿贝尔逆变换转化为求解类似的线性方程组[8]

$$
A _ { _ { A T P } } \underline { { \alpha } } = \underline { { P } }
$$

# 1.2.1 病态矩阵问题

由于OP和ATP方法所构造矩阵的病态特性，实验测量的路径积分信号的微小噪声会导致求解值与真实值偏差较大。在求解方程 $A \underline { { \alpha } } = \underline { { P } }$ 时，若将矩阵 $A$ 进行奇异值分解[9]，可以得到

$$
\boldsymbol { A } = \boldsymbol { U \Sigma V } ^ { T } = \sum _ { i = 1 } ^ { N } { u _ { i } \sigma _ { i } \nu _ { i } ^ { T } }
$$

式中： $\pmb { U }$ 和 $V$ 分别包含 $N$ 个正交列向量 $u _ { i }$ 和 $\nu _ { i } , \Sigma$ 是包含矩阵 $A$ 的奇异值 $\sigma _ { i }$ 的对角矩阵。由于矩阵 $\textbf {  { U } }$ 和 $V$ 的正交性，方程的解可以写成

$$
\alpha = \sum _ { i = 1 } ^ { N } \frac { u _ { i } ^ { T } p } { \sigma _ { i } } \nu _ { i } = \sum _ { i = 1 } ^ { N } ( \frac { u _ { i } ^ { T } p _ { 0 } } { \sigma _ { i } } \nu _ { i } + \frac { u _ { i } ^ { T } \delta p } { \sigma _ { i } } \nu _ { i } )
$$

式中： $p$ 是由实验测量获得的路径积分吸收信号，$p _ { \mathrm { 0 } }$ 是没有实验误差时理想的路径积分吸收信号，$\delta p = p - p _ { 0 }$ 是实验测量结果的误差。从(14)式可以看出，矩阵 $A$ 的小奇异值会放大实验误差的影响，从而降低阿贝尔转化的精确度。

# 1.2.2 Tikhonov正则化方法

对于稳定的火焰，其温度场和气体浓度分布应当是连续平滑的。一种有效的正则化方法是对上述矩阵方程添加约束项，即添加平滑约束条件，使用修正的方程进行阿贝尔逆变换求解[7,10.11]。因此，可将原来的矩阵方程 $A \underline { { \alpha } } = \underline { { P } }$ 修正成以下形式：

$$
{ \left[ \begin{array} { l } { A } \\ { \lambda L } \end{array} \right] } { \underline { { \alpha } } } = { \overline { { \left[ { \underline { { P } } } \right] } } }
$$

式中： $\pmb { L }$ 是用于约束平滑条件的拉普拉斯矩阵， $\lambda$ 是控制正则化程度的正则化系数。矩阵 $\pmb { L }$ 的形式如下：

$$
L = { \left[ \begin{array} { l l l l l } { 1 } & { - 1 } & { 0 } & { \cdots } & { 0 } \\ { 0 } & { 1 } & { - 1 } & & { \vdots } \\ { \vdots } & & { \ddots } & { \ddots } & { 0 } \\ { 0 } & { \cdots } & { 0 } & { 1 } & { - 1 } \end{array} \right] } _ { k \times n }
$$

矩阵 $\pmb { L }$ 用于使 $\underline { { \boldsymbol { \alpha } } }$ 中的相邻项平滑过渡，矩阵 $\pmb { L }$ 的行数 $k$ 可根据不同阿贝尔转化的对象以及阿贝尔转化矩阵的不同而做调整， $k { = } 1 , 2 { \ldots } N { - } 1$ 。对于OP方法， $k { = } 1$ (对方程加约束项 $\lambda ( \alpha _ { 0 } - \alpha _ { 1 } ) { = } 0$ 时即可以达到较好的转化效果；而对于ATP方法， $k$ 的选择对正则化效果的影响较小。下文中模拟中，对OP方法，取 $k { = } 1$ ，对ATP方法，取 $k { = } N { - } 1$ 。

由于方程(15)是超定方程，可通过最小二乘法求最优解，即求解下列方程：

$$
\left[ \boldsymbol { A } ^ { T } \quad \lambda \boldsymbol { L } ^ { T } \right] \left[ \begin{array} { l } { \boldsymbol { A } } \\ { \lambda \boldsymbol { L } } \end{array} \right] \boldsymbol { \underline { { \alpha } } } = \left[ \boldsymbol { A } ^ { T } \quad \lambda \boldsymbol { L } ^ { T } \right] \left[ \boldsymbol { \underline { { P } } } \right]
$$

简化成

$$
\begin{array} { r l } { \bigg [ \boldsymbol { A } ^ { T } \boldsymbol { A } + } & { { } \boldsymbol { \lambda } ^ { 2 } \boldsymbol { L } ^ { T } \boldsymbol { L } \bigg ] \boldsymbol { \underline { { \alpha } } } = \boldsymbol { A } ^ { T } \underline { { P } } } \end{array}
$$

![](images/d0fde33d043e885a320db449b36bd769c534f77ab36a9d5a26e8b48fec92194c.jpg)  
图2用于确定正则化系数的L-Curve

采用正则化的阿贝尔转换方法时，正则化系数λ的选择十分关键： $\lambda$ 过小，正则化效果不明显；而λ过大时，尽管结果曲线光滑，但准确性无法保证。L-curve方法被证实是比较简单有效的确定正则化参数的方法[9-11]。图2表示了L-curve 方法的基本原理，对于不同的 $\lambda$ 的值，绘出对应不同求解值 $x _ { \lambda }$ 的横坐标为 $\mathbb { I o g } _ { \mathbb { E } ^ { 2 } \bot \widehat { \mathbf { g } } } \mathbb { i } \mathbb { I } \mathbb { A } \mathbb { x } _ { \widehat { \mathbf { a } } } - \mathbb { i } \mathbb { \| } _ { \widehat { \mathbf { z } } } )$ 纵坐标为 $\mathbb { E } \mathbb { g } _ { \Xi = \Xi } ( \| \underline { { L } } \mathcal { X } _ { \Xi } \| _ { \Xi } )$ 的各点连成的曲线。其中 $| | \underline { { \bar { \mathbf { \jmath } } } } _ { i \cdot \vec { \mathbf { \jmath } } _ { i } } | | _ { \mathfrak { z } }$ 和 $\| \mathbb { A } \mathbb { x } _ { : } - \mathbb { b } \| _ { : }$ 分别是$\underline { { L } } x _ { 3 }$ 和 $A E = B$ 的二范数。对于某一，如果 $\| \mathbf { \underline { { I } } } ( \mathbf { \boldsymbol { \mathcal { X } } } = \| \mathbf { \boldsymbol { \rho } } _ { \tilde { \mathbf { a } } }$ 过大，则该逆变换仍然对测量噪声较为敏感，如果$\| \dot { A } \boldsymbol { x } _ { \widehat { \lambda } } - \dot { b } \| _ { 2 }$ 过大，则逆变换的结果精度较低。如图2所示,L-curve 出现最大曲率时， $\| \tilde { \underline { { \operatorname { L x } } } } _ { \widehat { \lambda } _ { \widehat { \lambda } _ { \widehat { \lambda } } } } \| _ { \widehat { \underline { { s } } } } .$ 和 $\| . \dot { \mathsf { A } } \boldsymbol { \mathscr { X } } _ { \widehat { \mathsf { a } } } - \boldsymbol { \mathscr { b } } \| _ { \widehat { \mathsf { a } } }$ 都较小，是较为理想的正则化系数。

在本实验中，需要对coflow火焰的多个高度处的测量数据进行阿贝尔转化，正则化系数的自动化选择可以简化数据处理过程。通过有限差分求导可以计算曲线曲率，找到曲率的最大值对应的正则化系数，从而实现正则化阿贝尔逆变换的自动化运算：

$$
\begin{array} { r } { k _ { \lambda } = \frac { \rho _ { \lambda } ^ { \mathrm { ' } } \eta _ { \lambda } ^ { \mathrm { " } } - \rho _ { \lambda } ^ { \mathrm { ' } } \eta _ { \lambda } ^ { \mathrm { ' } } } { \left[ \left( \rho _ { \lambda } ^ { \mathrm { ' } } \right) ^ { 2 } + \left( \eta _ { \lambda } ^ { \mathrm { ' } } \right) ^ { 2 } \right] ^ { 3 / 2 } } } \end{array}
$$

式中 $\gamma _ { i } a _ { i } = \log _ { i \in \mathbb { Z } } ( \lVert \lVert A x _ { i } - b \rVert _ { z } )$ ， $\eta _ { 2 } = \log _ { 2 , 0 } ( \| L \kappa _ { 2 } \| _ { 2 } )$

# 1.2.3 数值模拟验证

在coflow火焰的较低位置处，径向吸收率主要呈双峰分布，而在火焰的较高位置处，径向吸收率主要呈单峰分布。为了便于进行模拟计算，我们构造了如下图3所示的两种分布：

$$
\begin{array} { l } { \displaystyle f _ { 1 } ( \boldsymbol { r } ) = \frac { 1 } { 1 0 } \big ( 1 - r ^ { 2 } \big ) ^ { 2 } } \\ { \displaystyle f _ { 2 } ( \boldsymbol { r } ) = \frac { 1 } { 1 0 } \big ( 1 + 4 r ^ { 2 } - 5 r ^ { 4 } \big ) } \end{array}
$$

![](images/93d91fd0006f500657a567f78acc9c0dbec9314dd21700addc41579fb9d6b7a8.jpg)  
Fig.2L-Curve method for selecting regularization parameter

式中， $f _ { 1 } ( r )$ 和 $f _ { 2 } ( r )$ 分别为假设的沿火焰水平径向分布的单峰和双峰分布函数，其中分布半径 $r$ 作了归一化处理。根据式(9)使用分部积分方法可以计算出阿贝尔路径积分函数：

$$
P _ { 1 } ( x ) = \frac { 8 } { 7 5 } \big ( 1 - x ^ { 2 } \big ) ^ { 5 / 2 }
$$

$$
P _ { 2 } ( x ) = \frac { 4 } { 5 } \big ( 1 - x ^ { 2 } \big ) ^ { 3 / 2 } - \frac { 8 } { 1 5 } \big ( 1 - x ^ { 2 } \big ) ^ { 5 / 2 }
$$

式中， $P _ { 1 } ( x )$ 和 $P _ { 2 } ( x )$ 分别是单峰和双峰分布在距离火焰中心 $x$ 位置处的阿贝尔路径积分值。本实验中，考虑对20条等间距的路径积分值进行逆变换求解。当不考虑路径积分值的实验误差时，即使是最简单的OP方法也能获得较为精确的转化结果,如下图3所示。

模拟实验对积分值加幅值为 $2 \%$ 随机噪声，再对加噪声的积分值分别使用OP、ATP、正则化的OP（下文中称Tik-OP)和正则化的ATP方法(下文中称Tik-ATP)进行逆变换求解并与原始分布式比较，验证不同逆变换方法的求解精度，典型的转化结果如下图4所示。

![](images/8c0e6419a714248de1764f5c834df84828c1483e8306be17fd50964ead7dd32c.jpg)  
图3不考虑噪声时候的Abel转化Fig.3Abel inversion without noise  
图4考虑噪声时的阿贝尔转化结果 Fig.4 Abel inversion with noise

为了定量分析误差，重复进行了100次含噪声数值实验，利用100次平均的均方根误差来比较不同方法在有噪声情况下的转化精度：

$$
E _ { r m s } = \frac { | | \ f _ { i n \nu } - f _ { e x a c t } \ | | _ { 2 } } { \sqrt { N } * \operatorname* { m a x } ( f _ { e x a c t } ) }
$$

$$
\overline { { E _ { r m s } } } = \frac { 1 } { 1 0 0 } \Sigma _ { i = 1 } ^ { 1 0 0 } ( E _ { r m s } ) _ { i }
$$

式中， $E _ { r m s }$ 为均方根误差， $N$ 为 $f _ { i n \nu } / f _ { e x a c t }$ 中的项数,这里取 $N = 2 0 \ , \ f _ { e x a c t }$ 为径向分布的原始设定值， $f _ { i n \nu }$ 为阿贝尔逆变换的求解值， $\overline { { E _ { r m s } } }$ 为100 次模拟求解的均方根误差的平均值，结果如下表1所示。

表1均方根误差平均值比较  
Table1 Comparison ofMean Square Error   

<html><body><table><tr><td>AbelMethods</td><td>Single Peak</td><td>Double Peak</td></tr><tr><td>OP</td><td>0.08738</td><td>0.04345</td></tr><tr><td>ATP</td><td>0.03030</td><td>0.02187</td></tr><tr><td>Tik-OP</td><td>0.00491</td><td>0.01527</td></tr><tr><td>Tik-ATP</td><td>0.00520</td><td>0.01877</td></tr></table></body></html>

从表1可以看出，各种方法按照求解精度排序依次为：Tik-OP>Tik-ATP $\mathrm { > }$ ATP>OP。对于尺寸为$2 0 \times 2 0$ 的OP矩阵，本文采用的正则化方法可以有效提高转换精度，而对于ATP矩阵，正则化方法对精度的提高有限。

基于上述模拟结果，在处理整个扩散火焰的实验数据时候，可采用Tik-OP方法进行阿贝尔逆变换。

# 2 实验测量

图5是实验装置的示意图。本实验选用波长在4.17微米附近的ICL激光器，通过函数发生器产生的正弦波扫描波数范围在 $2 3 9 6 . 9 \mathrm { c m } ^ { - 1 }$ 至 $2 3 9 7 . 4 ~ \mathrm { c m } ^ { - 1 }$ 之间的中红外激光波长。激光器产生的激光通过两个分束镜分成三路光，即分别由三个探测器测量信号的标准具波长校准光路、参考光路和coflow火焰测量光路。为了防止激光经过高温火焰区域发生偏折而无法全部被探测器接收，在探测器前设置聚焦镜。

实验中，步进电机控制燃烧炉在水平方向和竖直方向上移动，其中水平方向测量火焰中心轴线到火焰外缘直至没有吸收信号的位置，移动间距为0.05cm，竖直方向从火焰底部到可见火焰尖部以上位置，移动间距 $0 . 1 \ \mathrm { c m }$ 。探测器2测得的参考光路的信号用作背景信号 $I _ { 0 }$ ，由于参考光路和经过火焰的光路初始激光强度不同，基线 $I _ { 0 }$ 通过除以距离火焰较远位置处的两路信号的峰峰值的比值进行校正。经过标准具的激光信号具有相邻的峰间隔相同波数的性质，结合HITRAN数据库中已知的基本固定的吸收峰波数，可标定在每个扫描周期内的激光波长信息。图6示出了火焰中某个测量位置的半个正弦扫描周期内的原始数据，其中背景信号经过如上所述的校正。图6中可以看出在火焰温度下，二氧化碳对4.17微米的中红外激光的吸收较强。

![](images/44f79ff587eb760d99903caa1fd192d4cf1c2d25e9cf6848b08a5516da3eae51.jpg)  
图5实验装置示意图

![](images/0d7a8de12b35ba1bd039782b65e2fb3e7664075c10e5cb13007eedda7aec4b54.jpg)  
Fig.5 Schematic view of the experimental apparatus   
图6实验测量的信号 Fig.6 Signals obtained in experiment

![](images/8deea4d4a841046548df02cc764e7896a93c9cadb20a01df858f34ba6a210f3b.jpg)  
图7实验值的阿贝尔转化 Fig.7Abel inversion of experimental data

为比较上述重构方法对单峰和双峰分布的实验测量值进行转换的准确性，分别对实验得到的火焰高度 $\mathrm { Y = 5 0 ~ m m }$ 和 $\scriptstyle \ Y = 2 0 \ m =$ 位置处的吸收信号路径积分值 $P ( x ) = - \mathrm { l n } ( I / I _ { 0 } ) _ { x }$ 使用前述阿贝尔转化方法进行逆变换求解并进行比较，结果如下图7所示。

参考模拟验证部分的结论并结合图7所示的结果，可以判断正则化的OP方法可以获得较为光滑准确的结果。因此对火焰的每一测量高度、各个激光波数得到的水平方向路径积分值采用Tik-OP方法进行阿贝尔逆变换求解，从而得到火焰各个高度的径向吸收率分布，并使用最小二乘法将转化后的吸收率与HITRAN数据库中的数据进行拟合，从而得到火焰的温度分布。

实验中选取与文献[2]中实验相似的工况，混合燃料气体中乙烯占 $60 \%$ 、氮气占 $40 \%$ ，燃料出口流速为 $5 \mathrm { c m / s }$ 。图8-10 对本实验的结果与文献[2] 中公布的结果进行了比较,其中火焰外围较远处的部分点被忽略。

![](images/5c6a2d6dadd8e70ed80f6fa5258a3db452dd0cbb36d510c7328881f5a0058a2f.jpg)  
图8火焰竖直剖面的二维温度分布

![](images/d86522df6f14119e0fbda5992155c519ab712ff89657e39766a66e3bbf764ecc.jpg)  
Fig.8 Temperature distribution of vertical central section of flame   
图9火焰不同高度处的径向温度分布  
Fig.9 Radial distribution of flame temperature at several heights

从图8-10可以看出，本实验测得的火焰温度与文献[2公布的结果较为相似；火焰高度 $: > 3 0 \mathrm { m m }$ 时，本实验获得的乙烯火焰温度分布与文献[2]中结果基本一致，且本实验的温度分布较为平滑。 $\mathrm { Y } { = } 2 5 ~ \mathrm { m m }$ 时，本实验的温度与文献[2中结果相差 $1 0 0 \mathrm { K }$ 左右，但是径向温度变化趋势较为相似。本实验和文献[2]中的实验并不能保证完全相同的实验工况，例如燃烧炉的尺寸、压缩空气的流速等存在差异，可能是产生不同测量结果的原因。

# 3结论

本研究使用TDLAS技术并结合阿贝尔转化方法重建了乙烯轴对称扩散火焰的温度场。为提高数据处理的精度，采用了Tikhonov正则化方法对阿贝尔转化矩阵(OP和ATP矩阵)进行约束，并进行了数值模拟比较。此外，为了验证实验测量与数据分析的可靠性，对与文献[2]中实验相似的工况进行了实验，并与文献中结果进行了比较。

1)Tikhonov正则化方法应用于本实验中尺寸为20的OP矩阵时，能够有效减少路径积分噪声对转化结果的影响，显著提高阿贝尔逆变换的精度;

2)测得的乙烯同轴扩散火焰的最高温度为约1850K。本实验获得火焰温度分布与与文献[2]中的结果较为一致。

![](images/f52a5d6a6adfa986990fe6a2719c4f5eddfc343b17ffe0acb9790da2da74a816.jpg)  
图10火焰中心竖直轴线的温度分布 Fig.10 Flame temperature profile along central vertical axis

# 参考文献

[1] JIN Hanfeng, WANG Yizun, ZHANG Kuiwen, et al.An experimental study on the formation of polycyclic aromatic hydrocarbons in laminar coflow non-premixed methane/air flames doped with four isomeric butanols [J].Proceedings of the Combustion Institute,2013,34: 779-786   
[2] SUN Zhiwei, Dally B,Nathan G, et al. Effects of hydrogenandnitrogenonsootvolume fraction,primary particle diameter and temperature inlaminarethlene/airdiffusion flames[J]. Combustion and Flame,2016,175:270-282   
[3] 金汉锋．丁醇掺混的甲烷同轴扩散火焰的实验 和动力学研究[D]．合肥：中国科学技术大学， 2015 JIN Hanfeng. Experimental and kinetic modeli ng of methane co-flow diffusion flames doped with butanol isomers [D].Hefei:University of Science and Technologyof China, 2015 Hanson R K,Kuntz P A,Kruger C H,et al. High-resolution spectroscopy of combustion gases using a tunable ir diode laser [J]. Applied Optics, 1977,16(8): 2405-2489   
[5] Girard JJ, Spearrin R M, Goldenstein C S, et al. Compact optical probe for flame temperature and carbon dioxide using interband cascade laser absorption near $4 . 2 ~ \mu \mathrm { m }$ [J].Combustion and Flame,2017,178:158-167   
[6] Villarreal R，Varghese $\mathrm { ~ P ~ L ~ }$ . Frequency-resolved absorption tomography with tunable diode lasers [J]. Applied Optics,2005,44(31): 6786-6795.   
[7] CAI Weiwei， Kaminski C F. Tomographic absorption spectroscopy for the study of gas dynamics and reactive flows [J].Progressin Energy and Combustion Science,2016,59:1-31   
[8] Dasch C J. One-dimensional tomography:a comparison of Abel,onion-peeling,and filtered back projection methods [J].Applied Optics,1992. 31(8): 1146-1152   
[9] LIU Chang，XU Lijun, CAO Zhang，et al. Reconstruction of Axisymmetric Temperature and GasConcentrationDistributions by Combining Fan-Beam TDLAS With Onion-Peeling Deconvolution [J]. IEEE Transactions on Instrumentation and Measurement, 2014,63(12): 3067-3075   
[10] Daun K J,Thomson K A,LIU Fengshan,et al. Deconvolution of axisymmetric flame properties using Tikhonov regularization [J]. Applied Optics, 2006, 45(19): 4638-4646   
[11] Akesson E O,Daun K J.Parameter selection methods for axisymmetric flame tomography through Tikhonov regularization [J]. Applied Optics,2008,47(3):407-416   
[12] Rothman L S,GordonIE,Babikov Y,et al. The HITRAN2012 molecular spectroscopic database [J]. Journalof Quantitative Spectroscopyand Radiative Transfer,13O:4-50