# 束团压缩

朱雄伟中国科学院高能物理研究所

# Abstract

本文提出了束团压缩物理的产生背景，束团压缩的基本原理、种类。运用束流光学的基本理论，给出了束团压缩的基本理论公式，论证了束团压缩的高阶限制。分析讨论了单级压缩、两级压缩中存在的设计物理问题，总结了束团压缩设计中经常遇见的一些物理问题。关于束团压缩的束流动力学问题，给出了束团压缩器中的粒子运动方程，以及完整的动力学方程-Vlasov方程。讨论了相干同步辐射效应和微束团不稳定性。最后，分析了磁压缩器中的误差问题。

Keywords:束团压缩，束流光学，加速器

# 1 引言

第四代光源，尤其是基于直线加速器的自由电子激光[1,2]，需要高亮度的超短电子束团，束团长度小于100fs，峰值电流达到几千安培。而在加速器中，各种粒子源由于受到种种物理条件（例如空间电荷效应）的限制，产生的粒子束的束团长度达不到所需要求的束团长度。为了产生所需束团长度的粒子束，我们通常采用束团压缩技术来压缩粒子束团。可以使束团尾部的粒子飞行时间快于头部的粒子，而且飞行时间尽可能短一些。从而产生短的粒子束团。束团压缩通常采用磁压缩技术。图一给出了束团压缩的基本原理示意图。其基本思想是通过射频电压加速产生具有相干能散的粒子束团，而具有能散的束团通过色散线产生路程差，尾部粒子追上头部粒子，从而束团得到压缩。

![](images/f14b78fd15e7b1c91863d6f5fa2ff59be0e17d5058c7e4e157de53fbb60187e4.jpg)  
图1.束团压缩原理图

本文我们讨论束团压缩技术的原理、种类以及一些需要考虑的基本问题。

# 2 束流光学

在加速器束流光学[3,4中，我们假定以参考粒子的坐标为基准，参考粒子的轨迹可以是直线，也可以是环形线，而带电粒子的坐标 $( x , y , z )$ 代表其与参考粒子的坐标差。沿参考线路程为s，位置向量 $X$ 为

$$
X = { \left( \begin{array} { l } { x } \\ { x ^ { \prime } } \\ { y } \\ { y ^ { \prime } } \\ { z } \\ { \delta } \end{array} \right) }
$$

式中'代表d/ds,δ代表分数动量偏差。带电粒子通过磁聚焦元件，磁聚焦元件可以用传输矩阵R表示，其表达式如下

$$
X ( 1 ) = R \cdot X ( 0 ) ,
$$

式中X(0）为带电粒子进入元件时的位置向量， $X ( 1 )$ 为带电粒子离开元件时的位置向量。如果带电粒子通过几个元部件，那么传输矩阵可表达为

$$
R ( t ) = R ( n ) \cdot R ( n - 1 ) . . . R ( 2 ) \cdot R ( 1 ) ,
$$

以上公式可以推广到三阶

$$
X _ { i } ( 1 ) = \sum _ { j } R _ { i j } X _ { j } ( 0 ) + \sum _ { j k } T _ { i j k } X _ { j } ( 0 ) X _ { k } ( 0 ) + \sum _ { j k l } U _ { i j k l } X _ { j } ( 0 ) X _ { k } ( 0 ) X _ { l } ( 0 )
$$

式中 $R$ ， $T$ ， $U$ 为一阶，二阶，三阶传输矩阵，常用的元素有 $R _ { 1 6 } , R _ { 2 6 } , R _ { 5 6 } , T _ { 5 6 6 } , U _ { 5 6 6 } { \frac { 5 } { \cdot } }$ 拿

# 3 束团压缩的原理与种类

磁压缩器[5,6]广泛应用在自由电子激光装置与正负电子对撞机中。在线性理论中，位置、能散的依赖关系为

$$
\begin{array} { r } { z = z _ { 0 } + R _ { 5 6 } \cdot \delta , } \\ { \delta = \delta _ { 0 } + a \cdot z _ { 0 } . } \end{array}
$$

式中 $R _ { 5 6 }$ 为一阶动量压缩因子, $\delta$ 为动量偏差或相对能散. $a$ 为一阶能散位置相干因子.假定无关的初始束团分布， $< z > = 0$ 。压缩前后束团长度的关系为

$$
\begin{array} { r } { \sigma _ { z } \approx \mid 1 + a \cdot R _ { 5 6 } \mid \sigma _ { z _ { 0 } } } \\ { \sigma _ { \delta } = \mid a \mid \cdot \sigma _ { z _ { 0 } } } \end{array}
$$

考虑二阶非线性，位置、能散的依赖关系为

$$
\begin{array} { r } { z = z _ { 0 } + R _ { 5 6 } \delta + T _ { 5 6 6 } \delta ^ { 2 } } \\ { \delta = \delta _ { 0 } + a z _ { 0 } + b z _ { 0 } ^ { 2 } } \end{array}
$$

式中 $T _ { 5 6 6 }$ 为二阶动量压缩因子， $b$ 为二阶位置能散相干因子。二阶束团长度压缩关系很复杂，

$$
\sigma _ { z } ^ { 2 } = ( 1 + a R _ { 5 6 } ) ^ { 2 } \sigma _ { z _ { 0 } } ^ { 2 } + \frac { 9 } { 5 } ( ( b - \frac { a ^ { 2 } } { 2 } ) ^ { 2 } + R _ { 5 6 } ^ { 2 } - 6 a b ( 1 + a R _ { 5 6 } ) R _ { 5 6 } ) \sigma _ { z _ { 0 } } ^ { 4 } .
$$

由上式可以看到，在线形理论中，当 $1 + a R _ { 5 6 } = 0$ 时，压缩最强烈。但是存在高阶项的压缩限制。高阶效应限制了束团压缩效果，从而达不到理想的一阶压缩效果，均匀分布的束团更容易得到压缩，

压缩器的种类主要有C型、S型，另外还有不常见的扭摆器型和弧区型。我们常用的chicane由四块相同的二极铁所组成，如下图

![](images/bc1f79986e55739d388d650cb58d03cf6ba8e7e2f4bb4ab6b4fe9d5d9f1999f0.jpg)  
图2.束团压缩器

二极铁长度为 $L _ { B }$ ，第一块二极铁与第二块二极铁之间的距离为 $\Delta L$ ，第二块二极铁与第三块二极铁之间的距离为 $\Delta L _ { C }$ .chicane加速器束线引入了路程差，纵向路程差可表达如下

$$
\Delta z = R _ { 5 6 } \delta + T _ { 5 6 6 } \delta ^ { 2 } + U _ { 5 6 6 6 } \delta ^ { 3 } + \ldots
$$

假定二极铁的偏转角为 $\theta _ { 0 }$ ，chicane引入的路程差为

$$
\Delta s \approx \theta _ { 0 } ^ { 2 } ( \Delta L + \frac { 2 } { 3 } L _ { B } )
$$

能散δ的带电粒子通过二极铁时的偏转角可表达为

$$
\theta ^ { 2 } = \theta _ { 0 } ^ { 2 } / ( 1 + \delta ) ^ { 2 }
$$

进行泰勒展开为

$$
\theta ^ { 2 } = \theta _ { 0 } ^ { 2 } ( 1 - 2 \delta + 3 \delta ^ { 2 } - 4 \delta ^ { 3 } + . . . )
$$

从而一阶动量压缩因子为

$$
{ \cal R } _ { 5 6 } \approx - 2 \theta _ { 0 } ^ { 2 } ( \Delta L + \frac { 2 } { 3 } L _ { B } ) .
$$

二阶、三阶压缩因子分别为 $\begin{array} { r } { T _ { 5 6 6 } = - \frac { 3 } { 2 } R _ { 5 6 } , U _ { 5 6 6 6 } \simeq 2 R _ { 5 6 } } \end{array}$ 1

# 4 束团压缩的一些设计考虑

束团压缩的设计需要在整个加速器设计中进行考虑[7,8,9]，因为束团压缩与射频加速密切相关。在直线加速器设计中，我们需要匹配全部的lattice 结构，主要是优化β函数，β函数尽可能小。由于压缩器主要有二极铁所组成，所以也要优化色散函数，一般只考虑一阶色散函数。

为了获得波荡器所需要的高峰值电流、小能散的电子束团，束团须由磁压缩器完成压缩,即在直线加速器中引入由四块二极铁组成的磁压缩器(chicane)，磁压缩器的位置与空间安排使得在压缩和加速过程中由纵向尾场、RF曲率、二阶动量压缩等引起的非线性大部抵消掉，经最后一级压缩后的相关能散须由纵向尾场补偿和RF补偿抵消掉，磁压缩器的设计应减轻相干、非相干同步辐射引起的发射度增长。在磁压缩器中粒子所走路径依赖于粒子能量从而使得束团得到压缩.经压缩后束团rms长度、rms能散与初始rms长度、rms能散的关系为

$$
\sigma _ { z } = \sqrt { ( 1 + k \cdot R _ { 5 6 } ) ^ { 2 } + R _ { 5 6 } ^ { 2 } \cdot \sigma _ { \delta } ^ { 2 } } \approx | 1 + k \cdot R _ { 5 6 } | \sigma _ { z } ,
$$

$$
\begin{array} { r } { \sigma _ { \delta } = \sqrt { k ^ { 2 } \sigma _ { z } ^ { 2 } + \sigma _ { \delta } ^ { 2 } } \approx | k | \sigma _ { z } , } \end{array}
$$

$$
k ( \varphi _ { 0 } , \triangle \varphi ) = - \frac { 2 \pi } { \lambda } ( 1 - \frac { E _ { i 0 } } { E _ { f 0 } } ) \frac { \sin ( \varphi _ { 0 } + \triangle \varphi ) } { \cos ( \varphi _ { 0 } ) } .
$$

式中 $\lambda$ 为射频波波长, $\varphi _ { 0 }$ 为加速相位误差, $E _ { i 0 } , E _ { f 0 }$ 为束团中心在加速段入口,出口处的能量.在压缩器中由非相干同步辐射(ISR)所引起的归一化发射度增长为

$$
\triangle \gamma \varepsilon _ { x } = 8 . 0 \times 1 0 ^ { - 8 } E ^ { 6 } ( \triangle L + L _ { B } + \frac { \beta _ { m a x } + \beta _ { m i n } } { 3 } ) ,
$$

$\beta _ { m a x } , \beta _ { m i n }$ 为最大、最小 $\beta$ 函数．ISR主要作用在高能情形．在chicane中由相干同步辐射(CSR)所引起的发射度增长为

$$
\frac { \triangle \varepsilon } { \varepsilon } \propto \frac { r _ { e } ^ { 2 } N ^ { 2 } } { \varepsilon _ { N } \gamma } ( \frac { \theta ^ { 1 0 } L _ { B } ^ { 5 } } { \sigma _ { z } ^ { 8 } } ) ^ { \frac { 1 } { 3 } } ,
$$

式中 $r _ { e }$ 为电子经典半径, $\varepsilon _ { N }$ 为归一化发射度, $N$ 为束团中电子数．对于单级束团压缩,压缩后束团长度变化对相位误差过于敏感．另外，单级束团压缩也受空间位置、非线性限制.而且须保持束流传输的发射度和能散。所以压缩难以由单级束团压缩一次完成。压缩由二级磁压缩器完成，二级磁压缩系统能降低压缩对相位抖动的敏感性一个数量级。对于二级磁压缩系统，束团经过第一节直线加速器,能量从 $E _ { 0 }$ 加速到 $E _ { 1 }$ （加速相位 $\varphi _ { 1 }$ ，第一级磁压缩器动量压缩因子 $R _ { 5 6 } = \alpha _ { 1 }$ ，经过第二节直线加速器束团能量从E1加速到 $E _ { 2 }$ （加速相位 $\varphi _ { 2 }$ )，第二级磁压缩器动量压缩因子 $R _ { 5 6 } = \alpha _ { 2 }$ ，经过两级压缩后束团长度、能散与初始束团长度、能散之间的关系近似为

$$
\begin{array} { r } { \tau _ { z _ { 2 } } = \sqrt { ( ( 1 + \alpha _ { 1 } k _ { 1 } ) ( 1 + \alpha _ { 2 } k _ { 2 } ) + \alpha _ { 2 } k _ { 1 } E _ { 1 } / E _ { 2 } ) ^ { 2 } \sigma _ { z _ { 0 } } ^ { 2 } + ( \alpha _ { 1 } ( 1 + \alpha _ { 2 } k _ { 2 } ) E _ { 0 } / E _ { 1 } + \alpha _ { 2 } E _ { 0 } / E _ { 2 } ) ^ { 2 } } . } \end{array}
$$

$$
\sigma _ { \delta _ { 2 } } = \sqrt { ( k _ { 2 } ( 1 + \alpha _ { 1 } k _ { 1 } ) ^ { 2 } + k _ { 1 } E _ { 1 } / E _ { 2 } ) ^ { 2 } \sigma _ { z _ { 0 } } ^ { 2 } + ( \alpha _ { 1 } k _ { 2 } E _ { 0 } / E _ { 1 } + E _ { 0 } / E _ { 2 } ) ^ { 2 } \sigma _ { \delta _ { 0 } } ^ { 2 } } .
$$

式中 $k _ { 1 }$ 是第一节直线加速器始末能量、加速相位的函数，与单节单级束团压缩系统相同， $k _ { 2 }$ 为

$$
k _ { 2 } = - \frac { 2 \pi } { \lambda } ( 1 - \frac { E _ { 1 } } { E _ { 2 } } ) \frac { \sin ( \varphi _ { 2 } + ( 1 + \alpha _ { 1 } k _ { 1 } ) \triangle \varphi _ { 1 } + \triangle \varphi _ { 2 } ) } { \cos \varphi _ { 2 } } ,
$$

△φ1,△φ2为第一、第二节加速器的相位抖动.运用以上线性关系可以简单地寻找磁压缩器的设计参数.

总之，束团压缩所需要考虑的一些物理问题可总结如下：

1.压缩器的种类选择（C型、S型、扭摆器型、弧型）。  
2.线性化问题。  
3.束团抖动效应。  
4.加速相位选择与加速效率。  
5.纵向、横向尾场影响与优化问题。  
6.能散限制。  
7.相干同步辐射效应及其影响。  
8.压缩器的成本问题等。

# 5 束团压缩中的束流动力学

磁压缩器中的束流动力学[10,11]和输运线中的束流动力学一样。横向运动方程依然由Hill方程所描述，纵向运动可由本文的束团压缩的基本原理简单描述就可以了。不过，在磁压缩其中纵向、横向耦合很强，我们需要考虑横向、纵向的耦合方程，不能分别独立描述。假定此压缩器中磁场方向在 $y$ 方向，那么电子在 $( x , z )$ 平面内运动，电子在 $( x , z )$ 平面内的运动方程为

$$
\begin{array} { r l r } & { } & { \displaystyle \frac { d x } { d s } = \theta } \\ & { } & { \displaystyle \frac { d \theta } { d s } = - k _ { \beta } ( s ) ^ { 2 } x + \frac { p } { R ( s ) } } \\ & { } & { \displaystyle \frac { d z } { d s } = - \frac { x } { R ( s ) } } \\ & { } & { \displaystyle \frac { d p } { d s } = 0 } \end{array}
$$

式中 $R ( s )$ 为二极铁中的弯转半径， $k _ { \beta } ( s )$ 为聚焦强度， $p = \Delta E / E$ 为相对能散。假定电子束团的分布函数为 $\rho ( x , \theta , z , p , s )$ ，分布函数 $\rho$ 可线性展开到一阶 $\rho = \rho _ { 0 } + \rho _ { 1 }$ ，其中 $\rho _ { 0 }$ 为不考虑相干同步辐射效应（CSR）时的分布函数， $\rho _ { 1 }$ 为考虑CSR效应时的线性化展开小量。将VLASOV方程线性化，可以求得线性化VLASOV方程为

$$
\frac { \partial \rho _ { 1 } } { \partial s } - \frac { x } { R } \frac { \partial \rho _ { 1 } } { \partial z } + \theta \frac { \partial \rho _ { 1 } } { \partial x } + ( - k _ { \beta } ( s ) ^ { 2 } x + \frac { p } { R ( s ) } ) \frac { \partial \rho _ { 1 } } { \partial \theta } = \frac { r _ { e } } { \gamma } \frac { \partial \rho _ { 0 } } { \partial p } \int d z ^ { \prime } W ( z - z ^ { \prime } , s ) n _ { 1 } ( z ^ { \prime } , s ) \rho _ { 1 } .
$$

式中 $\begin{array} { r } { n _ { 1 } ( z , s ) = \int d x d \theta d p \rho _ { 1 } } \end{array}$ ： $W ( z , s )$ 为束团的CSR尾场函数。以上方程组为磁压缩器中完整的束流动力学描述。它们是非常复杂的方程组，需要做详细的模拟仿真分析，或者说数字实验。数字实验无疑已成为物理学的一个重要发展方向。

考虑CSR效应，在经典电动力学中，运动的电子束团产生的辐射可由单个运动电子产生的辐射推广为

$$
\frac { d ^ { 2 } I } { d \omega d \Omega } = ( N + N ( N - 1 ) f ( \omega ) ) \cdot \int _ { - \infty } ^ { \infty } \hat { n } \times ( \beta \times \hat { n } ) e x p ( i \omega ( t - \hat { n } \cdot r ( t ) ) / c )
$$

式中 $f ( \omega )$ 为形状因子，N 为束团中的粒子数。上式中第二项来自于纵向的时间相干性。如果没有第二项，电子束团的辐射功率为单个电子辐射功率的简单和。当束团长度与电磁波波长相当时，第二项非常大，远远大于第一项，电子束团的辐射功率得到了远远的提高。这种现象被称为相干同步辐射效应。电子束团的CSR阻抗为

$$
Z ( k , s ) = \int _ { 0 } ^ { \infty } d \zeta W ( \zeta , s ) e x p ( - i k \zeta ) = - \frac { i k ^ { 1 / 3 } A } { R ^ { 2 / 3 } } ,
$$

其中A= 1.63i－ 0.94.

微束团不稳定性（microbunching instability）类似于速调管中的群聚不稳定性，或者叫微波不稳定性。微束团不稳定性它是由于电子束团中电子的路程差不同引起的纵向群聚不稳定性。在束团压缩器中，群聚不稳定性是由色差效应引起的，是由能散引起的纵向路程差引起的，也就是由磁铁的动量压缩因子（线性、非线性）所引起。而在速调管中它是由射频加速电压曲线所引起的。微束团不稳定性会引起能量调制放大和发射度的增长，从而使束流品质变坏。我们在文中[12,13,14]分析计算了束团压缩器chicane、Wiggler扭摆器中的微束团不稳定性。

# 6 磁压缩器的误差分析

全面来说，压缩过程由加速部分和磁压缩器部分共同组成。因此磁压缩器的误差分析包括加速部分与此压缩器部分。加速部分的误差由相位和振幅的误差，也就是相位与振幅的抖动效应。电子在RF场中加速，可见下图

![](images/9068ec3440a1f3ce7e4f6b98a7a973480cd5100799991e781cab6225893b26ff.jpg)  
图3.RF加速

上图中 $e V _ { 0 }$ 为加速电压， $\varphi$ 为束团中心的加速相位。那么电子的加速为 $E ( z ) = E _ { 0 } +$ $e V _ { 0 } \cos ( \varphi + 2 \pi z / \lambda )$ ，而束团长度抖动可近似为

$$
\frac { \Delta \sigma _ { z } } { \sigma _ { z } } \approx - ( \frac { \sigma _ { z _ { 0 } } } { \sigma _ { z } } \mp 1 ) \Delta \varphi \cot \varphi
$$

文献中我们分析了加速部分的误差效应，相位与振幅的抖动都有相应的限制。

对于磁铁误差，在水平面内偏转的二极铁的垂直分量[15]为

$$
B _ { y } ( x , 0 ) = \sum _ { n = 0 } ^ { \infty } B _ { n } \frac { x ^ { n } } { n ! } = B _ { 0 } \rho \sum _ { n = 0 } ^ { \infty } K _ { n } \frac { x ^ { n } } { n ! } = \sum _ { n = 0 } ^ { \infty } b _ { n } \frac { x ^ { n } } { a ^ { n } } ,
$$

式中 $B _ { 0 } \rho$ 为磁刚度， $a$ 为参考展开半径，MAD 中 $K _ { n }$ 定义为

$$
K _ { n } = \frac { B _ { n } } { B _ { 0 } \rho } = \frac { 1 } { B _ { 0 } \rho } \frac { n ! } { a ^ { n } } b _ { n } .
$$

$b _ { 0 }$ 为二极场分量， $b _ { 1 }$ 为四极场分量， $b _ { 2 }$ 为六极场分量。高阶场分量由磁铁误差产生。对于四极铁分量的误差限制为

$$
| \frac { b _ { 1 } } { b _ { 0 } } | < \frac { r _ { 0 } \sqrt { 2 \Delta \varepsilon } } { | \theta _ { 0 } \eta | \sigma _ { \delta } \sqrt { \beta } } , \
$$

式中 $r _ { 0 }$ 场展开的半径， $\Delta \varepsilon$ 为误差引起的发射度增长， $\eta , \beta$ 为色散函数，振荡振幅函数。类似的，六极铁分量误差限制估为

$$
| \frac { b _ { 2 } } { b _ { 0 } } | < \frac { r _ { 0 } ^ { 2 } \sqrt { 2 \Delta \varepsilon } } { | \theta _ { 0 } | \eta ^ { 2 } \sigma _ { \delta } ^ { 2 } \sqrt { \beta } } .
$$

在[16]中我们分析了磁器压缩的误差。在C型磁压缩器中，中间两块磁铁处色散函数最大，因此误差最紧。但对于倾角误差最后一块磁铁的误差最紧。图二给出了磁压缩器的典型Twiss参数图。

![](images/a88e941cebd3384ca5b94defc632dafe89cefcd6c857b94ac01b0966593b826e.jpg)  
图4.典型Twiss参数图

# 7 讨论

本文主要讨论了束团的磁压缩。另外，还有RF速度压缩和 $\alpha$ 磁铁压缩。速度压缩的压缩强度有限，适用于电子束产生的低能情形。 $\alpha$ 磁铁压缩一般用于常规直流电子枪，压缩强度同样有限。而在高亮度电子束情况，通常采用磁压缩。我们提出了束团压缩物理的产生背景与机制，束团磁压缩的基本方法和原理，磁压缩主要有C型（chicane）、S型（双chicane）、扭摆器型、四个FODO弧区型等种类。运用束流光学的基本理论，给出了束团压缩的基本理论公式，论证了束团压缩的高阶限制，给出了展开到二阶的束团长度公式。分析讨论了单级压缩、两级压缩中存在的设计物理问题，总结了束团压缩设计中经常遇见的一些物理问题。关于束团压缩的束流动力学问题，给出了束团压缩器中的粒子运动方程，以及完整的动力学方程-Vlasov方程。讨论了相干同步辐射效应和微束团不稳定性。最后，分析了磁压缩器中的误差问题，加速阶段的相位抖动与二极铁磁铁的误差限。

# References

[1] K.J.Kim, Zhirong Huang, Introduction to the Physics of Free Electron lasers, Lecture note,2003.   
[2] E.L.Saldin, E.A.Schneidmiller, The Physics of Free Eletron lasers, Springer, 2000.   
[3] M.Reiser, Theory and Design of Charged Particle Beams, John Wiley and Sons, Inc., 1994.   
[4] D.C.Carey, K.L.Brown, F.Rothacker, Third-order Transport, a computer program for designing charged particle beam transport systems, Fermilab-Pub-95/069,1995.   
[5] I.S.Ko, ICFA Beam Dynamics Newsletter, No.38, 2005.   
[6] 朱雄伟，束团磁压缩的高阶限制，高能物理与核物理，31，1，88，2007.   
[7] LCLS CDR, SLAC Report No.SLAC-R-593, 2002.   
[8] 朱雄伟，裴国玺，池云龙，戴建枰，陈森玉，杜应超，何小中，黄文会，林郁正， 唐传祥，BTF 加速器物理设计，高能物理与核物理，30，Sup.,126,2006.   
[9] Xiongwei Zhu, et.al.， Layout of Bunch Compressor for Beijing XFEL Test Facility, NIM A, 566, 250,2006.   
[10] S.Heifets, G.Stupakov, Phys.Rev.ST-AB, 5, 064401, 2002.   
[11] S.Heifets, G.Stupakov, SLAC-PUB-8988, 2001.   
[12] Yang Yu-Feng, Zhu Xiong-Wei, Microbunch Instability in Beijing XFEL Test Facility Bunch Compressor, High Energy Physics and Nuclear Physics,31, 2, 194, 2007.   
[13]_ Yang Yu-Feng, Zhu_Xiong-Wei， Microbunch Instability in Wigglers,High Energy Physics and Nuclear Physics, 31, 8, 778, 2007.   
[14] Zhu Xiong-Wei, Gao Jie, Study on ILC Bunch compressor, Chinese Physics C, 32, 11, 928,2008.

[15] H.Grote, F.C.Iselin, The MAD program, User's Reference Manual,1996.

[16] 朱雄伟，CTF磁压缩器的误差分析，Chinese Physics C,32,suppl.,218,2008.

# Bunch Compression

Zhu Xiong-Wei Institue of High Energy Physics, Chinese Academy of Sciences

# Abstract

In this paper,we discuss the physical background for bunch compression, the basic principle of bunch compression, and the kinds of bunch compressing. Using the fundamental theory of beam optics,one gives the basic formula of bunch compressing，proves the high order limiting terms. We analyse and discuss the design physics for single bunch compressor and two bunch compressor design for the high brightness electron linac,and summarize some physics problems in the design of linac including beam bunch compressing. As for the beam dynamics existing in the bunch compressor, we give the kinetic equations for bunch compressing taking into account of CSR effect and microbunching instability. Finally, we discuss the error problem for bunch compressor.

Keywords:bunch compression，beam optics，accelerator