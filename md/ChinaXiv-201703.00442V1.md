# 太阳能辅助燃煤发电系统蓄热运行策略优化

黄畅侯宏娟 丁泽宇　许克珂　杨勇平(华北电力大学能源动力与机械工程学院，北京102206)

摘要太阳能辅助燃煤发电已经被证明是一种有效利用太阳能的发电方式。与纯太阳能光热发电系统不同，太阳能辅助燃煤互补发电系统（下简称互补发电系统）中采用不同的蓄热运行策略将对互补系统的性能产生显著影响。本文针对槽式互补发电系统，建立了槽式太阳能集热场以及互补系统的数学模型，采用了真实的气象数据进行仿真模拟，研究分析了互补发电系统的年性能，得出了不同太阳能倍数、蓄热小时数对互补系统的太阳能发电成本 LCOE 的影响规律，并据此优化蓄热运行策略。其结果表明：三种策略中，削峰填谷策略是最适合互补发电系统的运行策略，在0.5蓄热小时数、1.2太阳能倍数下，其太阳能发电成本取得极小值，为 $0 . 0 6 4 ~ \ S / \mathrm { k W h }$

关键词燃煤互补发电系统；年性能；蓄热；策略；太阳能发电成本中图分类号：TM615 文献标识码：A 文章编号：0253-231X(2017)03-0453-06

# Optimization of Storage Operation Strategy for Solar Aided Coal-Fired Power Generation (SACPG) System

HUANG ChangHOU Hong-Juan DING Ze-YuXU Ke-KeYANG Yong-Ping School of Energyand Mechanical Enginering,NChina Electric Power University，Beijing 102206,China)

AbstractSolar aid coal-fired power genration (SACPG) technology has been proved to be an effcient way in the utilization of solarnergy. Different from solar-only generation,operation strategy has big impacts on performance nthis paper,a math model of parabolic trough solar feld integrated with coal-fired unit has beeqstablished. Annual performance of SACPG system is analyzed under diffrent storage capacity (hours) and solar multiple, and the effect on the levelized cost of electricity (LCOE) of SACPG system can be obtained also. Based on it， optimization of operation strategy could be found. The results show that the first operation strategy is the most suitable strategy of the SACPG system. The minimum LCOE is 0.064 \$/kWh with 0.5Hours storage capacity and 1.2 solar multiple. 5

Key wordsSACPG system; annual performance; storage system; operation strategy; LCOE

# 0引言

燃煤发电是我国电力供应的重要保障，也是集中治理燃煤污染、解决环境问题的关键。因而，实现燃煤发电系统能源的高效清洁利用具有重要战略意义。把太阳能加入到常规燃煤电厂一方面可大幅度降低太阳能热发电成本，另一方面也可提高燃煤电站的节能减排效能[1]。国内外有关太阳能集热与燃煤发电系统集成方面的研究最早在1975年由Zoschak 和 Wu[2] 提出，通过对7 种不同太阳能与800MW燃煤机组集成方案的对比，得出太阳能与给水系统的集成模式在初投资，设计及运行方面具有较好的前景。YING You 和 Hu Eric [3,4] 从热力学的角度对太阳能作为辅助热源的太阳能与燃煤互补发电系统具有的优越性进行了分析。结果表明，用太阳能替代朗肯循环电厂的抽汽加热给水，机组的热效率及火用效率均有所提高。YANGYongping等[1,5-9]对太阳能辅助燃煤机组互补发电的集成机理、集成方案及变工况特性进行了研究。黄畅[10]针对太阳能与不同容量燃煤机组耦合的集成方式，分析了非设计工况及年性能。

综上所述，目前的研究主要集中于互补发电系统的性能分析，鲜有针对互补发电系统蓄热运行策略优化的研究。相比于纯太阳能光热系统，互补发电系统由于集成了传统火电机组，其蓄热运行策略不宜照搬纯光热系统经验，而有待进一步研究。本文以槽式太阳能辅助某燃煤发电系统为例，分析了在3种蓄热运行策略下的太阳能与燃煤互补发电系统的年性能及LCOE，优化蓄热运行策略，为太阳能辅助燃煤机组的优化设计提供理论及数据依据。

# 1 系统描述

槽式太阳能辅助燃煤发电系统是利用太阳能热作为辅助热源，全部或部分替代原有燃煤机组的三级高加回热抽汽加热给水，被替代的抽汽继续在汽轮机中做功，实现太阳能辅助燃煤发电。系统图如图1所示，槽式太阳能集热场获得的太阳能热通过油水换热器加热给水，依次取代#3、#2、#1高加回热加热器中的抽汽。

![](images/cd48b1c6cd26856762850570235dcd4679a7d7e24f7e76a254179afeefe2802a.jpg)  
图1槽式太阳能辅助燃煤发电系统示意图Fig.1 scheme of $\mathrm { \check { \ g p s i g } }$ system

# 2 模型建立

# 2.1集热场模型

集热场单位采光面积所接收到的直射辐射能Qreceive $\mathrm { ( W / m ^ { 2 } ) }$ 可表示：

$$
Q _ { \mathrm { r e c e i v e } } { = } \binom { I _ { \mathrm { D N I } } \cdot \cos \theta + ( N _ { \mathrm { S C A } } - 1 ) \cdot } { I _ { \mathrm { D N I } } \cdot \cos \theta \cdot R } \bigg / \frac { \kappa _ { \mathrm { S C A } } \times \mathsf { X } ^ { \times } } { \Gamma }
$$

式中， $I _ { \mathrm { D N I } }$ 为直射辐射强度 $\mathrm { ( W / m ^ { 2 } } \mathrm { ) }$ ； $\displaystyle \mathrm { c o s } \theta$ 为太阳光入射角余弦； $N _ { \mathrm { S C A } }$ 为集热场内集热器的列数； $R$ 为集热器的阴影修正系数；

单位面积集热场上集热管吸收的太阳辐射能$Q _ { \mathrm { a b s o r d } } / ( \mathrm { W } / \mathrm { m } ^ { 2 } ) ^ { [ 6 ] }$

$$
\begin{array} { r } { Q _ { \mathrm { a b s o r d } } = I _ { \mathrm { D N I } } \cdot \cos \theta \cdot C _ { \mathrm { I A M } } \cdot R \cdot Q _ { \mathrm { e n d l o s s } } . } \\ { \eta _ { \mathrm { f i e l d } } \cdot \eta _ { \mathrm { H C E } } \cdot P _ { \mathrm { o p e r } } \quad } \end{array}
$$

式中： $C _ { \mathrm { I A M } }$ 为入射角修正系数; $Q _ { \mathrm { e n d l o s s } }$ 为集热器末端损失; $\eta _ { \mathrm { f i e l d } }$ 为集热场光学效率； $\eta _ { \mathrm { H C E } }$ 为集热管光学效率； $P _ { \mathrm { o p e r } }$ 为集热器运行比例，全部运行时取值为1。

因此，单位采光面积集热场获得的有效热量$Q _ { \mathrm { c o l } } / \mathrm { ( W / m ^ { 2 } ) }$

$$
Q _ { \mathrm { c o l } } = Q _ { \mathrm { a b s o r d } } - Q _ { \mathrm { l o s s } }
$$

其中, $Q _ { \mathrm { l o s s } }$ 为集热场管路损失及吸热器损失 $\mathrm { ( W / m ^ { 2 } }$ )[11]集热场效率计算公式如下：

$$
\eta _ { \mathrm { j r c } } = \frac { Q _ { \mathrm { c o l } } } { Q _ { \mathrm { r e c e i v e } } }
$$

# 2.2锅炉模型

为使计算简化，将锅炉看作一个黑匣子，并假设锅炉效率在槽式太阳能集热场加入前后保持不变，煤耗量 $\left( \mathrm { { k g / h } } \right)$ 可由式子表示为：

$$
m _ { \mathrm { c o a l } } \mathop { \mathcal { F } } _ { \mathrm { \normalfont {  } } } ^ { m _ { \mathrm { m s } } ( h _ { \mathrm { m s } } - h _ { \mathrm { m w } } ) + m _ { \mathrm { r s } } ( h _ { \mathrm { r o } } - h _ { \mathrm { r i } } ) }
$$

式电mms、 $m _ { \mathrm { r s } }$ 为主蒸汽流量和再热蒸汽流量,Ah; $h _ { \mathrm { m w } }$ 、 $h _ { \mathrm { m s } }$ 、 $h _ { \mathrm { r i } }$ 、 $h _ { \mathrm { r o } }$ 为锅炉入口处给水焓、锅炉出口主蒸汽焓、再热蒸汽冷端焓、再热蒸汽热段焓， $\mathrm { { k J / k g } }$ $q _ { \mathrm { c o a l } }$ 为标准煤热值, $\mathrm { { k J / k g } }$ ; $\eta _ { \mathrm { b } }$ 为锅炉效率。

# 2.3汽轮机模型

在太阳能辅助燃煤发电系统中，太阳能热的引入会引起汽轮机中的各级蒸汽流量、压力等热力参数发生变化。本模型中选用改进型弗留格尔公式来获得蒸汽流量以及抽汽点压力等热力参数的变化。

$$
\frac { m _ { i } ^ { \prime } } { m _ { i } } = \overset { \sqrt { p _ { \omega } ^ { 2 } - p _ { i + 1 } ^ { \prime 2 } } } { \oslash } \longrightarrow \frac { p _ { i } ^ { \prime 2 } - p _ { i + 1 } ^ { \prime 2 } } { p _ { i } ^ { 2 } - p _ { i + 1 } ^ { 2 } } = \left( \frac { m _ { i } ^ { \prime } } { m _ { i } } \right) ^ { 2 }
$$

式， $m _ { i }$ 为燃煤机组汽轮机中第 $\mathbf { \chi } _ { i }$ 级组的初始入口蒸汽流量， $\mathrm { k g / h }$ ： $m _ { i } ^ { \prime }$ 为加入太阳能集热系统后汽轮机中第 $i$ 级组的入口蒸汽流量， $\mathrm { { k g / h } }$

# 2.4评价指标

互补发电系统热电效率用 $\eta _ { \mathrm { r d } }$ 来表示，可由式(7)得到。

$$
\eta _ { \mathrm { r d } } = { \frac { P _ { \mathrm { e s u n } } } { Q _ { \mathrm { c o l } } \cdot \mathrm { A _ { j r c } } } }
$$

式中， $Q _ { \mathrm { c o l } }$ 为单位面积集热场获得的有效热量，$\mathrm { W / m ^ { 2 } }$ $A _ { \mathrm { j r c } }$ 为集热场面积, $\mathrm { m ^ { 2 } }$ ; $P _ { \mathrm { e s u n } }$ 为太阳能发电功率，MW，可由式(8)得到。

$$
P _ { \mathrm { e s u n } } = P _ { \mathrm { e } } \cdot \left( 1 - { \frac { b } { b _ { \mathrm { r e } } } } \right)
$$

式中， $P _ { \mathrm { e } }$ 为原燃煤火电机组功率容量，MW； $b _ { \mathrm { r e } }$ 为原燃煤火电机组标煤耗， $\mathrm { { g / k W h } }$ ; $b$ 为互补发电系统的标煤耗, $\mathrm { { g / k W h } }$ 0

互补发电系统光电效率用 $\eta _ { \mathrm { g d } }$ 来表示，可由式(9)得到。

$$
\eta _ { \mathrm { g d } } = \frac { P _ { \mathrm { e s u n } } } { \mathrm { D N I } \cdot \mathrm { A _ { j r c } } }
$$

互补发电系统太阳能发电成本LCOE：

$$
\mathrm { L C O E } = \frac { \left( \mathrm { C C } \cdot \mathrm { A F } \right) + \mathrm { O \& M } } { E _ { \mathrm { s o l a r , a } } }
$$

式中，CC为将太阳能加入燃煤机组的直接投资成本；AF是年本金利率；O&M为年运行维护成本； $E _ { \mathrm { s o l a r , a } }$ 为太阳能年发电量。

# 3案例研究

# 3.1 案例概述

本文以槽式太阳能辅助拉萨某 $3 0 0 \ \mathrm { M W }$ 燃煤凝汽式互补发电系统为例展开分析。太阳能完全取代三级高加所需要的太阳能热量为 $\mathrm { Q _ { 0 } { : } 3 . 4 8 4 { \times } 1 0 ^ { 8 } }$ $\mathrm { k J / h ( 9 6 7 7 7 ~ k W ) }$ 。

在夏至日正午12太阳时，选取太阳能直射辐照$\mathrm { D N I ~ 1 0 0 0 ~ W / m ^ { 2 } }$ 为设计条件，完全取代三级高加抽汽所需要的集热场面积为 $\mathrm { 1 2 9 1 6 4 ~ m ^ { 2 } }$ ，49os。在?该集热场面积下，太阳能倍数(Solarmultiple，SM)为1。 X

不同太阳能倍数下集热场面积、Loop 数如表1所示：

表1不同太阳能倍数下集热场面积  

<html><body><table><tr><td colspan="3">differentSM</td></tr><tr><td>状态 SM</td><td>集热场面积/m2</td><td>Loop数</td></tr><tr><td>1</td><td>129164</td><td>49</td></tr><tr><td>1.2</td><td>152888</td><td>58</td></tr><tr><td>1.4</td><td>179248</td><td>68</td></tr><tr><td>1.6</td><td>202972</td><td>77 http</td></tr><tr><td>1.8</td><td>229332</td><td>87</td></tr><tr><td>2.0</td><td>255692</td><td>97</td></tr></table></body></html>

在研究互补发电系统年性能时，采用的是拉萨典型年真实气象数据，其DNI分布如图2所示。太阳能发电成本是系统重要的经济性指标，表2中列出互补系统主要投资清单。

# 3.2互补发电系统在非设计工况下的热性能

如图3所示，随着 SM值增加，在夏至日12太阳时太阳能热依次替代#3、#2、#1三级高加抽汽，热电效率曲线在上升阶段相应地分为3个区域。当太阳能热恰好完全取代三级高加抽汽时，热电效率值达到最高 $3 7 . 3 \%$ ；当太阳能热继续增加，因多余的太阳能热废弃，热电效率下降。

![](images/dfcaf1fe1fdc3dc149a323448824a413a91502d8b7105c626e2164319b478c35.jpg)  
图2拉萨典型年太阳能直接辐射 Fig.2 typicalDNI distribution ofLhasa   
图3夏至日12太阳时不同SM下热电效率曲线 Fig.3 heat-to-electricity efficiency under different SM at 12 solar time on summer solstice

# 表2互补发电系统主要投资

Table1 various with solar fieldarea of   
Table 2 main cost of SACPG system   

<html><body><table><tr><td>版</td><td>项目</td><td>单位</td><td>单价</td></tr><tr><td></td><td>直接投资 (DC)</td><td></td><td></td></tr><tr><td></td><td>集热场</td><td>$/m²</td><td>242</td></tr><tr><td></td><td>蓄热系统</td><td>$/kWht</td><td>31.4</td></tr><tr><td></td><td>应急</td><td>%直接投资</td><td>10</td></tr><tr><td></td><td>间接投资</td><td></td><td></td></tr><tr><td></td><td>工程、基座</td><td>%直接投资</td><td>15</td></tr><tr><td></td><td>土地、管理</td><td>%直接投资</td><td>3.5</td></tr><tr><td></td><td>维护费</td><td>%直接投资</td><td>1.7</td></tr></table></body></html>

4037.3/jetp. 率电祥 3025 20 部分取代三级高加 部分取代二级高 部分取代一级高 多余热量废弃加 加太阳能热15 Y 1/107kJ/h= 0 10 20 30 40 50 60 70太阳能倍数=0.0 0.20.40.6 0.8 1.0 1.2 1.4 1.6 1.8 2.0

在图3中，当SM小于1时，随着SM值增大,太阳能热电效率从 $3 2 . 5 \%$ 开始递增，并在SM值 $\scriptstyle = 1$ 时取得极大值， $3 7 . 3 \%$ ；当SM大于1时，随着SM值递增，热电效率值从 $3 7 . 3 \%$ 递减，在 $\mathrm { S M } { = } 2$ 时降至$2 0 \%$ 以下。

可见，在互补发电热性能表现上，蓄热系统的重要性可体现为：

1）当太阳能热不足时，存储的蓄热补充太阳能热至完全取代三级高加抽汽，提高热电效率；

2）当太阳能热过多时，将多余的太阳能存储起来，提高太阳能热利用率。

基于此，本文提出了3种蓄热运行策略，研究分析互补系统在不同 SM值、蓄热容量下的性能表现，对策略方案进行优化。

# 3.3策略描述

# 3.3.1策略1削峰填谷

策略1是最为常见的运行策略，当集热场获得的太阳能热大于 $Q _ { 0 }$ 时，多余的太阳能热 $Q _ { 1 }$ 由蓄热系统存储起来，当获得的太阳能热不足 $Q _ { 0 }$ 时，蓄热系统放出热量 $Q _ { 2 }$ 补足至 $Q _ { 0 }$ ，其运行原理图如图4所示。

![](images/195d9f0de608119df9dcbb345c00cd382ab89412edf3fdd0ab33cfe39f532812.jpg)  
图4策略1蓄热系统运行原理图Fig.4 storage scheme of strategy 1

# 3.3.2策略2移谷削峰

考虑到了策略1在B阶段系统尚运行在部分取代三级高加抽汽的工况下，运行效率偏低，因而在策略2中将该阶段中的太阳能热 $Q _ { 1 }$ 存储起来，在午后光照条件不足时蓄热系统放出蓄热 $Q _ { 3 }$ 至 $Q _ { 0 }$ ，使系统运行在完全取代三级高加抽汽的工况下。其运行原理图如图5所示。

# 3.3.3策略3极端模式

考虑到了策略2将前期不足完全取代的太阳能热存储起来需要大容量蓄热系统。因此提出了极端运行模式的策略3。策略3中，针对前期不足完全取代抽汽的太阳能热，每小时都进行一次蓄热、放热：在每小时的前部分时间内先将太阳能热存储起来，并在该小时的后部分释放出来，使系统在该小时内前部分时间不取代抽汽，在后部分完全取代三级高加抽汽。策略3能够显著提高运行效率，但这需要蓄热系统的频繁的蓄热、放热操作。其运行原理图如图6所示。

![](images/13f3903e9d78b6ccfd4ba1d734b99e716d2067e0368ffaae47deb5f1aaf0a764.jpg)  
图5策略2蓄热系统运行原理图Fig.5 storage scheme of strategy 2

![](images/e3c787f3bdabef0ee89d48daef7a613c2a04e91fe4b9261ed1ee09e4fafad0d1.jpg)  
图6策略3蓄热系统运行原理图Fig.6 storage scheme of strategy 3

# 4 年性能分析

本文针对上述3种蓄热运行策略，通过建立的槽式太阳能互补发电系统模型，对互补发电系统3种蓄热运行策略下的年性能进行研究分析。

# 4.1策略1削峰填谷

互补发电系统采用策略1运行，不同蓄热小时数下年光电效率和太阳能发电成本LCOE随着太阳能倍数的变化曲线如图7所示。

![](images/0364857b0736160dcf8a5d5b7a4ff72657f7ca0108ee3cb6c4fbaccbf0ad849c.jpg)  
图7不同SM值瞎策略1光电效率、LCOEFig. 7 $\eta _ { \mathrm { g d } }$ and LCOE of strategy 1 under different SM

由图7可以看出，蓄热系统在不同蓄热小时数下，每一条年光电效率曲线都存在最大效率值。每一条曲线随着太阳能倍数的增加呈先增大后减小的趋势，在最合适的 SM值下光电效率达到最大值；商时，随着蓄热系统蓄热小时数增加，各曲线的最大效率值也呈增大的趋势。应注意的是，最大效率值的增大是以增大蓄热系统蓄热小时数为代价，增大了系统的投资成本。太阳能发电成本LCOE曲线随着 SM值增加均呈先降低后增加的趋势，存在LCOE极小值；经过对比，在6条LCOE曲线中，配置有0.5小时蓄热容量蓄热系统，在SM值为1.2时，互补发电系统太阳能发电成本LCOE取得极小值0.064$\ S / \mathrm { k W h }$ 9

# 4.2策略2移谷削峰

互补发电系统采用策略2运行，不同蓄热小时数下年光电效率和太阳能发电成本LCOE 随着太阳能倍数的变化曲线如图8所示。 ht

由图8可以看出，随着蓄热小时数增大，互补系统的光电效率增大显著；根据策略2的运行机理分析，这是由于蓄热小时数过小时，并不足以存储 $Q _ { 1 }$ 和 $Q _ { 2 }$ ，造成了太阳能热的大量浪费；随着蓄热小时数增加，太阳能热利用率增大，光电效率提高，发电量增多，太阳能发电成本LCOE 得以降低；随着蓄热小时数继续增加，过大的蓄热系统造成了系统成本显著增加，太阳能发电成本LCOE 随着增高。经过对比，在10条LCOE曲线中，配置有3小时蓄热容量蓄热系统在SM值为1.6时，互补发电系统太阳能发电成本LCOE取得极小值 $0 . 0 7 3 \ \ S / \mathrm { k W h }$ 0

# 4.3策略3极端模式

互补发电系统采用策略3运行，不同蓄热小时数下年光电效率和太阳能发电成本LCOE随着太阳能倍数的变化曲线如图9所示。

![](images/d025edf70376baf0360ee086ccdafc0d95f13f3468a9f04a012478a844737e5b.jpg)

![](images/08218c7ee46732881e491b3f0f36b6fc4b4da422cf46b3672097355a653633fd.jpg)  
图8(a）不同SM值下策略2光电效率

图8(b）不同SM值下策略2LCOE  
图9不同SM值下策略3光电效率、LCOEFig. 9 $\eta _ { \mathrm { g d } }$ and LCOE of strategy 3 under different SM  
![](images/b4dbcd55bf8202c5f8ef823f55334050e1416e74949d061afe1452768d5ae6f8.jpg)  
Fig.8(b)LCOE of strategy 2 under different SM

由图9我们能看出，策略3以极端模式运行下，随着太阳能倍数的增加，互补系统的光电效率降低；同时，蓄热小时较大的互补系统，光电效率下降得较为缓慢。这是由于太阳能倍数增大，聚集的太阳能热增多，蓄热系统当不足以储存 $Q _ { 1 }$ 热量，造成大量太阳能热浪费，导致互补系统的光电效率降低。经过分析对比，在6条LCOE 曲线中，配置有0.5小时蓄热容量蓄热系统，在SM值为1.0时，互补发电系统太阳能发电成本LCOE取得极小值 $0 . 0 6 2 ~ \mathrm { \mathfrak { F } / k W h }$ 业

# 4.4结果与讨论

通过对300MW互补发电系统在3种策略下的年性能分析，极端模式运行下的第3种运行策略其经济性表现最佳，太阳能发电成本可低至0.062$\ S / \mathrm { k W h }$ 。但就目前的工程技术水平，第3种运行策略是理想但难以实现的，一方面需要对蓄热系统进行频繁的操作，另一方面，系统也将面临运行工况频繁改变带来的严峻考验。不仅如此，本文在进行年性能模拟时，也统计了各种运行条件下蓄热系统在一年之中吸放热次数，如表3所示。

表33种运行策略下蓄热系统吸放热次数 Table 3 frequency of three strategies   

<html><body><table><tr><td>策略</td><td>吸放热次数/年</td></tr><tr><td>策略1：SM=1.2，蓄热小时=0.5</td><td>266</td></tr><tr><td>策略2：SM=1.6，蓄热小时=3</td><td>1014</td></tr><tr><td>策略3：SM=1,蓄热小时=0.5</td><td>17365 学报</td></tr></table></body></html>

由表3可以看出，运行在第3种策略下，蓄热系统吸放热操作频繁，一年中蓄热系统的吸放热次数远远大于策略1和策略.2，分别为其65 倍和 17倍。一般情况下，在光热电站中，双熔盐蓄热系统的损耗率特别低，能够持续运行30年而不用更换。但倘若蓄热系统运行在第3种策略下，蓄热系统蓄放热频繁，给系统的稳定性、安全性带来严峻的挑战。可见第3种运行策略是理想但难以实现的。

反观第1种运行策略，策略1中蓄热系统年吸放热次数仅有266次，在满足蓄热系统操作次数较少的同时，其太阳能发电成本也仅仅比策略3高了$0 . 0 0 2 ~ \ S / \mathrm { k W h }$ ，约3个百分点；同时也低了策略2将近 $0 . 0 1 ~ \ S / \mathrm { k W h }$ ，约12个百分点。因此，策略1是该$3 0 0 \mathrm { M W }$ 互补发电系统最佳的蓄热系统运行策略。

# 4结论

太阳能辅助燃煤互补发电系统，作为一种新型的光热发电形式，需要制定合理有效的运行策略，才能保障互补系统稳定运行在热性能、经济性能最佳的工况下。根据互补发电系统蓄热机制，本文提出了3种运行策略，分别为削峰填谷策略1，移谷削峰策略2以及极端模式下的策略3。针对这3种运行策略，基于已建立的互补发电系统仿真模型采用实际典型年气象数据，对拉萨槽式太阳能辅助某300

MW的凝汽式机组进行年运行仿真模拟，得出3种策略下的年性能。经过对比热性能、经济性能以及策略的可行性，策略1在0.5蓄热小时数、1.2太阳能倍数下，太阳能发电成本取得极小值 $0 . 0 6 4 ~ \ S / \mathrm { k W h }$ 是3种策略中最优的蓄热运行策略。

利用清洁能源太阳能发电能够有效减缓全球变暖和空气污染，而太阳能与常规化石能源互补发电技术已经被证明是利用太阳能发电的有效方式。本文针对互补发电技术中蓄热运行策略展开研究，所得结果可为互补发电技术的性能、成本优化提供理论指导。

# 参考文献

[1] HOU Hongjuan， YU Zhenyue, YANG Yongping，et al. Performance Evaluation of Solar Aided Feedwater Heating of Coal-fred Power Generation (SAFHCPG) System UnderDiferent Operating Conditions [J]. Applied Energy, 2013,112: 710-718 Zoschak R J,Wu S F, Studies of the Direct Input of Solar Energy to a Fossil-fueled Central Station Steam Power Plant [J].Solar Energy,1975,17: 5: 297-305   
[3] YING You, Hu E, Thermodynamic Advantages of Using Solar Energy in the Regenerative Rankine Power plant [J]. Applied Thermal Energy,1999,19:1173-1180   
[4] YING You,Hu E,A Medium-temperature Solar Thermal Power System and Its Efficiency Optimization [J].Applied Thermal Engineering, 2002,30:357-364   
[5] Hu E, YANG Yongping,Nishimura A,et al. Solar Aided Power Generation[J].Applied Energy, 2010,87(9):2881- 2885   
[6] YANG Yongping, CUI Yinghong, HOU HongJuan, et al. ResearchOn Solar Aided Coal-fred Power Generation System and Performance Analysis [J]. Science in China (SeYies E: Technological Sciences), 2008,12:11-21 ]YAN Qin, YANG Yongping, Nishimura A,et al. Multipoint and Multi-level Solar Integration Into Conventional Power Plant [J]. Energy Fuels,2010,24(7):3733-3738   
[8] YANG Yongping, YAN Qin, ZHAI Rongrong, et al. an Efficient Way to Use Medium-or-low Temperature Solar Heat for Power Generation-integration into Conventional Power Plant [J].Applied Thermal Engineering, 2011,31: 157-162   
[9] HOU Hongjuan, YANG Yongping,Hu E,et al. Evaluation of Solar Aided Biomass Power Generation Systems with Parabolic Trough Field [J]. Science China (Technological Sciences),2011,54(6): 1455-1461   
[10]黄畅，侯宏娟，徐璋,等.太阳能辅助不同容量燃煤机组热性 能分析[J].工程热物理学报,2016,V37(4)：695-700 HUANG Chang,HOU Hongjuan, XU Zhang, et al. Thermal Performance Analysis of Solar Aided Various Capacity Coal-Fired Power Generation (SACPG） System [J].Journal of Engineering Thermophysics,2016,V37(4): 695-700   
[11] Angela M P. Simulation and Performance Evaluation of Parabolic Trough Solar Power Plants [D].Ph.D.Thesis: University of Wisconsin-Madison,USA,2006