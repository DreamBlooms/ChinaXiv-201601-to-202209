编号：2016-0209

# Herschel-Bulkley 流体的修正多松弛参数格子玻尔兹曼方法

吴伟伟，黄筱调，袁鸿(南京工业大学机械与动力工程学院，南京 211800)

摘要：Herschel-Bulkley 流体作为非牛顿流体中重要的的一类，已广泛应用于工程领域。为了改善 LBM对 Herschel-Bulkley 流体流动模拟时的稳定性和精度，在多松弛时间参数 LBM(MRTLBM)的基础上提出了一种改进方法。以Poiseuille流为例，对改进算法进行了详细介绍，对剪切变稀型和剪切增稠型流体分别进行对比，并比较在不同指数情况下的相对误差随格子数增大的变化趋势，说明了此改进方法的有效性，最后通过在水泥3D打印喷头中的应用，与多松弛时间参数的LBM(MRTLBM)的模拟结果进行对比，进一步验证了此改进方法的可行性。

关键词：Herschel-Bulkley 流体；修正MRTLBM；Poiseuille流；水泥3D打印；MRTLBM中图分类号：0373 文献标识码：A

# A Modified Multiple-relaxation-time Lattice Boltzmann Method for Herschel-Bulkley Fluids

WU Wei-Wei, HUANG Xiao-Diao, YUAN Hong (School of Mechanical and Power Engineering,Nanjing Tech University,Nanjing 211800,China)

Abstract:As an important kind of non-Newtonian fluids,Herschel-Bulkley fluids have been applied into engineering widely.When the latice Boltzmann method (LBM) was used in Herschel-Bulkleyflow,a modified method based on multiple-relaxation-time latice Boltzmann method was presented to improve the stability and accuracy of the simulation. Then Poiseuille flow was taken as an example to discuss the detailed process of the modified method. Also the variation trends of the relative errors with the lattce nodes in case of diferent power-law indexes were analyzed.The results showed that the modified method was eficient.Finally,the method was applied into the flow in the extruder ofcement-3D printing,and the numerical results were compared with thatof multiple-relaxation-time lattice Boltzmann method (MRT LBM), which further proved the feasibility of the method.

Keywords: Herschel-Bulkley fluids; modified MRT LBM; Poiseuille flow; cement-3D prnting; MRT LBM

# 0引言

LBM为流体流动的模拟提供了除有限元方法之外的又一种行之有效的方法，物理过程清晰，计算过程简单，已被广泛用于许多复杂流体流动中[-6],其中对非牛顿流体流动的仿真也有了较深入的研究。在分析非牛顿流体流动时，松弛时间会随着流体当地粘度的实时变化而变化。众所周知，松弛时间在保持在1/2到1的范围内，可以保证模拟的稳定性和精度，当超出这个范围后，极易出现不稳定和精度较差的情况[7。为了解决这个问题，相关学者都提出了一系列的方法。GabbanelliS针对幂律流体提出了一种截断模型，并利用Poiseuille流进行了分析对比，结果验证了此方法的有效性[8]；Malaspinas O利用局部方法分别对幂律流体和Carreau流体进行了详细研究，结果表明在一定的指数范围内，该方法有较好的稳定性[；BoydJ等采用局部方法对幂律流体在管道中的流动进行了分析，研究表明该方法的计算精度和效率均高于GabbanelliS所提出的截断模型[0]；2001年，D'Humieres D 等针对三维方腔流动提出了多松弛时间参数的LBM，并证明了具有比普通LBM更好的稳定性[11]；后来MRTLBM也被用来解决非牛顿流体的仿真问题，CHAIZhenhua等利用MRTLBM对非牛顿流体中的幂律流体及宾汉流体进行了分析，结果表明此方法具有很好的稳定性和良好的精度[12];FallahK等利用MRTLBM对幂律流体在旋转圆柱中流动进行了模拟，分析了转速和幂律指数对流动过程的影响[13]；CHEN Songgui等采用MRTLBM对宾汉流体在平行平板中的三维流动进行了模拟，解决了传统LBM对非牛顿流体仿真时的不稳定性问题[14]；LI Qiuxiang等对幂律流体在二维方腔中的流动进行了分析，结果表明MRTLBM可以很好地应用于对非牛顿流体的仿真，而雷诺数大小和幂律指数对模拟结果有较大的影响[15]。

虽然对非牛顿流体的研究已经很深入，但是主要还是集中在幂律流体、宾汉流体等常见的非牛顿流体种类，对于不常见的如Herschel-Bulkley 流体等研究的就很少。本文以Herschel-Bulkley流体作为研究对象，基于MRTLBM方法，提出了一种改进方法，可以更有效地改善仿真过程的稳定性。以Poiseuille流为例，详细介绍了此方法，并与解析解进行了对比，分析了相对误差，最后将此方法应用于对水泥浆体在3D打印喷头流动中的分析，对该方法的可行性做进一步说明。

# 1MRTLBM对Herschel-Bulkley流体的 流动模拟

# 1.1Herschel-Bulkley流体的本构方程

Herschel-Bulkley流体的本构模型是以分段函数形式呈现的，由于存在初始屈服应力，当小于初始屈服应力时，剪切率为0，具体表达形式为：

$$
\tau _ { a } = \left\{ \begin{array} { l l } { \tau _ { 0 } + K \dot { \gamma } ^ { n } } & { , \left| \tau \right| > \tau _ { 0 } } \\ { \dot { \gamma } = 0 } & { , \left| \tau \right| < \tau _ { 0 } } \end{array} \right.
$$

为了避免分段函数在分析时所带来的不便，采用其修正本构方程如下：

$$
\tau _ { { \scriptscriptstyle a } } = \tau _ { 0 } [ 1 - \exp ( - m \dot { \gamma } ) ] + K \dot { \gamma } ^ { n }
$$

式中参数 $\mathbf { \nabla } _ { m }$ 主要控制应力的增长，来避免本构方程固有的非连续特性，当 $\mathbf { \nabla } _ { m }$ 大小趋向于0时，即成为幂律流体的本构方程，当 $\mathbf { \nabla } _ { m }$ 趋向于无穷大时，即成为理想的Herschel-Bulkley 流体，当 $\dot { \gamma } = 0$ 时，与原本构方程吻合，在一般情况下， $\mathbf { \nabla } _ { m }$ 取大一点的值，应当注意 $m$ 值不能取任意足够大的值，否则会带来收敛问题，进一步可以推导得到显观粘性系数方程[16-18],

$$
\nu _ { _ { a p } } = K \mid \dot { \gamma } \mid ^ { n - 1 } + \frac { \tau _ { _ 0 } } { \mid \dot { \gamma } \mid } [ 1 - \exp ( - m \mid \dot { \gamma } \mid ) ]
$$

# 1.2MRTLBM流体分析

MRT格子Boltzmann方程为：

$$
\begin{array} { l } { { f ( r + e _ { i } \delta t , t + \delta t ) - f ( r , t ) = } } \\ { { \qquad - M ^ { - 1 } \overline { { S } } M \Big [ f ( r , t ) - f ^ { e q } ( r , t ) \Big ] } } \end{array}
$$

将 $\mathbf { \chi } _ { f ( r , t ) }$ 和 $f ^ { q } ( r , t )$ 转换到矩空间 $\tilde { \boldsymbol { \mathrm { n } } } ( \boldsymbol { r } , t )$ 和 $\tilde { \boldsymbol { \Pi } } ^ { e q } \left( \boldsymbol { r } , t \right)$ ，即 $\tilde { \mathbf { n } } ( \pmb { r } , t ) = \pmb { M } \pmb { f } ( \pmb { r } , t )$ ， $\tilde { \mathbf { n } } ^ { e q } ( \pmb { r } , t ) = \pmb { M } \pmb { f } ^ { e q } ( \pmb { r } , t )$ ，矩阵 $M$ 定义如下：

$$
M = \left[ { \begin{array} { c c c c c c c c c } { 1 } & { 1 } & { 1 } & { 1 } & { 1 } & { 1 } & { 1 } & { 1 } & { 1 } \\ { - 4 } & { - 1 } & { - 1 } & { - 1 } & { - 1 } & { 2 } & { 2 } & { 2 } & { 2 } \\ { 4 } & { - 2 } & { - 2 } & { - 2 } & { 1 } & { 1 } & { 1 } & { 1 } \\ { 0 } & { 1 } & { 0 } & { - 1 } & { 0 } & { 1 } & { - 1 } & { - 1 } & { 1 } \\ { 0 } & { - 2 } & { 0 } & { 2 } & { 0 } & { 1 } & { - 1 } & { - 1 } & { 1 } \\ { 0 } & { 0 } & { 1 } & { 0 } & { 1 } & { 1 } & { - 1 } & { - 1 } \\ { 0 } & { 0 } & { - 2 } & { 0 } & { - 2 } & { 1 } & { 1 } & { - 1 } & { - 1 } \\ { 0 } & { 1 } & { - 1 } & { 1 } & { - 1 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 1 } & { - 1 } & { 1 } & { - 1 } \end{array} } \right]
$$

$\mathit { \Pi } _ { \overline { { S } } } ^ { - }$ 为与松弛相关的主对角线矩阵：

$$
\overline { { { \pmb { S } } } } = d i a g ( s _ { 0 } , s _ { 1 } , s _ { 2 } , s _ { 3 } , s _ { 4 } , s _ { 5 } , s _ { 6 } , s _ { 7 } , s _ { 8 } )
$$

在模型中，密度和动量属于守恒量，因此与密度和动量相关的量 $s _ { 0 }$ ， $s _ { 3 }$ ， $s _ { 5 }$ 均取0， $s _ { 7 }$ ， $s _ { 8 }$ 取 $1 / \tau$ 这里的 $\boldsymbol { \tau }$ 为BGK模型里的松弛时间，而剩余的其它参数取稍大于1的数，这里 $s _ { 1 } { = } s _ { 2 } { = } 1 . 4$ ， $s _ { 4 } { = } s _ { 6 } { = } 1 . 2$ 。MRT模型的演变过程由两个过程构成：碰撞和迁移，此处的碰撞步与BGK模型有所区别，按下述方程进行：

$$
f ^ { + } ( r , t ) = f ( r , t ) - M ^ { - 1 } \overline { { S } } [ \overleftarrow { \ast } \overrightarrow { / { \mathfrak { F } } } , t ) - \mathbf { \Phi } ^ { e q } ( r , t ) ]
$$

其中 $\boldsymbol { \mathscr { f } } ^ { + } ( \boldsymbol { r } , t )$ 即为碰撞后的密度分布函数；迁移步与BGK模型的相同：

$$
f ( \pmb { r } + \pmb { e } _ { i } \delta t , t + \delta t ) { = } \pmb { f } ^ { + } ( \pmb { r } , t )
$$

与BGK模型相比，MRT模型主要包含了矩空间和速度空间之间的转换过程。利用Chapman-Enskog展开，可以得到运动粘度：

$$
\mu { = } \rho \nu { = } \rho c _ { s } ^ { 2 } ( \frac { 1 } { s _ { 8 } } { - } \frac 1 2 ) \delta t
$$

也可以得到密度和速度的宏观量定义，与BGK模型相似：

$$
\rho = \sum _ { i = 0 } ^ { 8 } f _ { i } ( \pmb { r } , t ) , \rho \pmb { u } = \sum _ { i = 0 } ^ { 8 } c _ { i } f _ { i } ( \pmb { r } , t )
$$

运动粘度与剪切速率有关，传统数值方法求解，需要建立合适的差分模型，而LBM可以避免这个过

程，在MRT模型中，应变率张量比BGK模型复杂，可以推导得到[19][20].

$$
\begin{array} { l } { { \displaystyle S _ { \alpha \beta } = - \frac { 1 } { 2 \rho c _ { s } ^ { 2 } \delta _ { t } } } } \\ { { \displaystyle \quad \quad \cdot \left[ \sum _ { i = 0 } ^ { 8 } e _ { i \alpha } e _ { i \beta } \sum _ { j = 0 } ^ { 8 } ( M ^ { - 1 } \overline { { { S } } } M ) _ { i j } ( f _ { j } ( r , t ) - f _ { j } ^ { e q } ( r , t ) ) \right] ^ { ( 1 0 ) } } } \end{array}
$$

# 1.3修正MRTLBM

根据上面的分析可以知道，MRTLBM应用于非牛顿流体时，主要受当地松弛时间的影响，也可看成是受粘度的影响，而粘度通过应力张量与应变率相关联。对于Herschel-Bulkley 流体，当 $n { < } 1$ 时，对应剪切变稀型流体，当 $\scriptstyle n = 1$ 时，则为宾汉流体，当$n { > } 1$ 时，对应剪切增稠型流体。在对含有指数项的非牛顿流体直接应用MRTLBM分析时会出现稳定性和精度问题，当剪切率趋近于0时，对于 $n { < } 1$ 的剪切变稀型流体，粘度会趋向于无穷大，导致发散；对于 $n { > } 1$ 的剪切增稠型流体，粘度会趋向于0，在过去的学者研究过程中，并未针对Herschel-Bulkley 流体的分析提及相关的解决方法。

事实上，大部分的非牛顿流体仅仅在某一个剪切率范围内呈现出非牛顿流体的特性，在此范围外时，通常表现出类似牛顿流体的特性，即粘度是一个定常数[8]，所以基于这种现象，针对Herschel-Bulkley 流体，提出了一种修正MRTLBM方法，这种方法以分段函数的形式呈现。由于Herschel-Bulkley流体存在屈服应力，为了保证剪切率在有效范围外时，粘度是一个常数，这里用宾汉流体的本构模型来进行代替。

$$
\begin{array} { r } { \nu ( \dot { \gamma } ) = \left\{ \begin{array} { l l } { \tau _ { 0 } / \dot { \gamma } _ { 0 } + \mu _ { B } \dot { \gamma } _ { 0 } ^ { ( n - 1 ) } , \dot { \gamma } < \dot { \gamma } _ { 0 } } \\ { \tau _ { 0 } / \dot { \gamma } + K \dot { \gamma } ^ { ( n - 1 ) } , \dot { \gamma } _ { 0 } < \dot { \gamma } < \dot { \gamma } _ { \infty } } \\ { \tau _ { 0 } / \dot { \gamma } _ { \infty } + \mu _ { B } \dot { \gamma } _ { \infty } ^ { ( n - 1 ) } , \dot { \gamma } > \dot { \gamma } _ { \infty } } \end{array} \right. } \end{array}
$$

MRTLBM可以在动力粘度处于某一范围时，进行精确、稳定地模拟分析，而当松弛时间接近于1/2时，会出现不稳定的情况，引起发散，此时对应的粘度接近于0， $\scriptstyle \nu \leq 0 . 0 0 1$ ；对应地，当松弛时间大于1时，MRTLBM的精度会降低，此时对应的粘度相对较大， $\nu { \geq } 1 / 6$ 。因此对式(11)设置粘度的上极限值和下极限值 $\nu _ { \mathrm { m i n } } { = } 0 . 0 0 1$ 和 $\nu _ { \mathrm { m a x } } { = } 0 . 1 6$ 。很明显，对于剪切变稀型流体，粘度最大值对应剪切率接近于0的时候，相应地，对于剪切增稠型流体，粘度最小值对应剪切率接近于0的时候。

# 2 平行平板之间的流动

由于泊肃叶流存在理论解，常被用来验证稳定性及精度问题。这里以泊肃叶流为例，介绍这种修正模型的具体过程。两平行平板沿 $y$ 方向的距离为$H$ ，在 $x$ 方向存在一个恒定值的压力梯度 $\boldsymbol { \nabla } P$ ，可以得到沿 $y$ 方向的速度分量 $u _ { y }$ 的分布情况。根据对称性，将 $y$ 方向的距离分成[ $\cdot H / 2 , 0 ]$ 和 $[ 0 , H / 2 ]$ 两部分，根据对称性，只需对 $[ 0 , H / 2 ]$ 范围内分析，就可以得到 $u _ { y }$ 沿整个 $y$ 方向的分布情况。在 $[ 0 , H / 2 ]$ 区间内，可以分出四个不同的区域A、B、C和D，其中区域A对应的是靠近壁面的高剪切率范围，此时剪切率超过了 $\dot { \gamma } _ { \infty }$ ，以 $y _ { h }$ 作为分界值，在此区域内，将流体看成宾汉流体；区域B对应的是Herschel-Bulkley流体的有效区域，以 $y _ { l }$ 作为临界分界值；区域C对应的是低剪切率范围，此时的流体看成是宾汉流体；区域D对应的是应力小于屈服应力的阶段，此时剪切率为0，以 $y _ { \tau }$ 作为分界值。结合泊肃叶流的速度推导，可以得到该修正方法的速度分布的理论函数。

$$
\begin{array} { r } { u _ { y } = \left[ \begin{array} { l } { \displaystyle \frac { n } { n + 1 } \Big ( - \frac { 1 } { K } \frac { \hat { \alpha } P } { \hat { \alpha } x } \Big ) ^ { [ s ] } \Bigg [ \bigg ( \frac { H } { 2 } + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { ( s + 1 ) / s } - \bigg ( y _ { z } + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { ( s + 1 ) / s } \Bigg ] } \\ { - \frac { 1 } { 2 \nu _ { s e } \hat { \alpha } P } \Bigg [ \bigg ( \frac { H } { 2 } + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { 2 } - \bigg ( y + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { 2 } \Bigg ] + \alpha _ { 1 } } \\ { \displaystyle \frac { n } { n + 1 } \bigg ( - \frac { 1 } { K } \frac { \hat { \alpha } P } { \hat { \alpha } x } \bigg ) ^ { [ s ] } \Bigg [ \bigg ( \frac { H } { 2 } + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { ( s + 1 ) / s } - \bigg ( y + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { [ s + 1 ] / s } \Bigg ] + \alpha _ { 2 } , ~ y _ { i } \le y \le y _ { k } } \\ { - \frac { 1 } { 2 \nu _ { s e } \hat { \alpha } P } \Bigg [ \bigg ( \frac { H } { 2 } + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { 2 } - \bigg ( y + \frac { \tau _ { 0 } } { \hat { \alpha } P / \hat { \alpha } x } \bigg ) ^ { 2 } \Bigg ] + \alpha _ { 3 } } \end{array} \right] , } \end{array}
$$

上式中的常数项 $a _ { 1 } , \ a _ { 2 }$ 和 $a _ { 3 }$ 表达式如下：

$$
\begin{array} { r l } & { G _ { 1 } - \frac { \pi } { h + 1 } \Bigg ( - \frac { 1 } { h } \frac { \delta p ^ { h } } { \delta \Delta x } \Bigg ) ^ { ( 1 / 2 ) } \Bigg [ \Bigg ( \frac { H } { 2 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg ( \mathbf { J } _ { 1 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg ] } \\ & { \quad + \frac { 1 } { 2 \sqrt { \pi } \rho ^ { ( \tilde { h } ) } } \Bigg ( \Bigg [ \frac { H } { 2 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg ( \mathbf { J } _ { 1 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) } \Bigg ] } \\ & { \quad \sigma _ { 2 } - \frac { 1 } { 2 \sqrt { \pi } \rho ^ { ( \tilde { h } ) } } \Bigg ( \mathbf { J } _ { 2 } ^ { ( 1 / 2 ) - 1 } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg ( \mathbf { J } _ { 1 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) } \Bigg ] } \\ & { \quad \quad - \frac { \pi } { h + 1 } \Bigg ( \mathbf { \frac { J } { 2 } } \frac { \delta p ^ { h } } { \delta \Delta x } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg [ \frac { H } { 2 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ] ^ { ( 1 / 2 ) - 1 } \Bigg ( \mathbf { J } _ { 2 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg ] + \sigma _ { 2 } } \\ & { \quad \sigma _ { 3 } - \frac { \pi } { h + 1 } \Bigg ( - \frac { 1 } { h } \frac { \delta p ^ { h } } { \delta \Delta x } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg [ \left( \frac { H } { 2 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \right) ^ { ( 1 / 2 ) - 1 } \Bigg ( \mathbf { J } _ { 1 } + \frac { \Sigma _ { \mu } } { \delta p ^ { ( \tilde { h } , 1 ) } } \Bigg ) ^ { ( 1 / 2 ) - 1 } \Bigg ] } \\ &  \quad + \frac { 1 } { 2 \sqrt { \pi } \rho ^ { ( \tilde { h } , 1 ) } } \frac { \delta p ^ { h } }  \end{array}
$$

将上述速度分布的函数求导后，根据应力相等条件可以得到对应的分界值分别为：

$$
\begin{array} { l } { \displaystyle y _ { \tau } = - \frac { \tau _ { 0 } } { \hat { c } P / \hat { c } \boldsymbol { x } } } \\ { \displaystyle y _ { \tau } = - \frac { 1 } { \hat { c } P / \hat { c } \boldsymbol { x } } \Bigg [ \left( \frac { \left( \rho \nu _ { 0 } \right) ^ { n } } { K } \right) ^ { 1 / ( n - 1 ) } - \tau _ { 0 } \Bigg ] } \\ { \displaystyle y _ { h } = - \frac { 1 } { \hat { c } P / \hat { c } \boldsymbol { x } } \Bigg [ \left( \frac { \left( \rho \nu _ { \infty } \right) ^ { n } } { K } \right) ^ { 1 / ( n - 1 ) } - \tau _ { 0 } \Bigg ] } \end{array}
$$

其中 ${ \partial P } / { \partial x } = \nabla P$ ，根据表达式中物理量的数值大小的不同，可以得到不同的区域划分。

根据式(14)，这里主要考虑四个因素对最后仿真结果的影响：初始屈服应力 $\tau _ { 0 }$ ，压力梯度 $\boldsymbol { \nabla } P$ ，幂律指数 $n$ 以及格子数 $N$ 。观察式(14)后发现，为了保证$\tau _ { 0 } < \frac { 1 } { 2 } \left( \frac { \left( \rho \nu _ { 0 } \right) ^ { n } } { K } \right) ^ { 1 }$ /(n−1)$y _ { l }$ 或 $( \mathfrak { F } \mathbb { I } ) y _ { h }$ 的存在，则必须有 或和 $) \tau _ { 0 } < \frac { 1 } { 2 } \left( \frac { \left( \rho \nu _ { \infty } \right) ^ { n } } { K } \right) ^ { 1 / ( n - 1 ) } \circ$

为了考察使用此截断模型时，不同的指数 $n$ 的有效性，这里取 $n$ 的范围为 $0 . 2 { \sim } 5$ ，这里幂律指数 $n$ 取0.5和1.5，分别对应剪切变稀型流体和剪切增稠型流体，这样可以更清楚地表现初始屈服应力对仿真结果的影响。当 $n$ 取0.5时，压力梯度 $\boldsymbol { \nabla } P { = } { - } 1 . 5 { \times } 1 0 ^ { - 6 }$ ，流体的粘度系数 $K { = } 0 . 0 0 1$ ，平板的高度 $\scriptstyle H = 1 0$ ，在模拟时，格子数取为200，流体的密度 $\scriptstyle \rho = 1$ ，运动粘度的极限 $\nu _ { m i n } { = } 0 . 0 0 1$ ， $\nu _ { m a x } { = } 0 . 1 6$ ，这里 $n { < } 1$ ，则有 $\nu _ { 0 } { = } 0 . 1 6$ ，$\nu _ { \infty } { = } 0 . 0 0 1$ ，初始屈服应力 $\tau _ { 0 } { = } 3 . 0 { \times } 1 0 ^ { - 6 }$ ，其数值结果和仿真结果对比图如图1所示，图中实线是根据式(12)的解析解描绘的速度分布情况，圆圈是通过LBM仿真获得的，虚线部分分别是宾汉流体和

Herschel-Bulkley流体相对应的延续，垂直的虚线代表了不同区域的分界点。

![](images/6f489bc144b4c77a2038f26a175dddf974c518840dc757d79a1da8d48b1b6d6f.jpg)  
图 $1 \ n { = } 0 . 5$ 时的速度分布Fig.1 Velocity distribution for $\scriptstyle n = 0 . 5$

当幂律指数 $n$ 取1.5时，压力梯度 $\scriptstyle \nabla P = - 2 \times 1 0 ^ { - 6 }$ 流体的粘度系数 $K { = } 0 . 0 1$ ，平板的高度 $\scriptstyle H = 1 0$ ，在模拟时，格子数取为200，流体的密度 $\scriptstyle \rho = 1$ ，运动粘度的极限 $\nu _ { m i n } { = } 0 . 0 0 1$ ， $\nu _ { m a x } { = } 0 . 1 6$ ，这里 $n { > } 1$ ，则有 $\scriptstyle { \nu _ { 0 } = 0 . 0 0 1 }$ ，${ \nu _ { \infty } } \mathrm { { = } } 0 . 1 6$ ，初始屈服应力 $\tau _ { 0 } { = } 4 . 0 { \times } 1 0 ^ { - 6 }$ ，其数值结果和仿真结果对比图如图2所示，图中实线是根据式(12)的解析解描绘的速度分布情况，圆圈是通过LBM仿真获得的，虚线部分分别是宾汉流体和Herschel-Bulkley流体相对应的延续，垂直的虚线代表了不同区域的分界点。

观察图1和图2可以发现，无论初始屈服应力如何变化，数值解与解析解具有较好的重合度。初始屈服应力 $\tau _ { 0 }$ 与压力梯度VP决定了屈服阶段即区域D 的范围大小。

![](images/b32c95f8e6fbc5fd9823315d1c7b34edc7f8e9ba1d9fdc3cc6975305208f66fb.jpg)  
图 $2 \ n { = } 1 . 5$ 时的速度分布对比Fig.2 Velocity distribution for $n { = } 1 . 5$

这里对于四种指数不同的流体，均进行了一系列的仿真，比较MRTLBM仿真与解析解之间的相对误差，其中相对误差通过 $\sum _ { i = 1 } ^ { N } ( 1 - \nu _ { i } ^ { L B M } \ / \nu _ { i } ^ { a n a l } ) ^ { 2 }$ 可以计算获得。由于LBM仿真结果的精度与粘度有关，为了保证只讨论相对误差与格子数之间的关系，在进行单位转换的时，模型中的粘度 $\nu ^ { * } \substack { = } \nu ( \delta x ^ { 2 } / \delta t )$ ，令$\delta x ^ { 2 } / \delta t$ ，当增大LBM的格子数 $\mathrm { \Delta N }$ 时，只需要同时按比例缩放 $\delta x$ 和 $\delta t$ ，即可保证粘度不变，由于 $\delta x \propto 1 / N$ ，根据前面的关系可知， $\delta t \propto 1 / N ^ { 2 }$ ，这里 $N$ 逐渐从10增大到200，在指数和压力梯度不同的情况下，相对误差如图3所示。

![](images/45bee1044887b0ab51ad479a3d909c320f4838676de4f3bdf2724ca06ab761e5.jpg)  
图3相对误差对比图Fig.3Relative Error analysis

图中实线代表了斜率为-1的直线，图例中a表示低剪切率区域范围C较小的情况，b表示低剪切率区域C范围较大的情况，对比发现，a和b两种情况下产生的相对误差基本相同，且随着格子数的增加，相对误差不断地下降，如果进一步增加格子数量，可以控制在 $0 . 0 1 \%$ 以内，从图中可以进一步看出，当指数 $n$ 取值不同时，相对误差的差异性较明显。

# 3 在水泥3D打印喷头内的仿真应用

在进行水泥3D打印时，需要利用螺杆挤出方式来实现水泥浆体的挤出成型，因此了解水泥浆体在喷头内的流动显得尤为重要。水泥浆体在一定的水灰比下呈现出明显的Herschel-Bulkley流体特性，当室温为 $2 0 \mathrm { ~ \textdegree C }$ ，水灰比为0.5，水化时间为 $5 \mathrm { m i n }$ 时，浆体呈现出典型的Herschel-Bulkley流变模式，流变学方程描述为[21]:

$$
\tau _ { _ a } = \left\{ \begin{array} { l l } { 3 . 8 9 9 + 1 . 1 0 3 \dot { \gamma } ^ { 0 . 6 3 3 } \ , \left| \tau _ { _ a } \right| > 3 . 8 9 9 } \\ { \dot { \gamma } = 0 \ , \left| \tau _ { _ a } \right| < 3 . 8 9 9 } \end{array} \right.
$$

将上式转换成式(11)的形式，式中参数 $m$ 主要控制应力的增长，这里取 $\scriptstyle { m = 5 0 0 }$ ，则有

$$
\tau { = } 3 . 8 9 9 [ 1 { - } \exp ( - m \dot { \gamma } ) ] { + } 1 . 1 0 3 \dot { \gamma } ^ { n }
$$

水泥浆体在图4的螺槽区域流动，其中螺杆以恒定的转速 $N$ 进行旋转，假设螺杆静止，则可认为是机筒以转速 $N$ 进行反向旋转，将整个结构进行展开，即可形成一个截面为矩形的腔[22]，此时忽略螺棱的轻微倾斜[23]，展开示意图如图5所示，对图4水泥浆体在螺杆中的流动分析即转换成水泥浆体在图5中长方体型腔体中的流动分析。

T

![](images/4286c6eeba82e9f95ad445061f4e01dede5d3206df1e0f96e057d6ad0ba36598.jpg)  
图4喷头结构图  
Fig.4Extruder Structure   
图5喷头展开示意图 Fig.5 Expansion Structure

根据喷头的展开示意图，这里取中心位置的截面 $( Y - Z ) _ { C e n t e r }$ ，采用D2Q9 模型，其中只对上表面设置速度，速度方向沿 $y = h$ 处的Z方向，其他三个面速度均为0，忽略壁面滑移的影响，截面的实际尺寸为$W { = } 1 6 \ \mathrm { m m }$ ， $h { = } 6 \mathrm { m m }$ ，结合喷头扫描速度的需求以及水泥浆体的凝固时间，浆体的挤出速度相对较低，螺杆的旋转速度取 $3 0 \mathrm { \Delta ~ r } / \mathrm { m i n }$ 进行，螺杆的导程角$\scriptstyle \theta = 2 0 ^ { \circ }$ ，利用相似准则，取雷诺数 $R e$ 为关键准则数进行量纲转换，可以得到仿真模型中的各参数，再采用式(13)对粘度进行修正，即可保证稳定性和精度，得出流线图如图6所示。流体的流动以环流的形式呈现，环流的中心在(0.5W，0.7h)附近，在左下角和右下角不存在明显的流体流动。

![](images/e47c48f1d0d981daedd790f6f6e013839e444171e6c4786371f7fb88c20c1004.jpg)

运用修正MRTLBM，采取不同的格子数进行模拟，并与MRTLBM进行比较，得到相应的速度场分布，如图7所示，其中修正MRTLBM格子数分别取 $2 8 8 \times 1 0 8$ 和 $1 6 0 \times 6 0$ ，MRTLBM格子数取$2 8 8 \times 1 0 8$ 与修正MRTLBM进行比较。图7(a)是取螺槽宽度为 $8 \mathrm { m m }$ 时，速度分量 $u$ 与螺槽深度之间的关系图，图7(b)是取螺槽深度为 $5 . 4 \mathrm { m m }$ 时，速度分量$u$ 与螺槽宽度之间的关系图，图7(c)是取螺槽宽度为$1 4 . 4 \mathrm { m m }$ 时，速度分量 $\mathbf { \sigma } _ { \nu }$ 与螺槽深度之间的关系图，图7 (d)是取螺槽深度为 $3 \mathrm { m m }$ 时，速度分量 $\nu$ 与螺槽宽度之间的关系图。可以看出该修正方法可以有效对速度场的分布进行模拟，采取不同的格子数时，虽然结果存在一定误差，但是基本一致。

![](images/0cad688f514c1979962af744088a2a2571e12379c5bf2ead31d1545f2bc7733e.jpg)  
图6流线图  
图7速度分布图Fig.7 Velocity distributions

# 4结论

针对广义牛顿流体中的Herschel-Bulkley流体，提出了一种修正MRTLBM方法，可以有效改善在模拟时易出现发散的情况。

（1）通过Poiseuille流对此方法进行了详细论述，推导了理论解公式；计算了相对误差，随着格子数的增加，相对误差不断减小，能达到 $0 . 0 5 \%$ 左右，且剪切变稀型和剪切增稠型流体呈现相同的变化趋势，还进一步证明了低剪切率区域范围的大小对相对误差几乎没有影响，而指数 $n$ 的取值不同对其有较大影响。

（2）将此方法应用于对水泥浆体在3D打印喷头中流动情况的分析，并采用MRTLBM方法与文中的方法进行了对比，发现其速度场分布基本一致，进一步证明了此改进方法的有效性。

（3）对水泥3D打印喷头中的流动分析可知，受浆体粘性和喷头结构的影响，浆体在喷头横截面的流动呈现环流特征，环流中心大致在(0.5W，0.7h)处，可以根据流线图来判断浆体的流动区域。从流动分析可以看出，在腔体的下方左右两角处不存在明显的流体流动，而为了保证流体的流动速度，一方面可以适当增大螺杆的旋转速度，另一方面可以适当增大螺槽的宽度。

# 参考文献

[1] Sheikholeslami M,Gorji-Bandpy M,Ganji D D.Lattice Boltzmann Method for MHD Natural Convection Heat Transfer Using Nanofluid[J].Powder Technology, 2014, 254:82-93.   
[2] Ashorynejad H R,Mohamad A A,Sheikholeslami M. Magnetic Field Effects on Natural Convection Flow of a Nanofluid in a Horizontal Cylindrical Annulus Using Lattice Boltzmann Method[J]. International Journal of Thermal Sciences,2013,64: 240-250.   
[3] SHEN Ching，TIAN Dongbo，XIE Chong，et al. Examination of the LBM in Simulation of Microchannel FlowinTransitional Regime[C]//ASME 2003 1st InternationalConferenceonMicrochannels and Minichannels.America:American Society of Mechanical Engineers,2003: 405-410.   
[4] WANG Wentan，LIU Zhe，JIN Yong，et al.LBM Simulation of Droplet Formation in Micro-channels[J]. Chemical Engineering Journal,2011,173(3): 828-836.   
[5] GUO Zhaoli, Zhao T S,SHI Yong.A Lattice Boltzmann Algorithm for Eelectro-osmotic Flows in Microfluidic Devices[J]. The Journal of Chemical Physics,2005, 122(14): 144907.   
[6] YUAN Yudong,Rahman S.Extended Application of Lattice Boltzmann Method to Rarefied Gas Flow in Micro-channels[J].Physica A:Statistical Mechanics and its Applications,2016,463:25-36.   
[7] Niu X D, Shu C, Chew Y T,et al. Investigation of Stability and Hydrodynamics of Different Lattice Boltzmann Models[J]. Journal of Statistical Physics,2004,117(3-4): 665-680.   
[8] Gabbanelli S,Drazer G, Koplik J.Lattice Boltzmann MethodforNon-Newtonian(power-law）Fluids[J]. Physical ReviewE,2005,72(4):046312.   
[9] Malaspinas O,Courbebaisse G, Deville M.Simulation of Generalized Newtonian Fluids with the Lattice Boltzmann Method[J]. International Journal of Modern Physics C, 2007,18(12): 1939-1949.   
[10]Boyd J,Buick J,Green S.A second-order accurate lattice Boltzmann non-Newtonian flow model[J]. Journal of physics A: Mathematical and General,2006,39(46): 14241.   
[11] D'Humieres D.Multiple-relaxation-time lattice Boltzmann models in three dimensions[J].Philosophical Transactions of the Royal Society of London A: Mathematical, Physical and Engineering Sciences,2002,360(1792): 437-451.   
[12] CHAI Zhenhua, SHI Baochang,GUO Zhaoli，et al. Multiple-relaxation-time Lattice Boltzmann Model for GeneralizedNewtonianFluid Flows[J].Journalof Non-Newtonian Fluid Mechanics,2011,166(5): 332-342.   
[13]FallahK, KhayatM, BorgheiM H, etal. Multiple-relaxation-time Lattice Boltzmann Simulation of Non-Newtonian Flows Past a Rotating Circular Cylinder[J]. Journal of Non-Newtonian Fluid Mechanics,2012,177: 1-14.   
[14] CHEN Songgui, ZHANG Chuanhu, FENG Yuntian, et al. Three-dimensional Simulations of Bingham Plastic Flows withthe Multiple-relaxation-time Lattice Boltzmann Model[J].Engineering Applications of Computational Fluid Mechanics,2016,10(1): 347-360.   
[15] LI Qiuxiang，HONG Ning, SHI Baochang，et al. Simulation of Power-law fluid Flows in Two-dimensional SquareCavityUsingMulti-relaxation-timeLattice Boltzmann Method[J]. Communications in Computational Physics,2014,15(01): 265-284.   
[16] Mitsoulis E.Flows of Viscoplastic Materials:Models and Computations[J].Rheology Reviews,2007,2007:135-178.   
[17] Papanastasiou T C,Boudouvis A G.Flows of Viscoplastic Materials: Models and Computations[J]. Computers& Structures,1997,64(1): 677-694.   
[18]Alexandrou A N,McGilvreay T M,Burgos G. Steady Herschel-Bulkley Fluid FlowinThree-dimensional Expansions[J]. Journal of Non-Newtonian Fluid Mechanics. 2001,100(1): 77-96.   
[19] Buick JM,Cosgrove JA. Numerical Simulation of the Flow Field in the Mixing Section of a Screw Extruder by the Lattice Boltzmann Model[J]. Chemical Engineering Science,2006,61(10): 3323-3326.   
[20] Mohamad A A.Lattice Boltzmann Method:Fundamentals and Engineering Applications with Computer Codes[M]. Springer Science & Business Media,2011.   
[21] Cruz D O A, Pinho F T. Analysis of Isothermal Flow of a Phan-Thien-Tanner Fluid in a Simplified Model of a Single-screw Extruder[J]. Journal of Non-Newtonian Fluid Mechanics,2012,167: 95-105.   
[22] Kim S J,Kwon T H. Development of Numerical Simulation Methods and Analysis of Extrusion Processes of Particle-filled Plastic Materials Subject to Slip at the Wall[J].Powder Technology,1995,85(3): 227-239.   
[23] Sastrohartono T,Jaluria Y, Esseghir M,etal.A Numerical and Experimental Study of Three-dimensional Transport in the Channel of an Extruder for Polymeric Materials[J]. International Journal of Heat and Mass Transfer, 1995, 38(11): 1957-1973.