# 一种线性自抗扰控制器的无人直升机姿态控制方法研究

王云霞1，代冀阳1，王村松²，胡烽1(1．南昌航空大学 信息工程学院，南昌 330063;2．南京航空航天大学 自动化学院，南京 211106)

摘要：针对无人直升机模型复杂，控制器难于设计，易受外界干扰等问题，在建立亚拓系列直升机动力学模型基础上，提出了一种改进的二阶线性自抗扰控制器。首先，将线性扩张状态观测器用于估计影响输出结果的扰动，并加入跟踪微分器。然后，改进了控制器结构与反馈补偿系数，使直升机姿态角能够更快地响应所输入的指令，并能够按设定的角度飞行，以完成要求的任务；最后，通过引入白噪声干扰模块，来验证本文控制器的抗干扰能力。对比仿真结果表明，本文所提出的控制器对于无人直升机的姿态角有较好的控制效果，优于其他两种控制器。特别是在噪声干扰的条件下，也有较好的动态性能和鲁棒性。

关键词：改进线性自抗扰控制器；无人直升机；姿态角控制；抗干扰中图分类号：TP29 doi: 10.3969/j.issn.1001-3695.2017.11.0793

# Research on attitude control method of unmanned helicopter based on linear active disturbance rejection control

Wang Yunxia1,Dai Jiyangl,Wang Cunsong²,Hu Feng1 (1.CollegeofIformationEngineering,NanchangHangkongUniversityNanchang306,Cina;2.Automationlleof Nanjing University of Aeronautics& Astronautics,Nanjing211106,China)

Abstract: Inorderto solve the problems ofcomplex model ofunmannedhelicopter diffcultyofflightcontrolerdesign and susceptibleto exteral disturbances,this paper establish a kinetic modelof Trex series helicopters and propose an mproved second rder linearactive disturbancerejectioncontroler.First,usethe LADRCto estimate thedisturbance that fects the outputandadd thetracking diferentiatoratthesame time.Secondly,improve thecontroller structureandthe feedback compensationcoeffcient,sothatthehelicopteratitudeanglecanrespondtotheinput command morequickly,andcan flyata set angle toaccomplish therequired tasks;Finaly,introducethe white noise interference module to verifytheanti jamming abilityofthecontroler.Comparative simulationresultsshow that thecontroller inthis paper has better control effcton the atitude angleoftheunmanned helicopter.Itis better than theothertwocontrollers.Especiallyintheconditionof noise interference,it also has better dynamic performance and robustness.

Key Words: improved linear ADRC controller; unmanned helicopter; attitude angle control; anti-interference

# 0 引言

随着经济水平的提升，以及科学技术的发展，各国在战场上使用的武器也越来越智能化[1]。而旋转翼直升机，特别是无人直升机，以其对空间场地要求小、方向与速度易控制及安全性高的特点，在军事上的运用达到了前所未有的热度[2]。然而，直升机作为一个多输入多输出的非线性系统，具有强耦合性的六自由度刚体[3-5]，在执行任务时对其的反映时间及飞行的稳定性要求较高。此外，直升机极易受到外界的干扰，这不但给直升机操控手带来很大的困难，也给直升机飞行控制器的设计带来了巨大挑战，所以设计一个能够使直升机快速动作及有效避免外界干扰影响的控制器，不仅符合今日军事战场上的急切需求，也是民事应用中的安全保障。

对于直升机跟踪控制器的设计，国内外学者都取得了很多的成果。文献[6]设计了一种自适应反步法控制器，通过非线性自适应律来估计直升机所受到的各种干扰，然后将干扰值整合至反步法控制器中，对干扰有着较好的控制，但在干扰频率较高环境下的控制效果略显差强人意；文献[7]提出了一种小型无人直升机的模型预测控制轨迹跟踪(MPCTT)系统，跟踪的响应时间快，效果好，不过在直升机遇到干扰情况下的控制效果，并没有做详细的验证；文献[8-9]建立直升机模型的仿射非线性方程组，对建立的仿射非线性方程设计自适应模糊滑模控制器(AFSMC)，不过在控制中，仿射出的直升机模型较原模型还是有一定区别的；而对于直升机这类多输入多输出的复杂六自由度系统，前述的控制器对通道之间的交叉耦合是难以消除的，并且对于外界的干扰也没有较好的控制，故文献[10\~12]提出了自抗扰控制器(ADRC)，可以不依赖于被控对象本身的具体模型，通过状态观测器预测影响系统输出的扰动，然后对系统实施补偿以达到控制的效果；文献[13\~15]在自抗扰控制器的基础上，提出线性自抗扰控制器(LADRC)，算法简单易实现，需要调整的参数较少，不但有很好的跟踪效果，而且还有一定的抗干扰能力。

为了加快姿态角的响应速度，实现姿态角的稳定控制及提高直升机的抗干扰能力，以满足直升机在执行任务时对实时性与准确性的要求，本文在文献[16]的基础上，采用线性扩张状态观测器，加入跟踪微分器，并改进线性自抗扰控制器的结构与反馈补偿系数，对亚拓600直升机的姿态角进行控制，通过对比分析文献[16]中控制系统、模糊自整定PID(简称模糊PID)控制系统与本文控制系统的仿真实验结果，发现改进后的控制器响应时间更快，跟踪误差更小，并通过噪声干扰模块验证本文控制器的抗扰动能力。

# 1 无人直升机的飞行动力学模型

# 1.1主旋翼模型

主旋翼作为无人直升机最关键的部位，既可以通过旋转产生上升的升力，又可以操纵直升机，使其产生做俯仰，升降，横滚等运动所需要的力与力矩，从而操控直升机向各个方向运动。本文假定直升机的桨叶为刚体薄片、旋翼旋转时速度保持恒定不变、把旋翼的入流角与挥舞角近似于小角度使用，且忽略空气压缩性及桨叶失速的影响。则垂直上升飞行时主旋翼的升力为

$$
T _ { z j } = C _ { T } ^ { z j } \rho S _ { z j } ( \varOmega _ { z j } R _ { z j } ) ^ { 2 }
$$

其中： $C _ { T } ^ { z j }$ 为主旋翼拉力系数， $\rho$ 为空气密度， $R _ { z j }$ 为主旋翼半径， $S _ { z j } = \pi R _ { z j } ^ { 2 }$ 为桨盘面积， $\varOmega _ { z j }$ 为主旋翼旋转角速度。

将主旋翼的拉力分解到 $\boldsymbol { \cdot } , \boldsymbol { y }$ 、 $z$ 三个坐标轴上，即可得到直升机在 $x$ 、 $y$ 、 $z$ 三坐标轴上的作用力，这三个作用力可表示为

$$
X _ { \it z j } = - T _ { \it z j } a _ { \it I } , Y _ { \it z j } = T _ { \it z j } b _ { \it I } , Z _ { \it z j } = T _ { \it z j }
$$

由此可以得到主旋翼的滚转力矩 $L _ { z j }$ 、俯仰力矩 $M _ { z j }$ 及偏航力矩 $N _ { z j }$ 的表达式为

$$
\begin{array} { r } { L _ { z j } = ( K _ { \beta } + T _ { z j } h _ { z j } ) b _ { I } } \\ { M _ { z j } = ( K _ { \beta } + T _ { z j } h _ { z j } ) a _ { I } } \\ { N _ { z j } = C _ { q } ^ { z j } \rho R ^ { 3 } ( \varOmega _ { z j } R ) ^ { 2 } } \end{array}
$$

其中： $C _ { q } ^ { z j }$ 为旋翼反扭矩系数， $a _ { \scriptscriptstyle { l } }$ ， $b _ { \scriptscriptstyle { I } }$ 分别为主旋翼的纵，横

向挥舞角。

# 1.2尾桨模型

尾桨旋转时产生的拉力为

$$
Y _ { { \scriptscriptstyle w j } } = 1 / 2 C _ { \scriptscriptstyle T } ^ { w j } \rho \pi R _ { { \scriptscriptstyle w j } } ^ { { \mathrm { ~ ~ 2 ~ } } } ( \varOmega _ { { w j } } R _ { { w j } } )
$$

其中： $C _ { T } ^ { w j }$ 为尾桨拉力系数， $\varOmega _ { w j }$ 为尾桨旋转角速度， $R _ { w j }$ 为尾桨半径。

尾桨旋转时产生的偏航力矩与滚转力矩分别为

$$
N _ { _ { w j } } = - Y _ { _ { w j } } l _ { _ { w j } } , L _ { _ { w j } } = Y _ { _ { w j } } h _ { _ { w j } }
$$

其中： $l _ { w j }$ ， $h _ { w j }$ 分别为尾桨旋转轴中心到机体重心的水平距离与垂向距离。

# 1.3平尾和垂尾模型

直升机的平尾即水平安定面，安装于尾杆上，在直升机飞行时，为其提供俯仰通道上的阻尼，并对俯仰的稳定起到一定的作用。平尾的受力为

$$
Z _ { p w } = \frac { 1 } { 2 } \rho S _ { p w } ( C _ { z } ^ { p w } \big | u _ { a } \big | w _ { p w } + \Big | w _ { p w } \Big | w _ { p w } )
$$

其中： $S _ { p w }$ 为平尾面积， $C _ { z } ^ { p w }$ 为平尾升力系数， $w _ { p w }$ 为平尾的垂向速度。则平尾产生的俯仰力矩为

$$
M _ { p w } = Z _ { p w } l _ { p w }
$$

直升机的垂尾即垂直安定面，安装于尾桨附近，为直升机提供侧向拉力，以增加直升机的航向阻尼，并对航向的稳定起到一定的作用。则垂尾的侧向力为

$$
Y _ { c w } = - 1 / 2 \rho S _ { c w } ( C _ { T } ^ { c w } V _ { ? } ^ { c w } + \left| \nu _ { c w } \right| ) \nu _ { c w }
$$

其中： $V _ { \ast } ^ { c w } = \sqrt { ( { u _ { a } } ^ { 2 } + { w _ { c w } } ^ { 2 } ) }$ ， $S _ { c w }$ 为垂尾的面积， $C _ { T } ^ { c w }$ 为垂尾的升力系数， $\nu _ { _ { c w } }$ 为垂尾相对于空气运动时的侧向速度。

垂尾作用时产生的滚转力矩与偏航力矩分别为

$$
L _ { _ { c w } } = Y _ { _ { c w } } h _ { _ { c w } } , ~ N _ { _ { c w } } = - Y _ { _ { c w } } l _ { _ { c w } }
$$

其中： $l _ { { { c w } } }$ ， $h _ { { } _ { c w } }$ 分别为尾桨中心到机体质心的水平距离与垂向距离。

# 1.4机身模型

机身的空气动力在 $x$ ，y， $z$ 三坐标轴上的分量可表示为

$$
\begin{array} { l } { { { \displaystyle X _ { j s } = - \frac { 1 } { 2 } C _ { x } ^ { j s } \rho V ^ { 2 } S _ { j s } } } } \\ { { \displaystyle Y _ { j s } = \frac { 1 } { 2 } C _ { y } ^ { j s } \rho V ^ { 2 } S _ { j s } } } \\ { { \displaystyle Z _ { j s } = \frac { 1 } { 2 } C _ { z } ^ { j s } \rho V ^ { 2 } S _ { j s } } } \end{array}
$$

其中： $C _ { x } ^ { j s }$ ， $C _ { y } ^ { j s }$ ， $C _ { z } ^ { j s }$ 分别为机身沿三个坐标轴方向上分力的气动系数， $V$ 为机体相对于空气飞行的合速度， $S _ { j s }$ 为机身的有效迎面面积。

机体在 $x$ 、y、 $z$ 三坐标轴上的力矩分量可表示为

$$
\begin{array} { l } { { { \displaystyle L _ { j s } = \frac { 1 } { 2 } C _ { L } ^ { j s } \rho V ^ { 2 } S _ { j s } l _ { j s } + \mathcal { A } L _ { j s } } } } \\ { { \displaystyle M _ { j s } = \frac { 1 } { 2 } C _ { M } ^ { j s } \rho V ^ { 2 } S _ { j s } l _ { j s } + \mathcal { A } M _ { j s } } } \\ { { \displaystyle N _ { j s } = \frac { 1 } { 2 } C _ { N } ^ { j s } \rho V ^ { 2 } S _ { j s } l _ { j s } + \mathcal { A } N _ { j s } } } \end{array}
$$

其中: $C _ { L } ^ { j s }$ ， $C _ { M } ^ { j s }$ ， $C _ { N } ^ { j s }$ 分别为机体气动力对机体本身的重心构成的横滚力矩系数、俯仰力矩系数与偏航力矩系数， $l _ { j s }$ 为机身总长度， $\varDelta L _ { j s }$ ， $\mathbf { \nabla } \mathcal { A } { M _ { \mathbf { \omega } _ { j s } } }$ ， $\varDelta N _ { _ { j s } }$ 分别为绕对应机体轴的修正力矩。

# 1.5机体的合力与合力矩

直升机的重力在 $x$ ， $y$ ， $z$ 三个坐标轴上的分力表示为

$$
\begin{array} { l } { { X _ { _ { G } } = - m g s i n \theta \nonumber } } \\ { { Y _ { _ { G } } = - m g s i n \varphi c o s \theta \nonumber } } \\ { { Z _ { _ { G } } = - m g c o s \varphi c o s \theta } } \end{array}
$$

其中： $m$ 为直升机的总质量。则在机体坐标系下，直升机的合力与合力矩表示为

$$
F _ { _ B } = { \left[ \begin{array} { l } { F _ { _ x } } \\ { F _ { _ y } } \\ { F _ { _ z } } \end{array} \right] } = { \left[ \begin{array} { l l l l l l } { X _ { _ G } } & { X _ { _ { z j } } } & { X _ { _ { w j } } } & { X _ { _ { p w } } } & { X _ { _ { c w } } } & { X _ { _ { j s } } } \\ { Y _ { _ { G } } } & { Y _ { _ { z j } } } & { Y _ { _ { w j } } } & { Y _ { _ { p w } } } & { Y _ { _ { c w } } } & { Y _ { _ { j s } } } \\ { Z _ { _ G } } & { Z _ { _ { z j } } } & { Z _ { _ { w j } } } & { Z _ { _ { p w } } } & { Z _ { _ { c w } } } & { Z _ { _ { j s } } } \end{array} \right] }
$$

$$
{ \cal M } _ { _ B } = \left[ \begin{array} { c } { { L } } \\ { { M } } \\ { { N } } \end{array} \right] = \left[ \begin{array} { c c c c c } { { L _ { z j } } } & { { L _ { _ { w j } } } } & { { L _ { _ { p w } } } } & { { L _ { _ { c w } } } } & { { L _ { _ { j s } } } } \\ { { M _ { z j } } } & { { M _ { _ { w j } } } } & { { M _ { _ { p w } } } } & { { M _ { _ { c w } } } } & { { M _ { _ { j s } } } } \\ { { N _ { _ { z j } } } } & { { N _ { _ { w j } } } } & { { N _ { _ { p w } } } } & { { N _ { _ { c w } } } } & { { N _ { _ { j s } } } } \end{array} \right]
$$

# 1.6全机的动力学模型

将牛顿第二定律 $F = m a$ 与以上的结论相结合分析，则直升机的动力学方程为

$$
\begin{array} { r l } & { \dot { V } { = } F _ { _ B } / m { - } W { \times } V } \\ & { \dot { W } { = } I ^ { - } \big [ M _ { _ B } { - } W { \times } ( I W ) \big ] } \\ & { \dot { \gamma } { = } E W } \end{array}
$$

直升机机体坐标系的外力矩作用下的角运动方程为

$$
M _ { _ B } = \left[ \begin{array} { l } { L } \\ { M } \\ { N } \end{array} \right] = \left[ \begin{array} { l } { I _ { _ { x x } } \dot { p } } \\ { I _ { _ { y y } } \dot { q } } \\ { I _ { _ { z z } } \dot { r } } \end{array} \right] + W \times ( I W )
$$

其中: $V$ 为线速度， $W$ 为角速度，》为姿态角， $E$ 为角速度转换到欧拉角速度的转换矩阵， $I$ 为转动惯量矩阵，且

$$
V = [ { \boldsymbol { u } } \quad \nu \quad { \boldsymbol { w } } ] ^ { \mathrm { { T } } } , \ W = [ { \boldsymbol { p } } \quad { \boldsymbol { q } } \quad { \boldsymbol { r } } ] ^ { \mathrm { { T } } } , \ \gamma = [ \varphi \quad { \boldsymbol { \theta } } \quad \psi ] ^ { \mathrm { { T } } }
$$

由此可得，直升机的非线性动力学方程为

$$
\begin{array} { r }  \{ \begin{array} { l l } { \dot { \hat { u } } } \\ { \dot { \hat { v } } } \\ { \dot { \hat { w } } } \\ { \dot { \hat { w } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { q } } } \\ { \dot { \hat { q } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { p } } } \\ { \dot { \hat { \phi } } } \\ { \dot { \hat { \phi } } } \\ { \dot { \hat { \phi } } } \\ { \dot { \hat { \psi } } } \end{array}  [ \begin{array} { c } { \mathrm { r } \cdot \mathrm { w } \cdot \mathrm { w } q - g \cdot \mathrm { a } \hat { m } \hat { p } + \sum { F } _ { x } \hat { f } _ { m } } \\ { \mathrm { w } \cdot \mathrm { s } \mathrm { w } \hat { p } + \mathrm { s } \cos \delta \mathrm { i } \hat { w } + \sum { F } _ { x } \hat { f } _ { m } } \\ { \mathrm { a } q - \mathrm { v } \cdot \mathrm { s } \cos \delta \mathrm { i } \hat { \omega } \cos \hat { \mathrm { \Omega } } { + \sum { F } _ { x } \hat { f } _ { m } } } \\ { \mathrm { e } \cdot \hat { \hat { v } } _ { x } \cdot \hat { f } _ { x } } \\ { \mathrm { p } \cdot \hat { \hat { q } } _ { x } \cdot \sum \mathrm { a } \hat { w } \hat { f } _ { x } } \\ { \hat { p } ( \hat { t } _ { x _ { x } } - T _ { x _ { x } } ) \hat { f } _ { x _ { x } } \pm \sum \mathrm { a } \hat { f } _ { x } \hat { f } _ { x _ { x } } } \\ { \hat { p } \cdot \mathrm { s } \cdot \mathrm { w } \hat { f } _ { x } } \\ { \mathrm { p } \cdot \mathrm { s } \cdot ( \mathrm { q } \cdot \mathrm { s } \cos \hat { \mathrm { p } } \times \mathrm { o } \hat { m } ) } \\ { \mathrm { q } \cdot \mathrm { c } \cdot \mathrm { s } \cdot \mathrm { c } \cdot \mathrm { s } \hat { p } \mathrm { s } \cdot \mathrm { c } \hat { p } } \\ { \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { s } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \hat { p } } \\ { \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \cdot \mathrm { c } \hat { p } \times \mathrm { c } \hat { q } } \\  \hat { p } \cdot \mathrm { s } \cdot \mathrm { c } \end{array} \end{array}
$$

根据所建立的直升机的非线性模型，采用小扰动法进行线性化，即在直升机的飞行平衡点处将其运动方程按Taylor级数展开，并忽略二级及更高阶的导数，然后将直升机运动状态下的各个参量表示为基准状态下的值加上一个小扰动增量[15]，该方法使用起来较为简略，此处便不再赘述。由此方法可得直升机在机体轴系下的增量线性状态方程

$$
\varDelta \dot { X } = A \varDelta X + B \varDelta \delta
$$

其中: $\varDelta X = [ \varDelta u$ Δv Δw △p Δq $\boldsymbol { \varDelta r }$ 4 $\varDelta \theta$ Ay $a _ { _ I } \quad b _ { _ I } \mathbf { J } ^ { \mathrm { { T } } }$

$$
\begin{array} { r l } { \boldsymbol { \mathcal { A } } \boldsymbol { \delta } = \left[ \mathcal { A } \delta _ { l a t } \quad \mathcal { A } \delta _ { l o n } \quad \mathcal { A } \delta _ { p e d } \quad \mathcal { A } \delta _ { c o l } \right] ^ { \mathrm { T } } } \end{array}
$$

由此可得到直升机的增量运动方程，将其写成状态空间方程的形式，便可得到系统矩阵 $A$ 与输入矩阵 $B$ ，式中的 $\varDelta \delta _ { l a t }$ 、$\varDelta \delta _ { l o n }$ 、 $\varDelta \delta _ { p e d }$ 和 $\varDelta \delta _ { c o l }$ 分别表示旋翼横向周期变距、纵向周期变距、尾桨总距和主旋翼总距。其中参照文献[17]中亚拓600 直升机的各个参数，并将对应的参数代入到矩阵 $A$ 和矩阵 $B$ 中，便得到了亚拓600直升机悬停状态下的线性化模型。

# 2 改进线性自抗扰控制器的设计

线性自抗扰控制(LADRC)不考虑系统内部的具体结构，通过跟踪微分器来获得微分信号，并实现过渡过程的配置；通过线性状态观测器(LESO)来估计出实时系统的状态及扰动信息，预测系统的不确定性，即系统的内外扰动及模型的误差等，然后对误差系统进行反馈补偿，相对于ADRC所需调节的参数更少。

本文所设计的控制器采用二阶LADRC，主要模块是跟踪微分器(trackingdifferentiator-TD)和线性扩张状态观测器(linearextended stateobserver-LESO)两部分，结构简单易懂，算法清晰明了，有跟踪微分器中的参数 $\boldsymbol { r } , \boldsymbol { h } \mathrm { ~ } , \boldsymbol { T }$ ，线性扩张状态观测器的中的参数 $\boldsymbol { w } _ { o }$ ， $b _ { o }$ ，及反馈补偿回路中的参数 $w _ { o } , w _ { c } , k _ { d }$ 共有七个参数需要整定。本控制器相对于文献[16]加入了跟踪微分器，设计了控制器的新结构，改进了反馈补偿系数。改进后的控制器内部结构如图1所示，其中 $I n _ { - } \gamma$ 为输入姿态角的目标值，4M为直升机的输入通道参量，Y为姿态角反馈量。

![](images/e7895691be7d00fae71ba4f48b3d86162d69cc536367c1b8f9525fb7ac7af2e8.jpg)  
图1改进LADRC 的结构原理图

# 2.1跟踪微分器（TD)

跟踪微分器为控制器安排过渡过程。其离散表达式为

$$
\begin{array} { l } { { X _ { \mathit { I } } ( k + I ) = X _ { \mathit { I } } ( k ) + T X _ { \mathit { 2 } } ( k ) } } \\ { { X _ { \mathit { 2 } } ( k + I ) = X _ { \mathit { 2 } } ( k ) + T f h a n ( X _ { \mathit { I } } ( k ) , X _ { \mathit { 2 } } ( k ) , u ( k ) , r , h ) } } \end{array}
$$

其中: $X _ { \mathit { l } } ( k + \mathit { l } )$ ， $X _ { 2 } ( k + I )$ 为跟踪微分器的两个输出量，且分别跟踪输入值 $I n _ { - } \gamma$ 的值与 $I n _ { - } \gamma$ 的微分值， $\mathrm { ~  ~ { ~ \cal ~ T ~ } ~ }$ 为采样周期， $\boldsymbol { r }$ 决定跟踪速度的快慢， $h$ 对扰动有一定的滤波效果，增大该值可以更好地抑制误差。fhan函数为自抗扰控制技术中常用的非线性函数，该函数的表达式如(20)所示，并通过编写三个通道的S函数来建立跟踪微分器的函数模块。

$$
\begin{array}{c} \begin{array} { r l } & { | Y = X _ { + } + \hbar X _ { 2 }  } \\ & {  | d  = r h } \\ & { | d _ { \theta } = h d  } \\ & { | a _ { \theta } = \sqrt { d ^ { 2 } + \delta ^ { * } \vert Y \vert } | } \\ & {  | a = \{ X _ { + } + \frac { ( a _ { \theta } - d _ { \theta } ) - d } { 2 } \delta { i g n } ( Y ) , \qquad \begin{array} { r l } & { \vert Y \vert > d _ { \theta } } \\ & { \vert Y \vert < d _ { \theta } } \end{array}  } \\ & { | f  \leq d _ { \theta } } \\ & {  \hbar a n = \{ - r \delta { i g n } ( \alpha ) , \quad  d  > d  } \\ & { | a  \leq d } \end{array}   \end{array}
$$

# 2.2线性扩张状态观测器（LESO)

由上章所建直升机的姿态角模型分析可知，对于姿态角的运动可用二阶微分方程表达，故在控制器中可采用二阶线性扩张状态观测器[18]，其表达式为

$r _ { \theta } = 8 . 2 , h _ { \theta } = 1 . 0 6 , T _ { \theta } = 1 . 2 3 6 , r _ { \psi } = 0 . 0 1 , h _ { \psi } = 3 . 9 6 , T _ { \psi } = 1 . 4 9 2 , c o r r _ { \psi } = 0 . 0 9 2$ 将改进前的LADRC、改进后的LADRC与模糊PID控制三控制器的输出结果作对比。首先给 $\varphi$ ， $\theta$ ， $\psi$ 三个姿态角分别输入常量 $1 ^ { \circ }$ ， $3 ^ { \circ }$ ， $5 ^ { \circ }$ ，分别得到图3-5，通过对比可以看出，对于 $\varphi$ 角的控制，改进前的控制器虽然也有不错的控制效果，但姿态角的响应时间相对于改进后的略慢，虽然改进后的姿态角波形波动略大，但超调量较低，这对整体系统不会产生不良的影响，而模糊PID控制器达到稳定值的时间相对较慢，而且在靠近目标值前有一定的波动；对于 $\theta$ ， $\psi$ 两个角度通道，改进后的控制器比改进前及模糊PID控制器的响应时间更快，一般在2s-4s之间就可以达到并稳定在目标值，而改进前及模糊PID控制器则一般在5s及以后才能达到稳定，这对于直升机在做任务的过程中，本文控制器对其时效性的要求能够得到更好的满足。

$$
\left\{ \begin{array} { l } { { \dot { z } } _ { I } = z _ { 2 } - \beta _ { o I } z _ { I } + \beta _ { o I } y } \\ { { \dot { z } } _ { 2 } = z _ { 3 } - \beta _ { o 2 } z _ { I } + \beta _ { o 2 } y + b _ { o } u } \\ { { \dot { z } } _ { 3 } = - \beta _ { o 3 } z _ { I } + \beta _ { o 3 } y } \end{array} \right.
$$

该方程的特征方程为 $s ^ { 3 } + \beta _ { O I } s ^ { 2 } + \beta _ { O 2 } s + \beta _ { O 3 }$ ，为了更好地预测对象的状态与"总和扰动”，将特征方程式配置成 $\left( s + w _ { o } \right) ^ { 3 }$ 的形式，即参数 $\beta _ { o l }$ ， $\beta _ { o 2 }$ ， $\beta _ { o 3 }$ 分别赋值为 $3 w _ { o }$ ， $3 { w _ { o } } ^ { 2 }$ ， ${ w _ { o } } ^ { 3 }$ ， $w _ { o }$ （204为观测器的带宽，由此可知，LESO 仅有 $\boldsymbol { w _ { o } }$ 和 $b _ { o }$ 两个参数需要整定。则观测器的状态空间方程为

$$
{ \left[ \begin{array} { l } { { \dot { z } } _ { I } } \\ { { \dot { z } } _ { 2 } } \\ { { \dot { z } } _ { 3 } } \end{array} \right] } = { \left[ \begin{array} { l l l } { - 3 w _ { o } } & { I } & { O } \\ { - 3 w _ { o } ^ { 2 } } & { O } & { I } \\ { - 3 w _ { o } ^ { 3 } } & { O } & { O } \end{array} \right] } { \left[ \begin{array} { l } { z _ { I } } \\ { z _ { 2 } } \\ { z _ { 3 } } \end{array} \right] } + { \left[ \begin{array} { l l } { O } & { 3 w _ { o } } \\ { b _ { o } } & { 3 w _ { o } ^ { 2 } } \\ { O } & { 3 w _ { o } ^ { 3 } } \end{array} \right] } { \left[ \begin{array} { l } { u } \\ { y } \\ { z } \end{array} \right] }
$$

# 3 仿真实验与结果分析

在上章设计的控制器的基础上，在MATLAB/Simulink环境下搭建亚拓600直升机模型及控制仿真系统，整体模型如图2所示。In_y为输入姿态角的目标值，LADRC将控制的结果通过舵机输入直升机模型中，从而得到直升机的运动姿态角》，然后将姿态角反馈至控制器中，与目标输入值作比较并得到两者的误差值，通过观测器来估计出该误差，最后对误差进行补偿控制从而减小误差，其中 $f$ 为直升机飞行时受到的外界扰动。

![](images/03d293fcdd4045c7eea1d0a972e7859408d241e708c4ce5e060cd94e4147a027.jpg)  
图2直升机姿态角跟踪的结构图

# 3.1三控制器控制效果对比

首先，在输入扰动 $f = 0$ 时，给三个姿态角通道设定不同的跟踪微分器的参数值，分别为 $r _ { \phi } = 0 . 0 1 1$ ， $h _ { \phi } = 1 2 . 6 6 3$ ， $T _ { \phi } = 0 . 2$ ：

![](images/4c69ab4b76b773494be2d032dfe581a47d3ffb2b4435a4a7112eeff06ffff334.jpg)  
图3三控制器对滚转角 $\phi$ 的控制效果对比图

![](images/bc5fa7d60ad79a660b8bbb1a90a9ee12d19805e9a6eec02ec01c4b5c70e619af.jpg)  
图4三控制器对俯仰角 $\theta$ 的控制效果对比图

![](images/951c52ee992ea21b2b3262bb5b79c4630d1efddeb2b817946a53df8466a09408.jpg)  
图5三控制器对偏航角 $\psi$ 的控制效果对比图

为了更好地验证本文控制方法的控制效果，保持之前所有参数不变，在此基础上给三姿态角输入方波信号，将该模块的参数设置为：延迟时间为5，周期为50，幅值为5，脉宽为15，通过对比三个控制器控制下的三姿态角响应曲线及误差响应曲线，得到图6-7，从仿真对比图中可以看出，三种控制器对于输入的方波都会产生相应的响应，但改进后的LADRC使直升机的姿态角能够更快、更准确地完成指定的方波响应动作。通过对比方波响应的误差图可以发现，三控制器在响应速度上都有一定的延时，不过改进后的LADRC在三个姿态角通道上的控制误差最小，误差持续的时间也最短。经上述对比分析，改进后的LADRC的直升机姿态角控制效果要优于改进前的LADRC及模糊PID控制器的控制效果。

![](images/1d886a853154efb75f1132a1acf5608ab6350058911bc4430e273ebff619df70.jpg)

![](images/447518760659ae79a16eecace84d84885db75f72f92acc4f33fd5847dbcc3b06.jpg)  
图6三控制器在输入方波时姿态角响应曲线

3.2改进LADRC中加入噪声扰动时的控制仿真实验直升机在飞行过程中很容易遇到外界干扰，对于直升机而言，小的干扰也可能会造成很大的飞行困扰。为了验证本文控制器的抗干扰效果，在本文的直升机模型中加入有限带宽白噪声干扰(band-limitedwhite noise)，将该模块的参数设置为：噪声强度为0.01，采样时间为0.01，发生随机数的开始种子为默认值23341，白噪声信号图如图8所示。由于直升机在飞行过程中，姿态角一般按给定的固定角度进行增减变化，故根据此变化规律，在加入白噪声干扰的基础上给直升机的三姿态角分别输入阶跃响应和正弦信号。首先输入阶跃响应，并将该模块的参数设置为：延迟时间为5，幅值为10，得到图9，白噪声干扰下输入阶跃响应时姿态角跟踪曲线；为进一步验证本文控制器对于实时变化信号的控制效果，给直升机姿态角输入正弦信号 $I n _ { - } \gamma = 1 0 \mathrm { s i n } ( 0 . 4 t ) r a d$ ，具体的参数设置为幅值为10，角频率为0.4，得到图10，白噪声干扰下输入正弦信号时姿态角的跟踪曲线及跟踪误差响应曲线。

由图9可以看出，在白噪声干扰下的姿态角有很快的响应速度，所加入的扰动并没有给直升机的姿态角角度的控制带来明显的影响，由图10可以看出，在白噪声干扰下对于正弦曲线的跟踪效果良好，跟踪的总误差能够保持在 $\pm 4 ^ { \circ }$ 以内，总体而言，本文控制器在噪声扰动下的姿态角跟踪既具有快速性，又具有准确性与稳定性。

![](images/a49c45db4db543e59913ccf9e92f23d9872a0516ffde0c3ae58e88e97eb3fecd.jpg)  
图8有限带宽白噪声干扰显示图

![](images/f316e9e532bce59649c700e27a543a65eb2b46bb13d7a5df1aecf50371336904.jpg)  
图7三控制器在输入方波时姿态角控制误差对比图  
图9白噪声干扰下输入阶跃响应时姿态角跟踪曲线

![](images/bd0729c070cc301f658c3e0e6ab7772469436c175db88af9a7ba1d2905db42ef.jpg)  
图10白噪声干扰下输入正弦信号时姿态角跟踪曲线及误差响应曲线

# 4 结束语

无人直升机是多输入多输出、强耦合、非线性强的六自由度刚体，本文根据亚拓600无人直升机自身的结构与飞行特性，建立其动力学模型。本文提出的改进LADRC中加入了跟踪微分器，并改进了控制器连接结构与反馈补偿系数。改进后的线性自抗扰控制器结构相对简单，算法清晰。最后在MATLAB/simulink环境中搭建直升机模型与控制系统，通过给定三个姿态角固定的角度信号及方波信号，将改进前的LADRC、本文提出的改进的LADRC与模糊PID 控制器的控制方法分别应用于直升机的姿态角控制中。对比三控制器的控制结果发现，在本文控制器的控制下，姿态角响应速度更快，稳定性更好；此外，在白噪声干扰下，本文控制器也能对指定的阶跃信号及正弦信号快速作出响应，不仅有较高的跟踪准确性，也具有良好的抗干扰性能。

# 参考文献：

[1]代冀阳，王村松，殷林飞，等．飞行器分层势场路径规划算法[J].控 制理论与应用,2015,32(11):1505-1510.   
[2]Sandino LA,Bejar M,Kondak K,et al.A square-root unscented Kalman filter for attitude andrelative position estimation of a tethered unmanned helicopter [C]// Proc of International Conference on Unmanned Aircraft Systems.015.567-576.   
[3]He Y Q,Han JD.Acceleration-feedback-enhanced robust control of an unmanned helicopter[J]. Journal of Guidance Control & Dynamics,2010, 33 (4):1236-1250.   
[4]Wang B,Chen B M,Tong HL.An RPT approach to time-critical path following of an unmanned helicopter $[ \mathrm { C } ] / \AA$ Proc of the 8th Asian Control Conference. 2011: 211-216.   
[5]Ding L,Wu H, Yao Y.Chaotic Artificial bee colony algorithm for system identification ofasmallscale unmanned helicopter[J]. International Journal of Aerospace Engineering, 2015,2015 (1956): 1-11.   
[6]He YB. Adaptive backstepping-based robust tracking control of unmanned helicopters with disturbances[J].ControlTheory&Appications,2013,30 (30): 834-843.   
[7]Castil CL,MorenoW, Valavanis K P. Unmanned helicopter waypoint trajectory tracking using model predictive control [C]/ Proc of Conference on Control &Automation. 2008: 1-8.   
[8]Mahmoud M S,Koesdwiady A B. Improved digital tracking controler design for pilot-scale unmanned helicopter[J].Journal of the Franklin Institute,2012,349 (1): 42-58.   
[9]Razzaghian A, Moghaddam R K. Adaptive Fuzzy Sliding Mode Control for a Model-Scaled Unmanned Helicopter[J].2016,2016 (3): 286-302.   
[10] Gao Z. Active Disturbance Rejection Control: A paradigm shift in feedback control system design [C]/ Proc of American Control Conference.2006: 2399-2405.   
[11] Zou J,Fu X, Yang HY.Active disturbance rejection control for hydraulic width control system for rough mill[J]. Journal of Zhejig University Science A,2007,8 (9): 1429-1434.   
[12] Yanbo, Yuan,Zhang. Design of arobust guidance law via active disturbance rejection control[J]. Journal of Systems Engineering and Electronics,2015, 26 (2): 353-358.   
[13]丁力，马瑞，单文桃，等．小型无人直升机航向线性自抗扰控制[J]. 农业机械学报,2017,48(5): 22-27.   
[14] Wang X,Wang F,Wei W. Linear active disturbance rejection control of dissolved oxygen concentration based on benchmark simulation model number 1[J]. Mathematical Problems in Engineering,2015,2015 (4-5):1- 9.   
[15]吴超，王浩文，张玉文，等．基于 LADRC的无人直升机轨迹跟踪[J]. 航空学报,2015,36(2):473-481.   
[16] 于海山．无人直升机六自由度运动模拟平台控制系统设计与应用[D]. 南京：南京航空航天大学,2012.   
[17] Ding L,Wu H, Yao Y. Chaotic artificial bee colony algorithm for system identification ofa smal-scale unmanned helicopter[J]. International Journal of Aerospace Engineering,2015,(2015-7-21),2015,2015 (1956): 1-11.   
[18]韩京清．自抗扰控制技术— 一估计补偿不确定因素的控制技术[M]. 北京：国防工业大学出版社,2009:77-110.