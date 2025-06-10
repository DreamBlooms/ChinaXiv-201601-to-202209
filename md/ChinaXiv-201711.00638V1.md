# 颗粒堆积多孔介质干燥多尺度多层结构传热传质模型及模拟

袁越锦1,2\*,谭礼斌¹,徐英英¹,赵哲1，白博峰²（1.陕西科技大学机电工程学院，西安710021，2.西安交通大学动力工程多相流国家重点实验室 西安710049）

摘 要：针对骨架颗粒的多层物理结构问题，运用孔道网络方法、热质传递原理和多尺度理论等知识，建立了颗粒堆积多孔介质干燥的多尺度多层结构传热传质模型。以稻谷堆为典型代表进行热风干燥试验验证，模拟分析了颗粒内部不同组织物理特性等因素对干燥过程的影响。结果表明：建立的模型可有效模拟稻谷堆干燥过程；稻谷颗粒内存在较大的水分梯度。胚扩散系数对干燥过程的影响十分显著，其次是壳扩散系数，衣扩散系数影响最小；较小的胚扩散系数可将湿分有效地“囚禁"在胚内。

关键词：颗粒堆积多孔介质；干燥；多层结构模型；多尺度；扩散系数

中图分类号：TH432文献标识码：A

# Multi-scale and Multi-layer Structural Modeling and Simulation of Heat and Mass Transfer Processes for Drying of Grain Packing Porous Media

Yuan Yue-jin1,2,TanLi-bin',Xu Ying-ying',Zhao Zhel,BaiBo-feng² (1,CollegeofMechanicalandElectrical Engineering,Shaanxi UniversityofScienceandTechnology,Xian0,China; 2. State Key Laboratory of Multiphase Flow in Power Enginering, Xi'an Jiaotong University,Xi'an 710049, China)

Abstract: Aiming at the problem of multi-layer physical structure for the skeleton of porous media,a multi-scale and multi-layer structural model of heat and mass transfer processs for drying of grain packing porous media was established by applying the pore network method and multi-scale theory. An experimental study on rice drying was conducted in order to validate this model.The simulationand experimental results indicated thatthe established model could explain the mechanical properties of rice drying wel. There was a higher moisture gradient inside the rice grain.The difusion coeficient ofrice embryo played an important role in the drying process,and whose effect on dryig was larger than the diffsion coefficient of rice hull and chaff.The moisture was imprisoned effectively inside the rice when the diffusion coefficient of rice embryo was very small.

Key words: porous media of grain packing; dying; multi-layer structural model; multi-scale; diffsion coefficient

# 0引言

颗粒堆积多孔介质干燥涉及农业、食品、轻工、化工、建筑、煤炭等众多领域。目前，对农产品颗粒堆积多孔介质干燥的机理及模拟研究，传统的方法主要是连续介质法，即将这类物料视为虚拟的连续湿固体，不考虑物料堆中颗粒骨架与孔隙的差别，也不考虑颗粒内部组织结构的不同，直接运用现有热质传递等理论进行建模求解[1-2]。而事实上，农产品颗粒堆积多孔介质结构复杂，在大部分情况下更接近于离散介质；且其骨架颗粒内部是一个多层物理结构，包括种皮（壳）、种衣和胚体等组织。显然，忽略这些因素对干燥过程的影响是不符合实际情况的。

多尺度理论是研究各种不同空间尺度或时间尺度相互耦合现象的科学。经过近三十年的发展，多尺度理论已是流体动力学、材料科学、环境科学、化学、气象学和高能物理等科学的核心理论之一[3]。孔道网络干燥理论是在上个世纪90 年代初，Daian和Saliba以及Nowicki等人率先将渗流理论中常用的孔道网络方法引入到多孔介质干燥理论中，后经Prat和Yortsos 等人的进一步研究完善而逐渐发展起来的[4-7]。这一理论认为多孔介质的湿分迁移在孔隙中具有很大优势，用一系列规则排列的节点及与其相互连接的孔道来重现多孔介质孔隙空间的几何及拓扑结构，直接在孔道等级上研究干燥过程中多孔介质的热质传递问题。

本文拟将多尺度理论的基本思想引入颗粒堆积多孔介质干燥研究领域，综合运用孔道网络方法、热质传递原理等交叉学科的知识，建立其干燥过程的多尺度多层结构传热传质模型。并以稻谷堆为颗粒堆积多孔介质的典型代表进行热风干燥试验验证，模拟分析颗粒内部不同组织物理特性等因素对干燥过程的影响。

# 1二维多尺度多层结构传热传质模型

# 1.1物理模型

农产品颗粒堆积多孔介质通风干燥过程主要是指热风在风压力的推动下，从物料的某个或多个方向进入其孔隙体系，与骨架颗粒进行热质交换后从另一个或多个方向排出的过程，如图1a所示。显然，在热风干燥过程中孔隙是热质传递的优势通道。为区分颗粒骨架与孔隙的差别，本文采用文献[中的方法构建孔道网络物理模型如图1b 所示。模型主要由"孔-喉-孔"网络和骨架两部分组成，孔为球体，喉为圆柱体，孔和喉径服从一定的概率分布。一个二维孔道网络物理模型可由分布律、两节点间距离、模型规模数、配位数等参数来描述[6]。其次，为考查骨架颗粒内部壳、衣、胚等组织结构不同对干燥过程的影响，本文将研究对象划分为颗粒尺度与干燥器尺度两个不同级别来处理。在颗粒尺度上，每一个骨架颗粒都具有种皮（壳）、种衣和胚体三层不同的物理组织结构，如图1c所示。

![](images/3996ae63128809648892a9ca475e24f768161cfbb555b164d92bfc8fbcc8dfcb.jpg)  
图1多尺度多层结构模型  
Fig.1Modelof multi-scale and multi-layer

# 1.2数学模型

为简化数学模型，针对上述颗粒堆积多孔介质热风干燥过程，我们作如下基本假设：（1）在颗粒尺度上假设骨架颗粒为具有多层物理结构的椭球体，不收缩、无变形；假设颗粒内部湿分传递主要依靠液态或汽态扩散；假设骨架颗粒内的水分相变所需耗热由骨架颗粒本身提供。（2）在干燥器尺度上以对流换热为主，忽略热传导、辐射传热；对流传质为主，忽略扩散传质，不考虑有液相参与的各种传质；假设气相为不可压缩的理想气体。

# 1.2.1颗粒尺度

对于孔道网络物理模型中在颗粒尺度上的每个骨架颗粒（图1c），可采用雷可夫理论[1描述其内部的热质传递过程，由上述基本假设，经简化推导可得在圆柱坐标系下的热质传递方程组为

$$
\left\{ \begin{array} { l l } { \displaystyle { \frac { \hat { \sigma } T _ { \mathbf { g } } } { \hat { \sigma } t } } = \displaystyle { \frac { \lambda _ { g } } { \rho _ { g } C _ { g } } } \left( \displaystyle { \frac { \hat { \sigma } ^ { 2 } T _ { g } } { { \hat { \sigma } r } ^ { 2 } } } + \displaystyle { \frac { 1 } { r } \frac { \hat { \sigma } T _ { g } } { \hat { \sigma } r } } + \displaystyle { \frac { \hat { \sigma } ^ { 2 } T _ { g } } { \hat { \sigma } Z ^ { 2 } } } \right) } \\ { \displaystyle { \frac { \hat { \sigma } M } { \hat { \sigma } t } } = \displaystyle { D } \left( \displaystyle { \frac { \hat { \sigma } ^ { 2 } M } { \hat { \sigma } r ^ { 2 } } } + \displaystyle { \frac { 1 } { r } \frac { \hat { \sigma } M } { \hat { \sigma } r } } + \displaystyle { \frac { \hat { \sigma } ^ { 2 } M } { \hat { \sigma } z ^ { 2 } } } \right) } \end{array} \right.
$$

式中： $T _ { g }$ 为颗粒内部某时刻某处的温度， $\mathrm { ~ K ~ }$ ； $\lambda _ { g }$ 为颗粒热导率， $\mathrm { W } / \mathrm { m } \cdot \mathrm { K }$ ; $\rho _ { g }$ 为颗粒密度， $\mathrm { k g / m } ^ { 3 }$ ; $C _ { g }$ 为颗粒比热容， $\mathbf { J } / \mathrm { k g } \cdot \mathrm { K }$ ； $M$ 为颗粒内部某时刻某处的湿含量（d.b.）； $D$ 为颗粒内水分扩散系数， $\mathrm { m } ^ { 2 } / \mathrm { s }$ ： $\mathrm { ~  ~ { ~ t ~ } ~ }$ 为时间变量， $s$ . $\boldsymbol { r } , \boldsymbol { Z }$ 为圆柱坐标变量， $\mathrm { m }$ 。

# 1.2.2干燥器尺度

如图1b，设在某一时刻 $\mathbf { n } \triangle \mathbf { \mathfrak { t } }$ ，孔道网络物理模  
型中某孔节点 $( i , j )$ 内的蒸汽密度为 ${ \rho _ { \nu } } ^ { n } { \mathrm { } } _ { i j }$ ，则应用质  
量、能量守恒定律与达西定律可得在干燥器尺度上的  
传质、传热及动量传递控制方程组为  
$\begin{array} { l } { { { \frac { 4 } { 3 } } \pi R _ { i } ^ { 3 } { \frac { \rho ^ { n } } { \rho _ { i } } } \frac { \partial ^ { n } } { \partial t } = \displaystyle \sum _ { k = i } ^ { N } ( \pi r _ { k } ^ { 2 } { \frac { \nu } { \nu _ { k } } } _ { \nu _ { k } } ) { \rho _ { i } } ^ { \nu _ { k } } _ { i } + } } \\ { { { \frac { 1 } { 4 } } \sum _ { k = i } ^ { i } { \frac { 1 } { 4 } } _ { 3 \rho _ { k } ^ { 3 } { k } _ { i } } ( \rho _ { i } ^ { \nu } , \infty ^ { \nu _ { k } - \rho _ { r } } , 0 ) } } \\ { { { \frac { 4 } { 3 } } \pi R _ { i } ^ { 3 } \rho _ { i } { \sigma _ { i } } \frac { \left( T _ { k } ^ { n } - T _ { i } ^ { n - 1 } \right) } { \Delta t } = \displaystyle \sum _ { k = i } ^ { N } ( \pi r _ { k } ^ { 2 } { \nu } _ { k } _ { i } ) { \rho _ { k } } ^ { \nu _ { i } } { C _ { i } } _ { T _ { k } ^ { n } } ^ { \nu _ { k } } + } } \\ { { { \frac { 1 } { 4 } } \sum _ { k = i } ^ { i } { \frac { 4 } { 4 } } _ { 3 \rho _ { k } ^ { 3 } { k } } \Lambda ( { T _ { p } } ^ { \kappa } , \infty ^ { \kappa } , 0 ) } } \\ { { \ \times { \frac { \displaystyle \sum _ { k = i } ^ { N } { Q _ { k } } - \sum _ { k = i } ^ { N } { \frac { \displaystyle \frac { \Lambda _ { k } ^ { 2 } } { \rho _ { i } } } } { \mu } } } { \rho _ { k } } ^ { \nu _ { i } } ( { T _ { p } } ^ { n } - { T _ { p } ^ { n } } ^ { n } ) = ( \sum _ { k = i } ^ { N } { S _ { k } } _ { k } ) { I _ { p } } _ { \mathrm { i n } } } } \end{array}$ (2）（204号

式中： ${ \rho _ { \nu } ^ { \ n } } _ { i j }$ 为某一时刻某孔节点 $( i , j )$ 内的蒸汽密度， $\mathrm { k g / m } ^ { 3 }$ ; $R _ { d }$ 为节点孔半径， $\mathrm { ~ m ~ }$ ； $\nu _ { h } = q _ { h } / ( { \pi r _ { h } } ^ { 2 } )$ ，为喉道中风速, $\mathrm { m / s }$ ，； $\boldsymbol { r _ { h } }$ 为喉半径， $\mathrm { ~ m ~ }$ ; $A _ { g }$ 为颗粒的表面积， ${ \mathfrak { m } } ^ { 2 }$ ; $k _ { c }$ 为对流传质系数， $\mathrm { m / s }$ ： $\rho _ { \nu e q }$ 为颗粒表面的蒸汽密度， $\mathrm { k g / m } ^ { 3 }$ ; $\triangle t$ 为时间步长，s； ${ T _ { i j } } ^ { n }$ 为某一时刻某孔节点 $( i , j )$ 内的气相温度，K； $\rho$ 为气相密度， $\mathrm { k g / m } ^ { 3 }$ ； $C$ 为气相比热容， $\mathrm { J / K g . K }$ ； $h$ 为对流换热系数， $\mathrm { W } / ( \mathrm { m } ^ { 2 } \cdot \mathrm { K } )$ ； $q _ { k }$ 为喉中的气相体积流率，$\mathrm { m } ^ { 3 } / \mathrm { s }$ ； $\boldsymbol { A } _ { h }$ 为喉截面积， ${ \mathrm { m } } ^ { 2 }$ ; $k ^ { * }$ 为达西渗透率， ${ \mathrm { m } } ^ { 2 }$ ; $\mu$ 为气相粘度，Pa.s； $l$ 为喉长度， $\mathrm { ~ m ~ }$ ； $P$ 为孔节点风压，Pa； $\rho _ { \nu w }$ 为纯蒸汽密度， $\mathrm { k g / m } ^ { 3 }$ ；S=Agkke(pveqk-pv"j)/4，为颗粒向某孔释放的蒸汽速率， $\mathrm { k g / s }$ 。

# 1.2.3跨尺度热质交换控制方程

上述两个尺度方程之间的热质传递信息彼此分离，没有联系，故需将两者的信息联系起来，补充一定的跨尺度热质交换平衡方程方可求解。

在孔道网络物理模型的每个骨架颗粒表面上，存在着跨尺度的热质交换，即该颗粒内水分的减少量等于气化流入颗粒周围孔隙的蒸汽量；同时，该颗粒内热焓变化量等于颗粒从周围气相中对流换热得到的热量减去气化颗粒内水分所耗的热量。于是应用质量、能量守恒定律可得跨尺度的热质交换平衡方程组为

$$
\left\{ \begin{array} { l } { \displaystyle \frac { 4 \pi R ^ { 3 } \rho _ { g } ^ { ' } \Delta X } { 3 \Delta t } = \sum _ { i = e } ^ { N } \frac { A _ { g } } { 4 } k _ { c i } ( \rho _ { \nu e q } ^ { ~ n } - \rho _ { \nu ~ i } ^ { ~ n } ) } \\ { \displaystyle \frac { 4 } { 3 } \pi R ^ { 3 } \rho _ { g } ^ { ' } C _ { g } ^ { n } \frac { T _ { g } ^ { n } - T _ { g } ^ { n - 1 } } { \Delta t } = } \\ { \displaystyle \sum _ { i = e } ^ { N } \frac { A _ { g } } { 4 } h _ { i } \big ( T _ { i } ^ { ~ n } - T _ { g } ^ { n } \big ) - \frac { 4 } { 3 } \pi R ^ { 3 } \rho _ { g } ^ { ' } \frac { \Delta X } { \Delta t } \eta _ { f g } } \end{array} \right.
$$

式中： $\rho _ { \mathrm { ~ g ~ } } ^ { \prime }$ 为颗粒绝干密度， $\mathrm { k g / m } ^ { 3 }$ ; $\eta _ { f g }$ 为水分气化潜热系数， $\mathbf { J } / \mathrm { k g }$ ； $\triangle X$ 为某颗粒在 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 时间内的含水率差， $\mathbf { k g } / \mathbf { k g }$ 。

# 2验证性干燥试验

以稻谷堆为颗粒堆积多孔介质的典型代表进行热风干燥试验验证。首先，将稻谷除杂洗净并调质获得均匀一致的湿含量；然后，将稻谷置于干燥试验仓中进行热风干燥，同时测得稻谷堆主要结构特征参数。干燥仓为宽 $2 0 0 \mathrm { m m }$ ，高 $2 0 0 \mathrm { m m }$ ，厚$1 0 0 \mathrm { m m }$ 的长方腔体，仓底部中心处开一直角等腰三角形进风口；顶部敞开，与外界环境空气接触;在仓壁正面开有测量孔。

干燥试验开始时，仓进风口热风温度$4 2 . 0 ^ { \circ } \mathrm { C }$ ，热风相对湿度 $6 . 5 \%$ ，热风静压 $5 6 . 0 \mathrm { { P a } }$ 环境温度 $2 0 . 1 ^ { \circ } \mathrm { C }$ ；稻谷颗粒初始温度 $1 8 . 0 ^ { \circ } \mathrm { C }$ ，稻谷颗粒初始湿含量 $3 1 . 2 \%$ (d.b.)。干燥试验过程中，每隔一段时间拔开测量孔橡胶塞，用红外测温仪测量各点稻谷颗粒的温度；并从测量孔中取出适量稻谷样品，采用烘干法测得各样品的湿含量。仓内稻谷堆中孔隙气相的温、湿度由埋入各测量点的温、湿度传感器测量。

# 3计算机模拟

基于上述干燥模型，本文采用 $\mathrm { V C + + }$ 与MATLAB语言联合编程开发模拟程序。干燥器尺度控制方程和跨尺度热质交换平衡方程已是离散型的差分方程，直接采用有限差分的分离式解法求解；而颗粒尺度方程为偏微分形式，需先进行网格划分然后对其有限差分离散方可求解。稻谷颗粒为理想的椭球体，具有对称性，为提高计算速度，只需取其对称面的四分之一进行分析。模拟计算过程中，干燥模型的初始、边界条件与验证性试验情况一致。

# 4结果分析与讨论

# 4.1干燥仓内稻谷平均湿含量变化曲线

从图2可以看出，仓内稻谷颗粒的平均湿含量模拟与实验变化曲线基本吻合，其最大相对误差约为$7 . 6 \%$ 。这从宏观上表明，本文建立的模型有效。

![](images/afce842e1c9f7242f8f5f8757480065d6768efe71af47ff0ec79e18fcbf07205.jpg)  
图2仓内稻谷颗粒的平均湿含量曲线模拟与实验结果的比较 Fig.2Drying curves comparison of simulation and experiment

# 4.2颗粒内部不同组织物理特性对干燥过程影响4.2.1壳扩散系数

将壳扩散系数设定为5种不同的值，其余参数不变，进行颗粒堆积多孔介质干燥模拟，得到不同壳扩散系数下的颗粒干燥曲线如图3所示。从图中可以看出，颗粒壳扩散系数对干燥过程有一定影响。随着壳扩散系数的减小，干燥速度逐渐变慢，达到相同湿含量所需干燥时间越长。这主要是因为壳扩散系数越小，颗粒内湿分逸出壳表面越困难，干燥也就越慢。

![](images/f67ce39acf1879cee998b57d280a7b834dddc7016f9fa0555e314dee5b0698c4.jpg)  
图3不同壳扩散系数的颗粒干燥曲线

Fig.3Drying curves of simulation for different hull diffusion coefficient

# 4.2.2衣扩散系数

将衣扩散系数设定为5种不同的值，其余参数不变，进行颗粒堆积多孔介质干燥模拟，得到不同衣扩散系数下的颗粒干燥曲线如图4所示。从图中可以看出，颗粒衣扩散系数对干燥过程的影响很小。随着衣扩散系数的减小，干燥速度虽有所变慢，但变慢的幅度很小，可以忽略不计。这主要是因为颗粒种衣的组织物理厚度相对壳、胚来说薄得多，其扩散系数的变化对颗粒内部湿分迁移所起的作用有限。

![](images/bd334605f5e2bb1a536ec7d41f76c77b043501b31e73eed3caeb64802ed71a73.jpg)  
图4不同衣扩散系数的颗粒干燥曲线

Fig.4 Drying curves of simulation for different chaff diffusior coefficient

# 4.2.3胚扩散系数

将胚扩散系数设定为5种不同的值，其余参数不变，进行颗粒堆积多孔介质干燥模拟，得到不同胚扩散系数下的颗粒干燥曲线如图5所示，湿含量分布（ $\tan \angle 1 = 3 0 0 \mathrm { m i n }$ 时）如图6所示。

![](images/6e5ecd8b5d5c24f5aac59711b4563924b99f30dc3943e90b6f54881e263ed16a.jpg)  
图5不同胚扩散系数下的颗粒干燥曲线

![](images/3daca684175b3d2c159d4042bb4b626a8efcffed4b2eee4020daaa3d85fa428b.jpg)  
Fig.5Drying curvesof simulation fordifferent embryo diffusion   
图6不同胚扩散系数下的湿含量模拟结果  
Fig.6 Moisture distributions of simulation for different embryo

diffusion coefficient

由图5可以看出，颗粒胚扩散系数对干燥过程的影响巨大。随着胚扩散系数的减小，干燥速度明显变慢，特别是干燥的中后期，达到相同湿含量所需干燥时间显著增加。这一方面是因为种胚在颗粒组织中占有较大比例；另一方面，从图6也可以看出，胚扩散系数越小，颗粒内湿分从胚内迁移到壳表面越困难，湿分仿佛被"囚禁"在胚内，如当胚扩散系数为 $2 . 9 8 \times 1 0 ^ { - 1 1 } ~ \mathrm { m } ^ { 2 } / \mathrm { s }$ 时，其颗粒中心区域的湿含量几乎没有减小。因此，干燥也就越慢。

# 5结论

本文建立的多尺度多层结构传热传质模型可有效模拟颗粒堆积多孔介质干燥过程。模拟得到的仓内稻谷干燥曲线反映了其干燥过程的实际情况。颗粒内部不同组织物理特性对颗粒堆积多孔介质干燥有较大的影响，胚扩散系数的影响十分显著，其次是壳扩散系数，衣扩散系数影响最小。在干燥过程中，随着胚扩散系数的减小，干燥速度明显变慢，特别是干燥的中后期，达到相同湿含量所需干燥时间显著增加；较小的胚扩散系数可将湿分“囚禁"在胚内，使湿分较难从颗粒内迁移到壳表面。

# 参考文献

[1] 刘相东，杨彬彬.多孔介质干燥理论的回顾与展望.中国 农业大学学报,2005,10(4):81-92 LIU Xiangdong, YANG Binbin. Review and Vista on Drying Theories of Porous Medium. Journal of China Agricultural University, 2005,10(4): 81-92   
[2] Naghavi Z,Moheb A,Ziaei-rad S.Numerical Simulation of Rough Rice Drying in a Deep-Bed Dryer Using Nonequilibrium Model. Energy Conversion and Management, 2010,51(2): 258-264   
[3] 吴江航,黄社华,James Glimm,等.多尺度科学:面向 21 世纪的挑战.力学进展,1998,28(4):545-551 WU Jianghang,HUANG Shehua, James Glimm，et al. Multiscale Science: A Challenge for the Twenty-First Century.Advances in Mechanics,1998,28(4)545-551   
[4] PratM.Recent advances in Pore-scale Models for Drying of Porous Media. Chemical Engineering Journal, 20o2,86(1- 2): 153-164   
[5] Yiotis A G, Tsimpanogiannis I.N, Stubos A K,et al.Porenetwork Study of Characteristic Periods in the Drying of Porous Media. Journal of Colloid and Interface Science, 2006,297(2): 738-748   
[6] XIAO Zhifeng，YANG Deyong,YUAN Yuejin,et al. Fractal Pore Network Simulation on the Drying of Porous Media. Drying Technology,2008,26(6): 651-665   
[7] Shaeri M R,Beyhaghi S,Pillai K M. On Applying an External-Flow Driven Mass Transfer Boundary Condition toSimulate Drying from a Pore-network Model. International Journal of Heat and Mass Transfer,2013, 57(1): 331-344