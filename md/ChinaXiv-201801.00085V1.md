编号：163519

# 基于变物性的格子-玻尔兹曼通量求解器

曹玉会

（中国科学院大学，工程科学学院，北京，100049）Tel: 13521069415, Email: yhcao@ucas.ac.cn

摘要：本文提出一种考虑流体热物性变化的格子-玻尔兹曼通量求解器。该求解器能够捕捉流体物性参数的变化对流动和传热的影响，在保留了传统格子-玻尔兹曼方法固有优势的同时，克服了在网格划分、边界条件处理等方面的缺陷。本文采用该求解器模拟了同心环型腔内由温差驱动的自然对流，讨论了不同温差条件下的流动和传热特性，分析了物性变化的影响。结果表明：常物性解低估了换热设备的传热性能，而且 $R a$ 数越大，偏差越显著。

关键词：格子-玻尔兹曼方法（LBM)；格子-玻尔兹曼通量求解器（LBFS)；物性变化影响；自然对流

文献标识码：A

# A Variable Property-based Lattice Boltzmann Flux Solver

CAO Yu-Huil (1.College of Sciences and Engineering,University of Chinese Academy of Sciences,Beijing 100049,China)

Abstract:A variable property-based latice Boltzmann flux solver is proposed in the present paper.This solver is capable ofcapturing the efects of the variation in fluid properties on flow and heattransfer characteristics.It retains inherent advantages ofconventional latice Boltzmann method and overcomes many drawbacks such as thedificulty in using non-uniform meshes,the inconvenience of dealing with boundary conditions,etc.In the present paper, the natural convection induced by a radial temperature difference in a horizontal concentric annulus is simulated by the solver,the flow and heat transfer characteristics obtained under different temperature difference conditions are studied,and variable property effects are discussed.It is found that the commonly-concerned constant property solution(CPS) underestimates the heat transfer performance of heat exchangers,and the deviation of the CPS from the variable property solution becomes more and more notable with the increase of the Rayleigh number Ra.

Key words: lattce Boltzmann method; latice Boltzmann flux solver; variable property efects; natural convection

# 0引言

格子-玻尔兹曼方法（LBM）基于介观动理论，其中的演化过程物理图像清晰，计算简单，容易编程，计算是局部的，具有良好的并行性和可扩展性，在模拟大规模复杂非线性流动问题时具有独特优势，已被成功用于处理各类复杂流动问题[1-7]，如工程传热传质、湍流、多组分、多相流、界面动力

通讯作者：曹玉会，副教授，yhcao@ucas.ac.cn学、化学反应与燃烧等。

最近两年，Shu 等人[8-9]提出一种格子-玻尔兹曼通量求解器（LBFS），并将其推广应用于单相流体、多相流体的流动与传热的数值研究[10-12]。在LBFS中，通过对格子-玻尔兹曼方程进行C-E分析得到守恒的微分方程，然后采用有限体积方法对微分方程进行离散化处理，单元界面上的数值通量利用格子-玻尔兹曼方程的局部解进行估算。有关LBFS的详细介绍，可以参考文献[8]。

变物性的影响是过去几十年理论研究和数值研究的热点问题之一。已有研究结果表明：流体热物性随温度的变化对流动不稳定性有比较显著的影响[13-16]，同时对传热性能的影响也不容忽视[17-24]。然而，采用LBM研究这类问题的工作[25-26]比较少见，而且都只能采用均匀网格。

本文将LBFS推广用于变物性流体流动与传热过程的数值研究。关于本文中的变物性LBFS，有四点需要强调指出。第一，考虑了流体的黏性、导热系数、比热容以及体积力中流体密度随温度的变化。第二，可以很方便地采用非均匀网格。第三，存储量小，只需存储平衡分布函数。第四，普适性好，方程中的体积力以及由物性变化引入的附加项不会影响数值通量的估算过程。近期，本文作者提出一种可以同时考虑流体密度变化的算法（VPLBFS)，在文献[27]中做了详细介绍和系统检验。

# 1变物性格子-玻尔兹曼通量求解器

# 1.1宏观控制方程

对于变物性流体的流动和传热问题，在忽略黏性热耗散和压缩功的条件下，控制方程可以写成如下形式：

$$
\widehat { \cal O } _ { t } \rho + \nabla \cdot \left( \rho \mathbf { u } \right) = 0
$$

$$
\hat { \mathcal { O } } _ { t } ( \rho \mathbf { u } ) + \nabla \cdot ( \rho \mathbf { u } \mathbf { u } ) = - \nabla p + \nabla \Big [ \mu \big ( \nabla \mathbf { u } + ( \nabla \mathbf { u } ) ^ { T } \big ) \Big ] + F
$$

$$
\frac { 1 } { \rho C _ { p } } \big ( \hat { o } _ { t } T + \mathbf { u } \cdot \nabla T \big ) = \nabla \cdot ( \kappa \nabla T )
$$

在本文的研究工作中，流体的黏度 $\mu$ ，导热系数 $\kappa$ 和比热容 $C _ { p }$ 都是温度的函数， $F$ 是体积力，只有体积力中出现的流体密度是温度的函数。

# 1.2标准LBE和多尺度C-E分析

类似于常物性流体，变物性流体流动的标准LBE也可以写成方程（4）的形式：

$$
f _ { \alpha } ( r + e _ { \alpha } \delta _ { t } , t + \delta _ { t } ) = f _ { \alpha } ( r , t ) + \frac { f _ { \alpha } ^ { e q } ( r , t ) - f _ { \alpha } ( r , t ) } { \tau _ { f } } , \qquad \alpha = 0 , 1 , . . . . . , N
$$

其中， $r$ 是坐标位置， $\delta _ { t }$ 是粒子运动的时间步长，其大小等于格子的尺寸 $\delta _ { x }$ ， $e _ { \alpha }$ 是格子模型中 $\alpha$ 方向上的粒子速度， $N$ 是粒子速度的个数， $\tau _ { f }$ 是弛豫时间， $f _ { \alpha }$ 是 $\alpha$ 方向上的密度分布函数， $f _ { \alpha } ^ { e q }$ 是对应的平衡分布函数，具有方程（5）的形式：

$$
f _ { \alpha } ^ { e q } \left( \boldsymbol { r } , t \right) = \rho \omega _ { \alpha } \left[ 1 + \frac { \boldsymbol { e } _ { \alpha } \cdot \boldsymbol { u } } { c _ { s } ^ { 2 } } + \frac { \left( \boldsymbol { e } _ { \alpha } \cdot \boldsymbol { u } \right) ^ { 2 } - \left( \boldsymbol { c } _ { s } \ : \left| \boldsymbol { u } \right| \right) ^ { 2 } } { 2 c _ { s } ^ { 4 } } \right]
$$

其中， $\omega _ { \alpha }$ 是加权系数， $c _ { s }$ 是声速， $\omega _ { \alpha }$ 和 $c _ { s }$ 的数值取决于所选用的格子模型。对于二维问题，最常用的格子模型是 ${ \tt D } 2 { \tt q } 9$ 模型，图1给出了D2q9模型的示意图，各个方向上粒子的速度具有（6）的形式：

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

$$
e _ { \alpha } = \left\{ \begin{array} { l l } { 0 , } & { \ \alpha = 0 } \\ { \left( \cos [ ( \alpha - 1 ) \pi / 2 ] , \sin [ ( \alpha - 1 ) \pi / 2 ] \right) c , } & { \ \alpha = 1 , 2 , 3 , 4 } \\ { \sqrt { 2 } \left( \cos [ ( \alpha - 5 ) \pi / 2 + \pi / 4 ] , \sin [ ( \alpha - 5 ) \pi / 2 + \pi / 4 ] \right) c , } & { \ \alpha = 5 , 6 , 7 , 8 } \end{array} \right.
$$

其中， $c = \delta _ { x } / \delta _ { t }$ 。对于 ${ \tt D } 2 { \tt q } 9$ 模型，声速（204号 $c _ { s } = c / \sqrt { 3 }$ ，加权系数 $\omega _ { \alpha }$ 为 $\omega _ { \scriptscriptstyle 0 } = 4 / 9$ ，$\omega _ { 1 } = \omega _ { 2 } = \omega _ { 3 } = \omega _ { 4 } = 1 / 9$

$f _ { \alpha }$ 和 $f _ { \alpha } ^ { e q }$ 满足守恒律（7）和（8）：

对方程(4）做 Taylor 展开，得到下面的方程（9)

$$
\begin{array} { l } { { \displaystyle { \omega _ { 5 } = \omega _ { 6 } = \omega _ { 7 } = \omega _ { 8 } = 1 / 3 6 } \mathrm { ~ } _ { \mathrm { c } } } } \\ { { \displaystyle { \rho = \sum _ { \alpha = 0 } ^ { 8 } f _ { \alpha } = \sum _ { \alpha = 0 } ^ { 8 } f _ { \alpha } ^ { e q } } } } \end{array}
$$

$$
\rho \mathbf { u } = \sum _ { \alpha = 0 } ^ { 8 } { e _ { \alpha } f _ { \alpha } } = \sum _ { \alpha = 0 } ^ { 8 } { e _ { \alpha } f _ { \alpha } ^ { e q } }
$$

$$
\left( { \frac { \hat { \sigma } } { \hat { \sigma } t } } + \boldsymbol { e } _ { \alpha } \cdot \nabla \right) f _ { \alpha } + { \frac { \delta t } { 2 } } { \left( { \frac { \hat { \sigma } } { \hat { \sigma } t } } + \boldsymbol { e } _ { \alpha } \cdot \nabla \right) } ^ { 2 } f _ { \alpha } + { \frac { 1 } { \tau _ { f } \delta t } } { \left( f _ { \alpha } - f _ { \alpha } ^ { e q } \right) } + O \left( \delta t ^ { 2 } \right) = 0
$$

![](images/82185926f4e83882b8adccb19b86297ce6b3de445e5763096cac04cdc326f0e7.jpg)  
图 $1 \ \mathrm { D 2 q 9 }$ 格子模型示意图  
Fig.1 Schematic of the D2Q9 lattice model

在多尺度C-E 分析中，分布函数 $f _ { \alpha }$ 以及 $f _ { \alpha }$ 对时间和空间的偏导数按照以下形式进行多尺度展开，

$$
\begin{array} { l } { { f _ { \alpha } = f _ { \alpha } ^ { ( 0 ) } + \varepsilon f _ { \alpha } ^ { ( 1 ) } + \varepsilon ^ { 2 } f _ { \alpha } ^ { ( 2 ) } } } \\ { { \displaystyle { \frac { \hat { \sigma } } { \partial t } } = \varepsilon \frac { \hat { \sigma } } { \hat { \sigma } t _ { 0 } } + \varepsilon ^ { 2 } \frac { \hat { \sigma } } { \hat { \sigma } t _ { 1 } } } } \end{array}
$$

$$
\nabla _ { { r } } = \varepsilon \nabla _ { { r } 1 }
$$

其中， $\varepsilon$ 是一个小量，其大小正比于努森数。将方程 （10）代入方程（9)，经过整理得到下面的方程：

$$
\begin{array} { r l } & { \displaystyle \frac { \partial \rho } { \partial t } + \nabla \cdot \big ( \rho \mathbf { u } \big ) = 0 } \\ & { \displaystyle \frac { \partial \rho \mathbf { u } } { \partial t } + \nabla \cdot \big ( \rho \mathbf { u } \mathbf { u } \big ) = - \nabla \rho + \nabla \Big [ \mu \nabla \mathbf { u } + \big ( \nabla \mathbf { u } \big ) ^ { T } \Big ] } \end{array}
$$

其中,

$$
\mu = \rho c _ { s } ^ { 2 } \left( \tau _ { f } - 0 . 5 \right) \delta _ { t }
$$

对于温度场，引入分布函数 $g _ { \alpha }$ ，它的平衡分布函数记作 $g _ { \alpha } ^ { e q }$ 。在本文中，对温度分布函数 $g _ { \alpha }$ 采用了D2q4 模型，对 $g _ { \alpha }$ 满足的LBE 进行 Taylor展开和C-E分析之后，可以得到守恒律 (14)，宏观控制方程 （15)，热物性和弛豫时间 $\tau _ { g }$ 之间的关系式(16)。

$$
T = \sum _ { \alpha = 1 } ^ { M } g _ { \alpha } ^ { e q } = \sum _ { \alpha = 1 } ^ { M } g _ { \alpha }
$$

$$
\frac { { \partial { T } } } { { \partial t } } + \nabla \cdot ( { \bf { u } } T ) = \nabla \cdot ( D \nabla { T } )
$$

$$
D = \frac { 1 } { 2 } ( \tau _ { g } - 0 . 5 ) \delta _ { t } .
$$

# 1.3变物性LBFS的控制方程

从标准LBE出发得到的宏观控制方程（11）、（12）和（15）跟变物性流体自然对流的控制方程（1）、

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

（2）和（3）是有差别的。为了恢复方程（1）-(3)，同时又能保留格子-玻尔兹曼模型和守恒律的简洁形式，本文将由标准LBE得到的守恒律和关系式直接代入宏观控制方程（1）－（3），从而得到下面的方程：

$$
\frac { \partial \rho } { \partial t } + \nabla \cdot \left( \sum _ { \alpha = 0 } ^ { 8 } e _ { \alpha } f _ { \alpha } ^ { e q } \right) = 0
$$

$$
{ \frac { \partial \rho \mathbf { u } } { \partial t } } + \nabla \cdot \Pi = F 
$$

$$
\frac { \partial T } { \partial t } + \nabla \cdot \left[ \sum _ { \alpha = 1 } ^ { 4 } \left( e _ { \alpha } g _ { \alpha } ^ { e q } + \left( 1 - \frac { 1 } { 2 \tau _ { g } } \right) e _ { \alpha } g _ { \alpha } ^ { n e q } \right) \right] = - \kappa \nabla T \nabla \frac { D } { \kappa }
$$

对于二维问题，在变物性LBFS 中，方程（17）可以改写成以下形式：

$$
\frac { \partial W } { \partial t } { + } \frac { \partial E } { \partial x } { + } \frac { \partial F } { \partial y } { = F ^ { E } }
$$

其中,

$$
\boldsymbol { W } = \{ \rho , \rho u , \rho \nu , T \} ^ { T } ;
$$

$$
E = \left\{ P _ { _ x } , \Pi _ { _ { x x } } , \Pi _ { _ { y x } } , \mathcal { Q } _ { x } \right\} ^ { T }
$$

$$
F = \left\{ P _ { _ y } , \Pi _ { x y } , \Pi _ { y y } , Q _ { y } \right\} ^ { T } ;
$$

$$
\boldsymbol { F } ^ { E } = \left\{ 0 , 0 , F , - \kappa \nabla T \nabla \frac { D } { \kappa } \right\} ^ { T }
$$

$$
P _ { x } = \sum _ { \alpha = 0 } ^ { N } e _ { \alpha x } f _ { \alpha } ^ { e q }
$$

$$
P _ { y } = \sum _ { \alpha = 0 } ^ { N } e _ { \alpha y } f _ { \alpha } ^ { e q }
$$

$$
\begin{array} { r } { \Pi _ { x x } = \displaystyle \sum _ { \alpha = 0 } ^ { N } e _ { \alpha x } e _ { \alpha x } \Bigg [ f _ { \alpha } ^ { e q } + \left( 1 { - \frac { 1 } { 2 \tau _ { f } } } \right) f _ { \alpha } ^ { n e q } \Bigg ] } \\ { \Pi _ { x y } = \displaystyle \sum _ { \alpha = 0 } ^ { N } e _ { \alpha x } e _ { \alpha y } \Bigg [ f _ { \alpha } ^ { e q } + \left( 1 { - \frac { 1 } { 2 \tau _ { f } } } \right) f _ { \alpha } ^ { n e q } \Bigg ] } \end{array}
$$

$$
\begin{array} { r l } & { \Pi _ { y x } = \displaystyle \sum _ { \alpha = 0 } ^ { N } e _ { \alpha y } e _ { \alpha x } \Bigg [ f _ { \alpha } ^ { e q } + \left( 1 { - \frac { 1 } { 2 \tau _ { f } } } \right) f _ { \alpha } ^ { n e q } \Bigg ] } \\ & { \Pi _ { y y } = \displaystyle \sum _ { \alpha = 0 } ^ { N } e _ { \alpha y } e _ { \alpha y } \Bigg [ f _ { \alpha } ^ { e q } + \left( 1 { - \frac { 1 } { 2 \tau _ { f } } } \right) f _ { \alpha } ^ { n e q } \Bigg ] } \end{array}
$$

在变物性LBFS中，采用有限体积方法求解方程（18)，其中，每个单元中心的宏观物理量通过直接求解离散化方程得到，相邻单元界面上的数值通量利用LBM的解通过局部重构进行估算。按照有限体积方法，对方程（18）在控制体 $\Omega _ { i }$ 上进行积分,得到变物性LBFS 需要求解的控制方程（21)。

$$
\frac { d W _ { i } } { d t } = - \frac { 1 } { \Delta V _ { i } } \sum _ { k } R _ { k } \Delta S _ { k } + { F ^ { E } } _ { i } , R _ { k } = ( n _ { x } E + n _ { y } F ) _ { k }
$$

其中， $\Delta V _ { i }$ 是控制体 $\Omega _ { i }$ 的体积， $\Delta S _ { k }$ 是第 $k$ 个交界面（线）的面积（长度）。 $R _ { k }$ 是第 $k$ 个交界面（线）上的数值通量。估算 $R _ { k }$ 的具体做法，请参考文献8]。得到 $R _ { k }$ 之后，采用4阶龙格-库塔方法得到方程（21）的数值解。

# 2变物性LBFS算法检验

为了检验变物性LBFS的可靠性，在模拟同心环型腔内的自然对流之前，首先重复了文献[21]中的工作，模拟了方腔内的自然对流。空腔的上、下壁面是绝热条件，左、右两侧分别是温度恒定的高温壁面和低温壁面，温度分别记作 $T _ { h }$ 和 $T _ { c }$ 。方程（22）定义了一个无量纲温差比 $\theta$ ，用于衡量温差的大小。

$$
\theta = \left( T _ { h } - T _ { c } \right) / T _ { c }
$$

在本文的三个算例中，瑞利数 $R a$ 恒为 $1 0 ^ { 5 }$ ，普朗特数 $P r$ 恒为0.71， $T _ { c }$ 恒为 $3 0 0 \mathrm { K }$ ， $\theta$ 的取值分别为0.0101，0.403和0.8，所以， $T _ { h }$ 分别为

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

303.03K，420.9K和540K。流体的热物性参数，黏度 $\mu$ ，比热容 $C _ { p }$ 和导热系数 $\kappa$ ，都是温度的函数，函数表达式采用文献[18]中的形式，体积力中流体的密度仍采用Boussinesq 假设。

![](images/cd2c727a928ab8f639a1e32711a8e82db21910258dbb743be431be4c64f4e80e.jpg)  
图2．不同温差条件下稳态解的比较。瑞利数 $R a = 1 0 ^ { 5 }$ 。速度无滑移条件，左、右侧的恒温条件和上、下壁面的绝热条件。初始时刻，流体处于静止状态，流体的温度等于低温壁面温度。

图2展示了不同温差条件下稳态解之间的比较，包括流线和等温线。如图2所示，流体热物性的变化对流场和温度场都有比较明显的影响，随着温差的增大，变物性的影响逐渐增强。为了定量地分析流体热物性的变化对传热的影响，计算了左侧高温壁面上的平均努塞尔数Nu。图3给出了不同温差条件下得到的Nu随时间的变化。如图3所示，温差为0.0101时的Nu非常接近常物性解中的数值，随着温差的增大，传热速率逐渐增大。图2和图3中展示的结果与文献[21]中的结果吻合，表明变物性LBFS能有效捕捉到流体热物性随温度的变化对流场和温度场造成的影响。

# 3同心环型腔内的自然对流

本文采用变物性LBFS模拟了同心环型腔内由径向温差驱动的流动和传热过程。同心环的内环半径和外环半径分别记作 $R _ { i }$ 和 $R _ { o }$ ，纵横比  
$r r = R _ { o } / R _ { i } = 2 . 6$ 。内、外壁面温度记作 $T _ { c }$ 和 $T _ { h }$ 。跟第2部分相同，通过不同温差条件下数值结果之间的比较讨论流体热物性变化的影响。 $T _ { c }$ 恒为300K，无量纲温差比 $\theta$ 分别为0.0101，0.403和0.8。普朗特数 $P r$ 恒为0.71。初始时刻流体处于静止状态，流体温度为 $T _ { c }$ 。速度边界采用无滑移条件。沿  
径向采用非均匀网格，沿周向采用了均匀网格。

$$
\begin{array} { r l r } { - - } & { { } \theta _ { \scriptscriptstyle 0 } = 0 . 4 0 3 , } & { - \cdot - \quad \theta _ { \scriptscriptstyle 0 } = 0 . 8 \circ } \end{array}
$$

Fig.2 Comparison of steady-state solutions obtained under different temperature difference conditions. $R a = 1 0 ^ { 5 }$ ： Left: streamline, Right: isotherm．- $\theta _ { 0 } = 0 . 0 1 0 1$ ， $\cdot \quad \theta _ { 0 } = 0 . 4 0 3 , \quad - \cdot - \quad \theta _ { 0 } = 0 . 8 .$ （20

跟传统的LBM不同，变物性LBFS可以很方便地采用非均匀网格进行数值求解，而且不必通过分布函数给定边界条件，可以直接利用宏观物理量给出。对于上述条件下空腔内的自然对流，采用变物性LBFS进行求解，经网格独立性检验，发现使用$5 0 \times 5 0$ 的非均匀网格足以得出准确的稳态解。另外，对于边界条件的处理，直接给定四个壁面上的

# 3.1常物性解

首先，采用变物性LBFS的简化形式，忽略流体黏度、导热系数、比热容随温度的变化，得到了同心环型腔内自然对流的常物性解。网格数为 $1 8 0 \times 4 0$ 。图4给出了常物性解中速度分量和等温线的分布。瑞利数 $R a = 5 0 0 0 0$ ，流体的物性参数，如：黏度 $\mu$ ，比热容 $C _ { p }$ 和导热系数 $\kappa$ ，取温度为 $T _ { c }$ 时的值。这些定性的结果跟文献[28]中一致。在本文中，把常物性解作为参考，在下文中将通过定量的比较，分析变物性的影响。

![](images/be0b2a6ff24239d17e78c57ca30d5c191828efa07a30b207684441f900c05d6c.jpg)  
图3 左侧高温壁面上平均努塞尔数的时间演化。 Fig.3 The temporal evolution of the average Nusselt number Nu calculated on the left hot wall.

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/ab0ad28e08c934d540a115df4f1a08430a3417061bfedca2f00a809899d88fee.jpg)  
图4 常物性解中的速度分量和等温线。 $R a = 5 0 0 0 0$

Fig. 4 Distributions of velocity components and isotherms in constant property solution. $R a = 5 0 0 0 0$

# 3.2变物性的影响

在这部分，采用变物性LBFS模拟了三个不同 $\theta$ 条件下同心环型腔内的自然对流。流体的黏度，导热系数和比热容都是温度的函数，函数关系仍采用文献[18] 中的形式。 $R a$ 和 $P r$ 分别为 50000 和0.71。

图5展示了不同 $\theta$ 条件下数值解之间的比较，包括速度分量和等温线的分布。跟方腔中的情况类似，热物性的变化对速度场和温度场都有比较明显的影响。而且，随着温差比的增大，物性变化的影

响逐渐增强。

为了定量地分析物性变化对传热速率的影响，我们计算了外圆环上的传热系数 $\kappa _ { e q o }$ ，按照文献[28]， $\kappa _ { e q o }$ 可以被定义为（23）的形式$\boldsymbol { \kappa _ { e q o } } = \frac { r r \cdot \ln ( r r ) } { 2 \pi ( r r - 1 ) } \int _ { 0 } ^ { 2 \pi } \frac { \partial T } { \partial r } d \theta$ (23)

![](images/ef68e213ee00b15e2a70d5f4ac05f4061c180210e9d583a9785df2466524be76.jpg)  
图5 变物性解中速度分量、等温线之间的比较。 $\theta _ { _ { 0 } } = 0 . 0 1 0 1$ ， $\dots \ \theta _ { \scriptscriptstyle 0 } = 0 . 4 0 3 \ , \ \quad - \dots \ \theta _ { \scriptscriptstyle 0 } = 0 . 8$ 。Fig. 5 Comparison of velocity components and isotherms in variable property solutions.— $\theta _ { _ { 0 } } = 0 . 0 1 0 1$ ，… $\theta _ { _ 0 } = 0 . 4 0 3$ ，（204号

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

![](images/c733e4d0c5361a5dc966530e56aa92fff7448e823fe89ec1ba53a645cd75e821.jpg)  
图6外圆环上传热系数随时间的变化。 Fig.6 The temporal evolution of heat transfer coefficient calculated on the outer wall.

图6给出了不同温差条件下 $\kappa _ { e q o }$ 随时间的变化。当 $\theta _ { \scriptscriptstyle 0 } = 0 . 0 1 0 1$ 时，物性变化相对比较小，此时的变物性解与常物性解之间的相对误差很小， $\kappa _ { e q o }$ 略大于常物性解中 $\kappa _ { e q o }$ 的值。随着温差比的增大，物性变化的影响逐渐增强，当 $\theta _ { _ { 0 } } = 0 . 8$ 时，变物性解中$\kappa _ { e q o }$ 比相同 $R a$ 和 $P r$ 条件下常物性解中的 $\kappa _ { e q o }$ 大$1 5 \%$ 。这个定量的结果与空腔内的结果比较接近。这表明：一方面，变物性的影响对设备几何结构的变化并不敏感；另一方面，在数值计算中，通过忽略流体热物性的变化而得到的常物性解低估了对流换热系统的传热性能，而且温差越大，由热物性变化引起的偏差也越大。

![](images/2b77fa5c81a3348c38e57fbdc6c0bd81266bb0ad1022c131cf622cf0c53667de.jpg)  
3.3不同 $R a$ 条件下变物性的影响  
图7不同瑞利数条件下外圆环上传热系数的比较。 Fig.7The heat transfer coefficient obtained under different Rayleigh number conditions.

为了进一步分析变物性的影响，本文采用变物性LBFS模拟了不同 $R a$ 条件下同心环型腔内由温差驱动的自然对流，计算了稳态阶段外圆环上的传热系数 $\kappa _ { e q o }$ 。图7给出了不同 $R a$ 下变物性解中的 $\kappa _ { e q o }$ 。由图可见，随着 $R a$ 的增大， $\kappa _ { e q o }$ 逐渐增大，流体热物性的变化对 $\kappa _ { e q o }$ 的影响逐渐增强。换言之，在相同温差条件下， $R a$ 越大，变物性对传热的影响也越大。

# 4结论

本文提出一种基于流体物性变化的格子-玻尔兹曼通量求解器（变物性LBFS)，该求解器保留了传统LBM的优势，同时克服了传统LBM在网格划分，边界条件的处理等方面的缺陷。有关同心环型腔内由温差驱动的自然对流的数值研究结果表明：通常关注的常物性解低估了换热设备的传热速率，尤其是在温差较大，瑞利数也比较大的情况下。

# 参考文献

[1] Benzi R, Succi S, Vergassola M. The Lattice Boltzmann Equation: Theory and Applications[J]. Physics Reports，1992，222:145-197   
[2] Qian YH, Succi S,Orszag SA. Recent Advances in Lattice Boltzmann Computing [J]. Annual Review of Computational Physics，1995，3:195-242   
[3] Nourgaliev RR,Dinh TN,Theofanous TG. The Lattice Boltzmann Equation Method: Theoretical Interpretation, Numerics and Implications [J].International Journal of Multiphase Flow，2003，29:117-169   
[4] Chen S,Doolen GD. Lattice Boltzmann Method for Fluid Flows [J].Annual Review of Fluid Mechanics,1998, 30:329-364   
[5]何雅玲，王勇，李庆，格子Boltzmann 方法的理论及应 用[M]。科学出版社，2008

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

U11t IUI of Lattice Boltzmann Method [M]. The Science Publishing Company，2008 [6］郭照立，郑楚光，格子 Boltzmann 方法的原理及应用 [M]。科学出版社，2009 [6]Guo Zhaoli， Zheng Chuguang. The Principle and Application of Lattice Boltzmann Method [M].The Science Publishing Company， 2009 [7] Zhang XR, Cao Y. A Lattice Boltzmann Model for the Natural Convection with a Large Temperature Difference [J]. Progress in Computational Fluid Dynamics, 2011, 11: 269-278 [8] Shu C，Wang Y，Teo CJ，Wu J.Development of Lattice Boltzmann Flux Solver for Simulation of Incompressible Flows[J]. Advances in Applied Mathematicsand Mechanics，2014，6:436-460. [9] Shu C, Wang Y, Yang LM, Wu J. Lattice Boltzmann Flux Solver: an Efficient Approach for Numerical Simulation of Fluid Flows ［J]. Transactions of Nanjing University of Aeronautics and Astronautics， 2014，31: 1-15 [10] Wang Y，Shu C， Teo CJ. Thermal Lattice Boltzmann Flux Solver and its Application for Simulation of Incompressible Thermal Flows [J]. Computers & Fluids, 2014，94:98-111 [11] Wang Y， Shu C， Teo CJ. A Fractional Step Axisymmetric Lattice Boltzmann Flux Solverfor Incompressible Swirlingand Rotating Flows[J]. Computers & Fluids，2014，96:204-214 [12] Wang Y,Shu C, Huang HB,Teo CJ. Multiphase Lattice Boltzmann Flux Solver for Incompressible Multiphase Flows with Large Density Ratio ［J]. Journal of Computational Physics，2015，280:404-423 [13] Chen YM, Pearlstein AJ. Stability of FreeConvection Flowsof Variable-Viscosity Fluidsin Vertical and Inclined Slots [J]. Journal of Fluid Mechanics，1989，198:513-541 [14] Sabhapathy P, Cheng KC. The Effects of TemperatureDependent-Viscosityand CoefficientofThermal Expansion on the Stabilityof Laminar， Natural Convective Flow along an Isothermal， Vertical Surface [J]．International Journal of Heat and Mass Transfer, 1986，29:1521-1529

[15] Suslov SA， Paolucci S. Stability of Natural Convection Flow in a Tall Vertical Enclosure under NonBoussinesq Conditions ［J]. International Journal of Heat and Mass Transfer，1995，38: 2143-2157   
[16] Mlaouah H, Tsuji T， Nagano Y. A Study of NonBoussinesq Effect on Transition of Thermally Induced Flow in a Square Cavity ［J]. International Journal of Heat and Fluid Flow，1997，18:100-106   
[17] Gray DD,Giorgini A. The Validity of the Boussinesq Approximation for Liquids and Gases ［J]. International Journal of Heat and Mass Transfer，1976，19:545-551 [18] Zhong ZY，Yang KT，Lloyd JR. Variable Property Effects in Laminar Natural Convection in a Square Enclosure ［J]. Journal of Heat Transfer，1985,107:101- 138   
[19] Chenoweth DR,Paolucci S. Natural Convection in an Enclosed Vertical Air Layer with Large Horizontal TemperatureDifferences[J].JournalofFluid Mechanics，1986，169:173-210   
[20] Emery AF， Lee JW. The Effects of Property Variations on Natural Convection in a Square Enclosure [J]．Journal of Heat Transfer，1999，121: 57-62 [21] Leal MA, Machado HA, Cotta RM. Integral Transform Solutions of Transient Natural Convection in Enclosures with Variable Fluid Properties ［J]. International Journal of Heat and Mass Transfer，2000，43:3977-3990 [22] Hernandez J， Zamora B. Effects of Variable Propertiesand Non-uniform Heating on Natural ConvectionFlowsinVerticalChannels[J]. International Journal of Heat and Mass Transfer, 2005, 48:793-807   
[23] Sen S, Sarkar A. Effect of Variable Property and Surface Radiation on Laminar Natural Convection in a Square Cavity [J]. International Journal of Numerical Methods for Heat & Fluid Flow，1991，5(7):615-627 [24] Zamora B, Kaiser AS. Influence of the Variable Thermophysical Properties on the Turbulent Buoyancydriven Airflow Inside Open Square Cavities [J]. Heat & Mass Transfer，2012，48:35-53   
[25] Guo Z, Zhao TS. Lattice Boltzmann Simulation of Natural Convection with Temperature-dependent Viscosity in a Porous Cavity [J]. Progress in

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

Computational Fluid Dynamics，2004，5(1/2):110-117 [26] Zhang XR,Cao Y. A Lattice Boltzmann Model for Natural Convection with a Large Temperature Difference [J]．Progress in Computational Fluid Dynamics，2011, 11(5): 269-278   
[27] Cao Y. Variable Property-based Lattice Boltzmann Flux Solver for Thermal Flows in the Low Mach Number Limit [J]. International Journal of Heat and Mass Transfer，2016，103:254-264   
[28] Shu C. Application of Differential Quadrature Method to Simulate Natural Convection in a Concentric Annulus [J]. International Journal for Numerical Methods in Fluids，1999，30:977-993

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538