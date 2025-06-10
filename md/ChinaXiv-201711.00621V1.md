# 槽式太阳能真空吸热管真空夹层热损特性研究

# 朱天宇 金月 舒悦 蔡一凡

（河海大学机电工程学院，常州213022）

摘要：本文基于不同真空压力下槽式真空吸热管环形夹层内的四种不同传热机理，建立了真空夹层内稀薄气体的传热模型，并验证了模型及计算方法的准确性。计算了氢气穿透、漏入空气、玻璃管破裂三种情况下真空吸热管的热损值及玻璃管外壁面温度。分析了吸热管真空夹层内漏入不同气体对吸入管热损值及玻璃管外壁面温度的影响规律。结果表明氢气穿透对吸热管的性能影响最大，空气渗入次之。真空失效将显著的降低集热系统的光热转换效率。

关键字：真空吸热管；稀薄气体传热；环形夹层；热损特性 中图分类号：TM615

# Research on Heat Loss Characteristics of Vacuum Annulus in Parabolic Trough Solar

Receiver Tubes

Zhu Tian-yu Jin Yue Shu yue Cai yi-fan (School of Mechanical and Electrical Engineering, Hohai University, Changzhou 213022, China)

Abstract: Heat transfer models of rarefied gas inside the vacuum annulus were also established in this paper based on four different heat transfer mechanisms with various vacuum pressures and were proved correct. Heat loss and glass envelope temperature of receiver tubes were obtained under the conditions ofhydrogen penetration，air leak，glass breakage； heat transfer characteristics of rarefied gas inside the vacuum annulus were analyzed over diferent gas types, various vacuum pressures and ambient conditions.Analysis of the heat tube vacuum interlayer of leakage into the diferent gases on the suction pipe heat loss value and the influence law of glass tube wall temperature.The results show that hydrogen penetration is the greatest influence on the performance of the heat pipe, Air leak comes second, The vacuum failure willsignificantly reduce heating system and heat conversion efficiency.

Key Words: receiver tubes; heat transfer in rarefied gas; vacuum annulus; heat loss characteristics 符号说明：

$a$ （20 热适应系数 $P$ （20 压力，Pa ${ { T } ^ { * } }$ 有效气体温度$C _ { v }$ （204 定容摩尔热容，J/(mol·K) （204号 $P r$ （20 普朗特数 （20 $\beta$ （2 体积膨胀系数，1/K$d$ （204 特征长度，m $a$ （204 单位管长热损，W/m （204 $k$ （20 导热系数， ${ \mathsf { W } } / { ( \mathsf { m } { \cdot } \mathsf { K } ) }$ 基金项目：国家重点基础研究发展计划资助项目(2010CB227102)

$D$ （204号 直径，m  
$g$ （204号 重力加速度， $\mathsf { m } / \mathsf { s } ^ { 2 }$ ；跳跃距离， $\mathsf { m }$   
$\boldsymbol { { K } } \boldsymbol { { n } }$ （204号 克努曾数  
$M _ { g }$ （204 气体分子量

$R$ 摩尔气体常数 $\lambda$ 分子平均自由程，cm$R a$ 瑞利数 $\upsilon$ （204号 运动粘度， $\mathsf { m } ^ { 2 } / \mathsf { s }$ （204号$\tau$ （204号 温度，K $\mathcal { A }$ 热扩散系数， $\mathsf { m } ^ { 2 } / \mathsf { s }$

# 下标说明：

1 金属管外表面 Co 连续介质状态 0 外侧的2 玻璃管内表面 FM 自由分子状态 TJ 滑流状态a 环形夹层 i 内侧的 TR 过渡状态

槽式太阳能热发电是利用众多的槽型抛物面聚光集热器，经过串并联排列，达到较高的集热温度，加热工质，产生过热蒸汽，驱动汽轮发电机组发电。传统的槽式系统以导热油或熔融盐为集热工质，在高温下长期工作后分解产生的氢气能穿透金属管到达真空夹层，大气中的氨气等惰性气体也会穿透玻璃管到达夹层。封接的损坏会导致空气漏入[1][2]。

本文主要研究对象是槽式系统的真空集热管。真空吸热管是槽式太阳能热发电的核心部件之一，其性能对槽式太阳能发电系统的效率起着举足轻重的作用。集热管的热损是影响集热器效率的关键性因素，实际电站运行过程中，环形真空夹层内的真空会不可避免的出现失效现象，必须研究夹层内稀薄气体对传热的影响。本文通过研究真空吸热管真空夹层传热机理，建立真空夹层气体的传热模型，分析不同真空压力下环形气体夹层内的传热规律，获得真空压力与热损的定量关系。

# 1真空夹层气体传热模型

根据不同真空压力，环形夹层内将主要存在四种不同的传热机制，判定不同传热机制间的过渡点并选择合适的计算公式是非常重要的。

# 1.1稀薄气体状态的判定

根据稀薄气体运动理论，真空中稀薄气体的稀薄程度可以用一个无量纲参数来表示，即克努曾数（Knudsen）Kn:

$$
K n = \frac { \lambda } { d }
$$

Kn越大，则表示气体越稀薄，反之亦然。稀薄气体传热时的状态可按照 $\kappa \mathfrak { n }$ 划分为四 个区域[3].

（1） $K { \boldsymbol { n } } { > } 1 0$ ，稀薄气体处于自由分子流区；（2） ${ { 1 0 } ^ { - 1 } } { < } K { { n } ^ { < 1 0 } }$ ，稀薄气体处于过渡区；（3） ${ { 1 0 } ^ { - 3 } } { < } K { { n } { < } 1 0 } ^ { - 1 }$ ，稀薄气体处于速度滑移和温度跳跃区，也称滑流区，此区域内傅里叶导热定律、菲克定律以及N-S方程等都可适用；（4） $K n { < } 1 0 ^ { - 3 }$ ，稀薄气体处于连续介质区，可按照一般的传热学理论计算气体传热。

# 1.2自由分子流区的稀薄气体传热

计算表明，在环形空间内压力（简称环内压力）小于0.013Pa时， $K { \boldsymbol { n } } { > } 1 0$ ，环形夹层稀薄气体处于自由分子流区。对于环形夹层，其传热面为同轴圆柱，根据稀薄气体运动理论可以推导出夹层气体在自由分子流区的传热量（即单位管长的热损失）为[4I[5]：

$$
Q _ { F M } = \left[ { \frac { 1 } { a _ { 1 } } } + \left( { \frac { D _ { 1 } } { D _ { 2 } } } \right) ^ { b } \left( { \frac { 1 } { a _ { 2 } } } - 1 \right) ^ { - 1 } \right] { \frac { P _ { a } \left( C _ { \nu } + { \frac { R } { 2 } } \right) } { \left( 2 \pi R T ^ { * } M _ { g } \right) ^ { \frac { 1 } { 2 } } } } \left( T _ { 1 } - T _ { 2 } \right)
$$

式中，对于夹层为同轴圆柱传热面， $\scriptstyle \mathtt { b } = 1$ 。

# 1.3过渡区的稀薄气体传热

当环内压力达到 $0 . 0 1 3 { \sim } 1 . 3 3 \mathsf { P a }$ 时， ${ { 1 0 } ^ { - 1 } } { < } K { { n } { < } 1 0 }$ ，环内稀薄气体状态转变到过渡区。对于环形空间，气固界面为同轴圆柱，稀薄气体传热可按下式计算：

$$
\frac { { \cal Q } _ { T R } } { { \cal Q } _ { F M } } = \biggl [ 1 + \frac { 4 B } { 1 5 } \biggl ( \frac { G } { \lambda } \biggr ) a _ { 1 } \biggr ] ^ { - 1 }
$$

$$
G = \frac { D _ { 1 } } { 2 } \mathrm { l n } \frac { D _ { 2 } } { D _ { 1 } }
$$

式中，对于单原子气体， $B { = } 1$ ；对于双原子气体， $B = 4 5 / 3 8$ 。

# 1.4滑流区稀薄气体传热

当环内压力达到 $1 . 3 3 { \sim } 1 3 3 { \mathsf { P a } }$ 时， ${ { 1 0 } ^ { - 3 } } { < } { \cal { K } } _ { n } { < } { 1 0 } ^ { - 1 }$ ，环内稀薄气体转变到滑流区。在这样的中低压下，气体温度产生不连续性[。由于固体表面存在温度跳跃，对于传热过程，相当于增大了气体传热的间距。

把单原子气体和双原子气体的情况都考虑进去[7]，整理得：

$$
\frac { Q _ { \scriptscriptstyle T J } } { Q _ { \scriptscriptstyle F M } } = \left\{ \left[ \frac { 1 } { a _ { 1 } } + \left( \frac { D _ { 1 } } { D _ { 2 } } \right) ^ { b } \left( \frac { 1 } { a _ { 2 } } - 1 \right) \right] ^ { - 1 } \left[ \frac { 4 } { 1 5 } B \frac { G } { \lambda } + \frac { 1 } { 2 } \left( \frac { 2 - a _ { 1 } } { a _ { 1 } } + \left( \frac { D _ { 1 } } { D _ { 2 } } \right) ^ { b } \frac { 2 - a _ { 2 } } { a _ { 2 } } \right) \right] \right\} ^ { - 1 } \frac { Q _ { \scriptscriptstyle T J } } { Q _ { \scriptscriptstyle F M } } \left[ 2 - m \frac { m _ { \scriptscriptstyle T J } } { \lambda } \right] ^ { - 1 } .
$$

式中，对于夹层同轴圆柱， $b { = } 1$ ， $G = \frac { D _ { 1 } } { 2 } \mathrm { l n } \frac { D _ { 2 } } { D _ { 1 } }$

# 1.5连续介质区稀薄气体传热

随着环内压力进一步增大，达到133Pa以上时， $K n { < } 1 0 ^ { - 3 }$ ，稀薄气体转变到连续介质区，这时气体的自然对流开始逐渐主导环形夹层内的传热，从而导致传热系数的急剧增大。计算公式为：

$$
Q _ { c o } { = } \frac { 2 . 4 2 5 k ( T _ { 1 } - T _ { 2 } ) ( \operatorname { P r } R a / ( 0 . 8 6 1 + \operatorname { P r } ) ) ^ { 1 / 4 } } { ( 1 + ( D _ { 1 } / D _ { 2 } ) ^ { 3 / 5 } ) ^ { 5 / 4 } }
$$

式中，

$$
R a = \frac { g \beta ( T _ { 1 } - T _ { 2 } ) { D _ { 1 } } ^ { 3 } } { \mathcal { S } \upsilon }
$$

# 2槽式真空吸热管真空夹层气体的传热模拟

# 2.1 模型验证

验证气体传热模型时，计算所采用的参数参照文献[9]。

首先，将吸热管温度设定为 $2 5 0 ^ { \circ } \mathrm { C }$ ，夹层内气体类型选择氮气，模拟了从0.013Pa（ ${ { 1 0 } ^ { - 4 } }$ torr）到0.013MPa（100torr）不同真空压力下夹层热损的变化情况。将模拟结果与文献[9]测定的从 ${ { 1 0 } ^ { - 4 } }$ torr到100torr之间的15个离散真空压力值的实验结果进行比较分析，检验模型的准确性。

然后，夹层气体类型选择氮气，其真空压力设定为6700Pa(平衡时的分压)，模拟了金属管温度从 $0 ^ { \circ } \mathrm { C }$ 到 $4 5 0 ^ { \circ } \mathrm { C }$ 下夹层热损的变化情况。将模拟结果与文献[9]测定的氮气情况的8个离散值的实验结果进行比较分析，检验模型的准确性。

![](images/01e5c25ecbcd7f0e115e63b5240e8c4cdea002633ff13b0164a3c2125dc471b8.jpg)  
图1.1不同氨气压力下夹层热损的模拟对比 Fig.1.1 Values of heat loss at various helium pressure insimulationandreference

![](images/0c8f18c693018f353f51d7a8552faedd75a9e6f1891bef4d185ae960aa374262.jpg)  
图1.2不同金属管温度下夹层热损的模拟比 Fig.1.2 Values of heat loss at various absorber tube temperatureinsimulationandreference

图1.1为不同氨气压力下夹层热损的模拟计算结果和文献[9]实验数据的比较。从图中可以看出，本文模拟值和文献实验值有良好的吻合，证明本文的真空吸热管夹层气体传热模型具有较好的准确性。可以看出模拟曲线在每一个过渡区间都较光滑且与文献数据吻合良好。

图1.2表示随着金属管温度的升高，夹层内渗入氮气，且其分压达到平衡（6700Pa）的热损变化趋势。从图中可以看出，本文模拟值和文献实验值有良好的吻合，证明本文的真空吸热管夹层气体传热模型在常见温度变化范围内具有较好的准确性。

# 2.2模拟结果

本文模拟槽式真空吸热管真空夹层气体的传热时，采用类似于 Solel-UVAC真空吸热管，管内工质采用VP-1型导热油，其基本特性参数参照制造商手册。分别模拟了夹层内渗入氢气，且其分压与管内工质中的氢原子分压达到局部平衡，即133Pa的情况；夹层内完全漏入空气，即夹层内压力为0.1MPa的情况；玻璃管破裂时，金属管直接与周围环境进行换热的情况。

# 2.2.1氢气穿透的情况

图1.3为导热油温度 $3 4 0 ^ { \circ } \mathrm { C }$ ，环境温度 $2 0 ^ { \circ } \mathrm { C }$ ，环境风速 $2 \mathsf { m } / \mathsf { s }$ 时，吸热管夹层渗入氢气后，不同太阳辐射强度下吸热管热损和玻璃管外壁面温度的变化曲线。从图中可以看出，夹层渗入氢气后，吸热管热损和玻璃管外壁面温度都比良好真空条件下大幅增加。随着太阳辐射强度的增强，玻璃管外壁面温度和吸热管热损失都呈线性增加，但太阳辐射强度的变化对玻璃管外壁面温度和吸热管热损的影响不大。太阳辐射强度从 $3 0 0 \mathsf { W } / \mathsf { m } ^ { 2 }$ 增大至 $1 2 0 0 \ \mathsf { w / m } ^ { 2 }$ ，玻璃管外壁面温度只上升了 $1 . 8 ^ { \circ } \mathrm { C }$ ，而吸热管热损失也仅增加了18.2W/m。

图1.4为太阳辐射强度 $1 0 0 0 \mathsf { W / m } ^ { 2 }$ ，环境温度 $2 0 ^ { \circ } \mathrm { C }$ ，环境风速 $2 \mathsf { m } / \mathsf { s }$ 时，吸热管夹层漏入氢气后，不同工质温度下吸热管热损和玻璃管外壁面温度的变化情况。可以看出，夹层漏入氢气后，吸热管热损和玻璃管外壁面温度都比良好真空条件下大幅增加。随着工质温度的升高，玻璃管外壁面温度和吸热管热损都逐渐上升，变化趋势与真空良好情况下基本一致。

![](images/5577c6c3cb096f9ec92044fc7d761b81b9cd69400eeeb84fc3186e4129ad2f1a.jpg)  
图1.3不同太阳辐射强度下的吸热管热损和玻璃管外壁面温度 (氢气穿透）

![](images/304a0c0a89aecddd9b83d45fea27b14593d10fa4ba6fa3055173c494635e71b3.jpg)  
Fig.1.3 Heat loss and glass envelope temperature at various solar irradiation（hydrogen penetration）   
图1.4不同工质温度下的吸热管热损和玻璃管外壁面温度 (氢气穿透）  
Fig.1.4 Heat lossand glass envelope temperature at various HTF temperature （hydrogen

[在此处键入]

# 2.2.2漏入空气的情况

图1.5、图1.6分别为吸热管夹层漏入空气后，玻璃管外壁面温度和热损失随太阳辐射强度及工质温度变化的曲线。

从图中可以看出，不同工况下曲线的变化趋势和吸热管夹层真空良好以及渗入氢气两种情形基本一致。夹层漏入空气后，吸热管热损和玻璃管外壁面温度都比良好真空条件下大幅增加，但其影响小于渗入氢气。相同工况下，和夹层真空良好时相比，漏入空气后，玻璃管外壁面温度增大了约 $8 5 ^ { \circ } \mathrm { C }$ ，热损失增大了约620W/m，因此漏入空气对吸热管性能的影响也是比较大的。

![](images/0b3c0304dac667112d08ce78d3d28954b483e59007cde48dba35c1a51a44a517.jpg)  
图1.5不同太阳辐射强度下的吸热管热损和玻璃管外壁面温度 (漏入空气）

![](images/bf78b506e709feaad5c489ed0f839370701fd5f3eb9e1d293e53af1f2ad02c56.jpg)  
Fig.1.5 Heat loss and glass envelope temperature at various solar irradiation（air leak）   
图1.6不同工质温度下的吸热管热损和玻璃管外壁面温度 (漏入空气)Fig.1.6 Heat loss and glass envelope temperatureatvarious HTF temperature （air leak）

# 2.2.3 玻璃管破裂的情况

玻璃管破裂的情况下，金属管外表面的热损失将直接散失到周围环境中。图1.7、图1.8分别为玻璃管破裂后，吸热管热损失随太阳辐射强度及工质温度变化的关系曲线。

从图中可以看出，不同工况下，吸热管热损的变化趋势和前面所讨论的氢气穿透、漏入空气及良好真空的情况基本一致；玻璃管破裂后，吸热管热损失急剧增加，在相同工况下，吸热管热损失大约为夹层真空良好时的15倍。

![](images/cb3cce88b2b8e3298aeabc5915ddad1d1ab44177a3710c7efe061b28baf45d73.jpg)  
图1.7不同太阳辐射强度下的吸热管热损（玻璃管破裂）

![](images/dd435eb55f8b6495dd002d679e075c3d7e2ea8661eae14a39d2238422968a5af.jpg)  
图1.8不同工质温度下的吸热管热损(玻璃管破裂）  
Fig.1.7 Heat loss at various solar irradiation （glassbreak）   
Fig.1.8Heat loss at various HTF temperature （glass break)

# 3结论

根据建立的槽式真空吸热管真空夹层的气体传热模型，重点对真空吸热管真空夹层的热损特性进行了模拟与分析，验证了真空夹层气体传热模型的准确性和合理性；针对本文采用的真空吸热管，模拟了其在氢气穿透、漏入空气、玻璃管破裂三种情况下真空吸热管热损及玻璃管外壁面温度的变化趋势。结果表明氢气穿透对吸热管的性能影响大于空气漏入的影响，真空失效情况下吸热管对环境条件的改变较为敏感；真空失效将显著的降低集热系统的光热转换效率。本文结论可以为今后槽式太阳能真空吸热管的设计及运行提供理论参考依据。

# 参考文献

[1]东朝阳．槽式太阳能集热器热效率分析研究[D].华北电力大学,2013.   
[2] Price H,Forristall R,Wendelin T,Moss T, et al.Field Survey of Parabolic Trough Receiver Thermal Performance[R]. Conference Paper NREL/CP-550-39459, 2006.   
[3] 邓东泉,徐烈,孙恒,肖尤明,朱鸿梅;真空下气固界面的传热[J],低温与超导 2002,5,30(2):52—56. [4] Shen C. Rarefied Gas Dynamics[M]. Berlin, Heidelberg: Springer-Verlag Berlin Heidelberg, 2005. [5] Chen GB, Zhang P. Low-temperature Thermal Insulation and Heat Transfer Technology[M]. Beijing: Science Press,2004.   
[6] Dushman S.Scientific Foundations of Vacuum Technique[M]. New York: John Wiley and Sons, 1962.   
[7] Springer G S,Heat transfer in Rarefied Gas, Advances in Heat Transfer[M]. Academic Pres,New York, 1971, 7: 163-218.   
[8] Bejan A. Convection Heat Transfer[M], Second Edition. New York, NY: John Wiley & Sons,1995. 228.   
[在此处键入]

[9] Gong GJ et al. Modelling and Test Results on Heat Loss of Vacuum Absorber Tuber in Parabolic Trough Solar Plant[J]. In: Proceedings of ASME International Colloquium on Environmentally Preferred Advanced Power Generation, Costa Mesa, CA,USA,2010: 9-11.