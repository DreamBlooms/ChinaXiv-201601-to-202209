# 颗粒表面吸附层对纳米流体导热系数贡献的分子动力学研究

王新 敬登伟\*1

（西安交通大学动力工程多相流国家重点实验室，西安710049）

摘要：本文采用平衡分子动力学方法研究了纳米流体中固体颗粒周围的吸附层厚度及结构，并通过Green-Kubo 原理计算了吸附层内导热系数的分布。研究表明，纳米颗粒周围存在 $0 . 5 \mathrm { n m }$ 厚的吸附层，层内原子数密度提高了 $50 \text{‰}$ ，导热系数提高了$20 0 - 3 0 0 \%$ 。分析发现，吸附层导热系数的提高是由于原子数密度及吸附层内原子排列有序程度的提高引起的。该研究结果有望为建立合理的预测纳米流体的导热系数模型提供关键参数及理论指导。

关键词：纳米流体；吸附层；导热系数；分子动力学中图分类号： TK123 文献标识码：A

Molecular dynamics study of contribution of the particle surface absorption layer to the

thermal conductivity of nanofluids

WANG XinJING Deng-Wei\*

State Key Laboratory ofMultiphase Flow in Power Engineering, Xi'an Jiaotong University, Xi'an 710049, China)

Abstract: In this article we studied the thicknessand structure of absorption layer around nanoparticle and derived the thermal conductivity distribution based on the principle of Green-Kubo by equilibrium molecular dynamics simulation. The results showed that there is a $0 . 5 \mathrm { - n m }$ -thickness absorption layer with $50 \text{‰}$ enhancement on atom number density and $20 0 - 3 0 0 \%$ enhancement on thermal conductivity. It was found after analysis that the enhancement of thermal conductivity(TCE) is the result ofboth the enhancement of number density and the more ordered alignment of atoms within the absorption layer. Our Work is expected to provide critical parameters for the establishment of the mathematical model for prediction of the thermal conductivity of various nanofluids.

Key words: nanofluid; absorption layer; thermal conductivity; molecular dynamics

# 0引言

纳米流体是以一定的比例和方式在液体中添加纳米级尺度的金属或非金属固体颗粒形成的一类新的传热冷却介质[1]。大量的实验研究表明，纳米流体的导热系数由于纳米颗粒的加入而实现显著的提高[2-6]。然而，传统的基于有效介质理论的预测固液两相混合物导热系数的经典模型[7-9]在被用于预测纳米流体的导热系数时，其预测结果往往较实验值偏小。为了有效预测纳米流体的导热系数，国内外研究者基于纳米颗粒自身的特性及影响，提出了不同的热传导机理，归纳起来主要有以下三种：（1）颗粒的布朗运动及其引起的微对流[10-14]；（2）颗粒的团聚[15-19]；（3）颗粒表面的液体吸附层[20-25]。

2001年，Choi[20提出纳米颗粒与基液间存在吸附层，该层吸附层原子数密度大于纯液体且排列更加有序，因此其导热系数也大于纯液体。在此理论基础上，Yu 和Choi[21-22]先后发展出了修正后的 Maxwell andHamilton-Crosser 模型。Leong[23]，Xie[24]和 Rizvi[25]等人的研究工作也充分考虑了颗粒表面的吸附层发展出了不同的预测模型，这些模型与一部分实验结果吻合的很好，但都不具有普适性。

吸附层的厚度及导热系数是上述模型的两个重要参数，但这些模型本身并不能得到这两个参数。因此，有必要通过其它手段对吸附层进行研究。2009 年，Gerardi[26采用核磁共振实验方法测量出在氧化铝纳米颗粒表面形成了厚度为1.4nm 的液体吸附层。然而，就目前的报道而言，这样的实验结果是非常有限的[27]。而另一方面，在纳米级尺度下，分子动力学的快速发展为吸附层的研究提供了一种有效手段[28-33]。本文采用平衡分子动力学首次计算出吸附层内导热系数的分布，并对层内原子数密度的分布曲线及影响层内的导热系数的因素进行分析研究。

# 1 模拟方法

分子动力学是从微观层面研究纳米流体导热机理的有效手段[27]。分子动力学模拟根据牛顿运动力学从每个原子的初始位置及初始速度出发，由原子间的势能函数求解出每个原子所受的力，从而获得原子下一时刻的位置及速度，依次可得到系统内每个原子随时间的运动过程。原子的微观运动可以用来解释物质在宏观层面可观测的物理特性。

本文选择氩（Ar）原子构成基液，铜原子（Cu）或银原子（Ag）构成固体纳米颗粒，由于Ar原子的势能函数及参数与实验值吻合的很好，上述纳米流体体系被各种实验及理论研究广泛使用[28-33]。

![](images/74e2f9ce57b5eef010f2a8ae7f659eaf417ac175c7fa62df647cfa12b1f7529d.jpg)  
图1原子的初始位置图  
Fig.1 The original position of atoms

如图1所示，本文首先建立一个边长为 $1 0 \ \mathrm { n m }$ 的立方体作为模拟盒子，在盒子的中心划分出一个球形区域放置纳米颗粒，并将纳米颗粒限制在比其半径大 $0 . 1 \ \mathrm { n m }$ 的球形区域以方便后续的导热系数计算。Ar，Cu和Ag原子均按照面心立方堆积（FCC）方式排布，晶格常数分别是$5 7 3 . 0 6 , 3 6 1 . 4 9 , 4 0 7 . 3 0 ~ \mathrm { p m }$ ，其中 Ar 原子的晶格常数按照液氩密度等于 $1 4 1 0 \mathrm { k g / m } ^ { 3 }$ 计算而得。

Ar-Ar, $\mathrm { { C u - C u } }$ 和 $\mathrm { \ A r { - } C u }$ 原子间均采用L-J势能函数，其形式如下：

$$
\begin{array} { r l r } { \mathrm { U \Big ( r _ { i j } \Big ) } = 4 \varepsilon \Big [ \Bigg ( \frac { \sigma } { \mathrm { r _ { i j } } } \Bigg ) ^ { 1 2 } - \Bigg ( \frac { \sigma } { \mathrm { r _ { i j } } } \Bigg ) ^ { 6 } \uparrow \ \mathrm { r < r _ { c } } } & { } & \\ { \mathrm { U \Big ( r _ { i j } \Big ) } = 0 ? } & { } & { \quad \mathrm { r \geq r _ { c } } } \end{array}
$$

其中， $r _ { i j }$ 为原子 $i$ 和 $j$ 之间的距离， $r _ { c }$ 为截断半径，在此取 $1 . 5 \ \mathrm { n m }$ ，ε和 $\sigma$ 为势能函数的能量参数和长度参数，不同类原子间的势能参数可以由Lorentz-Berthelot混合法则取得，即：

$$
\sigma _ { \mathrm { { s l } } } = \frac { \sigma _ { \mathrm { { s s } } } + \sigma _ { \mathrm { { l l } } } } { 2 }
$$

$$
\mathfrak { E } _ { \mathrm { s l } } = \sqrt { \mathfrak { E } _ { \mathrm { s s } } \mathfrak { E } _ { \mathrm { l l } } }
$$

本文模拟所用到原子间的势能参数由文献所得，具体如下表所示[32]：

表 $1 ( \mathsf { c u } / \mathsf { A r }$ 相互作用的L-J势能参数Table1L-Jparameters used for Cu-Ar nanofluids  

<html><body><table><tr><td>原子对</td><td>σ/nm</td><td>ε/10-28J</td></tr><tr><td>Ar-Ar</td><td>0.3405</td><td>1.654</td></tr><tr><td>Cu-Cu</td><td>0.2338</td><td>65.581</td></tr><tr><td>Ag-Ag</td><td>0.2644</td><td>55.24</td></tr></table></body></html>

<html><body><table><tr><td>Cu-Ar</td><td>0.2872</td><td>10.415</td></tr><tr><td>Ag-Ar</td><td>0.3025</td><td>9.559</td></tr></table></body></html>

模拟中采用周期性边界条件，时间步长选取0.1fs，体系温度设定为 $8 5 \mathrm { ~ k ~ }$ ，体系在NVT系综下运行2000000步，再在NVE系综下运行2000000步，经过充分弛豫使体系达到平衡状态，记录此时各区域的原子数，最后在NVE系综下运行1000000步计算导热系数。根据Green-Kubo原理，导热系数可通过对微观热流的自相关函数积分求得，即

$$
\mathrm { K } = \frac { 1 } { \mathbf { k } _ { \mathrm { B } } \mathrm { V T } ^ { 2 } } \int _ { 0 } ^ { \infty } \mathbf { J } _ { \mathrm { x } } \left( 0 \right) \mathbf { J } _ { \mathrm { x } } \left( \mathbf { t } \right) \mathrm { d } \mathbf { t } { \mathrm { } } ^ { 2 } = \frac { 1 } { 3 \mathbf { k } _ { \mathrm { B } } \mathrm { V T } ^ { 2 } } \int _ { 0 } ^ { \infty } \mathbf { J } \left( 0 \right) \mathbf { J } \left( \mathbf { t } \right) \mathrm { d } \mathbf { t }
$$

$$
\mathrm { \frac { 1 } { V } } \Bigg [ \sum _ { \mathrm { i } } \mathrm { e } _ { \mathrm { i } } \mathbf { v } _ { \mathrm { i } } + \sum _ { \mathrm { i } < j } ( \mathbf { f } _ { \mathrm { i j } } \mathbb { \Gamma } \mathrm { \Gamma } \mathrm { \Gamma } \mathrm { \Gamma } _ { \mathrm { j } } ) \mathbf { x } _ { \mathrm { i j } } \Bigg ]
$$

其中， $K _ { B }$ 是玻尔兹曼常数， $V$ 是计算区域的体积， $T$ 是体系的温度， $J$ 是计算区域原子的微观热流， $e _ { i }$ 是原子 $i$ 的总能量（势能与动能的总和)， $\boldsymbol { \nu } _ { i }$ 是原子 $i$ 的速度矢量， $f _ { i j }$ 是原子 $i$ 与 $j$ 之间的作用力， $x _ { i j }$ 是原子 $i$ 与 $j$ 之间的距离。

# 2结果与讨论

# 2.1平衡状态的确定

在计算导热系数之前，保证体系达到平衡状态是至关重要的。当体系总原子数较多时（9000个原子)，不论是否处于平衡状态，体系的温度或能量都会很快稳定在某一定值[2]。本文的模拟体系中原子总数超过20000个，因此，仅仅通过温度或能量的涨落幅度已不足以判断体系是否进入平衡状态。在有关纳米流体吸附层的分子动力学研究中，固体颗粒周围原子数密度随时间的变化是一种行之有效的平衡判断标准[32]。从图2可看出，在运行到500000步（50ps）时，体系的温度波动范围已经很小，我们选择从此刻开始进行分析。

如图3所示，横坐标表示球壳区域与固体纳米颗粒表面的径向距离，纵坐标表示该区域的原子数密度 $n$ ，由球壳区域内的原子数 $N$ 及体积 $V$ 计算而得：

$$
\mathrm { n = \frac { N } { V } }
$$

![](images/69eef68fe26ad68de61ad6ff56391eec2b88fb9b6bbbe483f518de438366c6fc.jpg)  
图2弛  
豫过程中体系的温度变化

![](images/08154510375812df3ca15a916da59d8317ac21427efc20975c30e213580b8719.jpg)  
Fig.2 The evolution of temperature duringrelaxation   
图3   
Fig.3 Comparison of number density at different simulatior times

由图3可以看出，50ps与100ps 两时刻的原子数密度分布相比较，靠近固体纳米颗粒表面的区域原子数密度大幅度上升，说明在这段时间内体系中的原子由于固液原子间的相互作用向固体纳米颗粒表面迁移，体系并未进入平衡状态。100ps与200，300，400ps相比，原子数密度分布波动很小，可以判断出400ps 时体系已经达到平衡状态。

通过弛豫过程使体系进入平衡状态，就可以在NVE系综  
下进行导热系数的计算，而公式(3)中的积分时间原则上取无  
限长，在实际计算过程中计算时间不可能无限长，但积分时间选取过短，计算误

图4导热系数结果随积分时间的变化

![](images/20894c62fd2e2f5eb0bf64dae80c49600820d4ab35106d0e3327d824b04a5cba.jpg)  
不同时刻液体原子数密度比较  
Fig. 4   
thermal conductivity and integral time

Relations hip between result of

差会偏大。采用平衡分子动力学的方法计算导热系数，可以根据热流密度或导热系数的计算结果随积分时间的变化选取合理的积分时间[31]。如图4所示，可以看出随着积分时间变长，导热系数逐渐趋近于某一常数，计算误差趋近于0。本模拟选取100000步（ $1 0 0 \mathrm { p s }$ ）作为积分时间是合理的。

# 2.2原子数密度的分布

在分子动力学模拟中，纳米颗粒周围原子数密度的提高被用来研究吸附层[32-34]。本文将纳米颗粒周围的区域分成一系列紧邻的厚度为 $0 . 1 \ \mathrm { n m }$ 的球壳区域，计算每个区域的原子数密度，得到原子数密度分布图。如图5，可以看出在$0 . 2 , 0 . 5 , 0 . 8 ~ \mathrm { n m }$ 位置，原子数密度出现峰值，在 $0 . 8 \mathrm { n m }$ 之外原子数密度分布均匀可视为纯液氩的原子数密度。相比于纯液氩的原子数密度 $2 1 / \mathrm { n m } ^ { 3 }$ ，在 $0 . 0 . 2 \ \mathrm { n m }$ 区域平均原子数密度为$4 6 / \mathrm { n m } ^ { 3 }$ ， $0 { - } 0 . 5 \ \mathrm { n m }$ 区域平均原子数密度为 $2 9 / \mathrm { n m } ^ { 3 }$ ，这表明纳来颗粒周围形成了厚度约为 $0 . 5 \mathrm { n m }$ 的吸附层。平均而言，厚度为 $0 . 5 \mathrm { n m }$ 的吸附层原子数密度提高了 $50 \text{‰}$ 。

同时，从图5中也可以看出，在0.1， $0 . 3 \ \mathrm { n m }$ 等处层内原子数密度明显小于纯液氩的原子数密度，表明吸附层内原子数密度的分布是极不均匀的，其原因是吸附层结构的形成不仅取决于固液间相互作用，液体间的相互作用也是不可忽视的。结合图6，在 $0 { \cdot } 0 . 1 \ \mathrm { \ n m }$ 区域，由于距离太近，固液间表现为斥力作用，因此原子数密度较小；在 $0 . 1 \mathrm { - } 0 . 2 \ \mathrm { n m }$ 区域，由于固液间的相互吸引作用，原子数密度出现极大值；在$0 . 2 \mathrm { - } 0 . 5 \ \mathrm { n m }$ 区域，如果只考虑固液间的相互作用，原子数密度应该单调递减至纯液体的

![](images/a17f536f20039ff234d2ba081bc0430f80d597e02ffb167ad0d18b4a52020c39.jpg)  
图5铜纳米颗粒周围原子数密度的分布曲线

![](images/c7c8c68034f24c9441ff99a745e4cf68047509f0ca19bb522bceb9c9fef26b46.jpg)  
Fig.5Number density distribution curve around $\mathrm { C u }$ nanoparticle   
图6两原子间的势能随距离的变化

Fig.6 Evolution of potential energy with distance between two

![](images/1a31908d4dccf0dc23d4109c9d2e46fb353a35ec38c7d1367686ed8f887f617e.jpg)  
图7银纳米颗粒周围原子数密度的分布曲线

Fig.7 Number density distribution curve around $\mathbf { A } \mathbf { g }$ nanoparticle

原子数密度，但实际曲线表现为先急剧的减小再增加到另一个峰值，这是因为在 $0 . 2 \mathrm { - } 0 . 5 \ \mathrm { n m }$ 区域内，液体间的相互作用占据主导地位，由于 $0 . 1 \mathrm { - } 0 . 2 \ \mathrm { n m }$ 区域内原子数密度极大，这对相邻区域内原子的作用力也得到了加强，对距离较近的$0 . 2 \mathrm { - } 0 . 3 \ \mathrm { \ n m }$ 区域内的原子表现出斥力作用使其原子数密度急剧减小，对距离较远的 $0 . 4 \mathrm { - } 0 . 5 \ \mathrm { n m }$ 区域内的原子引力增加使其原子数密度增大。 $0 . 5 \ \mathrm { n m }$ 之后固液间相互作用可以忽略，原子数密度出现的极大极小值都可以依次解释。王楠等人[34]的研究工作表明吸附层呈现出双层结构，类似于扩散双电层模型，内层厚度约为 $0 . 4 2 \mathrm { n m }$ ，内外层总厚度约为 $0 . 7 6 \mathrm { n m }$ ，这与我们的研究结果吻合，但对出现该结构的深层次原因，该文并未进一步深入探讨。Cui等人[32]的研究中，随时间变化，原子数密度曲线整体下降，表明模拟过程中体系的总原子数在减少，就其采用的周期性边界条件而言，出现这样的结果是不合理的。

随着纳米颗粒直径从 $1 \ \mathrm { n m }$ 增大到 $3 \ \mathrm { n m }$ ，吸附层的厚度及结构并未出现明显变化。对比图7，可看出不同材料的纳米颗粒，吸附层的厚度及结构变化不大。

# 2.3导热系数的分布

本研究采用平衡分子动力学方法，基于Green-Kubo原理，在体系达到平衡状态后，计算每个球壳区域的导热系数，可以得到导热系数的分布曲线（不包含 $0 { \cdot } 0 . 1 \ \mathrm { n m }$ 区域的导热系数)，结果如图8及图9所示。平均而言，在 $0 . 1 \mathrm { - } 0 . 2 \ \mathrm { n m }$ 区域内，导热系数提高了 $3 0 0 \% { \cdot } 6 0 0 \%$ ；在0.1-0.5区域内，导热系数提高了约 $2 0 0 \% - 3 0 0 \%$ 。这表明吸附层内的导热系数大于纯液氩。

Babaei 等人[31]研究结果表明采用平衡与非平衡分子动力学方法计算纳米流体的导热系数，两种不同的方法结果是一致的，相差值是微小到可忽视的。而Liang 等人[30采用非平衡分子动力学方法，对于 $\mathrm { { C u / A r } }$ 体系的研究结果表明，吸附层的导热系数提高了约 $60 \%$ ，这与我们的结果差距较大，其原因主要是其吸附层的厚度选取为 $1 . 1 5 8 \mathrm { n m }$ 。当我们的吸附层厚度取 $1 . 1 \mathrm { n m }$ 时，吸附层导热系数提高了 $40 \% - 5 0 \%$ ，则小于 $60 \%$ 。这主要是由于Liang的模拟体系中，吸附层形成于铜原子组成的墙壁而不是球形颗粒，吸附层结构是矩形层状的而不是球壳状。这就意味着相对于我们的模型，Liang等人的模型中具有高导热系数的 $0 . 1 \mathrm { - } 0 . 2 \ \mathrm { ~ n m }$ 薄层的体积有显著提高，从而解释了其结果与我们结果的差值。

另外，对比原子数密度与导热系数分布图，可看出，图5和图7中的曲线分别与图8和图9中对应的曲线变化趋势同步一致。在0.2，0.5， $0 . 8 \mathrm { n m }$ （甚至包括 $1 . 1 \ \mathrm { n m }$ ）处原子数密度出现峰值，导热系数也出现相应的峰值；在 $0 . 3 , 0 . 6 , 0 . 9 \mathrm { n m }$ 处原子数密度出现极小值，导热系数也出现极小值；同时，也可以看出，任意两区域相比，原子数密度大，则导热系数也大，反之亦然。这表明导热系数的提高与原子数密度密切相关。

![](images/37876bde5e8e653fad5eaf5a8722847c4ff2324bcfc0dab5b5d5dce2072d7121.jpg)  
图8铜纳米颗粒周围导热系数的分布曲线 Fig.8 thermal conductivity distribution curve around $\mathrm { C u }$ nanoparticle

![](images/b090542115eb5576e9c7b67576c58343252ad74eeeda95ea0d63fdf66be21f05.jpg)  
图9银纳米颗粒周围导热系数的分布曲线 Fig.9 thermal conductivity distribution curve around Ag nanoparticle

![](images/de763358318b38e08ec2a9c34722a6144f6cb0c39fef52d83b0cf5a21dc28436.jpg)  
图10铜  
纳米颗粒周围单个Ar原子导热系数的分布曲线 Fig.10 thermal conductivity distribution curve of serial Ar atom around Cu nanoparticle

![](images/95c9315dcbdf7a95dc1ae0a18243ca8ba1b420243ce939cabee625e234228e70.jpg)  
图11银纳米颗粒周围单个Ar原子导热系数的分布曲线 Fig.11 thermal conductivity distribution curve of serial Ar atom around Ag nanoparticle

为了探究原子数密度与导热系数的关系，我们定义了如下的无量纲原子数密度 $n ^ { * }$ ：

$$
\begin{array} { r } { \mathfrak { N } ^ { * } = \frac { \mathfrak { n } } { \mathfrak { n } _ { \mathtt { i } } } } \end{array}
$$

其中， $n$ 为各球壳区域的原子数密度， $n _ { \theta }$ 为纯液氩的原子数密度，取 $2 1 / \mathrm { n m } ^ { 3 }$ 。本文采用导热系数与无量纲原子数密度的比值表征每个原子对导热系数的影响，可得到图10和图11。可以看出，在 $0 . 1 \mathrm { - } 0 . 5 \ \mathrm { \ n m }$ 的区域，每个吸附层原子对导热系数的贡献也有显著提高，平均而言提高了约 $40 \text{‰}$ 。

通过以上分析可看出，吸附层的形成及其高导热特性根本原因在于较强的固液间的相互作用。由于固液间的这种相互作用，一方面使其周围原子数密度增大；另一方面原子排列的有序化程度提高，导热结构得到优化，表现为每个原子对于导热系数的贡献也有所提高。

# 3结论

本文通过平衡分子动力学方法详细研究了吸附层原子数密度及导热系数的分布。主要得到以下结论：

（1）本文模拟表明吸附层的厚度约为 $0 . 5 \ \mathrm { n m }$ 。相比于纯液体，吸附层内的原子数密度提高了 $50 \text{‰}$ ，导热系数提高了 $20 0 - 3 0 0 \%$ 。该结果为准确预测纳米流体的导热系数提供了理论支撑。（2）由于固液和液液间原子的相互作用，吸附层内原子数密度及导热系数分布极不均匀，且在本文的模拟中，吸附层的厚度并未随着纳米颗粒粒径的变化而出现明显变化。（3）吸附层导热系数的提高一方面是由于原子数密度的提高，另一方面是由于原子排列有序化程度提高，两者的影响基本相当。（4）吸附层形成是由于固液间的相互作用力强于液体内部作用力，这启示我们在实际选取纳米流体时，固液间的相互作用也是一个值得考虑的因素。

# 参考文献

[1]Choi S U S.Enhancing thermal conductivity of fluids with nanoparticles[J].ASME-Publications-Fed,1995,231: 99-106. [2] Choi S U S,Zhang Z G, Yu W,et al. Anomalous thermal conductivity enhancement in nanotube suspensions[J].Applied Physics Letters,2001,79(14): 2252-2254.   
[3] Eastman JA, Choi S U S,Li S,et al. Anomalously increased effectivethermal conductivitiesof ethyleneglycol-based nanofluids containing copper nanoparticles[J].Applied Physics Letters,2001,78(6): 718-720.   
[4] Zhu H T, Zhang C Y, Tang Y M, et al. Novel synthesis and thermal conductivity of CuO nanofluid[J].The Journal Physical Chemistry C,2007,111(4): 1646-1650.   
[5] Gao J W,Zheng R T,Ohtani H,et al. Experimental investigation of heat conduction mechanisms in nanofluids. Clue on clustering[J]. Nano Letters,2009,9(12): 4128.   
[6] Eapen J, Rusconi R,Piazza R, et al. The classical nature of thermal conduction in nanofluids[J].Journal of Heat Transfer, 2010,132(10): 102402.   
[7] Maxwell JC.(A Treatise of Electricity and Magnetism, Vol. 1, Oxford Univ[J]. 1904.   
[8] Hamilton R L，Crosser O K. Thermal conductivity of heterogeneous two-componentsystems[J].Industrial Engineering Chemistry Fundamentals,1962,1(3): 187-191. suspensions [J]． Applied PhysicsLetters，2001，79(14): 2252-2254.   
[21] Yu W,Choi S U S.The role of interfacial layers in the enhanced thermal conductivity of nanofluids: a renovated Maxwell model[J].Journal of Nanoparticle Research，2003, 5(1-2): 167-171.   
[22] Yu W, Choi S U S. The role of interfacial layers in the [9] Davis R H. The effective thermal conductivity of a composite material with spherical inclusions[J]. International Journal of Thermophysics,1986,7(3): 609-620.   
[10] Keblinski P,Phillpot S R, Choi S U S, et al. Mechanisms of heat flow in suspensions of nano-sized particles (nanofluids)[J]. International Journal of Heat and Mass Transfer, 2002,45(4): 855-863.   
[11]PrasherR，Bhattacharya P,Phelan P E. Thermal conductivity of nanoscale colloidal solutions (nanofluids)[J]. Physical Review Letters, 2005, 94(2): 025901.   
[12] Evans W,Fish J,Keblinski P.Role of Brownian motion hydrodynamics on nanofluid thermal conductivity[J]. Applied Physics Letters,2006, 88(9): 093116.   
[13] Li C H, Peterson G P.Mixing effect on the enhancement of the effective thermal conductivity of nanoparticle suspensions (nanofluids)[J]. International Journal of Heat and Mass Transfer, 2007, 50(23): 4668-4677.   
[14] Ozerinc S,Kakac S,Yazicioglu A G. Enhanced thermal conductivityofnanofluids:astate-of-the-artreview[J]. Microfluidics and Nanofluidics,2010, 8(2): 145-170.   
[15] Xuan Y, Li Q, Hu W. Aggregation structure and thermal conductivity of nanofluids[J]. AIChE Journal, 2003,49(4): 1038-1043.   
[16] Hong K S, Hong TK, Yang H S. Thermal conductivity of Fe nanofluids depending on the cluster size of nanoparticles[J]. Applied Physics Letters,2006, 88(3): 031901.   
[17] Lee D, Kim J W, Kim B G. A new parameter to control heat transport in nanofluids: surface charge state of the particle in suspension[J]. The Journal of Physical Chemistry B,2006, 110(9): 4323-4328.   
[18] Prasher R, Phelan PE, Bhattacharya P. Effect of aggregation kinetics on the thermal conductivity of nanoscale colloidal solutions (nanofluid)[J]. Nano Letters, 2006, 6(7): 1529-1534. [19] Prasher R, Evans W, Meakin P, et al. Effect of aggregation on thermal conduction in colloidal nanofluids[J]. Applied Physics Letters,2006, 89(14): 143119.   
[20] Choi S U S,Zhang Z G, Yu W,et al. Anomalous thermal conductivity enhancement in nanotube   
enhanced thermal conductivity of nanofluids: a renovated Hamilton-Crosser model[J]. Journal of Nanoparticle Research, 2004, 6(4): 355-361.   
[23] Leong K C,Yang C,Murshed S M S.A model for the thermal conductivity of nanofluids-the efect of interfacial layer[J]. Journal of Nanoparticle Research,2006,8(2): 245-254. [24] Xie H, Fujii M, Zhang X. Effect of interfacial nanolayer on theeffectivethermalconductivityofnanoparticle-fluid mixture[J].International Journal of Heat and Mass Transfer, 2005,48(14): 2926-2932.   
[25]Rizvi IH, Jain A, Ghosh S K, et al. Mathematical modelling of thermal conductivity for nanofluid considering interfacial nano-layer[J].Heat and Mass transfer,2013,49(4): 595-600. [26] Gerardi C,Cory D,Buongiorno J,et al. Nuclear magnetic resonance-based study of ordered layering on the surface of alumina nanoparticles in water[J]. Applied Physics Letters, 2009, 95(25): 253104.   
[27]Kotia A,Borkakoti S,DevalP,et al.Review of interfacial layer's effect on thermal conductivity in nanofluid[J].Heat and Mass Transfer, 2017: 1-11.   
[28] Eapen J,Li J,Yip S.Probing transport mechanisms in nanofluids by molecular dynamics simulations[C]//Proceeding of the 18th National and 7th ISHMT-ASME heat and mass transfer conference,IIT Guwahati, India.2006.   
[29] LiL, Zhang Y,Ma H, et al.Molecular dynamics simulation of effect of liquid layering around the nanoparticle on the enhanced thermal conductivity of nanofluids[J]. Journal of Nanoparticle Research,2010,12(3): 811-821.   
[30]Liang Z,Tsai H L.Thermal conductivity of interfacial layers in nanofluids[J].Physical Review E,2011,83(4): O41602. [31]Babaei H，Keblinski P,Khodadadi JM.Equilibrium molecular dynamics determination of thermal conductivity for multi-component systems[J]. Journal of Applied Physics,2012, 112(5): 054310.   
[32]Cui W, Shen Z,Yang J, et al.Molecular dynamics simulation on the microstructure of absorption layer at the liquid-solid interface in nanofluids[J].International Communications in Heat and Mass Transfer,2016,71:75-85.   
[33] Paul J, Madhu A K, Jayadeep U B,et al.Liquid Layering and the Enhanced Thermal Conductivity of Ar-Cu Nanofluids:A Molecular Dynamics Study[C]//ASME 2016 Heat Transfer Summer Conference collocated with the ASME 2016 Fluids Engineering Division Summer Meeting and the ASME 2016 14th International Conference on Nanochannels,Microchannels, and Minichannels. American Society of Mechanical Engineers, 2016:V001T04A009-V001T04A009.   
[34]王楠，陈俊，安青松，等．纳米流体分散稳定性的分子动 力学研究初探[J]．工程热物理学报,2011,32(7):1107-1110. Wang Nan, Chen Jun,An Qingsong,et al. Elementary Research on the Dispersion and Stability of Nanofluids by Molecular Dynamics Simulations[J].Journal ofEngineering Thermo-physics,2011,32(7):1107-1110.