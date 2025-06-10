# 全钒液流电池传质及电流分布

孙 红1庄凯明²喻明富²吴玉厚²(1．沈阳建筑大学交通工程学院，沈阳1101682．沈阳建筑大学机械工程学院，沈阳110168)

摘要为了解决大规模蓄能全钒液流电池中传质不均衡而导致电池寿命缩短的问题，本文建立了一个三维数值模型研究全钒液流电池中的传质规律。模型耦合了Nernst-Planck 方程、Butler-Volmer 方程、Nernst 方程、质子交换膜中的传质方程等。模型模拟了全钒液流电池中不同价态钒离子的分布规律，以及电解质电流密度和电解质电势分布规律。研究发现：在放电过程中，沿电解液流动方向，反应物的离子浓度逐渐减少，生成物的离子浓度逐渐增加；电解质电流密度在膜表面达到最大，向两侧的集流体方向逐渐降低；沿电解液流动方向和阴极指向阳极方向，电解质电势逐渐降低。结果表明：集流体附近电化学反应更剧烈，质子在Nafion膜中的传递主要是依靠电渗作用和浓差作用

关键词全钒液流电池；钒离子；电流密度；电势中图分类号：TM911.4 文献标识码：A 文章编号：0253-231X(2017)03-0568-07

# Che Mass Transfer and Current Distribution of Vanadium Redox Flow Battery

SUN Hong1 ZHUANG Kai-Ming² YU Ming-Fu² WU Yu-Hou² (1.Department of Transportation Engineering,Shenyang Jianzhu University,Shenyang 11O168,China; 2.College of Mechanical Engineering,Shenyang Jianzhu University, Shenyang 110168,China)

Abstract In order to solve the shortened battery life problem caused by imbalance mass transferin all vanadium flow batteries，A three-dimensional mathematical model was established to simulate the mass transfer regularity in all vanadium flow batteries through coupling the proton exchange membrane mass transfer equation with Nernst-Planck equation, Butler-Volmer equation, and Nernst equation. The distribution of vanadium ions in different valence states,electrolyte current density and electrolyte potential of the vanadium redox fow battery was simulated. When discharging,reactant ions concentration decreased gradually and product ions changed reversely along the electrolyte flow direction.Electrolyte current density reached to its maximum on the membrane surface but decreased gradually along two sides of the current collctor flow direction. The electrolyte potential decreased gradually along the electrolyte flow and the direction from the cathode to the anode. The electrochemical reaction was more intense around the current collector.The proton transfer in the Nafion membrane mainly relied on electroosmosis efect and concentration effect. Key wordsvanadium redox flow battery; vanadium ions; current density; potential

# 0引言

随着人们对于能源需求的增加和化石能源的逐渐枯竭，可再生能源的开发和利用逐渐引起人们的关注和重视[1]。然而太阳能、风能等可再生能源具有明显的不连续、不稳定、不可控的非稳态特性，储能是解决这一问题的关键技术。全钒液流电池作为高效的储能技术之一，不仅可用于太阳能、风能等能量的储存，还可以用于电网的削峰填谷、调频调幅以及应急电源等多方面应用[2-3]。

电池的内部是一个包含多过程的耦合系统，电池的结构、电池内部的电化学反应、离子在电极内的传质、以及水和钒离子等物质在膜之间的渗透都对电池的性能有很大的影响[6-8]。全钒液流电池可以通过实验方法和模拟方法进行研究。WANG等通过对导流结构进行优化，降低了电池的浓差极化损失，提高了能量的转换效率[11]。YU 等[12]将隔膜进行处理，经测试改性后的隔膜的孔隙率变大，导电性增强，提高了电池的性能。

数值模拟是全钒液流电池研究的重要方法之一，可以研究电池的结构、反应条件等参数对电池内部传质的影响 [4]。全钒液流电池的数值模型是基于电池内部的氧化还原反应和传质过程，可以直观地反映电池内部的反应状态，所以对于钒电池的模拟研究多采用数值模型[13-15]。Wiedemann 等通过建立钒离子透膜的浓差扩散模型，得到了钒离子在无电场的情况下通过三种不同的离子交换膜的扩散系数[16]。Shah 等通过建立的全钒液流电池单体的二维等温动态模型，研究了浓度效应对电解液和水的迁移的影响[17]。Al-Fetlawi 等将二维等温模型扩展为非等温的模型，对电极的极化引起的能量效率的变化进行了研究[18]。Knehr 等考虑了其他离子在质子交换膜中的渗透对于电池性能的影响[15]。

电池内部的传质和各离子浓度的分布对电池性能有着重大的影响。本文通过对电极内物质的传质和反应过程的分析，建立了三维稳态的模型，利用数值方法从离子的扩散、电极的反应及膜中质子转移的角度研究了电池中各离子的分布状况、电解质电流密度以及电解质电势的分布情况。

# 1电池工作原理和结构

全钒液流电池的单体主要由夹具、电极流场板、石墨毡电极、电极框、质子交换膜、集流体和电解液储存罐、密封垫片等部件组成，电池单体的电解液从电极的两端流入，正极的电解液由四价和五价钒离子的硫酸溶液组成，负极的电解液由二价和三价钒离子的硫酸溶液组成。所建立的几何模型如图1所示，几何参数见表1。

![](images/fa23b29c42463fb60b87a52c776b6e99760be8847bf9099259e1d4f805d88030.jpg)  
图1全钒液流电池几何模型  
Fig.1 A geometric model of the vanadium flow battery

电池放电时，正极电解液中的 $\mathrm { V O _ { 2 } ^ { + } }$ 和负极电解液中的 $\mathrm { V ^ { 2 + } }$ 通过蠕动泵传输到电极表面发生氧化还原反应释放电能，此时负极电解液中的 $\mathrm { V } ^ { 2 + }$ 变为$\mathrm { V ^ { 3 + } }$ ，正极电解液中的 $\mathrm { V O _ { 2 } ^ { + } }$ 变为 $\mathrm { V O ^ { 2 + } }$ 。电池充电

时，发生可逆的氧化还原反应。离子在正极和负极  
区域内进行的化学反应如下：  
正极 $\mathrm { V O _ { 2 } ^ { + } } + 2 \mathrm { H ^ { + } } + \mathrm { e ^ { - } } \xrightarrow [ ] { \mu \times \pm } \mathrm { V O ^ { 2 + } } + \mathrm { H _ { 2 } O }$ 放电充电  
负极V2+ $\mathrm { V } ^ { 2 + } \frac { \stackrel {  } { \mu } \stackrel {  } { \mu } \stackrel {  } { \mu } } { \sim } \mathrm { V } ^ { 3 + } + e ^ { - }$ 充电  
总反应 $\mathrm { V O _ { 2 } ^ { + } + 2 H ^ { + } + V ^ { 2 + } \frac { \partial / \hat { \chi } \cdot \hat { \jmath } _ { - } } { \partial \cdot \mathrm { V O ^ { 2 + } + V ^ { 3 + } + H _ { 2 } O } } }$ 充电

表1模型的几何参数  
Table 1 Geometric parameters of the model   

<html><body><table><tr><td>参数</td><td>符号</td><td>数值</td><td>单位</td></tr><tr><td>负极电极厚度</td><td>Ln</td><td>4</td><td>mm</td></tr><tr><td>正极电极厚度</td><td>Lp</td><td>4</td><td>mm</td></tr><tr><td>质子交换膜厚度</td><td>Lm</td><td>0.18</td><td>mm</td></tr><tr><td>电极有效面积</td><td></td><td>35×35</td><td>mm²</td></tr><tr><td>电池的高度</td><td>H</td><td>35</td><td>mm</td></tr></table></body></html>

# 2数值模型

本文所建立的模型包括正极多孔电极、质子交换膜、负极多孔电极。为了使电解液与多孔电极充分接触进行电化学反应，电解液流经电池的方式如图1所示。采用三维、等温、稳态模型模拟电池的充放电状态。

# 2.1模型的假设

1）假设系统是一个稳态系统；2）假设电解液中各离子的行为与稀溶液中各离子的行为相同；3）假设质子传导膜是一个质子导体，只允许氢离子进行传递，其他离子和水分子的跨膜渗透不考虑。

# 2.2电极的过程动力学方程

根据假设 (2)，利用Nernst-Planck方程描述电解液中的离子传递行为：

$$
N _ { i } = - D _ { i , \mathrm { e f f } } \nabla c _ { i } - z _ { i } u _ { m , i , \mathrm { e f f } } F c _ { i } \nabla \varphi _ { 1 } + u c _ { i }
$$

上式包括了扩散项、迁移项和对流项， $N _ { i }$ 为 $i$ 组分的摩尔通量， $D _ { i , \mathrm { e f f } }$ 为 $\mathbf { \chi } _ { i }$ 组分在电极中的有效扩散系数， $u _ { m , i , \mathrm { e f f } }$ 为 $i$ 组分在电极中的有效迁移率, $u$ 为流体速度矢量。

本模型中利用Bruggemann 关系对扩散进行修正：

$$
D _ { i , \mathrm { e f f } } = \varepsilon ^ { 1 . 5 } D _ { i }
$$

其中 $\varepsilon$ 为多孔电极的孔隙率。迁移率由Nernst-Einstein关系给出：

$$
u _ { m , i , \mathrm { e f f } } = \frac { D _ { i , \mathrm { e f f } } } { R T }
$$

根据电荷守恒方程计算电极电流密度 $i _ { l }$ =

$$
i _ { l } = F \sum _ { i = 1 } ^ { n } z _ { i } ( - D _ { i } \nabla c _ { i } - z _ { i } u _ { m , i } F c _ { i } \nabla \varphi _ { l } )
$$

其中， $z _ { i }$ 为 $i$ 组分的电荷数， $D _ { i }$ 为 $i$ 组分在多孔电极中的扩散系数, $c _ { i }$ 为 $i$ 组分的浓度, $u _ { m , i }$ 为 $i$ 组分的迁移率。

电池的电极反应可以根据Butler-Volmer宏观动力学方程得：

$$
i _ { \mathrm { n e g } } = A i _ { \mathrm { 0 , n e g } } ( \exp { ( ( \frac { ( 1 - \alpha _ { \mathrm { n e g } } ) F \eta _ { \mathrm { n e g } } } { R T } ) -  }
$$

$$
\exp \left( \frac { - \alpha _ { \mathrm { n e g } } F \eta _ { \mathrm { n e g } } } { R T } \right) \Big )
$$

$$
i _ { \mathrm { p o s } } = A i _ { 0 , \mathrm { p o s } } ( \exp ( ( \frac { ( 1 - \alpha _ { \mathrm { p o s } } ) F \eta _ { \mathrm { p o s } } } { R T } ) - 
$$

$$
\exp \left( \frac { - \alpha _ { \mathrm { p o s } } F \eta _ { \mathrm { p o s } } } { R T } \right) \Big )
$$

其中， $A$ 是多孔电极的比表面积， $\alpha _ { \mathrm { n e g } }$ 和 $\alpha _ { \mathrm { { p o s } } }$ 分别是电池负极和正极反应的传递系数， $k _ { \mathrm { n e g } }$ 和 $k _ { \mathrm { p o s } }$ 分别为电池负极和正极的反应速度常数, $\eta _ { \mathrm { n e g } }$ 和 $\eta _ { \mathrm { p o s } }$ 分别为电池负极和正极反应的过电势。 $i _ { 0 , \mathrm { p o s } }$ 和 $i _ { 0 , \mathrm { n e g } }$ 分别为正、负极交换电流密度。

$$
i _ { 0 , \mathrm { p o s } } = F k _ { \mathrm { p o s } } ( a _ { \mathrm { V O ^ { 2 + } } } ) ^ { 1 - \alpha _ { \mathrm { p o s } } } ( a _ { \mathrm { V O _ { 2 } ^ { + } } } ) ^ { \alpha _ { \mathrm { p o s } } }
$$

$$
i _ { 0 , \mathrm { n e g } } = F k _ { \mathrm { n e g } } ( a _ { \mathrm { V } ^ { 2 + } } ) ^ { 1 - \alpha _ { \mathrm { n e g } } } ( a _ { \mathrm { V } ^ { 3 + } } ) ^ { \alpha _ { \mathrm { n e g } } }
$$

根据电池的反应方程式，电池的两个半反应的平衡电势可以由能斯特方程给出：

$$
E _ { \mathrm { e q , n e g } } = E _ { \mathrm { 0 , n e g } } + { \frac { R T } { F } } \ln \left( { \frac { a _ { \mathrm { V } ^ { 3 + } } } { a _ { \mathrm { V } ^ { 2 + } } } } \right)
$$

$$
E _ { \mathrm { e q , p o s } } = E _ { 0 , \mathrm { p o s } } + \frac { R T } { F } \ln \left( \frac { a _ { \mathrm { V O _ { 2 } ^ { + } } } ( a _ { \mathrm { H } ^ { + } } ) ^ { 2 } } { a _ { \mathrm { V O ^ { 2 + } } } } \right)
$$

其中， $\begin{array} { r } { \boldsymbol { E _ { 0 , \mathrm { n e g } } } } \end{array}$ 和 $E _ { \mathrm { 0 , p o s } }$ 分别为电池负极和正极反应的标准电极电势， $E _ { \mathrm { e q , n e g } }$ 和 $E _ { \mathrm { e q , p o s } }$ 分别为电池负极和正极的平衡电势, $a _ { \mathrm { i } }$ 是 $i$ 组分的化学活性， $R$ 为气体摩尔常数 $( 8 . 3 1 \ \mathrm { J / ( m o l \cdot K ) } )$ ， $T$ 是电池的温度， $F$ 是法拉第常数 $\left( 9 6 4 8 5 ~ \mathrm { s { \cdot } A / m o l } \right)$ 。

电池的两个半反应的过电势 $\eta ( \mathrm { V } )$ 被定义为：

$$
\eta _ { \mathrm { p o s } } = \left( \varphi _ { \mathrm { s , p o s } } - \varphi _ { \mathrm { l , p o s } } \right) - E _ { \mathrm { e q , p o s } }
$$

$$
\eta _ { \mathrm { n e g } } = ( \varphi _ { \mathrm { s , n e g } } - \varphi _ { \mathrm { l , n e g } } ) - E _ { \mathrm { e q , n e g } }
$$

其中， $\varphi _ { \mathrm { s } }$ 是多孔电极固相电势， $\varphi _ { \mathrm { l } }$ 是电解质电势。根据欧姆定律得到多孔电极中的电流 $i _ { \mathrm { s } }$ 为：

$$
i _ { \mathrm { s } } = - \sigma _ { \mathrm { s } } \nabla \varphi _ { \mathrm { s } }
$$

其中 $\sigma _ { \mathrm { s } }$ 为多孔电极的电导率。

# 2.3质子交换膜内的传质方程

由于正常的电解质电流密度等于膜的电流密度，所以有：

$$
n \cdot i _ { \mathrm { l , e } } = n \cdot i _ { \mathrm { l , m } }
$$

其中， $i _ { \mathrm { l , e } }$ 为电极中的电流， $i _ { \mathrm { l , m } }$ 为质子交换膜中的电流。因为质子通量和电流成正比，所以根据法拉第定律有：

$$
n \cdot N _ { + , \mathrm { e } } = n \cdot { \frac { i _ { \mathrm { l , m } } } { F } }
$$

其中， $N _ { + }$ 。为质子在膜中的通量，对于不渗透的离子，通量视为零。此外，电势和浓度的关系为：

$$
\varphi _ { \mathrm { l , m } } = \varphi _ { \mathrm { l , e } } + { \frac { R T } { F } } \ln \left( { \frac { a _ { + , \mathrm { m } } } { a _ { + , \mathrm { e } } } } \right)
$$

# 2.4边界条件

在正极的集流板上设定充放电电流的大小，负极的集流板上设定为电位接地边界。

1）电荷守恒方程

$$
\int \limits _ { \partial \Omega } i _ { \mathrm { s } } \cdot n \mathrm { d } l = i _ { \mathrm { s , a v e r a g e } } \int \mathrm { d } l ( \mathbb { M } \not \in \not \gimel \not \in \dot { 1 } \not \subseteq \not \exists \not \vdash )
$$

is,average为平均电极电流密度。

2)组分方程

入口条件：

$$
- \boldsymbol { n } \cdot \boldsymbol { N } _ { \mathrm { i } } = \boldsymbol { N } _ { 0 , \mathrm { i } }
$$

其中， $N _ { \mathrm { 0 , i } }$ 为 $\mathbf { \chi } _ { i }$ 组分向内的通量。

各组分的通量为：

$$
N _ { \mathrm { 0 , c H S O 4 _ { n e g } } } = \mathrm { c H S O 4 _ { 0 , n e g } } \times v
$$

$$
N _ { \mathrm { 0 , c H _ { n e g } } } = \mathrm { c H _ { 0 , n e g } } \times v
$$

$$
N _ { 0 , \mathrm { c V 2 } } = \mathrm { c V 2 } _ { 0 } \times v
$$

$$
N _ { 0 , \mathrm { { c V } 3 } } = \mathrm { { c V } 3 _ { 0 } } \times v
$$

出口条件：

$$
- \boldsymbol { n } \cdot \boldsymbol { D } _ { i } \nabla c _ { i } = 0
$$

# 2.5数值方法

本模型借助COMSOL 模拟软件，基于有限元方法，对电极动力学方程，扩散方程和电荷守恒方程进行耦合。在电池的正极和负极选择三次电流分布，Nernst-Planck物理场，膜区域选择二次电流分布物理场。在划分网格过程中，通过等差数列分布的方法将整个区域划分了1245个单元网格。构建几何模型时设置模型的相对修复容差为 $1 0 ^ { - 6 }$ 。

# 3数值模拟的结果与讨论

# 3.1模型的验证

为了验证所建立模型的准确性和可行性，在放电过程中将不同荷电状态下的实验电压值与模拟电压值进行对比。图2是电流密度为 $1 0 0 \ \mathrm { m A / c m ^ { 2 } }$ 、电解液流速为 $ { \mathrm { 3 0 ~ m L / m i n } }$ 、温度为 $2 0 ^ { \circ } \mathrm { C }$ 、进口钒离子浓度为 $1 5 0 0 \mathrm { m o l / m ^ { 3 } }$ 时液流电池放电过程中电池的模拟电压和实验电压随荷电状态SOC的变化曲线。图2显示，在放电过程中，模拟值和试验值吻合良好，最大误差小于 $4 \%$ ，平均误差小于 $1 \%$ ，证明了数值模型的可行性，因此本次建立的模型所计算的结果可靠。其误差可能由于在充放电后期反应物浓度快速下降产生的副反应造成的[10]。

![](images/7d0cf26db49af388a6fb86f8d67ad892bdb8ad20d90c25d91cb178b110b750b9.jpg)  
图2不同的 SOC下电池的模拟电压和实验电压的对比Fig.2 A comparison of simulated and measured dischargecurves under different SOC

# 3.2钒离子浓度的分布

全钒液流电池中参加反应最主要的活性物质是各价态的钒离子，本节根据所建立的三维模型，选取$X Y$ 面为研究面，对电极内钒离子浓度的分布情况进行了研究。模型的初始条件设定为，电池温度298.15K，流速 $\mathrm { 3 0 ~ m L / m i n }$ ，电解液浓度为 $1 2 0 0 \mathrm { m o l / m ^ { 3 } }$ 的$\mathrm { V ^ { 3 + } / V O ^ { 2 + } }$ 和 $\mathrm { 3 0 0 ~ m o l / m ^ { 3 } }$ 的 $\mathrm { V ^ { 2 + } / V O _ { 2 } ^ { + } }$ 。在电池放电的过程中，消耗 $\mathrm { V } ^ { 2 + }$ 和 $\mathrm { V O _ { 2 } ^ { + } }$ ，生成 $\mathrm { V ^ { 3 + } }$ 和 $\mathrm { V O ^ { 2 + } }$ ，如图 $3 { \sim } 6$ 所示，沿 $Y$ 轴方向 $\mathrm { V ^ { 3 + } }$ 和 $\mathrm { V O ^ { 2 + } }$ 离子的浓度逐渐增加， $\mathrm { V ^ { 2 + } }$ 和 $\mathrm { V O _ { 2 } ^ { + } }$ 的离子浓度逐渐减少。由于正、负电极在结构上是对称的，所以 $\mathrm { V } ^ { 2 + }$ 和 $\mathrm { V ^ { 3 + } }$ 浓度分布情况与 $\mathrm { V O _ { 2 } ^ { + } }$ 和 $\mathrm { V O ^ { 2 + } }$ 的浓度分布状况也是相似的。在充放电过程中，电池通过集流体和外部进行电子的传递，在电池内部是通过质子交换膜进行质子的传递。如图3和图4所示，在 $X$ 轴方向上 $\mathrm { V } ^ { 2 + }$ 和 $\mathrm { V O _ { 2 } ^ { + } }$ 离子的浓度向集流板一侧逐渐减少,如图5和图6所示，在 $X$ 轴方向上 $\mathrm { V ^ { 3 + } }$ 和 $\mathrm { V O ^ { 2 + } }$ 离子的浓度向集流板一侧逐渐增多。越靠近集流体，离子间的反应越剧烈。

![](images/d53d822de91e4f8981aad9e9b61a47f8134439a54c9b42a883b8a34f7813999d.jpg)  
图3 $\mathrm { V ^ { 2 + } }$ 的浓度分布（单位： $\mathrm { m o l } / \mathrm { m } ^ { 3 }$ ）Fig.3 The concentration distribution of $\mathrm { V } ^ { 2 + }$

![](images/f7361815d4f59ab8a2b532623832fe4ccc54d4bdbb40f2c6b69ecfdbcc42eacb.jpg)  
图4 $\mathrm { V O _ { 2 } ^ { + } }$ 的浓度分布（单位： $\mathrm { m o l } / \mathrm { m } ^ { 3 }$ ）Fig.4 The concentration distribution of $\mathrm { V O } _ { 2 } ^ { + }$

![](images/de294cba48499d2d2ed1add34d04caabb377f84343c01c10d9af65fc759045f7.jpg)  
图5 $\mathrm { V ^ { 3 + } }$ 的浓度分布（单位： $\mathrm { m o l } / \mathrm { m } ^ { 3 }$ ） Fig.5 The concentration distribution of $\mathrm { V ^ { 3 + } }$

![](images/6f48d213d20ff1948956288b55a8f407ee4bf1c8cbd5a9757c77e07c7d246cd5.jpg)  
图6 $\mathrm { V O ^ { 2 + } }$ 的浓度分布（单位： $\mathrm { m o l } / \mathrm { m } ^ { 3 }$ ）Fig.6 The concentration distribution of $\mathrm { V O ^ { 2 + } }$

![](images/96d55ee33ff496e2e03c5d5b64d6caa85d522b556561f2210d87f444e9a6aff8.jpg)  
图8阳极电解质电流密度分布（单位： $\mathrm { A / c m ^ { 2 } }$ ） Fig.8 Electrolyte electric current density distribution in the anode

# 3.3电解质电流密度的分布

如图7、图8所示电解质电流密度分布随着在多孔电极中的位置的不同而不同，在靠近质子交换膜表面处的电解质电流密度较大，而在远离膜的位置处电解质电流密度较小。模拟计算结果表明：沿着$Y$ 轴方向，电解质电流密度逐渐降低，由于随着反应的进行，反应物逐渐被消耗，电解质浓度降低时电解质电流密度沿液体流动方向降低。当反应速度等于及大于最大传质速度时，影响电解质电流密度分布的因素为传质，也就是此时的电解质电流密度分布不随着反应速度的改变而改变；而反应速度小于最大传质速度时，影响反应结果的因素为反应速度，电解质电流密度随反应速度的改变而逐渐改变分布状态，由于靠近集流体处的电解质电流密度变化梯度大，所以靠近集流体附近的反应速度较快。图9所示为在质子交换膜表面的电解质电流密度的分布情况，在 $X$ 方向上电解质电流密度没有较大的变化,在 $Y$ 方向上电解质电流密度先增大后逐渐减小，由于假设在质子交换膜中只允许质子的通过，所以在Nafion 膜中质子的传递主要有两种形式，电渗作用和浓差扩散。由于开始时反应物充足，随着反应的进行电解质电流密度快速的增大到最大值，反应达到平衡，随后由于反应物浓度的减少，沿着电解液流动的方向，电解质电流密度逐渐减少。

![](images/2deb1048672babce48db1c2c66cc0bf997492e41bc2ebbcd5830e4c12beb25a7.jpg)  
图7阴极电解质电流密度分布（单位： $\mathrm { A / c m ^ { 2 } }$ ） Fig.7 Electrolyte electric current density distribution in the cathode

![](images/8ea00a034cb58b003c6f5d614742532ca8295ae81892fbec5d428316d609ce49.jpg)  
图9膜内电解质电流密度分布（单位： $\mathrm { A / c m ^ { 2 } }$ ） Fig.9 Electrolyte electric current density distribution in the membrane

# 3.4电解质电势的分布

电极中的电解质电势分布如图10、图11所示。沿着 $X$ 轴方向上，电解质电势逐渐降低，这与液流电池的物理现象是一致的，在阴极中电子是沿着外电路流向阳极，同时质子在浓度差的影响下通过质子交换膜向阳极流动，在阳极与钒离子发生反应，沿着 $Y$ 轴方向上电解质电势逐渐减少，这是由于随着反应的进行，反应物逐渐消耗，沿着电解液的流动方向上，电解质电势会逐渐减小。图12所示为在膜中的电解质电势分布情况，沿 $X$ 方向和 $Y$ 方向，电解质电势逐渐减小。在质子交换膜与多孔电极的交界面处存在电势的变化，根据唐南电势原理，对于渗析平衡体系，若质子交换膜一侧的不能透过膜的大分子或胶体粒子带电，则体系中本来能自由透过膜的质子在膜的两边的浓度不再相等，产生了附加的渗透压，能斯特关系给出了可渗透离子处于平衡态时的跨膜势，即维持平衡浓度差所需要的电压。而唐南平衡产生静息膜电位，这个电压将造成离子浓度差。同时在质子交换膜的两侧存在的电势差由两部分组成，一部分是离子电流密度与膜的电阻的乘积,另一部分是由于两侧电解质溶液的组分不同造成的浓差平衡电势差。

![](images/98771792ff35cb5923895d3850b74fef8844ee6649f2e3cdf755a12da855e126.jpg)  
图10阴极电解质电势分布 (单位：V)

![](images/a5113382eeb043505086744c60d80a37817a876c6aca6a81e6e29cd9fefb3a7e.jpg)  
Fig.1O Electrolyte potential distribution in the cathode   
图11 阳极电解质电势分布 (单位：V)

![](images/653a41744b79b190ec8118a28f41336642ee753a77046b9330603494c294f3a2.jpg)  
Fig.11 Electrolyte potential distribution in the anode   
图12膜内电解质电势分布 (单位：V)  
Fig.12 Electrolyte potential distribution in the membrane

# 4结论

本文使用数值模拟的方法，通过对离子在电极中的扩散和反应的研究，建立了三维等温稳态的数值模型，得到了以下结论：

1）放电过程中，在电极表面沿电解液流动方向和由质子交换膜指向电极的方向上， $\mathrm { V ^ { 3 + } }$ 和 $\mathrm { V O ^ { 2 + } }$ 离子的浓度逐渐增加， $\mathrm { V } ^ { 2 + }$ 和 $\mathrm { V O _ { 2 } ^ { + } }$ 的离子浓度逐渐减少；

2)在电极表面，电解质电流密度在靠近质子交换膜处较大，而在远离膜的位置处较小；在质子交换膜表面，沿电解液流动方向电解质电流密度先增大后逐渐减小；

3）在电极中，沿电解液流动方向和阴极指向阳极方向，电解质电势分布逐渐降低；在质子交换膜中，沿电解液流动方向和阴极指向阳极方向，电解质电势分布逐渐减少。

# 参考文献

[1]Dunn B,Kamath H,Tarascon JM.Electrical Energy Storage for the Grid:a Battery of Choices [J]. Science,2011,   
334(6058): 928-935 [2]Chakrabarti M H,Lindfield Roberts E P,Saleem M. Charge-Discharge Performance of a Novel Undivided Redox Flow Battery for Renewable Energy Storage [J].International Journal of Green Energy,2010,7(4):445-460 [3]HuangKL,LiX,Liu S,et al.ResearchProgress of Vanadium Redox Flow Battery for Energy Storage in China [J]. Renewable energy,2008,33(2):186-192 [4] Ma L,InghamDB,Pourkashanian M,et al.Review of the Computational Fluid Dynamics Modeling of Fuel Cells [J]. Journal of Fuel Cell Science and Technology, 20o5,2(4):   
246-257 [5]Skyllas-Kazacos M,Chakrabarti MH,Hajimolana SA,et al.Progress in Flow Battery Research andDevelopment [J].Journal of The Electrochemical Society,2011,158(8): R55-R79 [6] ShahAA,Watt-Smith MJ,WalshFC.ADynamic Performance Model for Redox-Flow Batteries Involving Soluble Species [J].Electrochimica Acta,2008,53(27):8087-   
8100 [7]Al-FetlawiH,Shah AA,WalshFC.Non-isothermal Modelling of the All-Vanadium Redox Flow Battery [J].Electrochimica Acta,2009,55(1):78-89   
[8]Al-FetlawiH,ShahAA,WalshFC.Modelling the Effects of Oxygen Evolution in the All-Vanadium Redox Flow Battery [J].Electrochimica Acta,2010,55(9):3192-3205   
[9]Shah AA,Al-FetlawiH,WalshF C.Dynamic Modelling of Hydrogen Evolution Effects in the All-Vanadium Redox Flow Battery [J].Electrochimica Acta,2010,55(3): 1125-1139   
[10]You D，Zhang H，Chen J.A Simple Model for the Vanadium Redox Battery[J].Electrochimica Acta,2009, 54(27): 6827-6836   
[11]汪钱，陈金庆，王保国．导流结构和电极结构对全钒液流电 池性能的影响[J].电池，2008,38(6)：346-348 WANG Q,CHENJ,WANGB.Influence ofFlow Oriented Structure and Electrode Structure on the Performance of all Vanadium Redox Flow Battery [J].Battery Bimonthly, 2008,6:004   
[12]梁艳,何平,于婷婷,等.添加剂对全钒液流电池电解液的影 响[J].西南科技大学学报，2008,23(2)：11-14 LIANG Yan,HE Ping，YU Ting-ting,et al.Influence of Additives on All Vanadium Redox Flow Battery Electrolyte [J].Xian University of Science and Technology Acta,2008,23(2):11-14   
[13]Ma X,Zhang H,Xing F.A Three-Dimensional Model for Negative Half Cell of the Vanadium Redox Flow Battery [J].Electrochimica Acta,2011,58:238-246   
[14] Zheng Q,Zhang H,Xing F,et al.A Three-Dimensional Model for Thermal Analysis ina Vanadium Flow Battery [J].Applied Energy,2014,113:1675-1685   
[15]KnehrK W,Agar E,Dennison CR,et al.A Transient Vanadium Flow Battery Model Incorporating Vanadium Crossover and Water Transport Through the Membrane [J].Journal of The Electrochemical Society,2012,159(9): A1446-A1459   
[16]Wiedemann E,Heintz A,Lichtenthaler R N.Transport Properties of Vanadium Ions in Cation Exchange Membranes: Determination of Diffusion Coefficients Using a Dialysis Cell [J].Journal of Membrane Science，1998, 141(2): 215-221   
[17] Shah A A,Al-Fetlawi H,Walsh F C.Dynamic Modelling ofHydrogen Evolution Effects in the All-Vanadium Redox Flow Battery [J].Electrochimica Acta,2010,55(3): 1125-1139   
[18]Al-FetlawiH,ShahAA,Walsh FC.Non-Isothermal Modelling of the All-Vanadium Redox Flow Battery [J].Electrochimica Acta,2009,55(1):78-89