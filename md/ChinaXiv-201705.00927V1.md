# 复合发动机预冷器换热特性研究

李晨沛1 王跃社1 王海军1 魏宇青2(1．西安交通大学动力工程多相流国家重点实验室，西安710049;2．西安交通大学规划与基建管理中心，西安710049)

摘要复合发动机预冷器以其轻质紧凑的结构且高效的传热性能逐渐应用于超音速飞机发动机中，研究高流速高温差极端环境下微小尺度紧凑结构内换热机理对于提高发动机性能具有重大意义。本文针对 Sabre 复合发动机的预冷器，建立三维稳态可压缩流体横掠叉排管束的强制对流换热模型，研究管内流体速度，管外流体速度，入射角度以及管间距对于管外空气换热性能的影响机制。结果表明，通过增大管内制冷介质的流量，缩小管间距以及空气垂直入射等几种手段，均能达到提高预冷器换热效率的效果。

关键词预冷器；换热性能；数值模拟；微小通道中图分类号：TK172 文献标识码：A 文章编号:0253-231X(2017)04-0811-06

# Numerical Analysis of Heat Transfer/in Precooler for Hybrid Airbreathing Rocket Engines

LI Chen-Pei1 WANG Yue-She1WANG Hai-Jun1 WEI Yu-Qing² (1.StateKey Laboratoryof MultiphaseFlowinPoweEnginering,Xi'anJiaotong University，Xi'an710049,China; 2.Campus Planning and Basic Construetion Management Center, Xi'an Jiaotong University, xian 710049, China)

AbstractMicro-channel air predler is gradually used in supersonic aircraft engine,due to its advantages of light weight,compact structure and high-effciency in heat transfer. Thus, the numerical analysis of heat transfer in precooler for hybrid airbreathing rocket engines at high fow rates and large temperature difference has great value to increase engine effciency. In this paper,a three dimensional mathematical model is established to investigate the forced convection heat transfer characteristics in the staggered tube bundle,in which the fow is steady,compressible, forced convection. In particular, the efects of the flow rate,incident angle and the tube pitch are analyzed. It is found that the heat transfer is enhanced when the coolant flow rate increases Or the tube pitch decreases. As for the influence of incident angle,the results indicate that the vertical incidence is better than other incident degrees.

Key wordsprecooler; heat transfer; numericaP micro-channel

# 0引言

超音速飞机为降低飞机自重使用复合式预冷发动机，通过预冷大气中的空气作为氧化剂，同时实现吸气和火箭动力提供[1]。轻质大功率预冷器作为发动机热力循环中的关键组件，可在极短的时间内从来流空气中吸取足够的热量，达到深冷空气的目的。因此预冷器的功重比与紧凑度较高，常采用微小通道换热增强其换热性能。国内外针对复合式预冷发动机的研究主要包括英国的 Sabre [2-4]，日本的ATREX[5,6]和 S-engine三种发动机。三种换热器虽然结构不尽相同，但均采用管壳式，紧凑管束的换热方式，沿圆周方向布置管束，一方面使换热器结构更加紧凑，另一方面通过减薄管壁的方式增大换热面积，减轻换热器重量。

本文针对 Sabre发动机预冷器的结构进行模拟验证研究。由于预冷器结构的复杂性，对于该预冷器换热性能的研究较少。本文针对可压缩流体横掠叉排管束的强制对流换热，建立三维稳态模型，研究了管内的流体速度，管外流体的速度，入射角度，以及管间距对管外空气换热性能的影响，对预冷器的结构设计具有重大指导性意义。

# 1预冷器几何模型

# 1.1预冷器结构

预冷器的基本结构如图1所示，毛细管结构如图2所示。

![](images/9efa5b36cc969c7886286cc5c24ce86877a13fbc18f98e9208d3cb274eb58fe3.jpg)  
图1预冷器模块Fig.1 Precooler module

![](images/ef8cedcd832186bbce8f978d587d2b5f0e1889d152cf5b057441153f379519f8.jpg)  
图2预冷片示意图 Fig.2 The diagram of the precooling piece

预冷片呈弧形分布，弯曲向内，按一定角度圆周排列。预冷器的内外圈支管分布圆直径分别为340$\mathrm { m m }$ 、 $4 3 0 ~ \mathrm { m m }$ 。弯曲半径取 $1 9 0 ~ \mathrm { m m }$ ，沿径向按8层布置，25个预冷片围成一个基本结构。单个预冷片毛细管数量设定为80，毛细管外径 $1 . 2 \ \mathrm { m m }$ ，壁厚$0 . 1 5 ~ \mathrm { m m }$ 。

# 1.2模型描述与简化

由于管外为叉排管束，因此为了体现叉排结构特性，需建立三维流动模型，模拟管内外换热结构。

简化结构中，用两个半管和一个完整管子，体现叉排结构。对于两个半管的横截面，选用对称边界条件，使得半管的流动状态与完整管相似。此结构一方面尽可能简化了模型，降低网格数量，同时不影响计算结果。

此外，如图3所示，对管子进行编号， $1 { \sim } 2 5$ 依次沿顺时针分布。分析可知，25号管在A-A截面的流动状态，与1号管在B-B截面的流动状态相似。依次类推，24号管在A-A截面的流动状态，与25号管在B-B截面的流动状态相似。归纳可知，A-A截面和B-B截面之间的不同管可以等效看作1根完整的管，因此可截取1号管到2号管的部分作为模型计算基础单元，如图4所示。将图4所示单元的管束部分等效看作1号管的不同部分，即认为由外向内的管子为一根管。最外层管子的出口参数对应下一根管的进口参数，依次类推。直到最内层管子，恰好为十号管的出口。

![](images/1339f859fbd960fcc156d0ca48ca25df3dc6cfcf228ee0aa3ed225c610d0d70d.jpg)  
图3毛细管分布情况 Fig.3 The distribution of the micro-channel

![](images/b7f67fbc0236883205f25a0826fce85fa75e58f3953c04330d9c11908f276b04.jpg)  
图4局部放大图 Fig.4 Detail view

建立几何模型如图5所示，管内液氮由内圆流向外圆，管外空气沿半径方向入射再沿轴线方向被抽走。

![](images/8860c69d1899fe36cd67bdbde2ea76b4d8e50c7b91b48b1dc937eb3862b8c28a.jpg)  
图5简化模型结构Fig.5 The simplified model

# 2计算模型

# 2.1控制方程

管内外流体满足连续性方程及动量方程，如下：

$$
\frac { \partial \rho } { \partial t } + \frac { \partial ( \rho u ) } { \partial x } + \frac { \partial ( \rho \overline { { v } } \overline { { \mathbf { \nabla } } } } { \partial y } + \frac { \partial ( \rho w ) } { \partial z } = 0
$$

$$
{ \frac { \partial ( \rho u ) } { \partial t } } + \mathrm { { d i v } } ( \rho u U ) = \mathrm { { d i v } } ( \eta \cdot \mathrm { { g r a d } } u ) + S _ { \mathrm { { u } } } - { \frac { \partial p } { \partial x } }
$$

$$
{ \frac { \partial ( \rho v ) } { \partial t } } + \mathrm { { d i v } } ( \rho v U ) = { \mathrm { d i v } } ( \eta \cdot { \mathrm { g r a d } } v ) + S _ { \mathrm { v } } - { \frac { \partial p } { \partial y } }
$$

此外，本文考虑换热情况，引入能量方程如下：

$$
\frac { \partial ( \rho h ) } { \partial t } + \frac { \partial ( \rho u h ) } { \partial x } + \frac { \partial ( \rho v h ) } { \partial y } \frac { \partial ( \rho w h ) } { \partial z } =
$$

$$
- p \cdot \mathrm { d i v } U + \mathrm { d i v } ( \lambda \cdot \mathrm { g r a d } T ) + S _ { \mathrm { h } } + \varphi
$$

式中， $u , v$ 和 $w$ 分别为流体速度矢量 $U$ 在三个坐标方向上的分量， $p$ 为流体微元压力， $\rho$ 为流体密度, $\eta$ 为动力黏性系数， $S _ { \mathrm { u } }$ ， $S _ { \mathrm { v } }$ 和 $S _ { \mathrm { w } }$ 为广义源项, $\lambda$ 为流体导热系数， $\varPhi$ 为耗散能， $S _ { \mathrm { h } }$ 为流体内热源，本文中 $S _ { \mathrm { h } } { = } 0$ 。

# 2.2热平衡

同时考虑管内外流体流动对换热性能的影响， 保证管内外的热流量守恒有

$$
Q = A _ { \mathrm { i n } } h _ { \mathrm { i n } } ( T _ { \mathrm { f } } - T _ { \mathrm { w } } ) = A _ { \mathrm { o u t } } h _ { \mathrm { o u t } } ( T _ { \mathrm { f } } ^ { \prime } - T _ { \mathrm { w } } ^ { \prime } )
$$

其中 $\left| A _ { \mathrm { i n } } \right|$ 和 $A _ { \mathrm { o u t } }$ 分别为管内外的壁面面积， $h _ { \mathrm { i n } }$ 和$h _ { \mathrm { o u t } }$ 分别为内外流体的换热系数， $T _ { \mathrm { f } }$ ， $T _ { \mathrm { f } } ^ { \prime }$ 分别为内外流体接近壁面处的流体温度， $T _ { \mathrm { w } }$ ， $T _ { \mathrm { w } } ^ { \prime }$ 为内外壁面温度。

# 2.3沸腾换热计算公式

在考虑沸腾换热[8情况下，对流传热系数计算公式如下：

$$
\alpha _ { \mathrm { b } } = s \alpha _ { \mathrm { n b } } + \alpha _ { \mathrm { c b } }
$$

其中， $\alpha _ { \mathrm { b } }$ 为平均沸腾传热系数， $\alpha _ { \mathrm { n b } }$ 为泡核沸腾传热系数， $\alpha _ { \mathrm { c b } }$ 为膜核沸腾传热系数， $s$ 为泡核沸腾抑制因子。

$$
\alpha _ { \mathrm { n b } } = C q ^ { 0 . 6 7 } M _ { \mathrm { L } } ^ { - 0 . 5 } p _ { \mathrm { r } } ^ { m } ( - \lg p _ { \mathrm { r } } ) ^ { - 0 . 5 5 }
$$

其中,

$$
\begin{array} { r } { \mathbf { \widehat { Q } } _ { } C = 9 0 ~ \mathbf { W } ^ { 0 . 3 3 } / ( \mathbf { m } ^ { 0 . 6 6 } \cdot \mathbf { K } ) } \\ { m = 0 . 1 2 = 0 . 2 \lg \lvert R _ { \mathrm { p } } \rvert _ { \mathrm { \mu m } } } \end{array}
$$

为表面粗糙度， $R _ { \mathrm { p } } { = } 0 . 3 { \sim } 0 . 4 \ \mu \mathrm { m }$ ; $M _ { \mathrm { L } }$ 为液体的分子量， $\mathrm { \Delta g / m o l }$ ; $\textstyle p _ { \mathrm { r } }$ 为对比压力(液体压力与该流体的临界压力之比)； $q$ 为热流密度, $\mathrm { W / m ^ { 2 } }$ 。

$$
\alpha _ { \mathrm { c b } } = \alpha _ { t } \cdot F ( X _ { \mathrm { t t } } ) = 2 . 3 5 \alpha _ { \mathrm { t } } \left( \frac { 1 } { X _ { \mathrm { t t } } } + 0 . 2 1 3 \right) ^ { 0 . 7 3 6 }
$$

其中， $\alpha _ { \mathrm { { t } } }$ 为液体对流传热膜系数， $X _ { \mathrm { s t t } }$ 为Marttinelli数，可根据以下公式求取[9],

$$
\cdot \frac { \dot { \varsigma _ { h } } } { h _ { \mathrm { L O } } } = 3 . 5 \left( \frac { 1 } { X } \right) ^ { 0 . 5 }
$$

$$
h = h _ { \mathrm { L O } } \sqrt { \frac { \rho _ { \mathrm { L } } } { \rho _ { \mathrm { m } } } }
$$

其中， $\rho _ { \mathrm { L } }$ 为液相密度; $\rho _ { \mathrm { m } }$ 为汽液混合物的均相平均密度； $h _ { \mathrm { L O } }$ 为汽液两相全部为液相时的换热系数。

$$
s = \frac { 1 } { 1 + ( 2 . 5 3 \times 1 0 ^ { - 6 } ) R e _ { \mathrm { t p } } ^ { 1 . 1 7 } }
$$

其中,

$$
R e _ { \mathrm { t p } } = R e _ { \mathrm { L } } F ^ { 1 . 2 5 } = \left[ { \frac { G ( 1 - x ) D } { \mu _ { \mathrm { L } } } } \right] F ^ { 1 . 2 5 }
$$

式中， $G$ 为质量流量， $x$ 为干度， $\mu _ { \mathrm { L } }$ 为饱和液体黏度， $D$ 为管径。

# 3求解方法

流体计算分管内流动与管外流动两个部分。管外空气侧流体计算采用标准 $k { - } \varepsilon$ 湍流模型，侧边的边界采用绝热边界条件，进口采用速度边界条件，出口为压力边界条件，与壁面连接的边界保持热流量平衡。管内液氮侧流体计算时由于液氮流速不同，当管内 $R e$ 数小于2300时，不采用湍流模型，管内Re数大于2300时，采用标准 $k { - } \varepsilon$ 湍流模型，两侧的半管面均采用对称边界条件，保证整个管子结构的流动对称性，进口给定流量和温度，出口给定压力。同样与避免连接的边界保持热流量平衡。为保证管子进出口的连续性。使前一根管的出口参数与下一根管的进口参数保证连续。

压力速度耦合采用SIMPLE 算法，动量和能量均采用二阶迎风差分格式，压力、密度、体积力、动量、能量的松弛因子分别为0.3、1、1、0.7、1，连续性方程、 $X$ 方向分速度、 $Y$ 方向分速度的残差控制为 $1 0 ^ { - 4 }$ ，能量方程残差控制为 $1 0 ^ { - 7 }$ 。

# 4模拟结果及讨论

# 4.1液氮流量对于空气侧换热性能的影响

本文首先对沸腾式换热和单相换热的结果做出了比较。由于沸腾式换热的管内压力在临界压力下 (液氮临界压力为 $P _ { \mathrm { c r i t } } { = } 3 . 3 9 5 8 ~ \mathrm { M P a } )$ ，因此在考虑沸腾式换热时，设置管间距 $S _ { 1 } { = } 3 . 6$ mm管内入口压力为 $P { = } 3 ~ \mathrm { M P a }$ ，入口温度为 $\mathcal { k } \mathrm { \widehat { s } } _ { \mathrm { ~ \ast ~ } } ^ { \mathrm { ~ v ~ } }$ ，流速$u _ { \mathrm { N 2 } } { = } 0 . 2 4 ~ \mathrm { m / s }$ （层流)。空气入口度 $\tilde { T } _ { \mathrm { a i r , i n } } { = } 2 9 3 \ \mathrm { K }$ ，入口压力 $P _ { \mathrm { a i r } } { = } 0 . 1 0 1 3 ~ \mathrm { M P a } _ { \parallel } { } ^ { \prime }$ 流速 $\mathrm { \Delta \ u _ { a i r } = 1 0 \ m / s }$ 。根据沸腾式换热计算公式计算所得，空气出口温度为$T _ { \mathrm { a i r , o u t } } { = } 2 7 3 \ \mathrm { K }$ ，空气侧 $N u { = } 1 0 . 2 1 9$ 。

针对单相换热，本文模拟了液氮流速在0.24$\mathrm { m } / \mathrm { s }$ 、 $1 . 5 ~ \mathrm { m / s }$ 人 $\mathrm { 2 ~ m / s }$ 、 $4 ~ \mathrm { m / s }$ 情况下，液氮入口温度为 $7 6 ~ \mathrm { K }$ ，压力为 $\mathrm { 5 \ M P a }$ ，管间距 $S _ { 1 } { = } 3 . 6 ~ \mathrm { m m }$ ，空气流速为 $1 0 \mathrm { m / s }$ ，空气垂直入射(空气入射方向与管内制冷介质入射方向垂直)，入射温度为 $2 9 3 \ \mathrm { K }$ 勇口压力为1个大气压下，空气侧的换热情况，如下图6所示。

由图6可以看出，随着液氮流量的升高，空气侧的 $N u$ 数增高，换热性能增强，当液氮流速由0.24$\mathrm { m } / \mathrm { s }$ 增加到 $\mathrm { 1 ~ m / s }$ 时， $N u$ 数由11.09 增加到11.31,换热性能增强较大，这是因为在 $0 . 2 4 ~ \mathrm { m / s }$ 的情况下,管内液体流动状态为层流，换热性能较差，而随着液氮流速的增加，到 $1 \mathrm { m / s }$ 以后已转为湍流，换热性能增强。当流速增大到 $\mathrm { 1 . 5 ~ m / s }$ 后，换热性能的增加量减少，因此，建议管内液氮流速控制在 $1 . 5 ~ \mathrm { m / s }$ 。

沸腾换热与单相换热性能比较可知，沸腾换热的得到的出口温度为 $T _ { \mathrm { a i r , o u t } } { = } 2 7 3 \mathrm { K }$ ,单相换热在1.5$\mathrm { m } / \mathrm { s }$ 下得到的出口温度为 $T _ { \mathrm { a i r , o u t } } { = } 2 6 2 . 6 7 5 \ \mathrm { K }$ ，因此,沸腾换热的换热性能比超临界条件下的单相换热的换热性能差，此外，从安全性能的方面考虑，建议采用单相换热。

![](images/c3ae7c70e258df582ef8803105034d75860d79f84eef0b944c93aec48fdc0a29.jpg)  
液氮流量变化对空气侧换热的影响

# 4.2人射角度变化对于空气侧换热性能的影响

为验证空气侧入射角度对于空气侧换热的影响，分别模拟了入射角度为 $6 0 ^ { \circ }$ ， $6 5 ^ { \circ }$ ， $7 0 ^ { \circ }$ ， $7 5 ^ { \circ }$ ， $8 0 ^ { \circ }$ ， $8 5 ^ { \circ }$ ，$9 0 ^ { \circ }$ 情况下，液氮入口温度为 $7 6 ~ \mathrm { K }$ ，压力为 $\mathrm { 5 \ M P a }$ 5液氮入口速度为 $0 . 2 4 ~ \mathrm { m / s }$ ，管间距为 $3 . 6 ~ \mathrm { m m }$ ，空气流速为 $1 0 \mathrm { m / s }$ ，入射温度为 $2 9 3 \mathrm { K }$ ，出口压力为1个大气压下，空气侧的换热情况，如图7所示。

![](images/a8f62ce35ab31a71b91b9407351683137969d9c73d22d59b0bbefad5033c35c1.jpg)  
Fig.The variation of Nusselt number and temperature outside the tube with an increase in flow rate inside the tube   
图7空气入射角度变化对空气侧换热的影响 Fig.7 The variation of Nusselt number outside the tube with an increase in air incident angle

由图7可以看出，随着空气入射角度从 $6 0 ^ { \circ }$ 增加到 $9 0 ^ { \circ }$ ，空气侧的Nu数从9.6增加到11.08，换热性能增强，因此，垂直入射效果最佳。

# 4.3空气速度变化对于空气侧换热性能的影响

为验证空气入射速度对于空气侧换热的影响，分别模拟了空气入口速度为 $8 \mathrm { m / s }$ 1 $1 0 \mathrm { m / s }$ / $1 2 \mathrm { m / s }$ ，$2 0 ~ \mathrm { m / s }$ 情况下，液氮入口温度为 $7 6 \mathrm { ~ K ~ }$ ，压力为5$\mathrm { M P a }$ ，液氮入口流速为 $1 \mathrm { m / s }$ ，管间距分别 $3 . 6 ~ \mathrm { m m }$ 、$4 . 8 \mathrm { m m }$ 1 $6 ~ \mathrm { m m }$ ，空气入口为 $2 9 3 \mathrm { K }$ ，出口压力为1个大气压下，空气的换热情况，如图8所示。

![](images/ca857da965a71f6ae180ffdb5dad5d609953344be4b135e9bffa4695f4949607.jpg)  
图8不同管间距下，空气流速变化对空气侧 $\mathrm { \Delta N u }$ 数的影响 Fig. 8 The variation of Nusselt number outside the tubewith an increase in flow rate outside the tube at different tube pitch

由图8可以看出，随着空气流速从 $\mathrm { \Delta \hat { } \ m / s }$ 增加到 $2 0 ~ \mathrm { m / s }$ ，空气侧的Nu数逐渐增加，空气侧的换热效果增强，不同管间距条件下的Nu数增加量幅度几乎相同。但是由于空气流速的增加，会造成空气流量增加，进而使空气侧的出口温度上升，如图9所示。

![](images/873052d68c4d03643390a99a67f4a69f63ba706d9179745c2b5968a73e9f79b4.jpg)  
图9不同管间距下，空气流速变化对空气侧出口温度的影响 Fig.9 The variation of temperature outside the tube with an increase in flow rate outside the tube at different tube pitch

# 4.4管间距变化对于空气侧换热性能的影响

针对管间距变化对空气侧换热性能的影响，本文模拟了空气流量为 $1 0 ~ \mathrm { m / s }$ 时，换热管轴向间隙为$3 . 6 \ \mathrm { m m }$ 、 $4 ~ \mathrm { m m }$ 、 $4 . 8 ~ \mathrm { m m }$ 、 $6 ~ \mathrm { m m }$ 时，空气入口为常温，出口压力为1个大气压，液氮流速 $0 . 2 4 ~ \mathrm { m / s }$ ，入口压力 $\mathrm { 5 \ M P a }$ 、入口温度 $7 6 ~ \mathrm { K }$ 时空气的换热情况,如图10所示。

![](images/1eb8af9ae83dcdaac812e62af97351bb30b1d23468e1cf925bae72b75d24adbf.jpg)  
1 图10 管间距变化对空气侧换热的影响 Fig.10 The variation of Nusselt number and temperature outside the tube with an increase in tube pitch

由图10可以看出，随管间距的增加，空气侧的换热系数降低，换热性能减弱。由图8同样可以发现管间距增大换热性能减弱。此外，从图9可以看出随着管间距的增加，空气出口温度随着空气流速的增加的提高量逐渐降低。对于小管间距而言，空气流速的变化对空气出口温度的影响较大，说明紧凑型叉排管束的换热性能更好[7,10]，减小管间距有助于提高换热性能。

# 5结论

针对管壳式换热器的结构，我们针对不同的壳侧流体流速、管内流体流速、壳侧流体入射方向、管间距等对于空气换热的影响做出了模拟研究。研究得出以下结论：

1）沸腾式换热的换热性能比超临界条件下的单相换热的换热性能差，因此建议采用超临界条件下的单相换热更好。液氮流量的增加导致空气侧的换热效果增强，但是增强幅度会逐渐减小，因此选择$\mathrm { 1 . 5 ~ m / s }$ 的液氮流速不但可以增强空气侧的换热，同时经济性更好；

2)针对不同的空气入射角度而言垂直入射的换热效果较佳。主要原因是空气流速方向与换热管液氮流动方向的不同夹角可以分解为垂直入射方向的换热和顺流换热，由于顺流换热效果较差，因此， $7 0 ^ { \circ }$ 及 $6 0 ^ { \circ }$ 下的换热效果没有 $9 0 ^ { \circ }$ 的好;

3)空气流速的增加虽然会增强空气侧的换热效果，但是由于空气流量相应增加，并没有使空气的出口温度降低;4)对于不同换热管轴向间距的研究， $3 . 6 ~ \mathrm { m m }$ 间距下的换热效果较好，即紧凑式的换热结构更有利于换热效果的提升。

# 参考文献

[1]王娟，刘业奎，聂嵩等.国内外复合预冷发动机预冷器发展 思路及研制进展[C]/／第十一届全国低温工程大会论文集, 2013:472-479 WANG Juan,LIU Yekui,NIE Song,et al,The Development Ideas and Research Progress of Precooled Hybrid Airbreathing Rocket Engines at Home and Abroad [C]//Proceedings of the Eleventh National Conference on Cryogenic Engineering,2013:472-479   
[2]Murray JJ,Hempsell C M,Bond A.An Experimental Precooler for Airbreathing Rocket Engines [J].JournalBritish Interplanetary Society, 2001,54(5/6):199-209   
[3] Varvill R.Heat Exchanger Development at Reaction En gines Ltd [J].Acta Astronautica,2010,66(9):1468-1474   
[4] 牛文,李文杰.SKYLON飞行器与 SABRE 发动机研究 飞航导弹,2013(3):70-75 8 NIUWen,LI Wenjie,Researchon SKYLONAireraft and SABRE Engine [J].Winged Missiles Journal 2013(3): 70- 75   
[5]商旭升,蔡元虎，陈玉春．预冷却 ATREX 发动机主要部件 发展研究[J].弹箭与制导学报，2004(S6)：313-315 SHANG Xusheng,CAI Yuanhu,CHENG Yuchun,Development Study on Primary Components of the Pre-cooled ATREX Engine [J].Journal of Projectiles,Rockets,Missiles and Guidance,2004(S6): 313-315   
[6] Sato T，Tanatsugu N，Harada K，et al.Development Study on the Precooler of ATREX Engine [C]//Proceedings of the International Symposium on Space Technology and Science,20oo:42-47   
[7]李云鹤，杨雪峰．椭圆管束对流换热性能的数值模拟研究 [J].云南化工,2015 (4):1-5 LIYunhe,YANG Xuefeng.Numerical Simulation of Convective Heat TransferPerformance ofElliptical Tube Bundles[J].Yunnan Chemical Technology,2015 (4):1-5   
[8]钱颂文.换热器设计手册(精)[M].化学工业出版社，2006: 72-102 QIAN Songwen.Heat Exchanger Design Handbook [M]. Chemical Industry Press,2006:72-102   
[8] 林虎K液两相流和沸腾传热[M].西安交通大学出版社， 2003:316-317 LIN Zonghu. Two Phase Flow and Boiling Heat Transfer [M].Xi'an Jiao-tong University Press,2003:316-317   
10]焦凤，邓先和，孙大力等.管束排列及管间距对换热器传热性 能的影响[J].石油学报(石油加工)，2013,29(5)：836-843 JIAO Feng，DENG Xianhe,SUN Dali,et al.Effects of Tube Arrangements and Longitudinal Tube Spacing on Heat Transfer Performance of Heat Exchanger [J]. ActaPetrolei Sinica (Petroleum Processing Section),2013, 29(5):836-843

![](images/8b7c715861bbca137f71fca934cb7c88aba05d05d9a413a61ac1128d2f0cd2f3.jpg)