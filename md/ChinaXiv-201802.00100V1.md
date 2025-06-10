# 石墨烯中热脉冲传播的分子动力学研究

姚文俊，曹炳阳

（清华大学航天航空学院，热科学与动力工程教育部重点实验室，北京100084)(Tel：010-62781610，E-mail: caoby@tsinghua.edu.cn)

摘要：本文基于非平衡分子动力学方法，模拟研究了梯形、三角形和矩形热脉冲在石墨烯中的传播过程和规律。三种类型的温度脉冲采用直接速度修正法，通过调整对控温区原子施加的温度增量来实现。结果表明，热扰动在石墨烯中以有限的速度传播，并表现出明显的波动传递特征。热扰动在传播过程中激发出两道以不同速度传递的行波，一道波具有宏观动量，波速等于石墨烯声子群速度，为声波；另一道波是无宏观动量的热量的传播，波速是声速的 $1 / \sqrt { 3 }$ ，为热波。研究还发现，热脉冲形状对热波现象的产生以及声波、热波的传播速度没有影响，但对其峰值温度影响显著。

关键词：石墨烯；热脉冲传播；热波；分子动力学模拟中图分类号：TK121 文献标识码：A

# Molecular Dynamics Simulations of Heat Pulse Propagation in Graphene

YAO Wen-Jum' CAO Bing-Yangl (1.Key Laboratory for Thermal Science and Power Engineering of Ministry of Education, Department of Engineering Mechanics,Tsinghua University,Beijing 1ooo84, China)

Abstract: Based on nonequilibrium molecular dynamics,heat pulse propagation in graphene is studied by imposing trapezoid,triangle or rectangle shaped heat pulses.The three kinds of heat pulses are established byvelocity scaling methods. It is found that the heat pulse in graphene propagates with finite velocityand excites two waves. One of the two waves is a sound wave,which has macroscopic momentum and propagates at the speed of sound. The other is a thermal wave, whose propagation speed is $1 / \sqrt { 3 }$ of the sound velocity. The shape of the heat pulse has no influence on the thermal wave occurrence and velocities ofthe two waves, but it remarkably influences the peak temperature. Key words: Graphene; Heat pulse propagation; Thermal wave; Molecular dynamics simulations

# 0引言

石墨烯是由碳原子紧密排布成的六边形二维材料，自2004年首次成功制备以来，石墨烯凭借其优异的结构和物理性质迅速成为科学研究和工程应用的关注热点[1]。其中一个重要的研究方向就是利用其超高的导热和导电特性制备以石墨烯为基础材料的微/纳电子器件，解决芯片在高集成度下的散热问题，从而确保其运行的可靠性[2]。

对于一般情况下的导热问题，傅立叶导热定律有足够的描述精度。但对于微/纳米尺度下的超快速导热问题，其时间和空间尺度接近或小于材料的弛豫范围，导热过程偏离傅立叶导热定律，出现瞬态非傅立叶导热或热波现象[3,4]。Osman 等[5]模拟了碳纳米管在低温下的瞬态导热过程，发现热脉冲先后激发出三个波包，它们分别对应纵向模式、卷曲模式声学声子和第二声。Shiomi等在碳纳米管中模拟观察到了热波，并结合模态分析判定声学声子以弹道输运方式传递，光学声子对非傅立叶导热有主要贡献。

尽管碳纳米管与石墨烯同属低维碳素材料且具有很多相似之处，但两者在导热性能方面仍存在差异。目前关于石墨烯瞬态导热特性的研究还很少见到报道，因此本文以石墨烯为研究对象，采用非平衡分子动力学方法对石墨烯中热脉冲的传播过程进行了模拟，并在此基础上对比总结了不同类型热脉冲的传播特性和规律。

# 1 模拟方法

本文采用非平衡分子动力学方法模拟了石墨烯的瞬态导热过程，模拟系统如图1所示。系统长99.77$\mathrm { n m }$ 、宽 $2 . 1 6 \mathrm { n m }$ ，长、宽方向均采用周期性边界条件。碳碳原子间的作用力采用Brenner势能函数描述[7],即：

$$
E _ { \mathrm { b } } = \sum _ { i } \sum _ { j ( > i ) } f \left( r _ { i j } \right) \left[ V _ { \mathrm { R } } \left( r _ { i j } \right) - b _ { i j } V _ { \mathrm { A } } \left( r _ { i j } \right) \right] ,
$$

其中， $E _ { b }$ 是总势能， $f ( r _ { i j } )$ 是势能截断函数， $V _ { \mathrm { R } } , \ V _ { \mathrm { A } }$ 分别是原子间的排斥势和吸引势， $b _ { i j }$ 是多体作用系数，表示周围原子对 $i , j$ 原子作用势的影响，与原子间键角有关。系统原子相空间的演化采用Leapfrog-Verlet格式算法，积分步长取0.5fs。将模拟系统沿 $x$ 方向等分为200个区域，根据能量均分原理，各区域的瞬时温度可以通过统计平均原子动能获得：

$$
T \left( x , t \right) = \frac { 2 } { 3 N k _ { \mathrm { B } } } \sum _ { i = 1 } ^ { N } \frac { P _ { i } ^ { 2 } } { 2 m } ,
$$

其中， $T ( \boldsymbol { x } , t )$ 是温度， $m$ 是碳原子质量， $N$ 是各区域原子数， $k _ { \mathrm { B } }$ 是玻尔兹曼常数， $P _ { i }$ 是第 $i$ 个原子的动量。需要特别说明的是，当系统处于非平衡状态或存在宏观运动时， $T ( \boldsymbol { x } , t )$ 仅代表区域内原子的平均动能，但为方便讨论，本文仍将其表示为温度。

![](images/b50383ed34be346dd67ab97342c2d8e681140522b371b106ca43f053a47cf56c.jpg)  
图1模拟系统示意图

初始0.5ns采用Nose-Hoover热浴使系统达到平衡温度 $5 0 \mathrm { ~ K ~ }$ ，之后采用直接温度修正法在系统中间区域(图1阴影所示区域)施加持续时间1.0ps的温度脉冲。具体方法是采用速度修正因子 $\left( T _ { \mathfrak { p } } / T \right) ^ { 1 / 2 }$ 调整原子速度，使中间区域的瞬时温度达到指定脉冲温度。

图1中(a)、(b)、(c)所示的梯形、三角形和矩形脉冲的函数分别为：

$$
T _ { \mathrm { p } } = { \left\{ \begin{array} { l l } { 1 0 0 0 , } & { 0 \leq t \leq 0 . 5 } \\ { - 1 9 0 0 t + 1 9 5 0 , 0 . 5 \leq t \leq 1 . 0 } \end{array} \right. } ,
$$

$$
T _ { \mathrm { p } } = \left\{ \begin{array} { l l } { 1 9 0 0 t + 5 0 , } & { 0 \leq t \leq 0 . 5 } \\ { - 1 9 0 0 t + 1 9 5 0 , 0 . 5 \leq t \leq 1 . 0 } \end{array} \right. ,
$$

$$
T _ { \mathrm { p } } = 1 0 0 0 , 0 \leq t \leq 1 . 0 ,
$$

其中 $T _ { \mathrm { P } }$ 是脉冲温度，单位为K， $\mathbf { \Phi } _ { t }$ 是时间，单位是ps。三种脉冲最高温度均为 $1 0 0 0 \mathrm { ~ K ~ }$ ，持续时间均为1.0ps。以开始施加热脉冲的时刻为零时刻，加热停止后系统在绝热条件下演化，至4ps 时模拟结束，此时系统中心区域的热扰动已传播至长度方向的边界。另外，为消除噪音对模拟结果的影响，本文改变初始参数进行了20组模拟，由系综平均获得系统的温度及动量分布。由于模拟系统在长度方向是对称的，所以本文中只讨论 $0 { - } 5 0 ~ \mathrm { n m }$ 的区域。

# 2结果及讨论

图2以温度云图的形式给出了梯形热脉冲(式3a)在石墨烯中的传播过程。这里横、纵坐标分别表示空间位置和时间，颜色深浅示意温度的高低。云图中热脉冲施加在 $_ { x = 0 \sim 1 . 5 \ \mathrm { n m } }$ 和 $\scriptstyle { t = 0 \sim 1 . 0 }$ ps 的区域,在图中以矩形虚线框表示，下文中将该区域称为控温区。

![](images/edd807a5b7564e939bcfc3c37acbebec777fba54b3d4571df55d02a2415e9761.jpg)  
Fig.1 Schematic of the simulation system   
图2施加梯形热脉冲的系统温度云图  
Fig.2Temperature profile of the system imposed a trapezoid shaped heat pulse

从图2可以看出，如前所述，对平衡系统温度场的扰动是通过对控温区原子施加温度增量构造的。所施加的热脉冲随着时间的推演由控温区向系统两端传播，图中虚线表示扰动传播的波前位置，其在3.3ps左右到达系统边界，这充分说明在本文的模拟中，热扰动的传播速度是有限值。另外，在传播过程中，热脉冲共激发出两道以不同速度向边界传递的波，其中第一道波(实线1)速度较快，在3.5 ps左右到达系统边界，第二道波(实线2)速度较慢，在4ps 时仅传播至 $3 5 \mathrm { n m }$ 附近。上述扰动传播速度的有限性以及波动传递特征均是瞬态非傅立叶导热的体现。

傅立叶导热定律导出的温度演化方程会得出无限大的热扰动传播速率。为克服这个问题,Cattaneo[8]和 Vermotte[9等通过引入热流对时间的导数项提出了CV模型：

$$
\boldsymbol { q } + \tau \frac { \partial \boldsymbol { q } } { \partial t } = - \kappa { \nabla } T ~ ,
$$

其中 $\boldsymbol { q }$ 是热流密度， $\tau$ 是弛豫时间， $\kappa$ 是热导率。CV 模型使温度演化方程变为双曲型波动方程，从而可以得到有限的热扰动传播速度，即：

$$
\nu = \nu _ { g } \ / \ \sqrt { 3 } \ ,
$$

这里 $\mathbf { \Lambda } _ { \nu }$ 是热波速度， $\nu _ { \mathrm { g } }$ 是声速。

图3给出了波峰在不同时刻的位置，可以看出热脉冲激发的两道波在传播过程中波速不变，拟合直线可得 $\nu _ { 1 } { = } 1 3 . 4 ~ \mathrm { k m / s }$ 、 $\nu _ { 2 } { = } 9 . 3 3 ~ \mathrm { k m / s }$ 。由文献[10]可知模拟结果中第一道波的速度与石墨烯声子群速度基本相等，并且第二道波与第一道波的速度也基本符合 $1 / \sqrt { 3 }$ 倍的关系。

![](images/7321f37e11c05be3eec0b5a6ad62f2fe8a9f6b48e819706f0f92ee7a7ade5207.jpg)  
图3波峰位置随时间的变化  
Fig3.Location ofwave crestsvaryingwith time

图4(a)给出了 $t ^ { = 1 . 2 } \mathfrak { p s } . 2 . 0 \mathrm { p s }$ 和2.8ps 时石墨烯的温度分布以及2.8ps 时的动量分布。图4(b)给出了相同时刻由去掉局部宏观动量的原子速度计算的真实温度和动量分布。

从图4可以看出，热脉冲激发的两道行波在传播过程中能量逐渐衰减。同时受热扰动影响的区域均存在宏观动量，且 $0 { - } 3 0 ~ \mathrm { n m }$ 区域与 $3 0 { - } 4 5 ~ \mathrm { n m }$ 区域的局部动量方向相反，系统整体表现出纵向疏密波的特征。在去掉局部宏观动量后，第一道波完全消失，第二道波波峰温度有所衰减。以上结果均表明，施加在控温区的热脉冲在传播过程中激发的第一道波是系统受热膨胀所形成的声波，第二道波是由晶格振动形成的温度波，即热波。

![](images/5d9fe6ec2126fa92c23e83f7b822e2ba6c5527e020e8bbbc0e8b04c4fdd6af54.jpg)  
图4不同时刻温度和动量分布 (a)有宏观动量；(b)无宏观动量  
Fig 4.Temperature and momentum profiles at different time (a) with macroscopic momentum; (b) without macroscopic momentum

图5(a)、(b)分别为施加三角形(式3b)和矩形(式3c)热脉冲时的温度云图。比较图2和图5可以发现，三种超快速热脉冲在纳米尺度石墨烯中的传播过程均表现出明显的波动传递特征，并且脉冲形状的改变对其激发的行波波速和宽度没有影响，但对峰值

温度影响显著。在3ps时，梯形脉冲对应声波的峰值温度为 $4 6 5 \mathrm { K }$ ，三角形为257K，矩形为 $3 2 6 \mathrm { K }$ 。在三种脉冲中，矩形脉冲能量最高，梯形次之，三角形最小。可见脉冲激发的行波峰值能量的大小不能直接由热脉冲能量的多少决定，也与热脉冲在高温段的持续时间有关。高温段持续时间短且能量高的脉冲更容易激发出具有较高峰值能量的行波。

![](images/4ea571348d6379d479c92769fef591e4a685d682cd8dbeea20025f218c615457.jpg)  
图5施加(a)三角形、(b)矩形热脉冲的系统温度云图 Fig.5 Temperature profiles of the system imposed (a) a triangle and (b) a rectangle shaped heat pulse

# 3结论

本文采用非平衡分子动力学模拟方法，通过向石墨烯施加持续时间为1ps的梯形、三角形和矩形热脉冲，研究了热脉冲在石墨烯中的传播规律。热扰动的传播过程通过统计平均时空域上的原子动能温度描述。结果表明，石墨烯中热扰动以有限速度传播，并表现出明显的波动传递特征。热扰动激发出两道以不同速度传递的波，一道波具有宏观动量，其速度与声子群速度基本相等，是由系统受热膨胀所形成的纵向疏密波，为声波；另一道波无宏观动量，其速度与声速基本符合 $1 / \sqrt { 3 }$ 倍的关系，是由无规则晶格振动所形成的温度波，为热波。通过比较三种热脉冲的传播过程发现，热波现象的产生以及行波的波速均不受热脉冲形状的影响，但其峰值温度与脉冲形状有关。

# 参考文献

[1]Balandin AA,Ghosh S,Bao W, et al. Superior Thermal Conductivity of Single-Layer Graphene [J]. Nano Lett, 2008, 8(3): 902-907.   
[2]Geim A K, Kim P. Carbon Wonderland [J]. Sci Am, 2008, 298: 90-97.   
[3]Joseph D,Preziosi L.Heat waves [J].Rev Mod Phys,1989, 61: 41-73.   
[4] Cao B Y, Guo Z Y. Equation of Motion of a Phonon Gas and Non-Fourier Heat Conduction [J]. JAppl Phys,2007 102 (5): 53503-53506.   
[5]Osman MA, Srivastava D. Molecular Dynamics Simulation of Heat Pulse Propagation in Single-Wall Carbon Nanotubes [J].Phys Rev B,2005,72:125413-1-7.   
[6]Shiomi J, Maruyama S.Non-Fourier Heat Conduction in a Single-Walled Carbon Nanotube: Classical Molecular Dynamics Simulations [J]. Phys Rev B,2006,73: 205420-1-7.   
[7]Brenner D W. Empirical Potential for Hydrocarbons for Use in Simulation the Chemical Vapor Deposition of Diamond Films [J]. Phys Rev B,1990, 42(15): 9458-9471.   
[8] Cattaneo C. Sulla conduzione de calorie de calorie [J]. Attidel Semen MatEFis Univer Modena,1948,3:3-5.   
[9]Vernotte P. La veritable eqiation de la chaleur[J]. C R Acad Sci, 1958,247(23): 2103-2105.   
[10] Nika D L,Pokatilov EP, Askerov A S, et al. Phonon Thermal Conduction in Graphene: Role of Umklapp and Edge Roughness Scattering [J]. Phys Rev B,2009,79: 155413-1-12.