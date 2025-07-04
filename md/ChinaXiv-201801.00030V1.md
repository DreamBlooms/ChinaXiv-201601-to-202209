编号：162130

# 基于离散型伴随方法的单边膨胀喷管优化设计研究

宋红超 李鑫 季路成(北京理工大学，北京，100081)

摘要：目前高超声速喷管的设计方法主要有特征线方法与基于CFD分析的优化设计方法。采用特征线法设计喷管时流动需基于无粘、无旋假设进行简化，无法确保设计结果在真实流动情况下达到最优；采用遗传算法或常规梯度类方法等优化算法进行优化设计时，设计变量数目的增多为设计带来计算量方面极大的挑战。为克服上述方法在设计过程中的不足，依托伴随方法具有计算量与设计变量数目几乎无关的特点，本文发展了基于离散型伴随方法的单边膨胀喷管的设计方法，以控制喷管沿流程的面积分布作为参数化方法，在初步设计的性能优良的原型喷管基础上实现了精细化伴随优化设计，优化后推力系数比原型喷管提升0.8个百分点。

关键词：离散型伴随方法；单边膨胀喷管；参数化方法

# Research on the Optimization of Unilateral Expansion Nozzle Based on the

# Discrete Adjoint Method

HongChao Song' Li Xin² Ji Lucheng (Beijing Institute of Technology，Beijing，10o81，China)

Abstract: At present, the characteristic line method and the optimization method based on the CFD analysis are the mainly methods for hypersonic nozzles designing.However,the characteristic line method can't come over the shortcoming of the assumptions that the flow is no-viscosity and no-rotation. Besides,the genetic algorithm and general gradient-based algorithms used for hypersonic nozzles designing can’t handle the challenges of increasing number of design variables. Considering the calculation cost of the adjoint method isn't sensitive with the number of design variables,this paper uses the discrete adjoint method to design the unilateral expansion nozzle,accomplishing the parametric model of controlling the area distribution of the nozzle along the streamline. On the base of the initial nozzle designed by the genetic algorithm,which already has the great performance, the optimization can improve the thrust coeficient with O.8 percentage points.

Key Words: Discrete Adjoint Method; Unilateral Expansion Nozzle； Parametric Model

# 0引言

单边膨胀喷管广泛应用于高超声速飞行器冲压发动机的喷管中。目前，针对此类高超声速喷管的设计方法主要包括特征线法以及优化设计方法。

设计方法，该方法在给定喷管长度和质量流量的约束条件下，采用特征线法计算流场，并据此获得最大推力型面。Zudov 等2构造并求解了以超声速二维非对称喷管最大推力为目标函数的变分问题，其求解过程使用了特征线方法。国内，曹德一等[3]也采用特征线方法直接对后体单边膨胀喷管进行了设计。

特征线法被广泛用于超声速流动型面设计中，可设计出内部流场光滑且不存在激波的喷管。特征线法的一种典型方法是Rao提出的最大推力喷管早期特征线法在高超声速内流部件型面设计中取得一定效果。然而，特征线法需要基于流动无粘、无旋的假设，与真实流动具有较大的偏差，同时利用特征线法设计出的喷管通常情况下管道较长，需要对设计结果进行截短，导致设计喷管具有较大的性能损失。

随着计算流体力学和计算机技术的迅猛发展，近几十年出现的基于CFD分析的优化设计方法取得了重大进步。陈兵4基于NS方程的优化设计建立了二维尾喷管模型，应用复合形法对该模型进行了求解，随后又结合遗传算法与高效、高精度的空间推进算法[5]，对二维超声速超燃冲压发动机尾喷管进行了气动优化设计研究。甘文彪等则结合试验设计方法、替代模型技术以及遗传算法构建了一套优化方法，并将其应用于高超声速飞行器后体/尾喷管的一体化设计中。

上述高超声速喷管设计中所采用的遗传算法以及常规梯度类方法等，尽管有效，但计算量均会随设计变量数量的增加而成几何或指数规律增长，难以满足全三维工程设计中缩短设计周期、提高设计自动化以及精细化的需求。

相比常规优化方法，伴随方法具有计算量与设计变量数目几乎无关的明显优势，能够克服常规优化方法在计算量方面的不足。在Jameson和Giles等人[7-11]的努力下，经过二十多年的发展，翼型、机翼、翼身组合体乃至全机的气动伴随优化设计已得到较为成熟的应用。本文采用离散型伴随优化方法设计高超声速单边膨胀喷管，真正以精细化设计模式全面解决高超声速单边膨胀喷管设计问题，并为后续的进气道和推进系统一体化设计过程提供了技术参考。

# 1离散型伴随优化方法

# 1.1离散型伴随优化理论

对于定常流动优化问题，流动方程的残差 $R$ 可视为优化设计变量 $\mathbf { D }$ 、网格 $\mathbf { X }$ 和流动变量Q的函数，即： $\mathbf { R } = \mathbf { R } ( \mathbf { D } , \mathbf { Q } , \mathbf { X } ) = \mathbf { 0 }$ 。上述的残差方程本质上属于定常流动优化问题的限制条件。在初始目标函数 $f ( { \bf D } , { \bf Q } , { \bf X } )$ 中引入拉格朗日乘子，新目标函数 $L$ 为：

$$
L ( \mathbf { D } , \mathbf { Q } , \mathbf { X } , \lambda ) = f ( \mathbf { D } , \mathbf { Q } , \mathbf { X } ) + \lambda ^ { T } \mathbf { R } ( \mathbf { D } , \mathbf { Q } , \mathbf { X } )
$$

式(1)将约束优化问题转化为无约束优化问题，其中 $f ( D , Q , X )$ 为气动目标函数（一般求最小值)， $l$ 是拉格朗日乘子矢量(伴随变量)。式(1)对 $\mathbf { D }$ 求导：

$$
\begin{array} { l }  { \displaystyle { \frac { \mathrm { d } L } { \mathrm { d } { \bf D } } = { \frac { \hbar \omega } { \hbar { \frac { L + \hbar } { 2 } } } } + { \frac { \hbar \omega } { \hbar { \bf D } } } \mathrm { ~ { \bf A } ~ } _ { \pm } ^ { T } } \ { \displaystyle { \frac { \mathrm { d } f } { \mathrm { d } { \bf D } } } } } \\  { \displaystyle { \frac { \mathrm { d } L } { \mathrm { d } { \bf D } } } = { \frac { \hbar \omega } { \hbar { \bf D } } } + { \frac { \hbar \omega } { \hbar { \bf D } } } { \displaystyle { \frac { \mathrm { d } f } { \mathrm { d } { \bf D } } } } { \displaystyle { \frac { \mathrm { d } f } { \mathrm { d } { \bf D } } } } } \\   \displaystyle ~ + { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf D } + \hbar { \bf \Omega } } } { \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } + { \frac { \hbar \omega } { \hbar { \bf D } } } } { \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } + { \frac { \hbar \omega } { \hbar { \bf D } } } { \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } + { \frac { \hbar \omega } { \hbar { \bf D } } } { \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } } } \ { } } \\   \displaystyle ~ + { \frac { \hbar \omega } { \hbar { \bf D } + \hbar { \bf \Omega } } }  \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } + { \frac { \hbar \omega } { \hbar { \bf D } + { \bf \Omega } } } + { \frac { \hbar \omega } { \hbar { \bf D } + { \bf \Omega } } }  \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } + { \frac { \hbar \omega } { \hbar { \bf D } + { \bf \Omega } } } { \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } } \  \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } \  \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } \  \displaystyle { \frac { \mathrm { d } | { \bf D } } { \mathrm { d } { \bf D } + { \bf \Omega } } } \  \displaystyle { \frac { \mathrm { d } | { \bf R } | } { \mathrm { \bf \Omega } } } \  \displaystyle { \frac { \mathrm { d } | { \bf D } } { \mathrm { d } { \bf D } } } \  \displaystyle  \frac { \mathrm { d } | { \bf R } | }  \mathrm  \ \end{array}
$$

上式中 $\underbrace { \mathbf { \bar { \Phi } } ^ { [ i ] } \mathbf { Q } _ { \frac { \cdot } { \cdot } } ^ { \textit { \texttt { T } } } } _ { \mathbf { \Phi } ^ { [ i ] } \mathbf { D } ^ { \frac { \cdot } { \cdot } } }$ 是造成常规梯度类算法计算量大的主要原因。由于拉格朗日乘子 $\lambda$ 的任意性，通过控制 $\underbrace { \mathbf { \bar { \Phi } } ^ { [ i ] } \mathbf { Q } _ { \perp } } _ { \mathbf { \bar { \Phi } } ^ { [ i ] } \mathbf { D } ^ { \frac { i } { \cdot } } }$ 的系数为0可以相应地简化计算，即：

$$
\underbrace { \frac { 1 1 } { 4 } - 1 } _ { \begin{array} { l } { \frac { 1 } { 4 } } \end{array} } \mathrm { \bf { R } } _ { \frac { \cdot } { \cdot } } ^ { \textit { 1 } } \mathrm { \bf { \Sigma } } _ { \mathrm { \bf { \Sigma } } } = - \mathrm { \bf { \Sigma } } \frac { \ f } { \mathrm { \bf { Q } } }
$$

方程(3)即为流动问题的离散型伴随方程。满足伴随方程的基础上，简化后的目标函数为：

$$
\begin{array} { r l } & { \displaystyle \frac { \mathrm { d } L } { \mathrm { d } { \bf D } } = \frac { \frac { t _ { \mathrm { A R } } } { 2 \mathrm { e } } } { \hbar \mathrm { e } ^ { 2 } } + \frac { \sqrt { \frac { t _ { \mathrm { A R } } } { 2 } } } { 6 0 } { \bf D } ^ { \frac { 1 } { 2 } } \frac { \gamma } { 2 { \bf X } } } \\ & { + \left. \frac { t _ { \mathrm { A R } } } { \hbar \mathrm { e } ^ { 2 } } { \bf R } _ { \mathrm { B R } } ^ { T } + \frac { \sqrt { \frac { t _ { \mathrm { A R } } } { 2 } } } { 4 0 \mathrm { e } ^ { 2 } } { \bf X } ^ { T } \right. } \\ & { + \left. \frac { t _ { \mathrm { A R } } } { \hbar \mathrm { e } ^ { 2 } } { \bf R } _ { \mathrm { B R } } ^ { T } + \frac { \sqrt { \frac { t _ { \mathrm { A R } } } { 2 } } } { 4 0 \mathrm { e } ^ { 2 } } { \bf D } ^ { \frac { 1 } { 2 } } \frac { \gamma } { 2 { \bf X } } \right. } \end{array}
$$

# 1.2流动约束方程

# 1.2.1流动控制方程组

三维无量纲雷诺平均NS方程可以表述为如下形式：

$$
V \frac { \partial \mathbf { Q } } { \partial t } + \iiint _ { \Gamma } ( \mathbf { F } _ { i } \cdot \mathbf { n } ) d \Gamma - \iiint _ { \Gamma } ( \mathbf { F } _ { \nu } \cdot \mathbf { n } ) d \Gamma = 0
$$

其中， $\mathbf { n }$ 为控制体边界的外法向单位向量，Q为单元平均守恒变量， $\mathbf { F } _ { i }$ 为无粘通量， $\mathbf { F } _ { \nu }$ 为粘性通量。层流粘性计算采用完全气体假设，求解遵循Sutherland 公式。

# 1.2.2湍流模型

经由大量实验表明，本文选用的SA湍流模型具有非常强的鲁棒性，极适用于一般内流航空工程的应用。无量纲SA湍流模型控制方程如下：

$$
\begin{array} { r l } & { \cfrac { \mathrm { D } \tilde { v } } { \mathrm { D } t } = \cfrac { M _ { \infty } } { \rho R e } \left\{ \nabla \cdot [ ( v + ( 1 + c _ { b _ { 2 } } ) v \nabla \tilde { v } ] \right. } \\ & { \left. - c _ { b _ { 2 } } \tilde { v } \nabla ^ { 2 } \tilde { v } - \cfrac { M _ { \infty } } { R e } ( c _ { w _ { 1 } } f _ { w } - \cfrac { c _ { b _ { 1 } } } { \kappa ^ { 2 } } f _ { t _ { 2 } } ) \bigg ( \cfrac { \tilde { v } } { d } \bigg ) \right. } \\ & { \left. + c _ { b _ { 1 } } ( 1 - f _ { t _ { 2 } } ) \tilde { S } \tilde { v } \right. } \end{array}
$$

其中：

$$
f _ { \nu _ { 1 } } = \frac { \chi ^ { 3 } } { \chi ^ { 3 } + c _ { \nu _ { 1 } } ^ { 3 } } , \ \chi = \frac { \tilde { \upsilon } } { \upsilon }
$$

$$
\tilde { S } = S + \frac { M _ { \infty } } { R e } \frac { \tilde { \upsilon } } { \kappa ^ { 2 } d ^ { 2 } } f _ { \nu _ { 2 } } \ : , \ : f _ { t _ { 2 } } = c _ { t _ { 3 } } e ^ { - c _ { t _ { 4 } } \chi ^ { 2 } }
$$

$$
f _ { \nu _ { 2 } } = 1 - \frac { \chi } { 1 + \chi f _ { \nu _ { 1 } } } , f _ { \nu } = g \Biggl ( \frac { 1 + c _ { w _ { 3 } } ^ { 6 } } { g ^ { 6 } + c _ { w _ { 3 } } } \Biggr )
$$

$$
g = r + c _ { { \scriptscriptstyle w _ { 2 } } } \left( r ^ { 6 } - r \right) , r = \frac { M _ { \infty } } { R e } \frac { \tilde { \upsilon } } { \tilde { S } \kappa ^ { 2 } d ^ { 2 } }
$$

式(6)中 $s$ 为涡量的模， $d$ 为当前网格单元到壁面的最短距离。

# 1.3 优化方法

本次工作开发的优化程序包括问题目标函数建立、网格生成、流场求解、伴随场求解、敏感性计算、优化算法、网格变形共七个模块，详细优化流程(如流场求解方法、伴随场求解方法、优化算法以及网格变形等)参见文献12。

# 1.3.1目标函数

为使高超声速喷管推力系数最大化，本文选取的目标函数形式为：

$$
f = - \ T / T _ { 0 }
$$

其中 $T$ 为喷管推力系数， $T _ { 0 }$ 是初始喷管的推力系数。

# 1.3.2初边界条件

本次设计的单边膨胀喷管以4.5马赫的速度飞行在 $1 8 . 5 \mathrm { k m }$ 的高空，查得此高度的标准大气静压为 $6 9 9 4 . 8 \mathrm { P a }$ 。

喷管为超声速进口，依特征线理论，进口需指定所有的气动参数。进口给定马赫数1.4，静压$1 4 5 6 0 0 \mathrm { P a }$ ，静温 $1 5 0 0 \mathrm { K }$ ，比热比1.4；出口选择压力边界，并假设出口边界绝热和等熵，如果出口为超声速流动，则所有的气动参数均采用外推的方式进行计算；壁面条件采用无滑移壁面。当前程序初始条件选择以来流参数对全场进行初始化赋值。

# 1.3.3几何参数化方法

本文的设计变量选取喷管表面的500个节点，当发生扰动时，每个设计变量都在垂直于流线方向的平面内发生变动，继而改变喷管沿流程的面积分布。因此，参数化对象为气动形状的扰动而非气动形状本身，通过控制喷管的面积分布，抓住了喷管设计的关键因素，降低了优化设计变量的数目。喷管参数化方式为：

$$
r _ { n } ( \nu ) = r _ { n } ^ { b } + \mathrm { D } r _ { n } ( \nu )
$$

其中， $\mathbf { \sigma } _ { \nu }$ 为包含设计变量的矢量， $r _ { n } ( \nu )$ 是喷管型面在点 $n$ 处的坐标， $r _ { n } ^ { b }$ 为初始模型的型面坐标，$ { \mathrm Ḋ r Ḍ } _ { n } (  { \boldsymbol Ḋ \nu Ḍ } )$ 是扰动坐标，扰动坐标的具体表达式为：

$$
\mathrm { D } r _ { n } ( \nu ) = \bigotimes _ { i = 1 } ^ { m } \nu _ { m } n _ { n } ^ { p _ { m } }
$$

其中， $\mathbf { \nabla } _ { m }$ 表示设计变量的个数， $p _ { { \scriptscriptstyle m } }$ 表示第 $i$ 个设计变量的指数， $\mid n _ { n }$ 表示在点 $n$ 处的单位法向矢量。

# 2原型喷管方案设计

梯度类算法属于局域优化方法的一种，其最终优化目标为确定目标函数在优化域内的一个极值而非最值，不能保证优化结果的全局最优性。针对此问题，一种可行的解决方式为预先确定最优解所在的局部优化域，缩小伴随优化的优化区间以保证优化结果的有效性，因此原型喷管的设计至关重要。原型喷管作为伴随优化的起点，起到了“基因传承者”的作用,其性能一定程度上决定了后续伴随优化取得的效果。

为了提高性能，原型喷管的设计应采用具有全局寻优能力的优化算法，为此，控制原始喷管造型的参数需要尽可能少以减小原型喷管的设计计算量。本文的原型喷管设计过程中，给定尾喷管进口截面为圆形，喷管出口为矩形，整个优化过程中限制进出口形状以及喷管长度不变。在此基础上，沿流向的各展向剖面取为超椭圆，其面积和n指数沿流程分布作为优化参数，优化过程中，通过调节面积分布规律、超椭圆指数n分布规律以及下底板角度等9个参数，即可唯一确定喷管形状，见图1。

![](images/02fe5588d22bdfe513c40a1e80e143b384ca5f3510f3480118c7518eb66c7672.jpg)  
图1喷管造型示意图

该造型理念增强了喷管设计中的三维型面控制能力，特别注重面积沿流向的分布规律以及二面角原理的应用。

采用遗传算法进行原型喷管的设计时，喷管的网格数量为60万左右，为保证计算精度，Y-plus的值小于1，网格见图2。

![](images/4e0bcc5904cf13b8cd0a215c71e4264dddba01eabc8296036dc95faf5c8c3ea4.jpg)  
Fig.1 Diagram of Nozzle Modeling   
图2喷管网格布置  
Fig.2 Nozzle Grids

在9个控制参数的基础上，本文利用遗传算法进行进化寻优使喷管原始造型接近全局最优解。遗传算法的种群规模为10。由图3可发现种群进化到第八代时，推力系数由不足 $91 \%$ 迅速提升至 $9 3 \%$ 左右，且优化过程趋于稳定。将遗传算法优化过程的第八代计算结果作为原型喷管的最终设计，为后续伴随优化提供原始造型。图4为原型喷管马赫数在流动对称面内的分布云图以及沿流程的分布云图，可以发现，出口处马赫数分布较为均匀。

![](images/0ade21a1616affa5572bce9cf6ce1c3a8995be91c91c5533e7072cd0fecb4ab2.jpg)  
图3遗传算法收敛史

![](images/f56ae8ee50b122edf52ea7b94f5e7160fae7790c06c7adab450638b0f5b927ec.jpg)  
Fig.3 Convergence History of the Genetic   
图4原型喷管流场马赫数云图

Fig.4 Mach Number Distribution of the Original Nozzle

# 3伴随优化结果分析

以原型喷管为起点，通过喷管表面的500个设计变量对喷管进行精细化伴随优化设计，这种精细化程度是遗传算法及其它常规梯度类算法难以实现的。图5为目标函数随优化过程的迭代曲线。可以发现，在前三个优化迭代过程中，目标函数的提升较慢，这与优化算法、目标函数形式以及参数化方法都有关系；同时，优化在第四个优化过程中取得了最大的效果，推力提升了0.8个百分点左右；而后目标函数基本收敛，这预示着优化已经达到了极值，优化过程结束。本次伴随优化只进行了7次优化循环，计算量仅相当于14倍流场的计算量。

![](images/311e5ac09209d20072240c3b292ce03c76ea27ee31d50fbba1bb30551e4fa9cf.jpg)  
图5伴随优化目标函数收敛史

![](images/fc9cd15d9afa384c547e01b0c63aeb19525a234f2205283d0fe20e891df50027.jpg)  
Fig.5 Convergence History of the Objective Function Optimized by the Adjoint Method   
(a）对称面对比

![](images/4958ba852f9d55b53a7e80db56c2d716f2387d8bf4d3c77dc77b5bce7b140c2e.jpg)  
图6优化前后几何模型对比

本次伴随优化过程采用了常规的几何约束方法，限制进出口几何保持不变。图6为优化前后几何模型对比，可以发现，优化前后几何模型变化非常大，其中，圆圈处标记了变化最大位置处。图6(b)显示了二面角区的变化尤为明显。

![](images/7b26e9d54d90f79a2b84b52141779957871475c0eb42633c788e2c9d571109cd.jpg)  
Fig.6 Comparison of Geometry before and after Optimization   
(a）原型喷管对称面马赫数云图

![](images/7ee0f8dc52d59a817b80b00a515803bf244ad33e7d0ec9d29cf845a6323f3996.jpg)

图7优化前后对称面云图对比

Fig.7 Comparison of Flow Field before and after Optimization

图7为优化前后流动对称面内马赫数和静压分布云图。可以发现，优化前后的流场变化比较明显：原型喷管从进口到出口几何变化平缓，流场也是比较平缓地膨胀；相较于优化前，优化后喷管前半部分流场膨胀程度较低，而后半部分则急剧膨胀，下底板表现尤为明显。图8展示了马赫数沿流程的分布，也可以反映出优化后喷管前半部分膨胀程度小，但到出口处，优化后喷管的膨胀程度反而比原型喷管更大；尤其在角区附近，优化后的喷管出口四个角区膨胀程度更充分，角区流动得到了极大改善。

# 4总结

本文首先用较少的参数构造喷管，利用遗传算法进行全局性优化设计，得到性能良好的原型喷管；继而采用离散型伴随方法对原型喷管进行精细化优化设计，得到了推力系数继续提升0.8个百分点的最终设计结果。

本文开发的利用伴随方法对单边膨胀喷管进行设计的体系，无需对流动进行简化假设，并且不受到设计变量数量的限制，克服了现有设计方法的部分缺陷，满足了精细化设计的发展趋势。同时，本文的参数化模型为进气道及推进系统一体化优化设计提供了关键技术思路。

# 参考文献：

[1]Rao G V.Exhaust Nozzle Contour for Optimum Thrust[J]

Jet Propulsion: 1958,V28:377-382   
[2]Zudov V N,Lokotko A V ,Rylov A I.Numerical and Experimental Investigation of Two-Dimentional Asymmetric Nozzles[R].AIAA: 96-3141,1996   
[3]曹德一，李椿萱.高超声速飞行器尾喷管的优化设计[J]. 北京航空航天大学学报：2007，33(10)：1162-1165   
Cao Deyi，Li ChunXuan.The Optimation and Design of Outlet Nozzle in Hypersonic Aerocraf[J]. Journal of Beijing University of Aeronautics and Astronotics: 2007, 33(10): 1162-1163   
[4]陈兵,徐旭,蔡国飙.二维超燃冲压发动机尾喷管优化设计 [J].推进技术:2002，23(5)：433-437   
Chen Bing, Xu Xu, Cai Guobiao. Optimization And Design of Tail Nozzle for two dimensional scramjet[J].Journal of Propulsion Technology: 2002,23(5): 443-437   
[5]陈兵,徐旭,蔡国飙.基于遗传算法和空间推进方法的单壁 扩张喷管优化设计研究[J].航空学报:2007，28(4):827-832 Chen Bing,Xu Xu, Cai Guobiao. Optimization Design of Unilateral Expansion Nozzle Based on Genetic Algorithm and Space Propulsion Method[J]. Acta Aeronautica Astronautica Sinica: 2007,28(4):827-832   
[6]甘文彪,阎超.高超声速飞行器后体/尾喷管优化设计[J] 北京航空航天大学学报:2011，37(6)：1-6   
Gan Wenbiao,Yan Chao.Optimum Design of Hose ／Tail Nozzle forHypersonic Vehicle[J]. Journal of Beijing University of Aeronautics and Astronotics:2011, 37(6):1-6 [7]Jameson A.Aerodynamic Shape Optimization Using the Adjoint Method[R]. Lectures: Brussels, 2003   
[8]Giles M B, Pierce N A. Adjoint Equations in CFD: Duality, Boundary Condition and Solution Behavior[J]. AIAA Paper: 97-1850, 1997   
[9]Reuther J, Jameson A. Control Based Airfoil Design using the Euler Equations[J]. AIAA Paper: 94-4272-CP,1994   
[10]Reuther J, Jameson A.Aerodynamic Shape Optimization of Wing and Wing-body Configurations using Control Theory[J]. AIAA Paper: 95-0123-CP,1995   
[11]Reuther J，et al. Constrained Multipoint Aerodynamic Shape Optimization using an Adjoint Formulation and Parallel Computers[J].AIAA Paper: 97-0103   
[12]宋红超，季路成.目标函数形式对伴随优化影响的研究. 工程热物理会议:2016.   
Song Hongchao,Ji Lucheng. Influences of the Form of Objective Function on the Result Optimizied by Adjoint Method[J]. Meeting Paper: 2016