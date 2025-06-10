# 变极性等离子弧焊电弧物理特性的数值模拟

陈树君 徐 斌蒋凡

(北京工业大学机电学院汽车结构部件先进制造技术教育部工程研究中心北京100124)

摘 要基于磁流体动力学及Maxwel方程组，建立了变极性等离子电弧的三维瞬态计算模型，依据变极性等离子弧焊对铝合金板材穿孔焊接过程的物理特性，提出了随电弧极性变化的分时导电模型，通过计算得到了变极性等离子电弧的温度场、流场、电流密度和电弧压力的分布情况，以及电弧压力随时间的变化过程。通过实验测量了工件表面电弧中心压力，得到了不同极性时的电弧形态。结果表明：相同电流条件下，正极性时电弧温度场分布比反极性时更加分散，但正极性时电弧最高温度范围小于反极性时；反极性电弧压力和电流密度在电弧中心处均大于正极性，在经向距电弧中心一定距离处，2 种极性时的电弧压力茶  
和电流密度的大小出现反转；电弧压力对焊接电流响应迅速，正极性电弧压力小于反极性电弧压力，焊接电流过零时，电弧压力会降低到较低的值，流增如时电弧压力变化存在"缓冲"现象；对实验与计算得到发  
的变极性等离子电弧正反极性时电弧图像和工件表面电弧中心压力进行了对比，结果吻合良好。

关键词 变极性等离子电弧，三 ，数值模拟

中图分类号 TG456.2

# Numerical Simulation of Physical Characteristics of Variable Polarity

# Plasma Arc Welding

CHEN Shujun, XU Bin Engineering Research Center of Advanced Manufacturing Techgglogy for Automotive Components, Ministry of Education,Beijing University OfTechnology,Beijing100124

Correspondent: JIANG Fan, Tel: (010)67391620, E-mail: jiangfan@bjut.edu.cn

Supported by Young Scientists Fund of the National Natural Science Foundation of China (No.51505008) and

National Science and Technology Major Project of the Ministry of Science and Technology of China (No.2014zx04001-171)

Manuscript received 2016-06-27，in revised form 2017-02-22

ABSTRACT Variable polarity plasma arc (VPPA) is a kind of source to provide heat and force at welding proces. It can remove the oxide layer with high melting point on the surface of base metal using the cleaning action of cathode spots (the special property of VPPA). So variable polarity plasma arc welding (VPPAW) is a very suitable method to join aluminum alloys which always have extremely tenacious surface oxides.It is great significant to understand clearly the physical characteristics of VPPA for predicting welding defects and making the welding process stable. Therefore, modeling and simulating VPPAs are necessary and helpful to understand welding process theoryand promote its application further In this work,a three dimensional transient calculated model of VPPA was established.To describe the electrical characteristics of VPPA at different polarities,a sequential electric conducting model was proposed.With finite diffrence method,the temperature field,fluid flow and 公   
current density of VPPA were solved out. And the dist bution of plasma arc pressure on the anode surface ，as wellas its evolution processas the time going on were analyzed. Arc pressure was measured experimentally to 沙方   
verify the calculated model.The results show that thearc temperature field of EN (electrode negative) is more compressed than that of EP(electrog ositi But the range of high temperature at EN is a little bigger. Arc pressure and current density ofEN at central area are both higher than EP. Nonetheles,the magnitude of these values begins to reverse a rta Istance to center in radial direction. MoregVer, the arc pressure rapidly responses to welding current. Pressure at EP is about $20 \%$ lower than t it of EN. The pressure reduces to the 方   
lowest value when the current pass through O.After that, while the current reaches to normal value, the pressure will immediately impact to a larger value, then quickly recov rage value. Otherwise, to compare the experimental results with calculated results of arc images and arc pressure, they are in good agreement with each other.

KEY WORDS variable polarity plasma arc, three dimensional model, numerical simulation

铝合金作为一种轻质材料，不仅可以减轻工程制造领域中构件的重量，而且可以使结构件达到较高的强度，在航空航天、汽车制造及船舶行业等领域应用越来越广泛。变极性等离子弧焊以其良好的焊接质量和高效的焊接过程，成为铝合金结构件加工制造过程中较为理想的焊接方法。它采用交流方波电流，幅值和占空比独立可调，焊接过程中正极性(EP，W 针接焊接电源正极，工件接焊接电源负极，电流从W 针流向工件)与反极性(EN，W 针接焊接电源负极，工件接焊接电源正极，电流从工件流向W 针)之间周期性切换，正极性半波时工件表面氧化膜被清理干净，在拘束态电弧强大的等离子流吹力的作用下形成穿孔效应，可实现中厚板的一次焊接成形[1]，该方法已成功应用于航天飞机外储箱铝合金结构部件的焊接[2]。但目前等离子弧焊接工艺范围窄，稳定性和可重复性差，并且高能拘束态电弧在极性切换及外界环境影响时会出现电弧失稳，导致焊接缺陷的产生。因此，深入分析变极性等离子电弧机理，研究其热力输出作用，对拓宽变极性等离子弧焊工艺窗口，推广其工程应用，有着广泛的工程实用价值和深刻的理论指导意义。

目前，研究者对于电弧的检测已做了大量研究工作，包括电信号采集[3]、CCD 视觉传感[4.5]、光谱诊断[.7]、探针测量[8-10]、气压传感[1,12]和声信号传感[13,.14]等，利用这些方法对电弧物理有了一定程度认识，但由于电弧等离子体弧光强、流速快且各物性参数变化梯度大，单纯通过实验很难将细节信息量化。

近年来随着计算机技术的不断发展，数值模拟理论不断完善，焊接电弧的计算机模拟得到了长足的进步。对于电弧等离子体的数值模拟，国内外学者已取得了大量的研究成果[15-23]，但大多采用二维轴对称模型，在柱坐标系下求解电弧特性，与实际的电弧三维状态差别较大。Lago等[24]对三维模型和二维模型计算结果进行了对比，结果表明，2种模型对自由态电弧的计算几乎没有差别，但外加能量场使电弧偏转后，2种模型结果差别较大。Blais 等[25]计算了Ar气环境下的三维电弧，分析了外加磁场下电弧的偏转效应。Xu?等[26提供了一个较为符合实际的三维模型，利用该模型可以研究外界干扰对电弧的影响，为熔池动态变化过程建模提供了更加准确的边界条件。另外，为了进一步得到电弧对工件更加准确的热力传输结果，研究济者[27-33]在单电弧计算的基础上成功实现了包括工件W针在内的耦合电弧数值计算，计算结果表明，将电弧区与焊接工件设置为耦合边界，以实现弧对工件的热力传输作用，得到电弧作用下的熔池流场与温度场演变过程。Lowke和 Tanaka[34利用"局部热力学平衡扩散近似"的方法处理边界层，克服了近电极区电弧平衡电导率几乎为0的题，便台计算更加准确可靠。与直流电弧相比交流电弧的计算更加复杂。Tashiro 等[35基于能量守恒得到了氧化清理速率计算公式，同时考虑了阴阳极表面的产热特点，计算得到了老阳校交流电弧的二维电弧温度场及对工件的热传导作用。

上述研究大都集中于自由电弧或Ar气环境下的电弧计 而高 束态电弧物理的模型复杂，温度及流速梯度变化大，增加了电弧数值模拟研究的难度。研究者[36-3通过建立包括压缩喷嘴的物理模型，计算了X压缩等离子体的物理特性。Yin 等[3通过计算等离体电弧，得到了弧柱区内温度场与流场以及电磁力和电流密度的分布情况。Zhou 等[40-42]对比了不同湍流模型、不同压缩喷嘴尺寸以及旋转等离子气流对等离子电弧物理特性的影响，确定了与实际温度场吻合良好的湍流模型，并对等离子体切割弧进行了系统的模拟，另外，研究者[43]还研究了保护气对切割电弧的特性影响，发现保护气会使弧压增加，保护气成分对电弧电压没有影响。Jian 和 $\mathrm { W u } ^ { [ 4 4 , 4 5 ] }$ 建立了定点焊电弧与熔池耦合模型，将工件区域设置成流体，在计算所得到的电弧热力作用下，得到了直流等离子穿孔焊接小孔的演变过程。

与直流压缩等离子体相比，变极性等离子电弧的电流流向周期性切换，正极性时存在清理氧化膜的过程，其导电模式与直流电弧存在较大区别，建模过程中边界条件很难确定，因此，目前的研究中对于变极性等离子电弧的数值模拟研究较少。本工作深入分析了变极性等离子弧焊过程中电极发射电子特点，以及在铝合金工件穿孔稳定后的导电特性，建立了三维变极性等离子弧物理模型，提出了变极性等离子电弧的分时导电模型，得到了正反极性时电弧温度场和电弧压力的变化情况。搭建了变极性等离子弧焊电弧压力测试平台，实验测得了工件表面电弧中心处的电弧压力，通过高速摄像技术得到了不同极性时的电弧形态，对计算模型进行了验证。

# 1实验方法

本工作搭建了变极性等离子电弧压力与电弧图像采集平台，同时，为了分析变极性等离子弧焊穿孔后的导电情况，对铝合金板材进行了定点穿孔焊接实验。如图1所示。变极性等离子弧焊机以80C196KC 单片机为控制核心，主电路为双逆变型电路拓扑结构的VPPA-5 型变极性等离子逆变电源，焊枪通过冷却水制冷，EN 与EP 时间内的焊接电流相等，均为 $1 0 0 \mathrm { A }$ 。为了确保工件表面氧化膜清理效果，并且减轻W 针的烧损情况，每个周期内 EN与EP 的持续时间非别为10 和 $5 \mathrm { m s }$ ，正反极性转换时间为 $0 . 1 ~ \mathrm { m s }$ ，等离子气和保护气为纯Ar，等离子气流量为 $3 . 0 \mathrm { L } / \mathrm { m i n }$ ，保护气流量为 $1 5 \mathrm { L } / \mathrm { m i n }$ 。

![](images/3f699a62eb9f6a13c5251afb500c0dbbcdae233cef4a67ed67e0a8b48bbaab1f.jpg)  
图1变极性等离子弧压力测试及电弧图像采集系统

Fig.1 Measure system of arc pressure and image of variable polarity plasma arc (VPPA)

选用 HSTL-800 的压力变送器，该压力变送器可以将传输到其内部的气体压力转换为 $0 { \sim } 5 \mathrm { v }$ 电压输出，线性度良好，测量精度可达毫秒级别。水冷Cu块作为电极的一端与焊接电源相连，水冷Cu块分为2层，上层Cu块较薄，中心钻有直径非常小的小孔，等离子电弧压力通过小孔传递，下层Cu块较厚，中心为带有螺纹的通孔，压力变送器通过此螺纹孔固定，冷却水在下层Cu块内循环流动。实验过程中同时采集焊接电流以及变极性等离子电弧图像。

等离子穿孔实验选用 $5 \ \mathrm { m m }$ 厚的 5083 铝合金，其化学成分(质量分数， $0 \%$ 为： $\mathrm { S i } { \le } 0 . 4 0$ ， $\mathrm { C u } { \leq } 0 . 1 0$ ，Mg

4.0\~4.9， $Z \mathrm { n } { \le } 0 . 2 5$ ， $ { \mathrm { M n } } 0 . 4 { \sim } 1 . 0$ ， $\mathrm { T i } { \le } 0 . 1 5$ ，Cr0.05\~0.25，Fe0\~0.40，A1余量。将该铝合金板材通过酸洗钝化处理。

2变极性等离子电弧计算模型

# 2.1 物理模型

变极性等离子电弧与直流等离子电弧的压缩原理相同，但在不同极性时电弧形态会出现明显差别。图2所示为变极性等离子电弧不同极性时电弧形态示意图。等离子气体从W针与喷嘴之间流入，随即被电离成为等离子体，保护气从喷嘴与保护罩之间流入，对焊接熔池起保护作用，在压缩作用下形成高能束等离子电弧。电弧在EN半波时，W 针接电源负极发射电子主导电弧，在工件表面的阳极斑点寻找纯金属；而在 EP 半波时，工件发射电子，向电弧持续提供能量，此时工件表面的阴极斑点主动寻找氧化膜，因此 2个不同极性时的电弧形态会出现一定差别。 茶

![](images/525c13a7f5bb584ece448e15675a974eed2a449aadaf9b427f580f0aa83f3392.jpg)  
图2不同极性时变极性等离子电弧示意图

Fig.2 Schematic of VPPA at different polaritie8 (EN—electrode negative, EP-electrode positive)

# 2.2 磁流体动力学模型

为了简化计算做出如下假设：(1）等离子电弧处于局部热力学平衡状态；(2）计算域内流体为层流；(3)忽略由于流体内摩擦(黏性)和流体不同部分之间的热交换引起的能量耗散过程；(4)等离子电弧相对面对称；(5）电弧为连续介质，流体微元足够大，虽然相对物体体积足够小，但相对分子间距离足够大，即本工作研究流体的宏观性质。在上述假设的基础上，得到描述等离子电弧的控制方程。

质量守恒方程：

$$
\frac { \partial \rho } { \partial t } + \rho \mathrm { d i v } \nu = 0
$$

动量守恒方程：

$$
\begin{array} { r l } & { \frac { \Delta x _ { \theta } } { \Delta t } ( x , q , \theta , - \theta , \theta , \frac { \theta } { \theta } ) = } \\ & { \qquad - \frac { \epsilon } { \Delta t } \left[ \int _ { 0 } ^ { 1 } \frac { \Delta x _ { \theta } } { \Delta x } - \frac { \Delta x _ { \theta } } { \Delta y } \frac { \partial x _ { \theta } } { \partial x } \frac { \partial x _ { \theta } } { \partial y } \right] } \\ & { \qquad - \frac { \epsilon } { \Delta y } \frac { \epsilon } { \partial x } \frac { \partial x _ { \theta } } { \partial x } \frac { \partial x _ { \theta } } { \partial y } \frac { \partial x _ { \theta } } { \partial x } \frac { \partial y } { \partial x } \frac { \partial x _ { \theta } } { \partial y } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } } \\ & { \qquad - \frac { \epsilon } { \Delta y } \frac { \epsilon } { \partial x } \frac { \partial x _ { \theta } } { \partial y } \frac { \partial x _ { \theta } } { \partial y } \frac { \partial x _ { \theta } } { \partial y } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial y } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial y } } \\ & { \frac { \Delta x _ { \theta } } { \partial x } ( x , q , \theta , \theta , \theta , \theta , \theta , \theta , \theta , \theta , \theta ) \frac { \partial } { \partial \theta } \frac { \partial } { \partial y } \frac { \partial x _ { \theta } } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } \frac { \partial y } { \partial x } } \\ &  \qquad \quad \leq \frac { \epsilon } { \Delta y } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial y } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial } { \partial x } \frac { \partial }  \partial x  \end{array}
$$

能量守恒方程：

$$
\begin{array} { r l } & { \sqrt { \displaystyle { \sum _ { \hat { \mathcal { X } } } } } \displaystyle \sum _ { \hat { \mathcal { X } } } \hat { ( \rho { c _ { \mathrm { p } } } T ) } ^ { \hat { \mathcal { X } } } \displaystyle \sum _ { \hat { \mathcal { X } } } { \rho { c _ { \mathrm { p } } } \mathrm { d i v } ( T \nu ) } = \frac { \hat { \mathcal { O } } } { { \hat { \mathcal { O } } } x } \bigg ( k \frac { \hat { \mathcal { D } } T } { { \hat { \mathcal { D } } } x } \bigg ) + \frac { \hat { \mathcal { O } } } { { \hat { \mathcal { O } } } y } \bigg ( k \frac { \hat { \mathcal { O } } T } { { \hat { \mathcal { D } } } y } \bigg ) + \frac { \hat { \mathcal { O } } } { 8 \times } \oint \oint \oint _ { \Sigma } } \\ & { \quad \quad \quad \quad + \frac { { J _ { x } ^ { 2 } + J _ { y } ^ { 2 } + J _ { z } ^ { 2 } } } { \sigma } + \frac { 5 k _ { \mathrm { B } } } { 2 \sqrt { \hat { \mathcal { A } } } } \bigg ( J _ { x } \frac { \hat { \mathcal { O } } T } { { \hat { \mathcal { H } } } \times } + J _ { y } \frac { \hat { \mathcal { O } } T } { { \hat { \mathcal { O } } } y } + J _ { z } \frac { \hat { \mathcal { O } } T } { { \hat { \mathcal { O } } } z } \bigg ) } \\ & { \quad \quad \quad \quad - S _ { R } } \end{array}
$$

式中， $\rho$ 为密度； $\scriptstyle \pmb { \nu } = \boldsymbol { u } \pmb { i } + \boldsymbol { \nu } \pmb { j } + \boldsymbol { w } \pmb { k }$ ，为速度矢量； $i , j$ 和 $\pmb { k }$ 分别 $y$ 和向的单位矢量； $u , \ \nu$ 和 $w$ 分别为上述3个方向的速度分量； $J _ { x \setminus \ } J _ { y }$ 和 $J _ { z }$ 分别为上述3个方向的电流密度； $B _ { x } , \ B _ { y }$ 和 $B _ { z }$ 分别为上述3个方向磁感应强度； $P$ 为压力； $\mu$ 为黏度系数： $c _ { \mathfrak { p } }$ 为比热为温度： $k$ 为导热系数： $k _ { \mathrm { B } }$ 为 Boltzman常数； $e$ 为一个电荷的电荷量； $S _ { \mathrm { R } }$ 为辐射损失。

动量守恒方程中有Lorentz力项，能量守恒方程中有Joule 热项，需要求解磁感应强度 $B$ 和电流密度 $J$ 的分布，因此需要求解Maxwell方程组。

Ohm 定律：

$$
J _ { x } = - \sigma \frac { \hat { \sigma } \phi } { \hat { \sigma } x } = - \sigma E _ { x } , J _ { y } = - \sigma \frac { \hat { \sigma } \phi } { \hat { \sigma } y } = - \sigma E _ { y } , J _ { z } = - \sigma \frac { \hat { \sigma } \phi } { \hat { \sigma } z } = - \sigma E _ { z }
$$

电流连续性方程：

$$
\frac { \partial } { \partial x } \Bigg ( \sigma \frac { \hat { \sigma } \phi } { \hat { \alpha } x } \Bigg ) + \frac { \hat { \sigma } } { \hat { \alpha } y } \Bigg ( \sigma \frac { \hat { \sigma } \phi } { \hat { \sigma } y } \Bigg ) + \frac { \hat { \sigma } } { \hat { \alpha } z } \Bigg ( \sigma \frac { \hat { \sigma } \phi } { \hat { \alpha } z } \Bigg ) = 0
$$

磁矢势的Poisson方程：

$$
- \nabla ^ { 2 } A _ { x } = \mu _ { 0 } { J _ { x } } , \mathrm { ~ } - \nabla ^ { 2 } A _ { y } = \mu _ { 0 } { J _ { y } } , \mathrm { ~ } - \nabla ^ { 2 } A _ { z } = \mu _ { 0 } { J _ { z } }
$$

$$
B _ { x } = \frac { \partial A _ { z } } { \partial y } - \frac { \partial A _ { y } } { \partial z } , B _ { y } = \frac { \partial A _ { x } } { \partial z } - \frac { \partial A _ { z } } { \partial x } , B _ { z } = \frac { \partial A _ { y } } { \partial x } - \frac { \partial A _ { x } } { \partial y }
$$

式中， $\sigma$ 为电导率； $\phi$ 为电势； $E _ { x }$ 、 $E _ { y }$ 和 $E _ { z }$ 为3个方向电场强度； $\textstyle A _ { x }$ 、 $A _ { y }$ 和 $A _ { z }$ 为3个方向磁矢势； $\mu _ { 0 }$ 为真空磁导率。

# 2.3变极性等离子电弧分时导电模型

在焊接过程中，变极性等离子电弧的电流方向高频率切换，电流换向时 W 针端面和工件表面的物理状态产生很大变化。针对电弧电流的特点，首先以W针区域为研究对象，对W极端面的电流密度边界条件进行了分时处理。变极性过程实际为W针区交替进行的电子发射和接收过程，在EN时W 针为电子发射源，根据电弧物理中的最小电压原理可知，从W针尖端到四周电子，发射能力会逐渐减弱。而EP时工件为电子发射源，W针开始接收电子，进入W针喷嘴的电子密度很高，在W针端面几乎均匀接收电子。格因此，本工作提出了EN时W针端面Gauss面分布电流密度和 EP时均匀分布的电流密度，电流密度在W针端面上随时间的变化情况如式(10)(13)

EN时：

$$
\frac { 5 4 } { 1 _ { z } ( x , y ) } = - J _ { \mathrm { m a x } } \exp ( - 6 ( x ^ { 2 } + y ^ { 2 } ) )
$$

E 金预

EP时：

多

$$
J _ { _ z } ( x , y ) = \frac { I _ { _ \mathrm { E P } } } { \pi r _ { a } ^ { 2 } }
$$

海方

EN 向EP 转变时：

$$
J _ { z } ( x , y ) = { \frac { 1 } { \pi r _ { a } ^ { 2 } } } ( ( I _ { \mathrm { E P } } - \overbrace { \frac { 2 \imath \mathrm { e } \psi } { \hbar \mathrm { e } \psi } } ^ { \mathbf { \large \langle } \mathbf { \left( \right)} \mathrm { n S } \lambda \overbar { \psi } _ { \mathrm { \overline { { H } } } }  } + I _ { \mathrm { E N } } )
$$

EP 向 EN 转变时，

$$
J _ { z } ( x , y ) = \frac { 1 { \mathcal { V } } } { \pi r _ { a } ^ { 2 } } ( ( I _ { \mathrm { E N } } - I _ { \mathrm { E P } } ) \frac { \mathbf { \bar { \mu } } - ( ( \mathrm { n + 1 } ) \mathbf { S } - t _ { \mathrm { s } } ) } { t _ { \mathrm { s } } } + I _ { \mathrm { E P } } )
$$

式中， $J _ { z } ( x , \ y )$ 为W针端面电流密度； $J _ { \mathrm { m a x } } { = } 1 . 6 { \times } 1 0 ^ { 8 } \mathrm { ~ \ A / m } ^ { 2 }$ ，为峰值电流密度， $J _ { \mathrm { m a x } }$ 由$I _ { _ \mathrm { E N } } = \iint _ { D } J _ { \mathrm { m a x } } \exp ( - { \mathsf { b } } ( { \mathsf { x } } ^ { 2 } + { \mathsf { y } } ^ { 2 } ) ) d x d y$ 确定， $D$ 为半径 $0 . 5 \mathrm { m m }$ 的圆面； $b$ 为常数，取-1.94; $I _ { \mathrm { E P } } { = } { \ - 1 0 0 } \mathrm { A }$ ，为正极性电流， $I _ { \mathrm { E N } } { = } 1 0 0 \mathrm { A }$ ，为反极性电流； $n$ 为周期数； $S$ 为周期； $t _ { \mathrm { s } }$ 为正反极性切换所需时间； $t$ 为焊接时间;$r _ { \mathrm { a } }$ 为 $\mathrm { ~ w ~ }$ 针端面半径； $t _ { \mathrm { E N } }$ 为 EN时电流的持续时间。

另外，变极性等离子弧焊接过程中，随着电弧极性的周期性切换，电弧在焊接工件上的作用区域存在明显差异，电流流经位置随之变化。EN 时工件接电源正极，在工件表面附近的电弧区域形成阳极斑点，阳极斑点主动寻找纯金属，因此电流主要通过电弧中心区；EP 时工件接电源负极，电弧在工件表面形成阴极斑点，阴极斑点主动寻找氧化膜，所以电流主要通过四周氧化膜区域。因此本工作在工件表面设置了分时导电区域，即根据变极性时序在工件表面设置0电势的区域,在EN 时电流通过半径为 $m _ { 1 }$ 的圆面导通，

EP 时电流通过半径为 $m _ { 1 }$ 与 $m _ { 2 }$ 之间的圆环导通，其中 $m _ { 1 } { < } m _ { 2 }$ ，将这种分时序设置的电势称为 $\phi _ { \mathrm { V P P A } }$ 。

# 2.4 边界条件

基于变极性等离子电弧原理以及喷嘴结构，同时兼顾计算效率，在不影响三维效果的前提下建立了电弧的四分之一作为求解域，如图3所示。图中给出了求解区域尺寸及各几何面的边界条件。该几何模型包括了压缩喷嘴、阴极区与阳极区(本工作将W 针尖端简化为直径 $\mathrm { ~ 1 ~ m m }$ 的圆面)。另外，W 针直径为 $4 . 8 \mathrm { m m }$ 带有 $6 0 ^ { \circ }$ 倾角的尖端，W针内缩量 $4 \mathrm { m m }$ ，弧柱区高度 $4 \mathrm { m m }$ ，喷嘴孔径 $3 . 2 \mathrm { m m }$ 。等离子气入口和保护气入□为给定的常量，指定W 针端面温度 $3 0 0 0 \mathrm { K }$ ，除W 针端面和对称面以外的其它边界面温度为 $1 0 0 0 \mathrm { K }$ ，忽略各面向外界的辐射热损失，并假设其温度统一为 $1 0 0 0 ~ \mathrm { K }$ 。由于低温时Ar气的电导率非常小，为了保证初始时刻计算域内的导电性，将初始化温度设为 $8 0 0 0 \mathrm { K }$ 。其他边界条件如表1所示。

![](images/70c0763a1c7076adaa8c189a669e54c6eea3d7315c4b8e0bdade56d7ce83f4b5.jpg)  
图3求解区域及 条件存  
Fig.3 Solution area and boundary conditions

表边界条祥

Table 1 Boundary conditions   

<html><body><table><tr><td>Boundary</td><td>v / (m·s-1)</td><td>T/K</td><td>/V</td><td>A / (Wb·m-1)</td></tr><tr><td>ABC</td><td>v=0 an</td><td>1000</td><td>Φ=Φ VPPA</td><td>A=0 an</td></tr><tr><td>APOTXUQLGFEDC,APNSWVRMHIJKB</td><td>=0 an</td><td>T=0 an</td><td>=0 an</td><td>A=0 an</td></tr><tr><td>LGHM,XTONSW,UQLMRV,FGHI,EJK</td><td></td><td>1000</td><td>=0</td><td>A=0</td></tr><tr><td>OPN</td><td>=</td><td>3000</td><td>(10)-(13) an</td><td>an A=0</td></tr><tr><td>UXWV, EFIJ</td><td>v=Vconstant</td><td>1000</td><td>=0</td><td>an A=0</td></tr><tr><td>CBKD</td><td>（pv） =0 an</td><td>1000</td><td>an =0 an</td><td>an 0</td></tr></table></body></html>

Note: v—velocity vector, $n$ —unit vector normal to the surface, Vconstant—velocity constant based on gas flow rate, $\rho$ density, T—temperature, $\phi$ electric potential, $\phi _ { \mathrm { V P P A } }$ electric potential distribution at different polarity, A—magnetic potential vector

# 3结果与分析

依据所建立的变极性等离子电弧数值计算模型，编写用户自定义方程(UDF)，对 Fluent 流体计算软件进行了二次开发，计算分析了变极性等离子电弧的物理特性，并通过实验结果与计算结果的对比，对模型进行了验证。

# 3.1 模拟结果与分析

电弧对焊接工件的作用主要体现在热与力的传输过程，电弧的热力作用决定了焊接熔池三维分布形态，进而影响焊缝质量。图4给出了EN 和EP 时等子电弧的温度场和流场分布。可以看出，由于压缩喷嘴的作用，电弧明显被压缩，温度梯度增加。电弧处于EN时，工件表面形成阳极斑点，纯金属相比氧汉化膜更易接收电子，因此阳极斑点会主动"寻我"纯金属，电弧更加拘束，其达到 22000K以上高温区范围相比 EP 时大。从图4中的流场分以看温度越高的区域流体流速越快，最高流速主要集中于电弧轴线上。对比EN 和EP时的等温线可以看出，变极性等离子电弧在EP 时的温度场范围明显大于EN时的分布范围，以 $1 0 0 0 0 \mathrm { K }$ 等为例弧在EN状态时，1000K等温线与电市心轴线距离约为 $4 . 4 \mathrm { m m }$ ，在 EP状态时约为 $5 . 6 \mathrm { m m }$ 。变极性等离子电弧在2个不同状态时，EN时的最高温度分布范围大于EP时，济花而 EP 时低于最高温的范围大于 EN时。电弧不同极性时的温度场分布与理论分析较吻合，从而印证了模型的准确性。

![](images/fac140e0b24c7b4989b77e0385cac65222331a8b1ece3dcbbe60c89686775ec2.jpg)  
图4不同极性时变极性等离子电弧的温度场与流场分布

Fig.4 Temperature and flow field distributions of VPPA at EN (a) and EP (b)

图5为距等离子喷嘴 $3 \mathrm { m m }$ 处 $\mathrm { ( x { = } 7 ~ m m ) }$ 径向上的温度分布曲线，给出了三维模型中不同截面上的结果。随着与电弧中心轴线距离的增加，电弧温度逐渐减小，减小趋势接近线性模式。不同截面上的温度变化曲线不同，表明电弧温度的三维分布趋势不是完全对称的。各截面上EN和EP状态时的温度曲线表明，2种状态下在电弧中心轴线上和远离电弧中心处的温度温度基本相同，而在径向距离的中间区域 EP 时的温度大于EN 时，在 $x y$ 截面上电弧处于EN状态时温度较低，到 $1 0 0 0 0 \mathrm { K }$ 时与电弧中心的径向距离约为 $4 . 2 \mathrm { m m }$ EP 时此距离约为 $5 . 3 ~ \mathrm { m m }$ ，在 $x z$ 截面时上述两距离分别为4.4 和 $4 . 9 \mathrm { m m }$ ，说明电弧在三维各方向的温度场分布存在一定差别，不适宜用简化的二维模型进行描述。

![](images/eb70500b335aa7c4bd368e7b601be76973d83d10fe4b7bde80a565837a046bfd.jpg)  
[5 变极性等离子电弧径向温度分布曲线

原5

5 Radial temperature distributions of VPPA ( $\scriptstyle \chi = 7$

称

送方

变极性等离子电弧对焊接工件的另一项重要作用为力的传输，由于电弧形态在不同极性时存在明显差情况与电弧中心处电弧压力随时间的变化情况进行分析。图为变极性等离子电弧压力径向分布。总体沿径向呈 Gauss 分布，电弧中心压力最大，向四周逐渐低，时电弧中心处最大电弧压力为 X 参 $1 . 5 3 \mathrm { { k P a } }$ ，EP时为 $1 . 1 7 \ \mathrm { k P a }$ ，由于EN时的电弧拘束程度比EP 时大，因此虽然 EN 时电弧中心处电弧最大压力大于 EP时的电弧压力，但 EN 时电弧压力随距离的增加其降低速度大于 EP 时的电弧压力降低速度，因此两电弧压力曲线在距电弧中心约 $0 . 6 \ \mathrm { m m }$ 处重合，此时电弧压力约为 $1 \ \mathrm { k P a }$ ，随后 EP 时的电弧压力大于EN 时电弧压力，到达距离电弧中心较远的区域后，电弧压力曲线重合。由上述变极性等离子电弧压力径向分布特点可以看出，正反极性电流相同时，反极性的电弧对工件的穿透力强，电弧高压范围窄，正极性时电弧中心压力低，穿透力弱。因此，在利用变极性等离子电弧对工件进行穿孔焊接时，需要在保证清理氧化膜效果的前提下尽量延长反极性时间，以确保电弧的穿透效果。

![](images/5ce761193aeaf0a364bb32a9a716af470a195c1a4d5ecee963d1a402daa74147.jpg)  
图6变极性等离子电弧径向压力分布  
Fig.6 Radial pressure distMbutions of VPPA $\scriptstyle ( x = 7 { \mathrm { ~ m m } }$

属 收

等离子电弧被压缩之后形成了高温高速流动的等离子体，等离子体的流动会对电弧的热力传输起到决4定性作用，研究等离子体流可以深对等离子体作用机理的理解，为分析焊接过程电弧等离子体冲击力提供输入条件，如等离子体对熔池自由表面的冲击作用，以及填丝焊时熔滴由于等离子体冲刷受到的力作沙交用。图7给出了不同极性时电弧轴线上等离子体流速分布情况。 $x { = } 4 \ \mathrm { { \dot { m } } \mathrm { { m } } }$ 处为喷嘴端面，在喷嘴内部等离子体流速先增加后减小，最大值出现在喷嘴内部，在喷嘴等离子流速持续减小。EN 时的流速总体大于 EP 时的流速，EN 时最大等离子体流速出现在喷嘴内部距喷嘴端面 $1 . 9 \ \mathrm { m m }$ 处 $( x { = } 2 . 1 \ \mathrm { m m }$ ，最大值为欧你$5 1 4 \mathrm { m / s }$ ，EP 时最大流速出现在喷嘴内部距喷嘴端面.8mm 处 $\cdot x { = } 3 . 2 \ \mathrm { m m } )$ ，最大值为 $3 9 7 \mathrm { m / s }$ 。电弧内部等离子体可以达到非常高的速度，高速的等离子体决定了电弧具有高压力，在高温熔化金属母材后可以实现穿孔效应，完成中厚板一次焊接成形。

![](images/d5afbef55fe2708cb491fb79a8d1d524093a489dc8af8166edcae0312bd4ec79.jpg)  
图7变极性等离子电弧轴线上等离子体流速分布

电弧实际上为高温导电体，温要通Ohm 定律产生，因此电流密度的分布决定了电弧温度场的分布。图8为EN和EP 时工件表面径向电流密度分布。可以看出，在等离子焊枪的拘束作用下，电流密XA度主要集中于半径 $2 \mathrm { m m }$ 的区商丙，决定了电弧温度场的高拘束状态。E电弧中心区域电流密度约为 $5 \mathrm { A } / \mathrm { m m } ^ { 2 }$ ，大于EP 时的 $4 . 3 \mathrm { A / m m } ^ { 2 }$ ，随着距电弧中心轴线距离增加电流密度减小，在径向近似成Gauss茶分布，降低速度快，变化梯度大。从图8中还可以看出，在距离电弧中心约Ⅰmm处2种状态电流密度曲线重合，随后在距离电弧中心 $1 { \sim } 4 ~ \mathrm { m m }$ 处，EP 时的电流密 于EN由于变极性等离子电弧电流密度的这种特性，必定会导致不同极性时电弧形态的差异。 从

风参

![](images/4a8b9fb9111aa74ae66bb03ef29045ea35af6c07816a13af95cadcb9531cb330.jpg)  
Fig.7 Plasma velocity distMbutions of VPPA at the axis   
图8不同极性时工件表面径向电流密度分布

Fig.8 Radial current density distributions of different polarity at work-piece surface

# 3.2 实验验证

为了验证变极性等离子电弧在工件上的分时导电过程的分析模型，对铝合金板材进行了定点穿孔实验。图9所示为变极性等离子电弧定点焊接铝合金工件上表面形貌。可以看出，可将其分为中心区和环状氧化膜清理区。在穿透焊接工件达到稳态后，电弧在EN时，电弧导电主要通过中心区，而 EP时，阴极斑点在周围的氧化膜区域形成，电流密度主要集中于阴极斑点处，因此正极性时电弧导电主要通过图中的氧化膜清理区。

![](images/a71e103122e21546c99a7a1a3e4bccfd95b46b8d7b3feaa283716f26eab157f5.jpg)  
图9铝合金表面焊后形貌

Fig.9 Surface morphology of aluminum

图10 为变极性等离子电弧EN 和EP 时的电弧图像。 以看出，EP 时电弧形态大于EN时，并且在EP 时工件表面处的电弧边缘可以明显观察到阴极斑点，从而进一步说明本工作中工件表面边界条件设置的合理性。与图4计算得到的电弧温度场对比可知，EN和EP时的电弧形态以及2种状态下电弧形貌差异基本吻合。

![](images/2daa0facf2664d99cc0f51920fd87c6f8b5fb4ae48710d51a8e0542f40257ced.jpg)

# 图10不同极性时变极性等离子电弧图像

# Fig.10 Images of VPPA atEN(a) and EP (b)

另外，通过对比变极性等离子电弧图像和电弧中心电弧压力的实验测量结果与计算结果，对数值模型进行了验证。图11对比了电弧压力的计算结果与实验测量结果，在测量电弧压力时同步采集了焊接电流，电流为正时处于EN 状态，电流为负时处于EP 状态。另外，在测量电弧压力时，外界干扰信号(如焊机电信号干扰、外界气流扰动)对测量电弧压力输出的电压信号有一定的影响，本工作将电弧压力波形进行了滤波，主要分析其随焊接电流变化的变化情况，以及其不同阶段与计算所得的电弧压力的吻合程度。

变极性等离子电弧焊接电流需要周期性过零，即某时刻焊接电流为0，电弧必将熄灭，因此要使变极性电弧持续引燃，焊机过零响应时间必须足够快，本工作所用焊机从EN到 EP 的转变时间为 $0 . 1 ~ \mathrm { { \ m s } }$ 。对此转变过程，电弧力有明显的体现。以电弧从EN转EP为例，电流从 $1 0 0 \mathrm { A }$ 迅速减小至0，电弧压力从平均值约 $1 . 5 \mathrm { { \ k P a } }$ 降低到较小的值，计算结果约为 $0 . 3 \ \mathrm { k P a }$ ；随后焊接电流从0迅速降低到-100A，同时电汉弧压力迅速增加，此时电弧压力会升高到一个较大的值，计算结果约为 $1 . 2 \mathrm { k P a }$ ，然后降低到EP 时的电弧压力，从EN转向 EP时也有相同化过另外，从电弧压力测量结果可以看出，随焊接电流的变化，电弧压力有相同的演变趋势，并且EN 和EP 时电弧压力的计算结果与实验结果吻合良好。

![](images/f1e9100686e9c922698b53c90bdcd85076435fb35eb39caa06c5837c60896ddb.jpg)  
图11电弧中心处电弧压力随时间的演变  
Fig.11 Evolution of arc pressure at the center of VPPA

4结论

(1）变极性等离子弧最高温出现在喷嘴内部，EN 时最高温范围大于EP 时的范围，而喷嘴外部 EP 时的高温范围大于EN 时的范围，工件表面电弧压力和电流密度分布趋势相同，但随着径向距离的增加2种状态时的电弧压力和电流密度的大小会出现反转。

(2）电弧压力对变极性等离子电弧转换极性过程响应迅速，电流在过零时电弧压力出现极小值，随着电流的增加，电弧压力瞬间冲击到一个较大的值，随后快速降低到稳定值。相同电流条件下EP 时的电弧压力小于EN时。电弧压力和电弧图像的实验结果与计算结果吻合良好。

参考文献   
[1] Jenney CL,O'Brien A. Welding Handbook [M].2nd Ed., Miami: American Welding Society,2001: 309 [2] Nunes A CJr, Bayless E O Jr, Jones C S II et al. Variable polarity plasma arc welding on the space shuttle external tank [J]. Weld. J.,1984, 63: 27   
[3] Chen Q, Sun Z G, Sun JW, et al. Closed-loop contro weld penetration in keyhole plasma arc welding [J]. Trans. Nonferrous Met. Soc. China, 2004,14: 116   
W   
[4] Dong C L, Zhu YF, Zhang H,et al. Study onfront Sde arc light sensing in keyhole mode plasma arc welding [J]. China Mech. Eng.,2001,37(3): 海   
(董春林，朱轶峰，张 慧等．穿孔等离子弧焊正面弧光传感技术研究 [J]．机械工程学报,2001,37(3):30) [5] Satoru S. Sensing technbl gy for the welding process [J].Weld. Int., 2006,20: 18 敬   
[6] Thornton MF. Spectroscopic determination of temperature distribution for a TG arc [J]. J. Phys. Appl.Phys., 方   
1993,26D: 1432   
[7] Haidar J, Farmer A JD. Temperature measurements for hig ning arcs in nitrogen [J]. J. Phys. Appl.Phys., 1993,26D:1224   
[8] Zhang Y M, Zhang S B, Liu Y C.A plasma cloud ch arge sensor for pulse keyhole process control[J]. Meas. Sci. Technol.,2001,12: 1365   
[9]Fanara C. Sweeping electrostatic probes in atmospheric pressure arc plasmas-Part II: Temperature   
determination [J].IEEE Trans.Plasma Sci.,2005,33:1082   
[10] Chen SJ,Jiang F,Lu Z Y,etal. Measurement and analysis of the welding arc current density and pressure distribution based on split anode method [A]. Proceedings of International Conference on Mechatronics and Automation [C]. Beijing, China: IEEE,2011: 1544   
[11] Schwedersky MB, Goncalves e Silva R H, Dutra JC, et al. Two-dimensional arc stagnation pressure measurements for the double-electrode GTAW process [J]. Sci. Technol. Weld. Join., 2016,21: 275   
[12] Han YQ,Lü YH, Chen S J,et al. Influence of variable polarity plasma arc shape on arc force[J]. Tran. China Weld. Inst., 2005,26: 49

(韩永全，吕耀辉，陈树君等．变极性等离子电弧形态对电弧力的影响 [J]．焊接学报,2005,26(5):49) [13]Saad E, Wang HJ, Kovacevic R. Clasification of molten pool modes in variable polarity plasma arc welding based on acoustic signature [J]. J. Mater. Process. Technol., 20o6, 174: 127

[14] Wang YW,Zhao P S.Noncontact acoustic analysis monitoring of plasma arc welding [J]. Int. J. Pressure Vessels Piping, 2001, 78: 43

[15] Yuan X Q,Li H,Zhao T Z,et al. Study of the characteristic of D.C.arc plasma torch[J]. Acta. Phys.Sin., 2004, 53: 3806

(袁行球，李辉，赵太泽等．直流电弧等离子体炬的特性研究[J]．物理学报,2004,53:3806) [16] Tian JG, Deng J,LiYJ,et al. Numerical simulation fora free-burning argon arc with MHD model[J].Chin.

J. Theor.Appl. Mech.,2011, 43:32

(田君国，邓 晶，李要建等．自由燃烧电弧的磁流体动力学数值模拟[J]．力学学报,2011,43:32) 洛你   
[17] Shi Y, Guo CB, Huang JK, et al. Numerical simulation of pulsed current tungesten inert gas (TIG) welding   
arc [J]. Acta. Phys. Sin.,2011,60: 04 海

(石 玕，郭朝博，黄健康，等．脉冲电流作用下TIG电弧的数值分析[J]．物理学报,2011,60:048102) [18] Hsu KC,Etemadi K, dder E.Study of the free-burning high-intensity argonarc [J]. J. Appl. Phys.,1983, 54: 1293

送方

[19] Hsu K C,Pfender E.Two-temperature modeling of the free-burning,high-intensity arc[J]. J.Appl. Phys., 1983, 54: 4359 高收

[20] Kovitya P,LowkeJJ.Two-dimensionalanalysis offree burning arcs inargon[J]J.Phys. Appl. Phys.,2000,

18D: 53 医参

[21] McKelliget J, Szekely J.Heat transfer and fluid flow in the welding arc[J]. MetallTrans.,1986,17A: 1139 [22] Wu C S, Ushio M,Tanaka M. Analysis of the TIG welding arc behavior[J] Comput. Mater.Sci.,1997,7: 308 [23] Kim Y J,Lee JC.Numerical analysis of free-burning argon arcs based on the local thermodynamic equilibrium model at various electrical currents [J]. Thin Solid Films,2O13, 547: 28

[24] Lago F, Gonzalez JJ,Freton P,etal. A numerical modelling of an electric arc and its interaction with the anode: part I. Application to the interactionofalightning strike and an aircraft in flight[J]. J.Phys.Appl.Phys., 2006,39D:2294

[25] Blais A,Proulx P,Boulos MI. Three-dimensional numerical modelling of a magnetically deflected dc transferred arc in argon [J]. J. Phys. Appl. Phys., 2003, 36D: 488

[26] Xu G,Hu J,Tsai HL.Thre-dimensional modeling of the plasmaarc inarc welding[J]. J.Appl. Phys.,2008,

104:103301

[27]Tanaka M,Terasaki H, Ushio M,et al. Aunified numerical modeling of stationary tungsten-inert-gas welding process [J].Metall. Mater. Trans.,2002,33A: 2043

[28] Tanaka M, Terasaki H, Ushio M,et al. Numerical study of a free-burning argon arc with anode melting[J]. Plasma Chem. Plasma Process.,2003, 23: 585

[29]Tanaka M, Ushio M,Lowke JJ. Numerical study of gas tungsten arc plasma with anode melting[J]. Vacuum, 2004, 73: 381

[30] Wang X X,Fan D,Huang JK, et al. Aunified model ofcoupled arc plasma and weld pool for double electrodes TIG welding [J]. J. Phys. Appl. Phys., 2014, 47D: 275202

[31] Wang X X,Fan D, Huang JK, et al. Numerical simation ofcoupled arc in double electrode tungsten inert gas welding [J]. Acta. Phys. Sin., 2013, 62: 228101

(王新鑫，樊丁，黄健康等．双钨极耦合电弧数值模拟[J].物理学报,2013,62:228101) [32] Wang X X, Fan D, Huang J K, Numerigal simulation of heat transfer and fluid flow in double electrodes 17 TIG arc-weld pool [J]. Acta. Matall. Sin.,2015, 51: 178 >

(王新鑫，樊丁，黄健康等 钨极NG电弧-熔池传热与流动数值模拟[J]. 学报,2015,51:178) [33]Fan D,Huang Z C,Huang JK,et al.Three-dimensional numerical anysis ofinteraction between arc and X pool by considering the behavior of the metal vapor in tungsten inert gas welding [J]. Acta. Phys. Sin.,2015,64:

厨收

(樊 丁，黄自成，黄健康等．考虑金属蒸汽的钨极惰性气体保护焊电弧与熔池交互作用三维数值分析 [J].物理学报,2015,64:108102) 金物

[34]Lowke JJ,Tanaka M.‘LTE-difusionapproximation’for arccalculations [J].J.Phys.Appl.Phys.,2006,39D: 3634

[35]Tashiro S,Miyata M,Tanaka M.Numerical analysis ofAC tungsten inert gas welding of aluminum plate in consideration of oxide layer cleaning [J]. Thin Solid Films,2011, 519: 7025   
[36] McKellige J,SzekelyJ, Vardelle M,et al.Temperature and velocity fields in a gas stream exitinga plasma torch.Amathematical model and its experimental verification [J]. Plasma Chem. Plasma Process,1982,2: 317 [37] WesthoffR,SzekelyJ.Amodel offluid,heat flow,and electromagnetic phenomena in a nontransferredarc plasma torch [J]. J.Appl. Phys.,1991,70: 3455   
[38] Bauchire JM, Gonzalez JJ, Gleizes A. Modeling of a DC plasma torch in laminar and turbulent flow [J]. Plasma Chem. Plasma Proc.,1997,17: 409

[39] YinFL, Hu S S, Yu CL,etal. Computational simulation for the constricted flow of argon plasma arc [J]. Comput. Mater. Sci., 2007, 40: 389

[40] Zhou QH, Li H, Xu X, et al. Comparative study of turbulence models on highly constricted plasma cutting arc [J]. J. Phys. Appl. Phys., 2009, 42D: 015210

[41] Zhou QH,LiH,LiuF, et al.Effects ofnozzle length and process parameters on highlyconstricted oxygen plasma cutting arc [J]. Plasma Chem. Plasma Process., 20o8, 28: 729

[42] Zhou QH,Yin HT,LiH,etal.The effect of plasma-gas swirl flow ona highlyconstricted plasma cuting arc [J. J. Phys. Appl. Phys., 2009, 42D: 095208

[43] Zhou QH, Guo WK,Li H. Numerical simulation on the effect of shielding gas on the plasma cuting arc [J]. Acta. Phys. Sin., 2011, 60: 025214 茶

(周前红，郭文康，李 辉．保护气对切割弧特性影响的模拟研究 [J]．物理学报,2011,60:025214) 沙发   
[44] Jia X X, Wu C S.Numerical analysis ofthe coupled arc-weld pool-keyhole behaviors in stationary plasma   
arc welding[J] Int.J.Heat Mass Tra 839   
[45] Jian X X, Wu C S, Zhang G K,et al. Aunified 3D model for an interaction mechanism of the plasma arc,   
weld pool and keyhole in pla ma arc Welding[J]. J. Phys. Appl. Phys., 2015, 48D: 465504

炭方 管 拆 医参