# 双层薄膜界面声子输运的MonteCarlo模拟

冉鑫　郭洋裕　王沫然

(清华大学航天航空学院，热科学与动力工程教育部重点实验室，北京100084)

摘要界面声子热输运现象广泛地存在于纳米热电装置和微纳电子器件中，但其物理机制和介观模型仍不完善。本文将考虑真实色散关系的漫射失配（DMM）界面模型引入到高效、低噪的动力型声子 Monte Carlo(MC）方法，建立了一个频谱穿透系数的界面声子输运数值模型。采用新的数值模型研究了室温下 Si/Al薄膜中的界面声子输运，可准确捕捉法向输运和面向输运的非平衡效应。

关键词声子输运；MonteCarlo 模拟；界面热输运；微纳尺度传热中图分类号：TK124 文献标识码：A 文章编号:0253-231X(2017)04-0841-06

# Monte Carlo Simulation of Interfacial Phonon Transport Through Bilayer Thin Film

RAN Xin GUO Yang-Yu xWANG Mo-Ran

(Key Laboratory for Thermal Science and Power Enginering ofMjstryof Education,Departmentof Enginering Mechanics and CNMM, Tsinghua University,Beijing 100084, China)

AbstractInterfacial phonon transport_widly exists in nano thermoelectric and nano electronic devices, but the mechanism and mesoscopic modeling remain stillincomplete. The present work establishes a numerical model for interfagialphonon transport by introducing the diffuse mismatch model (DMM) with exact phonon dispersiofto a kinetic-type Monte Carlo (MC) scheme. Then the interfacial phonon transport through Si/Al bilayer thin film at room temperature is studied. The new numerical model is able to capturewell the non-equilibrium efects in both crossplane and in-plane transport. Key wordsphonon transport; Monte-Carlo simulation; interfacial heat transport; micro- and nanoscale heat transport

# 0引言

et p.i et.

近几十年来，随着微纳加工制造技术和微纳米科技的发展，微纳尺度热输运成为人们的研究热点在微纳系统中的热输运，界面效应占主导作用适用于体材料的 Fourier 导热定律不再成立[1]，因而亟需发展新的理论和模型。在传统的半导体器件中，声子和电子是主要的热载子 (Heatcarrier)，而本文主要关注声子热输运。微纳尺度热输运领域主要由田长霖等人在上世纪八九十年代开创[2]，经过几十年的发展，已有十足的进展，但仍存在很多尚未解决的难题，例如微纳热电材料的能量转换效率优化和微纳电子器件散热。这两种难题中都存在共同的界面声子热输运过程。

前人在界面声子输运方面进行了大量的理论研究，提出的经典界面输运模型主要包括：声学失配模型（Acoustic mismatch model,AMM)[3] 和漫射失配模型(Diffuse mismatch model,DMM) [4]。AMM模型通常只适用于极低温情形，认为声子以连续波的形式在介电固体中传播，并在光滑界面发生镜面反射和镜面透射，穿透系数 (透射率)可由界面两侧材料的声学阻抗计算获得，反射角和透射角由光学中的 Snell 定律计算获得[3]；而DMM 模型适用于更高温度的情形，认为声子在界面发生漫反射和漫透射，穿透系数主要取决于界面两侧材料的声子色散关系[4]。前人的实验研究间接表明了声子在界面处存在镜射和漫射行为，因此AMM模型和DMM模型均无法单独地准确描述所有的界面声子输运过程[5]。Chen[6]在1998 年提出一个基于Debye 近似的灰色混合模型，假设声子在界面发生部分镜射和部分漫射，但镜参数 (镜射的比例)是一个经验值，通常需要通过与实验结果的对比获得，声子界面输运行为的本质仍有待进一步的揭示。由于人们感兴趣的微纳尺度热输运过程通常发生在室温及更高温度下，DMM模型为目前较为广泛认可和使用的模型。后人在DMM模型的基础上也提出了很多的修正或者改进[7-11]，虽然无法准确地描述所有的声子界面输运，但更近一步地解释了实验结果[12,13]。

结合上述界面输运模型，前人通过求解声子玻尔兹曼方程对微纳尺度界面声子输运进行了很多的研究。求解声子玻尔兹曼方程的方法主要包括确定型（有限差分法FDM[14]等)和随机型(Monte Carlo,MC[15-17]）两种。MC方法避免了直接求解高维的声子玻尔兹曼方程，且对界面边界的处理简单并具有清晰的物理图像，因而是复杂界面(多层薄膜结构、纳米复合材料和纳米晶等）中声子输运研究的良好选择。Jeng 等[16]最早使用声子 MC 方法计算了纳米颗粒复合材料的等效热导率，采用了基于Debye近似的灰色DMM 模型；后来Huang 等[15]在声子MC 中考虑了Chen 提出的部分镜射和部分漫射的灰色混合界面模型；最近 Peraud 和 Hadjiconstantinou使用新发展的能量偏差声子MC方法模拟了瞬态热反射实验中Si/Al界面的多尺度声子输运过程，采用了Minnich 等[17] 提出的修正DMM模型。总之,前人的介观模拟工作在界面边界处理时均只考虑了常数型声子界面穿透系数，或者声子从一个方向穿过界面时的穿透系数是一个常数。但最近的实验测量[18]和微观理论计算结果[19]均表明，声子的界面穿透系数具有高度的频谱特性：通常而言，高频声子在界面处容易被反射，而低频声子则较容易通过界面。前人的模型研究也表明考虑真实色散关系和频谱穿透系数的DMM模型与Debye灰色DMM模型相比更符合实际[7,10]，计算获得的界面热导与实验结果更接近[13]。然而，目前仍然缺少一个考虑濒谱穿透系数的界面声子输运介观MC数值模型。因此，本文将基于考虑真实色散关系的 DMM模型，建立一个考虑频谱穿透系数的双层薄膜界面声子输运MC 数值模型。

向输运，在 $\mathbf { \Psi } _ { x }$ 方向上施加一个恒定的均匀温度梯度，上下边界绝热。

![](images/ad439d368d0408c78110dc8bc7dcf4ec51c8d8c685ae00ea7e93b2719a962ba3.jpg)  
图1硅/铝薄膜界面声子输运物理模型示意图 Fig.1 Physical model of Si/Al thin film interfacial phonon transport

本文采用硅、铝体材料的真实的声子色散关系[20,21]，忽略光学支对热输运的贡献，且使用四次多项式拟合表达式，即：

# 1物理模型和数值方法

# 1.1物理模型

本文以室温下硅/铝薄膜界面声子输运为研究对象，考虑了法向输运和面向输运两种情形，分别如图1(a)、图1(b)所示。对于法向输运，系统处于均匀的初始温度 $2 9 9 \mathrm { ~ K ~ }$ ，突然系统的左边界与 $3 0 1 ~ \mathrm { K }$ 的恒温热源接触，右边界与 $2 9 9 \mathrm { K }$ 的恒温热源接触。 $y$ 方向上尺度无限大，以保证一维的法向输运。对于面

$$
\omega \left( k \right) = A _ { 4 } k ^ { 4 } + A _ { 3 } k ^ { 3 } + A _ { 2 } k ^ { 2 } + A _ { 1 } k
$$

式中， $\omega$ 为声子频率， $k$ 为声子波数， $A _ { 1 }$ 、 $A _ { 2 }$ 、 $A _ { 3 }$ 和 $A _ { 4 }$ 为拟合参数。对于硅体材料，拟合参数分别为：横声学声子（TA)： $A _ { 1 } { = } 5 . 5 1 1 { \times } 1 0 ^ { 3 } \ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ ， $A _ { 2 } =$ $- 1 . 1 6 9 { \times } 1 0 ^ { - 8 } \ \mathrm { m ^ { 2 } { \cdot } s ^ { - 1 } }$ ， $A _ { 3 } { = } { - } 4 . 9 5 7 { \times } 1 0 ^ { - 1 7 } \ \mathrm { m ^ { 3 } { \cdot } s ^ { - 1 } }$ ，$A _ { 4 } { = } 2 . 4 3 2 { \times } 1 0 ^ { - 2 7 } ~ \mathrm { m } ^ { 4 } { \cdot } \mathrm { s } ^ { - 1 }$ ；纵声学声子（LA)： $A _ { 1 } =$ $8 . 1 9 2 \times 1 0 ^ { 3 } \ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ ， $A _ { 2 } mathrm { = - 1 . 1 4 0 { \times } 1 0 ^ { - 7 } \ m ^ { 2 } { \cdot } s ^ { - 1 } }$ ， $A _ { 3 } =$ $- 2 . 6 1 2 \times 1 0 ^ { - 1 8 } \mathrm { m ^ { 3 } \cdot s ^ { - 1 } }$ ， $A _ { 4 } { = } { - } 5 . 6 4 5 { \times } 1 0 ^ { - 2 9 } ~ \mathrm { m } ^ { 4 }$ ，$\mathrm { { s } ^ { - 1 } }$ [20]。对于铝体材料，考虑真实的色散关系[21],我们同样采用四次多项式拟合，我们拟合得到的无量纲的色散关系表达式为：

$$
\omega \left( K \right) = A _ { 4 } K ^ { 4 } + A _ { 3 } K ^ { 3 } + A _ { 2 } K ^ { 2 } + A _ { 1 } K
$$

式中， $K = k / k _ { \mathrm { m a x } }$ ， $k _ { \mathrm { m a x } } { = } 2 \pi / a$ ， $\boldsymbol { a }$ 为铝的晶格常数。拟合参数分别为：横声学声子(TA)： $A _ { 1 } { = } 5 . 1 4 7 { \times } 1 0 ^ { 1 3 }$ （20rad/s， $A _ { 2 } { = } 9 . 5 7 8 { \times } 1 0 ^ { 1 2 } \quad \mathrm { r a d / s } , \quad A _ { 3 } { = } { - } 3 . 2 0 4 { \times } 1 0 ^ { 1 3 }$ （204$\mathrm { r a d / s }$ ， $A _ { 4 } { = } 6 . 7 5 0 { \times } 1 0 ^ { 1 2 } \ \mathrm { r a d / s }$ ；纵声学声子 (LA)：$A _ { 1 } { = } 9 . 8 2 5 { \times } 1 0 ^ { 1 3 }$ rad/s, $A _ { 2 } { = } 2 . 2 2 6 { \times } 1 0 ^ { 1 3 }$ rad/s, $A _ { 3 } =$ $- 1 . 2 1 6 \times 1 0 ^ { 1 4 } ~ \mathrm { r a d / s } , ~ A _ { 4 } { = } 6 . 2 0 8 \times 1 0 ^ { 1 3 } ~ \mathrm { r a d / s } _ { \circ }$ （20

硅体材料的声子总弛豫时间基于Matthiessen定则，为： $\tau ^ { - 1 } = \tau _ { a } ^ { - 1 } + \tau _ { i } ^ { - 1 }$ ，其中非简谐三声子过程的弛豫时间表达式为[20]：

$$
\tau _ { a } ^ { - 1 } = A T \omega ^ { 2 } \exp ( - B / T )
$$

式中， $A { = } 1 . 4 { \times } 1 0 ^ { - 1 9 } ~ \mathrm { s / K }$ ， $B { = } 1 5 2 \mathrm { ~ K ~ }$ 。缺陷散射过程的弛豫时间表达式为[20]：

$$
\tau _ { i } ^ { - 1 } = C \omega ^ { 4 }
$$

式中， $C { = } 1 . 3 2 { \times } 1 0 ^ { - 4 5 } \ \mathrm { s } ^ { 3 }$ 。铝体材料的声子弛豫时间为[11]： $\tau = 1 \times 1 0 ^ { - 1 1 }$ s。声子的界面输运模型考虑真实色散关系和频谱穿透系数的DM模型[10]：

$$
\alpha _ { 1  2 } ( \omega ) = \frac { \displaystyle \sum _ { \mathrm { p } } \sqrt { \| b _ { \mathrm { p } , 1 } ( ^ { \mathrm { e x p } } ) \| ^ { 2 } } } { \displaystyle \sum _ { \mathrm { p } } [ k _ { \mathrm { p } , 1 } ( \omega ) ] ^ { 2 } + \sum _ { \mathrm { p } } [ k _ { \mathrm { p } , 2 } ( \omega ) ] ^ { 2 } }
$$

式中，下标1和2代表材料，p代表声子支。根据漫射假设，有： $\alpha _ { 2 \to 1 } \left( \omega \right) = 1 - \alpha _ { 1 \to 2 } \left( \omega \right)$ 0

# 1.2声子蒙特卡洛方法

本文采用 Peraud 和 Hadjiconstantinou 最近发展的动力型 Monte Carlo 方法[22]，该方法采用随机统计原理求解偏差能量形式的声子玻尔兹曼方程：

$$
\begin{array} { r l } & { \frac { \partial \left( e - e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } } \right) } { \partial t } + v _ { \mathrm { g } } ( \omega , \mathrm { p } ) \cdot \nabla ( e - e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } } ) = } \\ & { \qquad \frac { \left( e _ { \mathrm { l o c } } - e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } } \right) - \left( e - e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } } \right) } { \tau ( \omega , p , T ) } } \end{array}
$$

式中， $e$ 为声子的能量分布， ${ \boldsymbol { v } } _ { \mathrm { g } }$ 为声子群速度, $\omega$ 为声子角频率, $\mathrm { ~ p ~ }$ 为声子支， $T _ { \mathrm { e q } }$ 为假设的参考平衡温度， $e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } }$ 为在 $ { T _ { \mathrm { e q } } }$ 下的平衡能量分布, $e _ { \mathrm { l o c } }$ 为在当地伪温度 $T _ { \mathrm { l o c } }$ 的平衡能量分布， $\tau$ 为声子弛豫时间。基于能量偏差的MC方法只模拟导热过程偏离参考平衡分布的声子分布，因而统计噪音小；在进一步的小温差假定下，动力型MC将偏差能量的分布做线性化近似，归一化后为与当地温度无关的分布，因而无需在中间步骤中对宏观变量 (温度和伪温度)进行统计来获得过程中声子的平衡分布和非平衡分布，只要知道所需发射的声子的总数目，就可以一个一个跟踪，相比通常的 MC[17]进一步简化了数值算法,提高了计算效率。

动力型声子MC方法的主要流程依次包括初始化、迁移、散射、边界处理和宏观量统计。首先是初始化步，给定模拟粒子如下的平衡分布：

$$
( T _ { 0 } - T _ { \mathrm { e q } } ) D ( \omega , p ) \frac { \mathrm { d } e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } } } { \mathrm { d } T }
$$

$T _ { 0 }$ 为系统初始温度， $D ( \omega , \mathrm { p } )$ 为声子态密度，粒子以平衡分布（7）从边界或系统内部一个一个地依次发射。然后进行迁移步，模拟粒子的迁移位移是 ${ \pmb v } _ { \mathrm { g } } \Delta t$ 其电 $\exists \deg  - \tau \cdot \ln ( R )$ ， $\mathbf { \Psi } _ { t }$ 是模拟时间， $\tau$ 是材料的声子弛豫时间， $R$ 是一个介于0到1的随机数；迁移后若粒子遇到边界，则进行边界处理，否则对粒子进行散射处理，散射后的粒子服从的非平衡分布为：

$$
( T _ { \mathrm { l o c } } - T _ { \mathrm { e q } } ) \frac { D ( \omega , \mathrm { p ) } } { \tau ( \omega , \mathrm { p } , T _ { \mathrm { e q } } ) } \frac { \mathrm { d } e _ { T _ { \mathrm { e q } } } ^ { \mathrm { e q } } } { \mathrm { d } T }
$$

一次散射结束后，粒子继续进行漂移和下一次散射，如此循环往复，直至时间到达设定的计算终止时间或者粒子离开模拟系统边界。最后对时间和空间进行离散化，并在每一个时间节点上对声子在空间网格里的总能量和总能量流进行统计以获得温度和热流等宏观量。最后对边界处理进行说明，本文涉及的边界处理包括绝热边界、等温边界、恒定温度梯度边界和界面边界。绝热边界采用漫反射边界处理,假设粒子与边界碰撞后，反射粒子的方向随机给定，与入射粒子的速度方向无关，但是粒子的频率和波数保持不变。等温边界要求与边界碰撞的粒子全吸收，发射粒子是漫发射，即方向随机给定，满足平衡分布 (7)。面向输运中的恒定温度梯度边界采用热流周期性边界处理，从一个边界离开系统的粒子从另外一个边界重新进入系统，除位置之外的其它粒子信息都不改变。界面边界采用漫射处理，随机生成一个0到1之间的数，并与穿透系数比较，若小于穿透系数，则漫穿透；若大于穿透系数，则漫反射。

# 2程序验证

采用前面介绍的动力型MC方法，模拟了室温L $\scriptstyle { T = 3 0 0 \mathrm { ~ K ~ } }$ ）下单层硅薄膜中声子输运过程，考虑了法向输运和面向输运两种情形，分别与解析结果进行对比，验证程序的正确性。

对于硅薄膜中的法向声子输运，为了方便与已有法向输运的结果[23]进行对比，采用声子灰色模型并作Debye 近似，单晶硅体材料的热物性参数如表1所示[24]。法向 $K n$ 数 (声子平均自由程与薄膜厚度之比）依次为0.035、0.35和3.5，统计宏观量的时间间隔分别为 $5 \times 1 0 ^ { - 1 3 }$ s、 $5 \times 1 0 ^ { - 1 3 }$ s和 $3 \times 1 0 ^ { - 1 4 }$ s，网格数目是400、40和40，计算总时间分别是 $6 \times 1 0 ^ { - 8 }$ （204号s、 $1 . 2 \times 1 0 ^ { - 9 }$ s和 $3 \times 1 0 ^ { - 1 1 }$ s，偏差能量粒子数目是6000万、3000万和4000万。法向声子输运的模拟结果如图2所示。图2(a)表明，稳态温度分布均近似为线性，但随着 $K n$ 的增大，在边界处的温度跳跃越明显，法向非平衡效应越强，热阻越大，因而法向有效热导率越小，如图2(b）所示。当前的温度分布和法向有效热导率的MC模拟结果均与文献中已有的数值和理论结果吻合很好。

表1硅晶体在 $\mathbf { 3 0 0 ~ K }$ 的热物理性质 Table 1 Thermophysical properties of Si crysta at 300 K X   

<html><body><table><tr><td>Ug/m.s-1</td><td>1/nm</td><td>Cv/(J/(m³K))</td><td>T/</td></tr><tr><td>6400</td><td>41.79</td><td>1.18×106</td><td>6.53810-12</td></tr></table></body></html>

对硅薄膜中的面向声子输运同样采用灰色模型并作Debye 近似。考虑Kn分别等于0.1、0.4、1和3的四种情形，统计宏观量的时间间隔均为 $5 \times 1 0 ^ { - 1 3 }$ （20s，网格尺寸依次为 $4 . 1 7 9 \times 1 0 ^ { - 9 }$ m、 $4 . 1 7 9 \times 1 0 ^ { - 9 }$ （204号m、 $2 . 0 8 9 5 { \times } 1 0 ^ { - 9 } \mathrm { ~ m }$ 和 $6 . 9 6 5 0 { \times } 1 0 ^ { - 1 0 } \mathrm { ~ m }$ ，偏差能量粒子数目分别为3亿、3亿、4亿和4亿。分别在薄膜横截面均匀设置100、25、20和20个网格进行宏观量的统计，MC模拟结果如图3所示。结果表明，截面热流分布偏离 Fourier定律描述的均匀分布，边界附近的热流受到抑制， $K n$ 越大，偏离 Fourier 定律的程度越大，当前数值结果与经典Fuchs-Sondheimer模型的解析解[25]吻合很好。

![](images/99f9d8e07ebb67deca5badfa6c5ce08cdbbc442ce25ec337e2203131e10b551b.jpg)  
图2室温下硅薄膜中的稳态法向声子输运的MC 模拟结 果：(a）不同Kn数下的无量纲温度分布，符号是当前的MC数 值结果，虚线是对应EPRT(EquationofPhononRadiative Transfer)的DOM(Discrete Ordinates Method)数值 解[23]；(b)薄膜法向有效热导率随 $\mathrm { K n }$ 的变化规律，离散的空 心方格点是当前的 MC 数值结果，实线是理论表达式[23] Fig. 2 MC results of cross-plane phonon transport through Si hin film at room temperature:(a)non-dimensional emperature distribution at different Kn,symbols are the resent MC results,whereas dashed lines are DOM(Discrete ordinates method) solution of EPRT(Equation of phonon radiative transfer);(b) effective cross-plane thermal conductivity of thin flm,squares are the present MC results, and solid line is theoretical result[23]

![](images/bebc00b6d751170df9ed19aba612cd4c0f28fad6091bd651b8f227b462d9710d.jpg)  
Fig.3 Non-dimensional heat flux distribution of in-plane phonon transport through Si thin film at room temperature: symbols are present MC results,whereas solid line is the theoretical results of Fuchs- Sondheimer model

上述结果表明，本文采用的动力型MC数值程序可以有效捕捉法向和面向声子输运的非平衡效应，因而可用于本文的双层薄膜界面声子输运研究。

![](images/f6360e607e087c151f0e91ba857215ffcb3b5d6d86b1a1085c1618f2d3e97cf4.jpg)  
图3室温下硅薄膜中的稳态面向声子输运的无量纲热流分布示意图：符号代表当前的 MC 模拟结果，实线为Fuchs-Sondheimer 模型的解析解[25]

# 3结果和讨论

# 3.1双层薄膜界面法向声子输运

对于双层薄膜材料界面法向的声子输运，Si/Al薄膜的总厚度为 $4 0 \ \mathrm { n m }$ ，在法向均匀设置 40 个网格进行宏观量的统计，统计宏观量的时间间隔为$5 \times 1 0 ^ { - 1 3 }$ s,网格尺寸为 $1 { \times } 1 0 ^ { - 9 } \mathrm { m }$ ，式(7)中 ${ T _ { \mathrm { e q } } } \mathrm { { = } } 3 0 0$ K，模拟选取的总计算时间为 $1 . 2 \times 1 0 ^ { - 9 }$ s，使用的偏差能量粒子数为9000万。MC 模拟的温度分布结果如图4所示。结果表明，在每种材料内，温度分布近似为线性，且在Si/Al界面处存在温度跳跃 $\Delta T$ 。基于界面热导的定义[4：

$$
G _ { \mathrm { K } } = { \frac { q } { \Delta T } }
$$

可计算获得界面热导值为 $G _ { \mathrm { K } } { = } 4 . 2 2 6 8 { \times } 1 0 ^ { 8 }$ $\mathrm { W / ( m ^ { 2 } K ) }$ ，和室温下 $\mathrm { S i / A l }$ 界面热导的实验值$3 . 4 5 4 5 9 \times 1 0 ^ { 8 } \mathrm { W / ( m ^ { 2 } K ) ^ { [ 1 3 ] } }$ 接近。这表明考虑真实色散关系和频谱界面穿透系数的DMM模型能够较准确地描述界面声子输运，也验证了新的MC数值模型的可靠性。

![](images/6fb0d836d84243498c5f8b37c3c111fd7a0bcbd4103b5907edc6ca856e517d8b.jpg)  
图4室温下 $\mathrm { S i / A l }$ 薄膜界面法向声子输运温度分布图：圆圈代表考虑真实色散关系和频谱穿透系数的 MC计算结果，Si/Al薄膜的总厚度为 $4 0 ~ \mathrm { n m }$   
Fig.4 Temperature distribution of cross-plane interfaciak phonon transport through Si/Al thin film at room temperature:circles are the MC results with exact phonon dispersion and frequency-dependent transmission coeficient.

The thickness of Si/Al thin film is $4 0 \ \mathrm { n m }$

# 3.2双层薄膜界面面向声子输运

对于双层薄膜材料界面面向的声子热输运，Si/Al薄膜总厚度为 $4 0 \ \mathrm { n m }$ ，在纵向均匀设置40个网格进行宏观量的统计，统计宏观量的时间间隔为 $3 \times 1 0 ^ { - 1 3 }$ s，网格尺寸为 $1 \times 1 0 ^ { - 9 } \mathrm { ~ m ~ }$ ，式（7）中$\scriptstyle { T _ { \mathrm { e q } } = 3 0 0 \mathrm { ~ K ~ } }$ ，模拟选取的时间上限为 $3 { \times } 1 0 ^ { - 1 1 }$ s，使用的偏差能量粒子数是8000万。MC模拟的截面热流分布结果如图5所示。结果表明，每种材料中的截面热流分布类似于单层薄膜中面向声子输运的截面热流分布，界面处热流比薄膜内部的热流更低，这

表明界面对声子输运的抑制作用与边界效果类似。  
另外，可以发现，截面热流分布在界面处是连续的。

![](images/0322ea02c9fbb95041f7bbab384f79773860d23f246f577f2c0d287d4d469eda.jpg)  
图5室温下Si/A1薄膜中界面面向声子输运的截面热流分布示意图：圆圈代表考虑真实色散关系和频谱穿透系数的 MC 计算结果，Si/Al薄膜的总厚度为 $4 0 ~ \mathrm { n m }$ （204号

Fig5 Heat fux distribution of in-plane interfacial phonon transport through Si/Al thin film: circles are the MC results with the exact phonon dispersion and frequency-dependent transmission coefficients.The thickness of Si/Al thin film is 40 nm

# 4结论

本文采用动力型声子MonteCarlo方法并引入考虑真实色散关系的DMM界面模型，建立了一个频谱穿透系数的界面声子输运介观数值模型。对室温下Si/A1双层薄膜法向和面向的界面声子输运进行了研究，界面法向声子输运中计算获得的界面热导与实验结果吻合良好，新的数值模型能准确捕捉法向输运的界面温度跳跃和面向输运的非均匀热流分布。本文工作可以很容易拓展至多层薄膜的界面声子热输运研究中。研究结果将促进对界面声子输运机理的认识。

# 参考文献

[1] CHEN Gang.Nanoscale Energy Transport and Conversion:A Parallel Treatment of Electrons,Molecules, Phonons,and Photons [M].New York:Oxford University Press,2005   
[2]GUO Yangyu,WANG Moran.Phonon Hydrodynamics and Its Applications in Nanoscale Heat Transport [J]. Physics Reports,2015,595:1-44   
[3]Little W.The Transport of Heat between Dissimilar Solids at Low Temperatures [J].Canadian Journal of Physics, 1959,37(3):334-349   
[4]Swartz E T,PohlR O.Thermal Boundary Resistance [J]. Reviews of Modern Physics,1989,61(3):605-668   
[5]BellisL D,PhelanPE,Prasher R S.Variations of Acoustic and Diffuse Mismatch Models in Predicting ThermalBoundary Resistance [J]. Journal of Thermophysics and Heat Transfer,2000,14(2):144-150 [6] CHEN Gang. Thermal Conductivity and BallisticPhonon Transport in the Cross-Plane Direction of Superlattices [J].Physical Review B,1998,57(23):14958   
[7] Reddy P,Castelino K,Majumdar A.Diffuse Mismatch Model of Thermal Boundary Conductance Using Exact Phonon Dispersion [J]．Applied Physics Letters，2005, 87(21): 211908   
[8] Norris P M,Hopkins P E.Examining Interfacial Diffuse Phonon Scattering through Transient Thermoreflectance Measurements of Thermal Boundary Conductance [J]. Journal of Heat Transfer,2009,131(4):043207 [9] Loh GC,Tay BK,Teo EHT.Flux-Mediated Diffuse Mismatch Model [J].Applied Physics Letters,2010,97(12): 121917   
[10] Duda JC,Beechem T E, Smoyer JL,et al. Role of Dispersion on Phononic Thermal Boundary Conductance [J]. Journal of Applied Physics,2010,108(7):073515   
[11] Minnich AJ,CHEN Gang,Mansoor S,et al.Quasiballistic Heat Transfer Studied Using the Frequency-Dependent Boltzmann Transport Equation [J].Physical Review B, 2011,84(23): 235207   
[12]Hopkins P E.Thermal Transport across Solid Interfaces with Nanoscale Imperfections: Effects of Rough ness，Disorder，Dislocations,and Bonding on Therma Boundary Conductance [J]. ISRN Mechanical Engineering,2013(2013): 682586 勿   
[13] Monachon C,Weber L，Dames C. Thermal Boundary Conductance: A Materials Science Perspective [J]. Annual Review of Materials Research2016, 46(1): 433-463   
[14] Ali H, Yilbas B S.Phonon Transport in Silicon-Diamond Thin Film Pairs: Consideration of Thermal Boundary Resistance Due to Cutoff Mismatch and Diffusive Mismatch Models [J]. Numerical Heat Transfer,Part A:Applications,2015,68(12):1307-1330   
[15]HUANG Meijiau,Tsai T-C,LIULiangchun,etal.A Fast Monte-Carlo Solver for Phonon Transport in Nanostructured Semiconductors [J]. Computer Modeling in Engineering and Sciences (CMES),2009,42(2):107-129   
[16] JENG Mingshan,YANG Ronggui,Song D,et al. Modeling the Thermal Conductivity and Phonon Transport in Nanoparticle Composites Using Monte Carlo Simulation [J].Journal of Heat Transfer,2008,130(4):042410   
[17] Péraud J-P M,Hadjiconstantinou N G.Efficient Simulation of Multidimensional Phonon Transport Using Energy-Based Variance-Reduced Monte Carlo Formulations[J].Physical Review B,2011,84(20): 205331   
[18] HUA Chengyun,CHEN Xiangwen,Ravichandran NK,et al.Fresnel Transmission Coefficients for Thermal Phonons at Solid Interfaces [J].arXiv preprint:150907806,2015   
[19]LI Xiaobo,YANG Ronggui.Effect of Lattice Mismatch on Phonon Transmission and Interface Thermal Conductance across Dissimilar Material Interfaces [J].Physical Review B,2012,86(5):054305   
[20]Hopkins P E,Reinke C M,Su M F,et al.Reduction in the Ihermal Conductivity of Single Crystalline Silicon byPhononic Crystal Patterning [J]. Nano Letters, 2011, 11(): 107-112 jStedman R,Nilsson G.Dispersion Relations for Phonons in Aluminum at 80 and $3 0 0 ^ { \circ } \mathrm { K }$ [J].Physical Review,1966, 145(2): 492-500   
[22] Péraud J-P M,Hadjiconstantinou N G.An Alternative Approach to Efficient Simulation of Micro/Nanoscale Phonon Transport [J].Applied Physics Letters，2012, 101(15): 153114   
[23] Majumdar A.Microscale Heat Conduction in Dielectric Thin Films [J].Journal of Heat Transfer,1993,115(1): 7-16   
[24] GUO Yangyu,WANG Moran.Lattice Boltzmann Modeling of Phonon Transport [J]. Journal of Computational Physics, 2016,315: 1-15   
[25] Turney JE, McGaughey A J H, Amon C H. In-Plane Phonon Transport in Thin Films [J]. Journal of Applied Physics, 2010,107(2): 024317