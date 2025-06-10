# 喷射泵诱导时均非对称压降的机理分析

汤珂1²，封叶¹，金滔²，吴云翔‘（1.浙江大学制冷与低温研究所，杭州310027；2.浙江大学能源清洁利用国家重点实验室，杭州310027)

摘要：可诱导非对称压降的喷射泵被引入热声发动机的环路结构中，可以用于抑制Gedeon 流，进而提高热声发动机热效率。针对 Swift对喷射泵提供时均非对称压降的理论推导结论与Idelchik 等人报道的实验结果之间存在的矛盾，本文利用计算流体力学软件，研究了喷射泵的厚径比 $l / d _ { \mathrm { e } }$ 对时均非对称压降的影响情况。结果表明，改变厚径比 $l / d _ { \mathrm { e } }$ 会引起时均非对称压降方向的变化，在喷射泵设计中，除了应该考虑喷射泵流道两端面积不相同所带来的影响，还必须合理选择其厚径比 $l / d _ { \mathrm { e } } ^ { } ,$ 0

关键词：喷射泵；Gedeon流；交变流动；非对称压降中图分类号：TB511 文献标识码：A

# Analysis of Time-averaged Pressure Drop Induced by Jet Pump

TANG Ke1,2 FENG Ye’ JIN Ta01,2 WU Yunxiang (1. Institute of Refrigeration and Cryogenics, Zhejiang University, Hangzhou 31o027, China; 2. State Key Laboratoryof Clean Energy Utilization,Zhejiang University, Hangzhou 310027,China)

Abstract: Gedeon streaming，which may considerably deteriorate the thermal eficiency of a traveling-wave thermoacoustic engine,can be suppressed by inducing a jet pump into the loop configuration.The contradiction of the time-averaged pressure drop between Swift's theoretical derivation and Idelchik's experimental results, motivated us to study the effect of the jet pump's thickness-to-diameter ratio $l / d _ { \mathrm { e } }$ on the time-averaged asymmetric pressure drop by meansof computational fluid dynamics.The resultsindicate the variation in thickness-to-diameter ratio $l / d _ { \mathrm { e } }$ can change the direction of the time-averaged pressure drop induced by the jet pump,consequently,the designing of a jet pump needs to focus not only on the asymmetry of opening areas of both ends,but also on the thickness-to-diameter ratio $l / d _ { \mathrm { e } }$ ，

Key words: jet pump; Gedeon streaming; oscillating flow; time-averaged pressure drop

# 0引言

热声发动机由于具有无机械运动部件、结构简单、运行可靠、寿命长等特点而受到人们的广泛关注。行波热声发动机因其热声转换热力循环本征可逆[1]，理论上的效率高于驻波热声发动机，使其具有较大的应用潜力和发展前景。Swift等人研制的具有反馈环路的热声斯特林发动机[2.3]，是行波热声发动机的典型代表，热效率可达0.3，引发了近年来关于行波热声发动机的研究热潮[4-7]。

但是，反馈环路的引入会在热声发动机中形成闭合环路，这就可能导致Gedeon流的发生[8]。所谓Gedeon流是沿环路循环流动的时均流，或者称为声直流。Gedeon流可将热量直接从热端换热器传递至冷端换热器而不参与热声转换过程，是一种严重的热损失机制，其成为影响热声斯特林发动机热效率的一个重要因素。

Swift 等人采用喷射泵[2.3]对Gedeon 流进行抑制。利用两端流通面积不相等的锥形槽结构，使热声发动机中交变运动的流体在前后两个半周期内流经喷射泵时，产生时均非对称压降，进而起到抑制环路中Gedeon流的作用。Swift等人推导的相关计算公式中时均非对称压降方向为从喷射泵的大截面到小截面的方向，表明流体从喷射泵的大截面到小截面流动的压降大于反向流动的压降。

Idelchik等人[9研究了在稳定流动的情况下流体分别以相反方向流经非对称孔板时产生的压降情况。该非对称孔板与喷射泵具有相似结构，区别在于Idelchik等人报道的实验研究的孔板为圆孔而非矩形窄槽，且孔板的厚度与小孔的直径之比为$l / d { = } 0 { \sim } 0 . 0 1 5$ 。实验结果表明，流体从小截面到大截面流动的压降大于反向流动时的压降。

Swift在研究喷射泵工作机理时，只考虑了窄槽流道两端的流通面积和边沿形状不同这两个因素所造成的非对称压降，而忽略了喷射泵厚度的影响，这可能是导致其推导结论与Idelchik等人报道的实验结果相矛盾的原因。

基于上述分析，本文参考Swift 喷射泵模型，以窄槽型喷射泵作为研究对象，利用数值模拟方法，研究了不同流量下厚径比 $l / d _ { \mathrm { e } }$ 对非对称压降的影响，以获得适宜的二阶时均流阻且保持较小的一阶交变流阻，达到高效低损抑制Gedeon流的目的。

# 1计算方法的验证

参考 Swift等人[2.3]的研究思路，将交变流动处理为沿流道轴向的两个相反方向的稳定流动。研究在稳定流动条件下，喷射泵厚径比 $l / d _ { \mathrm { e } }$ 对时均非对称压降的影响。采用三维定常不可压缩雷诺时均N-S方程。由于Realizablek-ε模型能描述包含有射流和混合流的自由流动、管道内流动、边界层流动等不同类型的流动[10],因此在模拟中选择Realizablek-ε (RKE)模型。考虑到在喷射泵的入口和出口存在较大的压力梯度，压力的插值方法选用PRESTO。壁面设为绝热边界条件，流体工质为He。连续性方程、动量方程、能量方程均采用二阶迎风离散格式，计算时认为流体在管道进出口的流量差为 $0 . 1 \%$ 时即达到收敛。为了准确模拟喷射泵周围的涡流信息，对喷射泵以及邻近直管段进行了加密处理。

为了验证计算方法的正确性，以非对称孔板为研究对象[9],对流体的串流阻力系数 $k$ 进行了计算，并将计算结果与Idelchik等人报道的实验结果进行比较。 $k$ 表征流体流经非对称孔板产生的压力损失，可用式（1）计算：

$$
k = \Delta p \bigg / \frac { \rho \nu ^ { 2 } } { 2 }
$$

式中， $\Delta p$ 为流体流经非对称孔板的全压损失。该损失包括小截面处的截面突变引起的局部阻力损失、渐变管引起的摩擦损失、渐变管引起的扩散损失以及大截面处的截面突变引起的局部阻力损失四部分。 $\rho$ 为流体的密度， $ { \boldsymbol \nu }$ 为管道内流速。

表1列出了流体从非对称孔板的大截面到小截面的串流阻力系数 $k$ 的计算结果与实验结果的比较情况，其中管道面积与非对称孔板的小截面的面积比 $A / a _ { \mathrm { s } }$ 为0.02，0.04，0.06。管道内流速 $\nu$ 为 $2 \mathrm { m / s }$ 。从表1可看出，计算结果与实验结果的误差在 $7 \%$ 以内，可见该计算结果能够合理反映实验结果。

表1串流阻力系数 $k$ 的模拟结果与实验结果比较  
Table 1 Comparison of simulation results and experimental data for the resistance coefficient $k$   

<html><body><table><tr><td>面积比</td><td>0.02</td><td>0.04</td><td>0.06</td></tr><tr><td>实验值k</td><td>5157</td><td>1241.25</td><td>534</td></tr><tr><td>模拟值k</td><td>4830</td><td>1163.07</td><td>504.61</td></tr><tr><td>误差</td><td>-6.3%</td><td>-6.29%</td><td>-5.5%</td></tr></table></body></html>

# 2 计算参数选择

Swift等人认为时均非对称压降仅由于窄槽流道两端的流通面积和边沿形状的不同引起。本文为了消除以上两个因素对时均非对称压降的影响，研究在喷射泵两端的流通面积不变以及边缘均不倒圆角的情况下，厚径比 $l / d _ { \mathrm { e } }$ 对时均非对称压降的影响，并在此基础上提出合适的 $l / d _ { \mathrm { e } }$ ，以实现在提供合适的时均非对称压降的同时使压损保持较小的值。

采用的物理模型其管道内径为 $6 0 \mathrm { m m }$ ，喷射泵的结构参考 Swift之前的喷射泵模型[2.3]，以窄槽型的喷射泵作为研究对象，其小截面的面积为 $ { a _ { \mathrm { s } } } { = } 1 . 8$ $\mathrm { c m } ^ { 2 }$ ，大截面的面积为 $a _ { \mathrm { b } } { = } 3 . 0 \ \mathrm { c m } ^ { 2 }$ ，见图1。计算采用的工作压力为 $3 \ \mathrm { M P a }$ ，温度为 $3 0 0 ~ \mathrm { K }$ ，研究了流速为 $2 ~ \mathrm { m / s }$ ， $3 ~ \mathrm { m / s }$ ， $4 ~ \mathrm { m / s }$ 的情况下，改变 $l / d _ { \mathrm { e } }$ 对时均非对称压降的影响， $d _ { \mathrm { e } }$ 为喷射泵的小截面的当量直径。 $l / d _ { \mathrm { e } }$ 的选择：0.2、0.5、1.0、1.5、2.0、3.0、4.5、5.5、6.5、7.0、7.5、9.0、10.0。

H

# 3计算结果

为了便于分析，提出了时均非对称阻力系数$\Delta k$ 、时均总阻力系数 $k _ { \mathrm { t } }$ 和有效系数 $\boldsymbol { \varepsilon }$ 等三个参数用于表征喷射泵的性能。 $\Delta k$ 表征流体流经喷射泵产生的时均非对称压降， $k _ { \mathrm { t } }$ 表征流体流经喷射泵时产生的时均总压力损失， $\boldsymbol { \varepsilon }$ 表征流体流经喷射泵时单位时均总压力损失产生的时均非对称压降。它们的定义式如下

$$
\begin{array} { r l r } {  { \Delta k = \frac { \displaystyle \int _ { 0 } ^ { T / 2 } \Delta p _ { + } \mathrm { d } t - \int _ { T / 2 } ^ { T } \Delta p _ { - } \mathrm { d } t } { \displaystyle \int _ { 0 } ^ { T / 2 } \frac { \rho { \nu _ { + } } ^ { 2 } } { 2 } \mathrm { d } t + \int _ { T / 2 } ^ { T } \frac { \rho { \nu _ { - } } ^ { 2 } } { 2 } \mathrm { d } t } , } } \end{array}
$$

$$
k _ { \mathrm { t } } = \frac { \displaystyle \int _ { 0 } ^ { T / 2 } \Delta p _ { + } \mathrm { d } t + \int _ { T / 2 } ^ { T } \Delta p _ { - } \mathrm { d } t } { \displaystyle \int _ { 0 } ^ { T / 2 } \frac { \rho \nu _ { + } ^ { ~ 2 } } { 2 } \mathrm { d } t + \int _ { T / 2 } ^ { T } \frac { \rho \nu _ { - } ^ { ~ 2 } } { 2 } \mathrm { d } t } ~ ,
$$

$$
\varepsilon = \frac { \Delta k } { k _ { \mathrm { t } } }
$$

式中， $T$ 为周期，下标 $^ +$ ，-代表两个相反的流动， $^ +$ 表示流体从小截面流向大截面，-表示流体从大截面流向小截面。

图2为流体从喷射泵的小截面到大截面方向流动的串流阻力系数 $k _ { + }$ 的值随 $l / d _ { \mathrm { e } }$ 的变化。图3为流体从喷射泵的大截面到小截面方向流动的串流阻力系数 $k _ { - }$ 的值随厚径比 $l / d _ { \mathrm { e } }$ 的变化。

从图2可以看出，从喷射泵的小截面到大截面流动的串流阻力系数 $k _ { + }$ 随厚径比 $l / d _ { \mathrm { e } }$ 的增大而逐渐减小，压力损失减少。厚径比 $l / d _ { \mathrm { e } }$ 为 $5 . 5 { \sim } 1 0 . 0$ 时，变化趋势逐渐平缓，随着厚径比 $l / d _ { \mathrm { e } }$ 进一步增大,压降有略微上升趋势。从图3可以看出，喷射泵的大截面到小截面的串流阻力系数 $k _ { - }$ 的变化趋势与串流阻力系数 $k _ { + }$ 的变化趋势相似，但 $k _ { - }$ 的变化较 $k _ { + }$ 的变化略小。当厚径比 $l / d _ { \mathrm { e } }$ 大于3.0时，出现一段比较平缓的曲线，厚径比 $l / d _ { \mathrm { e } }$ 的增大对串流阻力系数 $k _ { - }$ 的影响较小。

![](images/36a2372482b74ebdd3d775013a66a38615dca08edb079f7b0a4e94e4fc44b4f6.jpg)  
图2串流阻力系数 $k _ { + }$ 随 $l / d _ { \mathrm { e } }$ 的变化 Fig.2 Variation in coefficient of resistance $k _ { + }$ with $l / d _ { \mathrm { e } }$

![](images/34251496ef94639fee46913f852a6274659be9db99e8c94b01e7f5b8ba6a9271.jpg)  
图3串流阻力系数 $k _ { - }$ 随 $l / d _ { \mathrm { e } }$ 的变化 Fig.3 Variation in coefficient of resistance $k _ { - }$ with $l / d _ { \mathrm { e } }$

图4和图5显示了流速为 $2 \ \mathrm { m / s }$ ，厚径比 $l / d _ { \mathrm { e } }$ 分别为0.2，2.0，5.5时流体流过喷射泵的速度分布情况。图4为从喷射泵的小截面到大截面流动的速度分布图，图5为从喷射泵的大截面到小截面流动的速度分布图。

从图4中可以看出，对于从喷射泵的小截面向大截面的流动，由于流体受到小截面的约束，会出现向中间收缩的情况。喷射泵阻挡流动，迫使流体质点向孔口加速，流体流速增加，静压力降低。流束进入小截面后在惯性力作用下继续收缩，但径向惯性力逐渐减小直至与扩张力平衡，这时流束的横

![](images/31ad3e86a237affcdb3647bdc4d2dcf66a8a58acbc94246e73e27da9f312ed54.jpg)  
图4不同 $l / d _ { \mathrm { e } }$ 下从小截面到大截面流动的速度分布图(a) $l / d _ { \mathrm { e } } { = } 0 . 2$ (b) $l / d _ { \mathrm { e } } { = } 2 . 0$ (c) $l / d _ { \mathrm { e } } { = } 5 . 5$

Fig. 4 Velocity distribution in flow from small opening to big opening under various $l / d _ { \mathrm { e } }$

(a) $l / d _ { \mathrm { e } } { = } 0 . 2$ (b) $l / d _ { \mathrm { e } } { = } 2 . 0$ （204号 (c) $l / d _ { \mathrm { e } } { = } 5 . 5$

![](images/f9b3e84b23ccbe9f94c16062464b76c1bdcb511e6f7f10f6a9290a756474f340.jpg)

截面积达到最小，流速增加到最大，静压降到最低。  
此后，流束扩大，速度降低，直至流束充满管道。

在 $l / d _ { \mathrm { e } }$ 较小的情况下，由于截面突缩带来的流束收缩有一定影响长度，在计算出口膨胀的压力损失时，必须考虑在边壁突变的附近出现的主流与边壁脱离的现象。 $l / d _ { \mathrm { e } }$ 为5.5时，实际流束面积接近于出口壁面面积，主流与边壁脱离的影响减小。这时串流阻力系数 $k _ { + }$ 的波动，主要由喷射泵内部摩擦损失与扩散损失随厚度的变化所引起。

从图5中可以看出，流体从喷射泵的大截面到小截面流动时，由于截面为渐缩，流体质点受到与流动方向一致的正压差作用，只会导致加速，不会出现主流与边壁脱离的现象。

从模拟结果可以看出，管道内流速的改变对串流阻力系数的影响较小。本文将交变流动处理为沿流道轴向的两个相反方向的稳定流动，假定前后半个周期的流速大小不变。因此，定义式（2）和（3)可简化为

$$
\Delta k = \frac { \Delta p _ { + } - \Delta p _ { - } } { 2 } \bigg / \frac { \rho \nu ^ { 2 } } { 2 } = \frac { k _ { + } - k _ { - } } { 2 }
$$

$$
k _ { \mathrm { t } } { = } \frac { \Delta p _ { + } + \Delta p _ { - } } { 2 } \Bigg / \frac { \rho \nu ^ { 2 } } { 2 } { = } \frac { k _ { + } + k _ { - } } { 2 }
$$

图6为时均非对称阻力系数 $\Delta k$ 随 $l / d _ { \mathrm { e } }$ 的变化。从图中可以看出， $l / d _ { \mathrm { e } }$ 较小时，流体从喷射泵的小截面流向大截面时的压降大于反向流动的压降，这与Idelchik等人报道的实验结果一致。随着 $l / d _ { \mathrm { e } }$ 的增加，流体从喷射泵的小截面流向大截面的压降迅速降低，而反向流动的压降减小相对较慢， $\Delta k$ 随之减小；当/d进一步增大，流体从喷射泵的小截面流向大截面的压降最终小于反向流动压降，此时 $\Delta k$ 变为负数。Swift理论模型关于喷射泵时均非对称压降的方向预测与 $\Delta k$ 变为负数时的情况一致，而与$\Delta k$ 为正数时的情况相反。究其原因，主要在于Swift等人在进行理论分析时，忽略了两个突变截面局部阻力间的相互影响。

![](images/eb0ed001722a3c2f21d24e73e796a20ca0ab9daac3de1d3cdf5a9808a7b16f0e.jpg)  
图5不同 $l / d _ { \mathrm { e } }$ 下从大截面到小截面流动的速度分布图 (a) $l / d _ { \mathrm { e } } { = } 0 . 2$ (b) $l / d _ { \mathrm { e } } { = } 2 . 0$ (c) $l / d _ { \mathrm { e } } { = } 5 . 5$ Fig.5 Velocity distribution in flow from big opening to small opening under various $l / d _ { \mathrm { e } }$ （204号 (a) $l / d _ { \mathrm { e } } { = } 0 . 2$ (b) $l / d _ { \mathrm { e } } { = } 2 . 0$ (c) $l / d _ { \mathrm { e } } { = } 5 . 5$   
图6时均非对称阻力系数 $\Delta k$ 随 $l / d _ { \mathrm { e } }$ 的变化 Fig.6 Variation in coefficient of time-averaged resistance $\Delta k$ with $l / d _ { \mathrm { e } }$ （204号

图7为时均总阻力系数 $k _ { \mathrm { t } }$ 的变化情况，其随着$l / d _ { \mathrm { e } }$ 增大而降低，之后变化趋缓，随着 $l / d _ { \mathrm { e } }$ 进一步增大，总压力损失略微上升。

图8为有效系数 $\boldsymbol { \varepsilon }$ 的示意图，为了实现高效低损的抑制直流， $\boldsymbol { \varepsilon }$ 的值应尽可能大。从图中可以看出，在 $l / d _ { \mathrm { e } }$ 较小时， $\boldsymbol { \varepsilon }$ 随 $l / d _ { \mathrm { e } }$ 的增大呈现先减小后增大的趋势，在一定的 $l / d _ { \mathrm { e } }$ 下出现极小值。

![](images/4179d54bf365ec0abd578bcdc74504fe5bb5cc1a64864f763e19d8fb4c50b162.jpg)  
图7时均总阻力系数 $k _ { \mathrm { t } }$ 随 $l / d _ { \mathrm { e } }$ 的变化 Fig.7 Variation in coefficient of overall resistance $k _ { \mathrm { t } }$ with $l / d _ { \mathrm { e } }$

![](images/286c91cff8eb43f7a831d5b324c868050c2f68aa5d5f4f55eb4a7f3f400a98bf.jpg)  
图8有效系数 $\boldsymbol { \varepsilon }$ 随 $l / d _ { \mathrm { e } }$ 的变化  
Fig.8 Variation in coefficient of effectiveness $\varepsilon$ with $l / d _ { \mathrm { e } }$

由图8中可以看出，在 $l / d _ { \mathrm { e } }$ 较小或者较大的情况下， $\boldsymbol { \varepsilon }$ 较大，可提供较大的时均非对称压降；但$l / d _ { \mathrm { e } }$ 较小时，时均总阻力损失很大。因此，在设计喷射泵时，可以优先考虑选择较大的 $l / d _ { \mathrm { e } }$ ，这样既可在提供合适的非对称压降的同时使压损较小。

通过模拟计算，在管内压力 $3 \ \mathrm { M P a }$ ，小截面的面积 $a _ { \mathrm { s } } { = } 1 . 8 ~ \mathrm { c m } ^ { 2 }$ ，大截面的面积为 $a _ { \mathrm { b } } { = } 3 . 0 \ \mathrm { c m } ^ { 2 }$ 的工况下，喷射泵的厚径比 $l / d _ { \mathrm { e } }$ 在 $7 . 0 { \sim } 1 0 . 0 \$ 的范围内时，流体以两个相反方向流经喷射泵的时均总阻力损失最小，且可得到较大的时均非对称压降，可被视为比较合适的 $l / d _ { \mathrm { e } }$ 范围。

# 4结论

针对Swift 对喷射泵提供时均非对称压降的理论推导结论与Idelchik等人报道的实验结果的矛盾，研究了在不同流速的条件下，流体在流经喷射泵时，改变厚径比 $l / d _ { \mathrm { e } }$ 对时均非对称压降的影响。

结果表明，当厚径比 $l / d _ { \mathrm { e } }$ 较小时，流体从喷射泵的小截面流向大截面的流动会发生主流与边壁脱离的现象，导致其压降远大于理论计算值，并大于沿相反方向流动的压降，时均非对称压降的方向为从喷射泵的小截面到大截面的方向，其结果与Swift等人理论模型的推导结果相矛盾。随着 $l / d _ { \mathrm { e } }$ 的增加，流体从喷射泵的小截面流向大截面的压降迅速降低，最终小于反向流动压降，时均非对称压降的方向为从喷射泵的大截面到小截面的方向，这与Swift理论推导的结论一致。厚径比 $l / d _ { \mathrm { e } }$ 改变，使时均非对称压降的方向发生变化。因此，在设计喷射泵时，必须综合考虑两端面面积和厚径比 $l / d _ { \mathrm { e } }$ 的影响，否则可能会导致喷射泵的设计不合理，不仅不能抑制直流，甚至会在一定程度加剧环路中的直流。

# 参考文献

[1]Ceperley P H.A Pistonless Stirling Engine—the Traveling Wave Heat Engine[J]. Journal of the Acoustical Society of America, 1979, 66(5): 1508--1513   
[2] Backhaus S, Swift G W.A Thermoacoustic Stirling Heat Engine[J]. Nature,1999,399: 335--338   
[3] Backhaus S, Swift G W. A Thermoacoustic-Stirling Heat Engine: Detailed Study[J]. Journal of the Acoustical Society of America, 2000, 107(6): 3148--3166   
[4]Yu G, Luo E,Dai W,et al. An Energy-Focused Thermoacoustic-Stirling Heat Engine Reaching a High Pressure Ratio Above 1.40[J]. Cryogenics, 2007,47(2): 132--137   
[5]Jin T, Mao C, Tang K, et al. Characteristics Study on the Oscillation Onset And Damping of a Traveling-Wave Thermoacoustic Prime Mover[J]. Journal of Zhejiang University (Science A), 2008,9(7): 944--949   
[6]Tijani M E H,Spoelstra S.A High Performance Thermoacoustic Engine[J]. Journal of Applied Physics, 2011,110(9): 093519   
[7]deBlokK.Novel4-StageTravelingWave Thermoacoustic Power Generator[C]/ In ASME 2010 3rd Joint US-European Fluids Engineering Summer Meeting collocatedwith8th International Conferenceon Nanochannels,Microchannels，andMinichannels, American Society of Mechanical Engineers,2012: 73--79   
[8] Gedeon D.DC Gas Flows in Stirling and Pulse Tube Cryocoolers. Cryocoolers 9[M]. New York: Plenum Press, 1997: 385--392   
[9]Idelchik I E.Handbook of Hydraulic Resistance,3rd ed[M].New York:Begell House,1996:170--172   
[10]Fluent 6.1 User's Guide Fluent Inc.,Lebanon,NH,2001