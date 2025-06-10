# 相变蓄能型联供系统最优相变温度研究

熊飞，张堙，王馨，张寅平（清华大学建筑技术科学系，北京，100084)

摘要：燃气轮机驱动的冷热电三联供系统是我国近年来大力鼓励发展的小型能源供应系统，将蓄能装置与联供系统结合对系统供能设备能起到减容增效的作用。本文建立了相变蓄能型联供系统的简化数学模型，提出了在给定实际用户负荷的情况下，以一次能耗最小为优化目标的最佳相变温度确定方法。典型算例分析表明，相变型烟气蓄热器的最优相变温度与用户负荷及设备性能相关，相比于NTU无限大，NTU有限大时，最优相变温度会升高，最小一次能耗会增大。

关键词联供;蓄能;相变温度;一次能耗中图分类号：TK16 文献标识码：A

# Optimal Phase Change Temperature for Energy Storage Based on :luctuating Loads in Building Cooling Heating and Power System

XIONG Fei, ZHANG Yin, WANG Xin, ZHANG Yinping Department of Building Science,Tsinghua University, Beijing looo84, China

Abstract: Natural gas driven Building Cooling Heating and Power (BCHP） system is encouraged to develop as small-scale energy supply system in recent year. In this paper, a thermodynamic model of BCHP system with phase change material (PCM) energy storage is established. According to practical user loads and considering the correspondingly hourly changing flow rate in charge and discharge processes, a simplified method is proposed to determine the optimal phase change temperature for BCHP-TES, aiming to minimize the primary energy consumption of BCHP-TES system. An illustrative example shows that the optimal phase change temperature can be obtained for given loads.It also indicates that compared to infinite NTU for PCM-TES， the optimal phase change temperature will increase as well as the corresponding minimal primary energy consumption for finite NTU.This work is of great importance for PCM optimization of BCHP-TES system design.

Key words: Tri-generation; Energy storage; Phase change temperature; Primary energy consumption

# 0前言

分布式供能系统具有能源效率高，污染物排放少，容量小，靠近用户等优点。基于能量梯级利用原理的冷热电联产系统是分布式系统的主要形式[1。多数情况下联产系统处于变工况运行模式，随着负荷的降低，各子系统性能均下降。为了改善系统性能，考虑将联供系统与蓄能装置结合，相对无蓄能的情况，系统节能率有所提高[2]。实际上，蓄能对联供系统节能率的影响与很多因素有关，有的系统加入蓄能后效果并不明显[3。对于“燃气轮机 $_ { \cdot } + { }$ 吸收机”的典型形式，蓄能的主要目的是改善系统变工况特性，使设备尽可能高效运行。相变蓄能是一种重要的蓄能方式，但在蓄能型联供系统中还有很多问题，如系统如何运行，何时蓄能，何时放能，相变蓄能的最优相变温度该如何确定。首先关于如何运行，也就是针对用户的典型日逐时负荷，怎么选取合适的高低峰分界线。相变温度的选取，不仅会影响烟气的流量，也会影响吸收机的COP和蓄能的总量。本文建立了相变蓄能型联供系统的简化数学模型，提出了在给定实际用户负荷的情况下，以一次能耗最小为优化目标的最佳相变温度确定方法，对于实际相变蓄能型联供系统设计具有一定参考意义。

# 1系统模型

# 1.1系统流程

以夏季工况为例，运行策略如图1、2。在低谷期，即用户侧负荷低于平均负荷时，从燃气轮机出来的烟气优先满足吸收机制冷（用户侧冷负荷)，多余的热量进入蓄能器进行蓄能，进入吸收机的烟气流量m是随

$$
\begin{array} { r l r l r l } { \dot { m } _ { 2 } } & { { } \quad } & { \dot { m } _ { 1 } } & { { } \quad } & { \dot { m } _ { 2 } = \dot { m } - \dot { m } _ { 1 } } \end{array}
$$

着用户侧的负荷逐时确定的，然后蓄能部分的烟气流量则是由确定的 。

![](images/89e57bba49d398ef4989d1e05c293a3c6a6f7361b6900dd837ff8edfd8335dc1.jpg)  
图1低谷期运行策略

![](images/558558f873e0dc85bc4196ba31805ec9e495da81d30feab1dd9c56a1adaf2cb9.jpg)  
Fig.1Operating Strategy in the off-peak period   
图2 高峰期运行策略  
Fig.2Operating Strategy in the peak period

对于高峰期，即用户侧负荷高于平均负荷时，燃气轮机的乏气全部进入尚不能满足用户侧的负荷要求，需要把低谷期蓄在蓄能器的热量取出来，取热流体采用从吸收机出来的烟气，温度为吸收机出口烟气温度 $\tau _ { a , o }$ 。取热流体和燃气轮机乏气混合后进入吸收机制冷，取热流体的流量 $\dot { m } _ { 3 }$ 由用户侧的负荷决定，不仅会影响吸收式制冷所消耗的热量，也会影响吸收机的 $\mathrm { C O P }$ 。

供给用户侧的能量：

低谷期:

$$
Q _ { c } { = } \dot { m } _ { 1 } c _ { p , a } ( T - T _ { a , o } ) C O P
$$

高峰期:

$$
Q _ { c } = Q \cdot C O P = ( { \dot { m } } + { \dot { m } } _ { 3 } ) c _ { p , a } ( { \frac { { \dot { m } } T + { \dot { m } } _ { 3 } T _ { d , o } } { { \dot { m } } + { \dot { m } } _ { 3 } } } - T _ { a , o } ) C O P
$$

# 1.2燃气轮机模型

热值为 $Q _ { g }$ 的天然气输入燃气轮机（发电效率 $\eta$ ），发出的电量 $P$ 直接供给用户。同时温度 $\tau _ { : }$ ，流量m的排烟流入吸收机发生器，作为高温热源驱动吸收式制冷循环。

对燃气轮机而言，由能量平衡得

$$
Q _ { g } - P = \dot { m } c _ { p , a } ( T - T _ { 0 } )
$$

燃气轮机采用变工况模型[4]，部分负荷运行时效率降低

$$
\frac { \eta } { \eta _ { e } } = 2 . 6 4 8 \frac { P } { P _ { e } } - 3 . 5 8 7 ( \frac { P } { P _ { e } } ) ^ { 2 } + 2 . 8 1 6 ( \frac { P } { P _ { e } } ) ^ { 3 } - 0 . 9 1 3 ( \frac { P } { P _ { e } } ) ^ { 4 }
$$

其中， $\eta _ { e }$ 为燃气轮机额定效率， $\eta$ 为实际效率， $P _ { e }$ 为额定功率， $P$ 为实际功率。根据排烟热量间的关系可得实际排烟温度 ${ { T } _ { 1 } }$ 与额定排烟温度 ${ T _ { 1 e } }$

$$
\frac { T _ { 1 } } { T _ { 1 e } } { = } \frac { 1 - \eta } { 1 - \eta _ { e } } \frac { \eta _ { e } } { \eta } \frac { P } { P _ { e } }
$$

# 1.3吸收机模型

从热力学原理上，吸收式制冷机可视为“热机 $^ +$ 热泵”的形式，吸收机的COP主要受发生温度 $\tau _ { g }$ 、蒸发温度 $T _ { e }$ 、冷凝温度 $T _ { c }$ 影响，为简化分析，用燃气轮机排烟温度取代发生温度，冷冻水供水温度取代蒸发温度，环境温度取代冷凝温度，则吸收机COP为

$$
C O P { = } { \mu ( 1 { - } { \frac { T _ { 0 } } { T _ { g } } } ) } { \frac { T _ { e } } { T _ { c } { - } T _ { e } } }
$$

其中 $\mu$ 为热力完善度。当燃气轮机满负荷运行时，即排烟温度为额定值时，吸收机发生温度最高，COP 达到最大值。假设 $T _ { g } { = } T { = } 7 7 3 \mathrm { K }$ ， ${ \cal T } _ { 0 } { = } { \cal T } _ { c } { = } 3 0 3 \mathrm { K }$ ， $T _ { e } { = } 2 8 0 \mathrm { K }$ ，并且假设该吸收机额定 $\mathrm { C O P { = } 1 . 2 }$ ，则可反求出热力完善度 $\mu { = } 0 . 1 6 3$ 。假定在变工况下， $\mu$ 保持不变，则可根据烟气温度求出吸收机实际的COP[5]。

# 1.4蓄能装置模型

蓄热时，燃气轮机乏气和蓄能介质换热满足方程：

$$
\frac { T - T _ { c , o } } { T - T _ { m } } = 1 - \exp ^ { - N T U }
$$

取热时，取热流体和蓄能介质换热满足方程：

$$
\frac { T _ { d , o } - T _ { a , o } } { T _ { m } - T _ { a , o } } { = } 1 { - } \mathrm { e x p } ^ { - N T U }
$$

其中， $\tau$ 为燃气轮机乏气温度， $T _ { m }$ 为待求相变温度，$\tau _ { c , o }$ 和 $\tau _ { d , o }$ 分别为蓄热和取热流体的出口温度， $\tau _ { a , o }$ 为烟气在吸收机出口的温度。一个周期内总蓄热量和取热量相等。

# 2 计算方法

低谷期，进入吸收机的烟气全部为经过燃气轮机后的高温烟气，因此吸收机的COP稳定为1.2。高峰期，进入吸收机的烟气为从燃气轮机出来的烟气和从蓄能器出来的取热流体的混合气体，温度会低于燃气轮机出口烟气温度，吸收机的效率会低于1.2，具体值按公式（6）计算。首先选取典型日逐时负荷的平均值划分高低峰，得出相应的燃气轮机烟气流量。在此条件下，由于高峰期的吸收机发生温度比低谷期的低，COP也低，使得蓄能器的蓄取不能平衡，会产生差值。通过优化燃气轮机烟气流量值m和蓄能器相变温度 $T _ { m }$ 的选取，使得蓄能器蓄取差值为零，此时燃气轮机烟气流量就是最小烟气流量，相变温度就是最优相变温度。

# 3 算例分析

选取北京某酒店夏季工况为例，给出了典型日逐时负荷，图3。设燃气轮机额定发电效率 $\eta _ { e } \mathrm { = } 3 5 \%$ ，烟气流出吸收机后温度 ${ T _ { a , o } } \mathrm { { = } } 4 5 3 \mathrm { { K } }$ ，烟气比容 $c _ { p , a } { = } 1 . 2 \mathrm { k J / }$ (kgK)，冷冻水供回水温度280K和 $2 8 5 ~ \mathrm { ~ K ~ } _ { \circ }$

![](images/77efd9cf50bf764b70615a0502778420fbf8b21de77d388f58029fe9d21ecb38.jpg)  
图3 典型日逐时冷负荷  
Fig.3A typical day hourly load

当NTU无限大时，计算得最小的燃气轮机烟气流量 $\dot { m } { = } 1 . 5 7 5 ~ \mathrm { k g / s }$ ，最优相变温度为 $T _ { m } { = } 5 8 6 \mathrm { ~ K ~ }$ 。可根据逐时冷负荷计算得到逐时燃气轮机的发电效率、发电量以及吸收机的COP。再根据电负荷的需求，确定买卖电量，从而确定典型日所需总的一次能耗（天然气热值)。多余的电量能够卖给大电网，则相应的一次能耗应该减去卖出电量所带来的收益。为了便于比较，将一次能源统一折算为天然气热值，即假设大电网是由天然气联合循环发电（效率 $5 5 \%$ )，则此时最小一次能耗为 $\phantom { - } 1 . 8 4 \times { 1 0 } ^ { 4 }$ kWh天然气，相比于分产系统，最大节能率为 $1 2 . 7 \%$ ，一次能耗随着相变温度的变化图4。

NTU有限时，最优相变温度会升高，最小一次能耗会增大，当 $N T U = 2$ 时，最优相变温度 $T _ { m } = 5 9 6 K$ ，最小一次能耗为 $1 . 8 5 \times { 1 0 } ^ { 4 } { \sf k W h }$ ，最大节能率为 $1 1 . 9 \%$ 。一次能耗和相变温度的变化关系如图4。

![](images/f89d37b2f8b3d1867322e6b5364e207e797010fec98f376a97d06dce4df887ff.jpg)  
图4 一次能耗随相变温度变化关系

Fig.4The relationship ofPEC and phase change temperature

# 4结论

本文提出了在给定实际用户负荷的情况下，以一次能耗最小为优化目标的最佳相变温度确定方法。对于给定的典型日逐时负荷，得出了最小一次能耗和最优相变温度，并和分产系统进行了对比，NTU无限大时，最大节能 $1 2 . 7 \%$ ，NTU $\scriptstyle \left[ = 2 \right.$ 时，最大节能 $1 1 . 9 \%$ 。NTU取有限值时，相比于NTU无限大，最优相变温度升高，最小一次能耗增大。在确定最优相变温度的同时，得到了一次能耗和相变温度的变化关系曲线，一次能耗高于最小一次能耗时，在最优相变温度左右两侧会存在两个相变温度对应着一个一次能耗。

# 参考文献

[1]刘爱国，张士杰，肖云汉．带蓄能装置的分布式热电冷联产系统优化配置[J]．热力发电,2010(06):14-20.  
LIU Aiguo,ZHANG Shijie,XIAO Yunhan Optimized Allocation ofDistributed Heat-electricity-cool Co-generation System  
[J],Thermal Power Generation 2010(06):14-20  
[2]冯志兵，金红光，燃气轮机冷热电联产系统与蓄能变工况特性[J]．中国电机工程学报,2006(4):25-30.  
FENG Zhibing,JINHongguang.Part-load Performance of CCHPwith Gas Turbine and Storage System [J]. Proceedings of the CSEE,2006,26(4): 25-30.  
[3]华贲.天然气冷热电联供能源系统[M].北京：中国建筑工业出版社,2010:6-7.  
HUABen Distributed Combined Cooling，Heating，and PowerGeneration System [M] 2010:6-7  
[4]黄纯浩．主动蓄能模式分布式供能系统集成[D]．中国科学院,2008.  
HUANG Chunhao.Integration of Active Storage DistributedEnergy System[D]. CAS,2008.  
[5]彦启森，石文星，田长青.空气调节用制冷技术[M].北京:中国建筑工业出版社,2010.  
YAN Qisen， SHI Wenxing， TIAN Changqing. RefrigerationTechnique for Air Conditioning [M]. Beijing: China Architecture &Building Press: 170-171.