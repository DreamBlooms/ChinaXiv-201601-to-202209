编号：162105

# 亚音叶型前缘形状对附面层参数影响

于贤君，朱宏伟，刘宝杰

（航空发动机气动热力重点实验室，先进航空发动机协同创新中心，北京航空航天大学能源与动力工程学院，北京

100191)

摘要：采用数值模拟方法研究了圆弧形、椭圆形和曲率连续无吸力峰前缘对叶型附面层发展的影响规律。通过提取不同工况下叶面附面层参数并结合叶表附面层速度型的变化，发现前缘吸力峰对叶型性能的影响本质在于吸力峰影响了附面层的起始发展状态。前缘吸力峰扩压参数 $D _ { \mathrm { s p i k e } }$ 过强会导致附面层起始发展状态恶化，造成提前转捩，甚至出现分离泡，叶表附面层迅速增厚，叶型损失增大，可用攻角范围减小。研究还表明，所设计的曲率连续无吸力峰前缘在任意工况总可以消除吸力面或压力面近前缘的吸力峰，从而使得叶表附面层的起始状态优于其它前缘叶型，因此气动性能要更好。

关键词：叶型前缘；亚音叶型；附面层；数值分析；压气机中图分类号：V231.3 文献标示码：A

# Effects of Leading-Edge Geometry on Boundary Layer Parameters in Subsonic airfoi l

YU Xian-Jun, ZHU Hong-Wei, LIU Bao-Jie

(NationalKeyLaboratoryofienceandTchologyonAero-Engine,AdvancedAero-EngineColabrationIovationCenterhool ofEnergy and Power Engineering,Beihang University,Beijing 1Oo191, China)

Abstract: The effect of circular,elliptical and curvature continuous leading edge on the development of boundary layer is studied by numerical simulation method.It is found thatthe influence of the leading edge suction peak on the aerodynamic performance in subsonic compressor blade is due to the fact the suction afects the initial development state of the boundary layer by extracting the parameters of the boundary layer under different working conditions and the velocity pattern of the bounder layer. The leading edge of the suction peak diffusion parameter $D _ { \mathrm { s p i k e } }$ is too strong will lead to the initial stateof deterioration of the boundary layer,resulting in early transition,or even separation bubble,blade surface layer of rapid thickening,loss of blade increases,the available atack angle range reduced.The study also shows that the design of curvature continuous spikeless leading edge in any condition can always eliminate the suction surface or pressre surface near the leading edge ofthe suction peak,so that the initial state of the blade surface layer is better than the other leading edge,so aerodynamic performance should be beter.

Key words: Leading edge; Subsonic compressor blade; Boundary layer; Numerical analysis; Compressor

# 0引言

未来飞机推进系统要求压气机的压比和效率都大大高于目前的使用水平，以提高发动机的推重比，减小燃油消耗率。将这种要求转换到叶片上即为：高负荷、大可用攻角范围和健康的叶表附面层[1]。从国内外研究趋势上看，可控扩散叶型（CDA）作为高效率、高负荷压气机设计的关键技术之一，并且在高压压气机中后部的亚音环境中已经得到了非常广泛的工程应用[2]。可控扩散叶型设计的核心思想在于控制叶型表面的等熵马赫数/叶表静压升系数按照特定的规律分布，使得叶表附面层发展的更加健康，以提高叶型性能。由于在航空发动机中，压气机叶片前缘厚度往往很小，最小可达$0 . 2 \mathrm { m m }$ 左右，相对厚度只有弦长的 $1 \%$ 左右，在工程设计中往往从结构强度层面考虑较多；另外，在叶型设计过程中，由于前尾缘曲率变化较为剧烈，通常采用分段设计的方法，即先生成叶身再添加前

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

尾缘的方式，这往往会导致前缘和叶身连接处的曲率变化很大。而且由于叶片加工精度不足以及叶片在使用过程中自然侵蚀和磨损等原因都会影响叶片前缘的几何形状，这些几何形状的改变都会对叶片性能产生一定的影响。

随着对叶型的深入研究，国内外诸多学者发现叶型前缘形状对叶片的气动性能有着不可忽视的影响[3]，随之这也成为了叶型研究的热点之一。为了便于加工，传统的叶型前缘采用圆形设计，但是随着诸多学者大量的数值模拟和实验研究表发现[4-7],由于圆形前缘和叶身连接处曲率不连续导致在前缘附近会产生分离泡，造成流动提前转捩，增加损失。陆宏志等[4.5]对椭圆形前缘进行了数值模拟发现，椭圆形前缘能够明显的抑制吸力峰，改善叶片的气动性能；作者基于控制前缘和叶身曲率过度的想法，提出了带平台的圆弧形前缘，发现这种设计可以改善叶表流动，达到与椭圆形前缘相近的结果。鉴于前缘问题的存在，宋寅[8.9]和袁春香[10]等人又提出了前缘曲率连续的设计方法，研究表明，曲率连续的设计方法能够更好的抑制前缘吸力峰（Spike）的产生，叶表附面层的发展更加健康，很有效的改善了叶片性能。AndrewP．SWheeler和Miller[11-12]等对上游转子尾迹叶型损失的影响进行的实验研究表明在上游尾迹干扰的情况下，椭圆形前缘较圆形前缘能够明显减小叶片的型面损失。Goodhand和Miller[13]对椭圆形前缘进行优化消除了吸力面前缘的吸力峰，实现了设计状态无前缘吸力峰（spikeless）叶型设计；随之又提出吸力峰的高度存在一个临界值，该临界值可以用前缘吸力峰扩散因子 $D _ { \mathrm { s p i k e } }$ 来评价，当吸力峰的高度超过临界值后，叶型损失会迅速增加。

以上研究结果表明，前缘形状对叶型性能有很大的影响。在同一状态下，不同的前缘形状对叶型性能的影响有所不同，但是前缘形状对叶表附面层发展影响的机制还没有完全澄清。鉴于此，本文的主要工作就是针对一个CDA叶型，在不改变叶身的情况下分别实现该叶型的圆形前缘、椭圆形前缘和Spikeless前缘设计，并利用可模拟边界层转换的数值分析方法对叶型的攻角损失特性进行了模拟，然后提取了详细的叶表附面层在的发展演化过程，对附面层参数进行了深入分析。通过对比不同前缘叶型附面层的发展过程，探讨了叶型前缘对叶型气动性能影响的机制。该研究将为进一步的实验研究和叶型优化提供必要的理论支持。

# 1数值计算方法

# 1.1叶型简介

本文采用的可控扩散叶型参数见表1。叶型前缘几何形状如图1。

表1CDA叶型参数简介  
Table1 CDA parameters   

<html><body><table><tr><td>Chord/m</td><td>0.18</td></tr><tr><td>Solidity</td><td>1.6</td></tr><tr><td>InletMachnumber</td><td>0.13</td></tr><tr><td>Stagger angle/(°)</td><td>21.77</td></tr><tr><td>Inlet metal angle/(°)</td><td>47</td></tr><tr><td>Camber angle/(°)</td><td>41</td></tr><tr><td>Turbulent intensity/(%)</td><td>5</td></tr><tr><td>Reynoldsnumber</td><td>5.45*105</td></tr></table></body></html>

(based on inletvelocity and chord)

![](images/42a4f5876c2efdd201ffe24d2141966fc4513febb659a86997c09332dcea6f0c.jpg)  
图1前缘几何形状

![](images/a49b0968d90348071c5f93f6f6303231240c7e709481afce8d4483207f0b9cda.jpg)  
Figure1Leading-Edge geometry   
图2网格  
Figure 2 mesh

# 1.2 网格

本文主要针对附面层流动细节进行研究，因此对网格要求较高。网格采用ICEM生成，在叶片表面利用"O"型网格在保证良好的正交性的同时进行了局部加密，保证了近壁面网格 $y ^ { + } { < } 1$ ，边界层内网格总数大于10道，且网格以1.1的比率向主流区递

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

增。图2为本文采用的网格，计算域距叶片前缘约1.5倍弦长，距叶片尾缘2倍弦长。展向给定20道网格，模型网格总数为64万。

# 1.3湍流模型选择及边界条件设定

本文使用ANSYSCFX软件进行叶型计算，为了更加准确的预测附面层的转捩和附面层的流动细节，计算中湍流模型选取 Shear Stress Transport 模型，并使用Gamma-theta转挨模型，计算格式采用高精度格式，保证二阶精度。边界条件设定方式为：进口边条给定总温、总压和气流角；出口边条根据不同的工况给定出口流量；栅距方向设置为周期性边界条件；展向上采用对称边条；叶片表面为光滑无滑移固体表面。当残差小于 $1 . 0 \times 1 0 ^ { - 4 }$ 时，判定计算收敛，但需保证流量、速度和压力残差曲线平直。

![](images/7a3cf7c5619dbeb128bfc3f7c0c0c2f2d8002813f8208e88b0b8fae4e1ca1e2a.jpg)  
图3叶表静压升系数

# 1.4数值模拟校验

在确定了数值模拟的网格、数值格式、湍流模型、转换模型和边界条件之后，用实验数据对CFX的计算结果进行校验，以确认计算结果的可靠性。图3为CFX计算结果和叶栅实验结果的对比。由于在叶栅实验中存在一定的三维流动效应，由于端壁附面层的存在，进出口轴流密流比AVDR约为1.02，但是在数值模拟中CFX没有考虑AVDR的影响，因此计算结果和实验结果之间稍有偏差，但是可以看到计算与实验结果的总体符合性较好，尤其是在前缘附近的计算结果和实验结果符合的较好，对吸力峰的模拟与实验对比有较好的一致性。另外，由于实验中没有看到分离泡型附面层转捩（可能是由于叶型的叶表粗糙度以及来流湍流度稍高造成的)，而计算结果显示出了分离泡转挨（ $40 \%$ 弦长位置附近）造成了压力平台。考虑到本文主要分析的是前缘对叶表附面层的定性影响，因此，数值模拟结果具有较好的参考性。

# 2前缘对叶型气动性能的影响

图4给出了计算得到的不同前缘几何造型的叶型总压损失特性，可以看出，三种前缘几何叶型的最小损失基本一致，但是可用攻角范围（以最小损失的两倍作为攻角计算范围）却有比较大的差别。圆形叶型的可用攻角范围明显比椭圆和Spikeless 前缘叶型小接近 $2 . 5 ^ { \circ }$ ，接近总工作范围的 $14 . 3 \%$ 。Spikeless前缘叶型可用攻角范围最宽，损失也最小。这表明不同的前缘几何造成了叶表附面层流动状态的差异，导致了损失和可用攻角范围具有差异。

![](images/8a2e3ca645be3a7c794e4714164f271c2e42f3d847f4a95651afd642f9ca9dc3.jpg)  
图4叶型总压损失比较

![](images/934f343385e266c131337efc24536803b46fa0a14a0e718e37f5a487e8812df1.jpg)  
Figure 3 Coefficient of static pressure of blade   
Figure 4 Comparison of total pressure loss   
图5叶型气流折转角比较  
Figure 5 Comparison of flow deflection angle

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/c7553dd689986f4322bd714dfd73ab2aceb0021f6c872eb7859c223a131b4e59.jpg)  
图6叶型 $D$ 因子比较

![](images/c7a1fddae17d1e63f26b08e3421e2fe7e6d623a3cf75c1e063d67be778600300.jpg)  
Figure 6 Comparison of $D$ factor   
Figure7Comparisonofblade deviationangle

从图5（叶型气流折转角特性）、图6（叶型D因子特性）和图7（叶型落后角特性）中可以看到，圆型前缘叶型的加功增压性能在大攻角状态明显要比其他两种叶型差，椭圆形前缘叶型次之，Spikeless前缘叶型的性能最优。还可以看到，圆形前缘叶型在攻角范围内的落后角都明显偏高，并且在大正、负攻角状态下附面层提前分离，使得叶型损失随着攻角的偏离而增加。而 Spikeless 前缘叶型落后角最小，大正、负攻角状态下附面层分离最迟，保持了很好的流动状态。综上所述，可以发现，在其他参数保持一致，只有前缘几何不同的情况下，叶型性能却有很大的差别，这是由于前缘几何不同造成了叶表附面层的发展状态出现差异，因此为了深入研究前缘几何对叶型性能的影响，下面对叶表附面层的发展进行详细对比分析。

# 3前缘对叶表附面层发展状态的影响

# 3.1附面层参数提取方法

为了提取附面层参数，自主发展了附面层提取程序，首先根据计算得到的流场将流场差值到与叶型表面严格正交的网格上，然后在正交网格上进行附面层参数的提取分析。对于任意位置的附面层厚度利用下式计算：

$$
\begin{array} { r } { \delta = \int _ { 0 } ^ { \delta } \Bigl ( 1 - \frac { \rho _ { 1 } u } { \rho _ { 2 } U } \Bigr ) d y } \end{array}
$$

积分方向沿叶表法向， $\rho _ { 1 } u$ 为当地密度和速度； $\rho _ { 2 } U$ 为主流密度和速度。其中主流的判断根据速度梯度沿法向的极值点来判断，当没有极值点时，则根据设定梯度的一个最小值来判断。由于边界层参数对梯度的阀值不敏感，因此可根据主流区的梯度极大值适当提高作为流场整体的边界层与主流的分界判断准则。动量厚度利用下式计算：

$$
\begin{array} { r } { \delta ^ { * } = \int _ { 0 \rho _ { 2 } U } ^ { \delta ^ { \rho _ { 1 } u } } \Bigl ( 1 - \frac { \rho _ { 1 } u } { \rho _ { 2 } U } \Bigr ) d y } \end{array}
$$

能量厚度利用下式计算：

$$
\begin{array} { r } { \theta ^ { * } = \int _ { 0 \overline { { \rho _ { 2 } U } } } ^ { \delta \rho _ { 1 } u } \biggl ( 1 - \frac { \rho _ { 1 } u ^ { 2 } } { \rho _ { 2 } U ^ { 2 } } \biggr ) d y } \end{array}
$$

从而形状因子为：

$$
H = \frac { \delta } { { \delta } ^ { * } }
$$

![](images/000722523d48298428b11e7aefb46c0186fba1090bb3772d9f04b76db0dee545.jpg)  
图7叶型落后角比较  
图8不同来流气流角时吸力面附面层形状因子的发展过程，来流气流角( $\mathrm { a ) } 3 5 ^ { \circ } ( \mathrm { b } ) 4 7 ^ { \circ }$ (c)50°

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

# 3.2不同攻角状态叶型附面层发展规律分析

图8、图9和图10为不同攻角下叶型吸力面附面层积分参数的变化，从中可以看出，在来流气流角为 $3 5 ^ { \circ }$ 的大负攻角工况下，三种叶型的滞止点位置均位于吸力面一侧，在吸力面一侧的前缘绕流过程没有很大的差别，因此附面层发展过程基本一致，都是在 $60 \%$ 流向位置处发生转捩，导致附面层迅速增厚，摩阻损失增大，因此在吸力面的损失基本一致。在来流气流角为 $4 7 ^ { \circ }$ 的设计工况下，三种叶型的滞止点位置均在前缘点附近，由于 Spikeless叶型前缘曲率变化最小，Ellipse 叶型前缘曲率变化次之，两者在前缘吸力面一侧的绕流过程很相近，都没有发生过强的突然压缩和膨胀过程，都是在$40 \%$ 流向位置发生了转捩，造成附面层迅速增厚，摩阻损失增大。但是circle叶型前缘处存在曲率不连续，从而circle叶型的前缘绕流存在较强的突然压缩和过度膨胀过程，即较强的前缘 Spike，并在前缘出现分离泡，导致吸力面在前缘附近就发生分离泡转捩，附面层也随之迅速增厚，摩阻损失增大。因此，在该状态下circle叶型吸力面的损失最大，Ellipse 和 Spikeless 的损失基本一致且最小。

![](images/ce4e2c4b0276e01188cdd4d5907907d56a1f5473f7586697448e8158df18aa6f.jpg)  
Figure 8 Development of boundary layer shape factor on suction surface at inflow angle of $( \mathrm { a } ) 3 5 ^ { \circ } ( \mathrm { b } ) 4 7 ^ { \circ } ( \mathrm { c } ) 5 0 ^ { \circ }$

![](images/a84428bfc7feb9d6c70a57db7f9f76bb2b4af0b4543db0ace9443a51c073119b.jpg)  
图9不同来流气流角时吸力面附面层能量厚度的发展过 程，来流气流角 $\mathrm { \hat { a } ) } 3 5 ^ { \circ } ( \mathbf { b } ) 4 7 ^ { \circ } ( \mathbf { c } ) 5 0 ^ { \circ }$ Figure 9 Development of boundary layer energy thickness on suction surface at inflow angle of (a) $3 5 ^ { \circ } ( \mathsf { b } ) 4 7 ^ { \circ }$ (c)50°

![](images/c597f5cd3c0a9713c150465a703c518df28d07b5da409e902ff21f230235786a.jpg)  
图10不同来流气流角时吸力面附面层表面摩阻系数的发 展，来流气流角 $\mathrm { \hat { a } ) } 3 5 ^ { \circ } ( \mathbf { b } ) 4 7 ^ { \circ } ( \mathbf { c } ) 5 0 ^ { \circ }$ Figure 1O Development of boundary layer friction coefficient on suction surface at inflow angle of ( $1 ) 3 5 ^ { \circ } ( \boldsymbol { \mathrm { b } } ) 4 7 ^ { \circ }$ (c)50°

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

在来流气流角为 $5 0 ^ { \circ }$ 的大正攻角工况下，三种叶型的滞止点位置均位于压力面一侧，流体需要绕过前缘点到达吸力面，而三种叶型前缘的曲率变化有较大的差别，这将导致前缘绕流存在不同程度压缩和膨胀过程。由于circle叶型前缘除前缘点外曲率最大并保持一致，但是在前缘和叶身连接点存在曲率突变，因此circle叶型的前缘绕流的突然压缩和过度膨胀过程最强，前缘 Spike也最强，并在吸力面前缘出现分离泡。吸力面转捩位置提前到了前缘附近，造成附面层过快的增厚，并在尾缘出现了较大的附面层分离，增加了吸力面叶型损失。Ellipse叶型前缘点曲率较大，除前缘点外前缘其他位置曲率较小，而且前缘和叶身连接处的曲率突变较小，因此Ellipse 叶型前缘绕流造成的突然压缩和过度膨胀过程较Circle前缘弱，虽然转捩位置也提前到了前缘附近，但是造成的附面层增厚却较慢，吸力面叶型损失增加较circle叶型小。虽然Spikeless叶型前缘点曲率最大，但是除前缘点外前缘其他位置曲率最小，前缘和叶身曲率连续，这大大减弱了前缘绕流的膨胀过程，优化了前缘绕流过程，叶型吸力面转捩位置依然保持在 $30 \%$ 的流向位置，比其他两种叶型靠后，而且尾缘的附面层分离也最弱，损失也最小。

![](images/fcca1ab84b5450335a977a5b62b661c504a8337c86d2ff4f25413218b0fcc1b2.jpg)

![](images/597e103716882a4006533cae9bbc323fd12ff96f487029369d66cffac73efa8b.jpg)

![](images/2f5e4e97513714d9b860d708728fb077e345bb41ca87d59ede7d37e8b78f0fd1.jpg)  
图11不同来流气流角时压力面附面层形状因子的发展过程，来流气流角 $\mathrm { \hat { a } ) } 3 5 ^ { \circ } ( \mathbf { b } ) 4 7 ^ { \circ } ( \mathbf { c } ) 5 0 ^ { \circ }$ Figure11Development ofboundary layer shape factoronpressure surface at inflow angle of $( \mathrm { a } ) 3 5 ^ { \circ } ( \mathrm { b } ) 4 7 ^ { \circ }$ (c)50°  
图12不同来流气流角时压力面附面层能量厚度的发展过 程，来流气流角( $\mathrm { a ) } 3 5 ^ { \circ } ( \mathrm { b } ) 4 7 ^ { \circ } ( \mathrm { c } ) 5 0 ^ { \circ }$ Figure l2 Development of boundary layer energy thickness on pressure surface at inflow angle of $( \mathrm { a } ) 3 5 ^ { \circ } ( \mathrm { b } ) 4 7 ^ { \circ }$ (c)50°

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

图11、图12和图13为不同攻角下叶型压力面附面层积分参数的变化。可以看到，在来流气流角为 $3 5 ^ { \circ }$ 的大负攻角工况下，三种叶型的滞止点位于吸力面一侧，因此前缘绕流过程和上文所述的大正攻角工况下吸力面的绕流过程类似，虽然压力面转捩都在前缘发生（分离泡转捩)，但是circle叶型的前缘绕流的突然压缩和膨胀过程最强，ellipse 叶型次之，Spikeless最弱。这就造成Circle压力面附面层增厚最快，厚度最大，Ellipse 叶型次之，Spikeless 叶型最小。因此，在该状态下，Circle 叶型压力面损失最大，Ellipse 叶型其次，Spikeless 叶型最小。

![](images/7e1ad0615c1b6a5edb96358cb99345283f053175258e016a0979f87562078fe5.jpg)  
图13不同来流气流角时吸力面附面层表面摩阻系数的发展，来流气流角( $\mathrm { 4 ) } 3 5 ^ { \circ } ( \mathrm { b } ) 4 7 ^ { \circ } ( \mathrm { c } ) 5 0 ^ { \circ }$   
Figure 13 Development of boundary layer friction coefficient on

pressure surface at inflow angle of ( $( \mathsf { a } ) 3 5 ^ { \circ } ( \mathsf { b } ) 4 7 ^ { \circ }$ (c)50°

在来流气流角为 $4 7 ^ { \circ }$ 的设计工况下，三种叶型的滞止点均位于前缘点附近，由于在吸力面绕流的压缩和膨胀过程较强，因此在压力面的压缩和膨胀过程相应就会弱，三种叶型均没有发生前缘压力面转捩（形状因子在2.5左右)，此时压力面没有发生分离泡转捩。从形状因子来看，一直到尾缘，压力面的形状因子都保持在2以上，因此可以判断此时模拟得到的压力面附面层状态属于全层流状态，故总体上损失都较小。但是不难看出，Ellipse 前缘和Circle前缘叶型由于前缘与叶身之间曲率过度存在一定的不连续性，使得在靠近前缘区域存在一个局部扰动，但没有触发典型的层流边界层分析，并且在该区域摩阻系数存在一个尖峰。由于前缘区域对附面层造成的扰动不同，因此附面层的发展起始状态也有所不同，导致了从前缘到尾缘附面层的发展状态还是不同，但是三者损失相差不大。当来流气流角增大到 $5 0 ^ { \circ }$ 的大攻角工况时，压力面一侧前缘绕流的压缩和膨胀过程进一步减弱，三种叶型的压力面都保持为层流状态，流动情况与 $4 7 ^ { \circ }$ 工况相似。

0.0010 0.00100 Circle Circle 0.0008 C—Ellipse 0.00075 C—Ellipse B 00OO Spikeless —Spikeless X=0.0005 0.00.00 S0.0004 0.00025 T 0.0002 0.0000 0.00000 0 1020304050607080 -1001020304050607080 V/(m/s) V/(m/s) 0.0020 0.0020 Circle Circle 0.0015 O-Ellipse 0.0016 一○—Ellipse m x=0.00pieless m 0.0012 xS2ikeless 0.0010 s h0.0008 0.0005 0.0004 0.0000 0.0000 -1001020304050607080 -1001020304050607080 V/(m/s) V/(m/s) 0.0020 Circle 0.0020 Circle -Ellipse O—Ellipse 0.0015 0.0015 △Spikeless △—Spikeless 0.0010X0.050 0.0010 X=0.022 0.0005 0.0005 0.0000 △ 0.0000 7 0 10203040506070 0 10203040506070 V/(m/s) V/(m/s) 0.0100 0.0100 Circle Circle 中 0.0075 O— Ellipse 中 0.0075 O—Ellipse Spikeless △—Spikeless 0.0050 X=0.06 0.000 X=0.076 s 0.0025 0.0025 0.0000 △ 0.0000 A A 0 10 2030405060 0 10 2030 40 50 V/(m/s) V/(m/s)

WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

0.0100 0.0100 -Circle 金 Circle 0.0075 —O—Ellipse 0.0075 O—Ellipse —Spikeless △—Spikeless   
0.00 X=0.076 0.0050Xx0.15 0.0025 0.0025 0.0000 0.0000 △ 0 10 20 30 40 50 0 51015202530354045 V/(m/s) V/(m/s) 0.0150 0.015 Circle Circle 0.0125 -O—Ellipse O—Ellipse 0.0100—△—Spikeless 0.010 △—Spikeless   
0.0075X=0.14 w/ys X=0.160   
0.0050 S0.005 0.0025 0.0000 0.000 -5 0 510152025303540 -50 510152025303540 V/(m/s） V/(m/s)

由以上分析可以看到，前缘不同带来的前缘绕流过程会有所差异，从而引起附面层的厚度不同，损失也会不同。如图14所示（横坐标V表示速度大小，纵坐标sh表示距离当地叶片表面的法向高度)，通过观察不同的流向位置附面层速度型的分布，可以更为清晰地分析附面层速度剖面的发展过程。从图中可以看到，在来流角度为 $5 0 ^ { \circ }$ 时，Circle叶型前缘绕流的加速和膨胀过程最严重，从$\scriptstyle \mathrm { X = 0 } . 0 0 0 5$ 到 $\scriptstyle \mathbf { X = } 0 . 0 0 2 4$ Circle前缘叶型的边界层速度剖面从最饱满变成了近壁亏损最严重，并且可以明显看到此时前缘的分离泡从 $\scriptstyle \mathrm { X = 0 . 0 0 0 9 }$ 前已经起始，在 $\scriptstyle \mathbf { X = } 0 . 0 0 2 4$ 之后结束。对于该分离泡的存在性从图10给出的叶表摩阻系数分布也可以看到，即在近前缘区域存在一个 $C _ { \mathrm { f } }$ 突降为零的波动。从$\scriptstyle \mathrm { X = 0 } . 0 0 7 5$ 的结果中可以看出，Circle前缘叶型的前缘分离泡已经再附，但是速度型的饱满程度显然较另外两个叶型都要差很多。从图8形状因子的分布上来看，经过分离泡之后附面层应当已经发生了转捩，因此附面层的厚度增加的很快，明显高于另外两种前缘叶型的附面层。

从图14所示的Spikeless前缘叶型的吸力面附面层剖面的发展过程可以看出，在近前缘区域没有分离的特征，因此，没有出现分离泡，这与图10所示的结果表现一致。从 $\scriptstyle \mathrm { X = 0 . 0 0 0 9 }$ 之后，Spikeless前缘叶型吸力面的速度剖面在三个叶型中都最为饱满，附面层厚度明显最小。从图10所示的结果可以看出，来流角度为 $5 0 ^ { \circ }$ 时Spikeless前缘叶型吸力面在 $20 \small { \sim } 3 0 \%$ 弦长之间的摩阻系数非常接近0，此时附面层应当是非常接近分离的状态，并且在此过程之中发生了附面层的转捩（见图8所示的结果），对应的X位置应当在 $\mathrm { X } { = } 0 . 0 3 6$ 到0.054之间。从图14所示的结果可以看到，在 $\scriptstyle \mathrm { X = 0 } . 0 2 2$ 位置Spikeless前缘叶型的附面层的近壁速度梯度明显小于另外两种叶型，表现为典型的层流速度剖面，但是在$X { = } 0 . 0 6$ 的位置已经转换成了典型的湍流速度型，说明在这个过程中发生了转捩，并且应当是尺度相对较小的分离泡转捩。由于Spikeless 前缘叶型转捩的位置最为靠后，因此后续发展的湍流附面层也相对更为健康。

从图14所示的Ellipse前缘叶型叶表附面层剖面的发展情况，可以看出Ellipse前缘叶型的前缘分离泡尺度与Circle前缘叶型相比尺度相当，但是强度稍弱，分离泡之后也发生了完全转捩，因此吸力面叶表附面层是层流附面层。相关现象与图8和图10 中显示的结果一致。总体上，Ellipse 前缘叶型的附面层厚度和饱满性介于Circle前缘叶型和Spikeless前缘叶型之间。

综上所述，可以发现，即使在前缘前后经历相同的逆压梯度，不同的前缘几何造成的前缘绕流过程不同，直接导致附面层的起始发展状态不同，使得叶表流动状态产生了很大差异，造成能量亏损不同（如图9和图12所示)，即叶型损失不同。这也就造成前缘几何不同，叶型损失有很大的差别，可用攻角范围也会有很大的变化。由此可见，不同的前缘形状对叶片性能的影响与前缘绕流强度息息相关，该绕流过程中造成的局部加速和减速越强，通常流动损失也越大。

# 4前缘局部绕流对叶表附面层的影响

# 4.1不同前缘造型对前缘Spike发展的影响

为了分析前缘局部扰流的关键影响因素，有必要借鉴Goodhand 和 Miller[13]提出的 $D _ { \mathrm { s p i k e } }$ 参数进行深入分析。该参数的定义如下：

$$
D _ { s p i k e } = \frac { U _ { M A X } - U _ { M I N } } { U _ { M A X } }
$$

其中各变量的定义如图15所示。该参数实际上是借鉴 $D$ 因子提出来的，表征了前缘突然压缩过程的强弱。

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/887f1073bd9b7b3905b7084f29f8db8dd852ed96c5dec6dc3518b51c601fc271.jpg)  
图15叶片表面压升系数和前缘局部压升系数分布示意图[13] Figure 15 The static pressure coefficient ofblade surface and the local static pressure coeficient of the leading edge[13]

图16为不同前缘叶型叶表压升系数随来流气流角的变化，结合图17给出的吸力面前缘 $D _ { \mathrm { s p i k e } }$ 随来流气流角的变化，可以看出，随着来流气流角增大，吸力面前缘 $D _ { \mathrm { s p i k e } }$ 也随之增大，即前缘吸力峰的强度增大。此外，不同的前缘几何叶型 $D _ { \mathrm { s p i k e } }$ 增长速率并不一致，Circle 前缘叶型 $D _ { \mathrm { s p i k e } }$ 增长最快,更容易出现吸力面分离泡，增加吸力面叶型损失。Spikeless 叶型在负攻角状态保持很低的 $D _ { \mathrm { s p i k e } }$ ，并且随来流气流角的变化增长缓慢，只有在 $4 5 ^ { \circ }$ 攻角之后， $D _ { \mathrm { s p i k e } }$ 增长速率加快。Ellipse 前缘叶型 $D _ { \mathrm { s p i k e } }$ 的变化介于Circle 前缘叶型和 Spikeless 叶型之间。由图18看出，相对于吸力面而言，压力面前缘绕流造成前缘 Spike 较小，随着来流气流角的增大，压力面前缘 $D _ { \mathrm { s p i k e } }$ 减小，对叶型性能的影响也随之减小。此外，可以明显看到 Spikeless 前缘的设计实现了吸力面从叶型最小损失攻角状态（ $4 5 ^ { \circ }$ 左右）到所有负攻角状态的无吸力峰流动；而压力面从最小损失攻角状态到正攻角边界之间无吸力峰；即所设计的Spikeless 前缘总可以实现吸力面或者压力面的无Spike 流动。Circle前缘叶型除了在最大负攻角状态吸力面 Spike 较弱，最大正攻角状态压力面 Spike较弱外，其它状态的 Spike 都非常明显。Ellipse 前缘在负攻角边界附近实现了吸力面无Spike，最大正攻角状态压力面无 Spike，其它状态都存在Spike。显然，Spike的强弱与叶表附面层的发展状态直接关联，即与叶型损失直接相关。Spikeless 前缘叶型之所以能够实现好的叶型性能，与基本消除或者显著削弱了Spike 密切关联，并且Spikeless 的状态较宽广。因此，有必要对叶表附面层参数与Spike之间的关联进行深入分析。

![](images/dfcd409198ab4bae343fe68761c302e3362dd18e06f26f3abc1bab07e9a266f5.jpg)  
图16不同前缘造型叶型前缘局部压升系数随气流角的变 化，(a) Circle (b) Ellipse (c) Spikeless Figure l6 Variations of the local static pressure coefficient near leading edge with inlet flow angle,(a)Circle (b)Elipse (c)

![](images/1093057db7bf4ed307a127c55ac59bd285e467cca68a6b867634c816714fde7f.jpg)  
图17吸力面前缘 $D _ { \mathrm { s p i k e } }$ 随来流气流角的变化 Figure 17 Variations of $D _ { \mathrm { s p i k e } }$ with the inlet angle at the leading edge of the suction surface

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538

![](images/8198519c103902c514b215c618ae1997bc3dc7f7391e4388a679afd680f77bc9.jpg)  
图18压力面前缘 $D _ { \mathrm { s p i k e } }$ 随来流气流角的变化 Figure 18The variation of $D _ { \mathrm { s p i k e } }$ with the inlet angle at the leading edge of the pressure surface

# 4.2前缘Spike与叶表附面层参数之间的关系

基于上面的分析，提取了 $10 \%$ 弦长位置的叶表动量厚度和形状因子，分析 $D _ { \mathrm { s p i k e } }$ 与附面层参数之间的关系。从图19和图20可以看出，叶型能量损失厚度随着 $D _ { \mathrm { s p i k e } }$ 的增大而增大，当 $D _ { \mathrm { s p i k e } }$ 达到一定值之后由于分离泡的出现，导致了叶型损失迅速增大。对于图19所示的吸力面结果，Spikeless 前缘叶型与其它前缘叶型相比在 $D _ { \mathrm { s p i k e } }$ 相同的情况下，造成的能量损失厚度要更大一些，Ellipse 前缘叶型与Circle前缘叶型相比也要大一些。此外，从图19所示的结果中可以看到 $D _ { \mathrm { s p i k e } } { > } 0 . 1 7$ 后才会造成吸力面叶型损失的显著增大（Spikeless 前缘和Circle 前缘叶型的临界值接近0.2)，这与Goodhand和Miller[13]给出的 $D _ { \mathrm { s p i k e } } { > } 0 . 1$ 的准则有较大偏差。而从图20所示的压力面结果可以看出，此时不同前缘叶型 $D _ { \mathrm { s p i k e } }$ 与附面层能量损失厚度的关系非常接近，规律与吸力面也相同，Circle前缘叶型在相同的 $D _ { \mathrm { s p i k e } }$ 情况下造成的损失要稍小一些。此外，压力面的结果显示 $D _ { \mathrm { s p i k e } } { > } 0 . 1 2$ 时会造成压力面叶型损失的显著增大（Circle前缘叶型的临界值接近0.14)，这与Goodhand和Miller[13]给出的准则较为接近；但是需要指出的是，此时Circle前缘叶型叶型的临界值接近0.18。由此见，从 $D _ { \mathrm { s p i k e } }$ 的角度进行评价，Circle 前缘叶型的损失对 $D _ { \mathrm { s p i k e } }$ 的容许度要更高一些。

![](images/78d0502f7f69cb490b536814aa71437427771a633fc554ef8dd7f6e835bbc9b9.jpg)  
图 19 吸力面 $10 \%$ 弦长位置处附面层能量厚度随 $D _ { \mathrm { s p i k e } }$ 的变化

![](images/43bec7186e3d29193f9967e38a63a5747e3d4a4ed973a717a4431c025199d30d.jpg)  
Figure 19 Variation of boundary layer energy thickness with $D _ { \mathrm { s p i k e } }$ on suction surface at $10 \%$ chord location   
图20压力面 $10 \%$ 弦长位置处附面层能量厚度随 $D _ { \mathrm { s p i k e } }$ 的变化

![](images/20bcc2be1c83c45a245de8b4e7c66f3f33d1e7359b7ab406ff15c76de0f659fd.jpg)  
Figure 2O Variation of boundary layer energy thickness with $D _ { \mathrm { s p i k e } }$ on pressure surface at $10 \%$ chord location   
图21吸力面 $10 \%$ 弦长位置处附面层形状因子随 $D _ { \mathrm { s p i k e } }$ 的变化  
Figure 21Variation of boundary layer shape factor with $D _ { \mathrm { s p i k e } }$ on suction surface at $10 \%$ chord location

图21和图22中给出了叶型前缘局部区域吸力面和压力面边界层形状因子与 $D _ { \mathrm { s p i k e } }$ 的关联关系。可以看出，在吸力面 $D _ { \mathrm { s p i k e } } { > } 0 . 1 7$ 后附面层的形状因子迅速减小，从层流状态转变为湍流状态，即发生了转捩。这表明通常情况下吸力面 $D _ { \mathrm { s p i k e } } { > } 0 . 1 7$ 会造

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

成前缘区域出现分离泡并触发转捩。同样可以看到，同在层流状态，Circle前缘叶型的形状因子要小一些，即附面层剖面的近壁速度梯度要更小一些，这是造成能量损失厚度要小一些的原因，这应当与前缘局部的曲率有关。从图22显示的压力面结果可以看出，此时诱发边界层转捩的临界 $D _ { \mathrm { s p i k e } }$ 约为0.12（Circle前缘叶型的临界值接近0.14)，由于形状因子迅速减小后有快速增大，这说明如果$D _ { \mathrm { s p i k e } }$ 如果过强（Spikeless 前缘和Ellipse 前缘叶型$D _ { \mathrm { s p i k e } } { > } 0 . 1 3$ ,Circle前缘叶型 $D _ { \mathrm { s p i k e } } { > } 0 . 1 5$ ）极有可能直接造成了大尺度的负攻角压力面分离流动，损失会快速增加。

![](images/562a87524ca7b7bb5ec3771f11a1d746131797e4854284898702636cc16b0235.jpg)  
图22压力面 $10 \%$ 弦长位置处附面层形状因子随 $D _ { \mathrm { s p i k e } }$ 的变化  
Figure 22 Variation of boundary layer shape factor with $D _ { \mathrm { s p i k e } }$ on pressure surface at $10 \%$ chord location

# 5结论

本文以三种不同前缘造型的叶型为例，通过数值模拟研究了不同前缘造型对叶型表面附面层发展机制，得到以下主要如下结论：

（1）、不同的前缘造型会使得前缘绕流过程不同，即前缘 Spike不同，过强的前缘Spike 会导致叶型性能下降，可用攻角范围减小。Circle叶型前缘绕流过程变化最为剧烈，损失偏大，可用攻角范围较小，Spikeless叶型削弱了前缘Spike，减小了叶型损失，增大了可用攻角范围。

（2）、前缘 Spike对叶型性能影响的主要在于，前缘Spike 影响了附面层的起始发展状态，过强的前缘Spike使得速度型不饱满，在经历相同逆压力梯度的情况下，更难以抵抗逆压梯度，造成附面层提前转捩，甚至出现分离泡，从而导致附面层迅速增厚，叶型损失增加，可用攻角范围减小。

（3）、吸力面前缘 $D _ { \mathrm { s p i k e } }$ 随着来流气流角的增大而增大，对吸力面性能的影响也随着增大，使得吸力面叶型性能下降，压力面反之。

（4）、叶型损失随着前缘 $D _ { \mathrm { s p i k e } }$ 的增大而增大，当达到某一值后，会引起叶型性能的急剧下降。

（5）、所设计的Spikeless前缘在任意工况总可以消除吸力面或者压力面近前缘的吸力峰，从而使得叶表附面层的起始状态优于其它前缘叶型。

参考文献   
[1] Hobbs D E,Weingold H D.Development of Controlled Diffusion Airfoils for Multistage Compressor Application [J].Journal of Engineering for Gas Turbines and Power, Transactions of the ASM E.1984,106: 271-278.   
[2]钟兢军，王会社，王仲奇．多级压气机中可控扩散叶型 研究的进展与展望第一部分可控扩散叶型的设计与发展 [J]．航空动力学报，2001，16(3):206-209. ZHONG Jingjun,WANG Huishe,WANG Zhongqi.Development and Prospect of Controlled Diffusion Airfoils for multtistage Compressor[J]. Journal of Aerospace Power,2001,16 (3):206-209.   
[3] Suder K L,Chima R V,Strazisar A J. The Effect of Adding Roughness and Thickness to a Transonic Axial Compressor Rotor [R].ASME GT-1994-339.   
[4] 陆宏志，徐力平．压气机叶片前缘形状的改进设计[J]．航 空动力学报,2000,02(2):129-132. LU Hongzhi， XU Liping. Improvement of Compressor Blade Leading Edge Design [J]. Journal of Aerospace Power,2000,02(2):129-132.   
[5] 陆宏志，徐力平．压气机叶片的带平台圆弧形前缘[J]．推 进技术,2003,24(6):532-536. LU Hongzhi,XU Liping. Circular Leading Edge with a Flat forCompressorBlades[J].JournalofPropulsion Technol0gy,2003,24(6):532-536.   
[6] 刘火星，李凌，蒋浩康,等．二维NACA65 叶型前缘几何 形状对气动性能的影响[J]．工程热物理学报，2003, 24(2):231-233. LIU Huoxing,LI Ling, JIANG Haokang,et al.Effect of Leading Edge Geometry on Seperation Bubble on a NACA 65Compressor Blade [J]．Journal of Engineering Themophysics,2003,24(2):231-223.   
[7] 刘火星，蒋浩康，陈懋章．压气机叶片前缘分离流动[J]. 工程热物理学报,2004,25(6):936-939. LIU Huoxing, JIANG Haokang，CHEN Maozhang. An Expermental Investigation of The Flow on Leading Edge of

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

CompressorBlade[J].JournalofEngineering Themophysics,2004,25(6):936-939.   
[8] 宋寅，顾春伟．曲率连续的压气机叶片前缘设计方法[J]. 推进技术,2013,34(11):1475-1481. SONG Yin,GU Chunwei. Continuous Curvature Leading Edge of Compressor blading[J]. Journal of Propulsion Technology,2013,34(11):1475-1481.   
[9]宋寅，顾春伟．叶片前缘形状对压气机气动性能的影响 [J]．工程热物理学报,2013,34(6):1015-1054. SONG Yin,GU Chunwei.Effect of Leading Edge on the Aerodynamic Performance of Compressor[J]. Journal of Engineering Thermophsics,2013,34(6):1015-1054.   
[10] 刘宝杰，袁春香，于贤君．前缘形状对可控扩散叶型性 能影响[J].推进技术,2013,34(7):890-897. LIU Baojie,YUAN Chunxiang，YU Xianjun.Effect of Leading Edge Geometry on Aerodynamic Performance in Controlled Diffusion Airfoil[J]. Journal of Propulsion Technology,2013,34(7):890-897.   
[11] Andrew P.S.Wheeler,Alessandro Sofia,and Robert J. Miller， The Effect of Leading-Edge Geometry on Wake Interactions in Compressors[R].ASME,2007.   
[12]Wheeler A P S,Miller R J.Compressor Wake/LeadingEdge Interactions at Off Design Incidences[C].2008.   
[13] Goodhand M N,Miller R J. Compressor Leading Edge Spikes: A New Performance Criterion [J].Journal of Turbomachinery,2011,133(2):394-399.

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538