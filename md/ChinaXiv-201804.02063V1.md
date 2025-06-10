# 基于飞蛾火焰优化算法的PMSM分数 ${ \mathsf { P l } } ^ { \lambda }$ 阶研究

张学典，孙俊峰，，秦晓飞(上海理工大学 光电信息与计算机工程学院，上海 200093)

摘要：针对PMSM(永磁同步电机)分数阶PP控制器的参数整定，提出了一种频域法和飞蛾火焰优化算法相结合的方法。以永磁同步电机的分数阶模型作为被控对象。首先使用频域法，根据系统的相对稳定性和增益变化的鲁棒性等条件得到控制器的方程；然后结合该方程的图像求解出分数阶 PP控制器的参数，以该参数为中心位置，指定寻优的范围，进而用火焰优化算法对其周围进行寻优。仿真和实验结果表明，该分数阶PI控制器能够降低系统的超调量，提高系统的快速跟踪能力和抗干扰能力，具有较强的鲁棒性。

关键词：永磁同步电机；PI控制器；参数整定；频域法；飞蛾火焰算法 中图分类号：TP273.2 doi: 10.3969/j.issn.1001-3695.2017.11.0740

Research of fractional order $\mathrm { P I } ^ { \lambda }$ for PMSM based on moths fire optimization algorithm

Zhang Xuedian†, Sun Junfeng, Qin Xiaofei (SchoolofOptical-Electrical&ComputerEngineeing,UniversityofShanghaiforcience&Technologyhanghai20093, China)

Abstract: Aiming at parameter tuning of fractional order $\mathrm { P I } ^ { \lambda }$ controller of PMSM, the author proposes a method,which combines the frequency-domain methodand moths fireoptimizationalgorithm.This paperusedthe fractional order modelof PMSMasthecontrolledobject.Firstly,itusedthefrequency-domainmethod,theitobtainedtheequationof thecontroller according totherelativestabilityofthesystemandtherobustnessof thegain variation.After that,it solved theparametersof fractional order $\mathrm { P I } ^ { \lambda }$ controller by combining the image of the equation and optimized these parameters by using moths fire optimizationalgorithm.Thesimulationand experimentresultsshowthatthefractional ordercontrolercanreduce theovershoot ofthesystem,improve therapidityandanti-interference abilityofthesystem,andhasacertaindegre ofrobustess.

Key words: permanent magnet synchronous motor; $\mathrm { P I } ^ { \lambda }$ controller;parameters tuning; frequency-domain method; moths fire algorithm

# 0 引言

永磁同步电机已经广泛得应用到了人们生活的各个领域。随着我国“中国制造2025”制造业强国战略的提出，像数控机床、机器人等领域都需要电机能够被精确的控制，而永磁同步电机因其优异的性能被应用到了这些领域作为运动控制的关键部件[1,2]。但是受电机参数变化、负载扰动等不确定因素的影响，控制系统的动态响应和抗干扰能力仍然不能满足现代工业控制的要求。因此，如何保证系统具有良好的动静态响应性能和较强的鲁棒性，一直是永磁同步电机控制界研究的热点[3]。随着现代控制理论的不断发展，许多先进的控制方法被提出，特别是分数阶理论的出现，分数阶控制器是借用整数阶逼近的方式在计算机中实现[4,5]，因此很多学者对其进行了研究，Oustaloup等人采用Outaloup递推滤波器近似，开发了CRONE控制器，并且证明了CRONE 控制器比传统的整数阶PID控制器具有很大的优势[]。Matignon等人针对分数阶系统的稳定性和可控制性等方面进行了研究[7]。1994年，Podlubny在研究分数阶控制系统基础上提出了分数阶 $\mathrm { P I } ^ { \lambda } \mathbf { D } ^ { \mu }$ 控制器[8]。

近年来分数阶 $\mathrm { P I } ^ { \lambda } \mathrm { D } ^ { \mu }$ 控制器得到了许多学者的关注，胡海波等人[9结合细菌觅食算法、粒子群算法对分数阶PID控制器进行了设计，提高了传统粒子群算法的计算效率，同时得到的分数阶PID控制器比整数阶控制器具有更好的动态特性。吴振宇等人[10]把分数阶PID应用到了智能车控制，最后证明分数阶PID控制器具有比传统PID控制器更好的动态性能和更强的鲁棒性。秦昌茂等人[1利用自抗扰分数阶PID控制方法，研究了高超声速飞行条件下的飞行器再入滑翔段制导轨迹跟踪，表明了分数阶PID具有更强的鲁棒性。Altintas 等人[12]结合遗传算法和分数阶PID优化了磁悬浮系统控制器的参数，通过分析验证了FOPID具有更好的灵活性，使系统具有很好的动态响应特性[12]。

本文是在频域法的基础上，应用飞蛾火焰[13,14]优化算法对分数阶 $\mathbf { P I } ^ { \mathrm { \lambda } }$ 控制器三个参数进行优化。 $\mathrm { P I } ^ { \lambda }$ 控制器的典型公式如式(1)所示。

$$
\mathbf { C } ( s ) = K _ { p } ( 1 + \frac { k _ { i } } { s ^ { \lambda } } )
$$

其中： $k _ { p } , k _ { i }$ 是分数阶比例和积分参数； $\lambda$ 为分数阶阶次。

飞蛾火焰优化算法[5是2015年Mirjalili等人提出的一种新型仿生群体智能算法，与其他的智能优化算法相比，它具有搜索速度较快、调节参数少、收敛精度高和鲁棒性能好等特点，其中不易陷入局部最优是它最主要的优点。

本文主要介绍了在满足系统动态响应性能、稳定性和增益鲁棒性的基础上，利用频域法获得控制器的公式，并作图求出了相应控制器参数；分析了飞蛾火焰优化算法的特点和数学模型，详细阐述了使用该算法优化的步骤；进行仿真检验，对比和分析了两种方法得出的结果。最后，为了增加实验结果的可信度，对优化后的控制器进行方波和正弦波速度信号跟踪仿真。

# 1 频域法获得控制器

相对于整数阶PI控制器，分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器多了一个可调参数λ，能在更大范围内调节控制器的性能。近年来许多学者利用分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器对一阶和二阶被控系统进行研究，但是现实生活中的被控系统实际上就是一个分数阶模型，所以摒弃传统的整数阶被控系统，采用分数阶被控系统更为合理。其模型为

$$
\operatorname { P } ( s ) = { \frac { K } { s ^ { \xi } ( T s + 1 ) } }
$$

被控系统的幅值和相位分别如式(3)(4)所示。

$$
| \operatorname { P } ( j \omega ) | = { \frac { K } { T { \sqrt { A ( \omega ) ^ { 2 } + B ( \omega ) ^ { 2 } } } } }
$$

$$
A r g [ \mathrm { P } ( j \omega ) ] = \arctan \left( - \frac { B ( \omega ) } { A ( \omega ) } \right)
$$

其中：

$$
A ( \omega ) = \omega ^ { \zeta + 1 } \cos \left( \frac { \pi } { 2 } ( \zeta + 1 ) \right) + \frac { 1 } { T } \omega ^ { \zeta } \cos \left( \frac { \pi } { 2 } \zeta \right)
$$

$$
B ( \omega ) = \omega ^ { \zeta + 1 } \sin \left( \frac { \pi } { 2 } ( \zeta + 1 ) \right) + \frac { 1 } { T } \omega ^ { \zeta } \sin \left( \frac { \pi } { 2 } \zeta \right)
$$

对于分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器式子式(1)的幅值和相位如下所示：

$$
\mid C ( j \omega ) \mid = K _ { p } \sqrt { P ( \omega ) ^ { 2 } + Q ( \omega ) ^ { 2 } }
$$

$$
A r g [ C ( j \omega ) ] = \arctan \left( - \frac { Q ( \omega ) } { P ( \omega ) } \right)
$$

其中：

$$
P ( \omega ) = 1 + K _ { i } \omega ^ { - \lambda } \cos \left( \frac { \pi } { 2 } \lambda \right)
$$

$$
Q ( \omega ) = K _ { i } \omega ^ { - \lambda } \sin \left( \frac { \pi } { 2 } \lambda \right)
$$

分数阶 $\mathbf { P } \mathbf { I } ^ { \lambda }$ 控制器的设计要考虑动态响应性能、稳定性和增益鲁棒性的要求[15\~18]。这里一般是基于以下三个指标来实现的：

a)增益穿越频率指标。根据系统的相频特性和幅频特性， 在增益穿越频率点 $\omega _ { c }$ 处，开环传递函数的幅值满足

$$
\big | C ( \mathrm { j } \omega _ { c } ) \mathrm { P } ( \mathrm { j } \omega _ { c } ) \big | = 1
$$

b)相位裕度指标。为了保证系统的稳定性，在增益截止频率点下的相位裕度 $\varphi _ { m }$ ，其满足

$$
A r g [ \mathbf { C } ( \mathrm { j } \omega _ { c } ) \mathbf { P } ( \mathrm { j } \omega _ { c } ) ] = - \boldsymbol { \pi } + \varphi _ { m }
$$

c)增益扰动鲁棒性指标。在增益截止频率 $\omega _ { c }$ 处，系统的相频特性曲线的导数是0。此时意味着系统对外界的干扰具有较强的鲁棒性，具体的表达式如(13)所示。

$$
[ \frac { d [ \mathrm { A r g } [ \mathrm { C ( j } \omega ) \mathrm { P ( j } \omega ) ] ] } { d \omega } ] _ { \omega = \omega _ { c } } = 0
$$

当给定了系统的开环增益穿越频率 $\omega _ { c }$ 、相位角裕度 $\varphi _ { { } _ { m } }$ 、控 制器阶次λ，由增益鲁棒性指标可得

$$
\left. \frac { d [ A r g ( C ( j \omega ) ) ] } { d \omega } \right| _ { \omega = \omega _ { c } } + \left. \frac { d [ A r g ( P ( j \omega ) ) ] } { d \omega } \right| _ { \omega = \omega _ { c } } = 0
$$

引入变量

$$
\left. M = \frac { d [ A r g ( P ( j \omega ) ) ] } { d \omega } \right| _ { \omega = \omega _ { c } }
$$

把 $\mathbf { M }$ 和式(8)带入式(14)中可得

$$
\frac { - \lambda K _ { i } \sin \Biggl ( \frac { \pi } { 2 } \lambda \Biggr ) \omega _ { c } ^ { - \lambda - 1 } } { \omega _ { c } ^ { - 2 \lambda } K _ { i } ^ { 2 } + 2 \omega _ { c } ^ { - \lambda } K _ { i } \cos \Biggl ( \frac { \pi } { 2 } \lambda \Biggr ) + 1 } + M = 0
$$

引入变量 $N = 2 M \omega _ { c } ^ { - \lambda } \cos \left( \frac { \pi } { 2 } \lambda \right) - \lambda \sin \left( \frac { \pi } { 2 } \lambda \right) \omega _ { c } ^ { - \lambda - 1 }$

把 $\mathrm { ~ N ~ }$ 带入式(15)中可解得

$$
K _ { i } = \frac { - N \pm \sqrt { N ^ { 2 } - 4 M ^ { 2 } \omega _ { c } ^ { - 2 \lambda } } } { 2 M \omega _ { c } ^ { - 2 \lambda } }
$$

把 $\omega _ { c }$ 、、 $K _ { i }$ 带入式(11)可以解得

$$
K _ { _ { P } } = \frac { T \sqrt { A ( \omega _ { c } ) ^ { 2 } + B ( \omega _ { c } ) ^ { 2 } } } { K \sqrt { P ( \omega _ { c } ) ^ { 2 } + Q ( \omega _ { c } ) ^ { 2 } } }
$$

本文采用的被控对象是PMSM，具体的电机参数如表1所示。利用上述的电机参数，采用数值拟合的方法对其电磁环和机械环进行分数阶系统时域参数辨识，可以求得被控对象的分数阶模型为

$$
G ( s ) = \frac { 6 1 9 6 . 6 9 } { s ^ { 1 . 9 5 5 } + 3 2 5 . 2 9 s ^ { 1 . 0 4 8 } + 3 9 7 4 . 6 6 }
$$

由式(18)可以得到被控对象的截止频率 ${ \omega _ { c } } { = } 1 2 \ \mathrm { r a d / s }$ ，相位

角裕度 $\varphi _ { m } = 9 0 ^ { \circ }$ ，时间常数 $r { = } 0 . 8 ~ \mathrm { s }$ 。

分别画出式(14)(15)的图形。 $k _ { i }$ 关于 $\lambda$ 的函数图像，如图1所示。

表1永磁同步电机的参数  

<html><body><table><tr><td>电机参数</td><td>参数值</td></tr><tr><td>额定转速n/(r/min)</td><td>2500</td></tr><tr><td>定子电阻R/Ω</td><td>3.987</td></tr><tr><td>定子dq轴电感L/H</td><td>0.0088</td></tr><tr><td>转动惯量J/(kg*m²)</td><td>0.0075</td></tr><tr><td>励磁磁通Wb</td><td>0.175</td></tr><tr><td>极对数p</td><td>1</td></tr></table></body></html>

![](images/ec4e532528bcf2c71f525b808e50269af5427f04f54991e5b3820d7e52cc8440.jpg)  
频域法获得控制器参数图

图中红线是式(14)的波形图，蓝线是式(15)的波形图，它们的交点为所求的参数，则 $( \lambda , k _ { i }$ )的值为(0.857,12.22)，带入式(17)可以得到 $k _ { p } = 3 . 6 7 2$ ，进而得到分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器为

$$
\begin{array} { r } { C ( \mathrm { s } ) = 3 . 6 7 2 ( 1 + \frac { 1 2 . 2 2 } { s ^ { 0 . 8 5 7 } } ) } \end{array}
$$

利用系统被控的分数阶模型式(18)和频域法得到的 $\mathbf { P I } ^ { \lambda }$ 控制器式(19)，可以得到系统的闭环传递函数，对其闭环传递函数进行阶跃仿真，则可以得到系统的阶跃响应波形，如图2所示。

![](images/729732f96ee05f6dc24916473e589d6cb1895c167cf3c6708b87a32ff3f1fa27.jpg)  
图1频域法获得控制器的曲线图  
图2频域法得到的系统阶跃响应波形

从图2的阶跃响应波形可以得到，上升的时间 $t _ { r } = 0 . 1 2 ~ \mathrm { s }$ ，调节的时间大约为 $t _ { s } = 0 . 6 ~ \mathrm { s }$ ，超调量为 $4 . 7 6 \%$ 。虽然此时得到的分数阶控制器可以确保特定的增益穿越频率、相位裕度和不错的增益扰动鲁棒性，但是仍不能使控制系统达到最佳的阶跃响应跟随性能。

因此分数阶控制器设计就转换成了如何得到最优的增益截止频率 $\omega _ { \mathrm { c } }$ 和分数阶阶次λ的问题。飞蛾火焰优化算法被用来搜索最优的增益穿越频率 $\omega _ { \mathrm { c } }$ 和分数阶次λ。将每一次得到的$( \omega _ { c } , \varphi _ { m } )$ 代入公式求得分数阶速度控制器，并在MATLAB中进行阶跃响应仿真。同时时间乘误差平方积分(ITAE)被计算来估计控制器的性能。通过飞蛾火焰优化算法的迭代计算，当ITAE值最小时，得到的分数阶控制器是最佳的。

# 2 飞蛾火焰优化算法(MFO)

# 2.1飞蛾火焰优化算法的特点

不同结构的控制器，参数优化的方法也有所不同。为了使优化过程不易陷入局部最优，并提高优化效率，本文利用飞蛾火焰优化算法来优化分数阶控制器，该算法是受飞蛾定位导航机制的启发，通过飞蛾火焰螺旋飞行数学模型更新飞蛾火焰位置，并最终收敛于火焰位置的新型群智能仿生算法。

MFO算法选择螺旋函数作为飞蛾空间位置的更新算子，在优化过程中遵循以下准则：

a)螺旋的初始点从飞蛾初始化空间位置开始，火焰的最佳空间位置是螺旋的最后一点。

b)螺旋的波动范围不超出搜索范围

c)在火焰周围，飞蛾能够随t(t为[-1,1间的随机数)的变化而收敛到任何点，t越小，离火焰的距离越近

d)当飞蛾靠近火焰时，火焰两侧的位置更新频率增加。

# 2.2飞蛾火焰优化算法的数学模型

MFO 算法数学模型描述如下所示：

$$
{ \cal M } = \left[ \begin{array} { c c c c } { { m _ { \scriptscriptstyle { I , I } } } } & { { m _ { \scriptscriptstyle { I , 2 } } } } & { { \cdots } } & { { m _ { \scriptscriptstyle { I , d } } } } \\ { { m _ { \scriptscriptstyle { 2 , I } } } } & { { m _ { \scriptscriptstyle { 2 , 2 } } } } & { { \cdots } } & { { m _ { \scriptscriptstyle { 2 , d } } } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { m _ { n , I } } } & { { m _ { n , 2 } } } & { { \cdots } } & { { m _ { n , d } } } \end{array} \right]
$$

$$
O M = [ O M _ { I } O M _ { 2 } \cdots O M _ { n } ]
$$

在矩阵式(20)中 $\mathbf { \Delta } _ { , n }$ 为飞蛾的种群规模； $\boldsymbol { \mathscr { d } }$ 为优化问题维度的飞蛾所处的空间位置。矩阵式(21)是用来存储飞蛾个体的适应度值。

MFO 算法中另一个关键部分是火焰，表示为

$$
F = { \left[ \begin{array} { l l l l } { F _ { _ { I , I } } } & { F _ { _ { I , 2 } } } & { \cdots } & { F _ { _ { I , d } } } \\ { F _ { _ { 2 , I } } } & { F _ { _ { 2 , 2 } } } & { \cdots } & { F _ { _ { 2 , d } } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { F _ { _ { n , I } } } & { F _ { _ { n , 2 } } } & { \cdots } & { F _ { _ { n , d } } } \end{array} \right] }
$$

并利用式(23)矩阵存储火焰适应度值，即

$$
O F = \left[ O F _ { \imath } O F _ { \imath } \cdots O F _ { \imath } \right]
$$

其中：n为飞蛾种群规模； $d$ 为优化问题维度。

飞蛾和火焰都是候选解，它们的主要区别是在进化过程中位置的更新方式不同。飞蛾是在搜索空间附近移动的搜索动因，火焰是当前迭代所获得的最佳位置。通过火焰位置不断地更新直至获得最佳的位置。因此，MFO算法可以定义为

$$
M F O = ( I , P , K )
$$

其中： $I$ 为随机生成的飞蛾种群规模和相应的适应值函数值；  
P为飞蛾在搜索空间移动的函数，其为M矩阵和位置更新返回值；  
$K$ 为终止条件是否满足的判别函数。

用数学模型描述飞蛾火焰位置更新如下：

$$
M _ { i } = \mathbf { S } \big ( M _ { i } , F _ { j } \big )
$$

其中： $M _ { i }$ 表示第 $i$ 只飞蛾位置； $F _ { j }$ 表示第 $j$ 个火焰； $s$ 为螺旋函数。

定义用于模拟飞蛾螺旋飞行路径的MFO算法表达式如下：

$$
\mathrm { S } ( M _ { i } , F _ { j } ) = D _ { i } e ^ { b t } \cos ( 2 \pi t ) + F _ { j }
$$

式(26)是对飞蛾螺旋曲线盘旋运动的路径模拟，其几何轨迹如图3所示。

![](images/2f786da3cf7d91d8f66a246ac33a2a56cb57235b74754efc645510b40d1b937e.jpg)  
图3飞蛾绕对数螺旋曲线几何轨迹图

其中：S表示飞蛾 $M _ { \mathrm { i } }$ 绕火焰 $F _ { \mathrm { i } }$ 运动更新后的位置，$D _ { i } { = } | F _ { j } - M _ { i }$ |是第i只飞蛾 $M _ { \mathrm { i } }$ 到第i个火焰 $F _ { \mathrm { i } }$ 的距离； $b$ 为螺旋形状常数； $t$ 为[-1.1]之间的随机数，它定义了飞蛾距离火焰下一位置的远近程度。

为保证MFO 算法获得较快的收敛速度，提出自适应火焰数量更新机制，即利用在迭代过程中自适应地减少火焰数目，公式为

$$
f l a m e n o { = } \operatorname { r o u n d } ( N - l \bullet { \frac { N - 1 } { T } } )
$$

其中：1为当前迭代次数；N为最大火焰数量；T为最大迭代次数。

# 2.3飞蛾火焰优化算法的设计和流程

选取ITAE作为系统动态性能的指标，搜索使ITAE值达到最小值的控制器。ITAE指标具有很好的选择性，系统参数的微小变化能够显著改变ITAE值。ITAE 指标如式(28)所示。

$$
J _ { _ { I T A E } } = \int _ { 0 } ^ { \infty } t \left| \boldsymbol { e } ( t ) \right| d t
$$

其中：e(t)为系统期望输出与实际输出之间的偏差。设计的算法流程如图4所示。

![](images/890691cb402eac691bb3a14c196308da95f19a562abbc4199eda0b4b17177b1a.jpg)  
图4算法流程

飞蛾火焰优化算法的具体参数设置如表2所示。

表2飞蛾火焰优化算法参数  

<html><body><table><tr><td>参数名</td><td>参数值</td></tr><tr><td>飞蛾种群规模n</td><td>100</td></tr><tr><td>最大火焰数量N</td><td>100</td></tr><tr><td>最大迭代次数</td><td>500</td></tr><tr><td>螺线塑形常数</td><td>1.5</td></tr><tr><td>终止条件</td><td>已知的最优解或者评价的次数超过500 次</td></tr></table></body></html>

# 3 仿真检验

# 3.1求解控制器

永磁同步电机分数阶速度控制系统可以为图5所示的简化模型。

![](images/20426a77858c28e3c22fe2de51f2fa5a31343ff51fed546aaea76f65993d86a0.jpg)  
图5永磁同步电机控制系统分数阶简化模型

图中，P(s)为永磁同步电机速度控制系统的被控对象；为了使仿真更加的合理，被控对象采用分数阶模型，C(s)为分数阶的速度 $\mathrm { P I } ^ { \lambda }$ 控制器。

采用前面提到的频域法和飞蛾火焰优化算法对分数阶PI控制器参数进行整定，其中飞蛾火焰算法的迭代过程如图6所示。

![](images/d241ef30a3dd89684d4d022081af0a8651761a795b5cd236032c9132175de815.jpg)  
图6飞蛾火焰优化算法的迭代过程

为了模拟飞蛾火焰优化算法的迭代过程和结果，对飞蛾火焰优化算法进行测试函数的仿真，如图7所示。

![](images/a7ee8a1f68049a4be1a1c948ce2e8c9a9985fb8256cbae621f62c137cb1815a9.jpg)  
图7飞蛾火焰优化算法的测试函数仿真结果

通过图6可以看出，随着迭代次数的增加，目标函数的适应度值不断地减小，说明优化的过程是比较合理的。在迭代次数到达180次左右时，目标函数基本达到了稳定状态。迭代180次时已经确定了最优值，同时相对于给定的迭代次数500次，其迭代结果是理想的。

通过飞蛾火焰算法优化后得到 $\omega _ { c } = 3 4 . 4$ ， $\lambda { = } 1 . 0 2 3$ 。则 $\mathbf { k } _ { \mathrm { i } }$ $_ { = 1 5 . 5 8 }$ ，带入式(17)可以得到 $\mathbf { k } _ { \mathrm { p } } = 2 . 0 0 3$ ；则分数阶 $\mathbf { P I } ^ { \mathrm { \lambda } }$ 控制器如式(29)所示。

$$
C ( s ) = 2 . 0 0 3 + \frac { 3 1 . 2 0 6 7 } { s ^ { 1 . 0 2 3 } }
$$

根据式(18)和(29)可以建立分数阶PI控制器飞蛾火焰优化算法的优化仿真模型，如图8所示。

![](images/cace584271b2ce1548392070b32e9cd1f5e1b575a0e61abd7596843fdbfedd6d.jpg)  
图8火焰优化算法优化的分数阶控制系统模型

由式(18)和(29)仿真可以得到控制系统的bode 图，如图9所示。

![](images/88d459bd54c2e72d245ed25e16ee31f046a7e8b26aae9c29270da727a19a9742.jpg)  
图9采用 $C ( s )$ 的控制系统的波特图

将图9的幅频特性曲线和相频特性曲线的参数进行整理，如表3所示。

表3 $\mathbf { P I } ^ { \lambda }$ 控制系统的bode图参数  

<html><body><table><tr><td>角速度rad/s</td><td>相位deg</td><td>幅值dB</td><td>曲线角/°</td></tr><tr><td>34.4</td><td>-105</td><td>-0.106</td><td>0</td></tr></table></body></html>

从图9和表3可以看出，系统的相频特性曲线在增益频率点处是水平的。所以，当系统增益出现微小的扰动时，系统的相位裕度能基本保持不变。也就是说，控制系统的相位裕度满足边界条件的要求，控制系统具有一定的鲁棒性。

# 3.2优化后的分数阶控制器与频域法控制器比较

优化后的分数阶控制器与频域法控制器比较如图10所示。把两个系统的阶跃响应的性能指标以表格的形式进行对比分析，如表4所示。

![](images/f4c25acba20b2e9a56f6b55ab3a8dd487e8344dc81da23d9195d462b978e2fea.jpg)  
图10频域法与飞蛾火焰算法优化比较

表4两种控制器参数对比  

<html><body><table><tr><td>控制器</td><td>调节时间ts /s</td><td>上升时间tr /s</td><td>超调量0%</td></tr><tr><td>G(1)</td><td>0.3</td><td>0.11</td><td>4.60</td></tr><tr><td>G(2)</td><td>0.5</td><td>0.15</td><td>4.32</td></tr></table></body></html>

从图10和表4可以看出，优化得到的分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器使系统的调节时间和上升时间明显降低，从而提高了系统的动态响应性能。从超调量这一方面来看，优化的控制器与频域法相差不大，以后可以通过改进飞蛾火焰算法来提高这方面的能力。

# 3.3优化的分数阶控制器之间的比较

由于控制系统的相位裕度已经满足边界条件的要求了，所以为了验证获得的控制器为最优的.从图9中的最佳增益频率和相位裕度的附近选择四组分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器，并将这五组优化的控制器进行电机速度跟踪仿真测试比较。

分数阶控制器 $C ( s )$ 采用前面求得的增益截止频率

$\omega _ { c } = 3 4 . 4 r a d / s$ 和相位裕度 $\varphi _ { m } = 7 5$ ,在其附近选取的四组$( \omega _ { c } , \varphi _ { m } )$ 分别为

C1: $\omega _ { c } { = } 4 0 \mathrm { r a d / s }$ $\begin{array} { c } { { \varphi _ { _ m } = 7 0 } } \\ { { { } } } \\ { { \varphi _ { _ m } = 6 5 } } \\ { { { } } } \\ { { \varphi _ { _ m } = 8 0 } } \\ { { { } } } \\ { { \varphi _ { _ m } = 8 5 } } \end{array}$ C2: $\omega _ { c } { = } 4 5 \mathrm { r a d / s }$ C3: ${ \omega _ { c } } = 3 0 \mathrm { r a d / s }$ C4: $\omega _ { c } { = } 2 5 \mathrm { r a d / s }$

很明显，C1比C2更接近 $( \omega _ { c } , \varphi _ { m } )$ ，C3比 $C 4$ 更接近 $( \omega _ { c } , \varphi _ { m } )$ 。基于这四组值，可以求出对应的四组分数阶控制器：

$$
\begin{array} { l } { { C _ { 1 } ( s ) = 2 . 1 6 4 + \frac { 3 3 . 8 8 9 0 } { s ^ { 0 . 9 3 2 } } } } \\ { { \ } } \\ { { C _ { 2 } ( s ) = 2 . 2 3 4 + \frac { 3 7 . 8 5 2 9 } { s ^ { 0 . 9 5 7 } } } } \\ { { \ } } \\ { { C _ { 3 } ( s ) = 1 . 8 8 5 + \frac { 3 0 . 7 5 0 0 } { s ^ { 1 . 1 0 9 } } } } \\ { { \ } } \\ { { C _ { 4 } ( s ) = 1 . 6 7 6 + \frac { 2 8 . 5 3 3 9 } { s ^ { 1 . 1 9 5 } } } } \end{array}
$$

设定电机的速度为 $1 0 0 0 \mathrm { r / m i n }$ ，在MATLAB上分别用 $C ( s )$ 、$C _ { 1 } ( s ) \textrm { , } C _ { 2 } ( s ) \textrm { , } C _ { 3 } ( s ) \textrm { , } C _ { 4 } ( s )$ 来控制分数阶永磁同步电机模型，并仿真它们的速度阶跃响应曲线。仿真的结果如图11所示。

![](images/319163bc57eb8e1bd3db49d8cebd2a8504c79c805ffa524105b7c9a215c3d220.jpg)  
图11不同分数阶控制系统的速度跟踪响应仿真

将图11的不同控制器的阶跃响应性能指标列出，如表5所

示。

表5控制器的阶跃响应性能指标  

<html><body><table><tr><td>控制器</td><td>峰值/转</td><td>速度稳定时刻/s</td><td>ITAE 值</td></tr><tr><td>C(s)</td><td>1060</td><td>0.25</td><td>1.038</td></tr><tr><td>C(s)</td><td>1090</td><td>0.16</td><td>4.567</td></tr><tr><td>C(s)</td><td>1100</td><td>0.13</td><td>9.345</td></tr><tr><td>C(s)</td><td>1050</td><td>0.4</td><td>10.876</td></tr><tr><td>C4(s)</td><td>1070</td><td>0.55</td><td>15.698</td></tr></table></body></html>

从图11和表5可以看出， $C _ { 1 } ( s )$ 的响应速度比 $C _ { 2 } ( s )$ 慢，但是超调量、波动和ITAE相对较小，从而可以得出结论 $C _ { 1 } ( s )$ 控制器的阶跃响应性能要优于 $C _ { 2 } ( s )$ 。同理，也可以看出 $C _ { 3 } ( s )$ 的响应速度比 $C _ { 4 } ( s )$ 快，并且超调量、波动和ITAE更小，因此可以证明以上的验证方案是合理的。

从图11和表5可以看出，尽管 $C _ { 1 } ( s )$ 和 $C _ { 2 } ( s )$ 控制系统的输出能够更快地达到稳定状态，但是超调量和ITAE 都比 $C ( s )$ 大，而 $C _ { 3 } ( s )$ 和 $C _ { 4 } ( s )$ 控制系统的输出响应速度要比 $C ( s )$ 慢，且超调量和ITAE都比 $C ( s )$ 大，因此使用所得到的 $C ( s )$ 控制系统拥有更为优异的动态响应性能。

# 3.4鲁棒性验证

为了验证优化后的分数阶系统具有较强的鲁棒性，将分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器的比例系数分别设置为最佳优化值的 $1 0 0 \% . 1 2 0 \%$ ，$80 \%$ ，即2.0030、2.4036、1.6024，并将三组控制器对分数阶电机模型进行速度阶跃响应仿真测试。

三组控制器为

$$
\begin{array} { l } { { C _ { p 1 } = 2 . 0 0 3 0 + { \displaystyle \frac { 3 1 . 2 0 6 7 } { s ^ { 1 . 0 2 3 } } } } } \\ { { \ } } \\ { { C _ { p 2 } = 2 . 4 0 3 6 + { \displaystyle \frac { 3 1 . 2 0 6 7 } { s ^ { 1 . 0 2 3 } } } } } \\ { { \ } } \\ { { C _ { p 3 } = 1 . 6 0 2 4 + { \displaystyle \frac { 3 1 . 2 0 6 7 } { s ^ { 1 . 0 2 3 } } } } } \end{array}
$$

仿真结果如图12所示。

![](images/b3c48565ec18a2407556e2043982e9e1e7829c1e98d65bd004c73925fc0e7390.jpg)  
图12优化的分数阶控制器鲁棒性验证

控制器鲁棒性性能指标如表6所示。

表6控制器鲁棒性性能指标  

<html><body><table><tr><td>Kp值</td><td>超调量/%</td><td>速度稳定时刻/s</td></tr><tr><td>2.0030</td><td>4.6</td><td>0.255</td></tr><tr><td>2.4036</td><td>4.63</td><td>0.255</td></tr><tr><td>1.6024</td><td>4.58</td><td>0.255</td></tr></table></body></html>

从图12和表6可以看出，三条曲线的超调量很接近，同时速度的稳定时刻也基本相同，因此可以得出结论，增益扰动大约在最佳值的 $\pm 2 0 \%$ 时，控制系统的相位裕度也几乎是相同的，这足够满足系统对增益扰动的鲁棒性要求。

# 3.5优化后的控制器方波和正弦波速度信号跟踪仿真

前面已经验证了控制系统具备良好的动态响应性能，为了进一步的验证优化后的控制器对其他信号的响应性能，将参考速度设置为方波信号和正弦波信号。事实上，方波信号和正弦波信号可以看成无穷个阶跃信号变化的过程。具体的波形如图13、14所示。

![](images/eb27290ea965222a24a3c0a106fbe0e7574e3b3d15ed02e42123f00e2448d02a.jpg)  
图13方波速度信号跟踪仿真

如图13所示，将幅值为 $\pm 1 0 r / \mathrm { { m i n } }$ ，频率为 $5 ~ \mathrm { H z }$ 的方波信号作为控制系统的参考速度信号，将其作用在优化后的分数阶控制系统中。在每次速度发生变化的时刻，都会有一个尖峰，这类似于前面的阶跃响应的过程，其超调量约为 $5 \%$ ，这与前面的阶跃响应一致。

在速度稳定到下一次速度变化期间，速度保持不变，这段时间可以看成一个稳态的过程，因而速度不会有波动。从超调量和整体的波形来看，优化的控制系统能够较好的跟踪方波速度信号。

![](images/8305e3199e8aa6c5a7501dfdf8fbb386b89269fa06bfd8af73fccac3ab2268de.jpg)  
图14正弦速度信号跟踪仿真

如图14所示，将幅值为 $\pm 2 r / \mathrm { m i n }$ ，频率为 $2 0 ~ \mathrm { H z }$ 的正弦信号作为控制系统的参考速度信号，将其作用在优化后的分数阶控制系统中。其中速度是时刻在变化的，没有稳态的时刻，因而波形呈现一种滞环的形式，这是控制器动态调节的结果。超调量约为 $1 \%$ ，这是因为正弦波两个相邻时刻的速度相差不大，所以调节过程相比阶跃信号比较快。

所以从超调量和整体的波形来看，优化的控制系统能够较好地跟踪正弦速度信号。

# 4 结束语

本文提出了一种飞蛾火焰算法优化分数阶控制器的方法。对于被控对象，摒弃传统的一阶和二阶模型，采用更为合理的分数阶模型作为被控对象。首先使用频域法得到分数阶PI控制器的参数，然后用算法对该分数阶 $\mathrm { P I } ^ { \mathrm { \lambda } }$ 控制器参数进行优化。为了验证算法得到的控制器的优越性，将其与频域法得到的控制器进行仿真对比；为了验证最优控制器的动态响应性能，将其与周围的值形成的控制器进行对比验证；为了验证其增益鲁棒性，通过对比 $\mathbf { k } _ { \mathrm { p } }$ 在 $\pm 1 0 \%$ 的范围变化时的响应曲线，最后对方波和正弦波速度信号进行仿真。仿真结果表明，优化后的分数阶系统具有很好的动态响应性能、较强的鲁棒性和不错的稳定性；但是优化的控制器与频域法相比，超调量并没有很大的改善，这也有待以后对飞蛾火焰算法在捕焰、弃焰以及适应度函数等方面的改进。

# 参考文献：

[1]Luo Y,Chen YQ,Ahn HS,et al.Fractional order robust control for cogging effect compensation in PMSM position servo systems: Stability analysis and experiments [J].Control Engineering Practice,2010,18 (9):1022-1036.   
[2]Jian W.Fractional order nonlinear feedback controller design for PMSM drives [J].Mathematical Problems in Engineering,2013,2013 (2013):301- 312.   
[3]Liu TH,Tseng S K,Tu Y C.Design and implementation of predictive controllers for dual-PMSM drive systems [J].Journal of Engineering,2009, 1(1): 275-288   
[4]Chen L,Liu C,Wu R,etal.Finite-time stability criteria for a class of fractional-order neural networks with delay [J].Neural Computing & Applications,2016,27: 549-556.   
[5]王军．永磁同步电机智能控制技术[M].西安：西安交通大学出版社, 2015.   
[6]WangL,SongQ,Liu Y,et al.Finite-time stability analysis of fractionalorder complex-valued memristor-based neural networks with both leakage and time-varying delays [J].Neurocomputing,2017,245 (76): 86-101.   
[7]Sierociuk D, Skovranek T, Macias M,et al. Difusion process modeling by using fractional-order models [J].Applied Mathematics & Computation, 2015,257 [C] : 2-11.   
[8]Chen YQ,Dou H,Vinagre B M,et al.A robust tuning method for fractional order PI controllers [J].IFAC Proceedings Volumes,2006,39 (11): 22-27.   
[9]胡海波，黄友锐.混合粒子群算法优化分数阶 PID 控制参数研究[J]. 计算机应用,2009,29(9):2483-2486.   
[10]吴振宇，赵亮，冯林．基于分数阶PID 控制器的智能车控制[J].控制 工程,2011,18(3):401-404.   
[11]秦昌茂，齐乃明，吕瑞，等．高超声速飞行器自抗扰分数阶PID控制器 设计[J].南京航空航天大学学报,2011,28(3):240-245.   
[12] Altintas G,Aydin Y.A comparison on genetic algorithm based integer order and fractional order PID control of magnetic bearing system [C]//Proc of IEEE International Conference on Mechatronics.2017:20-24.   
[13]崔东文．飞蛾火焰优化算法—一投影寻踪回归模型在需水预测中的应 用[J].华北水利水电大学学报：自然科学版,2017,38(2):25-29.   
[14] Jangir N,Pandya MH,TrivediI N,et al.Moth-flame optimization Algorithm for solving real challenging constrained engineering optimization problems [C]//Proc of IEEE Electrical,Electronics and Computer Science. 2016.   
[15] Qiao W, Tang X,Zheng S,et al.Adaptive two-degree-of-freedom PI for speed control of permanent magnet synchronous motor based on fractional order GPC[J].Isa Transactions,2016,64(34):303-313.   
[16] Yi Z,Chen W,Wei H.Permanent magnet synchronous motor vector control based on weighted integral gain of sliding mode variable structure[J]. Open Automation& Control Systems Journal,2015,7(1):323-330.   
[17]Heng M,Wang S,Wang F,et al.The sliding-mode control based on fractional order sign function of permanent magnet synchronous motor [J]. Transactions of China Electrotechnical Society,2017,32(9): 56-62.   
[18] Liu H,Li S.Speed control for PMSM servo system using predictive functional control and extended state observer[J].IEEE Trans on Industrial Electronics,2011,59 (2):1171-1183.