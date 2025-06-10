# 建筑室内边界对流换热量的反向计算模型

雷蕾1，薛雨²

(1.桂林电子科技大学 建筑与交通工程学院，广西 桂林 541004;2.大连理工大学 土木工程学院，辽宁 大连116024)

摘要：针对目前反向计算模型还无法实现对建筑室内边界对流换热量进行反向计算这一制约性差距，采用温度贡献率方法，将边界对流换热量与室内测点温度之间表示成因果关系的温度贡献因子矩阵，基于计算流体力学，将最小二乘与Tikhonov正则化方法相结合，建立依据室内数个测点的离散温度求解边界对流换热量的反问题数学模型。应用三维通风空腔和某建筑内一间办公室进行实验验证，模型求解值与实测值的均方根差均小于 $8 0 \%$ ，结果表明反向计算模型可以准确对室内边界对流换热量进行求解。

关键词：反问题；热边界条件；吉洪诺夫正则化；最小二乘；计算流体力学 中图分类号：TU18 doi:10.3969/j.issn.1001-3695.2018.04.0247

# Inverse method to determine wall boundary convective heat fluxes in indoor environments

Lei Leil†, Xue $\mathrm { Y u } ^ { 2 }$ （204号 (1.SchoolofArchitecture&TransportationEngineering,Guilin UniversityofElectronicTechnology,GuilinGuangxi541004, China; 2.School of Civil Engineering,Dalian Universityof Technology,Dalian Liaoning 116024,China)

Abstract:Thus far,noresearch has inverselysolvedforboundaryconvectiveheat fluxes in indoor environments.This study proposedan inverse method based on Tikhonov regularisation and least-squares optimisation using computational fluid dynamics (CFD)todetermine the wallboundaryconvectiveheatfuxes in indoor environments.The inversemodelapplied the CRI toestablishamatrix todescribethecause-efectrelationbetwee thecabin wallboundary heatfluxandtheexhibited discrete temperatureatcertain points.To testand evaluate the proposed inverse model,the surfaceheat fluxes on wals ina three dimensional ventilationcavityandanofficeinabuilding were inverselysolved.TheRMS errorsof the model were less than $80 \%$ .This study finds that thedeveloped inverse method canaccuratelyand efficiently determine the wallconvective heat fluxes in indoor environments.

Key words: inverse modeling; thermal boundary condition; Tikhonov regularization; least square; CFD

# 0 引言

在设计室内环境时，必须考虑热边界条件、送风位置、送风速度以及送风温度等环境参数。为获得舒适的热环境，热边界条件的合理设置是关键因素。确定热边界条件的常规方法须采用一种相当耗时的迭代式的猜测与校正过程。如果指定环境内的温度分布，那么就需要及时确定与之对应的热边界条件，这样将极大地加快热环境设计过程。这是一个基于特定目标温度反向确定热边界条件的计算问题，也就是基于有限的实测结果探索未知的边界条件，属于“由果及因”的反问题范畴。

许多研究人员在室内环境中进行了反向建模研究，但主要集中在污染源辨识[1-2问题上。文献[1]采用正定矩阵因子分解方法反向求解室内颗粒污染源的释放源强；文献[2]采用概率密度分布反向求解通风环境内的污染源位置；文献[3]研究在不用送风方式下室内污染源释放位置对污染物浓度分布的影响;文献[4]在不同送风方式的基础上，又增加不同送风速度这一条件，研究送风方式与送风速度不同组合情况下对室内甲醛浓度分布的影响；文献[5]应用Fluent数值模拟软件研究严寒地区室内自然通风和机械通风两者之间的通风效果，并分别研究不同送风速度与不同送风温度对室内不同高度位置处甲醛浓度的影响。

在现代工程背景下的传热反问题研究有了一定进展，文献[6]构建一种反演方法估算烤箱在加热过程中的边界温度曲线。文献[7]提出一种基于格林函数和动态观测的反向技术，在钻井过程中对工具界面的温度和热流量进行预测；除此之外，由于共轭梯度法的计算精度较高[8]，因此共轭梯度法是用来求解传热反问题的一种常用方法。文献[9,10]采用共轭梯度法反向求解混合送风方式下室内边界温度变化曲线特征；文献[11]研究固体热传导反问题，应用共轭梯度法反向求解固体边界导热热流值；文献[12]采用共轭梯度法反演高炉炉衬侵蚀过程中的传热曲线特征。除了应用广泛的共轭梯度法，文献[13]根据热防护绝热材料氧化铝纤维的温度测量值，采用遗传算法反向求解氧化铝纤维的有效热导率。

上述反问题模型均可利用计算流体力学（computationalfluiddynamics,CFD）求解，并且都可以满足计算精度需求。然而，这些方法通常代价高昂，需要设定恰当的迭代循环初始值，通常会导致计算量大且计算效率低。而且上述的反模型均基于单一的热边界条件进行反向求解，没有考虑当多个热边界条件同时存在时，各个热边界条件之间是如何影响温度分布的。到目前为止，还没有研究针对室内环境的热边界条件进行反向建模，更没有一种便捷高效的方法可以同时求解室内多个边界热流量。由于边界对流换热量对室内热湿环境有很大影响，因此，对于分析供热、通风和空调系统以及对空调环境的边界传热特性的研究具有重要意义。

反问题通常都属于病态问题，若输入数据中存在微小扰动，那么会对整个计算过程产生巨大影响。常采用Tikhonov正则化方法来处理不适定问题以提高反向控制方程的稳定性。迄今，由于室内复杂的气流模式而无法获得能量方程的分析解，因此室内热环境反模型计算结果的稳定性并没有完全得到解决。除了数学优化方法，日本学者Kato[14在1994 年首次提出温度贡献率（contributionratioof indoorclimate,CRI）方法，该方法用来分析室内单个热因子在多个热因子同时存在时如何影响其它热因子。例如，室内墙体与墙体之间的辐射换热，或墙体与室内空气之间的对流换热。然而CRI算法只考虑对流换热对室内空气温度分布的影响，并没有考虑墙体之间的辐射换热对室内空气的影响。因为辐射换热只在固体壁面之间进行热量传递，并不直接作用于空气温度，墙体壁面的对流换热才是影响室内空气温度的最重要因素，辐射换热仅是间接因素。目前CRI算法仅应用在正向求解室内温度分布的问题研究中，还没有将该算法应用到室内热环境的反向求解中。

综上所述，本文的研究目标是在室内环境中基于CFD和Tikhonov正则化原理，利用有限的温度测量信息反向求解室内边界对流换热量，并应用CRI算法加速反向计算过程，最终根据测点温度快速确定室内每个墙体壁面的对流换热量。

# 1 边界对流换热量的反向计算模型

# 1.1温度场的线性系统

建筑室内的热边界条件在能量方程中为热源项，由热力学第一定律推导得出的稳态能量方程如下[15]：

$$
\mathbf { u } \cdot \mathrm { g r a d } T = \mathrm { d i v } \big ( T \mathrm { g r a d } T \big ) + \frac { Q } { C _ { p } \rho }
$$

其中： $T$ 为空气温度 $( ^ { \circ } \mathrm { C } )$ ， $\mathbf { u }$ 为空气速度 $\mathrm { { ( m / s ) } }$ ， $\boldsymbol { { \cal T } }$ 为扩散系数 $\mathrm { ( m } ^ { 2 } / \mathrm { s } )$ ， $\boldsymbol { \mathcal { Q } }$ 为热源(W)， $C _ { P }$ 为定压比热 $( \mathrm { J / k g \cdot ^ { \circ } C } )$ ， $\rho$ 为空气密度 $( \mathrm { k g } / \mathrm { m } ^ { 3 } )$ ，div 为向量散度，grad为梯度运算。

若室内仅存在一个热源，那么由该热源形成的稳态能量方程如下：

$$
{ \bf u } \cdot \mathrm { g r a d } T _ { i } = \mathrm { d i v } \bigl ( T \mathrm { g r a d } T _ { i } \bigr ) + { \frac { Q _ { i } } { C _ { p } \rho } }
$$

若室内送风速度恒定不变，送风温度维持常值或在微小范围内变化，便可认为室内气流模式为稳态流场，这种情况下，仅对能量方程进行求解即可得到温度场。在机械通风条件下，强制对流起主导作用，若热边界条件改变时引起的热浮生力对流场造成的干扰很小，可假定温度场是一个线性系统[16]，室内$n$ 0 $( n > 1$ ）个热源共同作用下的温度场等于单个热源形成的子温度场的线性叠加，表达式如下：

$$
T \left( x , y , z \right) = T _ { 1 } \left( x , y , z \right) + T _ { 2 } \left( x , y , z \right) + \cdots + T _ { n } \left( x , y , z \right) = \sum _ { i = 1 } ^ { n } { T _ { i } \left( x , y , z \right) }
$$

其中， $T$ 为 $n$ 个热源下的总温度场， $T _ { i }$ 为第 $i$ 个热源 $Q _ { i }$ 单独存在时构成的子温度场。

由于室内湍流特性，温度场在严格意义上不完全是线性的，但与平均流场下的对流相比，时均速度场的非线性显得很微小，因此，假设室内温度场的线性性是合理的。借助能量方程(1)，式(3)转换成如下形式：

$$
\mathbf { u \cdot g r a d } T = \operatorname { d i v } \left( T \operatorname { g r a d } T \right) + \sum _ { i = 1 } ^ { n } { \frac { Q _ { i } } { C _ { p } \rho } }
$$

# 1.2 目标函数的建立

室内热边界条件的改变会影响温度场的改变，固体壁面之间仅存在辐射换热，作为透明介质的空气不吸收固体壁面释放的辐射射线，因此，空气与固体壁面之间的对流换热是室内空气温度改变的主要因素。根据流场稳态条件下的温度场满足线性性，室内测点温度变化量与边界对流换热变化量之间存在如下关系：

其中： ${ \bf T } { = } [ T _ { 1 } , \ T _ { 2 } , \ \cdots , \ T _ { n } ] ^ { \mathrm { T } }$ 为测点温度， $\mathbf { Q } { = } [ \boldsymbol { Q } _ { 1 } , \ \boldsymbol { Q } _ { 2 } , \ \cdots , \ \boldsymbol { Q } _ { n } ] ^ { \mathrm { T } }$ 为边界对流换热量。由于假定室内流场固定，温度变化量与边界对流换热变化量之间呈线性关系，因此A为描述边界对流换热量与测点温度之间因果关系的线性矩阵。

反模型的主要目的是根据室内测点温度求解热边界条件，由于矩阵A是一个病态矩阵，因此反向求解方程(5)是一个不具备数值稳定性的病态问题。鉴于此，若直接对方程(5)进行反向求解是无法实现的，为得到更贴近实际情况的计算值，需用一定的方法对方程(5)进行特殊处理，本文采用Tikhonov正则化方法在求解过程中增加正则化项来加强计算结果的稳定性。通过Tikhonov正则化方法将方程(5)转化为最小值目标函数问题，表达式如下[17];

$$
\mathrm { M i n } \ : Z ( \Delta \mathbf { Q } _ { n \times 1 } ) = \left\| \mathbf { A } _ { n \times n } \Delta \mathbf { Q } _ { n \times 1 } - \Delta \mathbf { T } _ { n \times 1 } \right\| _ { 2 } ^ { 2 } + \beta ^ { 2 } \left\| \mathbf { L } \Delta \mathbf { Q } _ { n \times 1 } \right\| _ { 2 } ^ { 2 }
$$

其中： $\left\| . \right\| _ { 2 }$ 为矩阵二范数， $\lambda$ 为正则化参数， $L$ 为正则化矩阵,最常用的表达式为

$$
\scriptstyle L = { \left[ \begin{array} { l l l l l l } { 1 } & { - 2 } & { 1 } & { 0 } & { 0 } & { \ldots } \\ { 0 } & { 1 } & { - 2 } & { 1 } & { 0 } & { \ldots } \\ { 0 } & { 0 } & { 1 } & { - 2 } & { 1 } & { \ldots } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \end{array} \right] } \in R ^ { ( n - 2 ) \times n }
$$

经过Tikhonov正则化处理后的反模型计算结果如下：

$$
\begin{array} { r } { \mathbf { Q } = ( \mathbf { A } ^ { \mathrm { T } } \mathbf { A } + \lambda ^ { 2 } \mathbf { L } ^ { \mathrm { T } } \mathbf { L } ) ^ { - 1 } \times ( \mathbf { A } ^ { \mathrm { T } } \Delta \mathbf { T } ) } \end{array}
$$

根据式(8)可知，若已知测点温度 ${ \bf T }$ 、线性矩阵A、正则化矩阵L和正则化参数λ，便可获得边界对流换热量 $\mathbf { Q }$ 。

如何选取合适的正则化参数λ是Tikhonov正则化方法求解的关键，定点方法（Fixed-point method，FP）是一种以较低计算代价便可得到参数 $\lambda$ 的简易算法[22-24]，FP算法的表达式如下：

$$
\phi _ { \eta } \left( \lambda \right) = \sqrt { \eta } \frac { { \left\| { \bf { A } } { \bf { Q } } _ { \lambda } - { \Delta } { \bf { T } } \right\| } _ { 2 } } { { \left\| { \bf { L } } { \bf { Q } } _ { \lambda } \right\| } _ { 2 } } \qquad \lambda > 0
$$

根据正则化修正之后的问题(6)，令

$$
x \big ( \lambda \big ) = \big \| \Delta T - A Q _ { \lambda } \big \| _ { 2 } ^ { 2 }
$$

$$
y ( \lambda ) { = } \left\| L Q _ { \lambda } \right\| _ { 2 } ^ { 2 }
$$

其中： $x ( \lambda )$ 是关于 $\lambda$ 的单调增函数， $y ( \lambda )$ 是关于 $\lambda$ 的单调减函数，根据这一性质，可以得到如下关于正则化参数λ的函数表达式：

$$
\Psi _ { \mu } ( \lambda ) = x ( \lambda ) y ^ { \mu } ( \lambda )
$$

其中： $\mu$ 是参变量，由于函数 $x ( \lambda )$ 和 $y ( \lambda )$ 的单调性，随着的不断迭代， $\Psi _ { \mu } ( \lambda )$ 存在极值点，并且令其取得极值的 $\lambda$ 就是优选的局部正则化参数。对 $\Psi _ { \mu } ( \lambda )$ 求一阶导数，令其等于零，得到关于正则化参数 $\lambda$ 的迭代公式 $\lambda _ { k + 1 } = \phi _ { \mu } \mathopen { } \mathclose \bgroup \left( \lambda _ { K } \aftergroup \egroup \right)$ ，其中：

$$
\phi _ { \mu } ( \lambda ) = \sqrt { \mu } \frac { \left. \Delta T - A Q _ { \lambda } \right. _ { 2 } } { \left. L Q _ { \lambda } \right. _ { 2 } }
$$

对于变量 $\mu$ ，大量的算例验证发现当 $\scriptstyle \mu = 1$ 时往往可以得到合理的正则化参数 $\lambda$ 。

$$
\phi _ { 1 } ( \lambda ) = \frac { { \left\| \Delta T - A Q _ { \lambda } \right\| } _ { 2 } } { { \left\| { L Q _ { \lambda } } \right\| } _ { 2 } }
$$

$\phi _ { 1 } ( \lambda )$ 是关于 $\lambda$ 的单调增函数，它具有在 $\lambda$ 的迭代区间上存在一个凸点和一个凹点的几何特征，凸点所对应的 $\lambda$ 就是局部最优正则化参数。

# 1.3温度贡献因子A的构建

采用CRI方法获取线性矩阵A的表达式。热边界 $i$ 对测点位置 $\mathbf { X }$ 处的CRI定义式[13]如下：

$$
C R I _ { i } \left( \mathbf { X } \right) = \frac { \Delta T _ { i } \left( \mathbf { X } \right) } { \Delta T _ { \mathrm { P } , i } } = \frac { \Delta T _ { i } \left( \mathbf { X } \right) } { \left[ \Delta Q _ { i } \middle / \left( \rho C _ { p } \dot { V } \right) \right] }
$$

其中： $\Delta T _ { i } ( { \mathbf { X } } )$ 是第 $i$ 个边界对流换热变化值 $\Delta Q _ { i }$ 在测点 $\mathbf { X }$ 处引起的温度变化值 ${ } ^ { ( \circ } \mathbf { C } )$ ， $\Delta T _ { \mathbb { P } , i }$ 是所有热边界同时存在时第 $i$ 个热边界 $Q _ { i }$ 引起的温度变化值 ${ } ^ { ( \circ } \mathrm { C } )$ ， $\rho$ 是空气密度 $\scriptstyle ( \mathrm { k g } / \mathrm { m } ^ { 3 } )$ ， $C _ { p }$ 是定压比热 $\mathrm { ( J / k g ^ { \circ } C ) }$ ， $\dot { V }$ 是空气通量 $( \mathrm { m } ^ { 3 } / \mathrm { s } )$ 。

将室内单个热边界独立存在时通过对流换热量引起测点温度的改变量记为 $\Delta T _ { \mathrm { S } j }$ ；所有热边界同时存在时对测点温度的贡献率记为矩阵C，单个热边界独立存在时对测点温度的贡献率记为矩阵 $\mathbf { X }$ ，根据温度场的线性叠加性，边界对流换热变化量与测点温度变化量之间的关系式如下：

$$
{ \left( \begin{array} { l } { \Delta T _ { S _ { 1 } } } \\ { \Delta T _ { S _ { 2 } } } \\ { \vdots } \\ { \Delta T _ { S _ { n } } } \end{array} \right) } = { \left( \begin{array} { l l l l l } { C _ { 1 1 } } & { C _ { 1 2 } } & { \cdots } & { C _ { 1 n } } \\ { C _ { 2 1 } } & { C _ { 2 2 } } & { \cdots } & { C _ { 2 n } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { C _ { n 1 } } & { C _ { n 2 } } & { \cdots } & { C _ { n n } } \end{array} \right) } { \left( \begin{array} { l l l l } { X _ { 1 1 } } & { 0 } & { \cdots } & { 0 } \\ { 0 } & { X _ { 2 2 } } & { \cdots } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { \cdots } & { X _ { n n } } \end{array} \right) } { \left( \begin{array} { l } { \Delta Q _ { 1 } } \\ { \Delta Q _ { 2 } } \\ { \vdots } \\ { \Delta Q _ { n } } \end{array} \right) }
$$

将表达式(15)代入到式(16)中，得到温度贡献因子矩阵A的表达式如下：

$$
\mathbf { A } = \mathbf { C X } = \left( \begin{array} { c c c c c c c } { \frac { \Delta T _ { 1 } C _ { _ { p } } \rho V } { \Delta Q _ { _ { 1 } } } } & { \frac { \Delta T _ { _ { 2 } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { 2 } } } } & { \ldots } & { \frac { \Delta T _ { _ { n } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { n } } } } \\ { \frac { \Delta T _ { _ { 1 } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { 1 } } } } & { \frac { \Delta T _ { _ { 2 } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { 2 } } } } & { \ldots } & { \frac { \Delta T _ { _ { n } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { n } } } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \frac { \Delta T _ { _ { 1 } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { 1 } } } } & { \frac { \Delta T _ { _ { 2 } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { 2 } } } } & { \ldots } & { \frac { \Delta T _ { _ { n } } C _ { _ { p } } \rho V } { \Delta Q _ { _ { n } } } } \end{array} \right) \left( \begin{array} { c c c c c c } { 1 } & { 0 } & { \ldots } & { 0 } \\ { C _ { _ { p } } \rho V } & { } & { } & { } & { } & { } \\ { 0 } & { \frac { 1 } { C _ { _ { p } } \rho V } } & { \ldots } & { 0 } \\ { \vdots } & { } & { } & { \vdots } \\ { 0 } & { 0 } & { \ldots } & { \frac { 1 } { C _ { _ { p } } \rho V } } \end{array} \right)
$$

# 2 三维通风空腔的实验验证

# 2.1 实验台描述

为评价反模型的有效性，搭建三维通风空腔实验台，几何尺寸为 $1 . 0 4 \mathrm { m } \times 1 . 0 4 \mathrm { m } \times 0 . 7 \mathrm { m } ( \mathrm { X } \times \mathrm { Y } \times \mathrm { Z } )$ ，如图1所示。空气由左上方宽度为 $0 . 0 1 8 \mathrm { ~ m ~ }$ 的条形风口送入，从空腔右下方宽度为 $0 . 0 2 4 \mathrm { ~ m ~ }$ 的排风口排出。根据图1(b)中的 $\mathrm { P _ { 1 } } \mathrm { - } \mathrm { P _ { 4 } }$ 共4个测点温度，应用反模型求解图1(a)中天花板、地板、左侧壁面及右侧壁面的对流换热量。

![](images/f928a30672d9f06bd3ef12cde4071323b01decdab85363346438bd69b44274f6.jpg)  
图1三维空腔通风实验台：(a）立体图;(b）中心截面图

# 2.2 实验验证结果

应用反模型计算的前提条件是稳态流场、测点温度、边界测量值、热物理特性和空间的几何尺寸。CFD是模拟室内速度分布、温度分布以及污染物扩散的有力工具。利用Fluent(6.3.26)数值模拟软件对三维通风空腔的速度场和温度场进行模拟。因为室内气流模式为湍流，所以选取RNG $k { - } \varepsilon$ 湍流模型；动量、湍流和能量方程的离散选取二阶迎风格式，采用Boussinesq模型近似热浮升力。由于辐射换热不直接作用于空气温度，因此在模拟过程中不考虑辐射换热模型。连续方程和动量方程的收敛控制在 $1 . 0 { \times } 1 0 ^ { - 3 }$ ，能量方程的收敛控制在 $1 . 0 { \times } 1 0 ^ { - 2 }$ 。在CRI方法计算中，存在4个热边界(天花板、地板、左侧壁面、右侧壁面)，获得室内稳态流场后，便可获取通风空腔4个固体壁面的CRI分布。根据4个壁面的CRI分布，借由计算式(17)构建温度贡献因子矩阵A。由CRI方法构建的矩阵描述了壁面对流换热量与测点温度之间的因果关系，由于该矩阵是流场和边界类型的函数，因此不受稳态流场和边界热流量的影响。

4个测点温度如图1(b)所示，在 $\mathrm { z } = 0 . 3 5 \mathrm { m }$ 截面中心线上的$\mathrm { P _ { 1 } } \mathrm { - } \mathrm { P _ { 4 } }$ 的温度值为已知信息，用来反向求解4个固体壁面的对流换热量。应用MATLAB自编译程序对反模型进行运算。

T为 $\mathbb { R } ^ { 4 \times 1 }$ 维向量，温度贡献因子矩阵 ${ \bf A } \in \mathrm { R } ^ { 4 \times 4 }$ ， $\mathbf { L }$ 采用二 阶正则化矩阵。前已述及，求解反模型的关键是要找到一个合 适的正则化参数λ。一旦确定 ${ \bf T }$ 、L和λ，那么根据式(8)便可 求解边界对流换热量 $\mathbf { Q }$ 。

Tikhonov正则化方法的目的是将修正后的目标函数最小化。应用FP方法获得 $\lambda { = } 1 8 0 7 . 1 7$ 为最优正则化参数，如图2所示。FP方法计算效率高，且计算能力强。将λ带入到式(8)中便可获得4个壁面的对流换热量，表1列出了4个固体壁面实际对流换热量与反模型计算结果以及两者之间的误差。从表1可知，实际值与反模型计算值较接近，两者之间的均方根差为$0 . 6 ^ { \circ } \mathrm { C }$ 。由此可见反模型可以确定边界对流换热量，且具有较好的实用价值。最终根据测点温度快速确定室内每个墙体壁面的对流换热量。

![](images/3a1b57d5135bb09042dc95ee2c0ba89dcb0bba4ab105dc9de411e0e1d2860dbd.jpg)  
图2三维通风空腔反模型中Fixed-point(FP)算法的曲率

表1三维通风空腔边界对流换热量的实际值与模型计算值  

<html><body><table><tr><td>热边界</td><td>实际值 (W)</td><td>模型计算值 (W)</td><td>误差 (W)</td></tr><tr><td>天花板</td><td>-8.06</td><td>-7.53</td><td>0.53</td></tr><tr><td>地板</td><td>90.19</td><td>90.75</td><td>0.56</td></tr><tr><td>左侧壁面</td><td>-35.67</td><td>-36.34</td><td>-0.67</td></tr><tr><td>右侧壁面</td><td>-10.73</td><td>-11.39</td><td>-0.66</td></tr></table></body></html>

注：边界对流换热量的正值表示热源(释放热量),负值表示热汇(吸收热量)

# 3 某建筑办公室的实验验证

# 3.1办公室环境描述

为验证反向计算模型在实际应用中的可行性，选取某栋建筑内的一间办公室进行实验测试。办公室的立体图如图2(a)所示，几何尺寸为 $4 . 9 2 ~ \mathrm { m } \times 4 . 3 2 ~ \mathrm { m } \times 2 . 4 2 ~ \mathrm { m } ~ ( \mathrm { X } \times \mathrm { Y } \times \mathrm { Z } ) ,$

办公室的一个角落里放置一个文件柜，另外两个角落里放置两张桌子和四台电脑，桌子前面坐着四个人，天花板上安装六盏日光灯，地板上安装四个尺寸为 $0 . 5 \mathrm { ~ m } { \times } 0 . 5 \mathrm { ~ m ~ }$ 的散流器，天花板上安装一个尺寸为 $0 . 3 \mathrm { ~ } \mathrm { m } { \times } 0 . 3 \mathrm { ~ m ~ }$ 的排风口。根据图 2(b)中给出的6个测点温度，应用反模型求解图2(a)中天花板、地板、东墙、西墙、南墙以及北墙的对流换热量。

![](images/31ab2b411f93ce726ed3e14fdddaa449fdfd977c0c5e39e1e79f254200542bd1.jpg)  
(a)办公室立体图

![](images/eae5600065168af71faa00f5c833a01c49cc7c92c439b7ed8977ca02147f2d75.jpg)

![](images/f873d453acf40b385559d5b7f714eb7f4c00bfb147e40d602030b31fbe13861d.jpg)  
图3某建筑办公室环境  
图4办公室反模型中Fixed-point (FP)算法的曲率

# 3.2 实验验证结果

采用与前面三维通风空腔测试实验相同的CFD模拟方法，6个测点构成的T为 $\mathbf { R } ^ { 6 \times 1 }$ 维向量，温度贡献因子矩阵 $\mathbf { A } \in \mathrm { R } ^ { 6 \times 6 }$ ，$\mathbf { L }$ 采用二阶正则化矩阵。应用FP方法获得 $\lambda = 2 6 . 3 3$ 为最优正则化参数，如图4所示。通过λ便可获得6个墙体壁面的对流换热量，表2列出了6个墙体壁面实际对流换热量与反模型计算结果以及两者之间的误差，实际值与反模型计算值之间的均方根差为 $0 . 7 9 ^ { \circ } \mathrm { C }$ 。说明反模型在实际应用中具有可行性。

表2办公室边界对流换热量的实际值与模型计算值  

<html><body><table><tr><td>热边界</td><td>实际值 (W)</td><td>模型计算值 (W)</td><td>误差 (W)</td></tr><tr><td>天花板</td><td>-60.42</td><td>-61.23</td><td>0.81</td></tr><tr><td>地板</td><td>196.81</td><td>197.52</td><td>-0.71</td></tr><tr><td>东墙</td><td>76.41</td><td>77.19</td><td>-0.78</td></tr><tr><td>西墙</td><td>83.23</td><td>84.07</td><td>-0.84</td></tr><tr><td>南墙</td><td>55.09</td><td>55.85</td><td>-0.76</td></tr><tr><td>北墙</td><td>66.79</td><td>67.65</td><td>-0.86</td></tr></table></body></html>

# 4 结束语

本文基于室内若干个测点温度提出一种确定边界对流换热量的反向计算模型。将Tikhonov正则化方法与最小二乘优化结合起来进行反向建模。正则化参数的选取对反模型求解至关重要。FP方法根据迭代函数 $\varPhi _ { \mathfrak { n } } ( \lambda )$ 的局部凸属性构建最佳正则化参数。FP方法以较低的计算成本得到可靠的计算结果，这是FP 算法的一个特点，这使得实现起来更加简单和高效。应用三维通风空腔实验台和某栋建筑内的一间办公室对反模型进行验证，实测值与模型计算值之间的均方根差均小于 $8 0 \%$ ，结果表明该反模型能够准确有效地对边界对流换热量进行反向确定。

# 参考文献：

[1]Suryawanshi S,Chauhan A S,Verma R，et al.Identification and quantification of indoor air pollutant sources within a residential academic campus [J]. Science of The Total Environment,2016,569:46-52.   
[2]Liu Ding,Zhao Fuyun,Yang Hen,et al.Probability adjoint identification of airborne pollutant sources depending on one sensor in a ventilated enclosure with conjugate heat and species transports [J]. International Journal of Heat and Mass Transfer,2016,102:919-933.   
[3]Yu Si,Yu Zhe,Ma Xiao,et al. Study on the influence of pollution source location on indoor pollutant distribution under different air supply [J]. Procedia Engineering,2017,205:2623-2630.   
[4] 岳高伟，陆梦华，贾慧娜.室内污染物扩散的通风优化数值模拟[J]. 流体机械,2014,42(4):81-85.(Yue Gaoweil,Lu Menghua,Jia Huina. Numerical Simulation of Indoor Pollutant Diffusion on Ventilation Optimization [J].Fluid Machinery,2014,42(4):1-85.)

[5]冯国会，姜编，黄凯良，等．严寒地区通风房间室内甲醛污染物浓度分

布规律研究[J].流体机械，2017,45(1):79-84.(Feng Guohui,Jiang Bian,Huang Kailiang,et al. Study on Concentration Distribution of Indoor Formaldehyde Polltants in Ventilation Room in Severe Cold Area[J]. Fluid Machinery,2017,45 (11): 79-84.)   
[6] Boulet M,Marcos B，Moresoli C,et al. Sequential inverse method implemented into CFD software for the estimation of a radiation boundary [J].International Journal of Thermal Sciences,2012,51: 7-15.   
[7]Sousa PFB,Borges VL,PereiraIC,et al. Estimation of heat flux and temperature field during drilling process using dynamic observers based on Green's function [J].Applied Thermal Engineering,2012,48:144-154.   
[8]李君，梁昔明．基于共轭梯度法改进的人工鱼群算法[J].计算机应用 研究，2017,34(12):3589-3593.(Li Jun,Liang Ximing.Hybrid AFSA with conjugate gradient methods [J]. Application Research of Computers, 2017,34 (12): 3589-3593. )   
[9]Zhao Fuyun,Liu Ding,Tang Ling,et al.Direct and inverse mixed convections in an enclosure with ventilation ports [J].International Journal of Heat and Mass Transfer,2009,52: 4400-4412.   
[10] Zhao Fuyun,Liu Ding,Tang Guifu.Numerical determination of boundary heat fluxes in an enclosure dynamically with natural convection through Fletcher-Reeves gradient method[J]. Computers and Fluids,2009，38: 797-809.   
[11] Zhao Fuyun,Liu Ding,Tang Guifu. Determining boundary heat flux profiles in an enclosure containing solid conducting block [J]. International Journal of Heat and Mass Transfer,2010,53:1269-1282.   
[12]苏福永，温治．基于传热反问题的高炉炉衬单层侵蚀模型[J].工程科 学学报,2017,39 (4): 574-580.(Su Fuyong,Wen Zhi.Blast furnace layer lining erosion problem based on inverse the heat conduction model [J]. Chinese Journal of Engineering,2017,39 (4): 574-580.)   
[13]褚福强，吴晓敏，朱毅，等．氧化铝纤维传热方式及反问题研究[J]. 工程热物理学报,2015,36(8):1756-1759.(Chu Fuqiang,Wu Xiaomin, Zhu Yi,et al. Heat transfer modes and inverse problem in alumina fibers [J].Journal of Engineering Thermophysics,2015,36(8): 1756-1759.)   
[14] Kato S,Murakami S,Kobayashi H. New scales for assessing contribution of heat sources and sinks to temperature distributions in room by means of numerical simulation [J].Proceedings of Roomvent,1994,539-557.   
[15] Sempey A,Inard C,Ghiaus C,et al.Fast simulation of temperature distribution inair-conditioned roomsbyusingproper orthogonal decomposition [J]. Building and Environment,209,44: 280-289.   
[16] Sasamoto T, Kato S,Zhang Wen.Control of indoor thermal environment based on concept of contribution ratio of indoor climate [J].Building Simulation,2010,3 (4): 263-278.   
[17] Tikhonov A,Arsenin V. Solutions of il-posed problems [M]. Washington, DC: Halsted Press.1977.