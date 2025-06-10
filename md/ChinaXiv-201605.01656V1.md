# AUSM系列算法对比研究及背景太阳风初步应用

王涛李会超 张曼 付华峰(中国科学院国家空间科学中心空间天气学国家重点实验室北京 100190)

（中国科学院大学 北京 100049)

摘要磁流体力学数值模拟是研究日地物理学现象的一个重要手段.对比三种AUSM算法,即 AUSM, $\mathrm { A U S M + }$ 和 AUSMPW+,结合 HDC 磁场散度消去方法计算多维 MHD 问题的性能．通过分析三种算法计算 Rotor 算例和Orszag-Tangvortex 算例的结果发现, ${ \mathrm { A U S M } } +$ 算法的性能最好.进一步使用 $\mathrm { \ A U S M + }$ 算法基于6片网格构造模拟了日冕结构，计算结果表明这种算法能够正确计算出日冕的大尺度结构．对于日冕结构模拟块，HDC 方法能够较好地控制磁场散度误差.

关键词 AUSM系列算法,HDC 方法，日冕模拟中图分类号P353

# Comparative Study of Three AUSM Algorithms and Simulated Application on the Solar Wind

WANG Tao LI Huichao ZHANG Man FU Huazheng (StateKey Laboratory of Space Weather National Space Science Center, Chinese Academy of Sciences,Beijing 100190) (University of ChineseAcademyof Sciences,Beijing 100049)

Abstract Numerical simulation of MHD (Magnetohydrodynamics） is an important method to study solar-terrestrial physics phenomena. In this paper, three AUSM algorithms, i.e., AUSM, AUSM $+$ ，AUSMPW $^ +$ ,were compared in conjunction with the HDC method to eliminate the divergence of the magnetic field. The AUSM $^ +$ algorithm is found to be better than the AUSM algorithm and the AUSMPW $^ +$ algorithm through the results of Rotor example and Orszag-Tang vortex example. Further, the AUSM $^ +$ algorithm is used to simulate the coronal with a six-component grid system. The results show that this algorithm can correctly calculate the large-scale structure of the corona. Also,the HDC method can maintain the divergence-free constraint on the magnetic field.

Key wordsAUSM algorithms,HDC method, Simulation of corona

# 0 引言

日地空间物理学研究涵盖了日冕、行星际、磁层、电离层等物理性质不同的空间区域，磁流体力学（MHD）数值模拟是研究日地物理学现象的一个重要手段,被广泛应用于日冕磁场结构[1-2]、背景太阳风结构[3]、日冕物质抛射（CME）事件[4]、太阳风-磁层相互作用等研究[5.随着基于磁流体力学数值模拟的空间天气预报方法投入运行[]，空间天气预报由经验预报向数值预报发展.

在MHD 数值模拟过程中，一般需进行特别处理以使磁场散度误差！ $\begin{array} { r } { \nabla \cdot \boldsymbol { B } = 0 , } \end{array}$ ）保持为零[7．目前主要的磁场散度误差处理方法有4种.(1)泊松校正法[8]，通过求解泊松方程计算磁场中与散度误差相关的部分，并将其从磁场计算结果中消去；（2）CT(ConstrainedTransport）方法[9l,通过求解电场旋度形式的磁感应方程，使磁场散度误差不随计算增加;(3)Powell的8 波模型[10],在守恒形式的MHD方程组右端添加正比于 $\nabla \cdot B$ 的源项,使得磁场散度误差可以随着流体运动被输运出去，避免散度误差累积;(4）Dedner 的 HDC(Hyperbolic Divergence Clean-ing）方法[11],通过在 MHD 方程组中添加一个耦合磁感应方程和 $\nabla \cdot B = 0$ 的方程,使得 MHD方程组变为9个方程，在不破坏MHD方程守恒性及不增加额外计算步骤的情况下消除磁场散度误差

在日地空间物理学的MHD 模拟研究中大都采用有限体积类数值方法．求解有限体积方法控制体界面通量时，迎风格式根据方程组特征波的传播方向计算通量，能够正确反映物理信息的传播方向，获得较好的间断捕捉效果．迎风格式可以分为FDS(Flux Difference Splitting)[12] 和 FVS (Flux VectorSplitting)[13] 两类．FDS 通过界面上近似黎曼问题的解得到界面上的通量，最典型的FDS类格式是Roe 格式；FVS格式则直接在界面上分裂通量的Jacobi矩阵得到包含迎风信息的数值通量，典型的FVS 类格式有Van Leer[13] 和 Steger-Warming[14]格式．为了集合 FDS 离散格式的高精度与 FVS离散格式的稳定性[16]，构造了混合通量分裂格式，具有代表性的有 AUSM（Advection Upstream S-plit Mach number)[17], LDFSS (Low-diffusion Flux-splitting Scheme)[18] 和 CUSP(Convection UpstreamSplit Pressure)[19] 等.

AUSM算法是迎风格式的一种，在可压缩流体力学（HD）数值模拟中取得了较好的效果．AUSM算法的核心思想是把方程组的流通量分为流动项和压力项，然后根据网格界面的马赫数计算流通量这种算法不需要计算通量Jacobi 矩阵的特征值和特征向量，方便易行．作为从计算流体引进的算法，1999年Agarwal和 Augustinus[20] 首先利用原始的ASUM算法计算一维Brio-Wu 激波管问题，虽然得到成功应用但是在强激波处会出现数值振荡．为了提高AUSM算法的稳定性，2007 年 Pan[21]在非结构网格下使用 $\mathrm { A U S M + }$ 算法计算了一维的Brio-Wu 激波管和二维nozzle 流动问题，取得较好的效果．为使AUSM系列算法更有效地捕获间断，2009年Han[22]将气体动力学改进的 $\mathrm { A U S M P W + }$ 算法引入磁流体力学求解激波问题，捕获能力增强，

本文介绍了AUSM,AUSM $+$ 和AUSMPW $+$ 三种AUSM数值格式构造和控制磁场散度误差的HDC方法，为了对比这三种算法在计算多维MHD问题时的性能,计算了二维Rotor 和Orszag-Tangvortex 两个标准算例，并使用计算效果最好的 $\mathrm { A U S M + }$ 算法计算了日冕结构，

# 1数值算法

# 1.1 控制方程

采取无量纲化变量．控制方程采用的是如下守恒形式的单流体理想MHD方程:

$$
\begin{array} { r l r } & { \frac { \partial \rho } { \partial t } + \nabla \cdot ( \rho v ) = 0 , } & { \mathrm { ( I ) } } \\ & { \frac { \partial \rho v } { \partial t } + \nabla \cdot \left[ \rho v \cdot v + \left( p + \frac { 1 } { 2 \mu _ { 0 } } B ^ { 2 } \right) I - \frac { 1 } { \mu _ { 0 } } B \cdot B \right] = 0 , } & \\ & { \frac { \partial E } { \partial t } + \nabla \cdot \left[ \left( E + p + \frac { 1 } { 2 \mu _ { 0 } } B ^ { 2 } \right) v - \right. } & \\ & { \left. \frac { 1 } { \mu _ { 0 } } ( v \cdot B ) B \right] = 0 , } & { \mathrm { ( 3 ) } } \\ & { \frac { \partial B } { \partial t } + \nabla \cdot \left( v \cdot B - B \cdot v \right) = 0 . } & { \mathrm { ( 4 ) } } \end{array}
$$

同时，磁场遵循高斯磁定律:

$$
\begin{array} { r } { \nabla \cdot \boldsymbol B = 0 . } \end{array}
$$

其中， $\rho$ 为密度, $\boldsymbol { v }$ 为速度, $p$ 为气体压强， $B$ 为磁感应强度， $\mu _ { 0 }$ 为真空磁导率, $\gamma$ 为气体比热比， $I$ 为单

位张量， $E$ 为能量,有

$$
E = \frac { p } { \gamma - 1 } + \frac { 1 } { 2 } \rho v ^ { 2 } + \frac { 1 } { 2 \mu _ { 0 } } B ^ { 2 } .
$$

# 1.2 AUSM系列算法

理想MHD方程的守恒形式可以写为

$$
\frac { \partial U } { \partial t } + \frac { \partial F } { \partial x } + \frac { \partial G } { \partial y } + \frac { \partial H } { \partial z } = 0 .
$$

式中， $\boldsymbol { \mathbf { \mathit { U } } }$ 为流动量， $F$ 为 $\mathbf { \Psi } _ { x }$ 方向流通量， $G$ 为 $y$ 方向流通量， $H$ 为 $z$ 方向流通量，

$$
U = \left[ \begin{array} { c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c } { \rho } & & & & & & & & & & & & & & & & & & & \\ & & & & & & & & & & & & & & & & & \\ & & & & & & & & & & & & & & & & & \\ & & & & & & & & & & & & & & & & & \\ { B _ { x } } & & & & & & & & & & & & & & \\ { B _ { y } } & & & & & & & & & & & & & \\ & & & & & & & & & & & & & & \\ & & & & & & & & & & & & & & \end{array} \right] .
$$

其中,

$$
\begin{array} { r } { \boldsymbol { \psi } = \left[ \begin{array} { c } { \rho } \\ { \rho } \\ { \rho \boldsymbol { u } } \\ { \rho \boldsymbol { v } } \\ { \rho \boldsymbol { w } } \\ { B _ { x } } \\ { B _ { y } } \\ { B _ { z } } \\ { E + p _ { \mathrm { t } } } \end{array} \right] , \quad \boldsymbol { P } = \left[ \begin{array} { c } { 0 } \\ { 0 } \\ { p _ { \mathrm { t } } - B _ { x } ^ { 2 } } \\ { - B _ { x } B _ { y } } \\ { - B _ { x } B _ { z } } \\ { - B _ { x } B _ { x } } \\ { - \boldsymbol { u } B _ { x } } \\ { - \boldsymbol { v } B _ { x } } \\ { - \boldsymbol { w } B _ { x } } \\ { - \boldsymbol { w } B _ { x } } \\ { E + p _ { \mathrm { t } } } \end{array} \right] , } \end{array}
$$

$$
\boldsymbol F = \left[ \begin{array} { c } { \rho u } \\ { \rho u ^ { 2 } + p _ { \mathrm { t } } - B _ { x } ^ { 2 } } \\ { \rho u ^ { \prime } - B _ { x } B _ { y } } \\ { \rho u v - B _ { x } B _ { z } } \\ { u B _ { x } - u B _ { x } } \\ { u B _ { y } - v B _ { x } } \\ { u B _ { z } - w B _ { x } } \\ { u B _ { z } - w B _ { x } } \\ { u B _ { x } - w B _ { x } } \\ { ( E + p _ { \mathrm { t } } ) u - B _ { x } ( u B _ { x } + v B _ { y } + w B _ { z } ) } \end{array} \right]
$$

半离散化的守恒型三维磁流体方程的形式为

$$
\begin{array} { r l } & { \displaystyle \frac { \partial U } { \partial t } + \frac { F _ { i + 1 / 2 , j , k } - F _ { i - 1 / 2 , j , k } } { \delta x } + } \\ & { \quad \quad \quad \quad \frac { G _ { i , j + 1 / 2 , k } - G _ { i , j - 1 / 2 , k } } { \delta y } + } \\ & { \quad \quad \quad \quad \quad \frac { H _ { i , j , k + 1 / 2 } - H _ { i , j , k - 1 / 2 } } { \delta z } = 0 . } \end{array}
$$

式中， $F _ { i + 1 / 2 , j , k }$ ， $F _ { i - 1 / 2 , j , k }$ ， $G _ { i , j + 1 / 2 , k }$ ， $G _ { i , j - 1 / 2 , k }$ ${ { H } _ { i , j , k + 1 / 2 } }$ ， $H _ { i , j , k - 1 / 2 }$ 为控制体界面上的数值通量.

在计算数值通量时，AUSM将通量分解为流动项 $F ^ { \mathrm { C } }$ 和压力项 $F ^ { \mathrm { P } }$ .以 $\mathbf { \Psi } _ { x }$ 方向上的通量 $F$ 为例,

$$
F = F ^ { \mathrm { C } } + F ^ { \mathrm { P } } = u \psi + P .
$$

$$
p _ { \mathrm { t } } = p + \frac { 1 } { 2 } ( B _ { x } ^ { 2 } + B _ { y } ^ { 2 } + B _ { z } ^ { 2 } ) .
$$

在 AUSM系列算法中，不同算法对界面上的通量采用的计算方法有所区别，下面分别予以介绍

# 1.2.1 AUSM算法

$$
\begin{array} { r } { F _ { 1 / 2 , \mathrm { A U S M } } = c _ { \mathrm { f } } ( M _ { L } ^ { + } \psi _ { L } + M _ { R } ^ { - } \psi _ { R } ) + } \\ { ( p _ { L } ^ { + } P _ { L } + p _ { R } ^ { - } P _ { R } ) . \qquad } \end{array}
$$

式中， $1 / 2$ 为网格界面处流通量， $( L , R )$ 为界面处重构的控制体变量，

$$
\begin{array} { l } { { \displaystyle M _ { L , R } = \frac { U _ { L , R } } { c _ { \mathrm { f } } } ; } } \\ { { \displaystyle M ^ { \pm } = \left\{ \begin{array} { l l } { { \pm \frac { 1 } { 4 } ( M \pm 1 ) ^ { 2 } , } } & { { | M | \leqslant 1 , } } \\ { { \frac { 1 } { 2 } ( M \pm | M | ) , } } & { { | M | > 1 ; } } \end{array} \right. } } \\ { { \displaystyle P ^ { \pm } = \left\{ \begin{array} { l l } { { \displaystyle \frac { 1 } { 4 } ( M \pm 1 ) ^ { 2 } ( 2 m M ) , } } & { { | M | \leqslant 1 , } } \\ { { \displaystyle \frac { 1 } { 2 } [ 1 \pm \mathrm { s g n } ( M ) ] , } } & { { | M | > 1 ; } } \end{array} \right. } } \end{array}
$$

$$
\begin{array}{c} \begin{array} { r l } & { c _ { \mathrm { f } } = \operatorname* { m i n } ( c _ { \mathrm { f } , L } , c _ { \mathrm { f } , R } ) ; } \\ & { c _ { \mathrm { f } , L } = \left\{ \frac { 1 } { 2 } \bigg [ \frac { \gamma p _ { L } + { B _ { L } } \cdot { B _ { L } } } { \rho _ { L } } + \right.} \end{array}   \end{array}
$$

$$
\sqrt { \left( \frac { \gamma p _ { L } + B _ { L } \cdot B _ { L } } { \rho _ { L } } \right) ^ { 2 } - 4 \frac { \gamma p _ { L } B _ { \mathrm { n } , L } ^ { 2 } } { \rho _ { L } ^ { 2 } } } \Biggr ] \Biggr \} ^ { \frac { 1 } { 2 } } ;
$$

$$
\begin{array}{c} \begin{array} { r l r } { \left. { c _ { \mathrm { f } , R } = \left\{ \frac { 1 } { 2 } \biggl [ \frac { \gamma p _ { R } + { \bf B } _ { R } \cdot { \bf B } _ { R } } { \rho _ { L } } + \right.} \\ & { } \end{array}  }  \\ & { } & { \sqrt { \left( \frac { \gamma p _ { R } + { \bf B } _ { R } \cdot { \bf B } _ { R } } { \rho _ { R } } \right) ^ { 2 } - 4 \frac { \gamma p _ { R } B _ { \mathbf { n } , R } ^ { 2 } } { \rho _ { R } ^ { 2 } } } \biggr ] \right\} ^ { \frac { 1 } { 2 } } ; }  \end{array}
$$

$B _ { \mathrm { n } } = S _ { \mathrm { f } } B$ 为法向磁场

# 1.2.2 $\mathbf { A U S M + }$ 算法

$\mathrm { \ A U S M + \ }$ 算法与 AUSM 算法的区别在于构造$M ^ { \pm }$ ， $P ^ { \pm }$ 时引入了 $\alpha$ 和 $\beta$ 项，此时界面的流通量为

$$
\begin{array} { r l } { F _ { 1 / 2 , \mathrm { A U S M } + } = c _ { \mathrm { f } } ( M _ { L } ^ { + } | _ { \beta = 1 / 8 } \psi _ { L } + M _ { R } ^ { - } | _ { \beta = 1 / 8 } \psi _ { R } ) + } & { } \\ { ( P _ { L } ^ { + } | _ { \alpha = 3 / 1 6 } P _ { L } + P _ { R } ^ { - } | _ { \alpha = 3 / 1 6 } P _ { R } ) . } & { } \end{array}
$$

$M ^ { \pm }$ 和 $P ^ { \pm }$ 的取值分别为

$$
\begin{array}{c} \begin{array} { r l } & { M _ { \beta = 1 / 8 } ^ { \pm } = \left\{ \begin{array} { l l } { \pm \displaystyle \frac { 1 } { 4 } ( M \pm 1 ) ^ { 2 } \pm \beta ( M ^ { 2 } - 1 ) ^ { 2 } , } \\ { \qquad \lvert M \rvert \leqslant 1 ; } \\ { \displaystyle \frac { 1 } { 2 } ( M \pm \lvert M \rvert ) , } \end{array} \right. ( 1 } \\ & { P _ { \alpha = 1 / 8 } ^ { \pm } = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 4 } ( M \pm 1 ) ^ { 2 } ( 2 m M ) \pm \alpha M ( M ^ { 2 } - 1 ) ^ { 2 } , } \\ { \qquad \displaystyle \left. \lvert M \rvert \leqslant 1 ; \right.} \\ { \displaystyle \frac { 1 } { 2 } [ 1 \pm \mathrm { s g n } ( M ) ] , } \end{array}  ( 1 \right.} \end{array}   \end{array}
$$

# 1.2.3 $\mathbf { A U S M P W + }$ 算法

$\mathrm { A U S M P W + }$ 算法在 $\mathrm { A U S M + }$ 算法的基础上增加了压力加权项，重新构造 $M ^ { \pm }$ ，得到 $\bar { M } ^ { \pm }$ ．此时界面流通量

$$
\begin{array} { r l } { F _ { 1 / 2 , \mathrm { A U S M P W + } } = } & { } \\ { \qquad } & { \qquad \displaystyle c _ { \mathrm { f } } ( { { \bar { M } } _ { L } ^ { + } } | _ { \beta = 1 / 8 } \psi _ { L } + { \bar { M } } _ { R } ^ { - } | _ { \beta = 1 / 8 } \psi _ { R } ) + } \\ { \qquad } & { \qquad \quad ( P _ { L } ^ { + } | _ { \alpha = 3 / 1 6 } P _ { L } + P _ { R } ^ { - } | _ { \alpha = 3 / 1 6 } P _ { R } ) . } \end{array}
$$

其中,

$$
\begin{array} { r l } & { M _ { \mathrm { f } } = M _ { L } ^ { + } + M _ { R } ^ { - } \geqslant 0 , } \\ & { \bar { M } _ { L } ^ { + } = M _ { L } ^ { + } + M _ { L } ^ { - } \big [ ( 1 - \omega ) \cdot ( 1 + f _ { R } ) - f _ { L } \big ] , } \\ & { \bar { M } _ { R } ^ { - } = M _ { R } ^ { - } \omega \big ( 1 + f _ { R } \big ) ; } \\ & { M _ { \mathrm { f } } = M _ { L } ^ { + } + M _ { R } ^ { - } < 0 , } \\ & { \bar { M } _ { L } ^ { + } = M _ { L } ^ { + } \omega \big ( 1 + f _ { L } \big ) , } \\ & { \bar { M } _ { R } ^ { - } = M _ { R } ^ { - } + M _ { R } ^ { + } \big [ ( 1 - \omega ) ( 1 + f _ { L } ) - f _ { R } \big ] . } \end{array}
$$

式中， $f , \omega$ 为与压力相关的系数，即

$$
f _ { L , R } = \left\{ \begin{array} { l l } { \displaystyle \frac { p _ { \mathrm { t } , L } , p _ { \mathrm { t } , R } } { p _ { \mathrm { t } , \mathrm { s } } } , \quad p _ { \mathrm { t } , \mathrm { s } } \neq 0 ; } \\ { \quad } \\ { 0 , \quad p _ { \mathrm { t } , \mathrm { s } } = 0 . } \end{array} \right.
$$

$$
p _ { \mathrm { t , s } } = P _ { L } ^ { + } p _ { \mathrm { t } , L } + P _ { R } ^ { - } p _ { \mathrm { t } , R } .
$$

$$
\begin{array} { r } { \omega = 1 - \operatorname* { m i n } \Big ( \frac { p _ { \mathrm { t } , L } } { p _ { \mathrm { t } , R } } , \frac { p _ { \mathrm { t } , R } } { p _ { \mathrm { t } , L } } \Big ) ^ { 3 } . } \end{array}
$$

# 1.3 磁场散度误差处理

为了限制磁场散度误差的增加，使用Dedner的 HDC 方法[11] 处理磁场散度.HDC 方法通过变量 $\varphi$ 将磁场散度方程与磁感应方程联系起来，即

$$
\begin{array} { r l } & { \displaystyle \frac { \partial \boldsymbol { B } } { \partial t } + \nabla \cdot \left( \boldsymbol { v } \cdot \boldsymbol { B } ^ { \mathrm { T } } - \boldsymbol { B } \cdot \boldsymbol { v } ^ { \mathrm { T } } \right) + \nabla \varphi = 0 , } \\ & { } \\ & { D ( \varphi ) + \nabla \cdot \boldsymbol { B } = 0 . } \end{array}
$$

式中 $D$ 为线性差分算符， $D$ 取值不同，可得到不同的修正方法[23-24].

这里取文献[24]中的

$$
D ( \varphi ) = { \frac { 1 } { c _ { \mathrm { h } } ^ { 2 } } } { \frac { \partial \varphi } { \partial t } } + { \frac { \varphi } { c _ { \mathrm { p } } ^ { 2 } } } .
$$

将式(23)代入式(22)，得到

$$
{ \frac { \partial ^ { 2 } \varphi } { \partial t ^ { 2 } } } + { \frac { c _ { \mathrm { h } } ^ { 2 } } { c _ { \mathrm { p } } ^ { 2 } } } { \frac { \partial \varphi } { \partial t } } - c _ { \mathrm { h } } ^ { 2 } \nabla ^ { 2 } \varphi = 0 .
$$

式(24)为变量 $\varphi$ 的对流-耗散方程，磁场散度误差随变量 $\varphi$ 被输运到计算边界，在输运过程中被耗散减小.式（24）中， $c _ { \mathrm { h } }$ 为输运速度， $c _ { \mathrm { p } }$ 为耗散率.为了不对计算的时间步增加额外的限制，将 $c _ { \mathrm { h } }$ 取为

$$
c _ { \mathrm { h } } = \frac { C _ { \mathrm { F L } } } { \Delta t \operatorname* { m a x } ( 1 / d ) } ,
$$

这里 $C _ { \mathrm { F L } } = \operatorname* { m a x } \Big [ \frac { ( | u | + c _ { \mathrm { f } } ) \Delta t } { d } \Big ]$ （204号 $d$ 为网格大小.

按照文献[23]，耗散率

$$
c _ { \mathrm { p } } = \sqrt { - \Delta t \frac { c _ { \mathrm { h } } ^ { 2 } } { \ln ( c _ { \mathrm { r } } ) } } , \quad 0 < c _ { \mathrm { r } } < 1 .
$$

算例中取 $c _ { \mathrm { r } } = 0 . 6$

此时，控制方程式 $( 1 ) { \sim } ( 4 )$ 变为

$$
\frac { \partial U } { \partial t } + \frac { \partial F } { \partial x } + \frac { \partial G } { \partial y } + \frac { \partial H } { \partial z } = S .
$$

$$
\frac { \partial } { \partial t } \left[ \begin{array} { c } { \rho } \\ { \rho { \boldsymbol { v } } } \\ { { \boldsymbol { B } } } \\ { E } \\ { \varphi } \end{array} \right] + \nabla \cdot \left[ \begin{array} { c } { \rho { \boldsymbol { v } } } \\ { \rho { \boldsymbol { v } } \cdot { \boldsymbol { v } } + I \Big ( p + \frac { 1 } { 2 } | { \boldsymbol { B } } | ^ { 2 } \Big ) - { \boldsymbol { B } } \cdot { \boldsymbol { B } } } \\ { { \boldsymbol { v } } \cdot { \boldsymbol { B } } - { \boldsymbol { B } } \cdot { \boldsymbol { v } } + I \varphi } \\ { \Big ( { \boldsymbol { E } } + { \boldsymbol { p } } + \frac { 1 } { 2 } | { \boldsymbol { B } } | ^ { 2 } \Big ) { \boldsymbol { v } } - { \boldsymbol { B } } ( { \boldsymbol { v } } \cdot { \boldsymbol { B } } ) } \\ { c _ { \mathrm { h } } ^ { 2 } { \boldsymbol { B } } } \end{array} \right] = 0 ,
$$

$$
\left[ \begin{array} { c } { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { - \frac { c _ { \mathrm { h } } ^ { 2 } } { c _ { \mathrm { p } } ^ { 2 } } \varphi } \end{array} \right] .
$$

界面上的流通量相应变为

$$
F _ { 1 / 2 } = F _ { 1 / 2 } ^ { \mathrm { o r i } } + \frac { 1 } { 2 } ( \chi _ { B , L } ^ { n } + \chi _ { B , R } ^ { n } ) .
$$

式中， $F _ { 1 / 2 } ^ { \mathrm { o r i } }$ 为前文推导的式（10）AUSM系列算法、式 (15) ${ \mathrm { A U S M } } +$ 或式（18）AUSMPW $+$ 的界面流通量F1/2:

以 $x$ 方向为例，式(26)通量的具体表达形式为

# 1.4 重构方法

重构方式这里选择了MUSCL方法[25]，以 $x$ 方向为例，重构过程可以表达为

$$
\begin{array} { r l } & { U _ { \cdot , j , k } ^ { L } = U _ { \cdot , j , k } + \frac { 1 } { 4 } ( 1 - K ) \cdot } \\ & { \mathrm { ~ \operatorname* { m i n } ~ m o d } \left( \Delta U _ { i - 1 / 2 , j , k } , b \Delta U _ { i + 1 / 2 , j , k } \right) + } \\ & { \frac { 1 } { 4 } ( 1 + K ) \operatorname* { m i n } \mathrm { ~ m o d } \left( \Delta U _ { i + 1 / 2 , j , k } , b \Delta U _ { i - 1 / 2 , j , k } \right) \cdot } \\ & { \left( 2 8 \right) } \\ & { U _ { \cdot , j , k } ^ { R } = U _ { \cdot , j , k } - \frac { 1 } { 4 } ( 1 - K ) \cdot } \\ & { \mathrm { ~ \operatorname* { m i n } ~ m o d } \left( \Delta U _ { i + 1 / 2 , j , k } , b \Delta U _ { i - 1 / 2 , j , k } \right) - } \\ & { \frac { 1 } { 4 } ( 1 + K ) \operatorname* { m i n } \mathrm { ~ m o d } \left( \Delta U _ { i - 1 / 2 , j , k } , b \Delta U _ { i + 1 / 2 , j , k } \right) \cdot } \end{array}
$$

$$
\psi = \left[ \begin{array} { c } { \rho } \\ { \rho u } \\ { \rho u } \\ { \rho v } \\ { \rho w } \\ { B _ { z } } \\ { B _ { z } } \\ { B _ { z } } \\ { E + p _ { \mathrm { t r } } } \\ { 0 } \end{array} \right] ,
$$

式中，

$$
\begin{array} { l } { \Delta U _ { i + 1 / 2 , j , k } = U _ { i + 1 , j , k } - U _ { i , j , k } , } \\ { K = - 1 , 0 , 3 ; \ b = 0 . 9 . } \end{array}
$$

# 1.5 时间差分

对时间采用了二阶Runge-Kutta离散法．设半离散化方程为

$$
\begin{array} { r } { P = \left[ { \begin{array} { c } { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { - ( B _ { x , L } + B _ { x , R } ) u / 2 } \\ { - ( B _ { x , L } + B _ { x , R } ) w / 2 } \\ { - ( B _ { x , L } + B _ { x , R } ) w / 2 } \\ { - ( B _ { x , L } + B _ { x , R } ) ( v \cdot B ) / 2 } \\ { 0 } \\ { 0 } \end{array} } \right] , } \end{array}
$$

$$
\frac { \mathrm { d } u } { \mathrm { d } t } = L _ { \mathrm { h } } ( u ) .
$$

式中， $L _ { \mathrm { h } } ( u )$ 为空间离散算子.

二阶精度时间差商格式为

$$
\begin{array} { l } { { u _ { j } ^ { ( 1 ) } = u _ { j } ^ { n } + \Delta t L _ { \mathrm { h } } ( u _ { j } ^ { n } ) , } } \\ { { u _ { j } ^ { n + 1 } = \displaystyle \frac { 1 } { 2 } ( u _ { j } ^ { n } + u _ { j } ^ { ( 1 ) } ) + \displaystyle \frac { 1 } { 2 } \Delta t L _ { \mathrm { h } } ( u ^ { ( 1 ) } ) . } } \end{array}
$$

# 2 数值算例

为了验证和对比三种AUSM数值算法的性 能，用这三种算法分别计算了二维Rotor 算例和二 维Orszag-Tangvortex 算例

$$
\begin{array} { r } { \boldsymbol { \mathcal { X } } _ { B } = \left[ \begin{array} { c } { 0 } \\ { 0 } \\ { - B _ { x } ( B _ { x } , L + B _ { x } , R ) / 2 } \\ { 0 } \\ { - B _ { y } ( B _ { x , L } + B _ { x , R } ) / 2 } \\ { - B _ { z } ( B _ { x , L } + B _ { x , R } ) / 2 } \\ { - B _ { z } ( B _ { x , L } + B _ { x , R } ) / 2 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { c _ { 1 } ^ { 2 } B _ { x } } \end{array} \right] . } \end{array}
$$

# 2.1 二维Rotor算例

Rotor 问题[26] 被建议作为一个检验TorsionalAlfvenWaves运动的标准算例.这个问题假设开始时在静止流体内部有一个稠密气体形成的快速旋转圆柱体．本文取二维笛卡儿坐标系下， $( x , y ) \ \in$ （204号 $[ - 0 . 5 , 0 . 5 ] ^ { 2 }$

该问题的初值为

$$
p = 1 , \quad B _ { x } = 5 / \sqrt { 4 \pi } , \quad B _ { y } = B _ { z } = 0 ,
$$

$$
\begin{array} { r l } & { \rho = 1 + 9 f ( r ) , \quad r = \sqrt { x ^ { 2 } + y ^ { 2 } } . } \\ & { \left\{ \begin{array} { l l } { u = - 2 f ( r ) y / 0 . 1 , \quad v = 2 f ( r ) x / 0 . 1 , } \\ { \qquad w = 0 . 0 , \quad r < 0 . 1 ; } \end{array} \right. } \\ & { \left\{ \begin{array} { r l } { u = - 2 f ( r ) y / r , \quad v = 2 f ( r ) x / r , } \\ { w = 0 . 0 , \quad r \geqslant 0 . 1 . } \end{array} \right. } \end{array}
$$

$$
f ( r ) = \left\{ \begin{array} { l l } { 1 , \quad r < 0 . 1 ; } \\ { \displaystyle \frac { 2 0 0 } { 3 } ( 0 . 1 1 5 - r ) , \quad 0 . 1 \leqslant r \leqslant 0 . 1 1 5 ; } \\ { 0 , \quad r > 0 . 1 1 5 . } \end{array} \right.
$$

![](images/2ffa38978d854e3dcb07180b9ade75835dd43e2576e7f9498a97f829d47207be.jpg)  
图1AUSM三种算法对Rotor 算例计算得到的$B _ { x }$ 等高图 $( t = 0 . 1 5$ ）  
Fig.1The $x$ direction magnetic field of three AUSM algorithms to solve the Rotor problem ( $\dot { \iota } = 0 . 1 5$ ）

绝热系数 $\gamma = 1 . 4$ ，函数 $f ( r )$ 通过让2个量在从内部状态！ $( r < 0 . 1 )$ 到外部状态 $( r > 0 . 1 1 5 )$ 的一个小距离 $\delta r = 0 . 0 1 5$ 内，以线性方式平滑圆柱体表面密度和速度的不连续性.网格数为 $2 0 0 \times 2 0 0$ ，边界为自由输出.图1和图2给出了AUSM三种算法计算Rotor算例所得压强和 $B _ { x }$ ：

在初始速度作用下，计算区域中的流体开始旋转，同时在离心力的作用下向外运动，使得中心区域压强下降.对比图1和图2所示的三种算法计算结果可知，三种算法均正确计算出Rotor问题的结构，但是 AUSM 算法计算结果中的等值线不平滑,AUSMPW $+$ 算法结果中的等值线出现比较明显的震荡,而 $\mathrm { \ A U S M + }$ 算法的计算效果较好.

![](images/fb1ad2596db2ee11a37417c270fa6304bbfede59a74ace4870ed4e7b1fb6ef2b.jpg)  
图2AUSM三种算法对 Rotor 算例计算得到的$p$ 等高图 $( t = 0 . 1 5$ ）  
Fig.2Pressure field of three AUSM algorithms to solvethe Rotor problem( $\left( t = 0 . 1 5 \right)$ ）

# 2.2 Orszag-Tang vortex 算例

由于Orszag-Tang vortex 问题 [27]在 vortex 形成时有多种激波的相互作用，常被用来作为考核磁流体力学算法有效性的标准算例.本文把Orszag-Tangvortex 问题的初始条件给定在 $( x , y ) \in [ 0 , 2 \pi ] ^ { 2 }$ 的一

![](images/d3ed3f96f91a1ea21a4f0cee3207789a29589554bbefbcd5f2862f048aa299b9.jpg)  
图3AUSM三种算法对 Orszag-Tang vortex 算例计算得到的 $p$ 等高图 $( t = 3$ 0  
Fig.3Pressure field of three AUSM algorithms to solve the Orszag-Tang vortex problem ( $\dot { \boldsymbol { t } } = 3$ ）

个正方形区域内,有

$$
\begin{array} { r l } & { \rho ( x , y , 0 ) = \gamma ^ { 2 } , \quad p ( x , y , 0 ) = \gamma , } \\ & { u ( x , y , 0 ) = - \sin y , \quad v ( x , y , 0 ) = \sin x , } \\ & { B _ { x } ( x , y , 0 ) = - \sin y , \quad B _ { y } ( x , y , 0 ) = \sin 2 x . } \end{array}
$$

其中, $\gamma = 5 / 3$ ，采用周期性边界条件，网格数为 $2 0 0 \times$ 200.

![](images/8734f7df52168cd4f3d9ec353a1d1a1b640b766dd6e8dea66fe5e5c54463b8dd.jpg)  
图3和图4给出了三种算法计算Orszag-Tang  
图4AUSM三种算法对Orszag-Tangvortex 算例计算得到的 $B _ { x }$ 等高图（ $\mathit { t } = 3$ ）  
Fig.4The $x$ direction magnetic field of three AUSM algorithms to solve the Orszag-Tang vortex problem( $\dot { \boldsymbol { t } } = 3$ ）

vortex算例的压强和 $\mathbf { \Psi } _ { x }$ 方向磁场的等值线图．对比其他文献的计算结果[27]可知,三种算法均正确计算出Orszag-Tangvortex算例的总体结构. ${ \mathrm { A U S M } } +$ 得到的效果比较好，而其他两种算法结果的等值线都出现了锯齿状非物理结构.AUSM的耗散较大，会忽略一些细小结构．图5为三种算法对vortex 算例计算所得压强．从图5可以看出，AUSMPW＋的捕获能力强,在 $x = 2 . 6$ ，3.4均处捕捉到激波，但是同时振荡也较大.

# 3AUSM $+$ 算法在日冕结构数值模拟中的初步应用

通过前文中算例计算结果的对比， $\mathrm { A U S M + }$ 算法能够得到比较好的结果，因此本文将这种方法进一步应用于日冕结构的数值模拟．计算区域选取为从太阳表面到 $1 6 R _ { \mathrm { s } }$ (太阳半径)的球壳,采用文献[28]的方法，将球面划分为相同的6个网格区域采用并行计算．该网格系统有效解决了极区网格收敛性和奇性问题.在球坐标下每个球面区域为

$$
\Bigl ( \frac { \pi } { 4 } - \delta \leqslant \theta \leqslant \frac { 3 \pi } { 4 } + \delta \Bigr ) \cap \Bigl ( \frac { 3 \pi } { 4 } - \delta \leqslant \phi \leqslant \frac { 5 \pi } { 4 } + \delta \Bigr ) .
$$

其中, $\delta$ 是一个依赖于网格步长的小量以确保6个网格之间有重合.每一个计算区域均由式 (31)定义，但是各自在不同的球坐标系下，每一区域在相应坐标系空间是一个矩形，6个网格之间的坐标可以相互转化，对6个网格区域的详细描述可以参考文献[28].

![](images/5d2f9e9e6b9d15c31b1a8ac0db139902b627fa6290c2a91accac99478e263051.jpg)  
图5AUSM三种算法vortex 算例得到在$y = x$ 处的压强值！ $( t = 3$ 0  
Fig.5Pressure field of three AUSM algorithms to solvethe vortex problem at $y = x$ 0 $\mathit { t } = 3$ ）

将控制方程式(25）变换到太阳共转坐标系下，考虑太阳引力，并添加动量和能量源项以描述太阳风加速和日冕加热过程，此时控制方程变为

$$
\frac { \partial \rho } { \partial t } + \boldsymbol { \nabla } \cdot \rho \boldsymbol { v } = 0 ,
$$

$$
\begin{array} { r l } & { \cfrac { \partial \ c } { \partial t } + \textbf { v } \cdot \boldsymbol { \rho } \boldsymbol { v } - \textbf { u } , } \\ & { \qquad \partial ( \boldsymbol { \rho v } ) } \\ & { \cfrac { \partial ( \boldsymbol { \rho v } ) } { \partial t } + \nabla \cdot \Big [ \boldsymbol { \rho v } \cdot \boldsymbol { v } + \Big ( \boldsymbol { p } + \cfrac { { B } ^ { 2 } } { 2 \mu } \Big ) \boldsymbol { I } - \cfrac { \boldsymbol { B } \cdot \boldsymbol { B } } { \mu } \Big ] = } \\ & { \qquad - 2 \rho \boldsymbol { \Omega } \times \boldsymbol { v } - \boldsymbol { \rho } \cfrac { G M _ { \mathrm { s } } } { r ^ { 3 } } \boldsymbol { r } - \rho \boldsymbol { \Omega } ( \boldsymbol { \varOmega } \boldsymbol { r } ) + S _ { M } , } \end{array}
$$

$$
\begin{array} { r l } & { \frac { \partial B } { \partial t } + \nabla \cdot ( \boldsymbol { v } \cdot \boldsymbol { B } - \boldsymbol { B } \cdot \boldsymbol { v } ) + \nabla \varphi = 0 , } \\ & { \frac { \partial E } { \partial t } + \nabla \cdot \left[ ( E + p _ { \mathrm { t } } ) \boldsymbol { v } - \frac { \boldsymbol { B } ( \boldsymbol { v } \cdot \boldsymbol { B } ) } { \mu } \right] = } \\ & { \qquad - \rho \boldsymbol { v } \cdot \left[ \frac { G M _ { \mathrm { s } } } { r ^ { 3 } } r + \varOmega ( \varOmega r ) \right] + S _ { E } , } \\ & { \frac { \partial \varphi } { \partial t } + c _ { \mathrm { h } } ^ { 2 } \nabla \cdot \boldsymbol { B } = - \frac { c _ { \mathrm { h } } ^ { 2 } } { c _ { \mathrm { p } } ^ { 2 } } \varphi . } \end{array}
$$

其中,

$$
\begin{array} { l } { { \displaystyle E = \frac { 1 } { 2 } \rho { \boldsymbol v } ^ { 2 } + \frac { p } { \gamma - 1 } + \frac { 1 } { 2 } B ^ { 2 } , } } \\ { { \displaystyle p _ { \mathrm { t } } = p + \frac { 1 } { 2 } B ^ { 2 } , } } \end{array}
$$

$\boldsymbol { r }$ 为以日心为坐标原点的位置矢量， $- G M / r ^ { 2 }$ 为太阳表面的重力加速度， $\Omega = 2 2 / 2 7 . 2 7 5 3 \mathrm { r a d } { \cdot } \mathrm { d } ^ { - 1 }$ 为太阳的自转角速度，比热 $\gamma = 1 . 0 5$ ，方程中的 $\boldsymbol { S _ { M } }$ 和 $S _ { E }$ 为反映太阳风加速和日冕加热过程的动量和能量源项,取法与文献[28相同.

采用 Parker[29] 的太阳风解作为流场的初始条件，底面温度 $T \ = \ 1 . 3 \times 1 0 ^ { 6 } \mathrm { K } .$ ，底面数密度 $\textit { n } =$ $1 . 5 \times 1 0 ^ { 8 } \mathrm { c m ^ { - 3 } }$ ．采用如下偶极磁场和8级磁场的线性组合

$$
\begin{array} { r l } & { B _ { r } = a B _ { r } ^ { ( 2 ) } + b B _ { r } ^ { ( 5 ) } , \quad B _ { \theta } = a B _ { \theta } ^ { ( 2 ) } + b B _ { \theta } ^ { ( 5 ) } , } \\ & { B _ { r } ^ { ( 2 ) } = 2 R ^ { 3 } \cos \theta / r ^ { 3 } , \quad B _ { \theta } ^ { ( 2 ) } = R ^ { 3 } \sin \theta / r ^ { 3 } , } \\ & { B _ { r } ^ { ( 5 ) } = R ^ { 5 } [ 4 ( 5 \cos ^ { 2 } \theta - 3 ) / ( 3 r ^ { 5 } ) ] \cos \theta , } \\ & { B _ { \theta } ^ { ( 5 ) } = R ^ { 5 } [ ( 5 \cos ^ { 2 } \theta - 1 ) / r ^ { 5 } ] \sin \theta \quad ( a = 3 , b = 1 ) } \end{array}
$$

作为磁场的初始条件.图6给出了初始磁场的位形！

模型计算 $\mathrm { 3 0 h }$ 后达到稳态．图7给出了极区 $( L = 9 0 ) ,$ ）和赤道 $( L = 2 )$ ）处太阳风速度和密度随半径的变化，可见太阳风速度随半径增大，而密度随半径减小，这与观测和其他模型的计算结果相符图8给出了磁场结构在子午面内的投影，可见在高纬度区域，磁场开放向行星际空间；而在低纬区域，则形成了闭合的冕环结构．高纬与低纬磁场结构的差异通过太阳风与磁场的相互作用反映到密度和速度结构上，赤道处的太阳风速度比极区高，而密度比极区低，这些结果与文献[1]的计算结果一致.图9给出了计算区域内最大的磁场散度误差随时间的变化，最大磁场散度误差被控制在 $1 0 ^ { - 3 }$ 以下,随着计算进行而逐步稳定，说明HDC方法在日冕结构模拟中能够有效控制磁场散度误差，

![](images/13a07dfde955486656395472135ff8e8ae6c2d3d3a688882ec3edc5c9448c1d0.jpg)

![](images/7382aa4b77eba0d478e01ae1e514259dbc4aedd862db146f16647ca3a3ce3fd6.jpg)  
图6初始磁场在子午面内的投影 Fig.6Initial magnetic field in the meridian plane of projection

# 4结论

对比了AUSM， $\mathrm { A U S M + }$ 和 $\mathrm { A U S M P W + }$ 三种算法在使用HDC散度消去方法后计算多维MHD问题的性能，结果表明 ${ \mathrm { A U S M } } +$ 算法的性能最好.进一步使用 $\mathrm { A U S M + }$ 算法在6块网格构造下模拟了日冕结构，计算结果表明这种算法能够正确计算出日冕的大尺度结构，同时HDC方法能够较好地控制磁场散度误差,具有进一步的应用价值

![](images/f17afe71de071da32afc6787bae2c5321fcd9f4d606a168660034c54dcf4797d.jpg)  
图8稳态后磁场结构

![](images/0fb5b2253e73b2852c24af55a61e807c4650464760049b779b6e0c19977bf592.jpg)  
图7稳态后赤道和极区附近随半径变化的速度和密度 Fig.7Velocity and density at the equator and polar region with radius under steady station   
Fig.8Steady magnetic field structure   
图9数值模拟过程中计算域内磁场散度最大值 Fig.9Maximum of the magnetic field divergence in the process of numerical simulation

# 参考文献

[1] Feng X,Zhou Y,Wu S T.A novel numerical implementation for solar wind modeling by the modified conservation element/solution element method[J].Ap.J., 2007, 655(2):1110-1126   
[2] Yang L P,Feng X S,Xiang CQ,et al.Time-dependent MHD modeling of the global solar corona for year 2007: Driven by daily-updated magnetic field synoptic data[J]. J. Geophys. Res., 2012,117(A8):1101-1024   
[3] Riley P,Lionello R,Linker JA et al. Global MHD modeling of the solar corona and inner heliosphere for the whole heliosphere interval[J]. Solar Phys.,2010,274(1/2):361- 377   
[4] Shen F,Shen C,Wang Y et al. Could the collision of CMEs in the heliosphere be super-elastic? Validation through three-dimensional simulations[J].Geophys.Res.Lett., 2013, 40(8):1457-1461   
[5] Lyon J,Fedder J,Mobarry C.The Lyon-Fedder-Mobarry (LFM） global MHD magnetospheric simulation code[J]. J.Atmos. Sol-Terr. Phys.,2004,66(15-16):1333-1350   
[6] Pizzo V,Millward G,Parsons A et al. Wang-SheeleyArge-Enlil Cone Model transitions to operations [J]. Space Weather, 2010,9:S03004   
[7] T6th G. The $\nabla \cdot B = 0$ constraint in shock-capturing magnetohydrodynamics codes[J]. J. Comp. Phys., 2000, 161(2):605-652   
[8] Brackbill J U,Barnes D C.The effect of nonzero $\nabla \cdot \mathbf { \mathbf { \mathbf { B } } }$ （20 on the numerical solution of the magnetohydrodynamic equations [J]. J.Comp.Phys.,1980,35(3):426-430   
[9] Evans C R,Hawley JF. Simulation of magnetohydrodynamic flows-A constrained transport method[J].Ap.J., 1988, 332:659-677   
10] Powell K G.An approximate Riemann solver for magnetohydrodynamics//Upwind and High-Resolution Schemes [M].Berlin: Springer-Verlag,1994:570-583   
11] Dedner A,Kemm F,Kroner D,et al.Hyperbolic divergence cleaning for the MHD equations [J]. J. Comp. Phys.,2002,175(2):645-673   
12] Roe P L. Approximate Riemann solvers, parameter vectors，and difference schemes[J]．J. Comp．Phys.，1997, 135(2):250-258   
13] Van Leer B.Flux-vector splitting for the Euler equations [C]//Eighth International Conference on Numerical Methods in Fluid Dynamics,Lecture Notes in Physics. Berlin: Springer-Verlag,1982:507-512   
14] Steger J L,Warming R F.Flux vector splitting of the inviscid gas dynamic equation with application to finitedifference methods[J].J. Comp．Phys,,1981,40(2):263- 293   
[15] Rossow C-C. A flux-splitting scheme for compressible and incompressible flows[J]．J.Comp．Phys.，2000, 164(10):104-122   
[16] Liou M S,Stefen C J.A new flux splitting scheme[J]. J. Comp.Phys.,1993,107(1):23   
[17] Liou M S.A Sequel to AUSM[J]. J. Comp.Phys.,1996, 129(4):364-382   
[18] Edwards J R.A low-diffusion flux-splitting scheme for Navier-Stokes calculations [J]. Comp.Fluids,1997,26(6): 653   
[19] Jameson A.Artificial diffusion,upwind biasing,limiters and their effect on accuracy and multigrid convergence in transonic and hypersonic flow [R],AIAA Paper,1993- 3359.Reston: AIAA,1993   
[20] Agarwal R,Augustinus J.A comparative study of advection upwind split (AUSM) and wave/particle split (WPS) schemes for fluid and MHD flows [R],AIAA Paper 1999- 3613.Reston: AIAA,1999   
[21] Pan Y,Wang JF,Wu Y W.Upwind scheme for ideal 2-D MHD flows based on unstructured mesh[J]. Trans. Nanjing Univ. Aeron. Astron., 2007, 24(1):1-7   
[22] Han S H, Lee JI, Kim K H.Accurate and robust pressure weight advection upstream splitting method for magnetohydrodynamics equations [J]. AIAA J., 2009,47(5):970- 981   
[23] Munz C D,Schneider R，Sonnendrucker E,et al. Maxwell's equations when the charge conservation is not satisfied[J]. Comp.Ren.Acad.Sci.: Math.，1999, 328(5):431-436   
[24] Munz C D,Omnes P, Schneider R,E.et al. Divergence correction techniques for Maxwell solvers based on a hyperbolic model[J]. J. Comp．Phys. 2000,161(2):484-511   
[25] Zhang Deliang. A Course in Computational Fluid Dynamics [M].Beijing:Higher Education Press,2010.In Chinese (张德良．计算流体力学教程[M].北京：高等教育出版 社,2010)   
[26] Balsara D S,Spicer D S.A staggered mesh algorithm using high order Godunov fluxes to ensure solenoidal magnetic fields in magnetohydrodynamic simulations [J].J. Comp. Phys.,1999,149(2):270-292   
[27] Shen Y, Zha G,Huerta MA. E-CUSP scheme for the equations of ideal magnetohydrodynamics with high order WENO scheme[J]. J. Comp.Phys., 2012,231(19):6233- 6247   
[28] Feng X S,Yang L P, Xiang C Q,et al. Three-dimensional solar wind modeling from the Sun to Earth by a SIP-CESE MHD model with a six-component grid[J]. Ap.J., 2010, 723:300-319   
[29] Parker E N. Dynamical theory of the solar wind[J]. Space SmiRem 1965 4(5/6):666-708