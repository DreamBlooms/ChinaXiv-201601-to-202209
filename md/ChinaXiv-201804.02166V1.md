# 基于改进粒子群算法的四旋翼自抗扰控制器优化设计

胡丹丹，张宇辰

(中国民航大学机器人研究所，天津300300)

摘要：针对四旋翼飞行器自抗扰控制器参数较多，人工整定困难且难以得到最优控制效果的问题，提出一种基于改进粒子群算法的四旋翼自抗扰控制器优化方法。在设计了四旋翼飞行器的自抗扰控制器之后，将自抗扰控制器的参数作为粒子群中的粒子进行迭代寻优，同时在传统的粒子群算法基础上，参考遗传算法，对适应值不好的粒子进行交叉保优，以提高粒子的多样性，加快寻优速度。仿真结果表明，对比人工整定参数的控制器，优化后的控制器超调更小，调节时间更快。该方法能够解决四旋翼飞行器自抗扰控制器人工参数整定困难的问题，且优化后的控制器具有更好的控制效果。

关键词：四旋翼飞行器；自抗扰控制；粒子群算法；参数优化；姿态控制;中图分类号：TP242 doi:10.3969/j.issn.1001-3695.2018.01.0026

# ADRC controller optimization design based on improved PSO algorithm for quad-rotor

HuDandan, Zhang Yuchen (Robotics Institute,Civil Aviation University of China,Tianjin 3oo3oo,China)

Abstract: Inordertosolve theproblem thatthe parametersofquad-rotoraircraftADRCcontrolerare dificult toset,and itis hard toget the optimal control effect due to manual parameter tuning,this paper proposed a design method of adaptive disturbance rejection controler based on improved particle swarm optimization for quad-rotor.After designed the ADRC controllerofquad-rotor,this methditerativelyoptimized theparametersof thecontrolerasparticles intheparticle swarm.At thesame time,basedonthe traditional particle swarmoptimizationandrefering togeneticalgorithm,itcrossguaranteed the particles with poorfitness valueto Improve thediversityofparticles,andto spedupthesearch speed.Thesimulationresults showthatcompared with thecontrollr with manual tuning parameters,teoptimized controllerhas less overshoot and faster adjusting time.This methodcansolve thedificultyofmanual parameterseting ofquad-rotoraircraftADRCcontroler,and the optimized controller has better control performance.

Key Words:quad-rotor aireraft; activedisturbance rejection controller(ADRC); particle swarm optimization(PSO); parameter optimization; attitude control

# 0 引言

四旋翼飞行器的控制系统是一个四输入、六输出的欠驱动非线性系统，具有强耦合性特点，难以建立精确模型且易受到外界干扰，因此，其优化设计成为近年来国内外学者研究的热点和难点。

Gonzalez-vazquez等人[1]于2010年基于经典PID控制方法，采用非线性PID控制器实现了四旋翼飞行器的姿态控制和位置控制。Alothman 等人[2]于2015 年提出了一种基于LQR的四旋翼飞行器载荷运输系统的设计方法，仿真结果表明控制效果优于传统PID控制器。Yang等人[3]提出了一种基于动态逆的四旋翼飞行器非线性控制方法。为了补偿该方法所产生的误差，设计了基于神经网络的自适应动态反转控制器。Raffo等[4]在2015年提出了一种用于四旋翼飞行器路径跟踪的非线性鲁棒控制策略，仿真结果表明该方法具有良好的鲁棒性。

诸如LQR、鲁棒控制、反步控制等[5.6]控制策略虽然有比较好的效果，但由于其控制算法或需要基于准确的数学模型，或计算量很大，数据的实时处理对处理器性能要求高，实现起来有一定的困难。目前各类四旋翼飞行器依然是使用传统串级PID 作为核心控制算法，PID算法对于控制精度不高的飞行任务可以基本满足控制需求，但是其抗干扰能力差，且无法满足高精度的控制需求。

为了提高飞行器的抗干扰性，学者们开始使用自抗扰技术来设计旋翼控制器[7-9]，相比于传统串级PID 控制器拥有更好的控制效果。但是自抗扰控制器参数较多，整定困难。为了得到最佳控制效果，且解决人工参数整定困难的问题，本文首先基于自抗扰技术设计了四旋翼飞行器控制器，对于自抗扰控制器的参数使用粒子群算法进行寻优，同时对于粒子群算法易陷入局部最优的问题加入遗传算法中的交叉保优思想进行改进。

# 1 四旋翼飞行器数学模型建立

选取X型四旋翼机型建立数学模型。定义两个坐标系：惯性坐标系和机体坐标系，如图1所示。

惯性坐标系E（OXYZ)相对于地球表面不动，取“东北天”（ENU）建立坐标系。

机体坐标系B（oxyz）与飞行器固联，原点为飞行器的重心、质心，ox轴为1号与3号电机夹角的角平分线方向，oy轴为2号与3号电机夹角的角平分线方向，ox轴垂直于oxy平面指向机体上方，该坐标系符合右手定则。

![](images/fbbc923f408f9c16d10842fb79e6edf159fd12fb017d1cd036cfdba3506d58f1.jpg)  
图1惯性坐标系与机体坐标系示意图

考虑到四旋翼飞行器的气动环境复杂，且易受到未知的外界干扰，为了方便模型的建立，对飞行器不失一般性地作出如下几点假设：a)视四旋翼飞行器为均匀对称刚体，飞行过程中质量保持不变；b机体坐标系的原点与飞行器几何中心及质心始终重合；c由于飞行器不会飞的很高很远，所以视地球表面为平面，飞行器所受重力和阻力不受飞行器飞行高度变化的影响，始终保持不变；d)不计算地球自转与公转对飞行器的影响。

飞行器的各姿态角定义如图2所示。

![](images/33741b1606f1512586e40919f0262040b43c44a5c061bb001adcf2bf27b12eaf.jpg)  
图2飞行器姿态角示意图

基于以上设定，四旋翼飞行器动力学模型可表示为如下形式：

$$
\begin{array} { r l } & { | \tilde { x } = ( \cos \phi \sin \theta \cos \psi + \sin \phi \sin \psi ) \frac { U _ { 1 } } { m } + A _ { s } | } \\ & { | \tilde { y } = ( \cos \phi \sin \theta \sin \psi + \sin \phi \cos \psi ) \frac { U _ { 1 } } { m } + A _ { s } | } \\ & { | \tilde { z } = ( \cos \phi \cos \theta ) \frac { U _ { 1 } } { m } - g + A _ { s } | } \\ & { | \tilde { \phi } = \partial \psi ( \frac { I _ { - } I _ { s } } { I _ { s } } ) + \frac { I } { \sqrt { 2 I _ { - } } } \sum _ { i } Z _ { + } + \mathcal { S } _ { \Psi } } \\ & { | \tilde { \theta } = \tilde { \phi } \psi ( \frac { I _ { - } I _ { s } } { I _ { s } } ) + \frac { I } { \sqrt { 2 I _ { - } } } \sum _ { i } y _ { * } + A _ { s } | } \\ & { | \tilde { \psi } = \tilde { \phi } \tilde { \phi } ( \frac { I _ { - } I _ { s } } { I _ { s } } ) + \frac { U _ { 1 } } { I _ { s } } + 4 _ { s } } \end{array}
$$

定义 $U _ { \scriptscriptstyle 1 } \sim U _ { \scriptscriptstyle 4 }$ 为各个通道的控制量，表述如下：

$$
\left\{ \begin{array} { l } { U _ { 1 } = F _ { 1 } + F _ { 2 } + F _ { 3 } + F _ { 4 } = k _ { 1 } \left( \Omega _ { 1 } ^ { 2 } + { \Omega _ { 2 } } ^ { 2 } + { \Omega _ { 3 } } ^ { 2 } + { \Omega _ { 4 } } ^ { 2 } \right) } \\ { U _ { 2 } = - F _ { 1 } + F _ { 2 } + F _ { 3 } - F _ { 4 } = k _ { 1 } \left( - { \Omega _ { 1 } } ^ { 2 } + { \Omega _ { 2 } } ^ { 2 } + { \Omega _ { 3 } } ^ { 2 } - { \Omega _ { 4 } } ^ { 2 } \right) } \\ { U _ { 3 } = - F _ { 1 } + F _ { 2 } - F _ { 3 } + F _ { 4 } = k _ { 1 } \left( - { \Omega _ { 1 } } ^ { 2 } + { \Omega _ { 2 } } ^ { 2 } - { \Omega _ { 3 } } ^ { 2 } + { \Omega _ { 4 } } ^ { 2 } \right) } \\ { U _ { 4 } = F _ { 1 } + F _ { 2 } - F _ { 3 } - F _ { 4 } = k _ { 2 } \left( { \Omega _ { 1 } } ^ { 2 } + { \Omega _ { 2 } } ^ { 2 } - { \Omega _ { 3 } } ^ { 2 } - { \Omega _ { 4 } } ^ { 2 } \right) } \end{array} \right.
$$

其中： $\phi , \theta , \psi$ 分别为滚转角、俯仰角和偏航角， $\mathbf { \lambda } _ { m }$ 为飞行器的质量， $g$ 为重力加速度， $I _ { x } , I _ { y } , I _ { z }$ 分别为三个轴上的转动惯量，$l$ 为旋翼中心到机体坐标系原点的距离， $F _ { _ 1 } \sim F _ { _ 4 }$ 为对应旋翼升力， $\varOmega _ { 1 } \sim \varOmega _ { 4 }$ 为对应电机的转速， $k _ { 1 }$ 为旋翼的升力系数， $k _ { 2 }$ 为旋翼的阻力系数。 $\varDelta _ { x } , \varDelta _ { y } , \varDelta _ { z } , \varDelta _ { \phi } , \varDelta _ { \theta } , \varDelta _ { \psi }$ 分别表示各个通道未建模和干扰部分。

# 2 四旋翼飞行器自抗扰控制器设计

# 2.1自抗扰控制器结构设计

自抗扰控制技术（active disturbance rejection controller,ADRC）是韩京清教授于上世纪80年代末期提出的一种新的控制理论[10]，其特点是不依赖于控制对象的模型，可以将系统建模不准确产生的“内扰”和系统外部扰动结合起来进行估计补偿。其结构包括跟踪微分器（TD）、扩张状态观测器（ESO）和非线性误差反馈控制律（NLSEF）三个部分。二阶自抗扰控制器结构如图3所示。

![](images/0ebc3ec88d5dceca1dd9f960719e0228f1a43d4bf05a1db4f46f37da45fb40e7.jpg)  
图3二阶自抗扰控制器结构图

四旋翼飞行器高度与姿态控制结构图如图4所示。

![](images/860d5dd40d7aa5ba366db62a989ad8235bbb1622a6c975172221003785a7721c.jpg)  
图4四旋翼飞行器高度与姿态控制结构图

姿态控制是飞行器可以稳定飞行的基础，由飞行器动力学模型可知，四旋翼的姿态角通道耦合在一起构成了飞行器的"内扰”，这可以通过设计扩张状态观测器来进行估计补偿，从而实现解耦控制，使得各个通道变为“积分串联器”型的线性系统[11]。姿态系统方程如下：

$$
\begin{array} { r l } & { ( \ddot { \tilde { \phi } } = \dot { \theta } \dot { \psi } ( \frac { I _ { y } - I _ { z } } { I _ { x } } ) + \frac { l } { \sqrt { 2 } I _ { x } } U _ { 2 } + { \mathcal A } _ { \phi }  } \\ & {  \{ \ddot { \theta } = \dot { \phi } \dot { \psi } ( \frac { I _ { z } - I _ { x } } { I _ { y } } ) + \frac { l } { \sqrt { 2 } I _ { y } } U _ { 3 } + { \mathcal A } _ { \theta }  } \\ & {  \ddot { \psi } = \dot { \phi } \dot { \theta } ( \frac { I _ { x } - I _ { y } } { I _ { z } } ) + \frac { U _ { 4 } } { I _ { z } } + { \mathcal A } _ { \psi } } \end{array}
$$

将上式整理为自抗扰理论对应的形式：

$$
\left[ \begin{array} { c } { \ddot { \phi } } \\ { \ddot { \theta } } \\ { \ddot { \psi } } \end{array} \right] = \left[ \begin{array} { c } { f _ { 1 } \left( \phi , \theta , \psi , \varDelta \right) } \\ { f _ { 2 } \left( \phi , \theta , \psi , \varDelta \right) } \\ { f _ { 3 } \left( \phi , \theta , \psi , \varDelta \right) } \end{array} \right] + \pmb { { B } } \left[ \begin{array} { c } { U _ { 2 } } \\ { U _ { 3 } } \\ { U _ { 4 } } \end{array} \right]
$$

$$
\begin{array} { r } { B = \left[ \begin{array} { c c c } { \displaystyle \frac { l } { \sqrt { 2 } I _ { x } } } & { 0 } & { 0 } \\ { 0 } & { \displaystyle \frac { l } { \sqrt { 2 } I _ { y } } } & { 0 } \\ { 0 } & { 0 } & { \displaystyle \frac { 1 } { I _ { z } } } \end{array} \right] , \quad \left\{ f _ { 1 } = \dot { \theta } \dot { \psi } \left( \frac { I _ { y } - I _ { z } } { I _ { x } } \right) + { \mathcal A } _ { \psi } \right. } \end{array}
$$

# 2.2自抗扰控制器算法设计

以四旋翼飞行器的滚转通道为例来描述自抗扰控制器的设计过程。 $T$ 为控制器的控制间隔。

1）跟踪微分器（TD)

TD可以为输入信号安排过渡过程，并提取输入信号的微分，表示如下：

$$
\left\{ \begin{array} { l } { { \nu _ { 1 } \left( k + 1 \right) = \nu _ { 1 } \left( k \right) + T \nu _ { 2 } \left( k \right) } } \\ { { \nu _ { 2 } \left( k + 1 \right) = \nu _ { 2 } \left( k \right) + T \mathrm { f s t } \left( \nu _ { 1 } \left( k \right) - \nu _ { d } , \nu _ { 2 } \left( k \right) , r , h \right) } } \end{array} \right.
$$

其中 $\nu _ { d }$ 是期望值， $\boldsymbol { r }$ 为速度因子， $h$ 为滤波因子，提高 $r$ 值可以减小安排过渡过程的时间，过大的 $\boldsymbol { r }$ 值会使得跟踪信号更加逼近输入信号，但会失去安排过渡过程的意义。滤波因子 $h$ 可以滤掉跟踪信号中的噪声， $h$ 越大滤波效果越好，但是增大 $h$ 会产生输入信号相位损失，一般来讲 $h$ 设定为3-10倍的控制周期。

2）扩张状态观测器（ESO）

ESO对系统的总扰动进行估计，并且实时补偿给控制器其表示如下：

$$
\left\{ \begin{array} { c } { \varepsilon _ { 1 } = \mathbf { z } _ { 1 } \left( k \right) - y \left( k \right) } \\ { \varepsilon _ { 1 } \left( k + 1 \right) = z _ { 1 } \left( k \right) + T \left( z _ { 2 } \left( k \right) - \beta _ { 1 } \varepsilon _ { 1 } \right) } \\ { z _ { 2 } \left( k + 1 \right) = z _ { 2 } \left( k \right) + T \left( z _ { 3 } \left( k \right) - \beta _ { 2 } \operatorname { f a l } \left( \varepsilon _ { 1 } , \alpha _ { 1 } , \delta \right) + b u \left( k \right) \right) } \\ { z _ { 3 } \left( k + 1 \right) = z _ { 3 } \left( k \right) - T \beta _ { 3 } \operatorname { f a l } \left( \varepsilon _ { 1 } , \alpha _ { 2 } , \delta \right) } \end{array} \right.
$$

其中： $\alpha _ { 1 } , \alpha _ { 2 }$ 决定 $\operatorname { f a l } ( \cdot )$ 的非线性程度，一般的， $\alpha _ { \mathrm { { 1 } } }$ 取0.5， $\alpha _ { 2 }$ 取 $0 . 2 5 \mathrm { ~ } _ { \circ } \mathrm { ~ } \delta$ 为 $\operatorname { f a l } ( \cdot )$ 函数在原点附近的线性区间宽度，如果 $\delta$ 太大会降低ESO对于非线性型号的逼近能力，过小的 $\delta$ 会导致高频震荡。 $\beta _ { 1 } , \beta _ { 2 } , \beta _ { 3 }$ 为状态误差反馈的反馈增益，影响ESO的收敛速度。 $\beta _ { 1 }$ 越大 $z _ { 1 }$ 跟踪输入信号的速度越快。同样的， $\beta _ { 2 }$ 越大$z _ { 2 }$ 跟踪输入信号的速度越快。 $\beta _ { 3 }$ 关系着观测器对于扰动估计产生的滞后， $\beta _ { 3 }$ 越大产生的滞后越小。 $\beta _ { 1 } , \beta _ { 2 } , \beta _ { 3 }$ 三个参数之间相互制约，增大 $\beta _ { 1 } , \beta _ { 2 }$ 能够抑制 $\beta _ { 3 }$ 过大产生的震荡。

# 3）非线性误差反馈控制律（NLSEF）

NLSEF中反馈误差以非线性的组合计算控制量，表示如下：

$$
\left\{ \begin{array} { l l } { \displaystyle e _ { 1 } = \nu _ { 1 } \left( k \right) - z _ { 1 } \left( k \right) } \\ { \displaystyle e _ { 2 } = \nu _ { 2 } \left( k \right) - z _ { 2 } \left( k \right) } \\ { \displaystyle u _ { 0 } \left( k \right) = k _ { 1 } \mathrm { ~ f a l } \left( e _ { 1 } , \alpha _ { 1 } , \delta _ { 0 } \right) + k _ { 2 } \mathrm { ~ f a l } \left( e _ { 2 } , \alpha _ { 2 } , \delta _ { 0 } \right) } \\ { \displaystyle u \left( k \right) = u _ { 0 } \left( k \right) - \frac { z _ { 3 } \left( k \right) } b } \end{array} \right.
$$

NLSEF 中要满足 $0 < \alpha _ { 1 } < 1 < \alpha _ { 2 }$ 的条件，一般取 $\alpha _ { \mathfrak { i } }$ 为0.75,$\alpha _ { 2 }$ 为 $1 . 2 5$ 。 $\delta _ { \phantom { } _ { 0 } }$ 的调节与ESO中的 $\delta$ 一致。 $k _ { \mathrm { 1 } }$ 越大系统响应越快， $k _ { 2 }$ 可以抑制系统的超调。 $b$ 由系统状态方程决定，对于四

旋翼飞行器无法精确建模的特性，可以将 $b$ 作为一个可调参数。算法中 fal(·)和 $\mathrm { f s t } ( \cdot )$ 表示如下：

$$
\operatorname { f a l } { \big ( } \varepsilon , \alpha , \delta { \big ) } = \left\{ \left| \varepsilon { \big | } ^ { \alpha } \operatorname { s i g n } { \big ( } \varepsilon { \big ) } , \left| \varepsilon \right| > \delta , \right. \right. _ { \delta > 0 }
$$

$$
\begin{array} { r l } & { \quad \mathrm { f s t } \big ( x _ { 1 } , x _ { 2 } , r , h \big ) = - \Bigg \{ \displaystyle \frac { r \alpha } { r } , | \alpha | \leq d } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad d = r h , d _ { 0 } = d h , y = x _ { 1 } + h x _ { 2 } , \alpha _ { 0 } = \left( d ^ { 2 } + 8 r \left| y \right| \right) ^ { 1 / 2 } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \alpha = \left\{ x _ { 2 } + \displaystyle \frac { a _ { 0 } - d } { 2 } , | y | > d _ { 0 } \right. } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array}
$$

自抗扰控制器不依赖模型，不需要针对具体被控对象来分析系统的稳定性，只需选取适当参数，就可以实现四旋翼飞行器姿态和高度的稳定控制。

# 3 基于改进粒子群算法的自抗扰控制器参数优化

粒子群算法（particle swarmoptimization，PSO）是计算智能领域的一种群体智能优化算法，由Kennedy和Eberhart 博士在1995 年提出的[12.13]。该算法已广泛的应用于众多领域的参数寻优问题[14,15]。粒子群算法速度与位置更新公式表示如下：

$$
\left\{ \begin{array} { l } { { { \nu } _ { i d } } \left( k + 1 \right) = { { \omega } { \nu } _ { i d } } \left( k \right) + { { c } _ { 1 } } { { r } _ { 1 } } \left( { { p } _ { i d } } - { { z } _ { i d } } \left( k \right) \right) } \\ { \qquad \quad + { { c } _ { 2 } } { { r } _ { 2 } } \left( { { p } _ { g d } } - { { z } _ { i d } } \left( k \right) \right) } \\ { { { z } _ { i d } } \left( k + 1 \right) = { { z } _ { i d } } \left( k \right) + { { \nu } _ { i d } } \left( k + 1 \right) } \end{array} \right.
$$

其中： $k$ 为迭代次数， $z _ { i }$ 为第 $i$ 个粒子， $^ d$ 为每个粒子的维度，$p _ { i }$ 为粒子迄今搜索到的最后位置， $p _ { g }$ 为整个粒子群迄今搜索到的最优位置， $\boldsymbol { c } _ { 1 } , \boldsymbol { c } _ { 2 }$ 为粒子的学习因子，使得粒子具有自我总结和向群体中优秀粒子学习的能力， $\omega$ 为粒子惯性权重，起着权衡局部最优和全局最优的作用， $r _ { 1 } , r _ { 2 }$ 为[0.1之间的随机数，使得群体具有多样性。

传统的粒子群算法是通过追随个体极值和群体极值来完成寻优的，虽然操作简单，且能够很快的收敛，但是随着迭代次数的增加，在收敛的同时，各粒子越来越相似，可能在局部解周边无法跳出。为了解决粒子群算法在进行寻优计算过程中陷入到局部最优的问题，借鉴遗传算法，在粒子每次迭代寻优的过程中加入选择、交叉操作以对粒子群算法进行改进，使得算法可以遍历到更多的粒子。具体为：每一次迭代后计算粒子群适应值的算术平均值，取适应值大于算术平均值的最大偶数个粒子直接进入下一次迭代，将剩余粒子进行遗传算法中的交叉选择操作，随机选取需要交叉的位数，并对粒子对应位进行交叉，将交叉后生成的子代与父代结合在一起并比较适应值，选择适应值更好的一半进入下一次迭代，生成新一组粒子群。

算法的适应度函数选取ITAE误差准则，其值越低，性能越好，基本形式如下：

$$
J = \int _ { 0 } ^ { \infty } t { \big | } e { \big ( } t { \big ) } { \big | } d t
$$

在自抗扰控制器中有14个可调参数，其中 ESO 中的$\beta _ { 1 } , \beta _ { 2 } , \beta _ { 3 }$ 和 NLSEF 中的 $k _ { 1 } , k _ { 2 } , b$ 是控制器最关键的6个参数，前者决定扰动的估计补偿能力，后者直接决定控制量的大小，本文将这6个参数作为粒子群算法的粒子，设计自抗扰控制器粒子群算法。

改进粒子群算法的流程如下所述：

a)初始化粒子群，随机产生所有粒子的位置和速度，并确定粒子的 ${ \boldsymbol { p } } _ { i }$ 和 $p _ { g }$ ：

b)按照粒子群速度与位置公式更新粒子的速度和位置；

c)将每个粒子代入控制器仿真器并计算对应的ITAE值。

d）计算所有粒子ITAE值的算术平均值，取偶数个ITAE值小于平均值的粒子直接进入下一次迭代。剩余粒子进行交叉选择，生成相同数量的子代，并与父代一起进行排序，取ITAE值更小的一半进入下一次迭代。

e)将每一个粒子的适应值与该粒子所经历过的最优位置${ \boldsymbol { p } } _ { i }$ 的适应值进行比较，如果更好，则将该粒子其作为新的 ${ \boldsymbol { p } } _ { i }$ ：对每个粒子，将其适应值与整个粒子群所经历过的最优位置 $p _ { g }$ 的适应值进行比较，如果更好，则将该粒子作为新的 $p _ { g }$ ：

f)如果没有满足最终条件（适应值小于预设阈值或者超过最大迭代次数)，则返回步骤b)，否则，退出算法，输出寻优过程曲线和最优解。

使用改进的粒子群算法对于自抗扰控制器的参数进行优化，其过程如图5所示。

![](images/9e4f1299cac730d4856f9e28733abc5baa571bcf02d26dd02398ff1eae877e04.jpg)  
图5PSO 算法流程图

关于惯性权重 $\omega$ ，较高的 $\omega$ 会使PSO拥有更好的全局搜索能力，而低 $\omega$ 值则对于局部搜索更加有利[16]。为了使得粒子群算法在计算初期具有更好的全局搜索能力，而在计算后期具有更好的局部寻优能力，现将 $\omega$ 设置为如下动态形式：

$$
\omega \big ( k \big ) = \omega _ { s t a r t } - \big ( \omega _ { s t a r t } - \omega _ { e n d } \big ) \Bigg ( \frac { k } { T _ { m a x } } \Bigg ) ^ { 2 }
$$

其中， $\omega ( k )$ 为第 $k$ 次迭代时的惯性权重， $\omega _ { s t a r t }$ 为惯性权重初始值，通常设定为0.9， $\omega _ { e n d }$ 为惯性权重终值，通常设定为0.4，$T _ { m a x }$ 为最大迭代次数。

# 4 实验分析

本文首先建立四旋翼ADRC控制器模型并与传统串级PID控制器进行比较，ADRC控制器仿真模块如图6所示：

![](images/38d6b08ab7eb69167f268d6a339308f2e68cfe77663edb4ecffcb96aadc83a51.jpg)  
图6Matlab/Simulink中 ADRC 仿真模块

仿真实验以滚转通道为例，旋翼自身参数如表1所示。

表1飞行器仿真参数  

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>m/kg</td><td>1.5</td></tr><tr><td>l/m</td><td>0.25</td></tr><tr><td>g/(m/s²)</td><td>9.81</td></tr><tr><td>1x/(kg·m²)</td><td>0.033</td></tr><tr><td>1,/(kg·m²)</td><td>0.033</td></tr><tr><td>I/(kg·m²）</td><td>0.061</td></tr><tr><td>k/(N·s2)</td><td>3.1×10-7</td></tr><tr><td>k/(N.s²)</td><td>1.12×10-7</td></tr></table></body></html>

选取控制周期为0.01s，ADRC参数如表2所示。

表2ADRC仿真参数  

<html><body><table><tr><td>模块</td><td>参数</td><td>数值</td></tr><tr><td>TD</td><td>r</td><td>2</td></tr><tr><td rowspan="2">ESO</td><td>h</td><td>0.05</td></tr><tr><td>β</td><td>100</td></tr><tr><td rowspan="10"></td><td>β</td><td>450</td></tr><tr><td>β</td><td>2900</td></tr><tr><td>α</td><td>0.5</td></tr><tr><td>α2</td><td>0.25</td></tr><tr><td>8</td><td>0.1</td></tr><tr><td>NLSEF</td><td>k 80</td></tr><tr><td>k</td><td>40</td></tr><tr><td>α</td><td>0.75</td></tr><tr><td>α2</td><td>1.25</td></tr><tr><td>8</td><td>0.1</td></tr><tr><td></td><td>b</td><td>5</td></tr></table></body></html>

设定期望滚转角度为15度，分别仿真PID和ADRC两种控制器得到的输出曲线如图7所示，控制性能指标如表3所示，从图中可以看出自抗扰算法超调量小于串级PID控制器且调节时间更短。

![](images/834b83858254d44625f1efa8fdd8afec10d5d1888900ef498bcb5a26dea3b29f.jpg)  
图7ADRC/PID 控制效果对比

表3滚转角控制性能指标对比  

<html><body><table><tr><td>控制器</td><td>超调/%</td><td>调节时间/s</td></tr><tr><td>串级PID</td><td>5.89</td><td>3.09</td></tr><tr><td>自抗扰控制</td><td>2.31</td><td>1.64</td></tr></table></body></html>

为了测试ADRC控制器的抗干扰能力，对两种控制器加入高斯白噪声，其控制效果如图8所示。

![](images/7107dff57f1ae6b09b4ee0894972500f0b69e50a53e8bcff35e42b6ff0546993.jpg)  
图8加入高斯噪声后ADRC/PID控制效果对比

飞行器稳定状态下，在5s时刻加入幅值为1、脉宽为1s的干扰输入信号来测试两种控制器的抗干扰能力，控制效果如图9所示。

![](images/5001235b4786a8c083d4a097ebd2ad715a8718ad0d927c56f3ba0eb0563319ed.jpg)  
图9加入突变噪声后ADRC/PID控制效果对比

实验表明，ADRC具有优秀的噪声抑制和抗干扰能力。

之后，加入改进粒子群对ADRC参数进行优化，对粒子群算法的各项参数进行设定，具体数值如表4所示。

表4 PSO参数设定  

<html><body><table><tr><td>参数</td><td>数值[k,k,b,β,β,β]</td></tr><tr><td></td><td>2</td></tr><tr><td>C2</td><td>2</td></tr><tr><td>粒子维度</td><td>6</td></tr><tr><td>粒子群规模</td><td>50</td></tr><tr><td>最大迭代次数</td><td>50</td></tr><tr><td>粒子速度上限</td><td>[1,1,0.25,1,2,5]</td></tr><tr><td>粒子速度下限</td><td>[-1,-1,-0.25,-1,2,5]</td></tr><tr><td>粒子寻优上限</td><td>[400,400,30,200,1000,4000]</td></tr><tr><td>粒子寻优下限</td><td>[1,/30. 60,200,150]</td></tr></table></body></html>

以四旋翼滚转角通道为例，其他参数设定保持不变，只进行 $k _ { 1 } , k _ { 2 } , b , \beta _ { 1 } , \beta _ { 2 } , \beta _ { 3 }$ 的优化，以15度作为输入，优化后与之前参数的各性能指标如表5所示。

表5滚转角优化前后参数与控制性能对比  

<html><body><table><tr><td></td><td>优化前</td><td>优化后</td></tr><tr><td>β</td><td>100</td><td>94.13</td></tr><tr><td>β</td><td>450</td><td>437.89</td></tr><tr><td>β</td><td>2900</td><td>2930.31</td></tr><tr><td>k</td><td>80</td><td>253.48</td></tr><tr><td>k</td><td>40</td><td>212.15</td></tr><tr><td>b</td><td>5</td><td>9.87</td></tr><tr><td>超调/%</td><td>2.31</td><td>0.32</td></tr><tr><td>调节时间/s</td><td>1.64</td><td>1.25</td></tr><tr><td>ITAE 性能</td><td>0.0145</td><td>0.0016</td></tr></table></body></html>

各个参数的变化曲线与优化之后的仿真结果如图10\~13所示。

![](images/063c40888c26dab63c2feb03cace377d937a7b7ebb206a22620bfeab1d1726de.jpg)  
图10 （20 $k _ { 1 } , k _ { 2 } , b$ 优化曲线

![](images/9eeb1a6151e3ed1990fed65783a570609b9b517c7ccba043a86490f08d3100f5.jpg)  
图11 $\beta _ { 1 } , \beta _ { 2 } , \beta _ { 3 }$ 优化曲线

![](images/c36228bb4eb85301cec25705658ae3173491f265f579a0982a8d012cf0620097.jpg)  
图12 ITAE适应值曲线

![](images/584fadd0db613c15ee50fde98a5471d32e6b0b77655077e4c4ae7e50edda6deb.jpg)  
图13优化前后的滚转角控制曲线

![](images/6a3080f2ba8403dfa8829c05ea7e7b4bbbab6852b0e35d9ac81bb77a8923256c.jpg)  
图15优化前后的高度控制曲线

俯仰角通道的特性与滚转角相近，可以使用相同的参数，不再另行优化。航偏角和高度分别输入60和5，优化前后的参数分别如表6、7所示，对比曲线分别如图14、15所示。

表6航偏角优化前后参数与控制性能对比  

<html><body><table><tr><td></td><td>优化前 优化后</td></tr><tr><td>β</td><td>100 112.45</td></tr><tr><td>β</td><td>450 609.71</td></tr><tr><td>β 3000</td><td>3532.56</td></tr><tr><td>k</td><td>100 288.14</td></tr><tr><td>k</td><td>80 256.2</td></tr><tr><td>b</td><td>15 23.41</td></tr><tr><td>超调/%</td><td>3.23 0.79</td></tr><tr><td>调节时间/s</td><td>2.75 2.11</td></tr></table></body></html>

![](images/bdee36639aaec77b9573ca31a056064629116dea328250d826a99249e8231b3b.jpg)  
图14优化前后的航偏角控制曲线

通过仿真实验可以看出，经过改进PSO算法优化后的ADRC控制器超调更且调节时间更短，同时无须人工调参。和滚转角通道类似，俯仰角通道、航偏角通道和高度通道的控制效果经过改进PSO算法优化后也具有很好的效果。因此使用改进粒子群算法对ADRC 控制器进行参数优化明是一种行之有效的方法。

# 5 结束语

本文首先设计了基于自抗扰控制技术的四旋翼飞行器姿态与高度控制器，为了得到最优控制效果，并针对自抗扰控制器参数较多，人工整定耗时长且难以达到最优的问题，提出了基于粒子群算法的自抗扰控制器参数优化方法，同时为了解决粒子群算法易陷入局部最优的问题，加入遗传算法中的交叉操作，对适应值不好的粒子进行交叉保优，以提高粒子的多样性，加快寻优速度。使用Simulink对整个优化过程进行了仿真，结果表明，使用改进的PSO算法，能够有效解决自抗扰控制器人工参数整定困难的问题，经过改进的PSO算法优化后的自抗扰控制器具有更好的动态特性和稳态特性，且算法简单，调参时间短，易于实现，具有较大的实际应用价值。

表7高度优化前后参数与控制性能对比  

<html><body><table><tr><td></td><td>优化前</td><td>优化后</td></tr><tr><td>β</td><td>100</td><td>127.14</td></tr><tr><td>β</td><td>450</td><td>771.28</td></tr><tr><td>β</td><td>3000</td><td>4000</td></tr><tr><td>k</td><td>120</td><td>322.4</td></tr><tr><td>k</td><td>100</td><td>335.21</td></tr><tr><td>b</td><td>20</td><td>25.63</td></tr><tr><td>超调/%</td><td>3.68</td><td>0.8</td></tr><tr><td>调节时间/s</td><td>4.36</td><td>3.42</td></tr></table></body></html>

# 参考文献：

[1]Gonzalez-Vazquez S,Moreno-Valenzuela J.A new nonlinear PI//PID controller for quadrotor posture regulation [C]//Proc of Electronics, Robotics and Automotive Mechanics Conference.2010:642-647.   
[2]Alothman Y,Jasim W,Gu Dongbing. Quad-rotor Lifting-transporting Cablesuspended Payloads Control [C]//Proc of the 21st International Conference on Automation and Computing.2015: 1-6.   
[3]Yang Ning,Wu Liaoni,Lin Qi.Adaptive flight control law based on neural networks and dynamic inversion for unmanned aerial vehicle[C]//Proc of International Conference on Automatic Control and Artificial Intelligence. 2012:355-358.   
[4]Raffo G V, Ortega M G,Rubio F R.Robust nonlinear control for path tracking of a quad-rotor helicopter[J].Asian Journal of Control,2015,17 (1): 142-156.   
[5]Tan Lining,Lu Libin,Jin Guodong.Attitude stabilization control of a quadrotor helicopter using integral Backstepping[C]//Proc of International Conference on Automatic Control and Artificial Intelligence.2012: 573-577.   
[6]De monte P,Lohmann B.Trajectory tracking control for a quadrotor helicopter based on backstepping using a decoupling quaternion parametrization [C]//Proc of the 21st Mediterranean Conference on Control & Automation.2013:507-512.   
[7]刘一莎，杨晟萱，王伟．四旋翼飞行器的自抗扰飞行控制方法[J].控 制理论与应用,2015,32(10):2-5.   
[8]杨立本，章卫国，黄得刚.基于ADRC姿态解耦的四旋翼飞行器鲁棒轨 迹跟踪[J].北京航空航天大学学报.2015,41(6):1026-1033.   
[9]叶孝璐，俞立，张文安等．基于串级 ADRC 的四旋翼飞行器悬停控制 [J]．中南大学学报：自然科学版,2017,48(8):2079-2087.   
[10]韩京清．从PID技术到“自抗扰控制”技术[J].控制工程,2002,9(3): 13-17.   
[11]张立明．自抗扰控制技术在AUV 航向控制中的应用[D].哈尔滨：哈 尔滨工程大学,2009.   
[12]Kennedy J,Eberhart R.Particle swarm optimization $[ \mathrm { C } ] / \hbar$ Proc of IEEE International Conference on Neural Networks.1995:1942-1948.   
[13] Eberhart R,Kennedy J.A New Optimizer Using Particle Swarm Theory [C]//Proc of the 6th International Symposium on Micro Machine and Human Science.1995:39-43.   
[14]张万绪，张向兰，李莹．基于改进粒子群算法的智能机器人路径规划 [J]．计算机应用,2014,34(02):510-513.   
[15]田佳，胡威，李琳，柯鹏，张凯．基于粒子群优化算法的多核处理器任 务调度研究[J].计算机应用研究,2017,34(12):3698-3700.   
[16] Shi Yuhui,Eberhart R.A Modified Particle Swarm Optimizer [C]//Proc of IEEE International Conference on Evolutionary Computation.1998: 69-73.