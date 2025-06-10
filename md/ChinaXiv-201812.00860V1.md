# SF断路器弧前因素对电弧形成过程的影响研究

李　静王奥飞¹樊小敏² 陈洋1（1.沈阳工业大学电气工程学院沈阳 1108702.华仪电气股份有限公司乐清325600）

李静女1977年生，博士，讲师，研究方向为电器及其控制。

摘要：本文以实际 ${ \mathrm { S F } } _ { 6 }$ 断路器灭弧室结构为计算模型，采用气体动力学方程，从微观角度出发，考虑粒子间的碰撞反应，探求液态金属桥断裂后稳态电弧生成前、触头开距为 $3 \mathrm { m m }$ 时，电弧等离子体粒子群的产生、发展及演变规律，分析研究了不同开断电流导致的金属蒸气含量变化对电弧弧前过程中等离子体微观参数的影响；同时研究了不同电极材料造成的二次电子发射系数差异对 ${ \mathrm { S F } } _ { 6 }$ 电弧弧前过程的影响。仿真为稳态电弧研究提供基础理论数据，对于高压开关设备的开发研制具有一定意义。

关键词： ${ \mathrm { S F } } _ { 6 }$ 断路器 电弧微观 弧前过程中图分类号：TM561.3

# Study on the Influence of Arc Before Factors on the Arc Forming Process of $\mathbf { S F _ { 6 } }$ Circuit Breaker

Li Jing'Wang Aofei'Fan Xiaomin² Chen Yang1 (1. Shenyang University of TechnologyShenyang 110870 China 2.Huayi Electric Co.Ltd. Yueqing 325600 China ）

![](images/d0531037bdc7428195104d78193f145555da7c3ac8676f3a2ca69e55d01001a3.jpg)  
收稿日期：2018-06-24

![](images/8293588b30dcae389b4b8ebffaac365f150f5cc17fb40c7cf1e07e64ef563ab5.jpg)

王奥飞男1992年生，硕士研究生，研究方向为电机与电器。

Abstract: An actual ${ \mathrm { S F } } _ { 6 }$ circuit breaker chamber is adopted as the model in this paper. By gas dynamic equations and collisions between charged particles,the generation, development and variation processes of arc plasma at the break of $3 \mathrm { m m }$ are studied from a microscopic view before the breaking of liquid metal bridge and stable arc formation. Effects of the content of metal vapor produced by high breaking current and secondary electron emission coefficient produced by different electrode materials on the microscopic parameters of arc plasma in arc before process are studied here.This simulation can provide the basic theory data for the steady-state arc research,and has certain significance for the development of high voltage switchgear.

Keywords: ${ \mathrm { S F } } _ { 6 }$ circuit breaker, arc,microscopic,arc before process

# 1 引言

随着电力需求的持续稳步增加，电力系统输电等级的提升对高压断路器的开断能力提出了更高的要求[1]。断路器在开断过程中不可避免地要产生电弧，在稳定电弧形成之前的过程，称为弧前过程。理论研究表明，弧前过程为电弧等离子体的发展提供了初始路径，影响了稳态电弧的能量。高温电弧可分为阴极区、弧柱区和阳极区，其中阴极区的阴极表面、空间电荷（鞘层）以及电离层（预鞘层），是电弧产生存在的基础，也是研究零后电弧重燃过程的前提条件[2]。其形成是在电弧稳定燃烧前期，即弧前过程中产生。

弧前过程包括金属相电弧和气体相电弧两个阶段，两个相态参与电弧过程的粒子成分发生了改变[3]。目前对于弧前过程的物理机理认识尚不完善，对电弧模型的研究主要集中在稳态电弧模型及弧后过程。20 世纪70年代末，K.P.Brand 和J.Kopainsky开展了标准大气压下 ${ \mathrm { S F } } _ { 6 }$ 电弧等离子体粒子组分的研究，其中原子的多级电离被忽略，只考虑一级电离反应[4]。文献[5]将气压范围拓展到10个大气压，并将硫原子的二级电离反应纳入模型，计算精度得到了提高。文献[6]在研究 ${ \mathrm { S F } } _ { 6 }$ 电弧等离子体时，考虑了铜蒸气的影响，发展了 $\mathrm { S F } _ { 6 } – \mathrm { C u }$ 混合气体粒子组分模型。文献[7]通过仿真得到直流低压空气电弧非平衡态燃弧过程中触头间隙的微观带电粒子密度、平均电子能量等各项微观物理量的动态变化规律，并分析了触头间空气电弧非平衡态燃弧过程及触头间电压对空气电弧形成过程的影响。而对于 ${ \mathrm { S F } } _ { 6 }$ 电弧弧前微观动态过程的研究相对较少，研究 ${ \mathrm { S F } } _ { 6 }$ 断路器电弧的微观动态形成过程及弧前因素的影响，对深入了解电弧形成机制，丰富完善电器电弧理论，提出新式灭弧方法意义重大。

本文以气体动力学模型为基础，考虑了电子、正负离子漂移扩散方程、微观粒子的碰撞方程及电场的泊松方程，基于实际 ${ \mathrm { S F } } _ { 6 }$ 断路器结构，建立了开距为 $3 \mathrm { m m }$ 时二维对称的 ${ \mathrm { S F } } _ { 6 }$ 断路器的几何模型，并利用多物理场耦合仿真计算软件COMSOLMultiphysics对上述模型进行求解，分析了大电流开断条件下 ${ \mathrm { S F } } _ { 6 }$ 断路器弧前过程中的电子密度、电场强度、平均电子能量及碰撞能量损失分布等各项微观参数的时变规律，并分析了大开断电流导致的金属蒸气含量变化及触头材料造成的二次电子发射系数差异对电弧弧前过程中微观参数的影响。

# 2 弧前因素仿真模型

# 2.1灭弧室简化模型

由于整个放电过程具有较好的轴对称性，因此本文采用的 ${ \mathrm { S F } } _ { 6 }$ 断路器灭弧室二维简化模型的几何结构如图1所示，主要由触头、触指和喷口组成。其中触头半径 $1 1 . 5 \mathrm { m m }$ ，触指内径 $1 1 . 5 \mathrm { m m }$ ，外径$3 8 . 5 \mathrm { m m }$ ，触头开距 $3 \mathrm { m m }$ 。

![](images/5ed93f7881c060a3e61e478ca2ff38929d2910c482d2aaeb834a5c51b770ae34.jpg)  
图1灭弧室简化模型  
Fig.1Simplified model of interrupter 1—阴极2—喷口3—采样截线 4- ${ \cdot } \mathrm { S F } _ { 6 }$ 5—阳极

由于模型具有较好的对称性，因此，仿真模型采用二维轴对称模型分析。

# 2.2电弧模型假设条件

本文电弧模型基于如下假设条件： $\textcircled{1}$ 开关断开后，开距固定为 $3 \mathrm { m m }$ 不变； $\textcircled{2}$ ${ \mathrm { S F } } _ { 6 }$ 断路器中 ${ \mathrm { S F } } _ { 6 }$ 气体和金属蒸气均匀分布于触头之间； $\textcircled{3}$ 忽略光电离过程中产生的倍增电子； $\textcircled{4}$ 忽略电子、离子的对流扩散，只考虑其在电场作用下的迁移运动； $\textcircled{5}$ 假设电弧对称，采用二维轴对称模型进行计算。

# 2.3数学模型

# 2.3.1气体动力学模型

对于弧前粒子运动过程采用带碰撞项的Boltzmann方程描述，即

$$
\frac { \partial f } { \partial t } + \boldsymbol { \nu } \cdot \nabla _ { r } f + \frac { F } { m } \nabla _ { r } f = \frac { \partial f } { \partial t } \Biggr | _ { c }
$$

对式（1）进行简化，在速度空间上积分，并代入电子迁移率计算式，求解电子数密度和电子能量密度的对数，可得简化方程组为

$$
\begin{array} { r l } & { \left[ \cfrac { \partial n _ { \mathrm { e } } } { \partial t } + \boldsymbol { \nabla } \cdot \boldsymbol { \Gamma } _ { \mathrm { e } } = \boldsymbol { R } _ { \mathrm { e } } - ( \boldsymbol { u } \cdot \boldsymbol { \nabla } ) n _ { \mathrm { e } } \right. } \\ & { \left. \cfrac { \partial n _ { \mathrm { e } } } { \partial t } + \boldsymbol { \nabla } \cdot \boldsymbol { \Gamma } _ { \mathrm { e } } + \boldsymbol { E } \cdot \boldsymbol { \Gamma } _ { \mathrm { { s } } } = \boldsymbol { R } _ { \mathrm { s } } - ( \boldsymbol { u } \cdot \boldsymbol { \nabla } ) n _ { \mathrm { e } } + \cfrac { Q + Q _ { \varepsilon } } { q } \right. } \end{array}
$$

其中

$$
\begin{array} { r l } & { \Gamma _ { \mathrm { { \varepsilon } } } = - n _ { \mathrm { { \varepsilon } } } ( \boldsymbol { \mu } _ { \mathrm { { \varepsilon } } } \cdot \boldsymbol { E } ) - D _ { \mathrm { { \varepsilon } } } \cdot \nabla n _ { \mathrm { { \varepsilon } } } } \\ & { \Gamma _ { \mathrm { { e } } } = - n _ { \mathrm { { e } } } ( \boldsymbol { \mu } _ { \mathrm { { e } } } \cdot \boldsymbol { E } ) - D _ { \mathrm { { e } } } \cdot \nabla n _ { \mathrm { { e } } } } \end{array}
$$

式中， $\varGamma _ { \varepsilon }$ ， $\varGamma _ { \mathrm { e } }$ 为不完全的伽玛函数； $R _ { \mathrm { e } }$ 为电子源；$R _ { \mathrm { { \varepsilon } } }$ 为电子能量损耗； $n _ { \mathrm { e } }$ 为电子密度； $n _ { \mathrm { { \varepsilon } } }$ 为平均电子能； $D _ { \mathrm { e } }$ 为电子扩散率； $\mu _ { \mathrm { { \varepsilon } } }$ 为电子能迁移率； $D _ { \varepsilon }$ 为电子能扩散率。

# 2.3.2 电场模型

在电场作用下，微观粒子产生运动，电场计算采用泊松（Poisson）方程，即

$$
\left\{ \begin{array} { l l } { \nabla \cdot ( \varepsilon _ { \scriptscriptstyle 0 } \varepsilon _ { \scriptscriptstyle \mathrm { r } } E ) = \rho _ { \mathrm { v } } } \\ { E = - \nabla V } \end{array} \right.
$$

式中， $\varepsilon _ { \boldsymbol { 0 } } , \varepsilon _ { \mathrm { r } }$ 为灭弧室气体介电常数； $E$ 为电场强度； $\rho _ { \mathrm { v } }$ 为体电荷密度。

# 2.3.3触头间粒子碰撞模型

触头间粒子在电场力的作用下，向触头运动与中性粒子反生碰撞反应，由于 ${ \mathrm { S F } } _ { 6 }$ 气体中的离子种类众多，本文主要考虑了 ${ \mathrm { S F } } _ { 6 }$ 气体与电子的碰撞反应、 ${ \mathrm { S F } } _ { 6 }$ 气体的表面反应、铜蒸气与电子的碰撞反应及铜蒸气的表面反应。由于离子的运动速度相对电子运动很慢，积累能量低，离子碰撞产生的电荷倍增在本文不予考虑。碰撞反应见下表。本文采用的 ${ \mathrm { S F } } _ { 6 }$ 与铜的碰撞截面数据来源于TRINITIdatabase 和 SIGLO database。

表 ${ \mathrm { S F } } _ { 6 }$ 气体与电子的空间碰撞反应方程  
Tab． Collision reaction equation between ${ \mathrm { S F } } _ { 6 }$ gas and electron   

<html><body><table><tr><td>序号</td><td>方程</td><td>粘附系数</td></tr><tr><td>1</td><td>吸附</td><td>e + SF6=> SFs-</td></tr><tr><td>2</td><td>吸附</td><td>e + SF6=> SF6-</td></tr><tr><td>3</td><td>吸附</td><td>e + SF6=> SF6-</td></tr><tr><td>4</td><td>激发</td><td>e + SF6=> e+ SF6S</td></tr><tr><td>5</td><td>伪弹性</td><td>e + SFs => e + SF6</td></tr><tr><td>6</td><td>激发</td><td>e + SF6=> e+ SF6s</td></tr><tr><td>7</td><td>伪弹性</td><td>e + SF6s => e +SF6</td></tr><tr><td>8</td><td>激发</td><td>e + SF=> e+ SFs</td></tr><tr><td>9</td><td>伪弹性</td><td>e + SFs => e + SF6</td></tr><tr><td>10</td><td>激发</td><td>e + SF=> e+ SFs</td></tr><tr><td>11</td><td>伪弹性</td><td>e + SF6s => e + SF6</td></tr><tr><td>12</td><td>激发</td><td>e + SF6=> e + SF6s</td></tr><tr><td>13</td><td>伪弹性</td><td>e + SF6s => e+ SF6</td></tr><tr><td>14</td><td>电离</td><td>e + SF6 => 2e+ SF6+</td></tr></table></body></html>

# 3 仿真结果分析

采用上述模型，本文对初始温度293K，气压15Torr ( $1 \mathrm { T o r r } = 1 3 3 . 3 \mathrm { P a } _ { \cdot }$ )，触头电压 $5 0 0 \mathrm { V }$ ，初始电子密度 $1 \times 1 0 ^ { 1 3 }$ 个 $/ \mathrm { m } ^ { 3 }$ ， $\mathrm { C u ^ { + } }$ 离子密度 $1 \times 1 0 ^ { 1 3 }$ 个 $/ \mathrm { m } ^ { 3 }$ ，电子迁移率为 $4 \times 1 0 ^ { 2 4 } / ( \mathrm { V } \cdot \mathrm { m } \cdot \mathrm { s } )$ ，初始电子平均能为 $4 \mathrm { e V }$ ，二次电子发射系数0.2，初始电子平均能$5 . 8 \mathrm { e V }$ 条件下的 ${ \mathrm { S F } } _ { 6 }$ 断路器灭弧室内电弧弧前发展过程进行了仿真，并分析了开断电流变化导致的金属蒸气含量差异及触头材料变化造成的二次发射系数差异对电弧发展过程的影响。

# 3.1金属蒸气含量对电弧形成过程的影响

本文仿真计算了触头开距为 $3 \mathrm { m m }$ 时金属蒸气摩尔含量分别为 $12 \%$ 、 $8 \%$ 、 $4 \%$ 、 $0 \%$ 时的 ${ \mathrm { S F } } _ { 6 }$ 混合铜蒸气的电弧弧前形成过程。图 $2 \sim$ 图4为不同时刻，不同铜蒸气含量各离子浓度分布图。可以看出，在 $t = 5 0 1 \mathrm { n s }$ 时，铜蒸气的摩尔分数为 $12 \%$ 的弧前鞘层已经形成，由于等离子体已经发展到阴极附近，阴极电场被大大加强，电子也得以获得巨大的能量，粒子之间的碰撞概率及有效碰撞系数上升，使得鞘层中的各种碰撞反应更加剧烈。

![](images/59255ef7806d09974de01009de300f066054e48d664e818b54b2a97aa6977da8.jpg)  
图2 $\scriptstyle t = 5 0 \mathrm { l n s }$ 时的 $\mathrm { S F } _ { 6 } -$ 电子密度分布 Fig.2 ${ \mathrm { S F } } _ { 6 } -$ density distribution when $t = 5 0 1$ ns

![](images/04df0acd3eed81b14fe5f8e0f29048e7f9bdecbcfdf584cf3a8af098d75f4dfa.jpg)  
图3 $t = 5 0 1 \mathrm { n s }$ 时的 $\mathrm { C u } +$ 分布  
Fig.3 ${ \mathrm { C u } } +$ density distribution when $t = 5 0 1 \mathrm { n s }$

![](images/f2835360df5f39903b428c25f018a2cded2791e3eeb4b3ee38b16745f98a9ffd.jpg)  
图4 $t = 5 0 \mathrm { l n s }$ 时的 ${ \mathrm { S F } } _ { 6 } +$ 分布

![](images/682a5ee22f824e010aa450079a2ed76c6e2b208d92fa7c2497d83edb828d3a8a.jpg)  
Fig.4 ${ \mathrm { S F } } _ { 6 } { + }$ density distribution when $t = 5 0 1$ ns   
图5电场强度分布

![](images/6b7e8b20571d3fa7c46e8ef0315b637da8e284cbf781b8319d952be978635084.jpg)  
Fig.5Electric field intensity distribution   
图6电子平均能分布  
Fig.6Mean electron energy distribution

通过对比可以看出，对于不同含量铜蒸气的${ \mathrm { S F } } _ { 6 }$ 电弧，铜蒸气含量越高，鞘层区的电子密度、各离子密度、电子平均能和电场强度都有一个明显的提升，其电弧发展也更为迅速。

# 3.2不同电极材料对电弧形成过程的影响

图7为不同二次发射系数时 $t = 5 0 1 \mathrm { { n s } }$ 的电子密度分布图，其二次发射系数分别为1、0.9、0.8。从图中可以看出，二次发射系数对 ${ \mathrm { S F } } _ { 6 }$ 电弧的形成过程影响很大，二次发射系数为1时，电弧已经发展到近阴极，鞘层区外的电子数目剧增达到 $3 . 9 \times 1 0 ^ { 1 7 }$ 个 $/ \mathrm { m } ^ { 3 }$ 二次发射系数为0.9时，等离子体电弧将要发展到阴极，弧柱头部电子密度达到 $5 . 5 \times 1 0 ^ { 1 6 }$ 个 $/ \mathrm { m } ^ { 3 }$ ；二次发射系数为0.8时，等离子电弧才发展到两电极中间的位置，电子密度最大值只有 $2 \times 1 0 ^ { 1 5 }$ 个 $/ \mathrm { m } ^ { 3 }$ 。

![](images/3105c114abcb670e249a0ae83bf33f5ab53ed43e1473379f37918e3c4da54d5e.jpg)  
图7不同二次发射系数时的电子密度分布Fig.7Distribution of electron density in different twoemission coefficients

对比发现，二次发射系数增大时，其电弧发展通道变得集中一些。这是因为当二次发射系数增大后，新生电子中二次发射产生的电子占的比例有所增加，而二次电子的产生依赖于正离子，又因为正离子运动速度较慢，所以在阴极阳极直线最短的路径点上的二次发射最强烈，因此电弧发展通道变得集中，而二次发射系数在0.8时其阳极电场还未反

向，没有形成等离子体。

图8为不同二次发射系数时 $t = 5 0 \mathrm { l n s }$ 的电场强度分布图，二次发射系数为1时，此时电弧已形成，近阳极及弧柱区电场强度为0，近阴极电场急剧增大，达到 $1 . 6 7 \times 1 0 ^ { 6 } \mathrm { V / m }$ ；二次发射系数为0.9时，电场强度相对有所下降，达到 $7 . 3 \times 1 0 ^ { 5 } \mathrm { V / m }$ 。

![](images/491e05a43434ac19920752bd79ba04fab16f0cfa10bf71ef0ddc0eeaa05b6929.jpg)  
图8不同二次发射系数时的电场强度分布 Fig.8Distribution of electric field intensity in different two emission coefficients

由不同二次发射系数时的电子密度，电场强度分布可以看出二次发射系数增大时，电弧发展速度加快，电弧发展通道变得集中。

# 4结论

为了揭示 ${ \mathrm { S F } } _ { 6 }$ 断路器弧前因素对 ${ \mathrm { S F } } _ { 6 }$ 电弧形成过程的影响，本文以气体动力学模型为基础，考虑

了电子、正负离子漂移扩散方程、微观粒子的碰撞  
方程及电场的泊松方程，基于实际 ${ \mathrm { S F } } _ { 6 }$ 断路器结构，  
研究了在触头间距为 $3 \mathrm { m m }$ 时不同金属蒸气含量、电  
极材料对 ${ \mathrm { S F } } _ { 6 }$ 电弧形成过程的影响，得到结论如下：(1）铜蒸气含量越高，鞘层区的电子密度，各  
离子密度、电子平均能、电场强度都有一个明显的  
提升，铜蒸气的混入显著加速了电弧的形成。(2）触头材料二次发射系数的增大会促进等离  
子体向阴极发展，从而不利于电弧熄灭，同时二次  
发射系数还影响电弧的形状。

# 参考文献

[1] 舒印彪，汤涌，孙华东．电力系统安全稳定标准研 究[J]．中国电机工程学报，2013，33(25)：1-8. Shu Yinbiao,Tang Yong, Sun Huadong. Research on power system security and stability standards[J]. Proceedings of the CSEE,2013,33(25): 1-8.   
[2] 刘晓明．高压 ${ \mathrm { S F } } _ { 6 }$ 断路器电弧动态数学模型及喷口 结构优化设计[D]．沈阳：沈阳工业大学，2003.   
[3] 刘定新，李艳培，荣命哲，等．金属相气相分断电弧 状态转换机理的研究[J]．低压电器，2005(3)：3-6. Liu Dingxin, Li Yanpei, Rong Mingzhe, et al. Study on the mechanism of arc transition from metallic phase to gaseous phase[J]. Low Voltage Apparatus, 2005(3): 3-6.   
[4] Brand K P, Kopainsky J.Particle densities in a decaying ${ \mathrm { S F } } _ { 6 }$ plasm[J]. Applied Physics,1978,16(4): 425-432.   
[5] Bartl J. Thermodynamical properties of the plasma ${ \mathrm { S F } } _ { 6 }$ in the temperature range from 230 to 20 000K and pressures from 0.1 to $1 . 0 \ \mathrm { M P a [ J ] }$ .Acta Technica CSAV,1980,25(1): 33-49.   
[6] Chervy B,Gleizes A,Razafinimanana M. Thermodynamic properties and transport coefficients in SF6 -Cu mixtures attemperatures of 300-30 000 K and pressures of 0.1-1 MPa[J]. Journal of Physics D: Applied Physics,1994,27(6):1193-1206.   
[7] 李静，杨光，曹云东，等．低压断路器触头电弧 非平衡态燃弧过程分析[J]．电器与能效管理技术， 2016(15): 7-12. Li Jing, Yang Guang, Cao Yundong, et al. Analysis of low voltage air switch arc non-equilibrium arcing process[J]. Electrical & Energy Management Technology,2016(15): 7-12.