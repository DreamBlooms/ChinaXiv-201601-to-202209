# 声功多级放大型环路热声制冷系统模拟研究

徐静远1,2 胡剑英¹　张丽敏¹　罗二仓1(1.中国科学院理化技术研究所低温工程学重点实验室，北京100190;2．中国科学院大学，北京100049)

摘要环路多级热驱动制冷系统因结构紧凑、潜在效率高等优点在大然气液化及再冷凝方面有艮好应用前景。本文提出一种能实现声功多级放大的环路热驱动制冷系统，在天然气液化温度下能够获得千瓦级冷量及较高的热致冷转换效率。基于经典热声理论对三单元环路系统展开了数值模拟。首先，考察了优化结构下声功的沿程分布。接着，将该结构与多脉管结构进行对比。结果表明，前者不仅具有结构简单，冷量方便获取等优势，同时也能获得与后者相媲美的系统性能。此外，进一步考察了谐振管面积比、谐振管长度、加热温度等重要参数对系统性能的影响。研究结果表明，在平均压力为 $7 \ \mathrm { M P a }$ ，加热温度为923K时，该系统能够获得1478W制冷量，相当于 $1 2 . 4 \%$ 相对卡诺效率。本文对后续实验工作具有重要指导意义。

关键词环路三级；热声；脉管制冷机；声功多级放大中图分类号：TK123 文献标识码：A 文章编号:0253-231X(2017)08-1597-06

# A Novel Multi-stage Traveling Wave Thermoacoustically Driven Cryocooler Capable of Multi-stage Power Amplification

XU Jing-Yuan $^ { 1 , 2 }$ HU Jian-Ying1 ZHANG Li-Min1 LUO Er-Cang1 (1.Key Laboratory of Cryogenics,Chinese Academy of Sciences，Beijing 10o190,China; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49,China)

AbstractLooped multi-stage thermacoustically driven cryocoolers are considered as promising candidates for applications in liquefaction and recondensation of natural gas.This paper introduces a new configuration capable of cascade power amplification, which could achieves kW-class cooling power and high thermal-to-cold effciency at natural gas liquefaction temperature. Based on the classic thermoacoustic theory,a three-stage system is numerically investigated. Firstly,the axis distributions of the acoustic power are presented. Then， a comparison is made between this configuration and the previous multiple-coolers configuration The result shows that，this configuration not only has an advantage of structural simplicity and cooling easy-access,but also comparable to the previous configuration in system performance.In addition, emphasis is put on the influence of some key parameters such as area ratio of resonance tube,resonance tube length and heating temperature, which are found to be critical to the engine performance According to the calculation results,a cooling power of 1478 W and a global exergy efficiency of $1 2 . 4 \%$ is achieved with 923 K heating temperature and 7 MPa pressurized helium gas. This paper provides significant guidance for future experimental work.

Key wordslooped three-stage; thermoacoustic; pulse tube cooler; cascade power amplification;

# 0引言

环路多级行波热声发动机是一种新型的热声装置，越来越受到广泛的关注。相比于传统热声发动机，该结构具有以下三个明显的优势：1）功率密度高。该结构采用直径较小的谐振管将发动机连成环路，避免了传统热声发动机中体积较大的谐振管，较大地提高了发动机的功率密度。有研究表明，一个典型的传统热声发动机[1]谐振管内的能量密度（声功与横截面积的比）仅为 $8 6 0 \ \mathrm { k W / m ^ { 2 } }$ ，而同等功率量级的环路热声发动机[2]可以达到 $7 0 5 4 ~ \mathrm { k W / m ^ { 2 } }$ 2)潜在效率高。环路结构的存在使得发动机回热器能够工作在行波声场下，且上一单元的声功能够被下一单元回收；3）功率易调节。根据对输出功率的需求，环路中可串联不同数目的发动机单元。2010年，DeBlok首次提出环路多级行波热声发动机的概念，并对环路四级系统进行了可行性验证[3]。根据环路多级热声发动机所接负载为直线发电机或脉管制冷机，可组成环路行波热声发电系统或环路行波热声制冷系统。对于前者，经过对环路三级发电系统的研究与改进[4]，本课题组最终获得了 $4 . 6 9 \mathrm { ~ k W }$ 的发电量及 $1 8 . 4 \%$ 的热电转换效率[5]。但是，直线发电机存在运动部件，降低了发电系统的可靠性，且对各部件一致性要求较高。与此相比，环路行波热声制冷系统无任何运动部件，可靠性高，在天然气液化领域有很大的应用潜力及研究价值。2012年，DeBlok将环路四级热声发动机中一个发动机单元换成了制冷机单元，搭建了一台小温差环路热声制冷系统[6]。然而，该系统在制冷温度为 $2 2 7 . 5 \mathrm { ~ K ~ }$ 时仅获得95.4W 的制冷量，且无法达到天然气液化温区。与这种结构不同，本课题组提出一种脉管制冷机旁接结构,并以在液化天然气温区获得千瓦级冷量为设计目标[7-10]。2015 年，我们搭建了一台旁接多个脉管制冷机的环路三级热声制冷系统 (多脉管结构)，在$1 1 0 \mathrm { ~ K ~ }$ 获得了 $1 . 2 \mathrm { ~ k W }$ 制冷量及 $8 \%$ 的整机相对卡诺效率[2]，这是目前同类热驱动制冷系统所获得的最高效率。但是，这种结构存在多个脉管制冷机，导致制造成本较高，且对冷量集中获取较为困难。本文提出一种声功多级放大型环路热声制冷系统，它不仅能高效地在天然气液化温区获得千瓦级冷量，而且在结构上弥补了多脉管结构的不足，因此具有较高的实用价值。本文采用基于热声理论的Sage软件对整机系统进行了数值模拟，重点考察了系统内在机理及重要参数。

# 1系统结构

图1为声功多级放大型环路三级热声制冷系统的示意图[11]。如图所示，三个完全相同的热声发动机通过谐振管串联成环路，一个脉管制冷机旁接于最后一级发动机单元的次水冷出口处。热声发动机单元由主水冷器、回热器、加热器、热缓冲管、次水冷器组成，脉管制冷机单元由主水冷器、回热器、冷头、脉冲管、层流化丝网、惯性管和气库组成。谐振管直径从小到大变化，长度均相等。特别地，需在发动机内放置隔直流膜用来抑制因环路结构产生的Gedon 直流[12]。在本文中，对直流的讨论不作为研究的重点。

系统工作的原理如下：加热器与热源相连形成高温端，水冷器经过水冷形成室温端。因此，发动机回热器中存在温度梯度。当该温度梯度超过临界梯度时系统起振，回热器内部工作气体与其内的固体填料产生热声效应，声功被放大。声功的传递方向如图所示：从 $^ { 3 \# }$ 谐振管回收的声功传递到1#热声发动机中，在回热器中第一次放大，声功传递到2#热声发动机中第二次放大，接着传递到3#热声发动机中第三次放大；最终部分声功传递到制冷机中被消耗，剩余的声功被回收至1# 热声发动机中重复以上过程。由于声功被多次放大，不同谐振管中传递的声功大小不同，因此谐振管的横截面积相应不同。

![](images/aa82fd0c556eca5517c17e0c01c26d8c7b23428b44c453d8e5c762838f412dda.jpg)  
Fig.1 Schematic diagram of a looped three-stage thermoacoustically driven cryocooler capable of multi-stage power amplification

1.隔直流膜；2.发动机主水冷器；3.发动机回热器；4.加热器； 5.热缓冲管；6.次水冷器；7.谐振管；8.制冷机主水冷器; 9.制冷机回热器；10.冷头；11.脉冲管；12.层流化丝网; 13.惯性管；14.气库

# 图1环路三级声功逐级放大型热声制冷系统

# 2 计算模型

# 2.1 计算方法

计算基于 Sage 软件[13]展开。它是一种采用图形化界面的软件，可用于计算交变流动热力系统的动力学特性和热力学特性。它在指定的几何边界条件下对动量方程、连续性方程和能量方程进行求解，得到压力波动、质量流率及温度分布，并以三阶甚至更高阶的形式表示。根据计算得到的波动量及热力参数，考察热声系统的特性与性能。

# 2.2优化结构尺寸

首先在一个典型的工况下对整机系统进行优化设计：平均压力 $7 \mathrm { M P a }$ ，热端温度 $9 2 3 \mathrm { ~ K ~ }$ ，水冷温度$2 9 3 \mathrm { K }$ ，制冷温度 $1 1 0 \mathrm { K }$ (天然气液化温度)。优化过程中，热声发动机单元的尺寸与文献[2]相同，重点对谐振管的尺寸及脉管制冷机尺寸进行优化。由于制冷量及整机相对卡诺效率均能在一定程度上体现制冷系统的性能，因此将两者作为优化目标进行综合考量。其中，整机相对卡诺效率为

$$
\begin{array} { r } { \eta _ { \mathrm { e x } } = } \\ { Q _ { \mathrm { c } } \left( \displaystyle \frac { T _ { 0 } } { T _ { \mathrm { c } } } - 1 \right) } \\ { \displaystyle \frac { T _ { 0 } } { Q _ { \mathrm { h 1 } } \left( 1 - \displaystyle \frac { T _ { 0 } } { T _ { \mathrm { h 1 } } } \right) + Q _ { \mathrm { h 2 } } \left( 1 - \displaystyle \frac { T _ { 0 } } { T _ { \mathrm { h 2 } } } \right) + Q _ { \mathrm { h 3 } } \left( 1 - \displaystyle \frac { T _ { 0 } } { T _ { \mathrm { h 3 } } } \right) } } \end{array}
$$

其中， $T _ { \mathrm { h } }$ 为加热温度， $Q _ { \mathrm { h } }$ 为加热量，下标的数字表示发动机单元的编号， $T _ { 0 }$ 为水冷温度， $T _ { \mathrm { c } }$ 为制冷温度， $Q _ { \mathrm { c } }$ 为制冷量。

优化后主要部件的尺寸如表1所列。发动机回热器填有丝径为 $5 ~ { \mu \mathrm { m } }$ 、孔隙率为 $8 4 \%$ 的150目不锈钢。制冷机回热器填有丝径为 $3 1 ~ \mu \mathrm { m }$ 、孔隙率为$7 0 \%$ 的300目不锈钢。制冷机调相机构为一根直径$1 2 ~ \mathrm { m m }$ 、长度 $1 . 9 \mathrm { ~ m ~ }$ 的铜管和 $^ \textrm { \scriptsize 1 L }$ 气库。

# 3计算结果

# 3.1声功沿程分布

图2为系统声功沿程分布图。图中横坐标起始于#1热声发动机的主水冷器，经过#1热声发动机单元和#1谐振管，经过#2热声发动机单元、 $\# 2$ 谐振管、 $\# 3$ 热声发动机单元，最后止于#3谐振管；脉管制冷机起始于旁接点处。可以看出，声功经过三次放大，最终一次性输出： $1 . 5 2 ~ \mathrm { k W }$ 声功从3# 发动机单元被回收，传递到1#发动机回热器中被第一次放大至 $3 . 9 2 ~ \mathrm { k W }$ ；放大的声功在1# 谐振管中消耗至 $3 . 2 1 ~ \mathrm { k W }$ 后传递到 $^ { 2 \# }$ 发动机回热器中，被第二次放大至 $7 . 7 ~ \mathrm { k W }$ ；接着声功在 $^ { 2 \# }$ 谐振管中消耗至 $5 . 3 7 ~ \mathrm { k W }$ 后传递到 $^ { 3 \# }$ 发动机回热器中，第三次放大至 $1 1 . 7 5 ~ \mathrm { k W }$ ；完成三次放大的声功分为两路传递：约 $8 3 ~ \mathrm { k W }$ 声功传递到制冷机冷头进行泵热，产生1478W 制冷量；剩余 $1 . 5 2 ~ \mathrm { k W }$ 声功经过 $^ { 3 \# }$ 谐振管被回收到#1热声发动机单元中，重复以上过程。第一级到第三级回热器中声功放大倍数依次为2.57、2.39、2.18，即声功每经过一次放大后，放大的倍数会降低。因此，如果需要串联更多的热声发动机，则需要考虑放大倍数降低带来的影响。

表1系统主要部件尺寸  
Table 1 Structure dimensions of the main components   

<html><body><table><tr><td></td><td>部件</td><td>尺寸 (直径×长度)</td><td>特性</td></tr><tr><td rowspan="3">发动机单元</td><td>主水冷器</td><td>80×6</td><td>孔隙率39.8%，翅片间隙0.5</td></tr><tr><td>回热器</td><td>80 ×60</td><td>150目不锈钢丝网</td></tr><tr><td>热缓冲管</td><td>80 × 125</td><td>壁厚6</td></tr><tr><td rowspan="3">制冷机单元</td><td>主水冷器</td><td>120 × 64</td><td>孔隙率 26%，翅片间隙0.4</td></tr><tr><td>回热器</td><td>120×7</td><td>300目不锈钢丝网</td></tr><tr><td>脉冲管</td><td>37×15</td><td>壁厚2</td></tr><tr><td rowspan="3">谐振管</td><td>1#</td><td>21 × 3600</td><td></td></tr><tr><td>2#</td><td>26×3600</td><td>壁厚1.5</td></tr><tr><td>3#</td><td>17 × 3600</td><td></td></tr></table></body></html>

注：表格中参数的单位均为毫米(mm)

![](images/60849def393733807d39831b922bb819272f6607a7f2410798f8233e7009fe2b.jpg)  
图2系统声功沿程分布图  
Fig.2 Axis distribution of acoustic power in the system

表2声功多级放大型与多脉管结构的热力性能对比  
Table 2 Comparisons between novel configuration and multiple-coolers configuration on global performance   

<html><body><table><tr><td rowspan="2">结构类型</td><td rowspan="2">频率/Hz</td><td colspan="2">加热量/W</td><td colspan="2">制冷量/W</td><td rowspan="2">整机效率/%</td></tr><tr><td>单元加热量</td><td>总加热量</td><td>单元制冷量</td><td>总制冷量</td></tr><tr><td rowspan="2">声功多级放大型</td><td rowspan="2">55.4</td><td>4955</td><td rowspan="2">29000</td><td>1</td><td rowspan="2">1478</td><td rowspan="2">12.42</td></tr><tr><td>9427 14620</td><td></td></tr><tr><td rowspan="3">多脉管结构</td><td rowspan="3">55.7</td><td>8170</td><td rowspan="3">24510</td><td>417</td><td rowspan="3">1251</td><td rowspan="3">12.46%</td></tr><tr><td></td><td>417</td></tr><tr><td>8170 8170</td><td>417</td></tr></table></body></html>

# 3.2与多脉管结构的对比研究

声功多级放大型制冷系统的性能如表2所示。在前期研究中，我们对多脉管结构系统 (图3)进行了数值模拟及实验研究，文献2表明了SAGE软件对计算结果的可靠性。而在本文模拟的新型结构中，模拟软件、各部件模型、参数设置、边界条件等均与文献2中多脉管结构一致，因此模拟结果也具备可靠性。我们将两种结构的热力性能进行了对比分析。为了公平对比两种结构的性能，我们设定两者系统频率及工况相等，并保持热声发动机单元的尺寸一致。从表中可以看出，两种结构的整机效率基本相等，但由于总加热量的差异，声功多级放大型结构可获得更多制冷量。进一步观察可以发现，该结构中1# ${ \sim } 3$ #发动机单元的加热量依次增加。相应地，

![](images/f6e5e6f8ee019d5bbaee4dd875ed404c400e83ddb8099741dd2693124a635a76.jpg)  
图3系统声功沿程分布图

1.隔直流膜；2.发动机主水冷器；3.发动机回热器；4.加热器; 5.热缓冲管；6.次水冷器；7.谐振管；8.制冷机主水冷器; 9.制冷机回热器；10.冷头；11.脉冲管；12.层流化丝网； 13.惯性管；14.气库

Fig.3 Schematic diagram of an existing multiple-cooler thermoacoustically-driven cooling system

如果进一步改变每一发动机单元的面积，则性能将有进一步提升的空间。目前多脉管结构已经获得同类型系统在天然气液化温区报道的最高效率，而计算显示声功多级放大型结构可以获得与之相媲美的系统性能，并且在冷量收集、结构复杂度、制造成本等方面更具优势。因此，声功多级放大型结构具有更大的发展潜力与实用价值。

# 3.3重要参数的影响

系统的性能好坏与运行工况及结构参数密不可分。本节进一步探究谐振管尺寸与加热温度对系统性能的影响。

3.3.1谐振管尺寸的影响 谐振管除了为发动机单元提供合适的阻抗，还用来传递声功。对于本系统来说，由于声功经过多级放大，在不同谐振管中大小不同。理论上，谐振管的面积应该随着声功的增加相应增大，即3#谐振管面积最小，1# 谐振管次之，2#谐振管最大。由于每个热声发动机的回热器温度梯度相同，声功基本以相近倍数放大。模拟中，我们假定谐振管面积依同等倍数增加，引入谐振管面积比 $A _ { \mathrm { r e s } }$

$$
A _ { \mathrm { r e s } } = { \frac { A _ { \mathrm { r e s 2 } } } { \mathrm { A } _ { \mathrm { r e s 1 } } } } = { \frac { A _ { \mathrm { r e s 1 } } } { \mathrm { A } _ { \mathrm { r e s 3 } } } }
$$

图4给出了不同谐振管面积比时系统的总制冷量和整机相对卡诺效率。可以看出，谐振管面积比对系统性能有显著的影响。其中，最大制冷量和最大相对卡诺效率对应不同的谐振管面积比。为了保证制冷量和效率均处于较大值，谐振管面积比应取在两者最大值对应的面积比之间，过大或者过小的面积比均会降低整机性能。如图所示，该系统中合适的谐振管面积比为 $1 . 2 { \sim } 1 . 7$ ，在优化的结构中选取为1.53。另外，谐振管长度对系统性能具有一定的影响。如图5所示，最大制冷量和整机效率对应的谐振管长度非常接近，在优化结构中选取为 $3 . 6 \mathrm { ~ m ~ }$ 。

![](images/ff878094036d051001de876bb2c34b9a14ae5fa6b030efe77f655cfcab2cde23.jpg)  
图4谐振管面积比对整机性能的影响(谐振管长度为 $3 . 6 ~ \mathrm { m } _ { . } ^ { \cdot }$ 1Fig.4 Thedependence of global performance on theresonance tube area-ratio (The resonance tube length is $3 . 6 \mathrm { ~ m } ^ { \cdot }$ ）

![](images/3ad1d571f154e9a3c93f803b2098ecf819a03424549942f26a21136f6664365d.jpg)  
图5谐振管长度对整机性能的影响 (谐振管面积比为1.53) Fig.5 The dependence of global performance on the resonance tube length (The resonance tube area-ratio is 1.53)

3.3.2热温度的影响 加热温度作为一个重要的工况参数，对系统的性能有着很大的影响。上节针对高品位能源的利用，主要考察了三个加热温度为同一高温时的系统性能。实际应用中，该热声系统还能够有效利用如工业余热、废热等低品位能源。对于同一工业设备的不同工序，所产生的烟气温度不相同,存在高温烟气 $\mathrm { ( > 6 0 0 ^ { \circ } C ) }$ 、中温烟气 $\mathrm { ( 2 3 0 { \sim } 6 0 0 ^ { \circ } C ) }$ 和低温烟气 $\mathrm { ( < 2 3 0 ^ { \circ } C ) }$ ）等。本节重点考察了变温热源时的系统性能，即将热源视为三种不同温度的工业烟气，各自通过一台热声发动机中加热器；每一股烟气在各自加热器中释放热量，产生较高的加热温度。依据实际经验，三种加热温度取为923K、803K、683K，并存在不同组合的可能性。

表3为不同温度热源下系统的性能。可以看出，当 $^ { 3 \# }$ 发动机加热器与温度最低的热源相连时，系统整机性能较好；当 $^ { 3 \# }$ 发动机加热温度最高时，制冷量则大幅度下降，极大降低了系统性能。当 $1 \# { \sim } 3 \#$ 热声发动机加热温度依次为 $9 2 3 \mathrm { ~ K ~ }$ 1 $8 0 3 \textrm { K }$ 、 $6 8 3 \mathrm { ~ K ~ }$ 时，整机系统可以获得691W的制冷量及 $1 2 . 7 7 \%$ 的整机相对卡诺效率，展现了在低品位能源利用方面

良好应用前景。

表3不同热源温度下的整机系统性能Table 3 Global system performance underdifferent heat source temperatures  

<html><body><table><tr><td colspan="3">加热温度/K</td><td rowspan="2">制冷量/ W</td><td rowspan="2">整机相对卡 诺效率/%</td></tr><tr><td>Th1</td><td>Th2</td><td>Th3</td></tr><tr><td>923</td><td>803</td><td>683</td><td>691</td><td>12.77</td></tr><tr><td>923</td><td>683</td><td>803</td><td>516</td><td>13.29</td></tr><tr><td>803</td><td>923</td><td>683</td><td>637</td><td>13.15</td></tr><tr><td>803</td><td>683</td><td>923</td><td>307</td><td>12.89</td></tr><tr><td>683</td><td>923</td><td>803</td><td>416</td><td>13.69</td></tr><tr><td>683</td><td>803</td><td>923</td><td>273</td><td>12.81</td></tr></table></body></html>

# 4结论

本文提出了一种应用于天然气液化温区的声功多级放大型环路行波热声制冷系统。它不仅保留了环路热声系统的潜在效率高、功率密度大、可靠性高等优点，还能够实现声功的多级放大与大功率的单一输出。相对于目前在同温区已取得较高效率的多脉管结构而言，该系统不仅能够获得与之媲美的整机性能，同时由于脉管制冷机的减少使得结构更简单，制造成本更小。本文在天然气液化温区对三级系统进行了数值模拟，研究得出以下几点结论：

1）根据声功沿程分布得出，声功经过三次放大后一次输出，且声功放大倍数随着次数依次降低;2)声功多级放大型结构可以获得与多脉管结构相媲美的系统性能。3）提出对系统性能影响较大的参数—谐振管面积比，存在一个取值区间使得系统性能较好；谐振管长度对整机性能影响显著；4）对利用低品位能源时，多种加热温度组合进行模拟：变温热源下，当最后一级发动机加热温度最低时，系统整机性能较好；当最后一级发动机加热温度最高时，制冷量大幅度下降;5）平均压力为 $7 \ \mathrm { M P a }$ 、加热温度为 $6 5 0 ^ { \circ } \mathrm { C }$ 时，该系统能够获得1478W的制冷量，相当于 $1 2 . 4 \%$ 的整机相对卡诺效率。

系统还存在优化空间。同时，相关的实验研究为下一步工作的重点。

# 参考文献

[1]DAI Wei,LUO Ercang,HU Jianying,et al.A Heat-driven Thermoacoustic Cooler Capable of Reaching Liquid Nitro

gen Temperature [J].Applied Physics Letters,2005,86:   
224103 [2] ZHANG Limin，HU Jianying，WU Zhanghua,et al. A 1 kW-class Multi-stage Heat-driven Thermoacoustic Cryocooler System Operating at Liquefied Natural gas Temperature Range [J].Applied Physics Letters,2015,   
107:033905 [3]Kees D B.Novel 4-stage Traveling Wave Thermoacoustic Power Generator [C]//International Conference on Nanochannels and Minichannels,2010 [4]WUZhanghua,YUGuoyao,ZHANGLimin,etal.Development of a 3kW Double-acting Thermoacoustic Stirling Electric Generator [J].Applied Energy，2014,136:866-   
872 [5] BI Tianjiao，WU Zhanghua,ZHANG Limin，et al. Development of a 5kW Traveling-wave Thermoacoustic Electric Generator [J]．Applied Energy，2015, http://dx.doi.org/10.1016/j.apenergy.2015.12.034 [6]Kees D B.Multi-stage Traveling Wave Thermoacoustics in Practice [C]//19th International Congress on Sound and Vibration,Vilnius,2012 [7] TONG Huan,HU Jianying,ZHANG Limin,et al. Experimental Study of an Acoustic Resonant Cooling System [J].Physics Procedia,2015,67:445-450 [8] XU Jingyuan，HU Jianying，ZHANG Limin，et al. Effect of Coupling Position on a Looped Three-stage Thermoacoustically-driven Pulse Tube Cryocooler [J].Energy,2015,93:994-998 [9]XU Jingyuan,ZHANG Limin,HU Jianying,et al.An Efficient Looped Multiple-stage Thermoacoustically-Driven Cryocooler for Liquefaction/Recondensation of Natural Gas[J].Energy,2016,112:804-809   
[10]徐静远，张丽敏，胡剑英等.环路三级热驱动制冷系统的理 论与实验研究[C]//第十二届全国低温工程大会会议集，南 京，2015 XU Jingyuan,ZHANG Limin,HU Jianying,et al. TheoreticalAnalysis and Experimental Verification of a Threestage Thermoacoustically Driven Pulse Tube Cryocooler System[C] //Proceeding of the 12th National Conference on Cryogenic Engineering，Nanjing,2015   
[11]罗二仓，徐静远，胡剑英等.一种声功多级放大的行波热声 发动机系统：中国，CN104775932A[P].2015-7-15 LUOErcang,XU Jingyaun,HU Jianying,et al.AcousticPowerMulti-stage Amplification Traveling-wave Thermoacoustic Engine System:China,CN104775932A [P]. 2015-7-15   
[12]Gedeon D.DC Gas Flow in Stirling and Pulse-tube Cryocoolers [J].Cryocooler,1997,9:385-392   
[13] Gedeon D.SAGE:Object-oriented Software for Cryocooler Design [C]//Proceedings of 8th International Cryocooler Conference,1995:281-292