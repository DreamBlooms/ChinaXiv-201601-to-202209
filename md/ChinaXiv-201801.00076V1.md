编号：161191

# 直接式 $\mathbf { S } \mathbf { - C O } _ { 2 }$ 塔式太阳能热发电系统光-热-功一体化热力学分析

朱含慧，王坤，何雅玲\*

（西安交通大学 热流科学与工程教育部重点实验室，陕西，西安，710049)

摘要：本文将简单回热，预压缩，再压缩，部分冷却和中间冷却超临界二氧化碳（ $\mathbf { S - C O } _ { 2 }$ ）布雷顿循环分别与塔式太阳能热发电（SPT）系统结合，建立了直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统的光-热-功一体化模型，对 5 种 $\mathbf { S - C O } _ { 2 }$ 循环下整个SPT系统在不同透平入口温度下的热力学性能进行了对比分析。结果表明：随着透平入口温度的增大，整个SPT系统的效率在650 $^ { \circ } \mathrm { C }$ 附近具有最大值，表明直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统的运行温度并非越高越好；在本文研究的透平入口温度范围内（ $5 0 0 { \sim } 8 0 0 ^ { \circ } \mathrm { C } )$ ，中间冷却和部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环下的SPT系统具有最高的效率，但系统也最为复杂；再压缩 $\mathbf { S - C O } _ { 2 }$ 循环下的 SPT系统在高温范围（650\~800 $^ { \circ } \mathrm { C }$ ）具有较高的效率，且系统比较简单，具有巨大的应用潜力。

关键词：直接式系统； $\mathrm { S - C O } _ { 2 }$ 循环；塔式太阳能热发电；一体化建模；热力学性能中图分类号：TK124 文献标识码：A

# Thermodynamic Analysis of Solar Thermal Power Tower Systems Integrated with the Direct-heated Supercritical $\mathbf { C O } _ { 2 }$ Brayton Cycles

ZHUHan-Hui WANG Kun HE Ya-Ling

KeyLaboratoryofThermo-Fluid ScienceandEngineringofMinistryofEducation,SchoolofEnergyandPowerEnginering,

Xi'an Jiaotong University,Xi'an, Shaanxi,710o49, China)

Abstract: In this paper, a complete mathematical model is developed for the solar power tower (SPT) system integrated with five different direct-heated supercritical $\mathrm { C O } _ { 2 }$ 0 $\mathrm { \ S - C O } _ { 2 } )$ ）Brayton cycles (simple,precompression,recompression,partial-cooling,and intercooling) respectively,and the effect of turbine inlet temperature (TIT) on the thermodynamic performances of the integrated SPT systems is investigated and compared among these cycles.The results reveal that the overall efficiencies do not increase with TIT monotonically but show a parabolic tendency with maximum values around the TIT of $6 5 0 ~ ^ { \circ } \mathrm { C }$ ,which shows that it is not necessary to pursue excessively high TIT for the direct-heated integrated SPT systems. Furthermore, the intercooling and the partial-cooling $\mathbf { S - C O } _ { 2 }$ cycles achieve the highest overall efficiencies at the TIT of $5 0 0 { \sim } 8 0 0 ~ ^ { \circ } \mathrm { C } ,$ ， whereas the corresponding cycle configurations are more complicated. The recompression $\mathrm { \bf S - C O } _ { 2 }$ cycle with relatively simple cycle configuration has higher overall efficiencies when the TIT is at $6 5 0 { \sim } 8 0 0 ^ { \circ } \mathrm { C }$ ,making it become an attractive candidate for SPT system applications.

Keywords: direct system; $\mathbf { S - C O } _ { 2 }$ Brayton cycles; solar power tower; complete mathematical model; thermodynamic performances

# 0

# 引言

作为一种太阳能资源大规模利用的有效方式，塔式太阳能热发电（SolarPowerTower，SPT）得到了越来越多的关注和发展，然而与传统化石能源发电系统相比，其发电成本仍然较高。在整个SPT系统中，动力循环子系统是将太阳能转化为高品位电能的最终环节。采用高效紧凑的动力循环形式是提高整个SPT系统效率、降低发电成本的有效途径。$\mathbf { S - C O } _ { 2 }$ 布雷顿循环相比传统蒸汽朗肯循环具有循环效率高、设备尺寸小，系统紧凑、且易实现干冷等优点[1]，因此在太阳能热发电系统中发展 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环是一个新的研究热点。

$\mathbf { S - C O } _ { 2 }$ 布雷顿循环在SPT系统中的应用主要有间接式和直接式两种：在间接式系统中， $\mathbf { S - C O } _ { 2 }$ 只作为动力循环子系统的作功工质，熔盐等其他工质作为吸热器中的传热流体，吸热器与动力循环子系统之间通过中间换热器连接；在直接式系统中，S-$\mathrm { C O } _ { 2 }$ 既作为动力循环系统的作功工质，又作为吸热器中的传热流体。由于熔盐等工质允许使用温度有限，限制了SPT系统效率的进一步提高，而 $\mathbf { S - C O } _ { 2 }$ 在高温下具有很好的稳定性，因此直接式 $\mathbf { S - C O } _ { 2 }$ 系统可以实现更高的运行温度，能够进一步提高系统效率。国内外学者已经开始对直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统开展了一些研究，例如，Turchi等[2]将再压缩、部分冷却及中间冷却等几种 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环（带再热）应用于聚光太阳能热发电系统，在干冷条件下对几种 $\mathbf { S - C O } _ { 2 }$ 循环的性能进行了研究，结果显示，部分冷却和中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环在干冷条件下仍可实现 $50 \%$ 以上的热效率。

Chacartegui等[3]将 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环和有机朗肯循环进行了组合，研究这种复合循环在塔式太阳能热发电系统中应用时的热力学性能，结果表明这种组合循环是可行的，但效率的提高幅度不大。Padilla等[4]将4种 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环与塔式太阳能热发电系统结合，并对每种循环在无再热和再热情况下分别进行了烟分析，但在他们的研究中，吸热器仅被当成一般形式的热源为 $\mathbf { S - C O } _ { 2 }$ 循环提供热量，其所具有的特殊性没有被考虑。

可见，直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统的相关研究较少，且仅局限于 $\mathbf { S - C O } _ { 2 }$ 布雷顿动力循环自身性能的分析，没有对包括吸热器在内的整个直接式 $\mathbf { S - C O } _ { 2 }$ 太阳能热发电系统的热力学性能进行研究。因此，本文针对直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统（包括定日镜场、吸热器、蓄热子系统以及动力循环子系统）建立了光-热-功一体化完整模型，在此基础上，对简单回热、预压缩、再压缩、部分冷却和中间冷却5种 $\mathbf { S - C O } _ { 2 }$ 循环形式下SPT系统的热力学性能进行了对比分析。

# 1系统介绍

本文研究的直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统主要由定日镜场、 $\mathbf { S - C O } _ { 2 }$ 吸热器、熔盐蓄热子系统以及 $\mathbf { S - C O } _ { 2 }$ 动力循环子系统4部分构成。其中，定日镜场采用DAHAN电站的定日镜场布置形式，其具体参数可参考文献[5，6]。 $\mathbf { S - C O } _ { 2 }$ 吸热器选用腔体式吸热器，由于高温高压的 $\mathbf { S - C O } _ { 2 }$ 作为吸热器中的传热流体，所以吸热器的管壁相对较厚。选用LiCl\~KC1 $45 \% - 5 5 \%$ ）混合盐[作为蓄热子系统的蓄热工质，其允许使用温度范围为 $3 5 5 { \sim } 1 1 0 0 ~ ^ { \circ } \mathrm { C }$ 。蓄热子系统主要由高温盐罐、低温盐罐以及 $\mathrm { \bf S - C O } _ { 2 } /$ 熔盐换热器组成。选取简单回热，预压缩，再压缩，部分冷却和中间冷却等5种形式[8]的 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环作为动力循环子系统。相应的直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统如图1-5所示。

图1所示的SPT系统中的动力循环子系统为简单回热 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环，其组成部件主要有透平、压缩机、冷却器和回热器。高温高压的 $\mathbf { S - C O } _ { 2 }$ 在透平内膨胀做功后，通过回热器对进入吸热器之前的 $\mathbf { S - C O } _ { 2 }$ 进行预热，然后经冷却器冷却之后进入压缩机升压，高压低温的 $\mathbf { S - C O } _ { 2 }$ 经回热器预热后进入吸热器，被加热成高温高压的 $\mathbf { S - C O } _ { 2 }$ ，至此S-$\mathrm { C O } _ { 2 }$ 完成了整个循环过程。增加回热器可回收一部分热量，提高循环的效率。

图2所示的SPT系统中的动力循环子系统为预压缩 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环，其在简单回热 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环基础上增加了低温回热器和预压缩机。预压缩 $\mathbf { S - C O } _ { 2 }$ 循环的过程与简单回热循环类似，区别是$\mathbf { S - C O } _ { 2 }$ 在两个回热器之间被预先压缩，以避免简单回热循环中回热器出现的夹点问题[9]，提高回热器的效率。同时预压缩机的添加也使 $\mathbf { S - C O } _ { 2 }$ 在压缩机入口的压力不再依赖透平出口的压力，保证主压缩机可以维持在 $\mathrm { C O } _ { 2 }$ 的临界点附近运行，降低压缩机的耗功。

图3所示的SPT系统的动力循环子系统为再压缩 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环，其与预压缩 $\mathbf { S - C O } _ { 2 }$ 循环的组成部件完全相同，但循环系统的布局不同。再压缩循环中低温回热器出口的 $\mathbf { S - C O } _ { 2 }$ 被分流，一股经过冷却器、主压缩机和低温回热器，一股直接通过再压缩机升至循环最高压力，二者在高温回热器入口前汇合。分流可以使低温回热器两侧 $\mathbf { S - C O } _ { 2 }$ 的热容流率相接近，从而防止低温回热器出现夹点问题，提高回热器的效率。由于分流至主压缩机 $\mathbf { S - C O } _ { 2 }$ 的质量流量相比分流之前有所减少，使其可以完全被冷却，降低了主压缩机的耗功，因此系统布局较为简单的再压缩 $\mathbf { S - C O } _ { 2 }$ 循环可实现较高的效率。

图4中所示的SPT系统中的动力循环子系统为部分冷却 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环，其为再压缩和预压缩$\mathbf { S - C O } _ { 2 }$ 循环的组合形式。部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环既采用分流的方法解决回热器中易出现的夹点问题，又

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

利用预压缩机使 $\mathbf { S - C O } _ { 2 }$ 在压缩机入口和透平出口的压力相互独立，与再压缩循环的区别是 $\mathbf { S - C O } _ { 2 }$ 经冷却和预先压缩之后再被分流，其余循环过程与再压缩循环完全相同。部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环的吸热温差较大，这有利于 $\mathbf { S - C O } _ { 2 }$ 吸热器的设计，也利于整个系统与显热蓄热系统结合[10]，因此适合于直接式S-$\mathrm { C O } _ { 2 }$ 聚光太阳能热发电系统。

![](images/856c2d7033800028cfee32e91d1bbb89c6c11f789c4d2f23bf59025c9bf864b2.jpg)  
图1简单回热 $\mathbf { S - C O } _ { 2 }$ 循环塔式太阳能热发电系统 Fig.1 SPT system integrated with the simple cycle

![](images/434cad65cdf7fc66115de9346005d25f35b9f9f3142adddcc08f07a3cea0ef16.jpg)  
图2预压缩 $\mathbf { S - C O } _ { 2 }$ 循环塔式太阳能热发电系统

![](images/4de7a125a1ca5410ebfc0231e68dcfa25d48e3e6d51b64a96357a7206c20a440.jpg)  
Fig.2 SPT system integrated with the pre-compression cycle   
图3再压缩 $\mathbf { S - C O } _ { 2 }$ 循环塔式太阳能热发电系统

![](images/d31a74543bb584903b29fc69d3ebe924aec0492acddcdb241749a0dc03e9d7a7.jpg)  
Fig.3SPT system integrated with the recompression cycle   
图4部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环塔式太阳能热发电系统 Fig.4SPT system integrated with the partial-cooling cycle

图5所示的SPT系统中的动力循环子系统为中间冷却 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环，是基于再压缩 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环的改进形式。中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环中主压缩机分为两级，在两级之间 $\mathbf { S - C O } _ { 2 }$ 被中间冷却器冷却，采取中间冷却可进一步减小压缩机的耗功、提高循环的效率，但循环的布局也相对复杂。

![](images/ce81a679b73fe0f949d1dda952c9d73a203340af6ae32300f510477e1d8b6054.jpg)  
图5中间冷却 $\mathrm { \bf S - C O } _ { 2 }$ 循环塔式太阳能热发电系统 Fig.5SPT system integratedwith the intercoolingcycle

在直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统中，太阳光经定日镜场反射后聚焦到吸热器表面将 $\mathbf { S - C O } _ { 2 }$ 加热至透平入口温度。太阳能充足情况下，被加热的 $\mathbf { S - C O } _ { 2 }$ 一部分直接进入动力循环子系统中做功发电，一部分则通过 $\mathrm { S - C O } _ { 2 } /$ 熔盐换热器将热量传递给熔盐蓄热子系统。若太阳能不足，熔盐蓄热子系统通过换热器给 $\mathbf { S - C O } _ { 2 }$ 动力循环子系统提供热量使其可以继续输出额定功率。在系统中增加熔盐蓄热子系统可以减小太阳能波动对动力循环子系统带来的冲击，保证系统安全稳定的运行。

# 2系统建模

为了对直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统进行完整的热力学性能分析，本节对整个SPT系统（包括定日镜场、 $\mathbf { S - C O } _ { 2 }$ 吸热器、熔盐蓄热子系统以及动力循环子系统）建立了光-热-功-体化模型。建模过程中采用了以下假设：（1）某一时刻太阳能辐射视为定值，系统中所有过程达到稳态；（2）忽略管路的压损和热损；（3）忽略每个组件中流体的动能和势能；（4）忽略蓄热子系统和动力循环子系统中各组件与环境的热交换。

# 2.1定日镜场

定日镜场的光学模拟采用HFLCAL模型[11,12],假设每个镜面在各时刻聚焦到吸热器表面的能流呈二维高斯分布，则某时刻定日镜场传递到吸热器表面的总能量 $F ( t )$ 为：

$$
\begin{array} { r } { F ( t ) = \displaystyle \sum _ { i = 1 } ^ { N } \left[ \frac { I ( t ) \cdot A \cdot \eta _ { \mathrm { r e f l } } \cdot \eta _ { \mathrm { a t m o } } ( x , y ) \cdot \eta _ { \mathrm { c o s } } ( x , y , t ) } { 2 \pi \sigma _ { \mathrm { H F } } } \right] } \\ { \cdot \displaystyle \iint _ { \mathrm { a p e r t u r e } } \mathrm { e } ^ { - \frac { \zeta ^ { 2 } + \gamma ^ { 2 } } { 2 \sigma _ { \mathrm { H F } } } } \mathrm { d } \zeta \mathrm { d } \gamma } \end{array}
$$

式中， $I ( t )$ 为太阳直射辐射强度； $A$ 为单个定日镜面积； $\eta _ { \mathrm { r e f l } }$ 为镜面有效反射率； $\eta _ { \mathrm { a t m o } } ( x , y )$ 为大气衰减系数； $\eta _ { \mathrm { { c o s } } } ( x , y , t )$ 为余弦效率； $\sigma _ { \mathrm { H F } }$ 为正态分布标准差，其受到太阳形状、定日镜跟踪误差、形面误差、散

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

光效应的影响，具体计算方法可参考文献[13]。

# $2 . 2 \mathrm { S } – \mathrm { C O } _ { 2 }$ 吸热器

$\mathbf { S - C O } _ { 2 }$ 腔体式吸热器的设计尺寸参数见表1。

表1吸热器几何尺寸参数表Table 1 Geometric parameters of the $\mathbf { S - C O } _ { 2 }$ receiver.  

<html><body><table><tr><td>吸热器参数</td><td>数值</td></tr><tr><td>吸热管外径/mm</td><td>19.0</td></tr><tr><td>吸热管壁厚[14]/mm</td><td>2.7686</td></tr><tr><td>吸热器开口尺寸/m×m</td><td>5×5</td></tr><tr><td>总面板数目/面</td><td>56</td></tr><tr><td>面板的吸热管数目/根</td><td>12</td></tr><tr><td>吸热器高度/m</td><td>6</td></tr><tr><td>吸热器表面发射率[14]</td><td>0.86</td></tr><tr><td>吸热器表面吸收率</td><td>0.86</td></tr><tr><td>风速/m·s-1</td><td>5</td></tr><tr><td>S-CO出口温度/C</td><td>500~800</td></tr></table></body></html>

定日镜场投射到吸热器表面的能量大部分被吸热器内的 $\mathbf { S - C O } _ { 2 }$ 吸收，另一部分通过对流、辐射、反射以及导热的方式损失于环境中。吸热器的能量平衡方程为：

$$
\begin{array} { r } { \mathcal { Q } _ { \mathrm { r e c } } = \mathcal { Q } _ { \mathrm { r e c , a b s } } + \mathcal { Q } _ { \mathrm { r e c , t o t l o s s } } = m _ { \mathrm { c , r e c } } \cdot ( h _ { \mathrm { m s , o u t } } - h _ { \mathrm { m s , i n } } ) } \end{array}
$$

$$
+ Q _ { \mathrm { c o n v } } + Q _ { \mathrm { e m } } + Q _ { \mathrm { r e f } } + Q _ { \mathrm { c o n d } }
$$

式中， $\scriptstyle Q _ { \mathrm { r e c } }$ 为到达吸热器的太阳辐射能； $\scriptstyle Q _ { \mathrm { r e c , a b s } }$ 为 S-$\mathrm { C O } _ { 2 }$ 吸热量； $\scriptstyle Q _ { \mathrm { r e c , t o t l o s s } }$ 为吸热器总的热损失； $m _ { \mathrm { c , r e c } }$ 为吸热器中 $\mathbf { S - C O } _ { 2 }$ 的质量流量； $h _ { \mathrm { m s , o u t } }$ 为吸热器出口 S-$\mathrm { C O } _ { 2 }$ 的焓； $h _ { \mathrm { m s , i n } }$ 为吸热器进口 $\mathbf { S - C O } _ { 2 }$ 的焓； $\varrho _ { \mathrm { c o n v } }$ 为对流热损失； $\varrho _ { \mathrm { e m } }$ 为辐射热损失； $\boldsymbol { Q } _ { \mathrm { r e f } }$ 为反射热损失； $\varrho _ { \mathrm { c o n d } }$ 为导热热损失；各项热损失的计算方法可参照文献[15]。

吸热器最终的热平衡状态通过迭代的方法计算，通过式（3）确定吸热器的热效率 $\eta _ { \mathrm { t , r e c } }$ 和烟效率$\eta _ { \mathrm { e , r e c } }$ ：

$$
\eta _ { \mathrm { t , r e c } } = Q _ { \mathrm { r e c , a b s } } \ / \ Q _ { \mathrm { r e c } } \eta _ { \mathrm { e , r e c } } = E _ { \mathrm { r e c , a b s } } \ / \ E _ { \mathrm { r e c } }
$$

式中， $\boldsymbol { E } _ { \mathrm { r e c } }$ 为到达吸热器的总烟； $E _ { \mathrm { r e c , a b s } }$ 为 $\mathbf { S - C O } _ { 2 }$ 吸收的总烟。

# 2.3蓄热子系统

蓄热子系统有储热和放热两个过程，忽略S-$\mathrm { C O } _ { 2 } /$ 熔盐换热器及蓄热罐与外界的热交换，则蓄热系统储热和放热过程的热效率均为 $100 \%$ 。换热器的换热温差不可避免的会引起烟损失，下文对蓄热系统储、放热过程的烟效率进行计算。

太阳能充足时，吸热器内 $\mathbf { S - C O } _ { 2 }$ 的质量流量大于动力循环子系统所需的质量流量，多余的 $\mathbf { S - C O } _ { 2 }$ 则通过 $\mathrm { \bf S - C O } _ { 2 } /$ 熔融盐换热器将热量传递给熔盐蓄热子系统进行储存，此时蓄热子系统进行储热过程。$\mathrm { S - C O } _ { 2 } /$ 熔盐换热器中 $\mathbf { S - C O } _ { 2 }$ 的入口温度与透平入口温度相等， $\mathbf { S - C O } _ { 2 }$ 的出口温度由 $\mathbf { S - C O } _ { 2 }$ 动力循环子系统决定，换热器高温端 $\mathbf { S - C O } _ { 2 }$ 与熔盐的温差设为$2 0 \ ^ { \circ } \mathrm { C }$ ，根据换热器效能（取0.94）可确定低温熔盐蓄热罐的蓄热温度，则蓄热子系统蓄热过程的烟效率 $\eta _ { \mathrm { e , t e s } }$ 为：

$$
\eta _ { \mathrm { e , t e s } } = \frac { m _ { \mathrm { s , e x } } \cdot [ h _ { \mathrm { h t , s } } - h _ { \mathrm { l t , s } } - T _ { 0 } \cdot c _ { \mathrm { p } } \cdot \ln { ( T _ { \mathrm { h t , s } } / T _ { \mathrm { l t , s } } ) } ] } { m _ { \mathrm { c , e x } } \cdot [ h _ { \mathrm { i n , c } } - h _ { \mathrm { o u t , c } } - T _ { 0 } \cdot ( s _ { \mathrm { i n , c } } - s _ { \mathrm { o u t , c } } ) ] }
$$

式中， $m _ { \mathrm { c , e x } }$ 为 $\mathbf { S - C O } _ { 2 }$ 的质量流量； $m _ { \mathrm { s , e x } }$ 为熔盐的质 量流量； $h _ { \mathrm { i n , c } }$ ， $h _ { \mathrm { o u t , c } }$ 分别为 $\mathbf { S - C O } _ { 2 }$ 进出口比焓; $h _ { \mathrm { l t , s } }$ ， $h _ { \mathrm { h t , s } }$ 分别为熔盐进出口比焓； $T _ { \mathrm { h t , s } }$ ， $T _ { \mathrm { l t , s } }$ 分别为 高、低温熔盐的温度； $T _ { 0 }$ 为环境温度； $s _ { \mathrm { i n , c } }$ ， $s _ { \mathrm { o u t , \mathfrak { c } } }$ 分 别为 $\mathbf { S - C O } _ { 2 }$ 进、出口比熵； $c _ { \mathfrak { p } }$ 为熔盐的定压比热。

蓄热子系统放热时使用同一个换热器将热源传递给 $\mathbf { S - C O } _ { 2 }$ 作功工质，换热器中 $\mathbf { S - C O } _ { 2 }$ 和熔盐的流动方向与蓄热过程刚好相反，则蓄热系统放热过程的烟效率 $\eta _ { \mathrm { e , t e r } }$ 为：$\eta _ { \mathrm { e , t e r } } = \frac { m _ { \mathrm { c , e x , r e l } } \cdot [ h _ { \mathrm { o u t , c , r e l } } - h _ { \mathrm { i n , c , r e l } } - T _ { 0 } \cdot ( s _ { \mathrm { o u t , c , r e l } } - s _ { \mathrm { i n , c , r e l } } ) ] } { m _ { \mathrm { s , e x , r e l } } \cdot [ h _ { \mathrm { h t , s } } - h _ { \mathrm { l t , s } } - T _ { 0 } \cdot c _ { \mathrm { p } } \cdot \ln { ( T _ { \mathrm { h t , s } } / T _ { \mathrm { l t , s } } ) } ] }$ (5)式中， $m _ { \mathrm { c , e x , r e l } }$ 为放热过程换热器中 $\mathbf { S - C O } _ { 2 }$ 的质量流量； $m _ { \mathrm { s , e x , r e l } }$ 为放热过程换热器中熔盐的质量流量;$h _ { \mathrm { o u t , c , r e l } }$ 为 $\mathbf { S - C O } _ { 2 }$ 出口比焓； $h _ { \mathrm { i n , c , r e l } }$ 为 $\mathbf { S - C O } _ { 2 }$ 入口比焓； $s _ { \mathrm { o u t , c , r e l } }$ 为 $\mathbf { S - C O } _ { 2 }$ 出口比熵； $s _ { \mathrm { i n , c , r e l } }$ 为 $\mathbf { S - C O } _ { 2 }$ 入口比熵。

# 2.4动力循环子系统

$\mathbf { S - C O } _ { 2 }$ 动力循环子系统是直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统的热-电转换环节，5种 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环中系统结构最复杂的是中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环，其余4种循环可通过对其简化得到，限于篇幅本节只描述中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环的热力学模型，S-$\mathrm { C O } _ { 2 }$ 动力循环子系统的各项参数见表2。

图6给出了透平入口温度为 $7 0 0 ~ ^ { \circ } \mathrm { C }$ 时中间冷却$\mathbf { S - C O } _ { 2 }$ 布雷顿循环的 $T _ { - S }$ 图。1为透平入口状态点，对应循环的最高温度和压力，5为压缩机C1入口状态点，对应循环的最低温度和压力，7为压缩机C2入口状态点，对应循环的最低温度和中间压力。循环的中间压力由参数RPR（压力比的比值）确定，用参数SR（分流比）定义流向主压缩机 $\mathbf { S - C O } _ { 2 }$ 的质量流量。1-2为 $\mathbf { S - C O } _ { 2 }$ 在透平内膨胀做功过程，4-10、5-6、7-8均为压缩机压缩 $\mathbf { S - C O } _ { 2 }$ 过程，4-5、6-7为 $\mathbf { S - C O } _ { 2 }$ 的冷却过程，2-3和11-12为高温回热器热交换过程，3-4和8-9为低温回热器换热过程，12-1

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

为 $\mathbf { S - C O } _ { 2 }$ 在吸热器内的吸热过程。

![](images/f9d8609376e7b311338904b3f37969a468293043835994ab9503b9202b301c19.jpg)  
图6中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环 $T _ { - S }$ 图（ $7 0 0 ^ { \circ } \mathrm { C } \$ ） Fig. 6 $T { - } s$ diagram of the intercooling $\mathbf { S - C O } _ { 2 }$ Brayton cycle

表2动力循环子系统各项数据参数[16]Table 2 Operating parameters for $\mathbf { S - C O } _ { 2 }$ power cycle blocks  

<html><body><table><tr><td>动力循环系统参数</td><td>数值</td></tr><tr><td>循环最高压力Pmax/MPa</td><td>25</td></tr><tr><td>循环压力比</td><td>3.4</td></tr><tr><td>循环最高温度Tmax／℃</td><td>500~800</td></tr><tr><td>循环最低温度Tmin/℃</td><td>32</td></tr><tr><td>透平效率nis,t</td><td>0.93</td></tr><tr><td>压缩机效率nis,c</td><td>0.89</td></tr><tr><td>低温回热器效能</td><td>0.95</td></tr><tr><td>高温回热器效能</td><td>0.95</td></tr><tr><td>S-CO/熔盐换热器效能</td><td>0.94</td></tr><tr><td></td><td></td></tr><tr><td>循环输出功率Wtot/MW</td><td>1.0</td></tr></table></body></html>

本文考虑了 $\mathbf { S - C O } _ { 2 }$ 物性的变化，利用美国国家标准与技术研究院（NIST）的REFPROP物性数据库调用 $\mathbf { S - C O } _ { 2 }$ 的物性。 $\mathbf { S - C O } _ { 2 }$ 循环的各个组成部件的能量关系式列于表3。中间冷却 $\mathbf { S - C O } _ { 2 }$ 动力循环的热效率 $\eta _ { \mathrm { t } }$ 和烟效率 $\eta _ { \mathrm { e } }$ 计算如下[17]:

$$
\begin{array} { r l } & { \eta _ { \mathrm { t } } = \big ( W _ { \mathrm { t } } - W _ { \mathrm { c l } } - W _ { \mathrm { c 2 } } - W _ { \mathrm { r c } } \big ) \big / Q } \\ & { \eta _ { \mathrm { e } } = \big ( W _ { \mathrm { t } } - W _ { \mathrm { c l } } - W _ { \mathrm { r c } } - W _ { \mathrm { c 2 } } \big ) \big / E _ { \mathrm { t o t a l } } } \end{array}
$$

式中， $\mathbf { S - C O } _ { 2 }$ 循环吸收的总烟 $E _ { \mathrm { t o t a l } }$ 为：

$$
E _ { \mathrm { t o t a l } } = m \cdot \left[ h _ { \mathrm { 1 } } - h _ { \mathrm { 1 2 } } - T _ { \mathrm { 0 } } \cdot ( s _ { \mathrm { 1 } } - s _ { \mathrm { 1 2 } } ) \right]
$$

式中， $\mathbf { \nabla } _ { m }$ 为循环中 $\mathbf { S - C O } _ { 2 }$ 的质量流量； $T _ { 0 }$ 为环境温度； $h _ { 1 }$ 为 $\mathbf { S - C O } _ { 2 }$ 在1点的焓； $h _ { 1 2 }$ 为 $\mathbf { S - C O } _ { 2 }$ 在12点的焓； $s _ { 1 }$ 为 S-CO2在1点的熵； $s _ { 1 2 }$ 为 $\mathbf { S - C O } _ { 2 }$ 在12点的熵。

表3中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环各组成部件的能量关系 Table 3 Energy balance equations of each component in the intercooling $\mathbf { S - C O } _ { 2 }$ Brayton cycle   

<html><body><table><tr><td>组成部件</td><td>能量关系</td></tr><tr><td>透平</td><td>nis,t=(h-h)/(h-hs) W=m·(h -h2)</td></tr><tr><td>高温回热器</td><td>h-h=h-h1 εHTR =(h-h)）/(h-h(t,Pm)</td></tr><tr><td>低温回热器</td><td>εLTR =(h-h）/(h-h(ts,Pmn)) εLTR =(h-hg）/(h(t，Pmax)-h）</td></tr><tr><td>预冷器</td><td>Qpc = SR·m·(h4-h5)</td></tr><tr><td>压缩机C1</td><td>Nis.c1 =(h6s-h5)/(h6-h5) Wcl = m·SR·(h6 -h5)</td></tr><tr><td>冷却器</td><td>SR=(h-h4)/(h-hg) Qic = SR·m·(h -h,)</td></tr><tr><td>压缩机C2</td><td>Nis.c2=(hgs-h)/(h-h) W = m·SR·(hg-h,)</td></tr><tr><td>再压缩机</td><td>nis,rc =(h1os-h4)/(ho-h4) Wc = m·(1- SR)·(ho -h4)</td></tr><tr><td>吸热器</td><td>Q=m·(h -h2)</td></tr></table></body></html>

根据上述能量关系式及循环系统已知参数，利用迭代的方法求得 $\mathbf { S - C O } _ { 2 }$ 循环的各个状态点参数，确定循环的热效率及烟效率。为了对5种 $\mathbf { S - C O } _ { 2 }$ 布雷顿循环的热力学性能进行对比，各个透平入口温度下，对预压缩循环的RPR，再压缩循环的 $S R$ ，部分冷却循环的SR、RPR和中间冷却循环的SR、RPR均以最大循环热效率为目标进行了优化[18]。将 S-$\mathrm { C O } _ { 2 }$ 循环模型的求解结果与文献[2]中的数据进行了对比，见表4。可见二者吻合得很好，验证了S-$\mathrm { C O } _ { 2 }$ 动力循环子系统模型的正确性。

表4透平入口温度为 $7 0 0 ^ { \circ } \mathrm { C }$ 时 $\mathbf { S - C O } _ { 2 }$ 循环的最优运行工况和效率  
Table 4 The optimal operating conditions and efficiency of $\mathbf { S - C O } _ { 2 }$ Brayton cycles at TIT of ${ 7 0 0 } ^ { \circ } \mathrm { C }$   

<html><body><table><tr><td>循环形式</td><td>Tmin/ C</td><td>SR</td><td>RPR</td><td>CHTR</td><td>&LTR</td><td>压力比</td><td>nt（文献 值）</td><td>nt（本文值）</td></tr><tr><td>再压缩</td><td>45</td><td>0.70</td><td>1</td><td>0.97</td><td>0.88</td><td>2.7</td><td>0.523</td><td>0.516</td></tr><tr><td></td><td>60</td><td>0.75</td><td></td><td>0.97</td><td>0.88</td><td>2.5</td><td>0.497</td><td>0.492</td></tr><tr><td>部分冷却</td><td>45</td><td>0.58</td><td>0.37</td><td>0.97</td><td>0.88</td><td>5.0</td><td>0.522</td><td>0.518</td></tr><tr><td></td><td>60</td><td>0.62</td><td>0.33</td><td>0.97</td><td>0.87</td><td>4.5</td><td>0.500</td><td>0.495</td></tr></table></body></html>

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

# 3结果与讨论

本文选择新疆省昌吉市（东经 $8 8 . 6 ^ { \circ }$ 北纬44.1°）夏至日正午时分作为系统的运行工况，对整个SPT系统（包括定日镜场、吸热器、蓄热子系统、动力循环子系统）的热力学性能进行计算分析，其中，蓄热子系统储存的热量通过放热过程折算为对应的 $\mathbf { S - C O } _ { 2 }$ 动力循环子系统的有用功，从而确定整个系统的热效率 $\eta _ { \mathrm { t , s y s } }$ 和烟效率 $\eta _ { \mathrm { e , s y s } }$ 。由于本文只选择了一个计算时刻，定日镜场的热效率和烟效率始终恒定，故不作分析。

# 3.1吸热器性能分析

图7、图8分别给出了5种 $\mathbf { S - C O } _ { 2 }$ 循环下整个SPT系统中吸热器的热效率和烟效率随透平入口温度的变化。从图7可以看出，吸热器的热效率随着透平入口温度的升高而逐渐降低，这是由于透平入□温度升高会使 $\mathbf { S - C O } _ { 2 }$ 吸热器吸热表面的平均温度升高，导致了热损失的加剧，出现吸热器热效率降低的现象。同一透平入口温度下，简单回热 $\mathbf { S - C O } _ { 2 }$ 循环具有最大的吸热温差，因而吸热器表面的平均温度最低、热损失最小，具有最高的效率；部分冷却、中间冷却、再压缩和预压缩循环下吸热器的热效率依次降低。从图8可以看出随着透平入口温度的升高，吸热器的烟效率会增加，然而当温度过高时，吸热器吸热表面的平均温度会增大，导致吸热器的热损失严重，造成较大的烟损失，导致烟效率开始下降。在最高点之前，简单回热循环下的吸热器烟效率最低，依次增大的是部分冷却、中间冷却、预压缩、再压缩 $\mathbf { S - C O } _ { 2 }$ 循环，最高点之后情况则相反，这均是由5种 $\mathbf { S - C O } _ { 2 }$ 循环的吸热温差不同造成的。

Fig.7Variations of $\eta _ { \mathrm { t , r e c } }$ with TIT for differentcycles   

<html><body><table><tr><td rowspan="2">中间冷却</td><td>45</td><td>0.65</td><td>0.60</td><td>0.97</td><td>0.90</td><td>3.6</td><td>0.526</td><td>0.530</td></tr><tr><td>60</td><td>0.70</td><td>0.54</td><td>0.97</td><td>0.90</td><td>3.3</td><td>0.503</td><td>0.509</td></tr></table></body></html>

![](images/6f94510534606b51192dfa49f6a6b6564bacd6c0778646b2b72ea30ab9326891.jpg)  
图7不同透平入口温度下吸热器的热效率

54.5%54.0% 28053.5% 26053.0%52.5% 220广 200180简单回热50.5% = 预压缩 6050.0% 再压缩 140-部分冷却49.5% + 中间冷却 12049.0%500 550 600 650 700 750 800透平入口温度tC

# 3.2蓄热子系统性能分析

图9、10分别给出了蓄热子系统蓄热和放热过程的烟效率随透平入口温度的变化，由图可知二者均随着透平入口温度的升高而逐渐增大。由于预压缩 $\mathbf { S - C O } _ { 2 }$ 循环的吸热温差最小，换热器效能相同的情况下蓄热子系统的蓄热温差最小，使得换热器内$\mathbf { S - C O } _ { 2 }$ 和熔盐的平均换热温差最小，则由换热温差引起的不可逆烟损失也最小，蓄热过程的烟效率最高，简单回热 $\mathbf { S - C O } _ { 2 }$ 循环情况则相反。蓄热子系统放热时中间换热器固定，由于蓄热过程使能量品味有所降低，放热时换热器的效能会低于0.94，所以受换热器效能的限制，5种 $\mathrm { \bf S - C O } _ { 2 }$ 循环下蓄热子系统放热过程的烟效率比较接近。

![](images/5d33bf03b2f57fbc1e7ad2fffbc57927d5d5ce166a63c73f1084d102d1bd085e.jpg)  
图8不同透平入口温度下吸热器的烟效率Fig.8 Variations of $\eta _ { \mathrm { { e , r e c } } }$ with TIT for different cycles  
图9不同透平入口温度下蓄热系统蓄热烟效率Fig.9 Variations of $\eta _ { \mathrm { e , t e s } }$ with TIT for different cycles

WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/b5667b64e04dd601c655490c7beaf4bfb9afc402f5de419fcef88703521bc86a.jpg)  
图10不同透平入口温度下蓄热系统放热烟效率Fig.10 Variations of $\eta _ { \mathrm { e , t e r } }$ with TIT for different cycles

# 3.3动力循环子系统性能分析

图11不同透平入口温度下 $\mathbf { S - C O } _ { 2 }$ 循环的热效率

Fig.11 Variations of $\eta _ { \mathrm { t } }$ with TIT for different cycles

图11、图12分别给出了5种 $\mathbf { S - C O } _ { 2 }$ 循环的效率 $\eta _ { \mathrm { t } }$ 和 $\eta _ { \mathrm { e } }$ 随透平入口温度的变化，透平入口温度升高，5种 $\mathbf { S - C O } _ { 2 }$ 循环的热效率和烟效率均增大。各个温度下，中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环具有最高的热效率和畑效率，最低的是简单回热循环，预压缩 $\mathbf { S - C O } _ { 2 }$ 循环的热效率略高于部分冷却循环。再压缩 $\mathbf { S - C O } _ { 2 }$ 循环的热效率和烟效率对透平入口温度的变化比较敏感，当温度超过650 $^ { \circ } \mathrm { C }$ ，其热效率和烟效率均会超过再压缩和预压缩 $\mathbf { S - C O } _ { 2 }$ 循环，部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环的烟效率对透平入口温度的变化较不敏感，在整个温度范围的变化较小。当温度高于 $7 0 0 ~ ^ { \circ } \mathrm { C }$ 时，预压缩和部分冷却 $\mathrm { \bf S - C O } _ { 2 }$ 循环的烟效率非常接近。

60%  
58% 中一简单循环预压缩  
56% 再压缩  
54% 部分冷却中间冷却  
50%  
48%  
46%  
44%  
42%  
40%  
38% A 配 上 二 上500 550 600 650 700 750 800透平入口温度tC

![](images/992bf78656090ab412bf98569ddc87e29eecc1051e2e76704d7e5b3929900df4.jpg)  
图11不同透平入口温度下 $\mathbf { S - C O } _ { 2 }$ 循环的热效率  
图12不同透平入口温度下 $\mathbf { S - C O } _ { 2 }$ 循环的烟效率

# 3.4整个SPT系统性能分析

吸热器、蓄热子系统及 $\mathbf { S - C O } _ { 2 }$ 动力循环子系统的性能直接决定了整个SPT系统的热力学性能，三者的共同作用使5种 $\mathbf { S - C O } _ { 2 }$ 循环下整个SPT系统的热效率和烟效率随透平入口温度的变化如图13、图14所示。随着透平入口温度的升高，系统的热效率和烟效率均呈现出先升高后减小的变化，这是由于温度较低时，动力循环子系统效率的影响占主导地位，整个系统的效率随着透平入口温度的升高而增加，而温度过高时，吸热器的热损失加剧，吸热器效率的影响占主导地位，整个系统的效率开始降低。各个温度下，中间冷却和部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环下整个SPT系统的效率较高，部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环自身的效率虽然在高温范围内低于再压缩 $\mathbf { S - C O } _ { 2 }$ 循环，但由于其吸热温差较大，吸热器的效率较高，使其对应的整个SPT系统的效率始终比再压缩 S-$\mathrm { C O } _ { 2 }$ 循环高。温度低于 $6 5 0 ~ ^ { \circ } \mathrm { C }$ 时，预压缩 $\mathbf { S - C O } _ { 2 }$ 循环下整个系统的效率比再压缩 $\mathbf { S - C O } _ { 2 }$ 循环高，超过$6 5 0 ~ ^ { \circ } \mathrm { C }$ 后情况则相反。简单回热循环下整个SPT系统的效率最低，比复杂循环下的SPT系统效率低$4 \%$ 左右。

![](images/c834a1b5bf1f2eb66cf4b9567bc5de8859280ee729b560a6a19899565ace3dc0.jpg)  
Fig.12Variations of $\eta _ { \mathrm { e } }$ with TIT for differentcycles   
图13不同透平入口温度下整个系统的热效率

![](images/846b5d099dfa5751bd3953fea6d2e138a5ebd26806ec8fea831d2258db0ffc05.jpg)  
Fig.11Variations of $\eta _ { \mathrm { t } }$ with TIT for different cycles   
Fig.13Variations of $\eta _ { \mathrm { t , s y s } }$ with TIT for different cycles   
图14不同透平入口温度下整个系统的烟效率  
Fig.14Variations of $\eta _ { \mathrm { e , s y s } }$ with TIT fordifferent cycles

WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

通过对5种 $\mathbf { S - C O } _ { 2 }$ 循环下塔式太阳能热发电系统热力学性能的分析，可以发现，每种 $\mathbf { S - C O } _ { 2 }$ 循环形式均有自己的优势和特点，整个太阳能热发电系统的热力学性能不仅受动力循环子系统的影响，还受到吸热器和蓄热子系统的约束，因此不能只关注$\mathbf { S - C O } _ { 2 }$ 动力循环自身的热力学性能，要根据太阳能电站自身的特点和实际需要选取最佳的循环形式。

# 4结论

本文针对直接式 $\mathbf { S - C O } _ { 2 }$ 塔式太阳能热发电系统（包括定日镜场、吸热器、蓄热子系统以及动力循环子系统）建立了光-热-功一体化完整模型，在此基础上，对简单回热、预压缩、再压缩、部分冷却和中间冷却5种 $\mathbf { S - C O } _ { 2 }$ 循环形式下SPT系统的热力学性能进行了对比分析。主要讨论了透平入口温度变化对整个系统热效率和烟效率的影响，结论如下：

（1）透平入口温度增大，吸热器的热效率逐渐减小，其烟效率先增大后逐渐减小，而蓄热子系统和动力循环子系统的热效率和烟效率随着透平入口温度的升高而增大，三者的共同作用使整个SPT系统的热效率和烟效率并不是随着透平入口温度不断的升高，而是在 $6 5 0 ~ ^ { \circ } \mathrm { C }$ 附近具有一个最大值，这表明整个系统的运行温度不是越高越好。

（2）在本文研究的透平入口温度范围内（2 $( 5 0 0 { \sim } 8 0 0 \ ^ { \circ } \mathrm { C } )$ ,中间冷却 $\mathbf { S - C O } _ { 2 }$ 循环下的SPT系统具有最高的热效率和烟效率。虽然部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环自身的效率在 $6 5 0 ~ ^ { \circ } \mathrm { C }$ 以上时不及再压缩 $\mathbf { S - C O } _ { 2 }$ 循环，但其对应的整个SPT系统的效率却仅次于中间冷却S-CO2循环，这是由于部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环具有较大的吸热温差、吸热器热效率较高的优势。中间冷却和部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环下的SPT系统虽然效率较高，但系统结构也是最复杂的。

（3）在650 $^ { \circ } \mathrm { C }$ 以下的温度范围，预压缩S-$\mathrm { C O } _ { 2 }$ 循环下整个SPT系统的效率比再压缩 $\mathbf { S - C O } _ { 2 }$ 循环高，温度超过 $6 5 0 ~ ^ { \circ } \mathrm { C }$ 后情况则刚好相反，说明两种循环各有优势。再压缩 $\mathbf { S - C O } _ { 2 }$ 循环的布局较为简单，且在高温范围与部分冷却 $\mathbf { S - C O } _ { 2 }$ 循环的效率相当，因此具有很大的应用潜力。

# 参考文献

[1]Ahn Y,Bae S J,Kim M, et al.Review of supercritical $\mathrm { C O } _ { 2 }$ power cycle technology and current status of research and development[J]. NuclearEngineering and Technology, 2015,47(6):647-661.   
[2]Turchi C S,Ma Z,Neises T W, et al. Thermodynamic study of advanced supercritical carbon dioxide power cycles for concentrating solar power systems[J]. Journal of Solar Energy Engineering,2013,135(4): 041007.   
[3] Chacartegui R,de Escalona J M M, Sänchez D,et al. Alternative cycles based on carbon dioxide for central receiversolarpowerplants[J].AppliedThermal Engineering,2011,31(5): 872-879.   
[4]Padilla R V,Too Y C S,Benito R,et al. Exergetic analysis of supercritical $\mathrm { C O } _ { 2 }$ Brayton cycles integrated with solar central receivers[J]. Applied Energy,2015,148: 348-365.   
[5] Yu Q,Wang Z, Xu E,et al. Modeling and simulation of 1MWe solar tower plant's solar flux distribution on the central cavity receiver[J]. Simulation Modelling Practice and Theory,2012,29:123-136.   
[6]Wang K, He Y L, Qiu Y, et al. A novel integrated simulation approach couples MCRT and Gebhart methods to simulate solar radiation transfer in a solar power tower system with a cavity receiver[J]. Renewable Energy,2016,89: 93-107.   
[7] Williams D F. Assessment of candidate molten salt coolants forthe NGNP/NHI heat-transfer loop[J]. ORNL/TM2006/69，Oak Ridge National Laboratory， Oak Ridge, Tennessee, 2006.   
[8] Kulhanek M, Dostal V. Supercritical carbon dioxide cycles thermodynamic analysis and comparison[C]//Supercritical $\mathrm { C O } _ { 2 }$ Power Cycle Symposium, Boulder, CO, May. 2011: 24- 25.   
[9] Dostal V,Driscoll M J, Hejzlar P.A supercritical carbon dioxide cycle for next generation nuclear reactors[J]. Massachusets Institute of Technology.Dept. of Nuclear Engineering， Cambridge，MA，Paper No.MIT-ANP-TR100,2004.   
[10] Neises T W,Turchi C S. Supercritical $\mathrm { C O } _ { 2 }$ Power Cycles: DesignConsiderationsforConcentratingSolar Power[C]//4th International Symposium—Supercritical CO. 2014,2: 9-10.   
[11] Kiera M. Heliostat field: computer codes, requirements, comparison of methods[J]. GAST-The Gas-Cooled Solar Tower Technology Program. Proceedings of the Final Presentation. Springer,Berlin,1989.   
[12]何雅玲，王坤，杜保存，等．聚光型太阳能热发电系统非 均匀辐射能流特性及解决方法的研究进展[J]．科学通报, 2016 (30): 3208-3237. He Ya-Ling,Wang Kun, Du Bao-Cun,et al. Non-uniform characteristics of solar flux distribution in the concentrating solar power systems and its corresponding solutions: A review (in Chinese). Chinese Science Bulletin，2016, 61(30):3208-3237.   
[13] SchwarzbozlP,Pitz-PaalR,Schmitz M.Visual HFLCAL-A software tool for layout and optimisation of heliostat fields[C]/Proceedings. 2009.   
[14] Ortega J D,Khivsara S D,Christian JM, et al. Coupled Optical-Thermal-Fluid Modeling of a Directly Heated Tubular Solar Receiver for Supercritical CO2 Brayton Cycle[C]//ASME 2015 9th International Conference on Energy Sustainability collocated with the ASME 2015 Power Conference,the ASME 2015 13th International Conference on Fuel Cell Science,Engineeringand Technology,and the ASME 2015 Nuclear Forum.American Society of Mechanical Engineers,2015: V001T05A018- V001T05A018.

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

[15]Li X,Kong W,Wang Z,et al. Thermal model and thermodynamicperformanceofmoltensaltcavity receiver[J].Renewable Energy,2010,35(5):981-988.   
[16]Kulhanek M,Dostal V.Thermodynamic analysisand comparison of supercritical carbon dioxide cycles[C]//Proceedings of Supercritical $\mathrm { C O } _ { 2 }$ Power Cycle Symposium.2011:24-25.   
[17] Xi H,Li M J,He Y L,et al. A graphical criterion for

workingfluidselectionandthermodynamicsystem comparison in waste heat recovery[J].Applied Thermal Engineering,2015,89: 772-782. [18] Xi H,Li M J,Xu C,et al. Parametric optimization of regenerative organic Rankine cycle(ORC） for low grade waste heat recovery using genetic algorithm[J]. Energy, 2013,58: 473-482.

# 附页:

通讯作者：何雅玲，教授  
通讯地址：陕西省西安市咸宁西路28号，西安交通大学，能源与动力工程学院，710049  
固定电话：029-82665930，手机13088999283  
E-mail: yalinghe@mail.xjtu.edu.cn

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538