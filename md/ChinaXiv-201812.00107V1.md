# 倒立摆的自适应积分反步控制策略

刘成基，陶玉帆，郭思雯，陈艺航(中国矿业大学(北京）机电与信息工程学院，北京100083)

摘要：针对直线单级倒立摆在模型参数不确定和外部扰动情况下的稳定控制问题，提出一种自适应积分反步控制策略，采用拉格朗日方程建立倒立摆系统的运动学模型。为减少稳态误差，将误差积分项引入反步法，设计了倒立摆的控制器。对含有未知参数的系统非线性状态微分方程，设计适当的 Lyapunov 函数推导出系统未知参数的自适应更新律，消弱了参数不确定性的影响。将自适应积分反步控制与一般的反步法控制，模糊控制及神经网络控制的仿真结果进行了对比，并在LabVIEW开发环境下进行了实物实验。结果表明，自适应积分反步法可以较为迅速且精确地完成稳定控制，较好地克服系统参数不确定及外部扰动的影响，具有较强的鲁棒性

关键词：倒立摆；不确定性；自适应控制；积分反步法中图分类号：TP273 doi: 10.19734/j.issn.1001-3695.2018.07.0534

Adaptive integral backstepping control strategy for inverted pendulum

Liu Chengji, Tao Yufan, Guo Siwen, Chen Yihang (SchoolofMechanicalElectronic&InformationEngineering,China UniversityofMining&Technology,Beijing00083, China)

Abstract:This paper proposed anadaptive integral backsteppngcontrol strategy to solve the stabilitycontrol problemof inverted pendulum system with uncertain model parameters and external disturbance.It established the kinematics modelof inverted pendulum systembyusingLagrangeequation.Inordertoreduce the steadystate error,itintroduced errorintegral termintobackstepping method todesignthecontrollerofinverted pendulum.Forthe nonlinear statediferential equations of system with unknown parameters,it designed a proper Lyapunov function to derive an adaptive update law for he unknown parametersofthe system,and weakened the influenceof parameter uncertainty.Then itcompared the simulation resultsof adaptive integral backsteppngcontrol with resultsof generalbacksteppingcontrol,fuzzycontroland neural network controland carredoutthe physical experiments inthe LabVIEWdevelopment environment.Theresults show that the adaptive integral backstepping method which has good robustness can complete thestabilitycontrol quickly and accurately,itcan also overcome the uncertaintyof the system parameters and the influence of external disturbance.

Key words: inverted pendulum; uncertainty; adaptive control; integral backstepping

# 0 引言

倒立摆系统作为控制领域的一种重要研究平台具有非线性、欠驱动、不稳定、强耦合等特点。近年来，很多学者对倒立摆系统的稳定控制进行了大量的研究[1-3],主要的控制方法包括线性化控制方法，如PID，LQR等；变结构控制方法，如滑模控制等；智能控制方法，如模糊控制，神经网络控制等。文献[4,5]应用PID和LQR控制方法来控制非线性倒立摆系统，将线性理论控制方法应用于线性化处理过的倒立摆模型，但其局限性在于要求系统线性化后误差较小、模型简单。考虑到倒立摆系统的非线性特点，为消弱不确定性的影响，文献[6]在滑模控制的基础上，对其切换增益进行参数模糊化，取得了一定的控制效果。模糊控制虽然不需要精确的数学模型，但常规模糊控制策略的局限在于难以建立起完善的模糊控制规则来保证其控制效果，需要结合其他控制方法，如LQR和PID 等[7,8]。因此文献[9]基于模糊控制加入了参数自调整的思想，根据误差及其变化率，对模糊控制参数进行在线自调整，取得了较好的控制效果。

反步法是一种构造性方法，具有较强的系统性、结构性和灵活性，在设计一大类严格参数非线性系统的自适应控制器时十分有效。其作为一种非线性控制的设计工具，不仅能够避免取消一些有用的非线性特性，而且镇定函数及控制Lyapunov函数的选择亦非常灵活；反馈控制律及相关控制Lyapunov函数的构造是系统的,能够较好地处理系统常参数不确定性和一般的不确定性干扰[10]。其设计思路为，将整个系统分解成不超过系统阶数的多个子系统，从高阶系统的内核开始，逐步设计每个子系统各自的控制律，最终递推出整个系统的控制律。

本文首先应用拉格朗日方程建立倒立摆系统的运动学模型[]，区别于传统的反步法，将误差积分环节加入到控制器的设计当中。通过为每个子系统单独设立适当的积分函数，在每个误差变量当中增加了积分项，减少了系统的稳态误差[12-15]。然后将自适应控制与反步法相结合，针对控制器中参数的不确定性，运用所设计的自适应律实现对控制器中不确定参数的在线估计，补偿了系统参数不确定性的影响，并且在倒立摆受到外部扰动时，自适应律会实时调整输入参数，从而实时改变控制器的输入，使得自适应积分反步法比传统反步法拥有更强的抗扰动性能，极大的增强了系统的鲁棒性。最后通过与传统反步法，模糊控制和神经网络控制的仿真对比及LabVIEW下的实物实验，验证了该方法的优越性。

# 1 倒立摆的运动学模型

本文以直线单级倒立摆为研究对象，采用拉格朗日方程建立了系统运动学模型。拉格朗日方程不需要牛顿定律，不必考虑约束力，使力学问题的运算简化，避免了繁琐的计算。将系统的运动学模型转换为运动控制二阶模型，再利用反步法建立倒立摆系统控制器。直线倒立摆的模型如图1所示。

![](images/16f6d4d4c347ae543028d98a640a57a83ae4241071170a358d97df4b24670fc9.jpg)  
图1倒立摆受力分析示意图  
Fig.1Diagram of force analysis of inverted pendulum

$F$ 为作用在小车上的力， $M$ 和 $m$ 分别为小车和摆杆的质量， $\mathbf { \xi } _ { l }$ 为摆杆质心到摆杆和小车铰接点的长度， $\theta$ 为摆杆与竖直方向的夹角， $x$ 为小车的位置， $g$ 为重力加速度， $f$ 为小车和轨道的摩擦力。

对于系统模型进行分析时，由于摆杆和小车铰接处的摩擦力对系统影响较小，这里忽略不计。系统拉格朗日方程如下：

$$
\frac { d } { d t } \bigg ( \frac { \hat { \sigma } T } { \hat { \sigma } \dot { q } _ { i } } \bigg ) - \frac { \hat { \sigma } T } { \hat { \sigma } q _ { i } } + \frac { \hat { \sigma } V } { \hat { \sigma } q _ { i } } + \frac { \hat { \sigma } \rho } { \hat { \sigma } q _ { i } } = F _ { q _ { i } }
$$

其中： $T$ 为系统动能； $\boldsymbol { V }$ 为系统势能； $\rho$ 为摩擦消耗能量； $q _ { i }$ 为广义坐标。摆杆动能为

$$
T _ { 1 } = { \frac { 1 } { 2 } } I \dot { \theta } ^ { 2 } + { \frac { 1 } { 2 } } m \{ [ { \frac { d } { d t } } ( l \cos \theta ) ] ^ { 2 } +
$$

$$
[ \frac { d } { d t } ( x + l \sin \theta ) ] ^ { 2 } \}
$$

小车动能为

$$
T _ { 2 } = { \frac { 1 } { 2 } } M { \dot { x } } ^ { 2 }
$$

以摆杆和小车铰接点水平面为0势能面。摆杆势能为

$$
V _ { 1 } = m g l \cos { \theta }
$$

小车势能在运动过程中不变。当 $q _ { i } = x$ 时，拉格朗日方程为(这里忽略摩擦力)

$$
F = ( M + m ) { \ddot { x } } + m l { \ddot { \theta } } \cos \theta - m l { \dot { \theta } } ^ { 2 } \sin \theta
$$

当 $q _ { i } = \theta$ 时，拉格朗日方程为

$$
( I + m l ^ { 2 } ) { \ddot { \theta } } + m l { \ddot { x } } \cos \theta - m g l \sin \theta = 0
$$

结合式(5)(6)得到力 $F$ 和角度 $\theta$ 的关系方程为

$$
\begin{array} { r } { F = - \lambda _ { 1 } \ddot { \theta } \sec \theta + \lambda _ { 2 } \tan \theta + \lambda _ { 3 } \left( \ddot { \theta } \cos \theta - \dot { \theta } ^ { 2 } \sin \theta \right) } \end{array}
$$

式(7)为带有未知参数的系统方程，其中 $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ ， $\lambda _ { 3 }$ 分别为

$$
\lambda _ { 1 } { = } \frac { ( M + m ) ( I + m l ^ { 2 } ) } { m l }
$$

$$
\lambda _ { 2 } = ( M + m ) g
$$

$$
\lambda _ { 3 } = m l
$$

# 2 自适应积分反步控制器设计

# 2.1控制器设计

倒立摆的控制器设计可以分为以下四步：

a)根据倒立摆模型方程式(7)\~(10)得到系统的状态方程式(11)\~(13)。

定义误差变量 $\mathbf { \Psi } _ { e }$ ，设计积分项(15)保证 $\boldsymbol { \mathscr { e } }$ 的渐进稳定，得到中间虚拟控制量。

为保证 $z$ 渐进稳定，设计积分函数式(19)。

b)由式(18)(19)得到系统稳定控制器式(20)。

令 $x _ { 1 } = \theta$ ， $x _ { 2 } = \dot { \theta }$ 得到式(7)的状态空间方程

$$
{ \dot { x } } _ { 1 } = x _ { 2 }
$$

$$
{ \dot { x } } _ { 2 } = { \frac { F - \lambda _ { 2 } \tan x _ { 1 } + \lambda _ { 3 } x _ { 2 } ^ { 2 } \sin x _ { 1 } } { h ( x _ { 1 } ) } }
$$

其中:

$$
h ( x _ { 1 } ) = - \lambda _ { 1 } \sec x _ { 1 } + \lambda _ { 3 } \cos x _ { 1 }
$$

首先定义误差变量为

$$
e = x _ { d } - x _ { 1 }
$$

$x _ { 1 }$ 为希望得到的系统稳定时摆杆与竖直方向夹角,为使系统渐进稳定，首先选用如下积分函数

$$
z = \dot { e } + k _ { \mathrm { 1 } } e
$$

得到虚拟控制量 $z$ ，当 $z$ 收敛至0时，有 $\dot { e } = - k _ { \mathrm { 1 } } e$ ，误差 $\boldsymbol { \mathscr { e } }$ 渐近收敛至0，其中 $k _ { \scriptscriptstyle 1 }$ 为误差增益且 $k _ { 1 } > 0$ ，求 $z$ 的微分得

$$
\dot { z } = \ddot { e } + k _ { \mathrm { 1 } } \dot { e }
$$

进而得到

$$
\dot { z } = \dddot { x } _ { d } - \dot { x } _ { 2 } + k _ { 1 } \dot { e }
$$

根据系统模型式(12)，将 ${ \dot { x } } _ { 2 }$ 代入式(17)得

$$
\dot { z } = \dddot { x } _ { d } + \frac { - F + \lambda _ { 2 } \tan x _ { 1 } - \lambda _ { 3 } \dot { x } _ { 1 } ^ { 2 } \sin x _ { 1 } } { h ( x _ { 1 } ) } + { \bf k } _ { 1 } \dot { e }
$$

为了使 $z$ 收敛至 $0$ ，这里再次设计积分函数

$$
\dot { z } = - \frac { k _ { 2 } z } { h ( x _ { 1 } ) }
$$

积分作用保证了 $z$ 的收敛性，其中 $k _ { 2 }$ 为控制量 $z$ 的增益且 $k _ { 2 } > 0$ 。由式(18)和(19)联立得到下式：

$$
\begin{array} { r } { F = k _ { 2 } z + \lambda _ { 2 } \tan x _ { 1 } - \lambda _ { 3 } \dot { x } _ { 1 } ^ { 2 } \sin x _ { 1 } + ( \ddot { x } _ { d } + k _ { 1 } \dot { e } ) ( - \lambda _ { 1 } \bullet } \end{array}
$$

$$
\sec x _ { 1 } + \lambda _ { 3 } \cos x _ { 1 } )
$$

式(20)即为系统的控制器。

# 2.2自适应律的推导

自适应控制所讨论的对象通常结构已知，参数未知，对于模型的和扰动的先验知识较少，在系统的运行过程中不断提取有关模型的信息，使参数不断更新，趋近于真实值。这里结合Lyapunov 稳定性定理设计估计参数的更新律。设 $\lambda _ { 1 }$ ，$\lambda _ { 2 }$ ， $\lambda _ { 3 }$ 的估计值分别为 $\hat { \lambda } _ { \scriptscriptstyle 1 }$ ， $\hat { \lambda } _ { 2 }$ ， $\hat { \lambda } _ { 3 }$ ，由式(20)得到下式:

$$
F = k _ { 2 } z + { \hat { \lambda } } _ { 2 } \tan x _ { 1 } - { \hat { \lambda } } _ { 3 } { \dot { x } } _ { 1 } ^ { 2 } \sin x _ { 1 } +
$$

$$
( { \ddot { x } _ { d } } + k _ { 1 } { \dot { e } } ) ( - { \hat { \lambda } _ { 1 } } \sec x _ { 1 } + { \hat { \lambda } _ { 3 } } \cos x _ { 1 } )
$$

这里未知参数的估计误差为 $\widetilde { \lambda } _ { 1 } = \lambda _ { 1 } - \widehat { \lambda } _ { 1 }$ ， $\widetilde { \lambda } _ { 2 } = \lambda _ { 2 } - \widehat { \lambda } _ { 2 }$ ， $\hat { \lambda } _ { 3 } = \lambda _ { 3 } - \hat { \lambda } _ { 3 }$ ，将式(21)代入式(18)得

$$
\begin{array} { r } { \dot { z } = \dddot { x } _ { d } + k _ { 1 } \dot { e } + [ - k z + \tilde { \lambda } _ { 2 } \tan x _ { 1 } - \tilde { \lambda } _ { 3 } \dot { x } _ { 1 } ^ { 2 } \sin x _ { 1 } - } \\ { \qquad } \\ { ( - \hat { \lambda } _ { 1 } \sec x _ { 1 } + \hat { \lambda } _ { 3 } \cos x _ { 1 } ) ( \ddot { x } _ { d } + k _ { 1 } \dot { e } ) ] / h ( x _ { 1 } ) } \end{array}
$$

为求得 $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ ， $\lambda _ { 3 }$ 的自适应更新律，定义Lyapunov 函

数

$$
V = \frac { 1 } { 2 } z ^ { 2 } h ( x _ { 1 } ) + \frac { \tilde { \lambda } _ { 1 } ^ { 2 } } { 2 \alpha _ { 1 } } + \frac { \tilde { \lambda } _ { 2 } ^ { 2 } } { 2 \alpha _ { 2 } } + \frac { \tilde { \lambda } _ { 3 } ^ { 2 } } { 2 \alpha _ { 3 } }
$$

$\alpha _ { 1 } , \alpha _ { 2 } , \alpha _ { 3 }$ 为自适应增益常量,且 $\alpha _ { \mathrm { { \scriptscriptstyle i } } } > 0$ ， $\alpha _ { 2 } > 0$ ， $\alpha _ { 3 } > 0$ 。对式(23)两边关于时间求导,则有

$$
\dot { V } = z \dot { z } h ( x _ { 1 } ) + \frac { \tilde { \lambda } _ { 1 } \dot { \hat { \lambda } } _ { 1 } } { \alpha _ { 1 } } + \frac { \tilde { \lambda } _ { 2 } \dot { \hat { \lambda } } _ { 2 } } { \alpha _ { 2 } } + \frac { \tilde { \lambda } _ { 3 } \dot { \hat { \lambda } } _ { 3 } } { \alpha _ { 3 } }
$$

将式(13)和(22)代入，则有

$$
\dot { V } = - k z ^ { 2 } + \widetilde { \lambda } _ { 1 } [ \frac { \dot { \hat { \lambda } } _ { 1 } } { \alpha _ { 1 } } - z ( \dddot { x } _ { d } + k _ { 1 } \dot { e } ) \sec x _ { 1 } ] + \widetilde { \lambda } _ { 2 } ( z \tan x _ { 1 } + \frac { \dot { \hat { \lambda } } _ { 2 } } { \alpha _ { 2 } } ) +
$$

$$
\tilde { \lambda } _ { 3 } [ z ( \ddot { x } _ { d } + k _ { 1 } \dot { e } ) \cos x _ { 1 } - z \dot { x } _ { 1 } ^ { 2 } \sin x _ { 1 } + \frac { \dot { \hat { \lambda } } _ { 3 } } { \alpha _ { 3 } } ]
$$

由Lyapunov 稳定性定理可知，为了使系统渐近稳定，需满足 $\dot { V } \le 0$ 。所以只需使

$$
{ \frac { \dot { \hat { \lambda } } _ { 1 } } { \alpha _ { 1 } } } - z ( \dddot { x } _ { d } + k _ { 1 } \dot { e } ) \sec x _ { 1 } = 0
$$

$$
z \tan x _ { 1 } + { \frac { \dot { \hat { \lambda } } _ { 2 } } { \alpha _ { 2 } } } = 0
$$

$$
z ( \ddot { x } _ { d } + k _ { 1 } \dot { e } ) \cos x _ { 1 } - z \dot { x } _ { 1 } ^ { 2 } \sin x _ { 1 } + \frac { \dot { \hat { \lambda } } _ { 3 } } { \alpha _ { 3 } } = 0
$$

由此得到

$$
\dot { \hat { \lambda } } _ { 1 } = \alpha _ { 1 } z ( \ddot { x } _ { d } + k _ { 1 } \dot { e } ) \sec x _ { 1 }
$$

$$
\dot { \hat { \lambda } } _ { 2 } = - \alpha _ { 2 } z \tan x _ { 1 }
$$

$$
\begin{array} { r } { \dot { \hat { \lambda } } _ { 3 } = \alpha _ { 3 } z \Big [ \dot { x } _ { \scriptscriptstyle 1 } ^ { 2 } \sin x _ { \scriptscriptstyle 1 } - ( \ddot { x } _ { \scriptscriptstyle d } + k _ { \scriptscriptstyle 1 } \dot { e } ) \cos x _ { \scriptscriptstyle 1 } \Big ] } \end{array}
$$

此即参数 $\hat { \lambda } _ { 1 }$ ， $\hat { \lambda } _ { 2 }$ ， $\hat { \lambda } _ { 3 }$ 的自适应更新律。

# 3 系统仿真

# 3.1仿真模型与参数设置

根据建立的直线单级倒立摆运动学模型和设计的自适应积分反步控制器，应用MATLAB/Simulink构建控制系统，并对其控制器和倒立摆模型部分进行封装，主要包括积分反步控制器，参数自适应器和倒立摆三个部分如图2所示。

仿真中倒立摆系统模型物理参数如表1所示。

表1倒立摆参数  
Table1 Inverted pendulum parameters   

<html><body><table><tr><td>物理量</td><td>参数值</td></tr><tr><td>小车质量M</td><td>0.46kg</td></tr><tr><td>摆杆质量m</td><td>0.21kg</td></tr><tr><td>摆杆质心到铰接点长度1</td><td>0.3m</td></tr><tr><td>重力加速度g</td><td>9.8m/s²</td></tr></table></body></html>

误差 $\boldsymbol { \mathscr { e } }$ 的增益和控制量<的增益通过不断试测，分别设置为 $k _ { \mathrm { 1 } } = 1 0$ ， $k _ { 2 } = 2 . 5$ 。

![](images/ed4673d69c6300e1128691c1b1c82053b2caae078fe0ea1a2055efc61938ee9b.jpg)  
图2MATLAB/Simulink 控制框图  
Fig.2MATLAB/Simulink control block diagram

# 3.2仿真结果

为验证本文自适应积分反步法控制的快速准确性，抗扰动性及适应参数不确定性的能力，将其和一般反步法、模糊控制法及神经网络控制法分别在无扰动和有扰动条件下进行仿真实验，然后将实验结果进行对比。模糊控制系统为2输入1输出，有49条控制规则,论域范围为[-10,10]。神经网络控制为双层网络。

实验1无扰动时四种方法的平衡控制

在初始角度为0.1rad的条件下，进行无扰动的平衡控制实验，结果如图3所示。自适应积分反步法、一般反步法、模糊控制法及神经网络控制法四种方法的稳定时间分别为1.5s，2.2s,2.5s，3.4s；稳态误差分别为 $2 . 5 { \times } 1 0 ^ { - 5 } \mathrm { r a d } , 3 { \times } 1 0 ^ { - 5 } \mathrm { r a d }$ ，

$5 { \times } 1 0 ^ { - 5 } \mathrm { r a d } , 6 . 5 { \times } 1 0 ^ { - 4 } \mathrm { i }$ rad;超调量分别为0.007rad，0.015rad,0.034rad，0.044rad。结果表明四种方法均实现了倒立摆的平衡控制，本文方法的稳定时间比其他三种方法分别短了0.7s，1s和1.3s，系统收敛速度更快，稳态误差比一般反步法更小，超调量也比其他三种方法小。

实验2有扰动时四种方法的平衡控制

为验证所设计控制器的抗扰动能力，进行加入扰动的平衡控制实验。系统稳定后加入一个宽度为0.1s，幅值为0.1rad的脉冲扰动，响应结果如图4所示。自适应积分反步法在4.7s时稳定，相比一般反步法、模糊控制法及神经网络控制法的稳定时间分别快了0.5s，1.2s，2.7s；同时其最大波动幅度在四种方法中也最小，仅为0.7rad，相比幅度最大的神经网络控制 $1 . 9 \mathrm { r a d }$ ，减少了1.2rad；且本文方法在一个小的波动后就稳定至0rad，而其他方法需经历多次回调才能稳定下来，本文方法相比于其他几种方法系统响应速度更快，抗干扰能力更优。

![](images/eee35b2d97203526b7f8478afaf95a512b21cd11aae1c0927a7c4f5334e85299.jpg)  
图3初始角为0.1rad 的摆杆角度响应

![](images/58fbe05dde08e8cab89c09a0a28a7ca40929ec096b67c3eb913650be826e2197.jpg)  
Fig.3Angle response of pendulum with an initial angle of O.lrad

实验3无扰动时控制器的参数自适应控制

通过设置不同摆杆初始角度 $\theta$ ，检验自适应积分反步法对不确定参数的自适应性。初始摆杆角度为 $5 ^ { \circ }$ （实线）， $1 0 ^ { \circ }$ （虚线）和 $1 5 ^ { \circ }$ （点线）。在MATLAB中运行得到仿真结果如图5\~10所示。

图5为摆杆角度响应，初始值越大超调也越大。图6为虚拟控制量z，积分作用使其收敛至0;图7为控制器输出 $F$ 的响应曲线，其变化趋势与虚拟控制量 $z$ 接近;图8\~10分别为参数， $\lambda _ { 2 }$ ， $\lambda _ { 3 }$ 的估计值，由图中可以看出3种条件下的参数估计值在有限时间内均收敛至恒定值，说明根据系统状态响应，设计的自适应控制器可以在线估计出系统的不确定参数[16并调整控制器输出，使系统具备了适应不同未知参数的能力。

![](images/672d5ea0513b7476ace8d0fc9fbae73d1bc6e8e1a38d5ff53ba72a7463d91528.jpg)  
图4加入干扰的摆杆角度响应  
图5摆杆角度响应 Fig.5Angle response of pendulum

![](images/84ea6c12f8e23cff0cc10010307a4af606e5ef7c7c7fbf4176111c61fa70255f.jpg)  
图6虚拟控制量z

![](images/3cbee5355901024c7fd507ee7520a8ab9c46c746916432409de842afe7bfc26a.jpg)  
Fig. 6Virtual control volume z  
图7控制器输出F

![](images/8d8b68ea16280d7b7ecb03594ff35977c61ccdbc2d7aff69713a475f93b2c0f6.jpg)  
Fig.4Angle response of pendulum with interference   
图8参数的估计值

![](images/1d1b33edeec66eca29aca5d2eba4a42c94cc5580c564f93ba7ee4a2057e473f1.jpg)  
Fig.7Controller output F   
Fig.8Estimated value of parameter $\lambda _ { 1 }$   
图9参数 $\lambda _ { 2 }$ 的估计值  
Fig.9Estimated value of parameter $\lambda _ { 2 }$

![](images/dc5159e93ae6357033d1e4cc2437944d705ca8b422a610eb392905ab0d4907ba.jpg)  
图10参数的估计值

# 4 LabVIEW实验

实物控制实验在LabVIEW开发环境下进行，实验平台如图11所示。倒立摆控制系统主要由角度编码器，步进电机，倒立摆摆杆及滑轨，数据采集卡，计算机，直流开关电源(12V)等。OMRONE6B2-CWZ6C编码器通过2路数字通道连接至数据采集卡传输摆杆角度信号。57步进电机通过3路数字通道连接数据采集卡，1路传输频率信号控制转速，2路传输方向信号控制电机转向。NIUSB-6210数据采集卡和计算机相连接进行数据交互。

LabVIEW程序主要包括输入模块，控制器模块和输出模块。输入模块主要由DAQ助手VI程序组成，通过DAQ助手接收数据采集卡传入的包含编码器角度信息的2路信号，设置信号通道属性为角度位置，编码器每转脉冲数为600，初始角为 $1 8 0 ^ { \circ }$ 。控制器模块内封装了控制器的VI程序。输出模块通过 $\mathrm { \Delta D A Q m x \ V I }$ 程序控件将3路信号输出，其中一路"CO 脉冲频率”输出频率信号，用以控制步进电机的转速，另外两路”数字输出“控制电机转动方向。“Frequency”输入框用以输入电机初始频率，“Counter(s)”用以选择使用的输出端口，“IdleState”用于选择系统处于无输入的空闲状态时电位的高低，“InitialDelay”用以输入控制程序运行之前的延时时间。如图12所示。图12中黑色方框为while循环体，其内部为需要循环计算的控制器模块，输入模块和输出模块。While 循环的步长为每10ms计算一次。

![](images/32ac42286eef6afbae0ff57e5935bf9153cce9dcfdd1af2c3e9bd7bf861ac990.jpg)  
图11倒立摆实验平台

![](images/1950effd70d1af525ccff4f8ec0e725e30d9786e9c3798c9ef78962623950cff.jpg)  
Fig.1OEstimated value of parameter $\lambda _ { 3 }$   
图12LabVIEW控制系统程序框图

![](images/8f0d728e82996dc636b225696019675ef15eb670010ff748cd04955a38bc816a.jpg)  
Fig.12Labview control system block diagram   
图13无干扰时摆杆角度响应  
Fig.13Angle response of pendulum without disturbance

![](images/22e33a90d2056fa739aed0525ab0457913913865723ddf4e9dd27f2860c82dfb.jpg)  
Fig.11Inverted pendulum experiment platform   
图14加干扰时的摆杆角度响应  
Fig.14Angle response of pendulum with interference

在无干扰条件下，设定初始摆杆角度为 $0 . 2 \mathrm { r a d }$ ，摆杆角度响应波形如图13所示。由图13可以看出：摆杆角度在2s内稳定至0rad，期间有小幅超调，幅度小于 $0 . 0 2 \mathrm { r a d }$ ，之后稳定在0rad附近，在竖直方向上保持稳定动态平衡。待系统稳定后在4s时人为（用手）施加一个干扰，平衡控制结果如图14所示，可以看出系统的抗干扰能力强、动态性能好、准确度高。与仿真结果相比，实物控制过程稳定时间略有滞后，并且有小幅超调，稳定时间基本符合。

# 5 结束语

针对具有参数不确定性及外界扰动的直线单级倒立摆系统，提出了一种自适应积分反步控制策略。对系统模型状态方程进行分析，基于反步法设计了系统的积分型反步控制器，且设计的自适应估计律可实现对不确定参数的在线估计。误差积分项的加入使得稳态误差相比传统反步法更小。在无扰动和有扰动条件下的仿真和实物控制结果表明，本文设计的自适应积分反步法可以快速有效地估计出一组系统参数，消弱了系统参数不确定性的影响，提高了系统的抗干扰能力，且控制过程快速准确，鲁棒性强。在今后研究中，将考虑数学模型中省略的摩擦项等影响因素，并结合其他方法进一步改进控制器的设计，以达到更精确的控制效果。

# 参考文献：

[1]王瑶为，邢科新，马剑，等．直线一级倒立摆的自抗扰控制方法及实 现[J].控制工程,2017,24(4):711-715.(Wang Yaowei,Xing Xinke, Ma Jian,et al.Implementation and Design of Active Disturbance Rejection Control for the Linear Inverted Pendulum [J].Control Engineering of China,2017,24(4):711-715.)   
[2]Jiang Shuhua,Li Mingqiu,Wang Chunyang.Design and simulation of fractional order PID controller for an inverted pendulum system [C]// Proc of International Conference on Manipulation Manufacturing and Measurement on the Nanoscale.Piscataway,NJ:IEEE Press,2017: 349-352.   
[3]Lee Haiwu.Performance the balance of circular inverted pendulum by usingLQR controlled theory[C]//Proc of IEEE International Conference on Consumer Electronics.Piscataway,NJ:IEEE Press,2017: 415-416.   
[4]Prasad LB,Tyagi B,Gupta H O.Optimal control of nonlinear inverted pendulum system using PID controller and LQR:performance analysis without and with disturbance input [J]. International Journal of Automation and Computing,2014,11(6): 661-670.   
[5]Sarkar T T,Dewan L.Application of LQR and MRAC for swing up control of inverted pendulum [C]//Proc of International Conference on Power,Control & Embedded Systems.Piscataway,NJ:IEEE Press, 2017: 1-6.   
[6]张蛟龙，张伟．不确定性倒立摆系统的自适应模糊滑模控制[J].计 算机仿真，2013,30(10):341-344,398.(Zhang Jiaolong，Zhang Wei. Research on adaptive fuzzy sliding mode control for uncertain inverted pendulumsystem[J]. ComputerSimulation，2013， 30(10): 341-344,398.)   
[7]Molazadeh V R,Banazadeh A,Shafieenejad I. Design of the LQR controller and observer with fuzzy logic GA and GA-PSO algorithm for triple an inverted pendulum and cart system [C]// Proc of International Conference on Advanced Mechatronic Systems.Piscataway,NJ:IEEE Press,2014:295-300.   
[8]Paliwal S,Chopra V,Singla S K. Stabilization of mobile inverted pendulum using fuzzy PID controllers [C]/Proc of the 7th India International Conference on Power Electronics.Piscataway,NJ:IEEE Press,2016: 1-4.   
[9]郑海平，钟晨星，吴利平，等．基于增益调度型参数自调整的倒立摆 模糊控制[J]．华中科技大学学报:自然科学版，2013,41(1):5-8. (Zheng Haiping,Zhong Chenxing，Wu Liping，et al.Fuzzy control based on parameter self-tuning with gain scheduling for an inverted pendulum [J].Journal of Huazhong University of Science and Technology:Natural Science Edition ,2013,41(1): 5-8.)   
[10] Gandhi P S,Borja P,Ortega R.Energy shaping control of an inverted flexible pendulum fixed to a cart [J]. Control Engineering Practice, 2016,56:27-36.   
[11]张萌璐．一阶倒立摆系统的逻辑切换自适应控制算法研究[D].杭 州：浙江大学,2017.(Zhang Menglu.Logic-based switching adaptive stabilization of linear single inverted pendulum system [D].Hangzhou: Zhejiang University,2017.)   
[12] Hoshyar M,Mola M.Full adaptive integral backstepping controller for interior permanent magnet synchronous motors [J].Asian Journal of Control,2018,20(2): 768-779.   
[13] Zhang Chuanlian,Chong Kilto.Quadrotor waypoint navigation and trajectory tracking using integral backstepping technique [C]//Proc of International Conference on Mechanical Engineering and Automation. [S.l.]: DEStech Publications Press,2015: 102-106.   
[14] Zhou Zhongcheng,Yu Changjun,Teo KokLay.some new results on integral-type backstepping method for a control problem governed by a linear heat equation [J]. IEEE Trans on Automatic Control,2O17,62(7): 3640-3645.   
[15] Yue Fengfa，Li Xingfei,Chen Cheng，et al. Adaptive integral backstepping sliding mode control for opto-electronic tracking system based on modified LuGre friction model [J]. International Journal of Systems Science,2017,48 (16): 3374-3381.   
[16]张兴华，唐其太．考虑参数和负载不确定性的内置式永磁同步电机 自适应反步控制[J].控制与决策，2016，31(8):1509-1512.(Zhang Xinghua,Tang Qitai．Adaptive backstepping control of interior permanent magnet synchronous motors considering parameter and load uncertainties [J].Control and Decision,2016,31(8):1509-1512.)