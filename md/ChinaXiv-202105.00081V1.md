# 天文镜面保护铝膜偏振特性测量方法

夏苏1,2，袁沭1(1．中国科学院云南天文台，云南昆明650011；2.中国科学院大学，北京 100049)

摘要：望远镜的仪器偏振效应主要由金属镜面的反射偏振效应引起，是当前高精度天文偏振测量主要面临的技术问题。为了能够消除仪器偏振对偏振测量精度的影响，在实验室对金属镀膜材料的偏振特性进行精确而全面测量研究就显得至关重要。本文针对保护铝膜提出一种偏振特性测量方法，该方法使用两种光电调制方式对保护铝膜的Mueller矩阵关键元素进行直接测量，并基于双层膜的结构模型，使用多入射角多波长下的测量数据在不依赖色散模型以及参数假设的情况下反演光学参数。本文方法的反演结果与传统方法得到的结果保持一致，同时本文方法能够对偏振特性进行更好的表征。

关键词：偏振测量；仪器偏振；保护铝膜偏振特性；Mueller矩阵；反演光学参数中图分类号：0436.3 文献标识码：A 文章编号：

# 引言

偏振测量是天理物理研究和太阳物理研究的强大观测工具，利用它我们可以直接获得很多天文目标的重要物理和几何信息，而这些信息是其它观测手段无法获得的。例如，太阳望远镜利用偏振光谱观测诊断太阳大气中的磁场结构[；恒星的发出的偏振辐射拥有更为丰富的物理内涵[2]。由于目标的低偏振特性，天文偏振测量始终都是一种光子饥饿的观测模式。因此，利用大口径望远镜收集更多的光子，已提高目标偏振信号的信噪比就成了天文偏振测量的重要发展方向。望远镜的仪器偏振效应，即望远镜光学系统对入射偏振信号的改变，是当前高精度天文偏振测量主要面临的技术问题。对于大口径反射望远镜，仪器偏振主要是由金属镜面的反射偏振效应引起。根据菲涅尔公式，金属镜面的损耗和延迟是入射角与镀膜材料折射率的函数。从微观上看，金属膜是由大量线尺度在几十纳米的金属晶粒随机堆叠而成的，其光学特性是镀膜材料，镀膜工艺，使用环境，以及使用时间的函数[3]。因此，为了能够准确把握金属薄膜的偏振特性，进而对望远镜进行准确的偏振光学设计或建模，并最终消除仪器偏振对偏振测量精度的影响，我们需要在实验室对金属镀膜材料的偏振特性进行精确而全面测量研究。

在大口径望远镜中常用的是铝膜反射镜，其偏振特性已被广泛研究。纯铝膜镀制完成不久之后，会在其表面生成天然的氧化铝薄膜[4.5]。氧化铝薄膜的出现使铝膜得到了保护，但也改变了铝镜的偏振特性，且在表征铝镜的偏振特性的时候，必须考虑氧化膜的存在[6]。然而氧化铝薄膜仍然阻止不了水分等的污染，因此在镀完铝膜后会继续在其表面额外镀一层氧化硅保护膜[3.7]，同样其偏振特性会有很大的变化。

传统椭偏测量方法是对固定入射角度下的椭偏光谱数据 $( \Psi , \Delta )$ 进行拟合，在拟合过程中会使用色散模型来约束各个波长下的折射率[8-10]，有时还需要使用已知的文献值去约束参数变化。因此，传统方法的反演的参数准确度很大程度上依赖于色散模型的选取，而且由于自由度的减少与参数假设等的限制，对于复杂的样品需要建立十分复杂的结构模型才能进行较好的表征。

本文提出一种保护铝膜偏振特性测量方法，该方法首先对保护铝膜的Mueller矩阵关键元素进行直接测量，然后基于双层膜的结构模型，使用测得的Mueller矩阵数据在不依赖色散模型以及参数假设的情况下反演光学参数。

# 1测量原理与方法

天文目标发出的偏振辐射的偏振状态可以用Stokes向量表示,即 $\mathbf { S } _ { \mathrm { i n } } = ( I \quad Q \quad U \quad V ) ^ { \mathrm { T } }$ ，其中 $I$ 表示入射光总强度， $Q$ 为垂直与水平偏振方向的强度参数， $U$ 表示 $\pm 4 5 ^ { \circ }$ 偏振方向的强度参数，V为圆偏振的强度参数，括号外的上角标 $\mathrm { \Delta T }$ 表示矩阵转置。经过镜面反射后的Stokes向量表示 ${ \bf S } _ { \mathrm { o u t } } = { \bf M } { \bf S } _ { \mathrm { i n } }$ ，式中 $\mathbf { M }$ 为镜面反射的缪勒矩阵，它的矩阵展开形式如下：

$$
\mathbf { M } = ( \begin{array} { l l l l } { m _ { I  I } } & { m _ { Q  I } } & { m _ { U  I } } & { m _ { V  I } } \\ { m _ { I  Q } } & { m _ { Q  Q } } & { m _ { U  Q } } & { m _ { V  Q } } \\ { m _ { I  U } } & { m _ { Q  U } } & { m _ { U  U } } & { m _ { V  U } } \\ { m _ { I  V } } & { m _ { Q  V } } & { m _ { U  V } } & { m _ { V  V } } \end{array} ) ,
$$

其中缪勒矩阵各元素可以分为三类[I]，按照下标描述如下为： $I  X , X = Q , U , V$ 表示仪器起偏； $X _ { 1 }  X _ { 2 \neq 1 } , X _ { 1 , 2 } = Q , U , V$ 表示仪器串扰； $X \to X , X = Q , U , V$ 表示仪器退偏。

当入射与出射的 Stokes 向量按如图1所示的偏振坐标系，即镜面反射变换的本征坐标系定义时，其中 $+ Q$ 对应光的s分量，金属镜面反射的缪勒矩阵可以简化为[12]:

![](images/ee5244a5188eef21cadb173a71c53dd4d96a53b222b42cb89836f94d53969e42.jpg)  
图1 入射光与出射光的偏振坐标系  
Fig.1 The polarization coordinate frames of incoming and outgoing light

$$
{ \bf M } = \left( \begin{array} { c c c c } { 1 } & { { c o s 2 \Psi } } & { 0 } & { 0 } \\ { { c o s 2 \Psi } } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { { s i n 2 \Psi c o s \Delta } } & { { s i n 2 \Psi s i n \Delta } } \\ { 0 } & { 0 } & { - { s i n 2 \Psi s i n \Delta } } & { { s i n 2 \Psi c o s \Delta } } \end{array} \right) ,
$$

其中 $\boldsymbol { \Psi }$ 与 $\Delta$ 是椭偏参数。考虑到金属反射缪勒矩阵的对称性,其偏振特性主要由$m _ { I  Q } , \ m _ { U  U } , \ m _ { V  U }$ 三项表征。因此，在随后的讨论中，Mueller矩阵仅指代以上三个非零阵元。

实验数据采集是使用商业的相位调制椭偏仪(UVISEL-Plus,Horiba),其系统结构如图2所示.从光源(氙灯)发出的光经过一个起偏器(洛匈棱镜)后斜入射到样品表面,由于样品的偏振特性,反射光的偏振会发生改变,之后经过光弹调制器(PEM)和分析器(洛匈棱镜)的调制之后被光谱仪所探测,最后得到三个测量量 $( I _ { 0 } , I _ { s } , I _ { \mathrm { c } } )$ ，取决于基于反射面的起偏器的方位角 $P$ ，调制器的方位角 $M$ 分析器的方位角 $A$ 与椭偏参数 $( \Psi , \Delta )$ ,表示为[13]：

$I _ { 0 } = 1 + c o s 2 P c o s 2 M c o s 2 ( A - M ) - \{ c o s 2 P + c o s 2 M c o s 2 ( A - M ) \} c o s 2 \Psi$ Is= sin2(A-M) sin2P sin2ψsin△ .#(3) Ic = sin 2(A-M){sin2M(cos 2ψ- cos 2P)+ sin2P cos 2M sin 2ψ cos△}

![](images/9c4920e853cf873a4c044a2af033e528f9114f3bcc89618eebcb00b12176ce8e.jpg)  
图2 相位调制椭偏仪的光学结构示意图  
Fig. 2 Optical configuration of the phase modulation ellipsometer

数据采集单元采集到的是 $I _ { s } , I _ { \mathrm { c } }$ 数据。传统方法需要通过 $I _ { s } , I _ { \mathrm { c } }$ 数据求得椭偏参数，然后把椭偏参数转化为样品的特性。而此时求解椭偏参数需要进行反余弦或反正弦函数操作，其定义域被限制在[-1,1],而由于 $I _ { s } , I _ { \mathrm { c } }$ 数据微小的误差，计算过程中会超过其定义域，导致计算错误。为了计算的准确性，我们可以直接通过对 $I _ { s } , I _ { \mathrm { c } }$ 数据的拟合来研究铝镜的偏振特性。由式(3)可以知道通过调整偏振器,调制器与分析器的方位角,我们可以得到不同的测量数据.对比式(2)可知,铝镜的Mueller矩阵的几个非实数元素可以由两种调制下的 $I _ { s } , I _ { \mathrm { c } }$ 表示，相应测得数据如下：

$$
\begin{array} { l } { { \mathrm { c o n f i g u r a t i o n ~ 1 : } P = 4 5 ^ { \circ } , M = 0 ^ { \circ } , A = 4 5 ^ { \circ } } } \\ { { I _ { s 1 } = s i n 2 \Psi s i n \Delta } } \\ { { I _ { c 1 } = s i n 2 \Psi c o s \Delta } } \\ { { \mathrm { c o n f i g u r a t i o n ~ 2 : } P = 4 5 ^ { \circ } , M = 4 5 ^ { \circ } , A = 9 0 ^ { \circ \# ( 4 ) } } } \\ { { I _ { s 2 } = s i n 2 \Psi s i n \Delta } } \\ { { I _ { c 2 } = c o s 2 \Psi } } \end{array}
$$

此时，我们就可以直接测量到Mueller矩阵的元素，相比于传统椭偏仪对椭偏参数的测量，可以得到反射镜更多的信息，则可以把测量到的铝镜测量数据表示成Mueller矩阵形式：

$$
\mathbf { M } _ { \mathrm { m e a s } } = \left( \begin{array} { c c c c } { 1 } & { I _ { \mathrm { c 2 } } } & { 0 } & { 0 } \\ { I _ { \mathrm { c 2 } } } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { I _ { \mathrm { c 1 } } } & { I _ { \mathrm { s 1 } } } \\ { 0 } & { 0 } & { - I _ { \mathrm { s 1 } } } & { I _ { \mathrm { c 1 } } } \end{array} \right) . \# ( 5 )
$$

为了研究铝镜偏振特性，我们需要获得足够多的信息，鉴于仪器测量能力，我们采集了铝反射镜样品（PF05-03-G01,THORLABS）在多入射角度(角度范围 $5 0 { - } 8 0 ^ { \circ }$ ，间隔 $2 ^ { \circ }$ ）下的光谱数据(波长范围 $4 0 0 \ \mathrm { n m - } 1 2 0 0 \ \mathrm { n m }$ ，间隔 $2 5 \mathrm { n m }$ )。图3显示的是测量得到的Mueller矩阵关键项 $( m _ { I  Q } , ~ m _ { U  U } , ~ m _ { V  U } )$ 它们的高度轴代表的是元素的大小。可以发现这三个Mueller矩阵元素的光谱随着入射角的变化也有明显变化。

![](images/a5ff043ed51b9c2786784356a6181dcdb76bd22b561f95196a7fcf83de8557e1.jpg)  
Fig. 3 The key elements of measured Mueller matrix

# 2 数据分析

与纯铝膜相比，加了氧化硅保护膜的铝镜的偏振特性变得更加复杂。图4给出了理性情况下带有保护层的铝膜分层结构,其中 $n _ { m }$ 为空气的折射率, $n _ { f }$ 为氧化硅的折射率， $n _ { b }$ 是金属铝的复折射率（定义 $n _ { b } = n _ { r } - i \kappa )$ ； $\theta _ { m }$ 为在空气中的入射角， $\theta _ { f }$ 是氧化层内的折射角,而 $\theta _ { b }$ 此时是复数,不再有简单的折射角意义,但仍然服从snell定律。

![](images/2fd9baee09eb78af01112648043f2e4354c813efe7e7ee990a4cb6798ea126e1.jpg)  
图3测量得到的Mueller矩阵关键元素  
图4 保护铝膜的理想结构模型示意图  
Fig. 4 The ideal structural model of protected aluminum coating

因此符合上图的菲涅尔反射系数为：

$$
r = \frac { \left( \boldsymbol { \eta } _ { m } - \boldsymbol { \eta } _ { b } \right) c o s \delta _ { f } + i \left( \frac { \boldsymbol { \eta } _ { b } } { \boldsymbol { \eta } _ { f } } - \boldsymbol { \eta } _ { f } \right) s i n \delta _ { f } } { \left( \boldsymbol { \eta } _ { m } + \boldsymbol { \eta } _ { b } \right) c o s \delta _ { f } + i \left( \frac { \boldsymbol { \eta } _ { b } } { \boldsymbol { \eta } _ { f } } + \boldsymbol { \eta } _ { f } \right) s i n \delta _ { f } } , \# ( 6 )
$$

其中 $\begin{array} { r } { \delta _ { f } = \frac { 2 \pi } { \lambda } n _ { f } d _ { f } c o s \theta _ { f } . } \end{array}$ 为氧化膜的相位厚度，而 $\mathsf { \Pi } _ { \mathsf { \Pi } _ { j } }$ 代表有效折射率，其下标 $j = m , f , b$ 分别对应于空气,氧化层,铝膜三种材料,而s与 $\mathfrak { p }$ 偏振分量的有效折射率分别表示为：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { { s } \mathrm { - c o m p o n e n t { : } } \ \eta _ { j } = n _ { j } c o s \theta _ { j } } \\ { \mathrm { p - c o m p o n e n t { : } } \ \eta _ { j } = n _ { j / } c o s \theta _ { j } } \end{array} \right. . \ } \end{array}
$$

根据式(2)与式(6)，并结合椭偏参数的定义 $\Psi e ^ { i \Delta } = r _ { p } / r _ { s }$ ，我们可以为图4中的结构建立偏振模型：

$$
{ \bf M } = { \bf f } { \big ( } n _ { r } ( \lambda ) , \kappa ( \lambda ) , n _ { f } ( \lambda ) , d _ { f } , n _ { m } , \lambda , \theta _ { m } { \big ) } , \ { \# } ( 8 )
$$

其中 $n _ { m }$ 、 $n _ { r }$ 、 $\kappa$ 与 $n _ { f }$ 都是 $\lambda$ 的函数。

由式(8)可以知道偏振特性与物理参数之间的关系，在本文中假设 $n _ { m } = 1$ ,对于特定入射角与特定波长下的 Mueller 矩阵关键项 $m _ { I  Q }$ ， $m _ { U  U }$ ， $m _ { V  U }$ 与光学参数的关系如下：

$$
\{ \begin{array} { l l } { m _ { I  Q } = f _ { 1 } \big ( n _ { r } , \mathbf { \boldsymbol { \kappa } } , n _ { f } , d _ { f } \big ) } \\ { m _ { U  U } = f _ { 2 } \big ( n _ { r } , \mathbf { \boldsymbol { \kappa } } , n _ { f } , d _ { f } \big ) \# ( 9 ) } \\ { m _ { V  U } = f _ { 3 } \big ( n _ { r } , \mathbf { \boldsymbol { \kappa } } , n _ { f } , d _ { f } \big ) } \end{array} 
$$

若是使用测量到的Mueller矩阵元素，并利用上述关系求解光学参数，此时只能建立三个方程。本文的方法不使用任何文献值，就需要求解四个参数，方程个数小于未知参数的个数，无法求解。多个入射角数据在单层铝膜的时候并不能得到更多的信息，而对于带氧化层的结构，光在氧化层间多次反射之后，不同入射角就可以提供额外的信息[14]。因此我们可以加入更多的入射角度下的测量数据以增加方程，每增加一个入射角度，就可以增加三个方程，理论上只需要两个角度就可以实现对光学参数的超定，一般会使用尽可能多的方程来反演光学参数。而光学参数之间是存在相关性的，例如 $d _ { f }$ 与k是正相关[15]，为了限制其相关性的影响，我们同时拟合了多个波长下的数据，每个波长下的 $\kappa$ 值不同，而 $d _ { f }$ 是统一的。此时在拟合光谱数据的时候，传统方法习惯使用色散模型来对各个波长下的折射率进行约束且只使用单个入射角的数据，拟合效果与反演参数准确度高度依赖模型的选取，而且由于自由度的减少与参数假设等的限制，复杂的样品需要建立十分复杂的结构模型才能进行较好的表征。本文基于图4所示双层膜结构模型，使用多个入射角的光谱数据，同时拟合多个波长点下的 $n _ { r }$ 、K、 $n _ { f }$ 与共同的 $d _ { f }$ ，且不使用色散模型，此反演方法自由度更高，能够对多个入射角下的光谱数据进行更好的表征。我们使用Levenberg-Marquardt 算法[16]来解决这个非线性最小二乘优化的问题：

$$
m i n \sum _ { i = 1 } ^ { n } [ ( I _ { \mathrm { c 2 } } - m _ { I  Q } ) ^ { 2 } + ( I _ { \mathrm { c 1 } } - m _ { U  U } ) ^ { 2 } + ( I _ { s 2 } - m _ { V  U } ) ^ { 2 } ] _ { i } \# ( 1 0 )
$$

其中 $n$ 为铝镜 Mueller 的个数； $m _ { I  Q } , m _ { U  U } , m _ { V  U }$ 分别为计算得到的关键项。

入射角度的数据越多能提供更多的信息,反演未知参数的精度也会越高，因此我们会用上文描述的方法同时拟合 $5 0 – 8 0 ^ { \circ }$ 入射角下的光谱数据，并使用传统方法反演结果作为对比。在传统方法中，铝膜复折射率使用Drude-Lorentz色散模型，氧化硅使用Lorentz色散模型然后分别对入射角 ${ 6 0 } ^ { \circ }$ 与 $7 0 ^ { \circ }$ （入射角选在样品的應布儒斯特角附近，测量数据灵敏度高)下的 $\boldsymbol { \Psi }$ 与 $\Delta$ 数据进行拟合。

拟合的效果由计算的值与原始数据的残差与原始数据的比值来决定，记为相对残差，单位为百分比。图5(a)所示是两种方法在 ${ { 6 0 } ^ { \circ } }$ 与 $7 0 ^ { \circ }$ 入射角下的相对残差，其中实线代表本文方法的相对残差，虚线表示传统方法的相对残差。对于 $m _ { I  Q }$ ， $m _ { U  U }$ ， $m _ { V  U }$ ，本文提出的方法都比传统方法的拟合效果好；尤其是 $m _ { I  Q }$ 元素，传统方法的相对残差到了 $50 \%$ 左右，而本文的方法的相对残差却几乎为零。本文方法是对多个入射角下的数据进行的拟合，得到的拟合结果是符合多入射角下的偏振特性，对于其他角度的相对残差也能达到相同的水平。此外，两种方法的残差曲线中同时出现相对残差突然变大的波长点，这是因为样品在这个波长点下的偏振特性特别弱，几乎为零，（例如在入射角 $7 0 ^ { \circ }$ 下，其中一个突变点 $7 2 5 \mathrm { n m }$ 处的仪器起偏特性只有7e-4)其作为分母求得的相对误差都会变得特别大。若不考虑个别突变点，两条曲线之间比较，还是可以知道本文方法的拟合效果更好。表1中显示的两种方法反演的氧化层厚度，它们之间只相差 $0 . 5 \mathrm { n m }$ 左右，两种方法测得的厚度基本一致。

表1本文方法与传统方法反演的 $\pmb { d } _ { f }$   
Table 1 The retrieval $ { \boldsymbol { d } } _ { f }$ of this work and traditional method   

<html><body><table><tr><td></td><td>This work</td><td>Traditional(60°)</td><td>Traditional(70°）</td></tr><tr><td>df/nm</td><td>190.5875</td><td>190.2589</td><td>190.0337</td></tr></table></body></html>

两种方法的拟合的光学参数与文献参考值如图 5(b)(c)(d)所示，其中实线是由多个波长点的结果平滑连接而成，虚线是铝膜复折射率（来自McPeak[9]）与氧化硅的折射率（来自$\mathrm { G a o } ^ { [ 1 7 ] }$ ）的文献参考曲线。对于 ${ \bf \ddot { n } } _ { r }$ 、 $\kappa$ 与 $n _ { f }$ 其图中三条曲线的变化趋势基本保持一致；只是本文方法与传统方法在数值上有一点差别，一是因为传统方法使用色散模型并不能完全表征反射镜的偏振特性，其中忽略了很多影响偏振特性的因素，二是因为本文方法考虑了 $m _ { I  Q }$ 的变化特性。尤其对于图5(b)，本文工作与虚线即参考曲线在大于 $1 0 0 0 \mathrm { n m }$ 波段的差异明显增大，参考曲线也是由传统方法求得，也是在 $7 0 ^ { \circ }$ 入射角下对他的铝膜样品进行的测量。因此可以发现参考曲线与传统方法在 $7 0 ^ { \circ }$ 下测量本文的样品的十分相近,但在大于 $1 0 0 0 \mathrm { n m }$ 的波段下还是有所差异。对于传统方法在入射角 ${ 6 0 } ^ { \circ }$ 下的结果，同样在大于 $1 0 0 0 \mathrm { n m }$ 的波段与参考曲线有所差异。因此本文工作与参考曲线的差异可以认为是样品的差异导致。而本文工作与传统方法曲线之间的差异可以认为是不考虑样品各向异性的前提下，均衡多个入射角下偏振特性的结果。本文方法的曲线都不够平滑，是因为本文方法没有使用色散模型等方式对光学参数随波长的变化趋势进行约束，只使用共同的氧化膜厚度去建立各个波长点之间的联系，得到的结果反而能够真实反应当前波长点下的偏振特性。

![](images/9a7791a9ad0257b9054384a97e61afaf7ac9bd397e2dda18f4b7f1a0e0ea7b83.jpg)

![](images/46091d99172dc0c2a310a6365cfc9243bb4cef4c86835499de7a0a5198b84c10.jpg)  
图5 (a)两种方法的在 ${ 6 0 } ^ { \circ }$ 与 $7 0 ^ { \circ }$ 入射角下对于测量数据的相对残差;(b)(c)(d)分别为两种方法反演的 ${ \mathrm { { \bar { n } } } _ { r } }$ 、 $\kappa$ 与 $n _ { f }$ 随波长变化的对比图  
Fig.5(a) The relative residuals for measured data by this work and traditional method at $6 0 ^ { \circ }$ and $7 0 ^ { \circ }$ ; (b)(c)(d) is the comparison of results for the dependence of wavelength of $n _ { r }$ ,K, $n _ { f }$ ,respectively

# 3结论

本文首先介绍了对保护铝膜的Mueller矩阵关键元素进行直接测量的原理与方法，然后介绍了在不依赖色散模型以及参数假设的情况下反演光学参数的方法与结果。实验结果表明，该方法反演得到的光学参数与传统方法的结果一致。相比于传统方法，该方法获取了更多的偏振特性信息，且自由度更高，能够对偏振特性（尤其是仪器起偏特性 $m _ { I  Q }$ ）进行更好的表征。本文方法的结果曲线都不够平滑，因为本文方法没有使用色散模型等方式对光学参数随波长的变化趋势进行约束，得到的结果反而能够真实反应当前波长点下的偏振特性。本文方法是对多个入射角下的数据进行的拟合，得到的反演结果是符合多入射角下的偏振特性，而且基于简单的双层膜结构，更有利于未来对未知入射角下的偏振特性进行预测与验证。

# 参考文献:

[1] 彭建国，袁沭，金振宇．弱偏振器件Mueller矩阵测量的校准及应用[J]．天文研究与技术， 2018,15(1): 95-103. Peng Jianguo, Yuan Shu, Jin Zhenyu. Calibration of Mueller Matrix Measurement of Weak Polarization Element and Its Application. Astronomical Research & Technology,2018,15(1): 95-103.   
[2] 辛玉新，屈中权，范玉峰,等．丽江2.4米望远镜检偏器控制系统设计[J]．天文研究与技术， 2012,9(1): 1-2. Xin Yuxin, Qu Zhongquan,Fan Yufeng, et al. Design of a Polarization-Analyzer Control System for the Lijiang $2 . 4 \mathrm { m }$ Telescope.Astronomical Research & Technology,2012,9(1):1-2.   
[3] FELLER A, KRISHNAPPA N,PLEIER O,et al. Reflectivity, polarization properties, and durability of metallic mirror coatings for the European Solar Telescope[J]. Modern Technologies in Space- and Ground-based Telescopes and Instrumentation II, 2012, 8450(September 2012): 84503U.   
[4] MOTTNF.A theory of the formation of protective oxide films on metals[J]. Transactions of the Faraday Society, 1939,35: 1175.   
[5] JEURGENS L PH, SLOOF W G, TICHELAAR F D, et al. Structure and morphology of aluminium-oxide films formed by thermal oxidation of aluminium[J].Thin Solid Films,2002,418(2): 89-101.   
[6] BURGE D K,BENNETTHE.Effect of a Thin Surface Film on the Ellipsometric Determination of Optical Constants[J]. Journal of the Optical Society of America,1964,54(12): 1428.   
[7] WILSON R N. Reflecting Telescope Optics I Manufacture, Testing, Alignment, Modern Techniques[M]..   
[8] RAKIC A D, DJURISIC A B, ELAZAR J M, et al. Optical properties of metallic films for vertical-cavity optoelectronic devices[J]. Applied Optics, 1998..   
[9] MCPEAK K M, JAYANTI S V., KRESS S JP, et al. Plasmonic films can easily be better: Rules and recipes[J].ACS Photonics,2015,2(3): 326-333.   
[10] CHENG F, SU P H, CHOI J, et al. Epitaxial Growth of Atomically Smooth Aluminum on Silicon and Its Intrinsic Optical Properties[J]. ACS Nano,2016,10(11): 9852-9860.   
[11] KELLER C U. Instrumentation for Astrophysical Spectropolarimetry[J]. Astrophysical Spectropolarimetry,2010(January 2002): 303-354.   
[12] AZZAM R MA, BASHARA N M. Ellpsometry and polarized light[M]. Amsterdam: North Holland, 1977.   
[13] FUJIWARA H. Spectroscopic Ellipsometry Principles and Applications[M]..   
[14] TOMPKINS H G, HILFIKER JN. Spectroscopic Ellipsometry: Practical Application to Thin Film Characterization[M].NEW YORK:MOMENTUMPRESS,2016.   
[15] DE JUAN OVELAR M, SNIK F,KELLER C U,et al. Instrumental polarisation at the Nasmyth focus of the E-ELT[J].Astronomy and Astrophysics,2014, 562:1-8.   
[16] MARQUARDT D W. An Algorithm for Least-squares Estimation of Nonliner Paramenters[J]. J. society for Ind. Appl. Math, 1963,11(431).   
[17] GAO L,LEMARCHAND R,LEQUIME M. Refractive index determination of SiO2 layer in the UV/Vis/NIR range: Spectrophotometric reverse engineering on single and bi-layer designs[J]. Journal of the European Optical Society,2013, 8: 13010.

# Measurement Method of Polarization Properties of Protected Aluminum Coating on Astronomical Mirror

Xia $\mathrm { S u } ^ { 1 , 2 }$ ，Yuan Shul

(1.Yunnan Observatories,Chinese Academy of Sciences,Kunming 650ol1,China,Email: yuanshu@ynao.ac.cn;

2.University of Chinese Academy of Sciences,Beijing 10oo49, China)

Abstract: The instrument polarization effect of the telescope, which is mainly caused by the reflection polarization effect of metal coatings on mirrors, is the principal technical problem facing the current high-precision astronomical polarimetry. It is essential to perform accurate and comprehensive measurements and research on the polarization properties of metal coating materials in the laboratory in order to eliminate the influence of instrument polarization on the accuracy of polarimetry. This paper proposes a polarization properties measurement method for the protected aluminum coating. This method can directly measure the key elements of the Mueller matrix of the protected aluminum coating by two photoelectric modulations at a multiple-angle-of-incidence spectrum. This method also retrieves the optical parameters based on the double-layer model without dispersion model and parameter assumptions.The retrieval results of the method in this paper are consistent with those obtained by traditional methods,and the method in this paper can fully characterize the polarization properties.

Key words: Polarimetry; Instrument polarization; Polarization properties of protected aluminum coating; Mueller matrix; Retrieve of optical parameters