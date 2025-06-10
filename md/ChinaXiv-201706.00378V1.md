# 喷管内壁多孔处理的圆口喷流大涡模拟

林健于新海 赖焕新(华东理工大学承压系统与安全教育部重点实验室，上海200237)

摘要本文对一亚音速圆口喷管内壁面施加盲孔，使其壁面多孔化，采用大涡模拟结合 FW-H方法研究了马赫数$\scriptstyle { M = 0 . 6 }$ 时喷管外的非稳态流场与远场噪声。研究结果显示，这种内壁小孔结构对喷管外流场的湍流脉动有一定的削弱作用。时空相关系数的对比表明，内壁小孔结构同时减弱了脉动量各自在时间和空间上的相关性，削弱了大尺度的涡结构。通过对涡强、膨胀率和 $\mathrm { \Delta Q }$ 涡识别准则的可视化分析，研究了剪切层中涡结构在喷流轴向的产生、发展与演化过程，结果表明内壁小孔结构抑制了涡配对现象，加强了流动掺混，从而加速了剪切层的发展。

关键词喷管；多孔内壁；大涡模拟；非稳态流场；气动噪声中图分类号：V211 文献标识码：A 文章编号:0253-231X(2017)05-0984-09

# Large Eddy Simulation of a Round Jet From a N6zzle With Porous Inner Wall

LIN Jian YU Xin-Hai LAIHuan-Xin (Key Laboratoryof Pressure SystemsandSafety,MinistryofEducatidn,East China UniversityofScienceandTechology Shanghai 20023China)

AbstractIn this paper,the inner wall_ofsubsonic nozzle is changed to be porous by adding blind holes. Large eddy simulation combihed with the FW-H method are employed to study the unsteady flow field and far-feld noiseradiation at Mach number M=O.6. The results show that the porous wall of the nozzle has sme effects on reducing the turbulence intensity. Comparisons of the turbulence correlation coeffeients reveal that both the temporal and spatial correlations of the turbulent fuctuatios arealssuppressedbytheporous inner wallLargescaleturblencestructures are weakened. The generation, development and evolution of vortices in the shear layer are studied by visualization and analysis of the vorticity,the dilatation and theQ-criterion. The results show that the pairing of vortices is suppressed and the fow mixing is enhanced by the porous wall and as a result,the development of the shear layer is accelerated.

Key wordsnozze; porous inner wal; large eddy simulation; unsteady field; aeroacoustic noise

# 0前言

喷流噪声是民用飞机的主要噪声源之一，其声压级可以达到 $\mathrm { 1 5 0 { \sim } 1 6 0 ~ d B ^ { [ 1 ] } }$ ，对环境造成极大的影响。在过去的半个世纪里，大涵道比发动机技术的发展和广泛应用，发动机喷流噪声已经得到了一定的控制。随着涵道比的增大或已接近技术极限[2]，喷流噪声的控制又重回了喷管本体，方法上大致包括主动方法和被动方法。

使用多孔结构对声源流场和气动声场进行控制，一直是降噪技术中的重要方法。国外将多孔结构直接应用于声源流场的报道，最早见于1984年Thiede等[3」采用多孔材料和多孔结构改善翼型气动性能的研究。类似地，Revell等[4]试验发现多孔处理的副翼侧边可以减小对机身噪声的贡献。这一类采用多孔材料结构减弱声源流场的应用还可见诸文献[5] $\sim$ [7]的报道。总体而言，虽然多孔处理已被证明是流动与噪声被动控制的一种有效措施[8,9]，但是目前对多孔流动控制技术的研究还不够广泛，对其机理的认识也不够清晰。在喷流流动以及噪声控制问题中，采用多孔材料或多孔处理方法的研究，无论是在实验测量或数值模拟分析方面，目前国内外尚未有公开发表的文献报道。

本文采用大涡模拟与FW-H声比拟方法相结合,在马赫数 $M = 0 . 6$ 时，对三种不同内流道的喷管分别进行流场和噪声计算，对比分析内壁小孔结构对喷流流场的时均速度和脉动量 $u ^ { \prime }$ 、 $\boldsymbol { v ^ { \prime } }$ 及 $p ^ { \prime }$ 分布的影响。在此基础上，进一步研究近喷管出口剪切层内$u ^ { \prime } , v ^ { \prime }$ 1 $p ^ { \prime }$ 在时间和空间的相关性，分析其分布与发展的特点。从涡强、膨胀率以及Q判据的可视化分析，研究该多孔结构对旋涡在喷流轴向的发生、发展与演化过程的影响。远场噪声的频谱分析则通过声比拟结果完成，目的是初步检验小孔结构对辐射噪声的抑制作用。

# 1数值计算方法

# 1.1物理模型及网格划分

本文计算对象是三个有出口延伸段的渐缩喷管，其中基础喷管I的出口延伸段为光滑内壁，喷管ⅡI和Ⅲ的延伸段内壁则有盲孔，图1是喷管几何模型及盲孔局部放大示意图。喷管出口直径 $D _ { j } = 1 0 ~ \mathrm { m m }$ 长度 $L = 1 7 0 ~ \mathrm { m m }$ 。喷管 $\pi$ 和ⅢI内壁小孔参数列于表1。

# 表1小孔参数

Table 1 Geometry parameters of the blind holes

![](images/673bd85cfca4d8d228330b794f3033e344c54362444397dacc9704463348f989.jpg)  
图1喷管几何模型Fig.1 Geometry model of nozzles

计算域如图2所示，其中喷管 II 和 III的求解域还包括所有盲孔。坐标原点位于喷管出口圆心，喷管外长度为 $6 0 D _ { j }$ ，上游宽度为 $2 0 D _ { j }$ ，下游宽度为$4 0 D _ { j }$ ；声源面宽度为 $1 0 D _ { j }$ 至 $3 0 D _ { j }$ ，长度为 $5 0 \textcircled { \div } 5 0$

![](images/3f705aa45fca20861ad5763aa1b826295053d9ed2e37d082fbaa30a0ba053066.jpg)  
图2计算域Fig.2 Computational domain

采用结构化网格，剪切层区域进行加密处理，喷管内部则采用O型网格。喷管 $\mathrm { I } { \sim } \mathrm { I I I }$ 的网格数分别为280万、286万和290万，为保证计算结果的可对比性，除内部网格外，本文保障三个喷管外部的网格划分完全一致。

# 1.2控制方程与计算方法

为对喷管中的可压缩流动进行大涡模拟，采用经Favre 滤波的N-S方程[10]：

$$
\frac { \partial \hat { \rho } } { \partial t } + \frac { \partial \hat { \rho } \tilde { u } _ { i } } { \partial x _ { i } } = 0
$$

$$
\begin{array} { c } { \displaystyle \frac { \partial } { \partial t } \left( \bar { \rho } \tilde { u } _ { i } \right) + \displaystyle \frac { \partial } { \partial x _ { j } } \left( \bar { \rho } \tilde { u } _ { i } \tilde { u } _ { j } \right) + \displaystyle \frac { \partial \bar { p } } { \partial x _ { i } } - \frac { \partial \tilde { \sigma } _ { i j } } { \partial x _ { j } } = } \\ { \displaystyle - \frac { \partial \tau _ { i j } } { \partial x _ { j } } + \frac { \partial } { \partial x _ { j } } \left( \bar { \sigma } _ { i j } - \tilde { \sigma } _ { i j } \right) } \end{array}
$$

$$
\frac { \partial \left( \bar { \rho } \tilde { e } + \bar { \rho } \tilde { u } _ { i } \tilde { u } _ { i } / 2 \right) } { \partial t } - \frac { \partial } { \partial x _ { j } } \left( \tilde { \sigma } _ { i j } \tilde { u } _ { i } \right) + \frac { \partial \tilde { q } _ { i } } { \partial x _ { i } } +
$$

$$
\underbrace { \partial \pm [ \delta { \tilde { \rho } } { \tilde { \wp } } + { \bar { \rho } } { \tilde { u } } _ { i } { \tilde { u } } _ { i } / 2 + { \bar { p } } ) { \tilde { u } } _ { i } ] } _ { \partial x _ { i } } = \mathrm { R H S } _ { E }
$$

式中顶部符号“-”表示空间滤波，而‘ $\cdot \sim "$ 表示Favre质量加权滤波变量； $\rho , u _ { i }$ 1 $p$ 和 $\boldsymbol { \mathbf { \ell } } _ { e }$ 分别表示密度、速度分量、压力和内能。式(2）中 $\tau _ { i j }$ 为亚格子应力，

$$
\tau _ { i j } = \bar { \rho } \big ( \widetilde { u _ { i } u _ { j } } - \tilde { u } _ { i } \tilde { u } _ { j } \big )
$$

$\bar { \sigma }$ 为过滤后的黏性应力张量； $\tilde { \sigma }$ 是以过滤速度和温度为参数的黏性应力张量项，

$$
\tilde { \sigma } = \mu ( \bar { T } ) \sqrt { ( \frac { \partial \tilde { u } _ { i } } { \partial x _ { j } } + \frac { \partial \tilde { u } _ { j } } { \partial x _ { i } } - \frac { 2 } { 3 } \frac { \partial \tilde { u } _ { k } } { \partial x _ { k } } \delta _ { i j } } )
$$

$\tilde { q } _ { i }$ 和 $P r$ 分别为热通量和普朗特常数，

'i et p.

$$
\tilde { q } _ { i } = - \frac { \mu \left( \tilde { T } \right) C _ { p } } { P r } \frac { \partial \tilde { T } } { \partial x _ { i } }
$$

$\mathrm { R H S } _ { E }$ 由7项构成，具体参见文献[11。本文亚格子模型选用动态 Smagorinsky-Lilly 模型。为使方程组封闭补充状态方程：

$$
\tilde { p } = R \bar { \rho } \tilde { T }
$$

式中 $R = 2 8 7 . 1 ~ \mathrm { J \cdot k g ^ { - 1 } { \cdot } K ^ { - 1 } }$

本文使用商业软件FLUENT进行模拟，计算分两步进行。首先对喷流流场进行数值仿真；其次提取声源面上的流场数据，通过FW-H方程计算喷流噪声场。流场计算选用Density-Based求解器，流体介质设置为理想气体，黏度采用Sutherland模型。采用RNG $k - \varepsilon$ 湍流模型进行稳态计算，整体质量流量误差小于 $1 \%$ 时认为稳态达到收敛。然后开始瞬态计算，为充分求解涡脱落过程以及保证CFL数小于1,设置非稳态时间步长 $t _ { \mathrm { s t e p } }$ 为 $5 \times 1 0 ^ { - 7 }$ s。非稳态计算时间达到 $t U _ { j } / D _ { j } > 2 0 0$ 时认为流动状态已经可以排除稳态初场的影响即达到统计学稳定，此后开始声场计算并进行流场数据采样统计，采样时间持续 $t U _ { j } / D _ { j } > 2 0 4 ,$ 5

表2喷管模拟结果的对比  
Table 2 Comparison of simulation results of nozzles   

<html><body><table><tr><td>喷管编号</td><td>理想值</td><td>喷管I</td><td>喷管Ⅱ</td><td>喷管Ⅲ</td></tr><tr><td>(Uj,max)t/(m/s)</td><td>204</td><td>205</td><td>204</td><td>204</td></tr><tr><td>(Uj)tm/(m/s)</td><td>204</td><td>197</td><td>195</td><td>196</td></tr><tr><td>(Pi,total)tm/Pa</td><td>128706.9</td><td>128706.9</td><td>128706.9</td><td>128706.9</td></tr><tr><td>(pj,total/tm/Pa</td><td>128706.9</td><td>126917.7</td><td>126510.1</td><td>126724.9</td></tr><tr><td>(VPtotal)tm/Pa</td><td>0</td><td>1789.2</td><td>2196.8</td><td>1982</td></tr><tr><td>(Vptotal)tm/<Pi,total)tm</td><td>0</td><td>1.39%</td><td>1.71%</td><td>1.54%</td></tr><tr><td>(mi)tm/(kg/s)</td><td>0.0193</td><td>0.0181</td><td>0.0182</td><td>0.0182</td></tr><tr><td>(mj)tm/(kg/s)</td><td>0.0193</td><td>0.0181</td><td>0.0182</td><td>0.0182</td></tr><tr><td>Th/N</td><td>3.57</td><td>3.24</td><td>3.23</td><td>3.24</td></tr></table></body></html>

# 1.3边界条件

为保证三种喷管模型出口马赫数都为0.6，边界条件统一给定为：上游喷管入口给定总压 ptotal =$1 2 8 7 0 6 \ \mathrm { P a }$ ，总温 $T _ { \mathrm { t o t a l } } = 3 1 3 . 8 7 5 ~ \mathrm { K }$ ，同时给出参考静压 $p _ { \mathrm { s t a t i c } } = 1 0 1 3 2 5 \ \mathrm { P a }$ ：喷管外计算域入只以及四周环境界面设置为无反射的压力边界条件给定总压 $p _ { \mathrm { t o t a l } } = 1 0 1 3 2 5 \ \mathrm { P a }$ ，总温 $T _ { \mathrm { t o t a l } } \underset { \mathbb { X } } { \Vec { \mathbf { x } } \mathbf { \cdot } \mathbf { \cdot } \mathbf { \cdot } \mathbf { \cdot } \mathbf { \cdot } \mathbf { \cdot } \mathbf { \cdot } } ~ $ 和参考静压 $p _ { \mathrm { s t a t i c } } = 1 0 1 3 2 5 \ \mathrm { P a }$ ；下游出口设置为无反射的压力出口边界条件，给定静压 $\mathcal { P } _ { \mathrm { s t a t i c } } = 1 0 1 3 2 5 \mathrm { P a }$ 总温 $T _ { \mathrm { t o t a l } } = 2 9 3 . 1 5 \ : \mathrm { K }$ ；喷管固壁采用无滑移、绝热壁面边界条件。

本文前期工作已通过实验数据的对比分析[12]，验证了计算模型、方法以及边界条件的有效性。

# 2计算结果及分析

# 2.1平均流动特性比较

为方便表述，对本文的符号作出如下说明 $\mathfrak { N }$ 和$u ^ { \prime }$ 分别表示轴向速度和轴向速度脉动； $\boldsymbol { v }$ 和 $\boldsymbol { v ^ { \prime } }$ 则表示径向速度和径向速度脉动； $p$ 和 $p ^ { \prime }$ 则表示压力和压力脉动； $\dot { m }$ 表示质量流量； $T _ { h }$ 表示推力。 $\langle \cdot \rangle$ 表示变量的平均值，其涉及的下标 $\mathbf { \Psi } _ { t }$ 表示时间平均， $\theta$ 表示周向平均， $m$ 表示质量加权平均。其余下标 $i$ 和 $j$ 分别表示喷管的进口和出口， $\mid c \mid$ 表示喷管中心线。

表2给出了喷管I、IⅡ、Ⅲ模拟结果以及理想气体完全膨胀值与之间的比较。可以发现由于理想状况为无黏流动，忽略了喷管内部的压力损失，导致喷管出口处质量加权轴向平均速度、质量流量、推力都大于喷管I、Ⅱ和Ⅲ的情况。对比喷管I和喷管ⅡI、IⅢI，推力分别为3.24N、3.23N和 $3 . 2 4 ~ \mathrm { N }$ ，即加入内壁小孔结构后喷管推力损失基本可以忽略不计，因此本文使用的多孔参数较为合理。

图3(a）为喷管出口轴向速度沿径向分布对比。可以看出喷管I出口高速流体分布范围最大；小孔结构增加喷管Ⅱ和Ⅲ内部对流体的径向干预，高速流体分布范围都略有减小。同时如图3(b）所示，喷管Ⅱ和Ⅲ沿径向速度梯度减小，这减弱了喷流向下游发展过程中卷入周围流体介质的能力，使得主流与周围环境发生质量、动量和能量的交换变得没有喷管I那样剧烈，因此出现了下图中喷管Ⅱ、IⅢI的势流核长度不减反增的现象。

![](images/c7d890f868c43dea7e594760b15d091404e636aff1883dd49b4fe391cde40383.jpg)  
图3喷管出口轴向速度及中心线上轴向速度分布—,喷管I；----,喷管II；-·-·-,喷管 IIIFig.3 Distributions of axial velocity along radius and thecenter axial lines.—,nozzle I;----,nozzle II; $- \cdot - \cdot -$ nozzle III

# 2.2脉动特性比较

图4给出了不同轴向位置湍流脉动沿径向的分布。可以看出在 $\boldsymbol { x } = D _ { j }$ 轴向位置处喷管 $\pi$ 和喷管ⅢI的轴向速度脉动 $u ^ { \prime }$ 略大于喷管I。往下游发展过程中两喷管的 $u ^ { \prime }$ 都得到了削弱，到 $x = 5 D _ { j }$ 位置时都已减小低于喷管Ⅰ。径向速度脉动 $\boldsymbol { v ^ { \prime } }$ 的减弱趋势比$u ^ { \prime }$ 的减弱趋势更明显，在 $x = D _ { j }$ 轴向位置时，喷管Ⅱ和Ⅲ的 $\boldsymbol { v ^ { \prime } }$ 就已降至低于喷管I的值。脉动速度分量乘积 $u ^ { \prime } v ^ { \prime }$ 以及压力脉动 $p ^ { \prime }$ 同样体现出了一定的减弱趋势。

# 2.3脉动的时空相关性分析

流场脉动的时空相关系数可用来考察不同时刻或不同位置两点脉动量间的相关性。如图5所示于剪切层中脉动值，点 $\mathbf { \Psi } _ { x }$ 与其下游点 $x +$ 两点的时空相关系数 $R _ { i j }$ 定义如下： m

$$
R _ { i j } \left( x , \xi , \tau \right) = \frac { \langle i ^ { \prime } \left( x , t \right) j ^ { \prime } ( x \llap / \llap / \llap / \llap / \llap / \tau ) \rangle _ { t } } { \sqrt { \langle i ^ { \prime 2 } \left( x \right) \rangle _ { t } } \sqrt { \langle j ^ { \prime 2 } \left( x + \xi \right) \rangle _ { t } } }
$$

式中， $x$ 为测点在流场中的轴向坐标， $\xi$ 为两个测点间的距离， $\tau$ 为延迟时间。

图 $6 ( \mathrm { a } ) \mathrm { \sim ( c ) }$ 分别表示喷管唇线上 $x = 2 . 5 D _ { j }$ 处轴向脉动速度 $u ^ { \prime }$ 、径向脉动速度 $\boldsymbol { v ^ { \prime } }$ 和压力脉动 $p ^ { \prime }$ 在时间序列上的自相关性 $R _ { u u }$ 、 $R _ { v v }$ 和 $R _ { p p }$ 。内壁小孔结构对此处Ruu 的影响甚微，而对 Ruu和 Rpp的影响较明显，它们各自的时间相关性被削减。类似地，本文小孔结构对压力脉动 $p ^ { \prime }$ 分别与 $u ^ { \prime }$ 、 $\boldsymbol { v ^ { \prime } }$ 在时间序列上的关联 $R _ { u p }$ 和 $R _ { v p }$ 也有明显的削弱作用。

![](images/653fac547bae6f38899a5bd94f76d62ccd7c9f1636cef1b349dcbebc81bd85d0.jpg)  
Fig.4 Radial profles of turbulent fluctuations at axial positions $x / D _ { j } = 1$ ,2.5 and5.Legend asin Fig.3

![](images/71db9192568d8db157169eb72c3fbf3b2888673d9dbd84b7665ea3289fb28426.jpg)  
图4不同轴向位置湍流脉动沿径向的分布。每幅图中从左到右的位置 $x / D _ { j }$ 分别为1、2.5和5，线型含义同图3

时间相关性的减弱一定程度上反映了流场混乱程度的增强，说明内壁小孔结构加速了大尺度旋涡向小涡的转变。

图7表示喷管唇线上 $x = 1 0 D _ { j }$ 处三个喷管的$R _ { u u }$ 、 $R _ { v v }$ 和 $R _ { p p }$ 所对应的云图。图中虚线斜率代表了该位置脉动量向下游的传递速率。可以发现喷管Ⅱ和Ⅲ中虚线的斜率大于喷管I中的对应值，可见内壁小孔结构加速了 $u ^ { \prime } , v ^ { \prime }$ 和 $p ^ { \prime }$ 向下游传递的速率。此外，喷管I的时空相关系数正值区域比喷管Ⅱ和Ⅲ较宽，说明在同样的时间间隔下，内壁小孔结构减弱了脉动量 $u ^ { \prime }$ 、 $\boldsymbol { v ^ { \prime } }$ 和 $p ^ { \prime }$ 各自在空间上的相关性，再次从空间角度印证了小孔结构减小旋涡结构的作用。

![](images/9111b2655f580c6a751b8e0287c8d1b37f7ad12746b6870771231d163ac4583b.jpg)  
图5剪切层中脉动相关系数定义的对应位置 $\mathbf { \Psi } _ { x }$ 和测点间距离 $\xi$ 示意图

![](images/ab1060ab42d56e9f698820b8fd0781c9f155a8d760f18794bb75061a2d7a4d29.jpg)  
Fig.5 Two-point spatial-temporal correlations in the shear layer,obtained for locationx and usinga spatial separation $\xi$   
图6喷管唇线上 $x = 2 . 5 D _ { j }$ 处脉动相关系数图中线型含义同图3  
Fig. 6 Two-point spatial-temporal correlations of fluctuations inthe shear layer at $x = 2 . 5 D _ { j }$ . Legend as in Fig.

$R _ { u u } ( x , \xi , \tau )$ （204号 Rv(x,,t) $R _ { p p } ( x , \xi , \tau )$ 0.025 0.02 0203040.5 0.6 0.02 0.02 0.2-0.1010.1 0.4 0.025 0.02 00.1020.3 G 0s   
I 0.015 0.01 0.9 - 0.8 心 -0.4 05 0.015 0.01 0.8 0.6 P 9 0.015 0.01 ' -08 总 0.6 0 0.05 0.3 0.05 0 0.05 0 0.2 0 0 0 0 0.0001 0.0002 0.0003 0 0.0001 0.0002 0.0003 0 0.0001 0.0002 0.0003 T T T D 0 0033A05 0.6 00 0002 # 5.00.10.2 0.3   
II oC 0--0 中国 0.01 -0.9 G 0.01 0 0.01 01 1 0.8 0.05 I 0.05 0.05 6 0 0 0 0 0.0001 0.00020.0003 % 0.00010.0002 0.0003 8 0.0001 0.0002 0.0003 T T T

0 0.025 0.3.45.50.6 0.025 QS: 620 0.025 20.00.10.2 0.7 1 0.5 0.02 10.8 0.6 0.02 G 0.02 ":.0.01 - 0.0.01 0 0.015 品品8品品园 e IⅢI Oe- E 0.05 -0.1 0.05 / -0.1 0.05 ！ 0.00010.00020.0003 哈 0.0001 0.00020.0003 0.0001 0.0002 0.0003 T T T

# 2.4剪切层厚度分析

$$
D = \frac { \partial u } { \partial x } + \frac { \partial v } { \partial y } + \frac { \partial w } { \partial z }
$$

剪切层厚度 $\delta = ( r _ { 0 . 1 0 } - r _ { 0 . 9 5 } )$ ,其中 $r _ { 0 . 1 }$ 和 $r _ { 0 . 9 5 }$ 分别表示轴向流速为 $1 0 \% \langle u _ { c } \rangle _ { t }$ 和 $9 5 \% \langle u _ { c } \rangle _ { t }$ 处对应的半径值。图8为剪切层厚度对比图，3条分布曲线基本都呈现出线性增长的趋势，这与剪切层理论一致。对比其斜率，可以发现内壁小孔结构降低了剪切层厚度增长的速度。

![](images/25da33441620ece85ff20781fd0ebe4677d082d37cc70d3d9e00fb13aac3f0fa.jpg)  
图7喷管唇线上 $x = 1 0 D _ { j }$ 处脉动相关系数云图Fig.7 Contours of $R _ { u u }$ 、 $R _ { v v }$ and $R _ { p p }$ at $x = 1 0 D _ { j }$ in the shear layer  
图8剪切层厚度对比图.线型含义同图3 Fig.8 Comparison of shear layer thickness. Legend as in Fig.3

# 2.5内壁小孔结构对流场影响的分析

Powell[13]和Howe[14]发展的涡声理论表明，声波的产生同流体中的旋涡和势流、以及旋涡之间的相互作用密切相关。本文从涡强 $| \varOmega |$ 、膨胀率 $D$ 和$Q$ 值这三个物理量出发，研究多孔壁面对流场中旋涡结构和强度等方面发挥的作用，重点考察剪切层中大尺度涡结构的发生、发展与演化过程，研究考察K-H不稳定性的发展与旋涡配对。 $| \varOmega |$ ， $D$ 和 $Q$ 的定义计算式为：

$$
| { \boldsymbol { \varOmega } } | = \left. { \boldsymbol { \nabla } } \times { \boldsymbol { \overrightarrow { V } } } \right.
$$

$$
Q = \left( { \frac { \partial u } { \partial x } } { \frac { \partial v } { \partial y } } - { \frac { \partial v } { \partial x } } { \frac { \partial u } { \partial y } } \right) + \left( { \frac { \partial v } { \partial y } } { \frac { \partial w } { \partial z } } - { \frac { \partial w } { \partial y } } { \frac { \partial v } { \partial z } } \right) +
$$

W图9 给出了𝑟－x平面上由涡强「5和膨胀率表征的瞬态涡结构图。图 $9 ( \mathrm { a } ) \mathrm { \sim } ( \mathrm { c } )$ 可以看出距离喷管出口约1.5倍半径范围内喷管都存在一个准层流环形混合层。这一准层流环形混合层的发展主要受不稳定性波引起的扰动增长的影响，导致剪切层变形以及旋涡卷起形成大尺度涡环结构，随后涡环向下游对流时产生涡配对现象，它也是喷流噪声产生的原因之一；最终涡环失去稳定性而变形。图9(a)、(b）中用虚线框标出的地方可以清晰的看到涡配对这种非线性相互作用现象，而在图9(c）中这种现象并不明显。比较图 $9 ( \mathrm { a } ) \mathrm { \sim ( c ) }$ 的膨胀率云图。可以发现，喷管I和Ⅱ分布规律类似，在喷管出口附近声波传播方法主要是上游和径向方向，而喷管IⅢI则出现了一部分声波往下游传播，说明喷管Ⅲ这组多孔参数已经对旋涡结构的改变产生了较为明显的作用。

为观察湍流涡结构沿流向的三维演化特征以及开孔对涡结构产生的影响，图10给出了涡量在不同的流向位置 $\mathbf { \Psi } _ { x }$ 横截面上的分布。在 $x / D _ { j } = 0 . 5$ 处可以看出轴对称涡环形成，这与线性稳定性理论的结果一致[15,16]。进一步的发展，旋涡出现周向的弯曲而开始失去稳定性，随后涡环变形，失去对称性，形成涡辫结构。喷管 $\pi$ 和喷管I由于径向扰动的加入，加速了剪切层的发展。因此轴对称涡环的特征不再明显，在 $0 . 5 D _ { j }$ 处(图10(d)、(g)）涡环已开始变形。而喷管I在 $x / D _ { j } = 2 . 5$ 处才出现的涡辫结构(图10(c)）在喷管 $\pi$ 和Ⅲ中提前至 $x / D _ { j } = 1$ 处即已出现。

![](images/8a6a26f48b8e54b2239181fb1507e8eb6925ebc8b577c68b84aa0e0a33861677.jpg)  
图9 $\boldsymbol { r } - \boldsymbol { x }$ 平面上由涡强 $| \varOmega |$ 和膨胀率表征的瞬态涡结构图涡强和膨胀率灰度云图由亮到暗表征的范围分别为（0.001,10）和 (-0.001,0.001) Fig.9 The instantaneous vortices shown by $| \varOmega |$ and dilatation field in $r - z$ plane.The gray contour levels from light to dark ar scaled by(O.0o1,1O) for vorticity and $( - 0 . 0 0 1 , 0 . 0 0 1 )$ for dilatation

![](images/73128135dcf17fa6ef095d99cda829938486fd907e6ba44e37c5c75b671acba6.jpg)  
图 $_ { 1 0 ~ x }$ 方不同位置切面涡量场结构Fig.1O The structure of vortices at different $x$ positions

图11分别展示了三个喷管模型的 $Q$ 准则等值面分布，其中 $Q = 2 0 0 0 0 0 0$ ，灰度代表了轴向流速的大小。从图11中可以看出在近喷管出口区域，剪切层扰动涡呈现周向的管状结构，这种剪切层不稳定性属于开尔文－亥姆霍兹不稳定 (KHI)。随后剪切层中的扰动涡出现明显的周向破碎，并向下游发展演化。下游涡结构表现出三维特性，比如项链涡，展展向涡以及沿流向细长的流线涡。对比图11中局部放大图可以发现，喷管Ⅱ和喷管ⅢI周向管状结构尺度明显小于喷管I中出现的尺度，再次证明了内壁小孔结构加强了流动掺混，加速了剪切层的发展。

# 2.6远场声压

本文通过FW-H方程对远场监测点的声压进行计算，得出不同监测点处的总声压级对比。噪声监测点采用同心圆面布置，圆心为喷管出口中心，测点距离为 $1 0 0 D _ { j }$ ，角度从 $1 0 ^ { \circ }$ 到 $1 5 0 ^ { \circ }$ 。图12是总声压级的对比。可以发现内壁小孔结构对降噪有一定的效果，且喷管ⅢI的降噪效果好于喷管 $\pi$ ，例如在$3 0 ^ { \circ }$ 处喷管ⅡI和ⅢI比喷管I的噪声分别降低1dB和$1 . 7 \ \mathrm { d B }$ 。

![](images/84cd08c6925ba5567a3568c03a5c757a811cb2630ce19cb1986ea09b29bb3c99.jpg)  
图11由Q判据表征的瞬时三维涡结构及局部放大图

![](images/863bee148e72b57e7e02fecf810807a108444830ed28161db90b28ee31dd7cad.jpg)  
Fig.1l Instantaneous thredimensional vortices represented by Q-Criterion and their local zooms

为进一步研究内壁小孔结构对声场频谱特性的影响，本文选取 $3 0 ^ { \circ }$ 方位监测点进行频谱分析。图13是该点 $1 / 3$ 倍频谱图。可以看出喷管I噪声主频在$2 5 0 0 \mathrm { { H z } }$ 的低频部分。加入内壁小孔结构后，喷管ⅡI主频增大至 $\mathrm { 4 0 0 0 ~ H z }$ 。此外喷管Ⅱ和喷管I在1200$\mathrm { { H z } }$ 以下的低频噪声得到了削弱，而1200 至 4500$\mathrm { H z }$ 之间噪声略有增强。该变化的原因可能是径向扰动加速大尺度涡破碎，相应地增加了小尺度涡的数量。

![](images/701306a4892781ae5523cf0f59ddab089b5e53be180922ad89813b7829b141bd.jpg)  
图12监测点方位示意以及总声压级对比图图中线型含义同图3  
Fig.12 Positions of monitoring point and comparison of total sound pressure level.Legend as in Fig.3   
图13 $3 0 ^ { \circ }$ 方位监测点声压频谱图 Fig.13 Sound pressure spectrum at the $3 0 ^ { \circ }$ azimuthal monitoring point

# 3结论

本文采用大涡模拟结合FW-H的方法对具有内壁盲孔结构的喷管喷流进行了研究，得到如下结论：

1）加入内壁小孔结构，由于沿程损失和局部损失的增加，减小了喷管出口截面上高速流体沿径向的分布范围，同时沿径向速度梯度的减小，势流核长度增加。

2)内壁小孔结构中流动和压力的重新分布削弱了喷管外流动的湍流脉动。

3）喷管近出口区域时间序列上的相关性$R _ { v v }$ ， $R _ { p p }$ ， $R _ { u p }$ 和 $R _ { v p }$ 因小孔结构的影响而减弱，而 $u ^ { \prime }$ 、 $\boldsymbol { v } ^ { \prime }$ 和 $p ^ { \prime }$ 往下游的传递速度则有所增大，相应地也减弱了它们各自的空间相关性。

4）喷流脉动特性的改变，宏观上体现为剪切层中涡配对现象被抑制和流动掺混的加强，从而加速了剪切层的发展，远场噪声也在一定程度上被抑制。

# 参考文献

[1]吴九汇．噪声分析与控制[M].西安：西安交通大学出版述 2011 Wu J H. Noise Analysis and Control [M]. Xiam: Xi'an Jiaotong University Press,2011 物   
[2] Bühler S,Kleiser L,Bogey C. Simulationof Subsonic Turbulent Nozzle Jet Flow and its NeaMled Sound [J]. AIAA Journal,2014, 52(8): 1653-1669生   
[3] Thiede P,Krogmann P, Stahewsky E.Active and Passive Shock/boundary Layer Interaction on Supercritical Airfoils [R]. AGARD CP-365,1984   
[4]Revell JD，Kuntz HL，Balena FJ,et al. Trailingedge flap Noise Reduction by Porous Acoustic Treatment [C]//3rd AIAA/CEAS Aeroacoustics Conference,Atlanta, USA,1997   
[5]Naito H,Fukagata K.Numerical Simulation of Flow Around a Circular Cylinder Having Porous Surface [J]. Physics of Fluids,2012,23(13):102-117   
[6] Lai H,Luo K H.A Conceptual Study of Cavity Aeroacoustics Control Using Porous Media Inserts [J].Flow, Turbulence and Combustion,2008,80(3):375-391   
[7]刘汉儒．多孔材料结构对外流不稳定性及流致噪声控制的 机理研究[D].西安交通大学，2014 Liu HR. Study on Mechanisms of External flow Instability and Flow-induces Noise Control by Porous Materials [D].Xi'an Jiaotong University, 2014   
[8]Bae Y,Moon Y J.Effective of Passive Porous Surface on the Trailing-edge Noise [J]. Physics of Fluids,2011,23: 126101   
[9] Schulze J,Sesterhenn J.Optimal Distribution of Porous Media to Reduce Trailing Edge Noise [J].Computers & Fluids,2013,78:41-53   
[10] Vreman B.Direct and Large-Eddy Simulation of the Compressible Turbulent Mixing Layer [D].Univ of Twente, TwenteThe Netherlands,1995   
[11] LarCheveque L, Sagaut P, Mary L, Labbe O. Large-eddy Simulation of a Compressible flow Past a Deep Cavity [J]. Physics of Fluids,2003,15(1):193-210 林健,赖焕新.亚音速圆口喷流的大涡模拟[J].华东理工大 学学报(自然科学版),2016,42(5)：715-721 Lin J,Lai HX.Large Eddy Simulation of Subsonic Round Jet [J].Journal of East China University of Science and Technology (Natural Science Edition), 2016,42(5): 715- 721   
[13] Powell A. Theory of Vortex Sound [J].The Journal of the Acoustical Society of America,1964, 36(1):177   
[14]Howe MS.Theory of Vortex Sound [M].Cambridge:Cambridge University Press,2003   
[15] Batchlor G K,GA E. Analysis of the Stability of Axisymmetric Jets [J]. Journal of Fluid Mechanics,1962,14: 529-551   
[16] Cohen J, Wygnanski I. The Evolution of Instability in the Axisymmetric Jet. Part 1. The Linear Growth of Disturances Near the Nozzle [J]. Journal of Fluid Mechanics, 1987,176:191-219