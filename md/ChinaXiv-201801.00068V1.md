编号：2016-0032

# 汽轮机静叶除湿方法的数值研究

张国杰，周忠宁，吴继青，李意民，张森（中国矿业大学电气与动力工程学院，徐州221116）

摘要：本文针对蒸汽轮机末级湿蒸汽形成现象，分析湿蒸汽非平衡凝结流动的控制方程及物理模型。对 Moses andStein喷嘴进行了计算分析，得出湿蒸汽形成过程的特点，并与实验结果相比，契合度可以证明数值计算模型及方法的正确性。最后对某汽轮机静叶进行数值计算，分析湿度及过冷度分布，提出一种新型的静叶除湿结构，并对除湿效果进行计算分析。结果表明，随着通道直径的增加，静叶出口位置的平均湿度降低，湿汽损失减小。

关键字：静叶除湿；非平衡；液滴形成；两相流动

# Study on Numerical Simulation of Steam Turbine Dehumidification

ZHNAG Guo-Jie, ZHOU Zhong-Ning,, WU Ji-Qing,LI Yi-Min, ZHANG Sen

SchoolofElectricalandPower Engineering,China UniversityofMining& Technology,Xuzhou,221116,China）

Abstract: The research，analyzed the governing equations and physical models of wet steam nonequilibrium condensation flow,carried out a numerical calculation on the Moses and Stein nozzle and the correctness of the numerical calculation is proved by comparing with the experimental results which is mainly aiming at the wet steam formation phenomenon in the last stage of the steam turbine.Besides,a fresh dehumidification structure was proposed and the numerical calculation was performed based on a specific steam turbine after analyzed the distribution of wetness and supercooling. The results show that: as passage diameter increasing,both of the average wetness in the outlet position of the stator and the wetness loss decrease.

Key words: Stator dehumidification; Non-equilibrium; Droplets emerging; Two-phase flow

# 0引言：

汽轮机是转换能量形式的重要设备，在国民经济中占有重要位置。然而在汽轮机末级，蒸汽膨胀做功，导致蒸汽温度低于饱和温度，产生不平衡凝结，会生成大量液滴，其对级的工作非常不利，不仅降低了透平的级效率，而且随着液滴的不断长大会严重的侵蚀动叶片。

汽轮机流道中湿蒸汽所携带的液滴的产生及其随蒸汽的流动是非常复杂的相变和两相流动问题。研究湿蒸汽难点在于不仅蒸汽的湿度沿叶片的圆周方向和半径方向均不是均匀分布的，而且液滴和蒸汽相互之间会发生传热和传质，其过程涉及复杂的相变问题。Stodola[1]和Wilson[2]最早在1920年使用超音速Laval喷嘴研究了这一现象，1930 年Yellott等[3-5]人也进行了类似的研究，Bakhtar 和 Zidi通过实验研究了三种不同膨胀率的二维喷嘴的成核现象，得出了沿喷嘴轴线方向的压比及液滴尺寸数据[，接着两人又进行理论方面的研究[7]。Gerber等[8]人开发了一套基于欧拉-拉格朗日方法的数值计算模型，并且使用该模型对Moore低压缩放喷管进行了计算，数值结果和实验值匹配度良好。Gerber和Kermnai两人基于欧拉-欧拉方法研究出了应用于高压、跨音速条件下的非平衡凝结的数值方法[9]，计算结果与实验结果契合度良好。但是直至今日，在汽轮机低压级内的湿蒸汽流动仍旧是很值得研究的，尤其是由于湿蒸汽引起的各种损失，具体可参考 Moore 和Sieverding[10]。

随着计算机技术的进步和两相流理论趋向成熟，使用数值模拟的方法来研究汽轮机内的湿蒸汽流动已经成为可能[1]。通过建立湿蒸汽凝结流动的数学模型，研究汽轮机中湿蒸汽形成及流动，能准确判断出液滴半径、液滴数目及湿度等湿蒸汽参数。

目前汽轮机除湿的方法主要分为内部和外部除湿两种，外部除湿是通过回热提高蒸汽参数，从而达到除湿的目的。而内部除湿主要分为三类：静叶除湿、动叶除湿、动静叶间隔板除湿。本文主要研究静叶除湿。而目前的静叶除湿主要是静叶制成空腔，通过空腔借助吹扫、抽吸或壁面加热的方法将沉积导叶表面的水膜或尾缘集中的大液滴去掉，以增加蒸汽干度。而这些除湿方法结构复杂，并且没有从根本上消除湿蒸汽的形成。

合理的静叶除湿结构，能够除去湿蒸汽中大部分水滴，从而提高汽轮机效率和安全性[10]。本文首先对汽轮机内部的湿蒸汽形成进行了分析，然后采用两相流模型对Moses和Stein喷嘴进行了数值计算，并与实验值进行对比，保证数值计算的可靠性。最后提出一种新型的除湿结构，并进行数值计算和结果分析。

# 1湿蒸汽相变过程及数学模型

透平静叶中流动的干蒸汽相变到湿蒸汽主要经历三个过程，第一阶段，饱和蒸汽越过饱和线后，发生凝结，产生少量极微小液滴。第二阶段，随着蒸汽的膨胀，过冷度增大，第一阶段产生的极微小液滴突然变大，但由于数目不是很多，液滴吸收蒸汽温度，半径减小，导致过冷度增加；第三阶段，随着蒸汽的膨胀，过冷度逐渐减小，成核率减小最后趋于恒定，液滴数目趋于不变，液滴半径略微增大 $( 0 . \mathrm { ~ l ~ - ~ } 1 \mu m )$ 。在整个流动过程中，可采用非平衡两相流模型对其进行计算。

# 1.1控制方程

汽轮机内的湿蒸汽中所形成的小液滴的运动是随着蒸汽一起运动的，为了研究，本文假设液滴和蒸汽之间没有相对运动，即液滴和蒸汽有共同的速度。因此控制方程包含连续相蒸汽和离散相液滴。

控制方程可表示为下式：

$$
\frac { \partial \rho _ { c } r _ { c } } { \partial \ t } + \frac { \partial } { \partial x _ { i } } ( \rho _ { c } u _ { i } r _ { c } ) = - \sum _ { i = 1 } ^ { n d } ( S _ { d } + m \ ^ { * } r _ { c } J _ { d } )
$$

上式为连续相质量方程的表达式，其中等号右边为源相，表示蒸汽形成的所有液滴的总质量。

而对离散相液滴的质量方程可用方程（2）表示。

$$
\frac { \partial \rho _ { d } r _ { d } } { \partial \mathrm { t } } + \frac { \partial } { \partial x _ { i } } ( \rho _ { d } u _ { i } r _ { d } ) = S _ { d } + m ^ { * } r _ { d } \mathrm { _ { } }
$$

对每一个液滴来说，其均对应一个质量方程，如式（3）所示。

$$
\frac { \partial \rho _ { d } N _ { d } } { \partial \mathrm { t } } + \frac { \partial } { \partial x _ { i } } \big ( \rho _ { d } u _ { i } N _ { d } \big ) = \rho _ { d } r _ { d } J _ { d }
$$

上述式中 $J _ { d }$ 表示成核率，表示单位体积的蒸汽在单位时间内形成的液滴数目， $r _ { c }$ 为蒸汽的体积分数，其与单个液滴体积分数 $r _ { \mathrm { d } }$ 的关系如下：

$$
r _ { c } + \sum _ { i = 1 } ^ { n d } r _ { d } = 1
$$

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

$m ^ { * }$ 为非平衡凝结过程中的质量生成率。在经典成核理论中，非平衡凝结过程中的质量生成率 $m ^ { * }$ 是由成核和液滴生长（或消亡）共同决定的[12]。它们的质量增加总和为质量生成率。因此 $m ^ { * }$ 可写为：

$$
m ^ { * } = { \frac { 4 } { 3 } } \pi \rho _ { l } J _ { d } r _ { * } ^ { 3 } + 4 \pi \rho _ { l } \eta \overline { { r } } ^ { 2 } { \frac { \partial \overline { { r } } } { \partial t } }
$$

式中 $\bar { r }$ 表示液滴平均半径， $\rho _ { l }$ 是液滴密度， $\boldsymbol { r } _ { * }$ 是液滴临界半径， $\eta$ 是单位体积内的液滴数目。

考虑到非等温效应的影响，采用了Kantrowitz对经典成核理论修正后的成核率 $J _ { d }$ 表达式[13]：

$$
J _ { d } = \frac { q _ { c } } { 1 + \theta } \Bigg ( \frac { \rho _ { c } ^ { 2 } } { \rho _ { l } } \Bigg ) \sqrt { \frac { 2 \sigma } { M _ { m } ^ { 3 } \pi } } e ^ { - \Bigg ( \frac { 4 \pi r _ { * } ^ { 2 } \sigma } { 3 k T } \Bigg ) }
$$

其中： $q _ { c }$ 是凝结系数（一般取值为1)， $k$ 是Boltzmann 常数， $M _ { m }$ 是单个水分子质量， $\sigma$ 是液滴表面张力， $\rho _ { l }$ 和 $\rho _ { c }$ 分别是液滴和蒸汽在温度 $T$ 下的密度， $\theta$ 是非等温修正系数，表达式如下：

$$
\theta \ = \ \frac { 2 ( \gamma - 1 ) h _ { c l } } { \gamma + 1 \ R T } \binom { h _ { c l } } { R T } - \frac { 1 } { 2 } \ /
$$

式中， $h _ { c l }$ 表示在压力 $p$ 下的相变潜热， $\gamma$ 代表比热容比。

在形成凝结核心后，核心小液滴和周围蒸汽不断发生传热传质。当液滴半径大于临界半径，液滴会生长；当液滴半径小于临界半径，液滴会蒸发[14]。临界半径的表达式为：

$$
r _ { * } = \frac { 2 \sigma } { \rho _ { l } R T l n S }
$$

上式中 $s$ 指过饱和度。过饱和度是气体实际压力和平衡相变时的饱和压力之比，表达式如下：

$$
\displaystyle { \cal S } = \frac { { \cal P } } { { \cal P } _ { s a t } ( T ) }
$$

其中， $P$ 为蒸汽压力， $P _ { s a t }$ 为该温度下水蒸汽饱和压力。

过冷度表征气体低于饱和温度的程度，表达式如下：

$$
\Delta T = T _ { s a t } - T
$$

液滴生长还涉及两个机理，第一个是从蒸汽凝结过程中的质量传递，第二个是以潜热的形式在液滴和蒸汽间进行的热传递。这种能量传递关系式，由J.B.Young 率先提出[15]，可写成：

$$
\frac { \partial \overline { { r } } } { \partial t } = \frac { P ~ \gamma + 1 } { h _ { c l } \rho _ { l } \sqrt { 2 \pi R T ~ 2 \gamma } } C _ { p } ( T _ { d } - T )
$$

其中 $T _ { d }$ 表示液滴温度。

在本文中，由于前文对所有相拥有共同的速度的假设，因此对动量方程只需要求解连续相（蒸汽）即可，中间相的动量变化用源相 $S _ { m }$ 表示。方程如下：

$$
\frac { \partial \big ( r \rho u _ { i } \big ) _ { c } } { \partial t } + \frac { \partial \big ( r \rho u _ { j } u _ { i } \big ) _ { c } } { \partial x _ { j } }
$$

$$
= - r _ { c } \frac { \partial p } { \partial x _ { i } } + \frac { \partial \left( r \tau _ { j i } \right) _ { c } } { \partial x _ { j } } - \sum _ { i = 1 } ^ { n d } S _ { m , d }
$$

对连续相的能量方程，本文以总焓的方式给出：

$$
\begin{array} { c } { { \displaystyle { \frac { \partial ( r \rho h ) _ { c } } { \partial t } } + \frac { \partial \left( r \rho u _ { j } h \right) _ { c } } { \partial x _ { j } } - r _ { c } \frac { \partial P } { \partial t } } } \\ { { = \displaystyle { \frac { \partial } { \partial x _ { j } } \Biggl ( r k _ { t } \frac { \partial T } { \partial x _ { j } } \Biggr ) _ { c } } + \frac { \partial \left( r \tau _ { j i } \right) _ { c } } { \partial x _ { j } } + \sum _ { i = 1 } ^ { n d } S _ { h , d } } } \end{array}
$$

上式中 $S _ { h }$ 包含了质量和传热的作用。根据Gyarmathy[16]所研究的内容表明，当液滴的直径小于1μm时，可采用式（14）来计算。

$$
T _ { d } = T _ { s a t } ( p ) - \Delta T  { \left( \frac { r ^ { * } } { r } \right) }
$$

# 2模型验证及分析

汽轮机静叶是一种特殊的喷嘴，由于难以测量，故其内部流动特性可以通过喷嘴来研究。本文通过研究MosesandStein喷嘴来验证两相流模型的正确性，为下小节的除湿计算奠定基础。

# 2.1MosesandStein喷嘴计算及结果分析

喷嘴的几何形状如图1所示。缩放喷嘴壁面是由两段圆弧组成，一段半径 $\scriptstyle R = 0 . 0 5 3$ m的亚音速区域，另一段半径 $R { = } 0 . 6 8 4 ~ \mathrm { ~ m ~ }$ 的超音速区，两段圆弧平滑连接。由公式 ${ \dot { \boldsymbol { e } } } _ { x } = - ( u / p ) ( d p / d x )$ ,可得出该喷嘴的膨胀率为8230 sec-1。缩放喷嘴的喉部位置$\scriptstyle x = 0 . 0 8 2 2$ m 处，喉部截面为 $1 0 \times 1 0$ mm的方形区域。

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

![](images/2eba3e434403d4ac1239f5246c719dab2a0cbabb510d5140d09a573f5cc69475.jpg)  
Fig.1 Geometry of the Moses and Stein Nozzle

Moses经行了多组编号的实验，本文选取了选取其中7组进行数值计算，其边界条件及测量数据见表1。

表1不同编号实验的边界条件及Wilson点参数  
Table 1 Boundary conditions and Wilson point parameter in different experimental numbers   

<html><body><table><tr><td colspan="2">进口条件</td><td colspan="3">Wilson点参数</td></tr><tr><td>No.</td><td>Po/kPa To/K</td><td>X/m</td><td>Pw/kPa Tw/K</td><td>Tsc/K</td></tr><tr><td>193</td><td>43.02</td><td>366.0</td><td>0.1074 15.25</td><td>285.9 41.566</td></tr><tr><td>226</td><td>41.42</td><td>380.0 0.1206</td><td>11.72</td><td>278.6 43.495</td></tr><tr><td>227</td><td>41.42</td><td>377.6 0.1179</td><td>12.30</td><td>280.3 42.775</td></tr><tr><td>228</td><td>41.42 375.6</td><td>0.1152</td><td>12.96</td><td>282.6 41.521</td></tr><tr><td>229</td><td>41.42 371.6</td><td>0.1130</td><td>13.51</td><td>283.0 41.962</td></tr><tr><td>230</td><td>41.42 370.9</td><td>0.1105</td><td>14.12</td><td>285.0 40.871</td></tr><tr><td>231</td><td>41.42</td><td>368.9 0.1090</td><td>14.49</td><td>285.4 41.008</td></tr></table></body></html>

网格数目对数值计算结果可靠性有很大影响，本文通过对不同数目的网格进行计算并与实验值进行了对比，网格无关性得以验证。最终网格如图2所示。

![](images/80e0045e27915ecc255bde839693d120f4bea70d7bc1b3c7858871e84c2373dc.jpg)  
图2模型网格  
Fig.2Mesh of model

本小节首先对No.193实验进行了数值计算并与实验测量值进行对比，如图3所示。

![](images/5606b1deb26c524d032f97cafc9ad4869f7364d6d10392d983f1aad10ab7c4c8.jpg)  
图1喷嘴几何结构  
图3压比分布

如图3所示，计算结果与实验值契合度良好，可以说明计算模型和方法的正确性。

为了解释蒸汽中液滴的形成过程，本文将喷嘴中心线上面的液滴的质量分数、过冷度、液滴数目、直径及成核率参数取出，如图4所示。

![](images/8c47a2e176a364136ddfce0da5af7bbb5e07958fd68c9fa3236fe0ab1316c31e.jpg)  
Fig.3Pressure ratio ditribution   
图4沿喷嘴中心线的液滴参数分布  
Fig.4Droplet parameters distribution along nozzle center line

喷嘴中心线上的液滴参数被取出，如图4所示。可以将上图分为3个区域，I区为喷嘴喉部之前，II区为喉部至Wilson点出现的位置，其余为III区域。为了更好的分析图4，先解释一下Wilson点，Wilson点由Wilson发现并提出[17]，其表示过冷度最大的点，而根据前文方程可知，过冷度最大，那么成核率也最大。在I区域，蒸汽到达喷嘴喉部之前一直处于膨胀状态，但由于蒸汽温度较高，过冷度较小，成核率低，只会产生少量数目的液滴，此时蒸汽湿度很小，并且从图4可知，蒸汽在低的过冷度时，并不会产生成核现象，当过冷度

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

达到约18K时，成核率才开始显著增加。携带少量液滴的蒸汽通过喉部进入II区域，继续膨胀，由于膨胀速率降低，导致其饱和温度变化很小，而液滴由于吸热半径减小，蒸汽温度降低，最终结果是蒸汽过冷度继续增加，直至最大点，即Wilson点，成核率和液滴数目都随着过冷度温度的增大而增大，但由于液滴直径的减小，蒸汽湿度几乎保持不变。进入II区域后，蒸汽膨胀率增大，饱和温度相应的减小速度增大，而Ⅱ区域产生的大量液滴其半径变大，释放液滴潜热导致蒸汽温度上升，过冷度减小，成核率减小，直至达到平衡状态。

为了更进一步验证数学模型和计算方法的可靠性，本文对多组编号实验进行了计算，并对其Wilson点出现的位置及相对应的过冷度进行了计算和对比，如图5所示。实验值Wilson点位置与计算值预测的Wilson点位置契合度很高，最大误差大概为 $2 . 5 \%$ ，预测是十分准确的。对于Wilson点处的过冷度，计算值与实验值相差不到4K，这也是可以接受的。

通过对Moses and Stein 喷嘴进行数值计算，并与实验结果进行了对比，分析了液滴形成的成因及影响因素，验证了数学模型及计算方法的正确性，为下一小节的除湿提供理论保障。

![](images/3659235dc1ec874858877bfab4e5f79e1dfe70ab123077941e2e14e37b626c99.jpg)  
图5不同实验编号过冷度的计算值与实验值 Fig.5 Compared of supercooling between simulation and experiment in different numbers

# 3．静叶除湿特性研究

# 3.1模型介绍

本小节研究了某型汽轮机的末级静叶，该级叶片总共有60个，本文只取其中一个流道进行计

算，轮毂和轮壳直径分别为 $7 6 2 \mathrm { m m }$ 和 $9 1 0 \mathrm { m m }$ ，其计算模型如图6所示。分别采用总压和总温进口（ $2 6 . 5 \ \mathrm { k P a }$ ，340.15K）和静压出口（ $6 . 6 2 \mathrm { k P a } )$ 。计算之前并对网格进行了无关性验证。

![](images/5362b5889b475bf413f5f1e59cd752570030b8524941526e7b6ccc2c9b25be73.jpg)  
图6计算模型

# 3.2计算结果分析

评判流道内湿度分布一般采用两个指标，一个是过冷度，因为液滴形成是由过冷度引起的，另一个是流道内的湿度，这是液滴形成所呈现的结果，因此本文从这两个特征入手，研究除湿方法。

图7和8给出了原形叶片 $50 \%$ 叶高上的过冷度分布及湿度分布。

![](images/f0f6b92b3ba9100fae49d41bc5fcc1258a3ec7a7fa8b80ff39d67fdc4b221633.jpg)  
Fig. 6 Model of computation   
图 $7 5 0 \%$ 叶高蒸汽过冷度分布Fig.7 Supercooling distribution at $50 \%$ span

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

# C hinaXiv合作期刊

![](images/0bc8373fd8f9d169eaed88db61a92662beba8bc434090aa81ebbbdca7f757017.jpg)  
图 $8 5 0 \%$ 叶高湿度分布

图7、8综合分析可知，过冷度最大的地方并非湿度最大的地方，而是在叶片流道的喉部之后附近过冷度最大，而湿度开始增大在喉部以后区域，与图4所述特点相吻合。

# 3.3除湿结构及计算结果分析

由3.2节分析可知，除湿可以有两种手段，一是降低过冷度从而降低成核率，达到除湿的目的；二是更直观的方法，直接将生成的湿度通过给其热量将其转变成蒸汽。本文主要研究第一种方法。

本文提出一种新型的除湿结构，见图9。通过将叶片前缘的高温蒸汽引射到成核率较大的区域，以达到除湿的目的。其中红色线为的叶片的中弧线，黑线前端点与中弧线相切，后短为过冷度最大的区域。d为所开通道的直径。本结构的优点在于不需要增加蒸汽量即可从根本上达到除湿的目的。

![](images/ce5f27ca720a130a8d30e2c4040632b21970cf84a53194315aab5d6d5630ad4f.jpg)  
Fig. 8 Mass fraction of $_ \mathrm { H } _ { 2 } \mathrm { O }$ at $50 \%$ span   
图9除湿结构图

其中红色线为的叶片的中弧线，黑线前端点与中弧线相切，后短为过冷度最大的区域。 $d$ 为所开通道的直径。

为了研究方便，将没有通道的叶片（原形叶片）的直径 $d$ 定义为0。本小节研究了5中不同通道直径结构的静叶，分别为 $1 \mathrm { m m }$ 、 $1 . 5 \mathrm { m m }$ 、 $2 \mathrm { m m }$ 、$2 . 5 \mathrm { m m }$ 、 $3 \mathrm { m m }$ 。对以上五种不同通道直径的模型进行计算，其湿度变化及湿汽损失如图10所示。

![](images/27daabbe924d3fd1fb780536bf5f331b4250a0a9d86987eaa547b8bf31c56326.jpg)  
Fig.9 The structure of dehumidification   
图10湿汽损失、湿度与通流直径的关系  
Fig.10 Wetness loss and Mass fraction for different diameters

由图10可以明显的看出，随着通流直径的增大，湿汽损失减小，湿度降低。 $3 \mathrm { m m }$ 通流直径时的湿度降低了近 $0 . 0 1 \%$ ，虽然看似不高，但是随着通

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

流流道数目的增加，必然会再使湿度有可观的降低。

# 4结论

针对汽轮机末级湿蒸汽形成这一现象，分析了湿蒸汽形成和流动的控制方程，并对已有实验数据的喷嘴进行了数值计算，分析了湿蒸汽形成的整个过程，验证了模型及方法的可靠性。最后对某汽轮机静叶进行计算分析，并提出一种新型除湿结构，计算了除湿效果。结果表明：经典成核理论和液滴生长模型能很好的描述蒸汽自发凝结的相变过程。当蒸汽过冷度达到约18K时，成核率才显著增加。成核率最大的位置在喷嘴喉部之后。除湿结构能从根本上达到除湿的目的，并且随着通流直径的增大，除湿效果增强，湿汽损失减小。

# 参考文献

[1] Stodola A. Steam and Gas Turbines [M].New York: McGraw-Hill, 1927:75-83   
[2] Wilson C T R. Investigation of X-Rays and $\beta$ -Ray by the Cloud Method Part II- $\cdot \beta$ -Rays [J]. Proceedings of the Royal Society ofLondon,1923,104:192-212   
[3] Yellott J I. Supersaturated Steam [J]. Transaction of the ASME,1934,56:411-430   
[4] Rettaliata JT .Undercooling in Steam Nozzles [J]. Transaction of the ASME,1936,58:599-605   
[5] Yellott JI，Holland C K. The Condensation of Flowing Steam Part I - Condensation in Diverging Nozzles [J]. Transactionof the ASME,1937,59:171-183   
[6] Bakhtar F.Nucleation phenomena in flowing high - pressure steam:experimental results[J]. Proceedings of the Institution of Mechanical Engineers,1989,203(A3): 195-200   
[7] Bakhtar F, Zidi K.Nucleation phenomena in flowing high pressure steam Part 2: theoretical analysis[J]. Proceedings of the Institution of Mechanical Engineers,1990,.204(A4): 233-242 [8] Gerber A G.Two-Phase Eulerian/Lagrangian Model for Nucleating Steam Flow[J]. Journal of Fluids Engineering, 2002,124(2):465-475   
[9] Gerber A G,Kermani M J.A pressure based EulerianEulerian multi-phase model for non-equilibrium condensation in transonic steam flow[J].International Journal of Heat and Mass Transfer,2004,47(10-11): 2217-2231   
[10] Moore M J,Sieverding C H.Two-phase steam flow in turbines and separators [M]. London: Hemisphere Publishing Corporation, 1976:245-268   
[11]丰镇平，李亮，李国君.汽轮机湿蒸汽两相凝结流动数 值研究的现状与进展[J].上海汽轮机,2002,6(2)1-10   
FENG Zhenping,LI Liang,LI Guojun. The status and progress of numerical research on flow condensation wet steam turbine [J]. Shanghai Turbine,2002,6 (2):1-10   
[12]Ishazaki K,Ikohagi T,Daiguji H. A High-Resolution Numerical Method for Transonic Non-equilibrium Condensation Flows Through a Steam Turbine Cascade [C].In Proceedings of the 6th International Symposium on Computational Fluid Dynamics,1995,1:479-484   
[13] Young JB. Two-Dimensional Nonequilibrium Wet-Steam Calculations for Nozzles and Turbine Cascades [J]. Journal of Turbomachinery.1992,114(3):569-579   
[14] Grubel M, Starzmann J,Schatz M,et al. Two-Phase Flow Modeling and Measurements in Low-Pressure Turbines-Part I: Numerical Validation of Wet Steam Models and Turbine Modeling [J]. Journal of Engineering for Gas Turbines & Power, 2014,137(4):042602   
[15] Young JB. The Spontaneous Condensation of Steam in Supersonic Nozzle [J]. Physico Chemical Hydrodynamics,1982, 3(2):57-82   
[16]Gyarmathy G. Grundlagen einer Theorie derNaβ dampfturine [D].Germany,1962   
[17]张冬阳.非平衡态湿蒸汽流动快速准确数值模拟方法研 究[D].中国科学院工程热物理研究所,2002   
ZHANG Dongyang.A fast and accurate numerical simulation method for nonequilibrium wet steam flow[D]. Chinese AcademyofSciences:Instituteofengineeringthermal physics,2002

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

# 附页：

作者简介：张国杰（ $1 9 8 9 - )$ ，男，博士研究生，主要从事透平机械内部流动的研究通讯作者：李意民，教授，liyimin@cumt.edu.cn

主要联系人：张国杰  
电话：18361220182  
邮箱：zhangguojie2015@cumt.edu.cn  
联系地址：江苏省徐州市中国矿业大学南湖校区机电楼A333  
邮编：221116

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538