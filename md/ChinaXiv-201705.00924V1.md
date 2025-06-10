# 固定接触角蒸发液滴内Marangoni对流数值模拟

唐甜1 石万元1,2

(1.重庆大学动力工程学院，重庆400044;2.重庆大学低品位能源利用技术及系统教育部重点实验室，重庆400044)

摘要考虑蒸发冷却效应、气相物质扩散、气液两相传热及界面变形，采用任意拉格朗日-欧拉法数值模拟研究了接触角 $\theta$ 、蒸发数 $\mathit { E c }$ 、Ma数对 $\mathrm { 0 . 6 5 c S t }$ 硅油液滴固定接触角模型蒸发及 Marangoni 对流的影响。发现：液滴无量纲体积 $V ^ { * }$ 变化与接触角 $\theta$ 、Ma数有关，而与 $\ E c$ 数无关；且 $V ^ { * 2 / 3 }$ 随时间线性减少。当 $\theta < 0 . 1 7 5$ rad时，随着 $\mathbf { \nabla } \_ { M a }$ 数的升高，液滴内部依次出现热毛细涡流结构、单个BM 涡流结构及多个BM 涡流结构。当 $0 . 1 7 5 ~ \mathrm { r a d } < \theta < 0 . 4 7 9 ~ \mathrm { r a d }$ 时，存在热毛细涡流结构或多个BM 涡流结构或两种同时存在，而无单个 BM 涡流结构。当 $\theta > 0 . 4 7 9$ rad 时，仅存在热毛细涡流结构。当 $0 . 1 0 5 ~ \mathrm { r a d } < \theta < 0 . 4 0 1$ rad 时，每两种涡流结构的分界 $\mathbf { \nabla } \_ { M a }$ 数均随 $\theta$ 增大而减少。当 $\theta > 0 . 4 0 1$ rad 时，热毛细涡流结构与多个BM 涡流结构的分界 $\mathbf { \nabla } \_ { M a }$ 数随 $\theta$ 增大而增大。

关键词液滴蒸发；两相传热；界面变形；Marangoni 对流中图分类号：TK123 文献标识码：A 文章编号:0253-231X(2017)04-0792-08

# Marangoni Convection in Evaporatimg Sessile Droplet With Constant Angle by Numerical Simulation

TANG P SHI Wan-Yuan1,2 (1. College of Power Engineering,Chongqing University， Chongqing 40o044, China; 2.KeyLabratoryofwgradeEergyUchologiesdSystes,stryofducationChongingo

Abstract Taking into acc6ut bf evaporation cooling, mass diffusion, two-phase heat transfer and gas-liquid interface deformation, the evaporation of a droplet of 0.65cSt silicone oil with constant contact angle on a heated substrate is numerically investigated using_Arbitrary Lagrangian-Eulerian method. The effects of contact angle $\theta$ , evaporation number $E c$ and Marangoni number Ma on the evaporation and the Marangoni convection are analyzed. Num@rical results find that the variation of volume $V ^ { * }$ is affected by $\theta$ and $M a$ but not by $E c$ ，andthe $V ^ { * 2 / 3 }$ varies with $t ^ { * }$ linearly. With increasing $M a$ ， the thermocapillary convection， singlyortex Bénard-Marangoni convection (BM convection) and multiple-vortex BM convection appear in sequence for $\theta < 0 . 1 7 5$ rad. Thermocapillary convection or multiple-vortex BM convection or both of them occur for O.175 rad $< \theta < 0 . 4 7 9$ rad but without single-vortex Bénard-Marangoni eonvection. Only thermocapillary convection appears for $\theta > 0 . 4 7 9$ rad. The neutral $M a$ between two kinds of vortex convection decreases with increasing contact angle for O.105 rad $< \theta < 0 . 4 0 1$ rad,while it increases for $\theta > 0 . 4 0 1$ rad.

Key wordsevaporating droplet; two-phase heat transfer; interface deformation; Marangoni convection

# 0引言

液滴蒸发在工程实际中的运用十分普遍，例如：相变冷却技术[1]、喷雾薄膜涂层工艺[2]、打印着色工艺[3]、DNA 芯片制造[4]、DNA分子调整及拉伸[5]、血液沉积疾病诊断技术[6]等。由于液滴为弧形表面，导致液滴表面总存在切向和法向温度梯度。切向温度梯度引起热毛细对流，足够大的法向温度梯度引起Bénard-Marangoni对流 (即BM对流)，文献中不加区分时两者均称为Marangoni对流

液滴蒸发及其内部Marangoni对流的研究大多集中于固定接触线模型(CR 模型)[7-9]，包括液滴蒸发过程的质量变化 (蒸发率)、几何形变 (接触角、液滴高度、体积)、沉积现象、表面温度以及Marangoni对流及其失稳等。其中文献[9采用归一化法研究了几何形变、液滴寿命与润湿半径、基底温度、环境湿度的关系。实际上，由于基底表面特性不同，液滴蒸发除了CR模型外，还有接触角保持不变的情况[10]，即固定接触角模型(CA 模型)，而目前对CA模型下液滴蒸发及其内部 Marangoni 对流的研究相对较少。已有研究主要采用理论和实验的方法，研究了液滴质量[11-13]、液滴体积[13]变化规律及热流体波 (失稳的热毛细对流)的波数与初始液滴几何尺寸、时间的关系[14]。在“one-side”模型下，文献[15]给出了Bénard-Marangoni对流模拟结果，但并没有深入研究。

为此，本文采用任意拉格朗日－欧拉法，数值模拟固定接触角模型情况下加热平面上蒸发液滴内Marangoni对流，主要分析接触角θ、Ec数、Ma数对它的影响。研究对理解固定接触角蒸发液滴内部流动和传热特征具有指导意义。

# 1数学物理模型

# 1.1物理模型

物理模型如图1所示，液滴初始形状为球冠形，初始润湿半径 $R _ { \mathrm { c } } = 2 . 5 ~ \mathrm { m m }$ ，接触角 $\Join { \overset { \underset { \mathrm { 1 1 2 } } { } } { = } } ~ 0 . 1 0 5 ~ \sim$ $0 . 5 2 4 ~ \mathrm { r a d }$ ；基底长度为 $1 . 5 R _ { \mathrm { c } }$ ，气相区域半径为 $6 5 R _ { \mathrm { c } }$ 。模拟考虑蒸发冷却效应、气相物质扩散、气液两相流动及蒸发引起的界面变形。气液两相工质分别为空气、 $0 . 6 5 \mathrm { c S t }$ 硅油，其物性参数如表1所示。

![](images/1ba1f936af1bce312ac8cd4d872a0d12ec9d027cdadbca836329b39d5df4eeb4.jpg)  
图1基底上液滴蒸发物理模型  
Fig.1 Schematic model of evaporating liquid droplet ona fat substrate

表1 $\mathbf { 2 5 } { ^ \circ } \mathbf { C }$ 时0.65cSt 硅油、空气的物性参数[16] Table 1 Physical properties of O.65cSt silicone oil and air at 25 C [16]   

<html><body><table><tr><td>参数</td><td>0.65cSt 硅油</td><td>空气</td></tr><tr><td>密度p/(kg/m)</td><td>760</td><td>1.18</td></tr><tr><td>动力黏度μ/((N·s)/m²)</td><td>4.94×10-4</td><td>1.83×10-5</td></tr><tr><td>导热系数入/(W/(m·K))</td><td>0.1</td><td>0.01</td></tr><tr><td>比热容cp/(J/(kg·K))</td><td>2000</td><td>1004</td></tr><tr><td>表面张力系数σ/(N/m)</td><td>1.52×10-2</td><td>一</td></tr><tr><td>表面张力温度系数ot/(N/(m·K)）9×10-5</td><td></td><td>一</td></tr><tr><td>蒸发潜热Ht/(J/kg)</td><td>2.23×105</td><td>1</td></tr><tr><td>浓度扩散系数D/(m²·s)</td><td>5.60×10-6</td><td></td></tr></table></body></html>

# 1.2数学模型及计算方法

模型采用轴对称模型，基本假设包括：液滴初始形状为球冠形；除表面张力随温度变化以外，其余物性参数均为常数；基底表面为等温边界条件；表面张力在流体流动中占主导作用（ $( B o \sim 0 . 0 1 )$ ，忽略重力的作用气液界面蒸汽浓度为饱和浓度；气、液两相流体均为不可压缩流体。考虑到VOF法难以计算变形较大的问题、而LevelSet法不满足质量守恒，本文借鉴文献[17]的计算方法，采用任意拉格朗日-欧拉方法(ALE)追踪气液界面变形。

# 1.2.1无量纲控制方程

质量守恒方程：

$$
\nabla \cdot \boldsymbol { u } ^ { * } { = } 0
$$

动量守恒方程 液相： D

$$
\overbrace { \boldsymbol { \mathcal { Q } } ^ { \prime } + \mathbf { \lambda } ^ { * } } ^ { \partial \boldsymbol { \mathsf { U } } } + \left( \boldsymbol { \mathsf { u } } _ { \mathrm { c } } ^ { * } \cdot \nabla \right) \boldsymbol { \mathsf { u } } ^ { * } = - \nabla p ^ { * } \pmb { I } + \frac { 1 } { R e _ { \mathrm { l } } } \nabla ^ { 2 } \boldsymbol { \mathsf { u } } ^ { * }
$$

气相：

$$
\frac { \partial \boldsymbol { u } ^ { * } } { \partial t ^ { * } } + \left( \boldsymbol { u } _ { \mathrm { c } } ^ { * } \cdot \nabla \right) \boldsymbol { u } ^ { * } = - \ \frac { 1 } { \rho _ { \mathrm { g } } ^ { * } } \nabla p ^ { * } \boldsymbol { I } + \frac { 1 } { R e _ { \mathrm { g } } } \nabla ^ { 2 } \boldsymbol { u } ^ { * }
$$

能量守恒方程：

液相：

$$
\frac { \partial T ^ { * } } { \partial t ^ { * } } + \left( \pmb { u } _ { \mathrm { c } } ^ { * } \cdot \nabla \right) T ^ { * } \mathrm { = } \frac { 1 } { P e _ { \mathrm { T } 1 } } \nabla ^ { 2 } T ^ { * }
$$

气相：

$$
\frac { \partial T ^ { * } } { \partial t ^ { * } } + \left( \pmb { u } _ { \mathrm { c } } ^ { * } \cdot \nabla \right) T ^ { * } { = } \frac { 1 } { P e _ { \mathrm { T g } } } \nabla ^ { 2 } T ^ { * }
$$

气相扩散方程：

$$
\frac { \partial c ^ { * } } { \partial t ^ { * } } + \left( \pmb { u } _ { \mathrm { c } } ^ { * } \cdot \nabla \right) c ^ { * } = \frac { 1 } { P e _ { \mathrm { D } } } \nabla ^ { 2 } c ^ { * }
$$

其中 $\boldsymbol { u } _ { \mathrm { c } } ^ { * }$ 为流体流动速度与网格移动速度之差： ${ \pmb u } _ { \mathrm { c } } ^ { * } =$ u\*-umesh。

# 1.2.2边界条件

1）流动边界条件a）对称轴采用对称边界条件

液相：

$$
{ \pmb u } ^ { * } \cdot { \pmb n } = 0 , \left[ - p ^ { * } { \pmb I } + \frac { 1 } { R e _ { 1 } } \nabla { \pmb u } ^ { * } \right] \cdot { \pmb n } = 0
$$

气相：

$$
{ \pmb u } ^ { * } \cdot { \pmb n } = 0 , \left[ - p ^ { * } { \pmb I } + \frac { \rho _ { \mathrm { g } } ^ { * } } { R e _ { \mathrm { g } } } \nabla { \pmb u } ^ { * } \right] \cdot { \pmb n } = 0
$$

b)气液界面力平衡条件

法向方向：

$$
\left[ - p ^ { * } I + \frac { \rho _ { \mathrm { g } } ^ { * } } { R e _ { \mathrm { g } } } \nabla { \pmb u } ^ { * } \right] _ { \mathrm { g } } : n { \pmb n } = \left[ - p ^ { * } { \pmb I } + \frac { 1 } { R e _ { \mathrm { l } } } \nabla { \pmb u } ^ { * } \right] _ { \mathrm { l } } : { \pmb n } { \pmb n } +
$$

$$
\left( \frac { 1 } { C a \cdot R e _ { \mathrm { l } } } - \frac { M a _ { T _ { \mathrm { w } } } } { R e _ { \mathrm { l } } ^ { 2 } \cdot P r _ { \mathrm { l } } } \left( T ^ { \ast } - T _ { 0 } ^ { \ast } \right) \right) k ^ { \ast }
$$

切向方向：

$$
\begin{array} { r l r } {  { [ - p ^ { * } I + \frac { \rho _ { \mathrm { g } } ^ { * } } { R e _ { \mathrm { g } } } \nabla \pmb { u } ^ { * } ] _ { \mathrm { g } } : \boldsymbol { n } t = [ \underbrace { - p ^ { * } \pmb { \eta } _ { \mathrm { \tiny ~ R } \mathrm { e } _ { 1 } } ^ { \pmb { \mathcal { R } } + \frac { \lambda _ { \mathrm { e } } ^ { * } } { R e _ { \mathrm { l } } } \nabla \pmb { u } ^ { * } } } _ { \mathrm { V e } _ { 1 } ^ { 2 } \mathrm { V e } _ { \mathrm { l } } ^ { 2 } } ] _ { \mathrm { l } } : \boldsymbol { n } t + \mathrm { \Omega } } } \\ & { } & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { } & { \quad \quad \quad \quad \quad \quad ( - \frac { M a _ { T _ { \mathrm { w } } } } { R e _ { 1 } ^ { 2 } \cdot P r _ { 1 } } ) \nabla _ { \mathrm { s } } T ^ { * } \cdot \boldsymbol { t } \qquad } & { \quad \quad \quad ( 6 - 2 ) } \end{array}
$$

气液界面质量流量与气液相速度关系[19]：

$$
( \pmb { u } _ { \mathrm { l g - g } } ^ { * } - \pmb { u } _ { \mathrm { l g - l } } ^ { * } ) \cdot \pmb { n } = \left( \frac { 1 } { \rho _ { \mathrm { g } } ^ { * } } - 1 \right) ( \pmb { n } \cdot \nabla c ^ { * } )
$$

其中，“：”为张量双点积运算符， $\ " { \mathbf { \Omega } } ^ { \ast } \mathbf { \Omega } ^ { \ast }$ 和 $^ { \ast } t ^ { \ast }$ 代表界面外法向单位向量和切向单位向量，“nn”、“nt”为它们的并矢。曲率 $k ^ { * } = R _ { \mathrm { c } } / r _ { \mathrm { c } }$ ， $r _ { \mathrm { c } }$ 为曲率半径。

c）液固、气固界面采用Naver-slip 滑移边界条件

液固界面：

$$
\left[ - p ^ { * } \pmb { I } + \frac { 1 } { R e _ { 1 } } \nabla \pmb { u } ^ { * } \right] _ { 1 } : \pmb { n } \pmb { t } = - \frac { 1 } { R e _ { 1 } } \frac { \pmb { u } ^ { * } } { \beta ^ { * } } \cdot \pmb { t }
$$

气固界面：

$$
\left[ - p ^ { * } \pmb { I } + \frac { 1 } { R e _ { \mathrm { g } } } \nabla \pmb { u } ^ { * } \right] _ { 1 } : \pmb { n } \pmb { t } = - \frac { 1 } { R e _ { \mathrm { g } } } \frac { \pmb { u } ^ { * } } { \beta ^ { * } } \cdot \pmb { t }
$$

其中， ${ \beta ^ { * } } \mathrm { { = } } \beta / R _ { \mathrm { c } }$ 为无量纲滑移长度， $\beta$ 为滑移长度。

d）气相外边界采用定压边界条件

$$
p _ { \infty } ^ { * } = 0
$$

2）传热边界条件

a）对称轴采用对称边界条件

$$
- { \pmb n } \cdot ( \nabla T ^ { * } ) = 0
$$

b）气液界面能量平衡边界条件

$$
\pmb { n } \cdot \Big [ \big ( \lambda _ { \mathrm { g } } ^ { * } \nabla T ^ { * } \big ) _ { \mathrm { g } } - \big ( \nabla T ^ { * } \big ) _ { 1 } \Big ] = E c \left( - \pmb { n } \cdot \left( - \nabla c ^ { * } \right) \right)
$$

c）气相外边界采用恒温边界条件

$$
T _ { \infty } ^ { * } = 0
$$

d)基底采用等温边界条件

$$
T _ { \mathrm { w } } ^ { * } = 1
$$

3)气相的浓度边界条件

a）对称轴采用对称边界条件

$$
- \pmb { n } \cdot \left( - \nabla c ^ { * } \right) = 0
$$

b）气液界面采用饱和浓度边界条件

$$
c _ { \mathrm { l g - g } } ^ { \mathrm { * } } = \frac { c _ { \mathrm { l g - g } } - c _ { \infty } } { c _ { \mathrm { s a t } } - c _ { \infty } }
$$

c）气相外边界采用恒定浓度边界条件

e

$$
c _ { \infty } ^ { * } = 0
$$

d轴上采用无通量边界条件

$$
- \pmb { n } \cdot \left( - \nabla c ^ { * } \right) = 0
$$

# 1.2.3 初始条件

$$
\begin{array} { r } { \pmb { u } _ { \mathrm { t = 0 } } ^ { * } = 0 , \quad p _ { \mathrm { t = 0 } } ^ { * } = 0 , \quad T _ { \mathrm { t = 0 } } ^ { * } = 0 , \quad c _ { \mathrm { t = 0 } } ^ { * } = 0 } \end{array}
$$

方程中几何尺寸、速度、时间、压力、密度、黏度、导热系数的无量纲尺度分别为 $R _ { \mathrm { c } } , u _ { \mathrm { e } } , R _ { \mathrm { c } } / u _ { \mathrm { e } }$ 、$\rho _ { \mathrm { l } } \mathbf { \boldsymbol { u } } _ { \mathrm { e } } ^ { 2 }$ $\rho _ { 1 } , \mu _ { 1 } , \lambda _ { 1 }$ ，其中 ${ \pmb u } _ { \mathrm { e } } = 2 \pi M D ( c _ { \mathrm { s a t } } - c _ { \infty } ) / \rho _ { 1 } R _ { \mathrm { c } } ,$ 无量纲温度定义为 $T ^ { * } = ( T - T _ { \infty } ) / ( T _ { \mathrm { w } } - T _ { \infty } )$ ，无量纲浓度定义为 $c ^ { * } = ( c - c _ { \infty } ) / ( c _ { \mathrm { s a t } } - c _ { \infty } )$ ；下标s、lg-l、lg-g、1、g、w、 $\propto$ 分别表示气液界面、界面液相侧、界面气相侧、液相、气相、基底、气相外边界；浓度 $c _ { \mathrm { s a t } }$ 、 $c _ { \infty }$ 满足理想气体状态方程 $c _ { \mathrm { s a t } } =$ $p _ { \mathrm { s a t } } / ( R T )$ 、 $c _ { \infty } = p _ { \mathrm { s a t } } { \cdot } R _ { \mathrm { H } } / ( R T )$ ；压力 $p _ { \mathrm { s a t } }$ (单位 $\mathrm { k P a }$ ）是通过安托尼方程[16] $\lg ( p _ { \mathrm { s a t } } ) = A - B / ( T + C )$ 得到；其中 $A = 7 . 0 7 4 0 6$ 银 $B = 1 6 5 7 . 4 6$ 银 $C = - 4 6 . 1 3$ 。

无量纲特征参数定义为：雷诺数 $R e \ : = \ : u _ { \mathrm { e } } R _ { \mathrm { c } } /$ $( \mu / \rho )$ ，普朗特数 $P r = \mu c _ { p } / \lambda$ ，传热佩克莱数 $P e _ { \mathrm { T } } =$ $R e P r = { \bf u } _ { \mathrm { e } } R _ { \mathrm { c } } / ( \lambda / \rho c _ { p } )$ ，表示对流传热与扩散传热之比，扩散佩克莱数 $P e _ { \mathrm { D } } = { \mathbf { u } } _ { \mathrm { e } } R _ { \mathrm { c } } / D$ ，表示对流传质与扩散传质之比，毛细数 $C a = \mu { \pmb u } _ { \mathrm { e } } / \sigma$ ，马兰戈尼数 $M a = \sigma _ { \mathrm { T } } ( T _ { \mathrm { w } } - T _ { \infty } ) R _ { \mathrm { c } } / ( \mu _ { \mathrm { l } } \lambda _ { \mathrm { l } } / \rho _ { \mathrm { l } } c _ { p , \mathrm { l } } )$ ，蒸发数$E c = H _ { \mathrm { t } } M D ( c _ { \mathrm { s a t } } - c _ { \infty } ) / ( T _ { \mathrm { w } } - T _ { \infty } ) \lambda _ { \mathrm { l } }$ ，表示蒸发散热与扩散传热之比。 $M$ 为摩尔质量， $D$ 为扩散系数， $R _ { \mathrm { H } } = c _ { \infty } / c _ { \mathrm { s a t } }$ 为气相外边界相对浓度， $R$ 为气体常数， $H _ { \mathrm { t } }$ 为气化潜热， $\sigma$ 为表面张力系数， $\sigma _ { \mathrm { T } }$ 为表面张力温度系数。

# 2网格无关性检验

为了选择合适的计算网格，选用网格尺寸为7.5$\mu \mathrm { m }$ 、 ${ \textrm { 9 } } \mu \mathrm { m }$ 、 $1 0 ~ { \mu \mathrm { m } }$ 、 $1 2 . 5 ~ { \mu \mathrm { m } }$ 四种网格进行计算。其中液相网格采用上述四种网格尺寸构成的均匀网格;气相网格尺寸由气液界面处网格尺寸向气相外边界以1.15倍的增长率逐渐增长，最大网格不超过1000$\mu \mathrm { m }$ 。计算180 s后液滴润湿半径及表面平均温度结果如表2所示，四种网格的计算结果相差很水考虑计算时间和精度影响，后续计算选取尽um的网格。

表2网格无关性验证，润湿半径 $\hbar _ { \mathrm { c } } = 2 . 5 ~ \mathbf { m m }$ Table 2 Mesh dependency for the droplet witl  
Rc =2.5mm   

<html><body><table><tr><td>液相网 格/um</td><td>润湿半 径r/um</td><td>r相对 误差%</td><td>表面平均 温度/°C</td><td>平均温度相 对误差%</td></tr><tr><td>7.5</td><td>1858.60</td><td>1</td><td>29.44</td><td>1</td></tr><tr><td>9</td><td>1864.66</td><td>0.33</td><td>29.44</td><td>0.0034</td></tr><tr><td>10</td><td>1865.05</td><td>0.02</td><td>29.44</td><td>0.0034</td></tr><tr><td>12.5</td><td>1869.18</td><td>0.22</td><td>29.44</td><td>0.014</td></tr></table></body></html>

在验证模型的准确性时，采用上述 ${ \mathfrak { g } } _ { \sharp \mathrm { m } }$ 网格模拟文献[18]中悬垂半球形 $0 . 6 5 \mathrm { c S t }$ 硅油液滴顶点温度变化。图2为本文模拟结果与文献结果比较，最大相对误差 $2 . 4 \%$ 出现在初始阶段，误差较小，说明目前采用的计算是正确的。

# 3结果与分析

# 3.1液滴蒸发过程及其影响因素

如图3所示，实线为模拟的液滴体积变化，虚线为拟合曲线。液滴体积 $V ^ { * }$ 的 $2 / 3$ 次方随时间线性减小，这与文献[11] $\sim$ [13]的理论与实验研究结果趋势一致。且接触角 $\theta$ 越小，其无量纲蒸发寿命越短(如图，当 $V ^ { * 2 / 3 } = 0$ 时， $\theta$ 从小到大对应的 $t ^ { * }$ 分别为0.50、0.66、0.82、0.97)。

![](images/daf6b38ae5d5f68a29dbab4aefac9139011cd6152a5e6c30bb1949f12d19ed9f.jpg)

![](images/0b6952d1333ef28ee42b1061a25f8e5761dc224bb7e9db0a3eec207a76937e10.jpg)  
图2模拟的液滴顶点温度与文献[18]对比结果 Fig.2 Comparison of apex temperatures of droplet between reference result[18l and present simulation result   
图不同接触角下液滴蒸发过程 $V ^ { * 2 / 3 }$ 随时间 ${ { t } ^ { * } }$ 的变化 ig.3 Time evolution of droplet volume $V ^ { * 2 / 3 }$ for different angles (rad)

通过对适用于CA、CR 模型的理论公式[11]$M _ { \theta } = 2 \pi f ( \theta ) D ( c _ { \mathrm { s a t } } ( T _ { \mathrm { l g } } ) - c _ { \infty } ) r$ 进行分析，发现液滴体积变化受三方面的影响：1)接触角 $\theta$ ， $f ( \theta )$ [13]随 $\theta$ 减小而减小；2）润湿半径 $\boldsymbol { r }$ ，润湿半径 $\boldsymbol { r }$ 随蒸发的进行逐渐减小；3）浓度 $c _ { \mathrm { s a t } } ( T _ { \mathrm { l g } } ) ( c _ { \infty }$ 不变时),安托尼方程[16]揭示浓度 $c _ { \mathrm { s a t } } ( T _ { \mathrm { l g } } )$ 与表面平均温度呈正相关关系，而表面平均温度在蒸发过程中变化相对缓慢。分析这些因素发现，相同蒸发条件（ $\mathit { \Delta } E c$ 数、 $\mathit { M a }$ 数相同）下，液滴体积变化主要受液滴几何形变 $( \theta , r )$ 的影响。

根据1.2节中无量纲特征数的定义， $\mathit { E c }$ 数随 $R _ { \mathrm { H } }$ 的增大而减小 (即：外边界浓度 $c _ { \infty }$ 增加，浓度差$c _ { \mathrm { s a t } } ( T _ { \mathrm { w } } ) - c _ { \infty }$ 减小，蒸发冷却效应减弱)， $\mathit { M a }$ 数随$T _ { \mathrm { w } }$ 增大而增大。模拟中通过改变 $R _ { \mathrm { H } } , T _ { \mathrm { w } }$ 来研究 $\mathit { E c }$ 数、 $\mathit { M a }$ 数对液滴无量纲体积变化的影响，发现两者的影响（如图4）与固定接触线模型有一定的差异。在CR 模型[9]下, $\mathit { E c }$ 数、 $\mathit { M a }$ 数对液滴无量纲体积变化无影响。而对CA模型，虽然 $\mathit { E c }$ 数对液滴无量纲体积的变化无明显的影响，但 $\mathit { M a }$ 越大，液滴无量纲体积变化越慢 (无量纲蒸发寿命越长)。这是因为随着 $\mathit { M a }$ 数增大，液滴蒸发的时间尺度越小(图4中Ma由小到大对应的时间尺度分别为：597.04s、422.09s、312.42s、238.68s)；同时液滴内部流动、温度分布也随之发生变化 (如图6所示)。

![](images/ac84717a34dfdfb8d45b36592c7c411a22497cceb38c42de2c76ccef2aeefa91.jpg)  
图4 $\theta = 0 . 5 2 4$ rad时 $\mathbf { \nabla } \_ { M a }$ 对液滴体积V\*随时间 $t ^ { * }$ 变化的影响Fig.4 The effects of $\mathit { M a }$ on the evolution of droplet volume$V ^ { * }$ with constant angle $\theta = 0 . 5 2 4$ rad

# 3.2 液滴内 Marangoni对流

如图5(a）所示，在相同的 $\mathit { M a }$ 数下，当接触角$\theta = 0 . 5 2 4 ~ \mathrm { r a d }$ 时，液滴内部存在单个热毛细涡流，表面流动沿三相接触线向顶点流动，表面温度随流动方向逐渐降低。当接触角 $\theta = 0 . 2 6 2$ rad时，液滴内部中心区域存在两个BM 涡流，如图5(b)所示，这两个BM涡流在三维空间上组成一个BM涡胞；而表面最高温度一直在三相接触线处，因此在液滴边缘始终存在由三相接触线向液滴顶点流动的热毛细涡流。热毛细涡流与BM涡流间存在局部冷点，而BM 涡流之间存在局部热点。另外，在Marangoni对流作用下，液滴内部等温线发生了弯曲；且存在BM涡流结构的液滴其等温线弯曲更加严重，说明对流更强。

在蒸发前期，液滴内部流动由热毛细对流逐渐转变为BM对流，且中心处BM 涡流强度比靠近热毛细对流的BM 涡流更强、涡胞尺寸更大，如图6所示 $\mathcal { \Leftrightarrow } \langle \overset { \mathcal { N } } { M } a = 3 4 6 1 5 . 4 6$ ，直到 $t ^ { * } = 1 . 6 7 \times 1 0 ^ { - 2 }$ 时液滴内部热毛细涡流与 BM 涡流的分布才趋于相对稳定，而 $M a = 1 3 8 4 6 1 . 5 4$ ， $t ^ { * } = 3 . 3 5 \times 1 0 ^ { - 3 }$ 时内部涡流结构已相对稳定。因此 $\mathit { M a }$ 数越大，液滴内热毛细涡流与BM涡流达到相对稳定的时间越短；且中心处的BM对流占据液滴内部的空间越大。

除了蒸发过程的影响外， $\mathit { M a }$ 数也会对液滴内部涡流结构产生影响，如图7所示。 $M a = 5 . 5 4 \times 1 0 ^ { 3 }$ 时，液滴内部形成单个逆时针流动的热毛细涡流结构； $M a = 9 . 0 0 \times \underline { { { 1 0 } } } ^ { 3 }$ 时液滴内部出现单个BM 涡流，其流动方向与热毛细涡流流动方向相反 (顺时针方向)，并与对称轴另一侧的 BM 涡流结构形成一个BM涡胞； $M a = 1 . 7 3 \times 1 0 ^ { 4 }$ 时，液滴中心区出现两个BM 涡流结构，两者形成一个BM涡胞结构，且

![](images/6b192c499b9b25730232614929c245b9037b8ff81908286f2bb64883cf92b517.jpg)  
图5 $M a = 6 9 2 3 0 . 7 7$ 时液滴内部等温线及内部流动情况 (a) $\theta = 0 . 5 2 4$ rad、(b) $\theta = 0 . 2 6 2$ rad 3.5The temperature field,streamlines and isotherm temperature lines for $M a = 6 9 2 3 0 . 7 7$ (a) $\scriptstyle \theta = 0 . 5 2 4$ rad, (b) $\scriptstyle { \theta = 0 . 2 6 2 }$

![](images/4adfc74b79b1188dbd9204836204598f5ac6019eaa67b81f763f31860dcd801e.jpg)  
图6 $\scriptstyle { \theta = 0 . 2 6 2 }$ rad 时液滴内部温度分布及内部流动 (a) $t ^ { * } = 1 . 6 8 \times 1 0 ^ { 4 } \mathrm { { \hat { s } } \mathrm { { \hat { \Omega } } \mathrm { { \hat { ( b } } } } }$ ） $t ^ { * } = 3 . 3 5 \times 1 0 ^ { - 3 }$ ，(c) $t ^ { * } = 1 . 6 7 \times 1 0 ^ { - 2 }$ (d）t\*=9.71×2Fig. 6 The evolution of temperature field and streamlines forthe contact angle $\theta = 0 . 2 6 2$ rad. (a) $t ^ { * } = 1 . 6 8 \times 1 0 ^ { - 3 }$ ，(b) $t ^ { * } = 3 . 3 5 \times 1 0 ^ { - 3 }$ ，(c) $t ^ { * } = \lesssim . 6 7 \gg 1 \sqrt { 0 } ^ { - 2 }$ ，(d) $t ^ { * } = 9 . 7 1 \times 1 0 ^ { - 2 }$ （2

![](images/a0f44282c4cf3b013a01a4bc4debad3f618e125ad0b0ea09d22f99a38fc4c1b2.jpg)  
图7接触角 $\theta = 0 . 1 5 7$ rad 时液滴内部温度分布及内部流动情况 (a) $M a = 5 . 5 4 \times 1 0 ^ { 3 }$ ，(b) $M a = 9 . 0 0 \times 1 0 ^ { 3 }$ 5(c) $M a = 1 . 7 3 \times 1 0 ^ { 4 }$ ， $( \dot { \mathrm { d } } ) \ \mathrm { M } a = 2 . 0 8 \times 1 0 ^ { 4 }$ （204Fig.7 The evolution of temperature field,streamlines with constant angel $\theta = 0 . 1 5 7$ rad. (a) $M a = 5 . 5 4 \times 1 0 ^ { 3 }$ 5(b) $M a = 9 . 0 0 \times 1 0 ^ { 3 }$ ，(c) $M _ { ☉ } ^ { \ast } \mathrm { _ { 1 . 7 3 } } \times 1 0 ^ { 4 }$ ，(d) $M a = 2 . 0 8 \times 1 0 ^ { 4 }$ （20

T

在液滴腰部形成新的小涡流。 $M a = 2 . 0 8 \times 1 0 ^ { 4 }$ 时，液滴内部出现三个BM涡流，其中靠近热毛细对流的 BM涡流的流动方向为顺时针，而BM涡流之间相互耦合流动。

由于液滴为弯曲界面，液滴内必然同时存在法向温度梯度和切向温度梯度。只要存在切向温度梯度，就会产生热毛细对流。所以，当 $\mathit { M a }$ 数较小时，液滴内以热毛细对流为主。当 $\mathit { M a }$ 数足够大，对应的法向温度梯度超过BM对流失稳的临界条件时，BM对流就会产生。相比热毛细对流，BM对流走过的路径较短，传热效率高，因此，随着 $\mathit { M a }$ 数的进一步增大，BM对流逐渐占据主导，表现为BM对流涡胞数逐渐增多，而热毛细对流所占的区域相应缩小。

为了分析接触角对液滴内Marangoni对流稳定性的影响，本文通过一系列的计算，确定了不同接触角下Marangoni对流结构之间的分界 $\mathit { M a }$ 数，如图8所示。

接触角介于 $0 . 1 0 5 { \sim } 0 . 5 2 4$ rad之间，存在三种不同的涡流结构，即：热毛细涡流结构、单个BM涡流结构及多个BM涡流结构。当接触角为 $0 . 1 0 5 { \sim } 0 . 1 7 5$ rad 时，在同一接触角下，随着 $\mathit { M a }$ 数的升高，液滴内部依次出现热毛细涡流结构、单个BM涡流结构及多个BM涡流结构三种对流结构；当接触角为$0 . 1 7 5 { \sim } 0 . 2 7 9$ rad时，液滴内部仅存在多个BM涡流结构；当接触角大于 $0 . 2 7 9 { \sim } 0 . 4 0 1$ rad 时，液滴内部依次出现多个BM涡流、热毛细涡流及多个BM涡流两种对流结构，而不会产生单个BM涡流结构；当接触角为 $0 . 4 0 1 \sim 0 . 4 7 9 ~ \mathrm { r a }$ d时，在同一接触角下，随着 $\mathit { M a }$ 数的升高，液滴内部依次出现热毛细涡流、多个BM涡流两种对流结构；当接触角大于0.479rad时，液滴内部仅存在热毛细涡流对流结构。当接触角为 $0 . 1 7 5 { \sim } 0 . 4 0 1$ rad 时，即使在很小Ma数下液滴内部也会产生多个BM涡流结构，因此蒸发冷却效应可以诱导BM涡流结构的产生。

图 8中黑色线为单个热毛细涡流结构与单个BM 涡流结构的分界线，红色线为单个BM涡流结构与多个BM涡流结构的分界线，蓝色线与绿色线为热毛细涡流对流结构与多个BM涡流结构的分界线。黑色线与红色线的分界Ma数随接触角增大逐渐减小，这是因为随着接触角的增大，液滴的厚度增加，液滴内流体受到基板的黏滞力相对减小，同时液滴内部导热减弱而液滴蒸发冷却效应增强，即使在相同的基板温度下，液滴内Marangoni对流也更强。因此，随着接触角的增大，分界 $\mathit { M a }$ 数逐渐减小，类似地，蓝色线与 $0 . 2 7 9 { \sim } 0 . 4 0 1$ rad之间的绿色线均随接触角的增大而减小。当接触角介于0.4010479rad 之间时，液滴厚度进一步增加，热毛细对流占主导作用，由于热毛细对流的流动方向与相邻的BM对流涡流的流动方向相反，它对BM流的产生具有抑制作用，因而此时产生多个BM 涡流结构的分界 $\mathit { M a }$ 数随接触角的增大而增大。

![](images/e840877d367e1e9de467e3dce64737fe3732a61375b56f7ee58215d4d5ab3262.jpg)  
图8 三种 Marangoni 涡流结构之间的分界 $\mathbf { \nabla } \_ { M a }$ 数 Fig.8 The Ma number for onset of different kinds of Marangoni convection modes versus the contact angle

# 4结论

在考虑液滴蒸发冷却效应、气相物质扩散、气液两相传热、气液界面变形情况下，数值模拟研究了固定接触角模型下液滴蒸发过程中气液两相流动，分析了接触角0、 $\mathit { E c }$ 数、 $\mathit { M a }$ 数对液滴蒸发过程的影响，重点研究了液滴内部Marangoni对流失稳现象。得到以下结论：

1）相同润湿半径下，接触角 $\theta$ 越小，液滴蒸发寿命越短；且体积的 $2 / 3$ 次方随时间线性减少。相同接触角下， $\mathit { E c }$ 数对液滴蒸发寿命 (液滴体积)无明显影响；而 $\mathit { M a }$ 数越大，液滴无量纲蒸发寿命越长。

2）当接触角为 $0 . 1 0 5 { \sim } 0 . 1 7 5 \ \$ rad，随着Ma数的升高，液滴内部依次出现热毛细涡流结构、单个BM 涡流结构及多个BM涡流结构。当接触角为$0 . 1 7 5 { \sim } 0 . 2 7 9 ~ \mathrm { r a c }$ 1，液滴内部仅存在多个BM涡流结构。当接触角介于 $0 . 2 7 9 { \sim } 0 . 4 7 9$ rad之间时，液滴内部存在热毛细涡流结构、多个BM 涡流结构。当接触角大千0.479 rad时，液滴内部仅存在热毛细涡流结构

3)当接触角为 $0 . 1 0 5 { \sim } 0 . 4 0 1$ rad时，热毛细涡流结构与单个BM涡流结构、单个BM涡流结构与多个BM涡流结构、热毛细涡流结构与多个BM涡流结构之间的分界Ma数随接触角增大而减少。当接触角大于0.401rad时，热毛细涡流结构与多个BM涡流结构之间的分界Ma数随接触角增大而增大。

# 参考文献

[1] Bar-Cohen A, Arlk M, Ohadi M, et al. Direct Liquid Cooling ofHighFlux Micro and Nano Electronic Components [J].Proceedings of the IEEE,2006,94(8):1529-1570   
[2]Karlsson S,Rasmuson A,Bjorn I N,et al.Characterizationand Mathematical Modelling of Single Fluidised Particle Coating [J]. Powder Technology， 2011,207(1): 245- 254   
[3] Sirringhaus H,Kawase T,Friend R H,et al. Highresolution Inkjet Printing of All-polymer Transistor Circuits[J].Science,2000,290(5299):2123-2126   
[4]Dugas V,Broutin J,Souteyrand E.Droplet Evaporation Study Applied to DNA Chip Manufacturing [J]. Langmuir,2005,21(20):9130-9136   
[5] Chopra M,LiL,Hu H,et al.DNA Molecular Configurationsin an EvaporatingDroplet Near a Glass Surface [J]. Journal of Rheology,2003,47(5): 1111-1132   
[6] Sefiane K.On the Formation of Regular Patterns From Drying Droplets and Their Potential Use For Bio-Medical Applications [J].Journal of Bionic Engineering,2010,7: S82-S93   
[7]David S,Sefiane K,Tadrist L,et al. Experimental Investigation of the Effect of Thermal Properties of the Substrate in the Wetting and Evaporation of Sessile Drops [J].Colloids and Surfaces A:Physicochemical and Engineering Aspects,2007,298(1):108-114   
[8]任泽霈，张能力，罗锐．平板上蒸发液滴内表面张力作用下 流动的研究[J].工程热物理学报，1987,8(4)：370-373 Ren Zepei, Zhang Nengli,Luo Rui. Flows Driven by Surface Tension in Droplet on a Plate [J]. Journal of Engineering Thermophysics,1987,8(4):370-373 [9]Hu D,Wu H.Numerical Study and Predictions of Evolution Behaviors of Evaporating Pinned Droplets Based ona Comprehensive Model [J].International Journal of Thermal Sciences,2015,96:149-159   
[10]Bourges-Monnier C,Shanahan ME R.Influence of Evaporation on Contact Angle [J].Langmuir,1995,11(7):2820- 2829   
[11]Picknett R G,Bexon R.The Evaporation of Sessile or Pendant Drops in Still Air[J].Journal of Colloid and Interface Science,1977,61(2):336-350   
[12]Cazabat AM,Guéna G.Evaporation ofMacroscopic Sessile Droplets [J].Soft Matter,2010,6(12):2591-2612   
[13]Erbil HY,Mchale G,Newton MI,et al.Drop Evaporation on Solid Surfaces:Constant Contact Angle Mode [J]. Langmuir,2002,18(7):2636-2641   
[14] Sobac B,Brutin D.Thermocapillary Instabilities in an Evaporating Drop Deposited onto a Heated Substrate [J]. Physics of Fluids,2012,24(3):032103   
[15]Karapetsas G,ValluriP,Sefiane K,et al.Convective Rolls and Hydrothermal Waves in Evaporating Sessile Drops [J]. Langmuir,2011,28(31):11433-11439   
[16] Säenz P J,Valluri P,Sefiane K，et al.On Phase Change in Marangoni-driven Flows and Its Effects on the Hydrothermal-wave Instabilities [J].Physics of Fluids,2014,26(2):024114   
[17]Yang Kai,Hong Fangjun,Cheng Ping.A Fully Coupled Numerical Simulation of Sessile Droplet Evaporation UsingArbitraryLagrangian-Eulerian Formulation[J].International Journal of Heat and Mass Transfer，2Ol4，70: 409-420   
[18] Savino R，Fico S.Transient Marangoni Convection in Hanging Evaporating Drops [J].Physics of Fluids,2004, 16(10): 3738-3752   
[19]Scardovelli R,Zaleski S.Direct Numerical Simulation of Free-Surface and Interfacial Flow [J].Annual Review of Fluid Mechanics, 2003, 31(1): 567-603

![](images/15a5dd108309e73ae8230e0944623306af292a00cfec52a9e5df1da598a7e778.jpg)