# 跨音速离心叶轮叶尖区域流动的数值分析

赵会晶 王志恒席光(西安交通大学能源与动力工程学院，西安710049)

摘要本文以压比为6.1的跨音速离心叶轮为研究对象，采用定常和非定常数值模拟分析了叶尖区域激波与泄漏涡的相互作用和泄漏涡的非定常特征。随着流量减小，激波与泄漏涡的相互作用增强，最终导致泄漏涡破裂。小流量下泄漏涡的破裂引起叶片载荷的变化，叶片载荷的变化反过来影响泄漏涡的强弱，如此形成一个非定常循环过程。单通道模拟得出非定常流动的频率为0.668 BPF,双通道和三通道模拟得到的频率则为0.88 BPF。但三种模型得出的非定常机理相同。

关键词激波；泄漏涡；破碎；叶片载荷中图分类号：TK123 文献标识码：A

文章编号：0253-231X(2017)03-0515-07

# Numerical Analysis of Flow Structures in the Tip Region of a Transonic Centrifugal Impeller

ZHAO Hui-JingWANG Zhi-HengXI Guang (School of Energy and Power Engineering,Xi'an Jiaotong University,Xi'an 710049,China)

Abstract In this paper,the transonic centrifugal impeller with a pressure ration of 6.1 is choose as the study object.The unsteady characteristics of tip leakage vortex and the interaction between shock and tip leakage vortex in the tip region are investigated by steady and unsteady numerical simulation. The results shows that,the interaction between shock and tip leakage vortex becomes stronger as the mass flow rate decreases,and finally the tip leakage vortex breaks down. At small mass flow rate, the broken-downed tip leakage vortex induces the variation of blade loadings. In turn,the changed blade loadings will alter the intensity of tip leakage vortex. Such alternative behavior finally results in the periodic process. The single-passage numerical simulation shows that the oscilation frequency of unsteady fow is 0.668 BPF,and the two-passage and three-passage simulations indicate the oscillation frequency is 0.88 BPF,but the three numerical models shows the same unsteady fow mechanism. Key wordsshock; tip leakage vortex; break down; blade loading

# 0前言

为了增加燃气轮机、涡轮增压器和发动机的输出功率，离心压气机的单级压比越来越高。另外压比和效率的增加也是为了满足节能减排的需求。当叶轮的外径受到限制时，为了增加压比只能提高叶轮转速。随着转速的提高，当叶轮的叶尖马赫数大于1时，产生激波。在跨音速离心叶轮中，激波的存在使叶尖区域流场更复杂。

一方面叶尖区域的激波/泄漏涡相互作用产生额外的损失。Krain等[1实验测量了一个跨音速离心叶轮的内部流场，发现激波/泄漏涡的相互作用增加了堵塞和损失。Ibaraki等[2]采用详细的数值模拟和先进的流动可视化技术对一个跨音速离心叶轮进行了研究，得出在叶轮的前缘附近，泄漏涡及激波/泄漏涡相互作用产生了总压损失。另一方面，激波/泄漏涡/边界层相互作用在叶尖区域产生的堵塞限制压气机的稳定运行工况。Hazby 等[3 研究了一个跨音速离心压气机在不同工况下的内部流场，指出激波/泄漏涡/边界层相互作用产生的堵塞在近失速工况下溢出相邻叶片前缘。随着质量流量减小，激波/泄漏涡的相互作用增强，产生的堵塞增加。由于堵塞会改变叶轮的来流条件，从而可能引发压气机的失速[4,5]。

然而，以上定常分析并不能完全解释叶尖区域复杂的流动现象。叶尖区域流动的非定常特性对压气机的噪声、震动和损失有着重要作用。并且大量研究表明，在近失速工况下，叶尖区域的非定常流动现象是引起失速的一个重要因素。Ce等[在失速开始时对一个亚音速离心叶轮进行了数值模拟，由于泄漏涡及泄漏涡/主流的相互作用，叶片的 $9 0 \%$ 叶高处出现明显的压力波动。泄漏涡的强度发生周期性变化，并且在泄漏流/主流相互作用的影响下发生周期性脱落。通过实验测量机匣表面的动态压力，Schleer等[7]指出近失速工况下，在叶片前缘附近沿着泄漏涡轨迹压力出现强烈波动。进一步，Huang等[8通过数值模拟发现近失速工况下泄漏涡的波动频率为0.42倍叶片通过频率。在近失速工况下，泄漏流与叶片压力面附近的回流相互作用，形成一个涡，从而引发离心压气机中的流动非稳定性[9]。然而,Bousquet等[10] 则得出在离心叶轮中泄漏流和二次流产生一个低速区，在近失速工况下，位于低速区与主流的交界面上的剪切层变得不稳定，并引发周期性分离涡脱落。这一非定常现象的频率与叶片通过频率无关。在跨音速离心压气机中，BUFFAZa等[11]通过实验测量了机匣上的动态压力，在近失速工况下，叶轮前缘附近沿着泄漏涡轨迹压力以0.4倍叶片通过频率发生波动。但文中并没有指出压力波动机理。而且目前有关跨音速离心压气机中叶尖区流动的非定常研究较少，本文以一跨音速离心叶轮为研究对象,结合定常和非定常模拟，讨论近失速工况下叶尖区域非定常流动现象，解释其非定常机理。希望为叶尖区流动控制提供参考。

算中先后采用了单通道、双通道和三通道模型。叶轮转过一个主叶片通道布置40个时间步，每个时间步迭代10次。在TURBOGRID中生成叶轮结构化网格，利用ICEM生成无叶扩压器结构化网格。叶轮网格模型如图2所示。通过网格无关性检验，在平衡计算精度和计算资源的基础上，整个计算域的网格约为 $9 . 2 \times 1 0 ^ { 5 }$ 。网格分布如图2所示，轴向、周向、展向网格点数分别为150、50、73。叶顶间隙内布置18个网格节点。壁面第一层网格距离大约为 8$\mu \mathrm { m } , y ^ { + }$ 小于5。

![](images/6ba77e9ac3b78de38600a573a24748a31702575e47a5a353d2913c54f9d9cdcf.jpg)  
图1计算模型

# 1研究对象及方法

# 1.1 研究对象

本文以Krain等设计跨音速离心叶轮为研究对象，由于其公开的实验数据和几何模型数据而被广泛研究[12,13]。叶轮基本参数如表1所示。为了减小扩压器对叶轮的影响，叶轮后接等面积无叶扩压器，计算模型如图1所示。

# 1.2数值方法

本文数值计算采用ANSYSCFX求解三维定常和非定常雷诺平均N-S方程组，湍流模型使用SST两方程模型。定常计算采用单通道模型，非定常计

# 表1叶轮基本参数

Table1 thebasicparametersoftheimpeller   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>设计转速/(r/min)</td><td>50000</td></tr><tr><td>设计流量/(kg/s)</td><td>2.55</td></tr><tr><td>叶轮进口叶尖直径Dit/mm</td><td>156</td></tr><tr><td>叶轮进口轮毂直径D1h/mm</td><td>60</td></tr><tr><td>叶轮出口直径D2/mm</td><td>224</td></tr><tr><td>叶轮出口宽度b2/mm</td><td>10.2</td></tr><tr><td>叶片数</td><td>13/13</td></tr></table></body></html>

![](images/f9712f2efe0f3952408328892f1ad0954d6b1e5be8b3d893d8ee3d6714a868bb.jpg)  
Fig.1 Computation model   
图2网格模型  
Fig.2 The mesh for the computational model

进口给定总温、总压和速度方向，出口在大流 量下给定静压，小流量下给定质量流量。固体壁面 均设无滑移，绝热边界条件。收敛判据为均方根残 差在小于 $1 0 ^ { - 5 }$ ，进、出口质量流量差小于 $0 . 1 \%$ ，效 率变化小于 $0 . 0 1 \%$ 。

# 1.3实验验证

在德国 DLR 实验台上对此叶轮进行了总体性能和流场测量，并且实验数据是在文献中公开发表的。对于本文所研究的叶轮，在质量流量为 $2 . 6 5 \mathrm { k g / s }$ 时开始出现非定常现象。并且由于本文主要研究失速前的非定常流动，并不关注失速本身，所以只在$2 . 5 5 { \sim } 2 . 6 5 \mathrm { k g / s }$ 取3个工况点进行非定常分析。为了验证数值方法的准确性，数值计算的总体性能和设计工况下的流场与实验结果进行了对比。如图3所示，所用的数值方法所预测的稳定工况范围和性能曲线趋势和实验吻合较好。只是预测的总压比和等熵效率值偏高，这可能是没有考虑实验时的流场分布周向不均匀性等因素引起的。图4和图5分别对设计工况下 $9 0 \%$ 叶高和叶轮出口截面的马赫数分布

![](images/725f715225ec69fcd404f5a5c6d5ec4c30b5fd73d27d9818c48d5da358eedd04.jpg)  
图3叶轮总体性能  
Fig.3 Overall performance for the impeller

128 43 (a)数值模拟

![](images/4dbcf1975067693ab0c8391b863ae72475986ca71fe18b9692305391e213f6ba.jpg)  
图4 $9 8 \%$ 叶高马赫数分布Fig.4 Mach number distribution at $9 5 \%$ span

![](images/c517caf22f7cb1f597ed8a54350237761b2163020b3621087ba1f2b61c60c58b.jpg)  
图5叶轮出口截面马赫数分布 Fig.5 Mach number distribution at the impeller outlet

与实验进行了对比，实验所得激波在吸力面附近向下游弯曲，而数值计算所得激波垂直于吸力面。这可能是数值模拟预测的流动分离过大引起的。总体来说，数值模拟结果和实验吻合良好。

# 2 结果与讨论

# 2.1叶尖区域流动的定常分析

在进行非定常分析之前，本文首先通过定常计算定性分析叶尖区域流场随工况的变化。跨音速离心叶轮叶尖区域的流场主要由激波和泄漏涡及其相互作用主导，所以本文重点关注激波/泄漏涡的相互作用。为了分析泄漏涡结构变化，定义标准涡为

$$
H _ { n } = \frac { \overline { { \zeta } } \cdot \overline { { w } } } { \left| \overline { { \zeta } } \right| \left| \overline { { w } } \right| }
$$

其中， $\overline { { \zeta } }$ 为绝对涡量， $\overline { { w } }$ 为相对速度矢量， $H _ { n }$ 表示绝对涡矢量与相对速度矢量夹角的余弦值。当涡矢量方向和相对速度方向相同时， $H _ { n }$ 为 $+ 1$ ，当两者方向相反时， $H _ { n }$ 为 $^ { - 1 }$ 。 $H _ { n }$ 的绝对值为1时表示涡绕流线的缠绕最强。如图6所示，黑色等值线表示$9 8 \%$ 叶高的马赫数分布，在叶片前缘附近存在脱体激波。泄漏流线从 $0 \sim 2 0 \%$ 弦长位置释放，其颜色表示标准涡大小。在近堵塞工况下，激波/泄漏涡相互作用对泄漏涡几乎没有影响，在激波之后，泄漏涡仍然保持旋绕状态，其标准涡值仍保持为-1。随着流量减小，激波向上游移动，激波/泄漏涡相互作用增强。在质量流量为 $2 . 7 \mathrm { k g / s }$ 时，激波之后泄漏涡旋绕强度降低，标准涡值降低，但是仍为负值，表示泄漏涡并没有破碎。继续减小流量，泄漏涡将发生破碎。在质量流量为 $2 . 5 5 ~ \mathrm { k g / s }$ 和 $2 . 4 ~ \mathrm { k g / s }$ 时，激波之后泄漏涡的标准涡值变为正值，甚至达到 $+ 1$ 。泄漏涡发生泡状破碎。泄漏涡发生破碎主要由三个因素决定：泄漏涡强度，激波强度和激波/泄漏涡的夹角。在图6中，各工况下激波强度及激波/泄漏涡之间的夹角变化较小，但随着流量减小，叶片最大载荷向前缘移动，使泄漏涡强度增加。并且激波之前泄漏涡与主流能量交换的时间降低，泄漏涡的轴向速度降低，在激波作用下更容易发生破碎。泄漏涡的破碎在激波之后产生低速区，甚至回流，造成堵塞，对压气机的稳定形成威胁。为了更深刻的解释泄漏涡破碎对叶尖区流场的影响，下面将进行非定常分析。

![](images/fe9e61cefb598713e3f819e0fac50f84baaca4d38622a21fe594dd719273cee9.jpg)  
图6泄漏流的标准涡分布和 $9 8 \%$ 叶高的马赫数分布Fig.6 The distributions of $H _ { n }$ and Mach number at $9 8 \%$ span

# 2.2叶尖区域流动的非定常分析

为了展示非定常波动在叶轮中的分布，图7给出了质量流量为 $2 . 6 ~ \mathrm { k g / s }$ 时静压的相对标准差 (RSD)在叶轮中的分布。相对标准差定义为：

$$
\sigma _ { i j } = \frac { \sqrt { \displaystyle { \frac { 1 } { N } \sum _ { j = 1 } ^ { N } ( P _ { i j } - \overline { { P _ { j } } } ) ^ { 2 } } } } { \overline { { P _ { i } } } }
$$

其中， $i$ 表示叶片内节点， $j$ 表示时间步， $N$ 表示总的时间步数。如图7所示，流动的非定常性主要发生在 $7 0 \%$ 叶高到机匣之间，在叶尖区域最强。在S1流面上，最强的非定常性主要分布在激波面和激波/泄漏涡相互作用区域。由此可以推断此非定性与激波和泄漏涡有关。

![](images/0aeefb656a25dee7b8e8de640b2e4a4184c8e0000710326465757d79e680c4dc.jpg)  
图7叶轮中静压标准差分布 Fig.7 RSD distribution in the impeller

为了分析在相对坐标系下此非定常现象的频率特性，如图8所示在S1流面上共设定了8个监测点，通过傅里叶变换，在8个监测点均存在一个0.668倍的主叶片通过频率 (BPF)，在激波/泄漏涡相互作用位置波动幅值最大。此外，在激波面上存在一个更低的波动频率 (0.133BPF)，可能和激波本身的非定性有关，这里不是我们关注的重点。

为了解释这一非定常机理，图9和图10分别给出了一个非定常周期内 $9 8 \%$ 叶高马赫数和涡量分布， $T$ 表示非定常周期。涡量的定义为：

$$
\zeta _ { n } = \frac { | \zeta | } { 2 \omega }
$$

其中， $\zeta$ 表示绝对涡量， $\omega$ 表示轴的转动角速度。一个非定常周期内 $0 \sim 2 5 \%$ 叶片弦长范围内叶片表面压力变化如图11所示，吸力面压力几乎没有变化，压力面压力变化较大，存在一个低压区 (绿色圆圈)，随时间沿压力面移动。在 $1 / 5 T$ ，激波/泄漏涡相互作用使泄漏涡破碎，激波后出现一个低速区。由于低速区的存在，叶片压力面出现一个低压区 (图 11)，叶片前缘载荷降低，泄漏涡强度降低 (图10(a))。同时，此低速区把激波向上游推动，形成一个凹凸结构。从$1 / 5 ~ T$ 到 $2 / 5 ~ T$ 。低速区持续增加，叶片前缘载荷继续降低，泄漏涡涡量变得更小。随着时间推进，低速区向下游扩散，激波的凹凸强度减弱。如图11所示叶片压力面上的低压区向下游移动，叶片前缘载荷逐渐恢复，相应的泄漏涡强度增强，在 $3 / 5 \ T$ ，泄漏涡强度最大，为泄漏涡破碎提供了条件。从 $3 / 5 T$ 到

![](images/ebcda6d486e2b6a112128f4485d6ea6c080c586c44165a40acf15b4a32bc6cb7.jpg)  
图8相对参考系下的频率特性

![](images/baee5251330754a19978007203ab851c34577c567492a67e5ba3a8ef15e915af.jpg)  
Fig.8 Frequency characteritics in the relative frame   
Fig.9 Mach number distribution at $9 5 \%$ span

$5 / 5 ~ T$ ，该泄漏涡向激波面移动。在 $5 / 5 ~ T$ ，泄漏涡又发生破碎，一个新的循环开始。由以上分析可知，泄漏涡的破碎与前缘泄漏涡涡量达到最大值之间存在一个滞后，这是由涡由叶片前缘传播到激波面所需时间决定的。此非定常性是一个在泄漏涡-激波/泄漏涡相互作用-叶片载荷相互影响的过程，和轴流转子中的自激非定常相似。为了进一步说明泄漏涡的非定常性，图12给出了叶片前缘附近泄漏流质量流量和动量随时间的变化，其变化的周期性和上述分析的非定常现象相吻合。 $1 / 5 \ T$ 到 $2 / 5 ~ T$ ，泄漏流的流量和动量降低，相应的涡量也降低。在 $3 / 5 \ T$ ，泄漏量及其动量达到最大值，相应的涡量值达到最大。

![](images/84348fdadea3a33aa58e4d5f9f95f0da25c0a97ab6ba8d1227527adf1e00fb04.jpg)  
图10 $9 8 \%$ 叶高涡量分布

![](images/0ce5ba37a35170a5b2573fedff27dc9cecc37768c5e3f0e59ac4725dc8b01395.jpg)  
图9 $9 8 \%$ 叶高马赫数分布  
Fig.10 vorticity distribution at $9 5 \%$ span   
图11一个周期内叶片表面压力波动  
Fig.11 Static pressure on the blade variations during one unsteady period $T$

![](images/af718625c78ee3aa4469de059df7cc0f5ff7a13fffa95f73e80535fd183eb89a.jpg)  
图12泄漏流质量流量和动量的非定常性 Fig.12 Time history of mass flow rate and momentum of tip leakage flow

# 2.3多通道非定常分析

为了捕捉流场的周向不均匀性，研究通道之间的相互影响，在质量流量为 $2 . 6 ~ \mathrm { k g / s }$ 时对此叶轮进行了双通道和三通道模拟。在双通道和三通道模拟中，傅里叶变换得到流道中压力波动频率分别0.9倍BPF和0.89倍BPF。可知多通道计算所得频率特性和单通道不同。这可能是相邻通道之间流动相互影响造成的。双通道和三通道模拟所得 $9 8 \%$ 叶高的马赫数分布分别如图13和14所示，由图可知，和单通道相同的是，激波/泄漏涡相互作用之后出现一个低速区，但是在同一时刻各个流道中的流动状态不同，相邻通道间流动形态存在相位差。对双通道模拟结果，在两个通道相同相位位置各取一个监测点，其压力波动如图15所示，两个通道的相同相位位置压力波动有一个 $1 0 8 ^ { \circ }$ 的相位差，方向与叶轮旋转方向相反。在三通道模拟中，相邻两个通道相同相位位置压力波动的相位差也是 $1 0 8 ^ { \circ }$ ，方向与叶轮旋转方向相反。由以上分析可知，此非定常现象和轴流压气机中的旋转不稳定性[14]相似。但值得注意的是本文中所研究的非定常现象和旋转失速不同，它是由各个通道内激波与泄漏涡相互作用引起的，不是由叶片前缘流动分离等现象周向传播造成的。各个通道内的压力波动相位差仅仅是由循环周期性引起的。但是它可能是旋转失速的先兆。

尽管多通道模拟所得频率特性和单通道不同，但单通道模拟可正确描述和解释产生非定常的机理。由于双通道和三通道模拟所得频率特性和相邻通道间的相位差相近，我们可以推测双通道和三通道模型可以比较准确地模拟这一非定常特性。当然，要准确解释这一非定常现象，整周全通道模拟是必须的。这也是我们下一步的工作。

![](images/4e4c93eb520e83544b48d377ee596b271a2f49d746f78b97920e5f9c4eaa6d69.jpg)  
图13双通道模拟中 $9 8 \%$ 叶高马赫数分布 Fig.13 Mach number distribution at $9 8 \%$ span for the two-passage simulation

![](images/95bfdb841581a770d29817cd15f4d91b88aaab3c05e7314c268e749d43744149.jpg)

![](images/2810850dcfa626a68232ec11285da8e09d2645515ed5758503a39650e388d108.jpg)  
图14三通道模拟中 $9 8 \%$ 叶高马赫数分布 Fig.14 Mach number distribution at $9 8 \%$ span for the three-passage simulation   
图15相邻通道内相位相同位置压力波动对比 Fig.15 Time history of static pressures at the same phase of two adjacent passages

# 3结论

本文通过对一跨音速离心叶轮进行定常/非定常数值模拟，得出激波/泄漏涡的相互作用使跨音速离心叶轮叶尖区域流场更复杂，是造成叶尖堵塞和流动非稳定性的主要原因。在小流量下，由于泄漏涡和叶片载荷的相互影响，流场出现非定常波动。而且通过多通道模拟发现各个通道内流场波动存在相位差。具体结果如下：

1）在跨音速离心叶轮前缘存在一个脱体激波，该激波与泄漏涡相互作用在激波后形成一个低速区，造成叶尖区域堵塞。随着质量流量减小，激波/泄漏涡相互作用增强，在近失速工况，泄漏涡发生泡状破碎。

2）单通道非定常模拟得出在近失速工况下，叶轮中出现流动非定常性，主要集中在叶尖区域，非定常频率为0.668BPF。泄漏涡破碎在叶片压力面形成一个低压区，使叶片前缘载荷降低，泄漏涡强度降低，激波/泄漏涡相互作用减弱。低压区沿压力面向下游移动，叶片前缘载荷恢复，泄漏涡强度增强，激波/泄漏涡相互作用使泄漏涡又发生破碎，下一个循环开始。如此形成叶尖区域的流动非定常性。

3)在双通道和三通道模拟中每个通道内的流动现象和单通道模拟结果相似，但非定常频率分别为0.89BPF和0.9BPF，而且相邻通道内相同相位位置的压比存在一定的相位差。此现象和轴流压气机中的旋转非稳定性相似。

(4)单通道模拟可定性的解释流动非定常机理，多通道模拟可提供更多的非定常细节，但准确的模拟叶尖区域的非定常现象，整周模拟时必须的，也是我们下一步的工作。

# 参考文献

[1]Krain H，Karpinski G，Beversdorff M.Flow Analysis ina Transonic Centrifugal Compressor Rotor Using 3- Component LaserVelocimetry [C]//ProceedingsofASME Turbo Expo 2001:New Orleans,USA,2001:1-12   
[2] Ibaraki S,Matsuo T,Kuma H, Sumida K,Suita T.Aerodynamics of a Transonic Centrifugal Compressor Impeller [J].ASME Transactions Journal of Turbomachinery, 2003, 125(2): 346-351   
[3] Hazby HR,Xu L.Role of Tip Leakage in Stall of a Transonic Centrifugal Impellr [C]// Proceedings of ASME Turbo Expo 2009:Florida,USA,2009:1245-1253   
[4] Yamada K,Tamagawa Y,Fukushima H,Furukawa M, Ibaraki S,IwakiriK.Comparative Study on Tip Clearance Flow Fields in Two Types of Transonic Centrifugal Compressor Impeller with Splitter Blades [C]// Proceedings of ASME Turbo Expo 2010:Glasgow,UK,2010:2053-2063   
[5] Marconcini M,Rubechini F,Arnone A,Ibaraki S,Design and Off-Design Numerical Investigation of a Transonic Double-Splitter Centrifugal Compressor [C]// Proceedings of ASME Turbo Expo 2008:Berlin,Germany, 2008:1571-1578   
[6] Ce Y, Shan C,Du L. Inlet Recirculation Influence to the Flow Structure of Centrifugal Impeller[J].Chinese Journal of Mechanical Engineering,2010,23(2):1-8   
[7] Schleer M,Song S J,Abhari R S.Clearance Effects on the Onset of Instability in a Centrifugal Compressor [J] Journal of Turbomachinery, 2008,130(3): 993-1003   
[8] Weiguang Huang, Shaojuan. Numerical Simulation of Rotating Stall in a Centrifugal Compressor with Vaned Diffuser[J]. Journal of Thermal Science,2007,16(2):115-120   
[9] Surana T,Ishida M. Suppression of Unstable Flow at Small Flow Rates in a Centrifugal Blower by Controlling Tip Leakage Flow and Reverse Flow [J]. Journal of Turbomachinery,2004,127(1):76-83   
[10] Bousquet Y,Carbonneau X, Trébinjac I. Numerical Investigation of Kelvin-Helmholtz Instability ina Centrifugal Compressor Operating Near Stall [J]. Journal of Turbomachinery,2016,138(7):1-9   
[11] Trebinjac N B I.Aerodynamic Instabilities in Transonic Centrifugal, Compressor [J]. Mechanics & Industry, 2014, 15(3): 191-196   
[12] Eisenlohr G.,Krain H,Richter F A,Valentin T. Investigations of the Flow Through a High Pressure Ratio Centrifugal Impeller [C]//Proceedings of ASME Turbo Expo 2002:Amsterdam,Netherlands 2002:649-657   
[13] Kaneko M,Tsujita H. Numerical Investigation of Influence of Tip Leakage Flow on Secondary Flow in Transonic Centrifugal Compressor at Design Condition [J]. Journal of Thermal Science,2015,24(2):117-122   
[14] Mailach R,Lehmann I,Vogeler K.Rotating Instabilities in an Axial Compressor Originating From the Fluctuating Blade Tip Vortex [J]. Journal of Turbomachinery,2001, 123(3): 453-460