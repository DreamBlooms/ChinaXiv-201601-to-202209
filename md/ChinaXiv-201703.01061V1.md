# Fe-C-Mn三元合金中奥氏体-铁素体相变的相场 模拟

# 张军1,2 陈文雄2 郑成武2 李殿中2

1中国科学技术大学化学与材料科学学院合肥230026  
2 中国科学院金属研究所沈阳材料科学国家(联合)实验室沈阳110016

摘要采用相场法研究了Fe-C-Mn 三元合金在临界区等温过程中发生的奥氏体-铁素体相变。基于Gibbs 自由能守恒理论，在相场模型中考虑了替换型元素Mn在奥氏体/铁素体相界面内扩散所导致的自由能耗散，描述了Fe-C-Mn三元合金中因 Mn在相界面偏聚所导致的相变停滞和相变不完全现象。利用相场模型研究了不同Mn 含量对奥氏体-铁素体相变微观组织转变和相变动力学的影响，结果显示：随着Mn 含量的增加，铁素体相的转变速率和体积分数降低，Mn在奥氏体/铁素体相界面内扩散所导致的溶质拖曳现象越明显，相变不完全程度加剧。

关键词 相场法，奥氏体，铁素体，Gibss自由能耗散，相变不完全

中图分类号 TG113.1文章编号 0412-1961(2017)00-0000-00

# Phase-Field Modeling of $\pmb { \gamma } \mathrm { \longrightarrow } \mathbf { a }$ Transformation in Fe-C-Mn Ternary

# Alloys

ZHANG Jun 1,², CHEN Wenxiong², ZHENG Chengwu², LI Dianzhong   
1 School of Chemistry and Materials Science, University of Science and Technology of China, Hefei 230026, China   
2 Shenyang National Laboratory for Materials Science, Institute of Metal Research, Chinese Academy of Sciences, Shenyang 1l0016,China   
Correspondent: ZHENG Chengwu, associate professor, Tel: (O24)83970106,E-mail:   
cwzheng@imr.ac.cn   
Supported by National Natural Science Foundation of China (Nos.51371169 and 51401214)

Manuscript received 2016-10-21,in revised form 2017-00-00

ABSTRACT The effect of Mn on the austenite-to-ferrite transformation has been widely studied by both physical models and experiments due to its technological importance for alloy design in steel industries.In recent years,an increasing interest of this issue is moved onto the effect of alloying element on the migrating interface during the austenite-to-ferrite transformation. For ternary Fe-C-Mn alloys,the interfacial condition is more complicated than that of binary Fe-C allys in view of the large difference in the diffusivity between the interstitial and substitutional alloying elements. Generally speaking， there are two main concepts,i.e. the paraequilibrium model and the local-equilibrium model，which have been proposed to describe the phase transformation kinetics in ternary Fe-C-Mn alloys based on different assumptions about the diffusion of the substitutional elements. And many modeling attempts have been made to study the effect of Mn on the migration kinetics by using these theories.In this work,a multi-phase-field (MPF) model coupling with a Gibbs-energy dissipation model was developed to simulate the isothermal austenite-to-ferrite transformation in ternary Fe-C-Mn alloys. This model has considered the Mn diffusion inside the migrating interface in a physical manner and takes its effect on the transformation kinetics into account. Comparison simulations were made to analyze the difference in the transformation kinetics and ferrite morphologies with and without considering the energy dissipation at the moving interface.It shows that the incomplete transformation phenomenon does occur due to the Mn difusion inside interface.The modified MPF model was then used to study the effect of Mn contents on the microstructures and kinetics of the phase transformations.It is found that the ferite growth along the austenite/austenite boundaries is faster than that in the perpendicular direction. This difference is intensified with increasing the Mn concentration, which hence leads to the ferrite morphology changed from eliptical to flat alike. It also produces a slower transformation kinetics and a larger degree of the incomplete transformation when increasing the Mn concentration.

KEY WORDS phase-field method，austenite， ferite，Gibbs-energy dissipation， incompletetransformation

Fe-C 合金中添加合金元素，如Mn、Ni、Cr等，有助于改善材料力学性能，对满足钢铁材料日益迫切的发展需求具有重要意义。奥氏体-铁素体相变是控制钢中相成分、晶粒尺寸及组织形貌等的重要转变之一。然而，在此相变过程中，由于合金元素的扩散速率远小于C 元素，关于合金元素分配与否的问题，目前学术界仍存在争议[1-4]。近十年来，许多数学或物理模型描述了其相变动力学和元素分配行为。最早，Christian2提出的界面控制生长理论认为，相变驱动力完全用于界面迁移过程，由此，界面迁移速率的大小正比于相变驱动力和界面迁移率。而 Zener4则认为相界面迁移所需要消耗的自由能可以忽略不计，相变过程完全由元素的扩散所控制。当然，Zener提出的扩散控制生长概念在二元合金的研究上得到了很好的证明。但是，对于三元Fe-C-X $X = \mathbf { M } \mathbf { n }$ 、Ni、Cr..)合金，相界面处合金元素的分配问题更为复杂，对相界面迁移驱动力和界面迁移率的影响也不明晰。所以，为了更好地描述相变过程中界面处合金元素的分配行为，基于合金元素扩散慢的因素，学术界提出了2个界面平衡概念：准平衡(paraequilibrium,PE)[5,6]和局部平衡(local equilibrium,LE)[7,8]。准平衡认为新相和母相具有相同的合金元素含量，界面处仅C元素处于平衡状态。而局部平衡则要求界面处的所有元素均处于平衡状态；另外，从热力学角度分析不同饱和度合金的元素平衡条件，又可以细分为合金元素再分配(partitioning local equilibrium,PLE)和非再分配局部平衡(negligible partitioning local equilibrium,NPLE)[7.8]。PLE 规定合金元素可在整个体系内进行扩散；而NPLE 要求合金元素仅在界面处扩散，但来不及进行体扩散。除此之外，混合控制生长理论(Mixed-mode)则认为界面迁移和元素扩散共同对相变动力学起到作用，相变过程中相界面的迁移和元素的扩散都会消耗自由能。可见，相变以何种模式进行依赖于与温度相关的界面迁移率和元素扩散率。目前Fe-C合金的混合控制相变模式已进行了大量研究并得到了验证[9,10]，但是，在 Fe-C-X 合金中由于移动相界面处存在 $X$ 元素分配的行为，应用混合控制生长理论研究奥氏体-铁素体的相变过程，需要额外考虑 $X$ 元素的影响。

Gamsjager[11]采用调整有效界面迁移率的方法来考虑 $X$ 元素分配的影响，研究了Fe-C-X合金连续冷却过程中奥氏体-铁素体的混合控制相变过程，但其中有效界面迁移率与相变温度和冷却速率的关系很难确定。目前有2 种理论：溶质拖电[12]和自由能耗散理论[13]，从热力学角度解释了 $X$ 元素分配对相变动力学的影响。Hillert等[14,15]认为2种假设是等价的，即溶质原子在界面处的偏聚对移动界面产生的拖电力等同于界面处溶质分配所耗散的自由能。基于上述假设，学者们建立了一些数学物理模型[16-18]来研究 $X$ 元素对相变过程的影响，并通过合理假设描述了奥氏体-铁素体相变过程。然而，这些模型与相场法的结合却鲜有报道。相场法在介观尺度方面的研究又具有一些独特的优势，例如，Loginova等[通过耦合溶质拖电力模型，采用相场法研究了Fe-C合金中奥氏体-铁素体块状转变过程。Zhu等[20运用相场法并结合自由能耗散模型，模拟了Fe-C-Mn合金中奥氏体-铁素体的循环相变过程。

相场法通过计算系列场变量描述多晶组织的微观结构和成分的演化。目前开发的相场模型已能成功地研究复杂微观几何结构和界面各向异性特征[21-23]对相变动力学和组织形貌的影响。同时，也能综合考虑有限C 扩散与有限界面迁移率对相变动力学的影响[24-26]，并成功地应用于奥氏体-铁素体混合控制相变过程的研究。而且，相场法能自动追踪界面位置的变化，也能更容易在界面处耦合溶质再分配的自由能耗散模型，分析界面处合金元素带来的影响。本工作采用多相场相变模型模拟Fe-C-Mn三元合金在临界区等温过程中发生的奥氏体-铁素体相变。通过2种相变模式，即考虑Mn分配和不考虑Mn分配，模拟单个铁素体晶粒的生长过程，分析 Mn 元素对相变动力学和转变体积分数的影响。进一步讨论合金中Mn含量对微观组织、C浓度以及相变动力学的影响。最后，针对铁素体相变不完全转变情况，分析不同Mn含量对铁素体相转变过程的影响机制。

# 1模型

# 1.1自由能耗散模型

在奥氏体-铁素体相变过程中，相较于C元素的扩散速率，合金元素Mn的扩散迁移速率非常缓慢。Mn元素在奥氏体相和铁素体相内的扩散速率也相差2\~3量级，故两相之间存在Mn的化学势阱，容易导致Mn元素在相界面处分配，对相界面的迁移起到拖电作用，造成部分化学自由能被耗散。

因此，Fe-C-Mn三元合金中相界面迁移驱动力的计算，需要考虑引入Mn元素分配的影响。

根据 Gibbs 自由能守恒理论[18]，相变的化学驱动力须与相变过程中所消耗的能量相等。奥氏体-铁素体相变所消耗的化学自由能 $\Delta G ^ { c h e m }$ 分为相界面迁移消耗的自由能 $\Delta G ^ { f r i c t i o n }$ 和耗散自由能 $\Delta G ^ { d i s } 2$ 部分：

$$
\Delta G ^ { f r i c t i o n } = \Delta G ^ { c h e m } - \Delta G ^ { d i s }
$$

上式表明相界面迁移过程中共有 $\Delta G ^ { d i s }$ 的化学自由能不能作为相界面迁移的驱动力。

Purdy 等[12]假设 $\mathbf { M } \mathbf { n }$ 在奥氏体-铁素体相界面处存在楔形的作用势，如图1所示。界面处 Mn元素在相界面的分配引起的 $\Delta G ^ { d i s }$ 可表述为：

$$
\Delta G ^ { d i s } = \int _ { - \zeta } ^ { \zeta } \Big ( x _ { M n } ^ { 0 } - x _ { M n } ( y ) \Big ) \frac { d E \big ( y \big ) } { d y } d y
$$

![](images/417ade3faabe9d019ec967099deb11024eb512a58987992f10a7d737709cdf47.jpg)  
图1相界面处Mn化学势的分布示意图

Fig.1 Schematic of the chemical potential of Mn inside the austenite/ferrite interface ( $2 \zeta$ is the physical interface thickness, $E _ { 0 }$ is the Mn-interface binding energy, $\mu _ { M n } ^ { \gamma }$ and $\mu _ { M n } ^ { \alpha }$ are the chemical potential of Mn in austenite and ferrite, respectively)

式中， $y$ 为坐标位置， $x _ { _ { M n } } ^ { 0 }$ 为合金中 $\mathbf { M } \mathbf { n }$ 的名义成分， $x _ { M n } \left( y \right)$ 为界面上某处的 Mn 元素浓度，$E ( y )$ 为界面处Mn原子的交互作用势。图1中 $\mu _ { { \scriptscriptstyle M n } } ^ { \gamma }$ 与 $\mu _ { M n } ^ { \alpha }$ 分别为 $\mathbf { M } \mathbf { n }$ 元素在奥氏体相和铁素体相的化学势； $2 \Delta E$ 为奥氏体相与铁素体相之间Mn的化学势之差 $2 \Delta E = \mu _ { { M n } } ^ { \gamma } - \mu _ { { M n } } ^ { \alpha }$ ，可通过热力学计算获得； $\phantom { + } E _ { 0 }$ 为 $\mathbf { M } \mathbf { n }$ 元素的界面结合能； $2 \zeta$ 为 $\mathbf { M } \mathbf { n }$ 元素在界面处的扩散宽度 $( 1 \mathrm { n m } )$ 。此模型忽略了 $\mathbf { M } \mathbf { n }$ 原子的长程扩散行为，仅考虑Mn元素在相界面处的再分配行为。当相界面以速率 $V$ 移动时，界面处Mn元素的分布形式如下[12.20]：

$$
D _ { \mathrm { i n t } } ^ { M n } \frac { \partial x _ { M n } ( y ) } { \partial y } + \frac { D _ { \mathrm { i n t } } ^ { M n } x _ { M n } ( y ) } { R T } \frac { \partial E \big ( y \big ) } { \partial y } + V \Big ( x _ { M n } ( y ) - x _ { M n } ^ { 0 } \Big ) = 0
$$

式中， $R$ 为气体常数， $T$ 为相变温度， $D _ { \mathrm { i n t } } ^ { M n }$ 为奥氏体/铁素体相界面处 $\mathbf { M } \mathbf { n }$ 原子的扩散迁移系数。综合式(2)和(3)， $\Delta G ^ { d i s }$ 的解析解形式表述如下[20]：

$$
\Delta G ^ { d i s } = \frac { R T x _ { M n } ^ { 0 } } { V _ { m } } \left\{ \left. - \frac { a ^ { 2 } \nu } { 1 + a } - \frac { b ^ { 2 } \nu } { 1 + b } + \frac { a ^ { 2 } \left( 1 - \exp \left( - \nu ( 1 + a ) \right) \right) } { \left( 1 + a \right) ^ { 2 } } + \frac { b ^ { 2 } \left( 1 - \exp \left( - \nu ( 1 + b ) \right) \right) } { \left( 1 + b \right) ^ { 2 } } \right\} \frac { a ^ { 2 } } { \left( 1 - \exp \left( - \nu ( 1 + a ) \right) \right) } \frac { a ^ { 2 } } { \left( 1 - a \right) ^ { 2 } } - \frac { b ^ { 2 } \nu } { \left( 1 + b \right) ^ { 2 } } + \right.
$$

$$
\begin{array} { l } { { \displaystyle \nu = \frac { V \zeta } { D _ { \mathrm { i n t } } ^ { M n } } } } \\ { { \displaystyle a = \frac { 1 } { \nu } \cdot \frac { \Delta E - E _ { 0 } } { R T } } } \end{array}
$$

$$
b = \frac { 1 } { \nu } \cdot \frac { \Delta E + E _ { 0 } } { R T }
$$

式中， $V _ { m }$ 为奥氏体的摩尔体积。图2为 $E _ { 0 } { = } 1 0  { ~ \mathrm { k J } \mathrm { \ m o l } ^ { - 1 } }$ 时 $\mathrm { F e - 0 . 1 C - 0 . 5 M n }$ （质量分数， $\%$ 合金在 $T = 1 0 2 3 \mathrm { K }$ 时 $\gamma {  } \alpha$ 相变的 $\Delta G ^ { d i s }$ 与 $V$ 的关系。可以发现：当高界面迁移速率时 $( > 1 \mu \mathrm { m } \mathrm { s } ^ { - 1 } )$ ，$\Delta G ^ { d i s }$ 较小，而在低界面迁移速率下作用明显。界面处自由能耗散会影响相变的动力学过程。

![](images/4266a0cc8bcf872928004fccdec21432235deeace859eeaf9fa00d4ffb3bdd9c.jpg)  
图 $2 \gamma {  } { \bf { \vec { a } } }$ 相变过程中耗散自由能 $( \Delta G ^ { d i s } )$ 的变化

Fig.2 Gibbs-energy dissipation $( \Delta G ^ { d i s } )$ is a function of $V \zeta / D _ { \mathrm { i n t } } ^ { \mathrm { M n } }$ during $\gamma { \longrightarrow } \alpha$ transformation with the binding energy $E _ { 0 } = 1 0 \mathrm { k J \ m o l ^ { - 1 } }$ （ $V$ -interface velocity, $\zeta$ -half thickness of the physical interface, $D _ { \mathrm { i n t } } ^ { \mathrm { M n } }$ —trans-interface diffusivity of Mn)

# 1.2相场变量与相场方程

本工作采用多相场模型模拟Fe-C-Mn三元合金的奥氏体-铁素体的相变过程，模型中选取非保守场变量 $\pmb { \eta } ( r , t )$ 和保守场变量 $\mathbf { \boldsymbol { x } } ( \boldsymbol { r } , t )$ 分别描述晶粒的取向与浓度。选择2组序参量 $\eta _ { \mathrm { l i } } ( r , t )$ 和 $\dot { \eta } _ { 2 \mathrm { i } } ( r , ~ t )$ 表示奥氏体相和铁素体相不同晶粒的取向，其中 $\eta$ 的第一个下标“1”和“2”分别表示奥氏体相和铁素体相，而第二个下标则表示不同晶粒的取向， $n$ 为取向数， $r$ 表示空间位置，t则表示演化时间。

体系内系统自由能 $F$ 为序参量 $\pmb { \eta }$ 与浓度 $\boldsymbol { x }$ 的函数[27,28].

$$
F ( \pmb { \eta } , \pmb { x } ) = F _ { s } ( \pmb { \eta } , \pmb { x } ) + F _ { c } ( \pmb { \eta } , \pmb { x } )
$$

式中， $F _ { s }$ 和 $F _ { c }$ 分别为界面自由能和化学自由能，两者均为相场变量 $\pmb { \eta }$ 和 $\boldsymbol { x }$ 的函数。

为了更直观的描述界面处Mn分配带来的自由能耗散对相变的影响，本工作采用2种相变模式对奥氏体-铁素体相变过程进行了模拟。模式I：相场模型仅考虑体系内C原子的长程扩散行为，不考虑自由能耗散；模式II：相场模型考虑体系内C原子的长程扩散行为和界面处Mn分配带来的自由能耗散。

C 浓度场变量 $x _ { c } ( r , t )$ 的演化采用Cahn-Hilliard动力学方程[27,28]来描述：

$$
\frac { \partial x _ { c } } { \partial t } = \nabla \Bigg [ \sum _ { k = 1 } ^ { 2 } w _ { k } M _ { k } \nabla ( \frac { \partial G _ { k } } { \partial x _ { c } ^ { k } } ) \Bigg ]
$$

序参量 $\eta _ { k i } ( \boldsymbol { r } , t )$ 的演化采用Allen-Cahn 动力学方程[27,28]来描述：模式I:

$$
\frac { \partial \eta _ { k i } } { \partial t } = - L \frac { \delta F ( \pmb { \eta } , \pmb { x } ) } { \partial \eta _ { k i } }
$$

模式II:

$$
\frac { \partial \eta _ { k i } } { \partial t } = - L \frac { \delta \Bigl [ F \bigl ( \pmb { \eta } , \pmb { x } \bigr ) - w _ { k } \Delta G ^ { d i s } \Bigr ] } { \partial \eta _ { k i } }
$$

式中， $L$ 和 $M _ { k }$ 分别为与界面迁移率 $M _ { p }$ 和C元素扩散迁移率 $M _ { c } ^ { \gamma }$ 和 $\boldsymbol { M } _ { \boldsymbol { c } } ^ { \alpha }$ 相关的模型参数; $w _ { k } ( \pmb { \eta } )$ 为插值函数，其物理意义为相 $k$ 在某处的体积分数； $x _ { c } ^ { k }$ 和 $G _ { k }$ 分别为 $k$ 相的C浓度和化学自由能(相 $k$ 为奥氏体相或铁素体相)，上述模型参数与物理参数的关系可参考文献[28]；界面处C浓度表示为两相混合：

$$
x _ { _ c } = w _ { _ \alpha } x _ { _ c } ^ { \alpha } + w _ { _ \gamma } x _ { _ c } ^ { \gamma }
$$

模拟中假设相变过程中相界面处相之间的C化学势平衡，C原子可在两相间快速交换：

$$
\frac { \partial G _ { \alpha } \left( x _ { c } ^ { \alpha } \right) } { \partial x _ { c } ^ { \alpha } } = \frac { \partial G _ { \gamma } \left( x _ { c } ^ { \gamma } \right) } { \partial x _ { c } ^ { \gamma } }
$$

采用规整溶体双亚点阵模型[24,29.30计算 Fe-C-Mn 三元体系中奥氏体相与铁素体相的化学自由能，两相之间的化学自由能差 $\Delta G ^ { c h e m }$ 提供奥氏体-铁素体相变的驱动力。

# 2 模拟条件

本工作针对Fe-C-Mn三元合金在临界区等温过程中发生的奥氏体-铁素体相变进行模拟。文中各元素所使用的浓度单位都为质量分数 $( \% )$ 。初始组织中奥氏体内的C和 $\mathbf { M } \mathbf { n }$ 均匀分布，而铁素体晶核的初始C浓度设为 $0 . 0 1 \%$ 。采用有限差分和逐步迭代方法对动力学方程进行求解。为提高数值计算的稳定性及精确性，在离散相场变量 $\eta$ 和 $x _ { c }$ 时，考虑了第一和二近邻的影响。 $V$ 的计算通过对序参量 $\eta$ 在时间 $( \Delta t )$ 和空间 $( \Delta y )$ 上进行一阶离散来求解：

$$
V = \frac { \hat { \partial } y } { \hat { \partial } t } = \frac { \hat { \partial } \eta } { \hat { \partial } t } / \frac { \hat { \partial } \eta } { \hat { \partial } y }
$$

$$
\begin{array} { r l r } {  { \frac { \hat { \mathcal { O } } \eta } { \hat { \mathcal { O } } y } = 0 . 2 5 \times ( \eta _ { i , j + 1 } ^ { t } + \eta _ { i , j - 1 } ^ { t } + \eta _ { i + 1 , j } ^ { t } + \eta _ { i - 1 , j } ^ { t } - 4 \eta _ { i , j } ^ { t } ) / ( 2 \Delta y ) } } \\ & { } & { + 0 . 5 \times 0 . 2 5 \times ( \eta _ { i + 1 , j + 1 } ^ { t } + \eta _ { i + 1 , j - 1 } ^ { t } + \eta _ { i - 1 , j + 1 } ^ { t } + \eta _ { i - 1 , j - 1 } ^ { t } - 4 \eta _ { i , j } ^ { t } ) / ( 2 \Delta y ) } \end{array}
$$

$$
\frac { { \hat { O } } \eta } { { \hat { O } } t } = \left( { \eta ^ { t } - \eta ^ { t + \Delta t } } \right) / \Delta t
$$

其中， $\Delta y$ 为网格单元尺寸， $\Delta t$ 为时间步长。为满足计算精度要求，对模拟区域进行离散时，需预设的相场界面宽度 $\delta$ 与 $\Delta y$ 的关系[27]： $\delta = n \Delta y$ 。当 $4 { \leqslant } n { \leqslant } 6$ 时，计算误差可控制在 $5 . 0 \%$

以内，本模拟设定 $\Delta y = 0 . 4 \mu \mathrm { m }$ ， $n = 6$ 。模拟所采用的物理参数如表1所示。

表1模拟所采用的物理参数  
Table1 Physical parameters used in the simulations   

<html><body><table><tr><td>Parameter (unit)</td><td>Value</td><td>Ref.</td></tr><tr><td>σα, (J·m²)</td><td>0.4</td><td>[20,31]</td></tr><tr><td>x,x (J · m²)</td><td>0.79</td><td>[31]</td></tr><tr><td>Dim (cm²· s-1)</td><td>0.5exp(-247650 /(RT))</td><td>[20]</td></tr><tr><td>M (m²·mol·J¹ ·s1)</td><td>1.5×10' exp(-142000/(RT)) RT</td><td>[32]</td></tr><tr><td>M(m²·mol ·J1 ·s1)</td><td>12.2×10 xp(-125000/(RT)) RT</td><td>[32]</td></tr><tr><td>M,(m·mol·J1 ·s-1)</td><td>0.5exp(-140000/(RT))</td><td>[32]</td></tr></table></body></html>

Note: R—ideal gas constant, T—annealing temperature,Oα.—i -interfacial energy between $ { \alpha }$ and 2， $\sigma _ { \gamma , \gamma }$ —interfacial energy between y and $\gamma$ ， $D _ { \mathrm { i n t } } ^ { M n }$ ——trans-interface diffusivity of $\mathbf { M } \mathbf { n }$ ， $M _ { \it { c } } ^ { \prime }$ —atom mobility of C in austenite, $\boldsymbol { M } _ { \boldsymbol { c } } ^ { \alpha }$ —atom mobility of C in ferrite, $M _ { \mathrm { { \it ~ p } } } { \it - } \alpha / \gamma$ interface mobility

# 3模拟结果及分析

# 3.12种相变模式下的相变行为

模拟所用材料选为Fe-0.1C-1.0Mn合金。图3为 $9 7 3 \mathrm { K }$ 等温时单个铁素体晶粒在2个奥氏体晶粒间生长的模拟结果。从图中可以发现，铁素体晶粒沿原奥氏体晶界比垂直于原奥氏体晶界方向生长较快，呈椭圆状。比较图3a和b的模拟结果发现，图3a的结果中铁素体晶粒生长较慢，并且，铁素体晶粒沿奥氏体晶界与垂直于奥氏体晶界方向之间的生长速率差距较大。图4为铁素体相的转变动力学。在 $9 7 3 \mathrm { ~ K ~ }$ 下模拟结果与文献[18]报道结果比较可以发现，模式I模拟的相变体积分数与文献报道的PE 模型的结果接近，而模式ⅡI模拟的体积分数与LE模型的结果接近。另外，比较模式I和ⅡI的铁素体转变动力学发现，两者在相转变速率和体积分数上表现出明显差异：后者的相转变速率明显慢于后者，而且，后者的铁素体相体积分数相对较小。两者不同之处仅在于是否引入 $\Delta G ^ { d i s }$ 的影响，即是否考虑Mn分配对界面处相变驱动力的影响。

![](images/ae0b90acf541a0ed8cf7907af4c0eb5154f194161c9be78acffc768a28717eff.jpg)

Fig.3 Single ferrite $ { \alpha }$ growths between austenite grains $\gamma _ { 1 }$ and $\gamma _ { 2 }$ at $9 7 3 \mathrm { ~ K ~ }$ with $\Delta G ^ { d i s }$ (al\~a3) and without $\Delta G ^ { d i s }$ (b1\~b3) at time $t = 2 0$ s (a1, b1), $t = 4 0 \ \mathrm { s }$ (a2, b2) and $t = 6 0$ s (a3,b3)

![](images/f45696e17f8c4cd5feaa11fd0f2651f9409999d31212fa9ca8f69d6caecc6929.jpg)  
图 $3 9 7 3 \mathrm { K }$ 等温时单个铁素体晶粒的生长过程

Fig.4Kineticsof ferrite $ { \alpha }$ growth under different conditions at $9 7 3 \mathrm { K }$ ,comparing with the LE and PE predictions[18]

图5为相界面处消耗的化学自由能 $\Delta G ^ { c h e m }$ 与耗散自由能 $\Delta G ^ { d i s }$ 随时间的演化情况。图5中的耗散自由能 $\Delta G ^ { d i s }$ 为图3a中铁素体沿箭头指示方向生长时相界面处的耗散自由能，即采用此生长方向的相界面迁移速率计算出的耗散自由能。可以看出，随着相变的进行， $\Delta G ^ { c h e m }$ 逐渐降低，此时相界面迁移速率相对较快， $\Delta G ^ { d i s }$ 的作用并不明显。但随着界面迁移速率的降低，$\Delta G ^ { d i s }$ 的作用越来越明显。当 $\Delta G ^ { c h e m } \leqslant \Delta G ^ { d i s }$ ，即 $\Delta G ^ { f r i c t i o n } \leqslant \mathrm { ~ 0 ~ }$ 时， $\alpha / \gamma$ 相界面会停止迁移，意味着相变过程发生停滞。但此时的 $\Delta G ^ { c h e m }$ 仍大于零，说明并未达到热力学平衡状态，此时的相变停滞是因Mn元素在相界面分配所引起的，这种暂时的相变停滞会导致相变的不完全[18,20,33]

![](images/3e44f59b94a56315f325e09dd4a3403cbf125e1b36aadbaf86b1d255845c5bfb.jpg)  
图4973K等温时铁素体晶粒的生长动力学  
图5 相界面迁移过程中 $\Delta G ^ { c h e m }$ 与 $\Delta G ^ { d i s }$ 的变化情况

Fig.5 Variations of total dissipation of the chemical free energy $( \Delta G ^ { c h e m } )$ and $\Delta G ^ { d i s }$ with time due to Mn diffusion inside the interface for austenite-to-ferrite transformation at $9 7 3 \mathrm { K }$

# 3.2不同Mn元素含量的影响

![](images/a9caeca8f9ef131e61062dd0491659867fc40ebbfb2b5974291cefcbaf5c9df5.jpg)  
图6不同合金的奥氏体-铁素体化学驱动力 $( \Delta G ^ { c h e m } )$ 与相变温度 $( T )$ 的关系 Fig.6 Chemical driving forces for the austenite-to-ferrite transformation as a function of temperature $( T )$ in the Fe-0.1C-2.0Mn,Fe-0.1C-1.0Mn and $\mathrm { F e - 0 . 1 C - 0 . 5 M n }$ (mass fraction $7 \%$ alloys ( $\mathrm { \Sigma } ^ { \mathrm { { T _ { c } } } }$ -triggering temperature of $\gamma { \xrightarrow [ ] { } } \mathbf { a }$ transformation)

图6为3种合金Fe-0.1C-mMn $\zeta _ { m } = 2 . 0$ 、1.0和0.5)的奥氏体-铁素体相变的化学驱动力$\Delta G ^ { c h e m }$ 随相变温度 $T$ 变化的情况。相变驱动力随合金中 $\mathbf { M } \mathbf { n }$ 含量的增加而降低。另外，图6表明不同合金中奥氏体-铁素体相变发生的临界温度 $T _ { \mathrm { c } }$ 随 $\mathbf { M } \mathbf { n }$ 含量的增加而降低，故选择的模拟温度必须在合金的临界温度之下，同时模拟温度不能过低，否则其相变驱动力过大，从而导致不易区分不同合金相变后的微观组织形貌。而且，在奥氏体-铁素体相变过程中，考虑铁素体形核仅发生在原始奥氏体晶界上，形核率的计算可参考文献[28]。

为研究Mn含量对奥氏体-铁素体相变过程的影响，采用模式ⅡI针对此3种合金在1043K温度进行等温奥氏体-铁素体相变模拟，其微观组织演化的模拟结果如图7所示。图中灰色区域为原奥氏体相，白色区域代表新形成的铁素体相。可以发现：(1) $0 . 5  { \mathrm { M n } }$ 成分下铁素体晶粒生长迅速，而且沿原奥氏体晶界比垂直于原奥氏体晶界方向生长快；(2) $1 . 0 \mathbf { M } \mathbf { n }$ 成分下铁素体晶粒生长速率降低，但沿原奥氏体晶界与垂直于原奥氏体晶界方向的生长速率之间差距增大；(3）2.0Mn成分下铁素体晶粒生长最慢，但沿原奥氏体晶界的生长速率远大于垂直于原奥氏体晶界方向的生长速率。相变完成时，微观组织表现出明显的差异：在0.5Mn成分下，由于铁素体晶粒之间接触较早，铁素体晶粒沿各方向的距离并不相等，最终形成为不规则状铁素体；在 $1 . 0  { \mathrm { M n } }$ 成分下，铁素体晶粒接触减少，并沿各方向充分生长，最终形成为椭圆状铁素体；在 $2 . 0  { \mathrm { M n } }$ 成分下，铁素体晶粒之间接触很少，并沿着原奥氏体晶界快速生长，最终形成为细长铁素体。观察3种成分不同时刻的铁素体晶粒组织，可以看出，相变过程中铁素体晶粒生长形貌主要受到不同方向上生长速率变化的影响。生长速率的大小主要依赖于相界面迁移驱动力的大小。图6所示 $T = 1 0 4 3 \mathrm { ~ K ~ }$ 时 $\mathrm { F e - 0 . 1 C - 2 . 0 M n }$ 合金的化学驱动力约为 $3 0 \mathrm { \ J / m o l }$ ，比Fe-0.1C-1.0Mn合金的要小约 $6 0 \mathrm { \ J / m o l }$ ， $2 . 0  { \mathrm { M n } }$ 成分下相界面迁移速率最低，铁素体晶粒生长最慢。并且，Mn元素分配对移动界面产生拖曳作用，消耗部分自由能 $\Delta G ^ { d i s }$ ，致使相界面迁移驱动力大幅降低，如此减弱了化学驱动力对铁素体晶粒生长的影响，而增强了界面能的影响，这种效应随着合金中Mn含量的增大而逐渐增强，导致沿原奥氏体晶界与垂直于原奥氏体晶界方向的生长速率之间的差距逐渐增大，铁素体晶粒形貌也会从椭圆状向扁平状转变。

![](images/abf2597f252b3f18c1449655d879691f1c51270c2d22102b9aafb02daf8099a9.jpg)  
图 $7 ~ 1 0 4 3 ~ \mathrm { K }$ 等温时不同合金相变过程中微观组织演化的模拟结果

Fig.7 Simulation of temporal evolutions of the microstructures at $1 0 4 3 \mathrm { K }$ during the austenite-to-ferrite transformation for Fe-0.1C-2.0Mn (a1\~a4),Fe-O.1C-1.0Mn (b1\~b4) and Fe-0.1C-0.5Mn (c1\~c4)

图8为3种合金相变过程中C浓度场演化的模拟结果。为了清晰辨识不同合金成分下C浓度的分布情况，图中采用了不同C浓度标尺对模拟结果进行标示。从图8中可以看出，Mn含量越高,奥氏体内形成的C浓度越低。Fe-0.1C-2.0Mn、Fe-0.1C-1.0Mn和Fe-0.1C-0.5Mn合金的C浓度 $( \% )$ 分别为0.115、0.271和0.371，皆低于THERMOCALC热力学计算的结果0.177、0.301和 $0 . 3 8 6 ( \% )$ 。另外，Mn含量的高低也将影响相变过程中奥氏体内C元素的分布均匀性。在Fe-C-Mn三元合金中两相区等温过程中形成组织的Mn和C成分的高低及分布对后续的连续冷却过程中贝氏体或马氏体相变有重要影响。

![](images/c96d1433479fc43417608e5337514ba205c41a50265c4802056fab851a80d402.jpg)

Fig.8 Simulation of temporal evolutions of the carbon concentration fields at $1 0 4 3 \mathrm { K }$ during the austenite-to-ferrite transformation for Fe-0.1C-2.0Mn (a1\~a4),Fe-0.1C-1.0Mn (b1\~b4)

图9所示为3种合金的铁素体相转变体积分数 $f _ { \alpha }$ 随时间的演化情况。可以看出，相变动力学受到合金中Mn含量的影响，Mn含量越低，相变进行越快，完成所需时间越短，如$0 . 5  { \mathrm { M n } }$ 成分下相变仅需要 $1 0 0 \mathrm { ~ s ~ }$ 就完成，而在 $2 . 0  { \mathrm { M n } }$ 成分下在 $t = 2 0 0 \mathrm { ~ s ~ }$ 时还未完成。另外，不同Mn含量下形成的铁素体体积分数不同：Mn含量越高，形成的铁素体体积分数越低，但此时 3种合金中的相变均未达到完全平衡，即 $f _ { \alpha } ^ { e q }$ 。

![](images/f73614e2c5e0907b0e689fc9f01e3f354f63c4477a497dbc5977f17736624b77.jpg)  
图 $8 ~ 1 0 4 3 ~ \mathrm { K }$ 等温时不同合金相变过程中C浓度场演化的模拟结果  
图9不同合金在 $1 0 4 3 \mathrm { K }$ 等温时的转变动力学

Fig.9 Ferrite fractions as a function of time during isothermal austenite-to-ferrite transformation at $1 0 4 3 \mathrm { K }$ for different alloys ( $f _ { \alpha } ^ { e q }$ —equilibrium volume fraction of ferrite)

定义 $\left( f _ { \alpha } ^ { e q } \mathrm { ~ - ~ } f _ { \alpha } \right) / \mathrm { ~ } f _ { \alpha } ^ { e q }$ 来描述奥氏体-铁素体相变不完全的转变程度，式中 $f _ { \alpha } ^ { e q }$ 为铁素体相的平衡体积分数，本工作利用THERMOCALC热力学软件计算得到。图10 给出了不同合金的相变转变程度。比较3种合金的相变转变程度发现，合金中Mn含量的增加将导致相变不完全的转变程度加剧。Chen 等[33]利用Fe-C-Mn三元合金进行循环相变实验，发现在相变过程中出现铁素体生长受阻或停滞现象，并认为此现象是由于Mn元素在移动相界面处发生了再分配，对界面移动起到了拖电作用，而且通过研究不同Mn含量对铁素体生长阻碍的影响程度，证实了 $\mathbf { M } \mathbf { n }$ 含量的增加将会更大程度地阻碍铁素体生长，致使相变不完全的转变程度加剧。在本工作中，模拟混合控制相变模式下的奥氏体-铁素体相变过程，忽略 Mn原子的长程扩散行为，仅考虑界面处Mn分配造成的自由能耗散。该过程中奥氏体内C 浓度的升高，导致相变驱动力逐渐降低，相界面迁移速率降低，耗散自由能 $\Delta G ^ { d i s }$ 增加，当相变驱动力 $\Delta G ^ { c h e m } { \leqslant } \Delta G ^ { d i s }$ 时，铁素体生长停滞，铁素体相转变体积分数不再增加，而此时相变驱动力 $\Delta G ^ { c h e m }$ 不为0。所以，若相变不完全的转变程度越高，相变刚结束时相变驱动力 $\Delta G ^ { c h e m }$ （204则越大，耗散自由能 $\Delta G ^ { d i s }$ 应越大。

![](images/fc69b562f825f7ec406f59664c583b87372b44ca8a6e6c699f0a8992305cb5b2.jpg)  
图10不同Mn含量下相变不完全的转变程度

Fig.1O The degree of incomplete transformation at $1 0 4 3 \mathrm { K }$ as a function of Mn concentration

合金中 Mn含量的增加，不仅导致相变驱动力 $\Delta G ^ { c h e m }$ 的降低，而且造成界面处Mn 分配过程中所耗散的自由能 $\Delta G ^ { d i s }$ 更大，两者的共同作用致使相界面迁移驱动力 $\Delta G ^ { f r i c t i o n }$ 降低，造成铁素体生长受阻碍程度增加，因此相变过程更早出现生长停滞，且相变不完全的转变程度加剧。所以，Fe-C-Mn三元合金的相变过程不仅受C原子的长程扩散行为所控制，而且也受到界面处Mn分配的影响。合金中Mn元素的添加不仅会影响奥氏体-铁素体相变过程中铁素体晶粒的生长形貌，而且会改变其相变动力学。

# 4结论

（1）本相场模型引入了自由能耗散模型，模拟了Fe-C-Mn三元合金在混合控制生长模式下的奥氏体-铁素体相变过程。通过2种相变模式对比，发现该相变过程中界面处Mn元素的分配行为会影响相转变的热力学和动力学，导致相变出现停滞现象。  
(2） 合金中的Mn含量会影响铁素体晶粒的生长形貌。Mn含量越高，铁素体晶粒沿原奥氏体晶界与垂直于原奥氏体晶界方向的生长速率之间的差距越大，晶粒形貌从椭圆状向扁平状转变。此外，随着Mn含量的升高，奥氏体相中C浓度与理论平衡碳浓度之间的差距增大。  
(3） 铁素体相的转变动力学和体积分数随合金中Mn含量的升高而降低。高Mn含量导致相变驱动力降低和Mn元素分配所耗散的自由能 $\Delta G ^ { d i s }$ 增大，使相变不完全的转变程度加剧。

# 参考文献

[1] Purdy G,Agren J，Borgenstam A，et al. ALEMI: A ten-year history of discussions of allying-element interactions with migrating interfaces [J].Metall. Mater. Trans.,2O11, 42A: 3703 [2] Christian JW.The Theory of Transformations in Metals and Alloys [M].3rd Ed.,Oxford: Elsevier Science,2002:1

[3] Hillert M. Diffusion and interface control of reactions in alloys [J]. Metall. Trans.,1975, 6A: 5 [4] Zener C. Theory of growth of spherical precipitates from solid solution [J].J. Appl. Phys.,1949,20: 950   
[5] Hultgren A. Isothermal transformation of austenite [J]. Trans. Am. Soc. Met., 1947, 39: 915 [6] Hilert M,Agren J. On the definitions of paraequilibrium and orthoequilibrium [J]. Scr.Mater., 2004, 50: 697   
[7] Coates D E. Diffusion-controlled precipitate growth in ternary-systems I[J]. Metall. Trans.,1972, 3: 1203   
[8] Hillert M. Nature of local equilibrium at the interface in the growth of ferrite from alloyed austenite [J]. Scr. Mater., 2002, 46: 447   
[9] Sietsma J, van der Zwaag S.A concise model for mixed-mode phase transformations in the solid state [J]. Acta Mater., 2004, 52: 4143   
[10] Krielaart G P, Sietsma J, van der Zwaag S. Ferrite formation in Fe-C alloys during austenite decomposition under non-equilibrium interface conditions [J]. Mater. Sci. Eng.,1997,A237: 216 [11] Gamsjager E. Kinetics of the austenite-to-ferrite phase transformation - From the intrinsic to an effective interface mobility [J]. Mater. Sci. Forum.,2007, 539-543: 2570   
[12] Purdy G R, Brechet Y JM. A solute drag treatment of the effects of alloying elements on the rate of the proeutectoid ferrite transformation in steels [J]. Acta Metall Mater.,1995, 43: 3763   
[13] Hillert M, Sundman B.A treatment of the solute drag on moving grain boundaries and phase interfaces in binary alloys [J]. Acta Metall.,1976,24: 731   
[14] Hillert M. Solute drag,solute trapping and diffusional dissipation of Gibbs energy [J]. Acta Mater., 1999,47: 4481   
[15] Hillert M, Odqvist J, Agren J. Comparison between solute drag and dissipation of Gibbs energy by diffusion [J]. Scr. Mater.,2001,45: 221   
[16] Enomoto M. Influence of solute drag on the growth of proeutectoid ferite in Fe-C-Mn alloy [J]. Acta Mater., 1999,47: 3533   
[17] Zurob H S,Panahi D, Hutchinson C R,et al. Self-consistent model for planar ferrte growth in Fe-C-X alloys [J]. Metall. Mater. Trans., 2013, 44A: 3456   
[18] Chen H, van der Zwaag S. A general mixed-mode model for the austenite-to-ferite transformation kinetics in Fe-C-M alloys [J]. Acta Mater.,2014,72: 1   
[19] Loginova I, Odqvist J, Amberg G, et al. The phase-field approach and solute drag modeling of the transition to massive $\gamma \to { \mathfrak { a } }$ transformation in binary Fe-C alloys [J]. Acta Mater.,2003, 51: 1327 [20] Zhu B Q, Chen H, Militzer M. Phase-field modeling of cyclic phase transformations in low-carbon steels [J]. Comput. Mater. Sci., 2015,108: 333   
[21] Moelans N, Blanpain B,Wollants P. Quantitative analysis of grain boundary properties in a generalized phase field model for grain growth in anisotropic systems [J]. Phys. Rev., 2OO8,78B: 1098 [22] Zaeem M A, El Kadiri H, Wang P T, et al. Investigating the effects of grain boundary energy anisotropy and second-phase particles on grain growth using a phase-field model [J]. Comput. Mater. Sci., 2011, 50: 2488   
[23] Chang K,Moelans N.Efect of grain boundary energy anisotropy on highly textured grain structures studied by phase-field simulations [J]. Acta Mater., 2O14, 64: 443   
[24] Loginova I, Agren J,Amberg G. On the formation of Widmanstatten ferrite in binary Fe-Cphase-field approach [J]. Acta Mater., 2004, 52: 4055   
[25] Mecozzi MG, Sietsma J, van der Zwaag S,et al. Analysis of the $\gamma \to { \mathfrak { a } }$ transformation in a C-Mn   
steel by phase-field modeling [J].Metall.Mater. Trans.,20O5,36A: 2327   
[26] Huang C J，Browne D J，McFadden S.A phase-field simulation of austenite to ferrite   
transformation kinetics in low carbon steels [J]. Acta Mater., 2OO6,54: 11   
[27] Moelans N. A quantitative and thermodynamically consistent phase-field interpolation function   
for multi-phase systems [J].Acta Mater.,2011,59:1077   
[28] Zhang J, Zheng C W,Li D Z. Modelling of isothermal austenite to ferrite transformation in a Fe-C   
alloy by phase-field method [J]. Acta Metall. Sin., 2016, 52:1449   
(张军，郑成武，李殿中．相场法模拟 Fe-C 合金中奥氏体-铁素体等温相变过程[J].金属学报,   
2016,52:1449)   
[29] Gustafson P.A thermodynamic evaluation of the C-Fe-W system [J]. Metall Trans.,1987,18A:   
175   
[30] Huang W.A thermodynamic assessment of the Fe-Mn-C system [J]. Metall Trans.,1990, 21A:   
2115   
[31] Savran VI. Austenite formation in C-Mn steel [D]. Delft: Delft University of Technology,2009   
[32] Zheng C W,Raabe D. Interaction between recrystallization and phase transformation during   
intercritical annealing in a cold-roled dual-phase steel: A cellular automaton model [J]. Acta Mater.,   
2013,61: 5504   
[33] Chen H,van der Zwaag S. Analysis of ferrite growth retardation induced by local Mn enrichment   
in austenite created by prior interface passages [J]. Acta Mater., 2O13,61: 1338