# 不同月球借力约束下的地月Halo轨道转移轨道设计

张景瑞，曾豪’，李明涛²(1．北京理工大学宇航学院，北京100081；2．中国科学院空间科学与应用研究中心，北京100190)

摘要：针对地月系L2点不同任务需求下的低耗能转移轨道设计问题基于不变流形理论与混合优化技术，深入研究了不同月球借力约束与不同幅值 Halo轨道的入轨点(简称HOI点)对转移轨道飞行时间与燃料消耗的影响给出了HOI点选择策略。首先结合任务要求并考虑月球引力影响在月球借力点施加不同约束条件,通过微分修正算法调整Halo轨道的稳定流形,设计月球到Halo轨道的转移轨道。采用遗传算法与微分修正算法相结合的混合优化策略,在同时考虑地球停泊轨道高度、倾角、升交点赤经与航迹角等多约束条件下,对燃料最优的地月转移轨道进行研究。最后分析月球借力高度、借力方位角和不同HOI点对平动点转移轨道飞行时间与燃耗变化量的影响,对于考虑月球借力的地月平动点转移轨道设计与应用具有重要的参考价值。

关键词：Halo轨道；不变流形；借力飞行；混合优化   
中图分类号： $\mathrm { V } 4 1 2 . 4 + 1$ 文献标识码：A 文章编号：1000-328(2016)02-0159-10   
DOI: 10.3873/j.issn.1000-1328.2016.02.004

# A Design Method for Earth-Moon Halo Orbit Transfer Trajectory Under Different Constraints to Moon Gravity-Assisted Maneuvers

ZHANG Jing-rui1,ZENG Hao' ,LI Ming-tao² (1.School of Aerospace Engineering,Beijing Institute of Technology,Beijing 1Ooo81,China; 2.Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 10o19O,China)

Abstract:Todesignlow-energy Earth-MoonL2Haloorbit transfer trajectory fordiferent missonrequirements,dep researchon the influence of diferentconstraints tothemoongravity-asisted maneuversand Haloorbit insertion(HOl) points with diffrentamplitudesontimeoflightandfuelconsumption ismade,andaselection strategyforHOIpointsis proposed in thispaper.Firstly,combined with missionrequirementsandefctsof the moongravity,diferentconstraints areappliedtothemoongravity-assistedmaneuvers.StablemanifoldofHaloorbitisadjustedthroughdiferentialcoection algorithmandthetransfertrajectoryfrommoontoHaloorbitisdesigned.Then,inconsiderationoforbitatitudeorbit inclination,rightascensionofascending nodeandtrackangleat thesametime,thehybridoptimizationstrategycombined geneticalgorithmwithdiferentialcorrctionalgorithmisadoptedtostudyEarth-MoonHaloorbittransfertrajectorieswith optimal fuelconsumption.Atlast,theinfluenceof moongravity-assistedaltitudeandazimuthaswellasdiferentHOI pointsonflight timeandfuelconsumptionof transfertrajectories isrespectivelyanalyzed,which hasreferencevalue for design and application of Earth-Moon Halo orbit transfer trajectories.

Key Words:Halo orbit; Invariant manifold；Moon gravity-asisted maneuver；Hybrid optimization

# 0引言

（简称EML2点)附近Halo轨道的应用价值逐日突显。航行于EML2点Halo轨道上的探测器能够观测月球背面，从而为月球背面的着陆任务提供导航方案。同时围绕EML2点能够设计出到达月球、火星

随着平动点轨道任务的相继提出以及月球背面在未来深空探测中存在的重要作用。地月系统L2点和其它行星的低耗能转移轨道，可作为探测深空环境的最佳落脚点[1-2]。因此 在平动点轨道任务中探测器采取何种飞行方式消耗多少燃料才能设计出合适的转移轨道一直是空间领域研究的热点问题。

针对平动点转移轨道设计问题，由于EML2点附近Halo轨道的稳定流形无法与地球停泊轨道相交基于不变流形设计零消耗转移轨道的方案并不存在。Zazzera等[3]采用遗传算法与序列二次规划的混合优化方法，设计了多条不考虑月球借力的EML2点间接转移轨道。Parker[4]基于弱稳定边界转移策略，通过连接日地系统与地月系统的不变流形研究了低地球轨道飞抵EML2点Halo轨道的转移轨道特性，但弱稳定转移存在着飞行时间长等问题。Gordon[5]则利用稳定流形理论与月球借力技术构造了不同幅值Halo轨道的两脉冲转移轨道，虽然降低了机动速度增量但两脉冲条件下借力点方位不可调整存在着局限性。同时，飞行耗时较长且大幅值条件下燃料消耗过多。文献[6-8]在Gordon[5]的研究基础上，给出了不变流形与月球借力飞行技术相结合的三脉冲转移轨道方案。但针对不同幅值Halo轨道，并未分析不同月球借力约束对Halo轨道的入轨点(HOI)选择策略的影响，以及借力机动点三轴速度增量大小等特征限制了在工程中的应用价值。

表1与图1描述了在以往研究中针对EML2点Halo轨道的转移轨道不同设计方法及参数之间的比较。其中CR3BP为圆型限制性三体模型，BCRFBP为双圆限制性四体模型JPL为星历模型IT为间接转移，WSB为弱稳定转移LFB为月球借力转移。

表1EML2点Halo轨道不同转移方式比较  
Table 1 Comparison of several types of transfers to the EML2 Halo orbits   

<html><body><table><tr><td>参考 文献</td><td>Halo轨道 幅值/km</td><td>停泊轨 道高度/km</td><td>动力学 模型</td><td>轨道转 移方式</td></tr><tr><td>[3]</td><td>8000</td><td>200</td><td>CR3BP</td><td>IT</td></tr><tr><td>[4]</td><td>53000</td><td>185</td><td>JPL</td><td>WSB</td></tr><tr><td>[4]</td><td>53000</td><td>185</td><td>CR3BP</td><td>WSB</td></tr><tr><td>[5]</td><td>6000</td><td>200</td><td>CR3BP</td><td>LFB</td></tr><tr><td>[6]</td><td>5000</td><td>200</td><td>JPL</td><td>LFB</td></tr><tr><td>[7]</td><td>5000</td><td>400</td><td>CR3BP</td><td>LFB</td></tr><tr><td>[8]</td><td>5000</td><td>200</td><td>CR3BP</td><td>LFB</td></tr><tr><td>[9]</td><td>8000</td><td>167</td><td>BCRFBP</td><td>WSB</td></tr></table></body></html>

本文针对以上问题，结合平动点不变流形的特性利用遗传算法与微分修正算法结合的混合优化技术，设计了同时考虑地球停泊轨道高度、倾角、航迹角等约束的燃料最优地月段转移轨道。同时，在不同应用背景下，通过微分修正算法调整稳定流形，得到了满足月球借力约束的月球至Halo轨道的转移轨道。重点分析了在不同月球借力约束下，不同幅值Halo轨道的不同入轨点与飞行时间、机动速度增量之间的关系，总结相应的变化规律，最终确定HOI点的选择策略对以EML2点Halo轨道为目标轨道的深空探测器转移轨道设计具有借鉴意义。

![](images/3acd9ce96079d0efd453344ef6b11a07f65edb6c522805752d4e1c340fa5cadf.jpg)  
图1总速度增量(直方图)与飞行时间(曲线)Fig.1Total velocity increment(bar）and time of flight(curve)

# 1转移轨道模型及设计方案分析

# 1.1 圆型限制性三体模型

针对地球停泊轨道与EML2点Halo轨道之间的转移轨道本文基于圆型限制性三体模型进行分析则在会合坐标系下探测器的动力学模型可表示为[10]：

$$
\ddot { \boldsymbol { r } } = \left( \frac { \partial \boldsymbol { U } ( \boldsymbol { r } ) } { \partial \boldsymbol { r } } \right) ^ { \mathrm { T } } + \boldsymbol { h } ( \boldsymbol { \nu } )
$$

式中:

$$
\frac { \partial U ( r ) } { \partial r } = \left[ \begin{array} { c } { x - \frac { \big ( 1 - \mu \big ) \big ( x + \mu \big ) } { r _ { 1 } ^ { 3 } } - \frac { \mu \big ( x - 1 + \mu \big ) } { r _ { 2 } ^ { 3 } } } \\ { y - \frac { \big ( 1 - \mu \big ) \mathcal { I } } { r _ { 1 } ^ { 3 } } - \frac { \mu \mathcal { I } } { r _ { 2 } ^ { 3 } } } \\ { - \frac { \big ( 1 - \mu \big ) z } { r _ { 1 } ^ { 3 } } - \frac { \mu z } { r _ { 2 } ^ { 3 } } } \end{array} \right] ^ { 2 }
$$

${ \pmb h } ( \ \nu ) = [ 2 \dot { y } \ , - 2 \dot { x } \ \beta ] ^ { \mathrm { T } } , r _ { 1 } \ r _ { 2 }$ 分别为探测器与地球和月球间的距离,地－月系中 $, \mu \approx 1 . 2 1 5 \times 1 0 ^ { - 2 }$ 1$[ x \ y \ z \ x \ y ]$ 表征探测器在会合坐标系中的状态量。

# 1.2Halo轨道及状态转移矩阵

EML2点是位于月球背面的共线平动点，其附近存在的周期Halo轨道能够为执行特殊空间任务的探测器提供理想航行位置。本文针对不同幅值Halo 轨道进行研究[10]即对法向幅值由 $2 0 0 0 ~ \mathrm { k m } \sim$ $1 0 0 0 0 ~ \mathrm { k m }$ 的9组参数进行分析。

状态转移矩阵 ${ \pmb { \phi } } ( \{ \textit { t } \} _ { 0 } )$ 用于描述下一时刻目标点的状态改变量与当前时刻的状态变化量之间的关系。在圆型限制性三体问题模型中，状态转移矩阵满足以下微分方程。

$$
\begin{array} { r l } { \dot { \pmb { \phi } } ( \textit { t } \iota _ { 0 } ) } & { = A ( \textit { t } ) \ \pmb { \phi } ( \textit { t } \iota _ { 0 } ) } \end{array}
$$

式中：状态转移矩阵的初值为 $6 \times 6$ 的单位矩阵即 $\pmb { \phi } ( \mathrm { \Omega } _ { t _ { 0 } } \mathrm { \Delta } _ { t _ { 0 } } ) = \pmb { I } _ { 6 }$ ；矩阵 $\mathbf { \nabla } _ { \mathbf { } } A ( \mathbf { \nabla } _ { t } )$ 为非线性系统的雅可比 矩阵满足

$$
\begin{array} { r } { A ( \mathbf { \Phi } _ { t } ) \ \mathbf { \Phi } = \left[ \begin{array} { c c c c c c } { \mathbf { 0 } _ { 3 \times 3 } } & & & & { I _ { 3 } } \\ { U _ { x x } } & { U _ { x y } } & { U _ { x z } } & { 0 } & { 2 } & { 0 } \\ { U _ { y x } } & { U _ { y y } } & { U _ { y z } } & { - 2 } & { 0 } & { 0 } \\ { U _ { z x } } & { U _ { z y } } & { U _ { z z } } & { 0 } & { 0 } & { 0 } \end{array} \right] _ { \mathbf { \Phi } _ { 6 \times \mathbf { \Phi } } } } \end{array}
$$

$U _ { i j }$ 为 $\pmb { U } ( r )$ 关于 $\boldsymbol { r } ~ = ~ \left[ x ~ \ y ~ \ z \right] ^ { \mathrm { T } }$ 的二阶偏导数 ${ \bf \nabla } , { \cal I } _ { 3 }$ 为单位矩阵。联立求解式(1)与式(2），能够确定任意时刻的状态转移矩阵。

# 1.3转移轨道设计方案

本文通过脉冲修正EML2点Halo轨道的稳定流形并结合月球借力技术给出了三脉冲转移轨道设计方案。同时为了实现对月球背面近距离观测与未来为月球背面搭建无线电望远镜时进行物质运输、投放等任务设计了短时间绕月飞行的四脉冲转移轨道。

![](images/995f4a73da9fe4e6bf0a6b892ff682983d30a9e6b0891b50ad5086bb337fe3de.jpg)  
图2转移轨道设计方案Fig.2Transfer orbit design scheme

在三脉冲与四脉冲设计方案中，重点分析了不同月球借力约束条件下不同幅值Halo轨道的不同入轨点对转移轨道参数的影响，最终确定不同设计方案的HOI点选择策略如图2所示。

# 2约束条件与分析方法

为了利用与Halo轨道相连的稳定流形，本文采用逆向积分策略设计地月平动点转移轨道。在考虑多约束条件下分别对月球至Halo轨道与地-月间的转移轨道进行分析。

# 2.1 月球至目标Halo轨道段

在转移轨道设计过程中，当月球借力点考虑不同约束时将对速度增量等参数产生较大的影响。为了分析不同约束条件下的借力效果，首先定义月球借力约束 即近月高度 $\boldsymbol { h } _ { \boldsymbol { m } }$ 、航迹角 $\gamma _ { { } _ { m } }$ 、借力方位角 $\delta _ { { \scriptscriptstyle m } }$ 其中航迹角 $\gamma _ { { } _ { m } }$ 为速度矢量和垂直于位置矢量的法线之间的夹角;方位角 $\delta _ { { \scriptscriptstyle m } }$ 为月球借力点轨道平面与会合系中 $x y$ 平面所形成的二面角。航迹角与方位角的描述如图3所示。

![](images/374bd9b4c65e78901573730d4f2c08c528ada8ec8ef94f20b6c181b22fb8c396.jpg)  
图3航迹角 $\gamma _ { m }$ (左)与方位角 $\delta _ { { \scriptscriptstyle m } }$ (右)约束Fig.3 Constraints of track angle $\gamma _ { m }$ （left）andazimuth $\delta _ { { \scriptscriptstyle m } }$ (right)

假设会合系中借力点位置、速度矢量为: $r _ { \mathrm { f m } } \ =$ $[ x _ { \mathrm { f m } } \ y _ { \mathrm { f m } } \ z _ { \mathrm { f m } } ] ^ { \mathrm { T } }$ 与 $V _ { _ { \mathrm { \scriptsize ~ f m } } } \ = \ [ \dot { x } _ { _ { \mathrm { \scriptsize ~ f m } } } \ \dot { y } _ { _ { \mathrm { \scriptsize ~ f m } } } \ \dot { z } _ { _ { \mathrm { \scriptsize ~ f m } } } ] ^ { \mathrm { \scriptsize ~ T } }$ 则探测器相对于月球质心的位置矢量表示为 $P _ { \mathrm { f m } } ~ = ~ \left[ x _ { \mathrm { f m } } ~ - ~ 1 ~ + ~ \right.$ $\mu \ \gamma _ { \mathrm { f m } } \ z _ { \mathrm { f m } } ] ^ { \mathrm { T } }$ 月球半径为 $R _ { \mathrm { m } }$ ，月球借力约束条件满足式（3）即

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { h _ { m } ~ = ~ \sqrt { \left( { x } _ { \mathrm { f m } } ~ - 1 ~ + \mu \right) ^ { 2 } ~ + { y } _ { \mathrm { f m } } ^ { 2 } ~ + { z } _ { \mathrm { f m } } ^ { 2 } ~ } - R _ { \mathrm { m } } } \\ { ~ } \\ { { \gamma } _ { m } ~ = ~ \arcsin \Bigl ( \displaystyle \frac { \left( { \displaystyle x } _ { \mathrm { f m } } ~ - 1 ~ + \mu \right) ~ { \dot { x } } _ { \mathrm { f m } } ~ + { y } _ { \mathrm { f m } } { \dot { y } } _ { \mathrm { f m } } ~ + { z } _ { \mathrm { f m } } { \dot { z } } _ { \mathrm { f m } } } { \| P _ { \mathrm { f m } } \| \left\| { \displaystyle V } _ { \mathrm { f m } } \right\| } \Bigr . } \\ { ~ } \\ { { \delta } _ { m } ~ = ~ \operatorname { a r c c o s } \Bigl ( \displaystyle \frac { \left( { \displaystyle x } _ { \mathrm { f m } } ~ - 1 ~ + \mu \right) ~ { \dot { y } } _ { \mathrm { f m } } ~ - { y } _ { \mathrm { f m } } { \dot { x } } _ { \mathrm { f m } } } { \| Q _ { \mathrm { f m } } \| } \Bigr ) } \end{array} \right. } \end{array}
$$

式中： $\begin{array} { r l r } { \pmb { Q } _ { \mathrm { f m } } } & { = } & { \left[ \begin{array} { c } { y _ { \mathrm { f m } } \dot { z } _ { \mathrm { f m } } - z _ { \mathrm { f m } } \dot { y } _ { \mathrm { f m } } } \\ { z _ { \mathrm { f m } } \dot { x } _ { \mathrm { f m } } - \left( \begin{array} { c } { x _ { \mathrm { f m } } - 1 + \mu } \end{array} \right) \dot { z } _ { \mathrm { f m } } } \\ { \left( \begin{array} { c } { x _ { \mathrm { f m } } - 1 + \mu } \end{array} \right) \dot { y } _ { \mathrm { f m } } - y _ { \mathrm { f m } } \dot { x } _ { \mathrm { f m } } } \end{array} \right] } \end{array}$ ,文中$\lVert \cdot \rVert$ 为2范数。

由于目标Halo轨道的稳定流形能够延伸到月球附近，可利用稳定流形为转移轨道的设计提供初值。同时在给定约束条件下微分修正作为一个局部优化算法 具有快速收敛特性。因此采用最小二乘微分修正算法对流形进行脉冲调整，使得转移轨道末端满足期望的月球借力约束具体步骤如下：

Step1.针对转移轨道末端约束条件本文选定控制变量 $\pmb { C } _ { 0 }$ 为HOI点三轴速度矢量 $V$ 与飞行时间$T$ 。通过比较约束条件的实际值与期望值 $c _ { \mathrm { d m } }$ 确定约束矢量 $F ( C _ { m } )$ 即

$$
\left\{ \begin{array} { c } { { C _ { 0 } ~ = ~ [ V _ { x } ~ , V _ { y } ~ , V _ { z } ~ , T ] _ { \mathrm { H 0 I } } ^ { \mathrm { T } } } } \\ { { } } \\ { { { \cal F } ( C _ { m } ) } } \\ { { } } \end{array} \right. = \left[ \begin{array} { c } { { { h _ { m } } - h _ { \mathrm { d m } } } } \\ { { { \sin } \gamma _ { m } - { \sin } \gamma _ { \mathrm { d m } } } } \\ { { { \cos } \delta _ { m } - { \cos } \delta _ { \mathrm { d m } } } } \end{array} \right] _ { \mathrm { m o o n } }
$$

Step2.结合状态转移矩阵 $\pmb { \phi }$ 推导约束矢量相对于控制变量的微分关系式。具体地，根据链规则约束矢量满足

$$
\delta F _ { i } = \frac { \partial F _ { i } } { \partial V _ { x } } \delta V _ { x } + \frac { \partial F _ { i } } { \partial V _ { y } } \delta V _ { y } + \frac { \partial F _ { i } } { \partial V _ { z } } \delta V _ { z } + \frac { \partial F _ { i } } { \partial T } \delta T =
$$

$$
\bigg ( \frac { \partial F _ { i } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { T } } } \pmb { \phi } _ { \mathrm { r v } } + \frac { \partial F _ { i } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } \pmb { \phi } _ { \mathrm { v v } } \bigg ) \delta V + \bigg ( \frac { \partial F _ { i } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { T } } } V _ { \mathrm { f m } } + \frac { \partial F _ { i } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } \pmb { a } _ { \mathrm { f m } } \bigg ) \delta T
$$

式中： $\frac { \partial F _ { i } } { \partial V _ { x } } \ , \frac { \partial F _ { i } } { \partial T }$ 的推导过程如式(6)所示 1 $\frac { \partial F _ { i } } { \partial V _ { y } } \ , \frac { \partial F _ { i } } { \partial V _ { z } }$ 与 $\frac { \partial F _ { i } } { \partial V _ { x } }$ 的表达式类似； $\delta F _ { i }$ 为式（4）中约束矢量的第衔表达式； $\phi _ { _ \mathrm { r v } } \ \pmb { \mathcal { P } } _ { \mathrm { v v } }$ 为状态转移矩阵中 $3 \times 3$ 子矩阵即 $\pmb { \phi } = \left[ \begin{array} { l l } { \pmb { \phi } _ { \mathrm { r r } } } & { \pmb { \phi } _ { \mathrm { r v } } } \\ { \pmb { \phi } _ { \mathrm { v } } } & { \pmb { \phi } _ { \mathrm { v } } } \end{array} \right] ; \pmb { a } _ { \mathrm { f m } }$ 为月球借力点加速度矢量。

$$
[ { \frac { \partial F _ { i } } { \partial V _ { x } } } = { \frac { \partial F _ { i } } { \partial X _ { \mathrm { f m } } ^ { \mathrm { T } } } } { \frac { \partial X _ { \mathrm { f m } } } { \partial V _ { x } } } = [ { \frac { \partial F _ { i } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { T } } } } { \frac { \partial F _ { i } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } } ] [ { \frac { \partial r _ { \mathrm { f m } } } { \partial V _ { x } } } ] =
$$

$$
\Big [ \frac { \partial F _ { i } } { \partial \pmb { r } _ { \mathrm { f m } } ^ { \mathrm { T } } } \frac { \partial F _ { i } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } \Big ] \Big [ \pmb { \phi } _ { r \times 4 } \Big ]
$$

由式（5)可知求解v即可确定约策矢量关于控制变量的微分关系式。

# (1)借力高度约束

结合式(3）、式(4)及矢量求导法则，月球借力点高度约束的微分关系式满足

$$
\begin{array}{c} \begin{array} { r } { \left\{ \frac { \partial F _ { 1 } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { T } } } = \frac { \partial h _ { m } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { T } } } = \frac { P _ { \mathrm { f m } } ^ { \mathrm { T } } } { \left. P _ { \mathrm { f m } } \right. } \right.} \\ { \frac { \partial F _ { 1 } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } = \mathbf { 0 } _ { 1 \times 3 } } \end{array}   \end{array}
$$

（2）飞行航迹角约束

探测器相对于月球的飞行航迹角约束的微分关系式为

$$
\left\{ \begin{array} { l l } { \displaystyle { \frac { \partial F _ { 2 } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { T } } } } = \displaystyle { \frac { 1 } { \| P _ { \mathrm { f m } } \| } } \frac { V _ { \mathrm { f m } } ^ { \mathrm { T } } } { \| V _ { \mathrm { f m } } \| } - \displaystyle { \frac { P _ { \mathrm { f m } } ^ { \mathrm { T } } } { \| P _ { \mathrm { f m } } \| ^ { 2 } } } \mathrm { s i n } \gamma _ { m } } \\ { \displaystyle { \frac { \partial F _ { 2 } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } } = \displaystyle { \frac { 1 } { \| V _ { \mathrm { f m } } \| } } \displaystyle { \frac { P _ { \mathrm { f m } } ^ { \mathrm { T } } } { \| P _ { \mathrm { f m } } \| } } - \displaystyle { \frac { V _ { \mathrm { f m } } ^ { \mathrm { T } } } { \| V _ { \mathrm { f m } } \| ^ { 2 } } } \mathrm { s i n } \gamma _ { m } } \end{array} \right.
$$

(3)借力方位角 $\delta _ { { \scriptscriptstyle m } }$ 约束

借力方位角 $\delta _ { { \scriptscriptstyle m } }$ 约束关于位置、速度矢量的微分关系式为

$$
\Big [ \frac { \partial F _ { i } } { \partial \pmb { r } _ { \mathrm { f m } } ^ { \mathrm { T } } } \frac { \partial F _ { i } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { T } } } \Big ] \Big [ \pmb { \Sigma } _ { \mathrm { f m } } ^ { V _ { \mathrm { f m } } } \Big ]
$$

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \partial F _ { \mathrm { 3 } } } { \partial r _ { \mathrm { f m } } ^ { \mathrm { \Gamma } } } = \frac { 1 } { \| Q _ { \mathrm { f m } } \| } k _ { \mathrm { 1 } } + \frac { ( \mathbf { \nabla } P _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } V _ { \mathrm { f m } } ) \displaystyle V _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } - \mathrm { \Gamma } \| V _ { \mathrm { f m } } \| ^ { 2 } P _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } } { \| Q _ { \mathrm { f m } } \| ^ { 2 } } \mathrm { c o s } \delta _ { m } } \\ { \displaystyle \frac { \partial F _ { \mathrm { 3 } } } { \partial V _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } } = \frac { 1 } { \| Q _ { \mathrm { f m } } \| } k _ { \mathrm { 2 } } + \frac { ( \mathbf { \nabla } P _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } V _ { \mathrm { f m } } ) \displaystyle P _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } - \mathrm { \Gamma } \| P _ { \mathrm { f m } } \| ^ { 2 } V _ { \mathrm { f m } } ^ { \mathrm { \scriptscriptstyle T } } } { \| Q _ { \mathrm { f m } } \| ^ { 2 } } \mathrm { c o s } \delta _ { m } } \end{array} \right.
$$

式中:

$$
k _ { \mathrm { 1 } } ~ = ~ [ \dot { y } _ { \mathrm { f m } } ~ , - \dot { x } _ { \mathrm { f m } } ~ \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } ] ~ k _ { \mathrm { 2 } } ~ = ~ [ - y _ { \mathrm { f m } } ~ \kappa _ { \mathrm { f m } } ~ - 1 ~ + \mu ~ \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } \mathrm { ~ } ] \mathrm { ~ } \circ ~
$$

Step3.在微分修正过程中选定积分终止条件为零航迹角可以保证转移轨道较好地满足借力点约束条件。因此处理约束条件时,设定F=sinγm$- \sin \gamma _ { \mathrm { d m } } \ = \ 0$ 由式(5)可推导 $\delta T \ : = \ : \delta T ( \delta V )$ 代入借力高度与方位角约束的微分关系式中，满足

$$
{ \bigl [ } { \begin{array} { l } { \delta F _ { 1 } } \\ { \delta F _ { 3 } } \end{array} } { \bigr ] } = { \left[ \begin{array} { l } { { \cfrac { \partial F _ { 1 } } { \partial V ^ { \mathrm { T } } } } - { \cfrac { \partial F _ { 1 } / \partial T } { \partial F _ { 2 } / \partial T } } { \cfrac { \partial F _ { 2 } } { \partial V ^ { \mathrm { T } } } } } \\ { { \cfrac { \partial F _ { 3 } } { \partial V ^ { \mathrm { T } } } } - { \cfrac { \partial F _ { 3 } / \partial T } { \partial F _ { 2 } / \partial T } } { \cfrac { \partial F _ { 2 } } { \partial V ^ { \mathrm { T } } } } } \end{array} \right] } \delta V
$$

利用最小二乘法迭代求解式（10），可确定 $\delta V$ ，进而修正HOI点三轴速度矢量，使得最终的转移轨道末端收敛于期望的约束值。

# 2.2地球至月球转移轨道段

为了体现圆形地球停泊轨道特性，考虑末端约束条件包括轨道高度 $h _ { e }$ 、轨道倾角 $i _ { e }$ 、升交点赤经$\varOmega _ { e }$ 及地－月转移飞行时间 $T _ { e }$ 并以相对地球的航迹角 $\gamma _ { e }$ 为积分终止条件。

针对地-月转移轨道特性研究，本文采用遗传算法（Geneticalgorithm，GA）与微分修正算法（Differentialcorrection，DC）相结合的混合优化方法。一方面，充分利用遗传算法的全局收敛特性与微分修正的局部快速收敛特性;另一方面遗传算法的优化结果可作为微分修正算法的初值，避免了微分修正的初始猜想。基于混合优化算法，设计了燃料最优的地月转移轨道。

# (1)遗传算法全局优化

遗传算法是基于基因遗传学原理与自然选择策略的智能优化算法[1]。利用群体搜索策略与个体之间的信息交换，以适应度值判断个体的好坏并结合选择、交叉及变异等一系列遗传操作最终逼近问题的最优解。

在地月转移轨道设计时，优化变量为借力点速度增量 $\Delta V _ { m } ~ = ~ [ \Delta V _ { x } \ , \Delta V _ { y } \ , \Delta V _ { z } ] _ { m } ^ { \mathrm { T } }$ ,以燃料最优为性能指标分析可知，Halo轨道入轨速度增量对总速度增量的影响较小。因此，选取自标函数 $J _ { \mathrm { G A } }$ 为地球逃逸点与月球借力机动点速度增量大小，满足

$$
J _ { \mathrm { G A } } ~ = ~ \Delta V _ { \mathrm { e a r t h } } ~ + ~ \Delta V _ { \mathrm { m o o n } }
$$

式中： $\Delta V _ { \mathrm { { m o o n } } }$ 为月球借力点三轴速度增量大小，即$\| \Delta V _ { _ m } \|$ 。优化过程中同时考虑地球停泊轨道高度、轨道倾角、升交点赤经及飞行时间约束定义为不等式约束，满足

$$
\begin{array} { r } { \pmb { \psi } _ { \mathrm { G A } } = \left\{ \begin{array} { l l } { h _ { \mathrm { m i n } } < h _ { e } < h _ { \mathrm { m a x } } } \\ { i _ { \mathrm { m i n } } < i _ { e } < i _ { \mathrm { m a x } } } \\ { \Omega _ { \mathrm { m i n } } < \Omega _ { e } < \Omega _ { \mathrm { m a x } } } \\ { T _ { \mathrm { m i n } } < T _ { e } < T _ { \mathrm { m a x } } } \end{array} \right. } \end{array}
$$

式中：下标 $\operatorname* { m i n }$ 与max分别表示在遗传算法优化中，设定的约束条件最小值与最大值。

# (2)微分修正局部优化

通过遗传算法能够使地月转移轨道末端位于期望的地球停泊轨道附近，并且轨道根数满足我国发射要求。因此在微分修正局部优化中只考虑轨道高度与航迹角约束。

$$
\pmb { \psi } _ { \mathrm { { b c } } } = \left[ \begin{array} { c } { h _ { e } - h _ { \mathrm { { d e } } } } \\ { \sin \gamma _ { e } - \sin \gamma _ { \mathrm { { d e } } } } \end{array} \right]
$$

同理结合式(7）(8)与式(10)的微分关系能够设计出同时满足轨道高度与航迹角约束的地－月转移轨道。

综上所述，混合优化求解过程如图4所示。

![](images/f159a36437ee93001c4e77f0f0332d0d4a23b631a0d946c5302771eed03e0bc6.jpg)  
图4混合优化算法流程图  
Fig.4Flow chart of the hybrid optimization algorithm

# 3仿真结果分析

本文以地月系统L2点附近不同法向幅值的Halo轨道为自标轨道，在考虑不同月球借力约束与地球停泊轨道约束条件下通过脉冲调整稳定流形并结合混合优化算法，设计了三脉冲与四脉冲的平动点转移轨道。

为充分分析目标Halo轨道上不同HOI点对飞行时间与机动速度增量的影响，首先将Halo轨道按照时间等分为360个点,定义Halo轨道与会合系xy平面相交的两点中距离月球较远的点为1点，积分一周后对Halo轨道上各点进行编号。

# 3.1三脉冲转移轨道方案分析

在三脉冲转移轨道设计过程中，当保持其他条件不变的情况下，借力高度越低，借力飞行的效果越显著[6]。因此，本文研究借力约束条件对燃耗等参数的影响时，对固定的借力高度进行分析，任务约束如表2所示。

# 表2任务约束条件

Table 2The mission constraints   

<html><body><table><tr><td>参数</td><td>约束条件</td></tr><tr><td>地球停泊轨道高度h/km</td><td>200</td></tr><tr><td>偏心率e</td><td>0</td></tr><tr><td>倾角范围(iminimax）/(°)</td><td>(20 60)</td></tr><tr><td>RAAN范围(ΩminΩmax）/(°)</td><td>(-70 0)</td></tr><tr><td>地-月段飞行时间(Tmin，Tmax）/天</td><td>(46)</td></tr><tr><td>发射时间(年/月/日)</td><td>2020/01/01</td></tr><tr><td>航迹角γ。iym/(°</td><td>0</td></tr><tr><td>月球借力点高度hm/km</td><td>100</td></tr><tr><td>位置误差/m</td><td>1</td></tr><tr><td>角度误差/(°)</td><td>1 ×10-3</td></tr></table></body></html>

# 3.1.1只考虑借力高度约束的借力效果分析

在表2的任务约束下，仅施加月球借力高度约束分析不同法向幅值Halo轨道、不同HOI点与各个机动点速度增量大小及飞行时间的关系。由图5～7可知:（1)只考虑借力高度约束时随着Halo轨道法向幅值不断增大HOI点空间位置逐步改变，为了满足借力高度约束，需要消耗更大的速度增量用于调整稳定流形。因此针对相同编号的HOI点，不同幅值Halo轨道所需总速度增量呈现增长趋势且变化显著;（2)针对各个机动点施加的速度增量大小，Halo轨道入轨速度增量单调变化，法向幅值对HOI点速度增量的影响较小。同时月球借力点与地球逃逸点速度增量是影响总速度增量差异的主要因素；(3)相比于地月段飞行时间月球至Halo轨道段耗时较长与总飞行时间变化一致保持单调递增。

结合图5与图6随着Halo轨道法向幅值逐步增大仅仅考虑月球借力高度约束并不能有效地降低借力点的速度增量。通过分析借力方位角 $\delta _ { { \scriptscriptstyle m } }$ 的变化如图8所示当Halo轨道法向幅值为 $2 0 0 0 ~ \mathrm { k m }$

![](images/c205ee0119abb6dbf3b9f7a9151daab330270f67efc861f5c61f2db1f5d80422.jpg)  
图5不同幅值Halo轨道HOI点消耗的总速度增量Fig.5Total speed increment at HOI of Halo orbitswith different amplitude  
图6三处机动点施加的速度增量大小 Fig.6Speed increment performed on three-impulse maneuver points   
Fig.7Time of flight in each transfer orbit segment

A=2000 kmA=3000 km---A=4000 kmA_=5000 km m1 A=6000km030 60 90 120150180210 240270 300 330 360( 400 2004V 10030 60 90 120150180210 240 270 300330 360330304 3110 306090120150180210 240270 300330 360Halo轨道入轨点

A=2000 km.A=3000 km----.A=4000 kmA=5000km -.A=6000km  
1 30 6090120 150180 210 240270 300 330 360/回 6  
- 5430 60 90120 150 180 210 240 270 300 330 3603020101 30 60 90 120150 180 210 240 270 300 330 3600 Halo轨道入轨点

时借力方位角 $\delta _ { \scriptscriptstyle m } ~ \in ~ ( 4 ^ { \circ } ~ 5 ^ { \circ } )$ 随着法向幅值的增大，相同HOI点对应的借力方位角逐渐增加。因此本文在借力高度与航迹角约束的基础上进一步添加方位角约束分析不同方位角对速度增量与总飞行时间的影响进而确定降低飞行燃耗的策略。

![](images/112a6a510dea594f5465e22208a9aea1d40adc551136082040aa9d2503ba262e.jpg)  
图7转移轨道飞行时间  
图8不同幅值Halo轨道对应的借力方位角 Fig.8Gravity-assist azimuth for Halo orbits with different amplitude

# 3.1.2 借力方位角对借力效果的影响分析

通过脉冲调整稳定流形可确保轨道末端满足借力高度与航迹角约束然而当添加方位角约束后部分稳定流形不易收敛到期望的借力点。因此，以下针对不同方位角约束分析不同幅值Halo轨道的转移轨道特性数据对比后确定HOI点的选择策略。

图9描述了不同借力方位角约束下飞行时间-速度增量曲线左图中线段间空白区域表征稳定流形未能较好地满足约束条件，右图为总飞行时间$T \in ( 1 8 \ 2 4 )$ 天的放大图。

![](images/74bcfe26f45c9eb539f7278057be2053925940547e0ca81fed543ce64319b1d4.jpg)  
图9 $A _ { z } = 5 0 0 0 ~ \mathrm { k m }$ 时不同借力方位角速度增量曲线  
Fig.9Speed increment curves for different gravity-assist azimuth when $A _ { z } = 5 0 0 0 ~ \mathrm { k m }$

（1)针对相同HOI点随着借力方位角的减小，借力飞行对入轨点速度增量的影响逐渐增强，但借力点所需的速度增量呈现下降趋势，总速度增量相比于仅考虑借力高度约束时不断降低，最大差值为$5 8 . 5 2 ~ \mathrm { m / s }$ 。

(2)针对不同HOI点选取借力方位角 $\delta _ { { \scriptscriptstyle m } } = 4 ^ { \circ }$ 分析在 $T \in ( 1 2 , 1 7 ) \cup ( 1 8 , 2 4 )$ 天区间内总速度增量存在两个极小值，即Node $= 1 4 3$ ,耗时14.81天总燃耗 $3 3 2 9 . 9 4 \mathrm { \ m / s } ; \mathrm { N o d e } = 3 1 0$ ，飞行时间与总速度增量分别为21.77天 $, 3 3 2 2 . 6 5 \mathrm { ~ m } / \mathrm { s }$ 。同时，满足约束的入轨点数自随着借力方位角的变化而减少。综合分析较好地满足借力约束的HOI点选取范围为[90 160)与[240315）。

表3选取幅值为 $5 0 0 0 ~ \mathrm { k m }$ 的 Halo轨道对比分析不同借力约束下机动点消耗的速度增量大小其中各个HOI点的第一行数据为仅考虑借力高度与航迹角约束的情况。

图10与图11表明:(1)当Halo轨道法向幅值增大时，总速度增量逐步增加,满足 $\Delta V _ { \underset {  } {  } } \ \in$ ( $3 3 2 0 \ \mathrm { m / s }$ （204号 $3 4 0 0 \ \mathrm { m / s } .$ ）。进一步说明了大幅值Halo轨道的稳定流形在月球处的借力效果较差必须施加更大的脉冲对流形进行修正以满足给定的约束；(2)在给定的两个入轨点区间内随着入轨点的变化HOI点速度增量总体呈现先减小后增大的趋势，而借力点增量变化相反。

表3不同借力约束条件下参数比较  
Table 3Parameter comparison under different gravity-assist constraint conditions   

<html><body><table><tr><td>HOI点</td><td>借力方 位角/（°)</td><td>HOI点机动 速度增量 /(m·s-1)</td><td>借力点机动 速度增量 /(m·s-1)</td><td>三脉冲总 速度增量 /(m·s-1)</td></tr><tr><td rowspan="3">90</td><td>10.51</td><td>18.34</td><td>226.16</td><td>3372.88</td></tr><tr><td>4.00</td><td>38.64</td><td>189.39</td><td>3348.82</td></tr><tr><td>8.00</td><td>20.71</td><td>203.15</td><td>3345.11</td></tr><tr><td rowspan="3">120</td><td>10.97</td><td>9.33</td><td>233.33</td><td>3372.68</td></tr><tr><td>4.00</td><td>16.92</td><td>193.82</td><td>3331.85</td></tr><tr><td>8.00</td><td>11.04</td><td>206.32</td><td>3339.52</td></tr><tr><td rowspan="3">270</td><td>12.05</td><td>0.22</td><td>248.39</td><td>3381.32</td></tr><tr><td>4.00</td><td>13.15</td><td>190.85</td><td>3324.48</td></tr><tr><td>8.00</td><td>6.50</td><td>202.73</td><td>3330.77</td></tr><tr><td rowspan="3">300</td><td>12.04</td><td>0.03</td><td>248.38</td><td>3381.11</td></tr><tr><td>4.00</td><td>12.05</td><td>190.52</td><td>3323.00</td></tr><tr><td>8.00</td><td>5.28</td><td>204.01</td><td>3331.04</td></tr></table></body></html>

![](images/c455f590e8c1a928740479ad7e2b310bce6a4cd25bc6cb6e9ef61e01fc768888.jpg)  
图10不同法向幅值的不同方位角对比分析图

![](images/099c17792df4b75948a40cb9b7c74c10d8dfc7a6ebe520911d64546a4d047509.jpg)  
Fig.10Comparison diagram of different azimuth in different normal amplitude   
图11方位角 $\delta _ { \scriptscriptstyle m } \ = \ 6 ^ { \circ }$ 时HOI点与借力点速度增量 Fig.11Speed increment at HOI and gravity-assist points when $\delta _ { \scriptscriptstyle m } \ = \ 6 ^ { \circ }$

表4给出了不同幅值条件下对应的最佳入轨点、停泊轨道等各项参数。

综上所述，选取幅值 $A _ { _ z } = 1 0 0 0 0 \ \mathrm { k m }$ 的Halo轨道为目标轨道，设计了三脉冲转移轨道，如图12所示其中虚线为只考虑借力高度与航迹角约束实线为添加方位角约束的转移轨道。在借力高度与航迹角约束条件下，总飞行时间为13.25天，地球逃逸点、月球借力点与HOI点速度增量大小分别为$3 1 3 3 . 4 1 \mathrm { ~ m / s ~ } , 6 8 5 . 0 1 \mathrm { ~ m / s ~ }$ 与 $9 . 6 7 ~ \mathrm { m / s }$ 。当添加借力方位角约束后，三处机动点速度增量大小分别为$3 1 2 0 . 3 3 ~ \mathrm { m / s }$ （ $, 1 9 0 . 2 4 \mathrm { ~ m } / \mathrm { s }$ 与 $3 9 . 6 2 ~ \mathrm { m / s }$ 总飞行时间变化较小即13.63天。比较两种情况可知在飞行时间相近条件下，考虑借力方位角后的总速度增量显著降低相差 $4 7 7 . 9 \mathrm { ~ m / s ~ }$ 。

# 表4方位角 $\delta _ { { \scriptscriptstyle m } } = 4 ^ { \circ }$ 时不同幅值的借力效果对比

Table 4Comparison of gravity-assist effects in different amplitude when $\delta _ { { \scriptscriptstyle m } } \ = \ 4 ^ { \circ }$   

<html><body><table><tr><td>Halo轨道 幅值/km</td><td>最佳入 轨点HOI</td><td>倾角/升交 点赤经/(°)</td><td>飞行时间 /天</td><td>总速度增 量/(m·s-1)</td></tr><tr><td>5000</td><td>143</td><td>35.8/-10.9</td><td>14.81</td><td>3329.94</td></tr><tr><td>6000</td><td>141</td><td>23.0/-19.6</td><td>14.89</td><td>3333.28</td></tr><tr><td>7000</td><td>135</td><td>23.1/-17.5</td><td>14.57</td><td>3337.27</td></tr><tr><td>8000</td><td>128</td><td>21.1/-21.1</td><td>14.08</td><td>3341.80</td></tr><tr><td>9000</td><td>126</td><td>21.1/-26.5</td><td>13.96</td><td>3345.74</td></tr><tr><td>10000</td><td>120</td><td>21.6/-35.3</td><td>13.63</td><td>3350.19</td></tr></table></body></html>

![](images/9215388310029a8e26349582cab0732683f110e753e93308c63e6fa611fcc154.jpg)  
图12不同借力约束条件的三脉冲转移轨道 Fig.12Three-impulse transfer trajectories under different gravity-assist constraint conditions

# 3.2 四脉冲绕月转移轨道方案分析

由于月球背面在未来的空间研究中具有巨大的应用价值如何在燃耗较低的条件下实现探测器对月球背面近距离观测。针对此问题，采用与三脉冲设计方案类似的方法，设计了短时间绕月飞行的四脉冲转移轨道分析了不同HOI点在不同借力方位角约束下的转移轨道特性。目标函数为

$$
J _ { _ { \mathrm { G A } } } = \Delta V _ { _ { \mathrm { e a r t h } } } + \Delta V _ { _ { \mathrm { m l } } } + \Delta V _ { _ { \mathrm { m 2 } } }
$$

式中： $\Delta V _ { \mathrm { { m 1 } } } ~ { \Delta V _ { \mathrm { { m 2 } } } }$ 分别表示月球两次机动点的速度增量大小。

图13中探测器以 $3 1 1 8 . 3 5 \mathrm { ~ m } / \mathrm { s }$ 的速度增量从轨道高度为 $2 0 0 ~ \mathrm { k m }$ 、倾角 $2 4 ^ { \circ }$ 、升交点赤经 $\boldsymbol { - 3 1 ^ { \circ } }$ 的地球停泊轨道逃逸，飞行4.42天后到达高度为$4 0 0 ~ \mathrm { k m }$ 的月球借力机动点1，施加脉冲 $2 5 0 . 9 2 ~ \mathrm { m / s }$ 形成1.33天的绕月飞行轨道，当飞行高度为$1 0 0 ~ \mathrm { k m }$ 方位角为 $4 ^ { \circ }$ 时进行第二次借力机动进入月球-Halo轨道段，增量大小为 $5 1 . 3 8 \mathrm { ~ m } / \mathrm { s }$ ，航行8.97天后以 $1 5 . 6 1 ~ \mathrm { m / s }$ 的增量完成入轨操作。

图14与表5进一步分析了四脉冲轨道设计方案中不同借力约束与机动点速度增量之间的关系，表5中各项法向幅值包含的四组数据依次对应方位角 $\delta _ { { \scriptscriptstyle m } } = 4 ^ { \circ } ~ 6 ^ { \circ } ~ 8 ^ { \circ } ~ , 1 0 ^ { \circ }$ 。分析可知：随着借力方位角的减小满足约束的HOI点数自及速度增量、借力点1速度增量、总速度增量的变化趋势与三脉冲设计方案结果相似而借力效果对飞行时间、借力点2速度增量的影响较小。

![](images/1eb46feef2bc9589c88b0cc6cc85c5d548e1a0c44bb4a6adbe24fbc611987dc8.jpg)  
图13 $A _ { z } = 5 0 0 0 ~ \mathrm { k m }$ 的四脉冲转移轨道

![](images/7b19204f5bdab0f7cd6030507c944cbeccd97b4d208af75b2301ba42756aabf0.jpg)  
Fig.13Four-impulse transfer trajectory when $A _ { z } = 5 0 0 0 ~ \mathrm { k m }$   
图14 $A _ { z } = 5 0 0 0 ~ \mathrm { k m }$ 时不同借力方位角约束分析Fig.14Analysis of constraints of different gravity-assistazimuth when $A _ { z } = 5 0 0 0 ~ \mathrm { k m }$

表5Node $= 1 2 5$ 时不同方位角转移轨道参数对比Table 5Parameter comparison of transfer trajectory withdifferent azimuth when Node $= 1 2 5$   

<html><body><table><tr><td>Halo轨 道法向 幅值/km</td><td>借力点1 速度增量 /(m·s-1)</td><td>借力点2 速度增量 /(m·s-1)</td><td>HOI点机 动速度增量 /(m·s-1)</td><td>四脉冲总 速度增量 /(m·s-1)</td></tr><tr><td rowspan="5">5000</td><td>251.29</td><td>51.38</td><td>16.24</td><td>3437.33</td></tr><tr><td>256.86</td><td>51.38</td><td>12.92</td><td>3440.76</td></tr><tr><td>265.67</td><td>51.37</td><td>10.30</td><td>3448.80</td></tr><tr><td>281.40</td><td>51.34</td><td>8.73</td><td></td></tr><tr><td></td><td>51.40</td><td>40.81</td><td>3466.27 3460.16</td></tr><tr><td rowspan="4">10000</td><td>249.77</td><td></td><td>34.12</td><td></td></tr><tr><td>258.56</td><td>51.46</td><td></td><td>3464.17</td></tr><tr><td>270.35</td><td>51.48</td><td>29.74</td><td>3474.09</td></tr><tr><td>292.76</td><td>51.48</td><td>25.77</td><td>3497.35</td></tr></table></body></html>

# 4结论

本文针对地月L2点不同任务需求的转移轨道设计问题基于不变流形理论与混合优化技术重点研究了不同月球借力约束与HOI点对转移轨道飞行时间、机动速度增量的影响。研究结果表明在圆型限制性三体系统中：

(1)针对小幅值Halo轨道，仅考虑借力高度与航迹角约束即可设计出满足要求且燃耗较低的三脉冲转移轨道。其中总速度增量主要取决于借力点与地球逃逸点所施加的脉冲大小，总飞行时间随着HOI点的增大呈现单调变化。

(2)针对固定幅值Halo轨道分析，添加借力方位角约束后，满足要求的HOI点数目逐渐减少，但相比于仅考虑借力高度与航迹角约束，月球借力机动增量与总速度增量显著下降，而借力方位角的变化对飞行时间的影响较小。

(3)针对不同幅值Halo轨道分析选定借力方位角与Halo轨道入轨点后，由于流形特性的影响，随着法向幅值的增大HOI点施加脉冲依次增加借力点速度增量降低总燃耗不断增大。同时在四脉冲设计方案中借力点2所需速度增量变化较小。

以上的研究与分析，对于考虑月球借力的地月平动点转移轨道的设计与应用、参数选择等具有重要的借鉴意义。

# 参考文献

[1］徐明,徐世杰．地－月系平动点及Halo轨道的应用研究 [J]．宇航学报 $2 0 0 6 ~ 2 7 ( 4 ) : 6 9 5 ~ - 6 9 9$ [Xu Ming,Xu Shijie.The application of libration points and Halo orbits in the earth-moon system to space mission design [J].Journal of Astronautics,2006,27(4):695-699.]

[2］侯锡云刘林．共线平动点的动力学特征及其在深空探测中 的应用[J]．宇航学报,2008,29(3):737-747．[Hou Xiyun,Liu Lin.The dynamics and applications of the collinear libration points in deep space exploration [J]．Journal of Astronautics ,2008 ,29(3):737 -747.]

[3]Zazzera FB,Topputo F，Massari M.Assessment of mission design including utilization of libration points and weak stability boundaries [R]．ESTEC Contract No．18147/04/NL/MV， 2004.   
[4] Parker JS.Low-energy ballistic lunar transfers [D].Colorado: University of Colorado,2007.   
[5] Zanzottera A,Migotti G,CastelliR,etal.Intersecting invariant manifolds in spatial restricted three-body problems:design and optimization of Earth-to-Halo transfers in the Sun-Earth-Moon scenario [J].Commun Nonlinear Sci Numer Simulat 2O12,17: 832 -843.   
[6]Gordon D P.Transfers to earth-moon L2 Halo orbits using lunar proximity and invariant manifolds[D].Indiana:Purdue University,2008.   
[7] Li MT,Zheng JH. Impulsive lunar Halo transfers using the stable manifolds and lunar flybys [J]．Acta Astronautica,2010， 66:1481-1492.   
[8] Renk F,Hechler M,Messerschmid E.Exploration mission in the Sun-Earth-Moon system:a detailed view on selected transfer problems [J]．Acta Astronautica,2010,67:82-96.   
[9] BastienLB,Pierre K,StephanieLD.Computing an optimized trajectory between Earth and an EML2 Halo orbit[C]．AIAA Guidance，Navigation，andControl Conference，Maryland， USA,2014.   
[10]Koon W S,Lo M W,Marsden JE.Dynamical systems,the three-body problem and space mission design [M].Singapore: World Scientific ,2004.

[11]杨希祥 李晓斌 肖飞等．智能优化算法及其在飞行器优化 设计领域的应用综述[J]．宇航学报，200930(6)：2052- 2061．[Yang Xi-xiang,LiXiao-bin,Xiao Fei,etal.Overview of intelligent optimization algorithm and its application in flight vehicles optimization design [J].Journal of Astronautics,2009, 30(6):2052-2061.]

# 作者简介：

张景瑞(1974-）女教授研究方向为空间飞行器姿态动力学与控制非线性控制。  
通信地址：北京理工大学求是楼分布式航天器系统技术研究所(100081)  
电话：(010)68912285  
Email: zhangjingrui@ bit. edu.cn

(编辑:曹亚君)