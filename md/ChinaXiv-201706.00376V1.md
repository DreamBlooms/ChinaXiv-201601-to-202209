# 非轴对称端壁改善涡轮叶栅流场研究

斯夏依 羌晓青 滕金芳 冯锦璋(上海交通大学航空航天学院，上海 200240)

摘要以 Pack B 涡轮平面叶栅为研究对象，采用非轴对称端壁造型方法，以减少涡轮叶栅总压损失为优化目标，进行了涡轮叶栅的非轴对称端壁优化设计，优化后的总压损失减小了 $1 1 . 8 3 \%$ 。通过对叶栅的下端壁以及上下端壁进行非轴对称造型并与原型光壁模型进行全叶高流场对比分析表明：非轴对称造型对几乎全叶高的总压损失分布产生影响，大幅减小了 $2 0 \%$ 和 $8 0 \%$ 叶高附近的总压损失，对气流角和下游涡强度的影响局限在近造型壁面侧的 $3 0 \%$ 叶高内。

关键词涡轮平面叶栅；非轴对称端壁；数值模拟精度；优化设计；流场分析中图分类号：V231.3 文献标识码：A 文章编号：0253-231X(2017)05-0970-08

# Investigation of Improving the Turbine Cascade Flow Using Non-axisymmetric Endwall Contouring>

SI Xia-YiQIANG Xiao-QingTENGXFang FENG Jin-Zhang

Abstract The optimization design of the non-axisymmetric endwal of turbine cascade was carried out with the turbine blade cascade PackB THe optimization goal is to reduce the total pressure loss of the turbine cascade. After optimization, the total pressure loss decreases by $1 1 . 8 3 \%$ .The following conclusions are obtained ow field comparison with three models, which are respectively cascade with non-axisymmetrigontouring in no/one/both side endwall. Non-axisymmetric endwall contouring on one side hayeefect on the total pressure loss distribution at almost the whole span of blades and greatly reducedthe total pressure loss near the 20% and 80% span. However,the influence of the outlet flow angle and intensity of downstream vortex is limited $\mathfrak { C } ^ { \mathfrak { \otimes } \mathfrak { \otimes } \mathcal { 7 } _ { 0 } }$ span near the contouring endwall. X

Key wordsturbine cascade; non-axisymmetric endwall; numerical simulation precision; optimization design; flow field analysis O

# 0引言

端壁损失在涡轮叶栅总损失中约占了三分之的比重[1]，是涡轮内部重要的损失源之一，主要产生于二次流以及端壁边界层内的黏性摩擦作用。端壁造型技术引入了沿周向 (非轴对称)和流向 (轴对称)的凸凹设计，非轴对称造型在20世纪90年代首次被Rose 等[2]验证能有效地降低涡轮中二次流损失，使端壁附近的压力场更均匀。非轴对称端壁造型基本原理是利用流线曲率来改变流道内部的压力梯度：凸的流线曲率能够加速流动，减小当地静压;凹的流线曲率能够延迟流动，增加当地静压。

现有的非轴对称造型方法可分为两类：第一类方法是在分析给定的流场细节的基础上，选择合适的造型结构。Harvey 和 Rose 等[3,4] 针对涡轮叶栅，在流场分析以及二次流机理研究的基础上生成了三维非轴对称轮毂造型，有效地减小了通道涡的尺度，弱化了对转涡。Dorfner 和 Voss 等[5]延续上述思路对3级压气机的第三级静子进行了非轴对称轮毂造型，有效地消除了静叶角区回流，同时在近失速工况下使级效率提高了 $1 \%$ 。第二类是采用优化的方法在对端壁复杂流动不能完全了解的情况下，借助优化方法找到符合流场的最优结构。Reising和Schiffer[6,7]采用自动多目标优化与三维RANS的联合求解器寻找高亚音速压气机动静叶栅的最优端壁几何形状，最终通过下端壁的处理手段，抑制了根部区域的角区分离，在设计工况以及非设计工况效率均有所提升。唐慧敏和罗华玲等[8,9]以ISIGHT 为平台对低速PackB 涡轮平面叶栅以及一级半高负荷轴流涡轮的上下端壁进行了非轴对称端壁的优化设计，减小了总压损失，验证了非轴对称端壁对通道内涡的生成和发展有抑制作用，也影响到涡的不稳定性。

在涡轮平面叶栅非轴对称造型的研究中，通常讨论非轴对称端壁对半叶高的流场的影响。本文以Fine/Design3D模块为平台，对低速PackB 涡轮平面叶栅进行非轴对称造型优化设计，分别对叶栅的上端壁和上下端壁进行非轴对称造型，根据三种方案在整个叶高范围内的流场差异，深入分析非轴对称端壁对涡轮叶栅流动的影响机理。

# 1几何模型和数值方法

本文选择的计算模型PackB 涡轮平面叶栅是Pratt&Whitney公司用于低压涡轮研究的低速试验叶栅，其在 2008 年发表了针对该叶栅进行的非轴对称端壁设计试验成果。叶栅的实验数据及详细参数见文献[10]，其中，叶高为 $0 . 2 0 3 \mathrm { ~ m ~ }$ ，轴向弦长为$0 . 0 7 5 4 \mathrm { ~ m ~ }$ ，进、出口气流角分别是 $3 5 ^ { \circ }$ 和-60赫数分别是0.073和0.111。

采用Fine/Autogrid对PackB 涡轮平面叶栅进行网格构造，经过对中径处截面参数的数值对比后确定了叶栅的B2B拓扑结构。改变径向的网格层数(见表1)，通过与实验出口气流角分布的对比，确定网格对计算精度的影响 (见图1)。

表1不同量级网格参数  
Table 1 Flow path nodes of different grid   

<html><body><table><tr><td>总网格数</td><td>径向网格点数</td></tr><tr><td>30</td><td>37</td></tr><tr><td>50</td><td>61</td></tr><tr><td>70</td><td>85 htt p</td></tr><tr><td>100</td><td>125</td></tr><tr><td>130</td><td>161</td></tr><tr><td>150</td><td>189</td></tr><tr><td>200</td><td>257</td></tr></table></body></html>

100万以下的网格，预测精度差，不仅没有捕捉到 $1 5 \%$ 叶高的气流角峰值，在中径处计算结果与试验值相比误差大。当网格数达到100万时，中径处的气流角计算结果与试验值吻合较好，但在 $1 5 \%$ 相对叶高处的气流角的预测仍存在一定偏差。当总网格数达到200万时，此时径向网格点数为257，该网格计算得到的气流角 (红色曲线)与试验值吻合良好，最大偏差仅为 $3 . 4 \% ( 1 1 \%$ 叶高位置处)。这一现象在前期的有关PackB的文献中并没有被发现。计算结果表明径向的网格疏密不仅会对近端壁的流场特征捕捉有决定作用，对中径处的流场细节的捕捉也会产生影响。

![](images/a8d4cd414bd1040f5f24a0ca704e80e1176b9fc22507367cc4a7608c79b7d271.jpg)  
厂 图1出口气流角径向分布对比 Fig.1 Comparison of angle spanwise distribution

![](images/b58234ed073f3f52f709ced2174c6f981dec218444a39435bf50dccb3658c274.jpg)  
图2不同湍流模型与试验的吸力面极限流线 Fig Suction surface streamline of different turbulent model and experiment result

根据参考文献[10]中试验得到的吸力面油流显示，对比不同湍流模型采用上述网格计算得到的吸力面极限流线 (见图2)。试验中吸力面有较大的回流，开始于 $6 0 \%$ 左右弦长位置，主流区的回流与端壁的角区分离相互作用形成较大的螺旋状，产生掺混导致下游的损失增加，在之后的总压损失分析中也能验证。其中 $k { - } \varepsilon$ 带壁面函数 (End Wall Function)模型计算得到的吸力面回流、涡尺度与试验最吻合。

因此，计算采用200万网格拓扑结构和 $k { - } \varepsilon$ 带壁面函数湍流模型， $y ^ { + }$ 值小于3，符合湍流模型计算要求。

# 2非轴对称端壁优化

本文针对PackB涡轮平面叶栅的一侧端壁进

行了非轴对称端壁优化设计 (采用非轴对称造型的一侧记为下端壁，光壁的另一侧记为上端壁)，优化工具为Fine/Design3D 模块，优化流程如图3所示。

# 2.1参数化拟合

![](images/80a6cc39f35c5f7429c1bf2190d3fa8825cab62564a929ced802a91cb7d8756f.jpg)  
图3非轴对称端壁优化流程 Fig.3 Optimization process

本文的目的是通过端壁造型控制二次流以达到减小损失的目的，造型的方法如图4所示，在端壁沿流向上截取5条切线，每条切线上按等距选取6个自由控制点生成PackB 涡轮叶栅的非轴对称端壁。非轴对称端壁造型范围略超出了叶片前尾缘切线1与切线5上的控制点高度取值保持优化自变量数为24，通过Bezier拟合方式造型形成非轴对称端壁曲面。

# 2.2多目标遗传算法优化

Fine/Design3D的优化过程是基于人工神经网络、遗传算法和近似函数技术展开的。优化前采用Database_Generation模块生成数据库，采用拉丁超立方离散取样方式对参数化后端壁面上的24个优化自变量在 $1 0 \%$ 叶高 $( \pm 0 . 0 1 \mathrm { m } )$ 范围内生成60个样本，保证生成的样本具有全局代表性。优化过程应用Op-timization模块，采用基于人工神经网络的NSGA-II多目标遗传算法寻找目标函数的最优值。本文的优化目标为：在流量基本不变的基础上，减少涡轮叶栅总压损失。为此，设置了3个罚函数（ObjectiveFunction)，具体条件为：流量越接近 $1 2 3 \mathrm { k g / s }$ ，总压损失系数越接近0.05，罚函数越小；总压损失系数$< 0 . 0 8$ 。罚函数被定义为：

![](images/a77e94586ba1364a0c278c81cf2818f1c7c43e4868e892c07307ed7ecc2f1982.jpg)  
图4非轴对称端壁造型点分布  
Fig.5 Non-axisymmetric endwall contouring comparison

$$
O F = \sum P _ { i } = P _ { \dot { m } } + P _ { \mathrm { l o s s 1 } } + P _ { \mathrm { l o s s 2 } } ,
$$

$$
P _ { i } = w \left( { \frac { Q _ { \mathrm { i m p } } - Q } { Q _ { \mathrm { r e f } } } } \right) ^ { k }
$$

其中,输入值 $Q _ { \mathrm { i m p } }$ 和参考值 $Q _ { \mathrm { r e f } }$ 设为相同； $w$ 是比重 (PenaltyWeight)，通过增加总压损失系数的比重因子，使其在优化过程中具有优先性；指数 $k$ 为2。经过20多次迭代，优化结果基本收敛。

# 2.3非轴对称端壁优化结果

菜用上述优化流程得到的非轴对称端壁造型(见图 5(a)）与参考文献[8]，[10]中优化结果（见图5(b)、(c)）几何特征基本一致，高度差云图如图6所示。

![](images/af979cb3c8c6e5238377c2edf976b015767c891e026dcf4d97021d0a707be364.jpg)  
图5非轴对称端壁造型对比

![](images/6e1f9b1da116872a5e40c2deef27ffd23a67f3ff1f0be1f7129fe6fdc40745b7.jpg)  
Fig.4 Non-axisymmetric endwall contouring control points   
图6优化前后端壁高度差云图  
Fig.6 Non-axisymmetric endwall contouring sketch

# 3结果分析

将优化后的非轴对称造型分别应用在叶栅的下端壁(Opt1）和上下端壁(Opt2)，并与光壁模型（da-tum）做对比。三个模型的流场参数如表2所示,下端壁加入非轴对称造型后流量变化不大仅减小了$0 . 7 3 \%$ ，总压损失减小了 $1 1 . 8 3 \%$ ，二次流动能系数$C _ { \mathrm { S K E } }$ 减小了 $1 3 . 3 9 \%$ ；上下端壁同时采用非轴对称造型时，流量减小了 $0 . 9 8 \%$ ，总压损失减小了 $1 3 . 3 2 \%$ 5二次流动能系数减小了 $1 4 . 5 6 \%$ 。采用相同几何模型的文献[8]，[10]对平面叶栅的两侧端壁同时采用非轴对称造型，总压损失分别减小了 $1 2 . 9 6 \%$ 和 $9 . 6 \%$ 5相比而言本文的优化效果明显，下文将对优化前后的流场进行详细的分析。

表2三种模型的流场参数  
Table 2 Flow parameters of three models   

<html><body><table><tr><td>方案</td><td>m/(kg/s)</td><td></td><td>△w/%</td><td>CsKE</td><td>△CsKE/%</td></tr><tr><td>Datum</td><td>124.66</td><td>0.07537</td><td>0</td><td>0.00335126</td><td>0</td></tr><tr><td>Opt1</td><td>123.75</td><td>0.066456</td><td>11.83</td><td>0.00290255</td><td>13.39</td></tr><tr><td>Opt2</td><td>123.44</td><td>0.065332</td><td>13.32</td><td>0.00286324</td><td>14.56X</td></tr></table></body></html>

总压损失和二次流动能系数的定义如下

$$
\omega = \frac { T P _ { 1 } - T P _ { 2 } } { T P _ { 2 } - S P _ { 2 } } , \quad C _ { \mathrm { S K E } } = \frac { 0 . 5 \rho \left( \beta _ { \mathrm { s e c } } ^ { 2 } \right) \left( \beta _ { \mathrm { s e c } } ^ { 2 } \right) } { \mathcal { N } P _ { 2 } ^ { 1 } \cdot \ b { \mathrm { s } } ^ { 2 } - S P _ { 2 } }
$$

其中，1和2分别表示叶栅进口和出口（ $1 4 0 \%$ 轴向弦长位置 $B _ { x }$ ， $\boldsymbol { v } _ { \mathrm { s e c } }$ 和 $u _ { \mathrm { s e c } }$ 表示二次流速度分量。

# 3.1气动参数分析

图7为总压损失系数沿径向分布。由图7可以观察到采用下端壁非轴对称造型后（opt1）总压损失减小最明显的位置是 $1 5 \% { \sim } 3 0 \%$ 叶高以及 $8 0 \% \sim 9 0 \%$ 叶高。再增加上端壁的非轴对称造型时，总压损失减小不明显，主要分布在 $7 0 \% \sim 8 5 \%$ 叶高。而叶片通道中主流区吸力面的回流和端壁角区分离的相互作用的叶高也在 $1 0 \% { \sim } 3 0 \%$ 和 $7 0 \% \sim 9 0 \%$ 范围内(见图2(c))。由此可见 $1 4 0 \%$ 轴向弦长位置损失的主要来源就是回流和角区分离相互作用带来的能量掺混。

图8为叶片出口气流角沿径向的分布。叶片的几何出气角是 $6 0 ^ { \circ }$ ，图8中下端壁采用非轴造型与光壁的模型相比，在 $5 \%$ 叶高内折转角增加， $1 5 \% \sim 2 3 \%$ 叶高内落后角减小，而 $3 0 \%$ 叶高以上范围的出口气流角几乎没有变化。总的来说，非轴对称端壁造型使得出口气流角在主流区分布更加均匀，平均气流角从$5 5 . 4 5 ^ { \circ }$ 增大到了 $5 6 . 0 9 ^ { \circ }$ ，落后角减小了约 $0 . 6 4 ^ { \circ }$ 。再增加上端壁的非轴对称造型时，气流角在顶部的变化趋势一致， $9 5 \%$ 叶高以上折转角增加， $7 7 \% \sim 8 5 \%$ 叶高内落后角减小。

![](images/0cdda9dadea38a58a5343029e82c8e746b86307b47ba614f27108f5c7d12e0f8.jpg)  
图7总压损失系数沿径向分布 $( 1 . 4 { \cal B } _ { x } )$

Total pressure loss coefficient spanwise distribution $( 1 . 4 B _ { x } )$ （204

![](images/2dc0abedd6fd7289995e57e54ea3b8bc1f5b95618e06b8a39272e150ac14f93b.jpg)  
图8出口气流角沿径向分布 $( 1 . 4 B _ { x }$ ）Fig.8 Outflow angle spanwise distribution $( 1 . 4 { \cal B } _ { x } )$

在采用单侧的非轴对称造型后，总压损失在上叶高附近也有变化，而气流角的改变只集中在近壁面 $3 0 \%$ 叶高以内。表明气流角和总压损失发生改变的机理不一样，下文将进行深入的探讨。

对 $1 4 0 \%$ 轴向弦长位置的总压损失分布进行分析，如图9所示。下端壁非轴对称造型后总压损失系数有所减小，主要体现在 $5 \%$ 叶高内的近下端壁 (图中红色标示区域)的高损失区1在造型后消失， $2 0 \%$ 、 $8 0 \%$ 叶高附近的两个高损失区2的损失同时减小，后者对应了图7中的损失峰值减小。但$9 5 \%$ 叶高以上的近上端壁的高损失区1与造型前没有改变，再增加上端壁的非轴对称造型后，促端壁的高损失区1消失。结果表明，单侧的非轴对称造型会对高损失区2产生影响，减小损朱；而高损失区1只在该侧有非轴造型时才会减乐。

![](images/e0379305f812a98440c2c743d97a390ba7ea3b8fe6b375d3a63674caebcbcb25.jpg)  
图9总压损失系数云图 $( 1 . 4 { \cal B } _ { x } )$ Fig.9 Total pressure loss coefficient distribution

# 3.2壁面流谱分析

通过流线的分析发现高损失区1来源于上游叶片通道中的吸力面壁角涡，图10(a)中再附线AL1、AL2为壁角涡对吸力面流线的影响形式。分离线SL1和 SL2分别是上下端壁的角区分离，F1和F2分别是角区分离和回流相互作用形成的螺旋点。当下端壁采用非轴对称端壁时，回流位置从光壁算例的$7 5 \%$ 弦长后移到 $8 0 \%$ 弦长，回流区域减小；同时，回流与角区分离相互作用形成的螺旋状涡的影响范围由约 $1 0 \%$ 叶高减小为约 $3 . 9 \%$ 叶高，螺旋点的位置基本不变为 $1 2 . 9 \%$ 和 $8 7 . 4 \%$ 叶高，角区分离的起始点也几乎没有变化，都是从根部的 $2 1 . 2 \%$ 弦长位置开始。再增加上端壁的非轴对称造型后，吸力面的涡拓扑结构变化不大。

螺旋状涡和图9中的高损失区2的相对叶高位置基本相同，在下端壁采用非轴对称造型后，两个螺旋状涡和两个高损失区2同时减小，进一步验证了损失主要来源于吸力面尾缘回流和角区分离相互作用形成的螺旋状涡的能量掺混过程。在PackB涡轮平面叶栅中，单侧采用非轴对称端壁通过减弱上下端壁两侧的角区分离和回流的相互作用达到降低总压损失的目的，而单侧端壁造型会对几平整个叶高的流动产生影响的机理将在下文深入分析。

![](images/f290c3ad05e9defb58f18708e28e1713cbc2155ffc64308782fbd4fbcccf8362.jpg)  
图10叶片吸力面极限流线 Fig.1O Suction surface streamline

由于优化后的非轴对称端壁造型表现出的特征有：叶片通道前半段的吸力面下凹，压力面上凸，通道后半段压力面下凹，吸力面上凸。端壁造型对近壁面的静压及流线分布(见图11)有直接的影响。造型前后近壁面流线的前缘鞍点位置没有改变，但马蹄涡吸力面分支和压力面分支汇合后形成的再附线距离壁面更近 (如图11中标红色区域所示)，即吸力面分离的周向尺度更小。这是因为端壁的非轴对称造型减小了通道前半段的压力梯度，增大了后半段的压力梯度，改变了马蹄涡分支的空间走向，从而影响通道涡的发展。

![](images/103b3e2db91d169206f467f401235fc88e7c4a779b07c6ba94cca0aa8bd49928.jpg)  
Fig.11 Endwall streamline and static pressiredistribution

# 3.3涡结构分析

图12、13分别是下端壁非轴对称造型 $1 3 \%$ $2 5 \%$ 轴向弦长位置流线投影和总压分布图 (选取半高进行分析)。在 $1 3 \%$ 轴向弦长截面，光壁叶栅的通道内已经形成了一定强度的旋涡，而采用非轴对称端壁造型后在该截面位置旋涡才刚刚产生未完全发展，该现象表明非轴对称端壁造型能有效地延迟旋涡在流向的形成位置。在 $2 5 \%$ 轴向弦长截面，非轴对称端壁的通道低压区和下通道涡都被有效限制在端壁下凹区域，与光壁原型相比螺旋点后移。

![](images/3105ce2aeac1dadc8fac62ed266a9355baa1f288af101a7727418482d6403a38.jpg)  
图12 $0 . 1 3 B _ { x }$ 的总压分布和周向流线 (半叶高) Fig.12 Circumferential streamline and total pressure distribution( $0 . 1 3 B _ { x }$ ， $5 0 \%$ span)

在涡轮叶片通道中，通道涡在叶栅的各涡系中占主导地位，影响通道内二次流发展和质量转移机制。当PackB的下端壁采用非轴对称造型时，通过壁面的曲率改变了近壁面压力梯度，进而改变了通道涡的周向位置并抑制其发展；通道涡强度和位置的变化影响了质量迁移使叶片尾缘分离的位置后移，减弱回流，从而减小了与角区分离相互作用后产生的螺旋状涡的强度和尺度，使总压损失减小。

![](images/5581656fe31fca3f5fa252bda1c5662d60046e7f551c5b24ed37d15e0f941b81.jpg)  
图11近壁面静压和流线分布图  
图13 $0 . 2 5 B _ { x }$ 的总压分布和周向流线 (半叶高) Fig.13 Circumferential streamline and total pressure distribution ( $0 . 2 5 B _ { x }$ ， $5 0 \%$ span)

采用 $\lambda _ { 2 }$ 准则衡量 $9 0 \%$ 和 $1 4 0 \%$ 轴向弦长位置的涡的分布，如图14、图15所示。选择 $9 0 \%$ 轴向弦长位置是为了排除尾缘脱落涡的影响。由图14可见，在靠近吸力面角区有两个反向涡，其中1和 $1 ^ { \prime }$ 是通道涡，2和 $2 ^ { \prime }$ 是壁角涡。当下端壁采用非轴对称造型时，下通道涡1的尺度减小，位置略向吸力面靠近，下壁角涡2尺度增大但位置不变，上通道的涡。轴对称造型时，其附近涡的尺度也减小。

![](images/99ee1eb84adc3342135643ec7cf0ffd0462ba19897c11840b48658b25ac02e55.jpg)  
图 $1 4 \lambda _ { 2 }$ 准则对比( $9 0 \%$ 轴向弦长位置)Fig. 14 $\lambda _ { 2 }$ criterion distribution $( 0 . 9 B _ { x } )$

![](images/0bff15ab2d97fd9a9227922252d914ea76d2c50e19f6ce290dd7b6aaa220ca93.jpg)  
图15 $\lambda _ { 2 }$ 准则对比( $1 4 0 \%$ 轴向弦长位置)Fig. 15 $\lambda _ { 2 }$ criterion distribution $( \mathbf { q . 4 } B _ { x } )$ ）

位置和尺度基本不变。壁角涡的尺度较小，但会影响根部的出口气流角[12]。因此，图8中 $5 \%$ 叶高以下出口气流角的过偏转增大的原因是壁角涡2的增大；通道涡在向下游发展的过程中有向吸力面和主流区发展的趋势，在 $1 5 \% \sim 2 3 \%$ 叶高范围内的落后角减小的原因是通道涡1的减小； $3 0 \%$ 叶高以上涡强度和气流角分布均不变。再增加上端壁的非轴对称造型后，涡和气流角变化趋势一致。

在 $1 4 0 \%$ 轴向弦长位置，通道涡在尾缘脱落涡的相互作用下，分别在上下端壁附近形成两对较强的反向涡。下端壁采用非轴对称造型时，对应图9中高损失区2的损失减小的同时该区域的涡的结构也有所改变，尺度减小，涡的尺度受非轴对称端壁影响更明显的区域在近下端壁 $2 5 \%$ 叶高范围内，而 $7 5 \%$ 叶高以上的涡分布几乎没有变化。再采用上端壁的非

单侧的非轴对称端壁通过对通道涡的作用能对几乎全叶高的流场造成影响，减小了总压损失，但对气流角分布的影响仅在 $3 0 \%$ 叶高范围内。造成该差别的原因是其影响机理的不同。总压损失在整个叶高范围内都有所减小的原因是，下通道涡被抑制，导致流量重新分配后回流减小，从而减弱了回流和角区分离相互作用形成的两个螺旋状涡的强度和大小，减弱了高损失区2的损失。气流角的变化与 $\lambda _ { 2 }$ 准则的变化较为一致，仅在非轴对称端壁附近才有直接的影响， $5 \%$ 叶高内因为壁角涡增强而导致转折角增大， $1 5 \% \sim 2 3 \%$ 叶高因为通道涡减弱而使落后角减小。总压损失在近壁面 $5 \%$ 叶高内也因为上游壁角涡的增大改变了尾缘的涡结构分布而减小。从文中的分析发现，总压损失较高的区域和涡尺度较大的区域并不一致，在下端壁采用非轴对称造型时，中径以上叶高的总压损失也有较大的减小而涡的结构和大小几乎不变。在之后的研究中将针对损失和涡的形式、大小之间的相互作用关系进行深入的研究分析。

# 4结论

1）通过与PackB 涡轮平面叶栅的试验数据做对比，发现了数值模拟精度对径向网格点数具有依赖性。径向网格疏密不仅会对近根部的流场特征捕捉有决定作用，对中径处的流场细节的捕捉也会产生影响。

2）采用集成了参数化拟合、流场分析、样本数据库建立以及基于人工神经网络的多目标遗传优化算法等模块的自动寻优流程，对PackB 涡轮平面叶栅一侧端壁进行非轴对称端壁优化设计，使叶栅总压损失减小了 $1 1 . 8 3 \%$ ，二次流动能系数减小了$1 3 . 3 9 \%$ 。

3)通过对光壁、下端壁非轴对称和上下端壁非轴对称造型三个模型的详细分析发现：上下端壁非轴对称造型可以减小 $9 5 \%$ 叶高以上近上端壁的高损失区，而只有下端壁进行非轴对称造型时通道涡和壁角涡则不受影响；下端壁造型时凡乎对全叶高的总压损失有影响，尤其表现在减小！ $3 0 \%$ 和 $8 0 \%$ 叶高附近的损失峰值；由于下端壁非轴对称造型抑制了下通道涡，减弱了主流区回流，减小了与上下角区分离的掺混，从而使得总压损失减小；非轴对称造型后，下通道涡尺度减小，下壁角涡尺度增大，气流角的变化趋势与涡结构的改变较为一致。

# 参考文献

[1]Denton J D.Loss Mechanism in Turbomachines [R]. ASMEPaper,93-GT-435,1993   
[2]Rose M G.Non-axisymmetric Endwall Profling in the HP NGV's of an Axial Flow Gas Turbine [R].ASME Paper, 94-GT-249, 1994   
[3] Harvey N W,Rose M G,Taylor M D,et al. Nonaxisymmetric Turbine End Wall Design -Part I: ThreeDimensional Linear Design System [J]. Journal of Turbomachinery. 2000,122(2): 278-285   
[4] Hartland J C,Gregory-Smith D G,Harvey N W,et al. Non-axisymmetric Turbine End Wall Design: Part II - Experimental Validation [J]. Journal of Turbomachinery. 2000,122(2): 286-293   
[5]Dorfner C，Nicke E,Voss C.Axis-Asymmetric Profiled Endwall Design by Using Multi-objective Optimization Linked With 3D RANS-Flow-Simulations [R].ASME Paper GT2007-27268,2007   
[6] Reising S,Schiffer HP.Non-Axisymmetric End Wall Profiling in Transonic Compressors - Part I: Improving the Static Pressure Recovery at Off-Design Conditions by Sequential Hub and Shroud End Wall Profiling [R].ASME Paper GT2009-59133,2009   
[7] Reising 8 Schiffer H P. Non-Axisymmetric End Wall Profiln in Transonic Compressors - Part II:Design Study of a Transonic Compressor Rotor Using Non-Axisymmetric NEnd Walls - Optimization Strategies and Performance [R]. ASME Paper GT2009-59134,2009   
[8]唐慧敏，刘帅强，罗华玲．涡轮平面叶栅非轴对称端壁优化 设计[J].航空动力学报，2015,30(03)：707-713 TANG Huimin,LIU Shuaiqiang,LUO Hualing,et al. Optimal Design of Profiled endwall for Turbine Cascade. Journal of Aerospace Power, 2015,30(03):707-713   
[9] TANG Huimin,LIU Shuaiqiang,LUO Hualing,et al. Unsteady Effects of Profiled Endwalls on a 1.5 Stage Axial Turbine [R].ASME Paper GT2015-43871, 2015   
[10] Knezevici D C,Sjolander S A，Praisner T J,et al. MeasurementsCof Secondary Losses in a High-Lift FrontLoaded Turbine Cascade with the Implementation of NonAxisymmetric Endwall Contouring [R]. ASME GT2009- 5967 2009   
[11]Wang HP,Olson SJ,Goldstein RJ,et al.Flow VisualIzation ina Linear Turbine Cascade of High Performance Turbine Blade [R]. ASME Paper, 95-GT-7, 1995   
[12] Gregory-Smith D G,Graves C P. Secondary Flows and Losses ina Turbine Cascade [R].Durham Univ (England), Dept of Engineering,1983