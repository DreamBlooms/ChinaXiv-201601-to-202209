# 新型单层双频双极化微带反射阵天线的设计

薛飞② 王宏建\*① 董兴超②(中国科学院国家空间科学中心微波遥感技术重点实验室北京100190)②(中国科学院大学北京100149)

摘要：该文提出一种新型的具有多谐振结构的单层微带反射阵单元，是由六个振子以一定的间隔平行放置组合而成，该单元具有良好的线极化特性，采用高频电磁仿真软件HFSS 对单元的各个参数进行优化分析，使得单元的反射相位曲线在两个频段内均具有良好的线性度。根据此单元设计了一个工作在 $\mathrm { { X / K u } }$ 波段的偏馈双频双极化微带反射阵天线，在两个频段内采用同一个角锥喇叭天线作为其馈源。将此反射阵天线进行加工并测试，测试结果表明，在X波段中心频率10GHz和 $\mathrm { K u }$ 波段中心频率13.58GHz处，天线均具有良好的辐射性能。实测和仿真结果吻合的较好，证明了该反射阵天线具有良好的双频辐射性能。该文的设计对于微带反射阵列天线实现双频双极化性能来说具有重要的参考价值。

关键词：微带反射阵；双频双极化；多谐振结构；偏馈  
中图分类号： 文献标识码：A 文章编号：  
DOI:10.11999/JEIT160332

# Design of a Novel Single Layer Dual-band Dual-polarization

# Microstrip Reflectarray

XUE Fei@② WANG Hongjian① DONG Xingchao①② (Key Laboratory of Microwave Remote Sensing National Space Science Center, Chinese Academy of Sciences,Beijing1ooi9o,China) (University of Chinese Academyof Sciences, Beijing 100149, China)

Abstract: A novel single layer microstrip reflectarray element with multi-resonance structure is presented.The element is composed of six dipoles which are placed in paralel at acertain distance.The element has good linear polarization properties. Ansoft HFSS is used tooptimize the parameters and linear reflection phase curves in two bands are achieved. A dual-banddual-polarizationreflectarraycomposedoftheelements isdesigned,fabricatedand measured.Theproposed reflectarray operates in two frequency bands within X band centered at 1o GHz and Ku band centered at $1 3 . 5 8 \ : \mathrm { G H z }$ The reflectarray isofsetfedbyonlyonehornantenna forboth bands intwoorthogonal polarizations.Measured results show good radiation performance inboth bands.A wellcoincide is obtained between the simulated and measured results, which demonstrate the desirabledual-banddual-polarizationradiation performanceof thereflectarray.Thedesign is valuable to other reflectarray in achieving dual-band dual-polarization performance.

Key words:Microstrip reflectarray; Dual-band dual-polarization; Multi-resonance; Offset fed

# 1引言

近年来，高增益天线的应用日益广泛，传统的高增益天线主要包括抛物面反射天线和阵列天线，但是两者都存在明显的缺点。高增益抛物面反射天线体积庞大，风阻大容易损坏，难以运输，波束扫描范围较小[，而且其曲面也对加工精度提出了很高的要求。阵列天线则是需要复杂的馈电网络，这会导致其传输损耗增大，天线的效率很难保证。微带反射阵天线是一种结合了上述两种高增益天线的阵列，其具有质量轻，加工简单，价格低廉，易与微带电路集成，易于和其他物体共形等特点，近年来得到了快速的发展与应用。此外，微带反射阵易于实现高天线效率，并且可以很容易地进行宽角度的波束扫描[2]。

收稿日期：2016-04-07\*通信作者：王宏建wanghongjian@mirslab.cn

传统的微带反射阵天线的带宽通常都较窄[3]，因此实现双频或者多频口径复用是非常有意义的。虽然现有的双频双极化反射阵天线已经获得了初步的应用，但是要实现两个频段相近的而且设计简单的单层双频反射阵仍旧存在一定的难度。目前来说，微带反射阵天线实现双频或者多频工作主要有以下两种形式：一，将高低频段的单元都置于同一层介质上的单层结构形式[+-8]。在这种情况下，当高低频率之间离得比较近时，其单元可以采用相同的周期，但是此时需要合理设计单元的形式以及排列方式，来减小频率之间的互相干扰影响。但是当两个频率离得比较远时，比如相差3到4倍时，高频和低频单元各自的周期以及单元与地板之间的距离的选取会存在一定的难度。文献[6]中采用单层形式实现了7.1GHz，8.4GHz和 32GHz的三频段圆极化工作，其单元形式分别采用裂开的正方形环，十字形振子和嵌入偶极子的裂开圆环。相对于双层结构来说，单层结构的优势在于不存在上层对下层的遮挡及损耗影响，但不同频率单元之间的互耦较大。二，将不同频段的单元置于不同的介质层上的双层结构形式。低频阵面置于高频阵面之上[9,10]或者高频阵面置于低频阵面之上[1,12]这两种形式都可以实现双频工作，文献[9]中提出了一种新的单元形式，利用该单元设计了一个直径为 $0 . 5 \mathrm { m }$ 的双频右旋圆极化反射阵，在7.3GHz和31.75GHz处均得到了较高的效率和较低的交叉极化性能。文献[11]中使用双层结构实现了L波段和Ka波段的双频工作性能，上层高频阵列的地板采用频率选择表面（Frequency Selective Surface，FSS）有效地降低了上层对于下层的影响，较好地实现了双频工作性能。然而，双层结构形式具有其固有的缺点。首先，上层单元及其地板对于下层单元的遮挡会对下层单元工作的频段的增益有很大的影响。其次，下层单元激发的谐振模式会影响上层单元阵列的增益和副瓣。最后，双层结构难以对齐且加工成本高。此外，采用具有分形结构的单元也可实现双频或多频工作[13-15]，分形单元所具有的自相似性和自加载特性可以用来实现多频工作或者展宽带宽。然而上述文献中均是对两个频段相距较远时才适用，对于距离较近的两个频段来说，传统的设计对于实现双频双极化的的性能来说是具有一定的难度的。

本文提出了一种具有多谐振结构的单层六平行振子微带反射阵单元，通过对单元的各个参数进行扫描分析，得出一组较为合理的参数组合，然后对单元的极化特性进行了分析，验证了采用该单元实现双频双极化的可行性。接着采用该单元设计了一个工作于X/Ku波段的双频双线极化微带反射阵天线，该天线是在不同的极化方向实现不同的工作频率。采用同一喇叭天线对反射阵的两个不同频段进行馈电，馈电方式为偏馈，并分别在两个频段处对反射阵进行仿真分析，结果表明反射阵具有较好的双频双极化辐射性能，将此反射阵天线进行加工并测试，得到的测试结果与仿真结果吻合的较好。

# 2微带反射阵的基本原理

微带反射阵天线与抛物面天线都是将馈源辐射出来的球面波波前，经过天线的反射转换成平面波波前，抛物面是利用其特有的几何特性来调整入射波经过反射后的相位，而微带反射阵天线是利用每个单元的调相能力来调节天线口径面上的相位分布的。微带反射阵中的每个单元都要经过合理的相位调节才能实现特定的波束指向或者波束特性。考虑如图1所示的坐标系，对于波束指向为 $( q _ { 0 } , f _ { \mathrm { 0 } } )$ 的微带反射阵天线来说，第 $i$ 个单元所需引入的相移 $f _ { _ R } ( x _ { i } , y _ { i } )$ 可表示为：

$$
f _ { _ R } ( x _ { i } , y _ { i } ) = k _ { 0 } [ d _ { i } - ( x _ { i } \mathrm { c o s } f _ { _ 0 } + y _ { i } \mathrm { s i n } f _ { _ 0 } ) \mathrm { s i n } q _ { 0 } ]
$$

其中， $k _ { 0 }$ 为真空中的传播常数； $( x _ { i } , y _ { i } )$ 是第 $i$ 个单元的中心坐标。利用式（1)，结合单元的反射相位曲线就可以得出反射阵中每个单元的参数。

![](images/96c91640233b4521a379eeb2bb28a46d2283ec4406014bd927f52c5151c766df.jpg)  
图1微带反射阵列天线原理图

# 3 单元的设计及分析

文章中提出的单层六平行振子单元结构及其在阵中的排列方式如图2所示，X波段单元与Ku波段单元以相同的周期 $L$ 交叉排列，该单元结构简单且具有多谐振结构，适合作为微带反射阵的单元，单元的工作极化方向为振子长度方向。周期 $L$ 取 $\mathrm { 1 4 m m }$ ，即在 $\mathsf { 1 0 G H z }$ 处为0.47个波长，在 $1 3 . 5 8 \mathrm { G H z }$ 处为0.63个波长。介质的介电常数为2.25，厚度 $h = \mathrm { { 3 m m } }$ 。中间两个振子长度 $a$ ，两边振子的长度 $a _ { _ 1 }$ 和 $a _ { _ 2 }$ 正比于中间振子长度（204号 $a : a _ { 1 } = k ? a \ , \ a _ { 2 } = k$ 创k $\mathbf { \Delta } _ { a }$ ，其中 $k$ 为常数。振子宽度均为 $w$ ，相邻振子之间的间距均为 $d$ 。采用文献[16]中提出的WGA对单元的反射相位进行分析，得到单元的反射相位曲线。

![](images/933de14e77e24166aff88b824d35f265755d8b512bb58c4862e796ebf958ea47.jpg)  
图2六平行振子单元结构及排列方式

当 $a$ 从 $4 \mathrm { m m }$ 变化到 $1 3 . 6 \mathrm { m m }$ 时，分别在两个频段内分析不同的单元参数（ $d$ ， $w$ ， $k$ ）对单元反射相位曲线的影响，从而得出一组较优的参数组合。图3给出了不同的 $d$ 的值对单元反射相位曲线的影响，从该图中可以看出，相邻振子间距 $d$ 取不同值时，单元在两个频段处的反射相位曲线差别较小，说明d对单元反射相位的影响较小，这里选择 $d = \mathrm { o } . 5 \mathrm { m m }$ 。图4给出了不同 $w$ 值对单元反射相位曲线的影响，从图中可以看出不同振子宽度 $w$ 对应的反射相位曲线有一定的差别，当 $w = 0 . 8 \mathrm { m m }$ 时，不管是在13.58GHz 还是在10GHz处，单元的反射相位曲线的范围均较大且线性度均较好，因此，这里选择 $w = \mathrm { 0 . 8 m m }$ 是合理的。图5为不同的 $k$ 值对单元反射相位曲线的影响。从图5中可以看出，不同的 $k$ 值在两个频段处均对单元的反射相位曲线有较大的影响，尤其是在高频处。综合考虑两个频段内反射相位曲线的线性度和相位变化范围，本文选择 $k = 0 . 7$ ：

![](images/5100ced1956c03aeec49b5eca9464f1ec889c1615f8ec63f6c27ca3f17189a2a.jpg)  
图3不同d的值对单元反射相位的影响（ ${ \mathrm { \Delta } w { = } 0 . 8 \mathrm { m m } }$ ， $k { = } 0 . 7$ ）

![](images/122516c53db19ff43dda28ba29b2e5054a8d0681ea79944f3c945e56c52756ea.jpg)  
图4不同的值对单元反射相位的影响（ $d { = } 0 . 5 \mathrm { m m }$ $k { = } 0 . 7$ ）

![](images/53af258c45f89a0682928b12bda34a308846aae53e6916018be1360d10b4b923.jpg)  
图5不同值对单元反射相位曲线的影响（ $d { = } 0 . 5 \mathrm { m m } , \mathrm { { } } w { = } 0 . 8 \mathrm { m m } )$ （20

综上，当 $d = 0 . 5 \mathrm { m m }$ ， $w = 0 . 8 \mathrm { m m }$ ， $k = 0 . 7$ ，随着振子尺寸 $a$ 从 $4 \mathrm { m m }$ 变化到 $_ { 1 3 . 6 \mathrm { m m } }$ 时，单元在低频（10GHz）处反射相位曲线范围约为 $3 7 0 ^ { \circ }$ ，在高频（13.58GHz）处反射相位曲线范围约为 ${ 6 3 0 } ^ { \circ }$ ，满足微带反射阵单元最小反射相位范围不小于 $3 6 0 ^ { \circ }$ 的要求，而且在两个频段内的反射相位曲线的线性度较好。

当入射波极化方向垂直于振子长度方向时，计算单元的反射相位曲线，其结果如图6所示（该图是在13.58GHz 处得出的结果，10GHz 处同样可以得到类似的结论)。从图6可知，在入射波的极化方向正交于单元振子的长度方向的情况下，当振子长度变化时，单元的反射相位变化很小，说明与该单元工作极化正交的线极化入射波对该单元的影响很小，也意味着单元具有良好的线极化特性。

![](images/c8b789e76ccee8c642481363ccbeb69ce69379dc7961b3dfa1f60cff2350367b.jpg)  
图6入射波极化方向垂直于振子单元长度方向时单元的反射相位曲线（ $1 3 . 5 8 \mathrm { G H z }$ ）

对不同频段的单元之间的互耦影响进行了研究，其单元模型如图7所示，其中 $b _ { 1 } = k ? b , b _ { 2 } = k ? b _ { 1 }$ ，以低频单元对高频单元反射相位曲线的影响为例。图8为低频单元影响下的高频单元的反射相位曲线。从图 8可以看出，低频单元的存在与否，以及其尺寸大小对高频单元反射相位曲线几乎没有影响。因此得出本文提出的单层六平行振子单元低频对高频的影响很小，通过类似的分析也可以得出高频对低频的影响很小。

高频单元 C 一 低频单元 高频单元 频单元对高频单元的影响 （b）高频单元对低频单元的影

![](images/9b2c2648f1f4e9e006ac56530f1f2c6327305930523e2195825924a4f82ebe15.jpg)  
图7不同频段的单元之间的互耦影响分析模型  
图8低频单元影响下的高频单元的反射相位曲线（ $1 3 . 5 8 \mathrm { G H z }$ ）

# 4反射阵的设计与仿真/实测结果

利用上述提出的单层六平行振子单元设计了一个工作在 $\mathrm { { X / K u } }$ 波段的双频双线极化微带反射阵天线，天线模型结构如图9所示。在X波段处，其工作极化方向为 $y$ 极化，共有 $1 3 \times 1 3 = 1 6 9$ 个单元，馈源的相位中心距阵列的垂直距离 $H = 1 5 7 . 6 \mathrm { m m }$ 。在 $\mathrm { K u }$ 波段处，其工作极化方向为 $x$ 极化，共有 $1 2 \times 1 2 = 1 4 4$ 个单元，馈源的相位中心距阵列的垂直距离 $H = 1 4 5 . 5 \mathrm { m m }$ 。为了消除正馈时馈源对反射阵的遮挡，该反射阵在两个频段内均采用角锥喇叭天线偏馈的方式进行馈电，其入射角度 $q$ 均为 ${ 3 0 } ^ { \circ }$ ，主波束方向均为垂直阵面方向，即图9中 $z$ 轴方向。喇叭馈源天线在10GHz 和 $1 3 . 5 8 \mathrm { G H z }$ 处的仿真方向图如图10所示。

![](images/b227052677f986df244fd36692cd46c557d485b88544e40bf3e45c324e6a0374.jpg)  
图9双频双极化微带反射阵天线模型

![](images/ed53ae61c0d960e554ac2fd94b91744634a903cbf8e376184ca4293f7014fb52.jpg)  
图10喇叭馈源在10GHz和 $1 3 . 5 8 \mathrm { G H z }$ 处的辐射方向图

设计的微带反射阵天线在X波段（ $, \mathrm { { 1 o G H z } }$ )的仿真方向图如图11所示，从图11中可以看出，在 $\boldsymbol { \mathrm { 1 0 G H z } }$ 处仿真增益达到23.7dB，波束准确地指向了 $\scriptstyle q = 0 ^ { \circ }$ 的方向。对于E面方向图，副瓣为-15.5dB，交叉极化低于-29dB,对于H面方向图，副瓣为-18dB,交叉极化低于-34.4dB。图12为反射阵天线在 $\mathrm { \ K u }$ 波段（13.58GHz)的仿真方向图，从图12可以得出，在 $1 3 . 5 8 \mathrm { G H z }$ 处仿真增益为24.7dB，波束指向准确地指向 $\scriptstyle q = 0 ^ { \circ }$ 的方向。对于E面方向图副瓣为-18.5dB，交叉极化低于-28.6dB，对于H面方向图，副瓣为-13.5dB，交叉极化低于-33.7dB。

![](images/d39358b3a821ebef6e9f0c1de2f74098032fc79d4ad7c8b24651dff8afa9fcbd.jpg)  
图11反射阵在X波段处的仿真方向图（10GHz）

![](images/b71d84507b067a19e046ae1dbc6103aab2399d606e6acd557533fb4b769a5e18.jpg)  
图12反射阵在Ku波段处的仿真方向图（13.58GHz）

为了验证上述单元及所设计的微带反射阵天线的有效性，对该天线进行加工并测试。图13和图14 分别给出了反射阵天线在10GHz和13.58GHz处的实测方向图。实测结果表明，在两个频段处波束指向均准确地指向了 $\scriptstyle q = 0 ^ { \circ }$ 的方向，反射阵天线在10GHz 处的实测增益为23.68dB，E 面方向图的副瓣为-14.8dB,H面副瓣为-17.2dB，E面和H面的交叉极化均低于-26dB。在13.58GHz的实测增益为 24.56dB，E面方向图副瓣为-19.5dB，交叉极化低于-30dB，H面副瓣为-13.5dB，交叉极化低于-26.5dB。在10GHz处仿真与实测结果基本吻合，在 $1 3 . 5 8 \mathrm { G H z }$ 处实测与仿真的E面方向图副瓣有些许差异，主要是由于天线的简陋工装使得馈源横向偏焦引起的。总地来说，实测结果与仿真结果吻合的较好。图15和图16分别给出了反射阵天线在X波段和 $\mathrm { \ K u }$ 波段的实测增益和效率随频率变化的曲线，从图15和图16 中可以得出，在X波段内，1dB 增益带宽(增益波动小于1dB)约为 $1 2 . 5 \% ( 9 . 9 5 \mathrm { \sim } 1 1 . 2 \mathrm { G H z } )$ ，在中心频率10GHz 处，其实测效率为 $5 0 . 4 3 \%$ 。在 Ku 波段内，1dB 增益带宽约为 $12 . 9 \%$ （ $1 2 . 4 1 { \sim } 1 4 . 1 7 \mathrm { G H z } \rangle$ ，在中心频率13.58GHz 处，其实测效率为 $40 \%$ 。由于本文中设计的微带反射阵天线馈源的偏置角度较大，因此在不同极化和不同频率处的最大辐射方向会发生较小的变化。图17给出了反射阵天线的最大辐射方向随频率变化的曲线，从图17中可以看出，在上述X和Ku波段的1dB 增益带宽范围内，最大辐射方向偏离 $\boldsymbol { 0 } ^ { \circ }$ 方向的角度很小，均在±2.1°以内。上述实测结果验证了本文设计的反射阵天线良好的双频双极化辐射性能。

![](images/615ad8fabcf3ab481208d75b0a0e7e9e5601d760e167178dc839ec69648a6e5e.jpg)  
图13反射阵在X波段处的实测方向图（10GHz）

![](images/5fa0f9af6f7957ac0582b4c07cf678d3aaa8191e0fac33be0852b75d4e9b83ab.jpg)  
图14反射阵在Ku波段处的实测方向图（ $1 3 . 5 8 \mathrm { G H z }$ ）

![](images/0ea1d7a4962d66a9be75c9aebad77618feab6421eecdc87f4ba16cf9d1b8a5d3.jpg)  
图15反射阵实测增益和效率与频率的关系（X波段）

![](images/a9fc29092f4c57131a64f9d50e554041325aaabd355738aa72b3419cda6b35c3.jpg)  
图16反射阵实测增益和效率与频率的关系（Ku波段）

![](images/7beb0e8e44e32eb264d4ab15c6e9d194e007fcc4af2e8ac8bbe1cabf7ab6cc39.jpg)  
图17反射阵最大辐射方向与频率的关系

# 5结论

本文提出了一种新型的多谐振单层微带反射阵单元，该单元由6个振子平行放置组合而成，其结构简单，易于实现。利用该单元设计了一个工作在X/Ku 波段的双频双极化微带反射阵天线，其X 波段单元与Ku波段单元以相同的周期交叉排列于阵中。采用同一个角锥喇叭天线对反射阵的两个不同频段以偏馈的方式进行馈电。仿真分析表明该反射阵具有较好的双频双极化辐射性能，将该反射阵进行加工并在微波暗室中进行测试，测试结果与仿真结果吻合的较好，验证了该单元的有效性及反射阵天线工程可行性。本文中所介绍的设计思路及单元形式对于微带反射阵列天线实现双频双极化性能来说具有重要的参考价值。

# 参考文献

[1]刘肖萌，高文军，邓云凯．有限扫描反射面天线相控波束重构技术[J]．电子与信息学报，2012，34(2):481-486.doi:10.3724/SP.J.1146.2011.00593.

controlJ].JournalofElectronics&InformationTechnology2012,34(2):481-486.doi:10.3724/SP.J1146.2011.00593.   
[2]KARNATI K KandGONG X.Acontinuous Ka-band beam-scaningreflectarrayintegratedwithBSTC.2015 IEEE International SymposiumonAntennasandropagation &USNC/URSINationalRadio Science Meeting,Vancouver,BC,Canada215:154-1541.doi: 10.1109/APS.2015.7305159.   
[3] POZAR D.Bandwidth of reflectarraysJJ.Electronics Letters,2003,39(21):1490-1491.doi: 10.1049/el:20030990.   
[4] CHAHARIMRR,SHAKERJ,andGAGONNBroadbanddual-bandlinearrthogoalpolarisatioreflectarryJElectoicee 2009,45(1): 13-14. doi: 10.1049/el:20092679.   
[5]MALFAJANIRSandATLABSBAFZ.Designandimplementationof adual-bandsinglelyerreflectarayinXandKbands.EEE Transactions on Antennas and Propagation, 2014,62(8): 4425-4431. doi: 10.1109/TAP.2014.2327137.   
[6]YANGKIYYUA,etal.Asinglelaerreflectarryantenafor//KabandsaplicaiosC].IternatioalCoferecen Electromagneticsin AdvancedApplications (ICEAA),Torino,Italy207:1058-1061.doi:10.1109/ICEAA.2007.48749.   
[7HAMZAV-ZARGHANZandATLABBAFZAnewbroadbandsingle-layerdual-bandreflectarayantenainX-andKubandsJEEE Antennas and Wireless Propagation Leters,2015,14: 602-605.doi: 10.1109/LAWP.2014.2374351.   
8QUSiggXIaetlgeadaiglerlatio.Ecson Antennas and Propagation,2014,62(1):199-205.doi: 10.1109/TAP.2013.2287517.   
[9]HANCODNBCKCHUAJ,etal.ACKaalfreqncyduallrarlyolaredreflectarate withosriing elementsJ].IEEE TransactionsonAntennasandPropagation,2004,52(11): 2871-2876.doi:10.1109/TAP.2004.83514.   
[10]HANCUAGJndAK.Aigfecfe-dX/KuandrfarruingtnmbaesEEcison Antennas and Propagation,2005,53(9): 2792-2798. doi: 10.1109/TAP.2005.854531.   
[11]SMITHTGOHELFUKIOS,etal.AnbackedGHzcicularlypolarizedreflctarrforasredapertureLdKa-bad atelitemcattEcsted(2)d   
[12]CHAHA,HAKERJndLEGHDalbandK/Xrtarayitoabadopelemetscote and Propagation, 2010,4(2): 225-231. doi: 10.1049/iet-map.2008.0369.   
[13]HARAPRVUHOAVCetlcrostripractalpatchnteaforultibandounicatiolectoics Letters,2000,36(14):1179-1180.d0i: 10.1049/el:20000832.   
[14]SINHASdefcaldeEEeesgoLee6: 10.1109/LAWP.2007.891519.   
[15]薛飞，王宏建，易敏，等．新型微带反射阵单元的设计及其应用[J．电波科学学报,2015,30(3):571-575.doi:10.13443/j.cjors.2014062701. XUEFei，WAgianaiofelulisoctieartitslcaioe Journal of Radio Science, 2015,30(3): 571-575. doi:10.13443/j.cjors.2014062701.   
[16]TSAIFCEandBALKOWsKIME.Anequivalent waveguideappoachtodesigningofreflectarrays usingvariable-sizemicostrip patchesJ].Microwave and Optical Technology Letter,2002,34(3):172-175.doi: 10.1002/mop.10407.

薛飞：男，1989年生，博士生，研究方向为微带反射阵列天线的研究与设计.王宏建：男，1969 年生，研究员，博士生导师，研究方向为电磁场与微波技术.董兴超：男，1988年生，博士生，研究方向为微带天线、缝隙耦合阵列天线的研究