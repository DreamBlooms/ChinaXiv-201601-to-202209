# CN 53-1189/P ISSN 1672-7673

# 新疆奇台110米射电望远镜主焦点馈源换馈方案研究

赵聪1,²，许谦'，王娜¹，项斌斌1(1.中国科学院新疆天文台，新疆 乌鲁木齐830011；2.中国科学院大学，北京100049)

摘要：随着射电天文研究的不断深入，科学家对望远镜分辨率和灵敏度的要求也不断提高，同时要求望远镜具有更宽的观测波段。单口径望远镜低频波段用主焦点接收，馈源尺寸可以更紧凑。为了不影响双反射面天线次焦点的馈电功能，主焦点馈源的放置及换馈方案必须高效合理。以建于新疆奇台的 $1 1 0 \mathrm { m }$ 口径全可动射电望远镜为研究对象，以意大利SRT $6 4 ~ \mathrm { m }$ 和德国Effelsberg $1 0 0 \mathrm { ~ m ~ }$ 射电望远镜为参考，对两种方案应用于奇台 $1 1 0 \mathrm { m }$ 射电望远镜的可行性进行分析，并提出一种利用线性模组进行主焦馈源快速切换的新型方案。进行了直线模组机构的建模和仿真，并对口径面信号遮挡进行了分析，结果表明，此方案能有效满足望远镜的工作需求。

关键词：馈电方式；射电望远镜；主焦点馈源；丝杆线性模组中图分类号：TH751 文献标识码：A 文章编号：1672-7673(2017)02-0172-07

在过去的十几年里，国内射电望远镜技术有了快速的发展，望远镜口径越来越大，精度也越来越高。2012年10月， $6 5 \mathrm { ~ m ~ }$ 全可动射电望远镜在上海佘山落成，该望远镜工作波段覆盖 $1 . 6 ~ \mathrm { G H z } \sim 4 6 \$ $\mathrm { G H z }$ ，采用主反射面可调节的主动面技术[1]。目前贵州平塘 $5 0 0 \mathrm { ~ m ~ }$ 口径局部可动球面射电望远镜于2016 年9月完工[2]。正在筹建的新疆奇台 $1 1 0 \mathrm { m }$ 口径全可动射电望远镜（QiTai radio Telescope，QTT）,可以显著提高我国天体物理、天体测量和空间探测的水平。 $1 1 0 \mathrm { ~ m ~ }$ 射电望远镜的工作波段覆盖150$\mathrm { M H z } \sim 1 1 5 ~ \mathrm { G H z } ^ { [ 3 ] }$ ，需要配备一定数量的接收机。高频馈源更适宜放置在次焦点，次焦馈源有更小的尺寸，接收更少的背景噪声，而低频段的馈源安装在主焦点，结构紧凑合理[4]。 $1 1 0 \mathrm { ~ m ~ }$ 射电望远镜的主、次焦点均能馈电，能安装更多的接收机。

世界范围内主、次焦点均有馈电功能的望远镜有3台，分别是德国 $1 0 0 \mathrm { ~ m ~ }$ 望远镜[5]、美国GreenBank $1 0 0 \mathrm { ~ m ~ }$ 望远镜(GBT)[6、意大利 $6 4 ~ \mathrm { m }$ 望远镜(SRT)[7］。德国 $1 0 0 \mathrm { ~ m ~ }$ 望远镜的主焦点换馈方案采用副面中心开孔的方式（图1a），主焦点馈源工作时，副面中心孔的面板打开，所需的馈源由此伸出。使用完毕只需收回主焦点馈源，副面中心面板闭合，就完成一次主焦点馈源工作过程。由于Effelsberg 天线采用标准抛物面，因此馈源伸出的副面中心开口区域处于几何光学遮挡区域，此区域内的表面精度不影响天线的工作效率。采用中心伸缩桶的馈电方案能够避免换馈机构对主反射面产生额外遮挡而降低效率。意大利 $6 4 ~ \mathrm { m }$ 望远镜的主焦点换馈方案是将主焦点馈源放置于一横梁上，位于副面边缘（图1b）。换馈机构由后方的丝杆和电机驱动绕副面上方的回转副运动，由初始位置运动$7 8 ^ { \circ }$ 将馈源移动至主焦点位置。不同的馈源可在横梁上移动，从而切换不同的主焦点馈源。由于意大利 $6 4 ~ \mathrm { m }$ 望远镜为赋形双反射面天线，主焦点换馈方案不宜采用德国 $1 0 0 \mathrm { ~ m ~ }$ 望远镜的方案，它所用的方案主焦点换馈简单快速，能在儿分钟内完成，但对口径面有遮挡而造成大线效率降低。美国绿岸望远镜是偏焦望远镜，主焦点馈源与推杆链接，不工作时收在副面撑腿旁，工作时由推杆将其推至主焦点位置（图1c)。绿岸望远镜主焦换馈较容易实现，对口径面没有遮挡，缺点是换馈时间长，完成一次换馈需要2\~4小时。

![](images/adf45e9c268a6cb37f6c288f1d1fd1bbbae52c552c8a2fe1e0ea5d3334f0c056.jpg)  
图1Effelsberg、SRT、GBT主焦点馈源换馈机构Fig.1Effelsberg，SRT and GBT primary focus positioner

$1 1 0 \mathrm { m }$ 射电望远镜为格里高利型天线并具有赋形功能，副反射面尺寸较大，对主焦点换馈方案有很高要求。赋形功能对副反射面中心几何遮挡区域的面形精度有要求，若采用德国 $1 0 0 \mathrm { ~ m ~ }$ 望远镜方案，中心区域面板开合精度难以保证。大口径的副反射面采用意大利 $6 4 \mathrm { ~ m ~ }$ 望远镜主焦馈电方式，换馈机构的结构笨重，对天线产生更大的遮挡，同时换馈机构的重复定位精度较难保证。

结合多种方案提出了一种以开式丝杆线性模组为驱动的主焦点换馈方案。开式线性模组由电机、联轴器、滚珠丝杆、轴承座、电机座和转接座等模块组成，主要特点：（1)高刚度、高精度;(2)易安装、易维护。

# 1设计方案

1.1主焦点换馈机构的技术要求

换馈机构主要实现的目标是通过机构运动，在主焦观测时将接收机送至主焦点位置，并实现多个接收机在主焦点之间的切换。机构运动实现过程中重点保证以下几点：

(1)定位准确，能准确地保证馈源相心与焦点重合；  
(2)主焦点接收机要复位准确，并尽量减小天线遮挡;  
(3)传动平稳，传动精度高；  
（4)尽量采取自动换馈的方案，减轻操作人员的工作难度；  
(5)在满足机构刚度的条件下，有更小的结构和质量。

# 1.2 机构组成

$1 1 0 \mathrm { m }$ 射电望远镜前期研究中，主焦点初步配置3个不同频段的接收机，分别为 $0 . 1 5 \ : \mathrm { G H z } \sim 0 . 1 6 \ : \mathrm { G H z } ,$ $0 . 6 \mathrm { G H z } { \sim } 4 \mathrm { G H z }$ 两个单波束接收机和一个频段 $1 ~ \mathrm { G H z } \sim 2 ~ \mathrm { G H z }$ 的PAF接收机。根据馈源结构特性，设计了一种基于开式丝杆线性模组驱动的换馈机构，由焦点位移机构与馈源切换机构组成，如图2。

焦点位移机构主要包括两组开式丝杆线性模组、馈源安置横梁等。焦点位移机构只有两个位置，工作位置与闲时位置。工作位置时馈源安置横梁位于天线副面的中心位置（如图3a)；闲时位置的馈源安置横梁位于副面侧方，且不遮挡副面(如图3b)。不同位置切换需将望远镜指向天顶，以切换至工作位置为例，馈源切换机构的两组开式丝杆线性模组同步运动，带动馈源安置横梁到工作位置。

馈源切换机构主要由一组开式丝杆线性模组和排列在线性模组螺母面的主焦点馈源组成。馈源切换机构的3个馈源排列如图4，馈源2位于丝杆线性模组中央，线性模组可做往复运动，向左移动一个馈源宽度的距离就切换至馈源3，相反方向移动可以切换为馈源1，这样就完成了3个馈源之间的切换。

![](images/c8b2c6d9baa5d8826e459e5015c16918f302dffa80067b0ca9b2a94d6899b6f1.jpg)  
图2 $1 1 0 \mathrm { m }$ 射电望远镜主焦点换馈机构

![](images/6790d9081b20dd2f6512e0a45e91bcaf964c539f9847e93f1ee52b4703abec3b.jpg)  
Fig.2QTT primary focus positioner

目前为 $1 1 0 \mathrm { m }$ 射电望远镜前期研究阶段，大口径射电望远镜主副反射面直径比一般为 $1 0 : 1$ ，$1 1 0 \mathrm { m }$ 射电望远镜主反射面直径为 $1 1 0 \mathrm { m }$ ，副反射面直径取 $1 1 \mathrm { ~ m ~ }$ ，焦径比按照0.33设计，副反射面距主焦点 $3 . 2 \mathrm { m }$ 。经过优化设计，焦点位移机构中的馈源安置横梁长度可取 $1 2 \mathrm { m }$ ，馈源安装于馈源安置横梁预先设定好的馈源盒中。考虑到最小行程和余量，焦点位移机构中开式丝杆线性模组的行程为 $7 \mathrm { m }$ ，才能保证有足够的运动距离将馈源送至焦点位置。3个馈源中，相邻两个馈源中心轴线距离 $1 . 5 \mathrm { ~ m ~ }$ ，中间的馈源向左或向右移动$1 . 5 \mathrm { m }$ ，能切换到另外2个馈源，取馈源切换机构

![](images/769646b91d554968fbfc2f7d90355fb9dd4e03413c352246adf424883c9cf7fd.jpg)  
图3焦点位移机构。(a)焦点位移机构处于闲时位置；(b)焦点位移机构处于工作位置Fig.3Focus positioner.（a）free time position；（b）working time position  
图4馈源切换机构可将3个馈源分别切换至主焦点 Fig.4Feeds switching mechanism for the primary focus receivers

中线性丝杆模组行程为 $3 . 3 \mathrm { ~ m ~ }$ ，这样3个主焦点馈源都能到达焦点位置，且有一定的余量。由 $1 1 0 \mathrm { m }$ 射电望远镜主焦点换馈机构主要工作部件的结构尺寸，得出各部件的大体质量，见表1。

Table1Weight of the QTT primary focus positioner   

<html><body><table><tr><td>部件</td><td>3个馈源</td><td>馈源安置横梁</td><td>短行程丝杆模组</td><td>2个长行程丝杆模组</td><td>总质量</td></tr><tr><td>质量/kg</td><td>500</td><td>1 250</td><td>450</td><td>1400</td><td>3600</td></tr></table></body></html>

1.3焦点位移机构和馈源切换机构的丝杆副尺寸

# 1.3.1焦点位移机构的丝杆副尺寸

$1 1 0 \mathrm { m }$ 射电望远镜主焦点切换机构要在几分钟内完成换馈工作，根据要求，焦点位移机构应在  
$2 1 0 \mathrm { ~ s ~ }$ 内将馈源切换机构送至主焦点位置。由于焦点位移机构丝杆副长度为 $7 \mathrm { m }$ ，长行程的丝杆转速不  
宜过快，取最大转速 $n _ { \mathrm { m a x } }$ 为 $1 2 0 ~ \mathrm { r / m i n }$ ，按照机构运动时间的要求，最大速度 $v _ { \operatorname* { m a x } }$ 应为 $1 8 0 0 \mathrm { m m / m i n }$ 。$P _ { \mathrm { h } } = { \frac { v _ { \mathrm { m a x } } } { n _ { \mathrm { m a x } } } } = 1 5 ~ { \mathrm { m m } }$ $3 6 0 ^ { \circ }$

丝杆副的选取需要知道丝杆的预期额定动载荷，计算过程中需要比较工作时间要求与预紧要求的额定动载荷，取较大值进行校验。焦点位移机构丝杆最大轴向负载 $F _ { \mathrm { m a x } }$ 为天线指向地平时，大小为$2 3 2 0 0 \mathrm { N }$ 。 $1 1 0 \mathrm { m }$ 射电望远镜焦点位移机构丝杆副预期额定动载荷在预紧要求下较高，预紧要求下的预期额定动载荷 $C _ { \mathrm { a m } }$ 可由(1)式得出：

$$
C _ { \mathrm { a m } } = f _ { \mathrm { e } } F _ { \mathrm { m a x } } ,
$$

其中， $f _ { \mathrm { e } }$ 为预紧载荷系数值为4.5，求得丝杆副预期额定动载荷 $C _ { \mathrm { a m } }$ 为 $1 0 4 . 4 \mathrm { K N }$ 。

丝杆螺纹底径 $d _ { 0 }$ 为外螺纹牙角底部直径，即丝杆小径。允许最小螺纹直径 $d _ { 2 \mathrm { m } }$ 为选取丝杆副之前，由丝杆副工作要求计算得出丝杆小径的最小参数。允许最小螺纹底径 $d _ { 2 \mathrm { m } }$ 由(2)式得出：

$$
d _ { 2 \mathrm { m } } = a \sqrt { \frac { F _ { \mathrm { 0 } } L } { \delta _ { \mathrm { m } } } } ,
$$

其中， $\delta _ { \mathrm { { m } } }$ 为丝杆允许的最大轴向变形量，取 $\delta _ { \mathrm { { m } } } = 2 . 5 ~ \mathrm { { u m } }$ ; $F _ { 0 }$ 为丝杆运动时所受的轴向力，大小为4 640N； $L$ 为滚珠丝杆两轴承支撑点间的距离，取 $L = 7 ~ 0 0 0 ~ \mathrm { m m }$ ； $\mathbf { \alpha } _ { a }$ 为丝杆轴的支撑方式系数，采用两端固定式，一般取 $\scriptstyle a = 0 . 0 3 9$ 。由(2)式得出焦点位移机构丝杆副的最小螺纹底径 $d _ { 2 \mathrm { m } } = 6 5 . 4 \ \mathrm { m m }$ 。

根据计算结果，确定焦点切换机构的一对丝杆线性模组的丝杆选型为内循环固定法兰式、直筒双螺母垫片预紧GD 型8016-4，参数见表2。经验证，GD型8016-4丝杆副螺纹底径 $d _ { 2 } = 6 8 . 6 \ \mathrm { m m }$ 大于最小螺纹底径 $d _ { 2 \mathrm { m } }$ ，额定动载荷 $C _ { \mathrm { a } } = 1 1 5 . 4 8 3 ~ \mathrm { K N } > C _ { \mathrm { a m } }$ ，结构强度满足望远镜焦点位移机构的要求。

表1 $\mathbf { 1 1 0 \ m }$ 射电望远镜主焦点换馈机构质量  
表2GD型8016-4丝杆副参数  

<html><body><table><tr><td>直径d/mm</td><td>螺纹底径d/mm</td><td>额定动载荷C/KN</td><td>滚珠直径Dw/mm</td><td>螺母长l/mm</td></tr><tr><td>80</td><td>68.6</td><td>115. 483</td><td>9. 525</td><td>248</td></tr></table></body></html>

# 1. 3. 2 馈源切换机构的丝杆副尺寸

馈源切换机构线性模组选型过程与焦点位移机构丝杆副选型过程大体相同。不同的是馈源切换机构丝杆副的最大轴向载荷 $F _ { \mathrm { m a x } } = 5 0 0 0 ~ \mathrm { N }$ （天线指平），最大行程 $3 3 0 0 \mathrm { m m }$ 。

由（1）、（2)式计算得出馈源切换机构丝杆副预期额定动载荷 $C _ { \mathrm { a m } } = 2 2 . 5 1 ~ \mathrm { K N }$ ，最小螺纹底径$d _ { 2 \mathrm { m } } = 2 2 . 2 5 ~ \mathrm { m m }$ 。选取内循环法兰式、直筒双螺母垫片预紧GD型4010-4丝杆，参数见表3。经验证选用丝杆副螺纹底径 $d _ { 2 } = 3 2 . 9 \ \mathrm { m m }$ ，大于最小螺纹底径，即 $d _ { 2 } > d _ { 2 \mathrm { m } }$ 。额定动载荷 $C _ { \mathrm { a } } = 3 4 . 3 5 8 ~ \mathrm { K N }$ ，大于预期额定动载荷，即 $C _ { \mathrm { a } } { > } C _ { \mathrm { a m } }$ 。结构强度能达到馈源切换机构的工作需求。

Table 2 Screw parameters of GD 8016-4   
表3GD型4010-4丝杆副参数  
Table 3Screw parameters of GD 4010-4   

<html><body><table><tr><td>直径d/mm</td><td>螺纹底径d2/mm</td><td>额定动载荷C/KN</td><td>滚珠直径Dw/mm</td><td>螺母长l/mm</td></tr><tr><td>40</td><td>32.9</td><td>34.358</td><td>5. 953</td><td>162</td></tr></table></body></html>

# 2换馈方案分析

# 2.1换馈机构对天线效率的影响

由于副反射面及其支架对天线口面的遮挡，在天线口面上形成一个阴影，天线场等于没有遮挡的口面辐射场与阴影面积辐射相位反向 ${ 1 8 0 } ^ { \circ }$ 场的叠加，使得天线增益下降，旁瓣电平升高[9]。

在已知天线口径尺寸和工作频率的情况下，天线的增益可由(3)式计算得出：

$$
G = \left( \frac { \pi D } { \lambda } \right) ^ { 2 } \eta _ { \mathrm { { A } } } ,
$$

其中， $G$ 为天线增益； $D$ 为天线口径； $\lambda$ 为天线工作频率的波长； $\eta _ { \mathrm { A } }$ 为天线效率。从(3)式可以看出，天线效率决定天线增益。天线效率受多种因素的影响，一般可表达如下：

$$
\eta _ { \mathrm { \tiny ~ A } } = \eta _ { \mathrm { \tiny ~ 1 } } \eta _ { \mathrm { \tiny 2 } } \eta _ { \mathrm { \tiny 3 } } \eta _ { \mathrm { \tiny 4 } } \eta _ { \mathrm { \tiny 5 } } \eta _ { \mathrm { \tiny 6 } } \eta _ { \mathrm { \tiny 7 } } \eta _ { \mathrm { \tiny 8 } } ,
$$

其中， $\eta _ { \scriptscriptstyle 1 }$ 为口面利用率； $\eta _ { 2 }$ 为截获效率； $\eta _ { 3 }$ 为遮挡效率； $\eta _ { 4 }$ 为失配效率损失； $\eta _ { 5 }$ 为表面公差损失；  
$\eta _ { 6 }$ 为馈源差损效率损失； $\eta _ { 7 }$ 为相位损失； $\eta _ { \mathrm { 8 } }$ 为极化损失。

主焦点换馈机构对天线效率影响主要为 $\eta _ { 3 }$ 遮挡效率，对于 $1 1 0 \mathrm { ~ m ~ }$ 射电望远镜来说，遮挡效率主要是天线副面和副面支杆遮挡造成的损失，加装主焦点换馈机构增加了天线对主面的遮挡。在工程上，一般利用几何光学方法计算天线的遮挡损失[10]：

$$
\eta _ { 3 } = ( 1 - \frac { \Delta } { A } ) ^ { 2 } ,
$$

其中， $A$ 为天线的口径面积； $\Delta$ 为口径面被遮挡的面积。主焦点换馈机构在主面上投影面积约为$2 6 . 7 \mathrm { m } ^ { 2 }$ ，为整体主面面积的 $0 . 2 8 \%$ 。利用(5)式计算得主焦点换馈机构对天线造成遮挡损失比未加装时增加了 $0 . 4 9 \%$ 0

意大利 $6 4 ~ \mathrm { m }$ 望远镜与 $1 1 0 \mathrm { ~ m ~ }$ 射电望远镜主焦换馈方案对比见表4，本方案中 $1 1 0 \mathrm { ~ m ~ }$ 射电望远镜的主焦点换馈机构比意大利 $6 4 \mathrm { ~ m ~ }$ 望远镜对天线效率影响略小。意大利 $6 4 \mathrm { ~ m ~ }$ 望远镜副反射面口径为 $7 . 5 \mathrm { m }$ ，但其主焦点换馈机构馈源安置横梁达到了 $1 2 \mathrm { m }$ ，整体结构笨重。而 $1 1 0 \mathrm { m }$ 射电望远镜在具有更大副反射面口径( $1 1 \mathrm { ~ m ~ } )$ 的情况下，主焦换馈机构横梁尺寸仅为 $1 2 \mathrm { ~ m ~ }$ ，结构相对更小、更轻。

# 2.2主焦点馈源偏焦量

理想情况下馈源相心应与焦点位置完全重合，但实际上由于馈源支架的变形及馈源安装不准确对馈源对焦造成一定影响。对于 $1 1 0 \mathrm { m }$ 射电望远镜的主焦点馈源，馈源偏离抛物面的焦点分为两种情况：馈源沿抛物面轴线方向的偏移（轴偏）;馈源沿垂直于抛物面轴线方向的偏移(横偏）。

当馈源轴偏时，天线增益降低，旁瓣电平升高，最大辐射方向不变，仍在抛物面轴线上。

表4 $\mathbf { 1 1 0 \ m }$ 射电望远镜与SRT的主焦点换馈方案对比 Table 4Comparison of primary focus positioner ofQTT and SRT   

<html><body><table><tr><td></td><td>QTT</td><td>SRT</td></tr><tr><td>主焦点位移机构</td><td></td><td></td></tr><tr><td>行程/mm</td><td>6200</td><td>4 300</td></tr><tr><td>速度(mm/s)</td><td>30</td><td>22</td></tr><tr><td>加速度(mm/s²)</td><td>10</td><td>11</td></tr><tr><td>运动时间/s</td><td>210</td><td>190</td></tr><tr><td>馈源切换机构</td><td></td><td></td></tr><tr><td>行程/mm</td><td>3 000</td><td>3 000</td></tr><tr><td>速度(mm/s)</td><td>30</td><td>25</td></tr><tr><td>加速度(mm/s²)</td><td>10</td><td>10</td></tr><tr><td>切换时间 (单个馈源/最大行程)/s</td><td>53/103</td><td>40/120</td></tr><tr><td>馈源安置横梁长度/mm</td><td>12 000</td><td>12 000</td></tr><tr><td>主焦点馈源换馈机构 对天线的遮挡</td><td>0.49%</td><td>0.50%</td></tr></table></body></html>

$1 1 0 \mathrm { m }$ 射电望远镜的主焦点馈源轴向偏焦应小于 $0 . 1 \lambda$ ，其增益损失较小，旁瓣升高不大。馈源横偏时，天线方向图主瓣最大辐射方向将偏离一定角度，这时方向图变得不对称，靠近轴线一边的旁瓣电平明显升高，而另一边旁瓣则减小[1]。主瓣宽度变化不大，增益损失较小。给定 $1 1 0 \mathrm { m }$ 射电望远镜的主焦点馈源横向偏焦应小于0.1入，其增益损失较小，旁瓣电平升高在允许范围内。

$1 1 0 \mathrm { m }$ 射电望远镜的主焦点馈源最短工作波长为 $1 5 \ \mathrm { c m }$ ，设计过程中取其轴向与横向偏差均不大于 $0 . 1 \lambda$ 。即偏焦量小于 $1 . 5 \mathrm { c m }$ 。在仅考虑自重的情况下，对 $1 1 0 \mathrm { m }$ 射电望远镜主焦点换馈机构进行了仿真。馈源在天线指向天顶时轴向偏焦量最大，在天线指向地平时横向偏焦量最大。仿真结果（图5)给出了天线指向天顶和指向地平两种位置的馈源偏焦量。

![](images/10c113bbae681f90077e62f0d174876178eba72a4fb00e253072f2fc3a577ae5.jpg)  
图5 $1 1 0 \mathrm { m }$ 射电望远镜主焦馈源偏焦量仿真分析。(a)天线指向天顶时的馈源偏焦量;(b)天线指向地平时的馈源偏焦量

Fig.5Simulation of feed offset at QTT primary focus（a） antenna pitching axis at $9 0 ^ { \circ }$ ；（b）antenna pitching axis at $0 ^ { \circ }$

仿真分析结果表明：天线在指向天顶时，馈源靠近焦点部分的轴向偏焦量约为 $5 \ \mathrm { m m }$ ，小于允许的最大轴向偏焦量[12]；天线指向地平时，馈源横向偏焦量约为 $1 4 . 6 ~ \mathrm { m m }$ ，略低于允许的最小变形量$1 5 ~ \mathrm { m m }$ 。未来加装馈源位置测量系统，借助馈源机构可在平面内做二维平动，也可进一步调整减小指向地平时横向偏焦量。从仿真结果看，整体换馈机构满足 $1 1 0 \mathrm { m }$ 射电望远镜的主焦点换馈工作。

# 3结论

通过对国外超大口径射电望远镜主焦点换馈方案的调查分析，并结合 $1 1 0 \mathrm { m }$ 射电望远镜的结构参数和设计特点，提出了适用于 $1 1 0 \mathrm { m }$ 射电望远镜的一种前馈馈源换馈方案，此方案特点为：

(1)结构较为简易，便于实现;(2)采用开式丝杆线性模组传动，便于精确定位和平稳传动。开式丝杆线性模组具有设计、安装、维护简便，可靠性高的优点。(3)相较同类型天线主焦馈电机构，对主面遮挡小，定位精度高。整体机构可以通过改进材料降低重量，能达到目前重量的1/3。且在今后望远镜升级过程中，可以添加更多的主焦点馈源。

# 参考文献：

[1] Shen Zhiqiang.The Shanghai $6 5 \mathrm { m }$ RT［R].Beijing：The $6 5 \mathrm { m }$ Radio Telescope Team，2013.  
[2] Nan Rendong，Li Di，Jin Chengjin，et al. The Five-hundred-meter Aperture Spherical RadioTelescope（FAST） project［J]. International Journal of Modern Physics D，2011，20： 989-1024.  
[3] 王娜.新疆奇台110米射电望远镜［J].中国科学：物理学 力学 天文学，2014,44(8)：783-794.Wang Na. Xinjiang Qitai $1 1 0 \mathrm { m }$ radio telescope（in Chinese）［J].Scientia Sinica：Physica,Mechanica & Astronomica，2014，44(8）:783-794.  
[4] Wilson TL，Rohlfs K,Huttemeister S. Tools of radio astronomy [M]. Berlin: Spriger-Verlag,2009: 177-179.  
[5] Wielebinski R，Junkes N,Grahl B H.The Effelsberg 1OO radio telescope：construction and fortyyears of radio astronomy [J]. Journal of Astronomy History and Heritage，2011,14(1）: 3-21.  
[6] Prestage R M,Constantikes K T,Hunter TR,et al. The green bank telescope [J].Proceedingsof the IEEE，2009,97(8)：1382-1390.  
[7] Olmi L，Grueff G.SRT:design and technical specifications [J].Memoriedella Societa Astronomica ItalianaSupplement，2006，10：19-24.  
[8] 成大先.机械设计手册［M].北京：化学工业出版社，2008：1244-1247.  
[9] 朱钟淦，叶尚辉.天线结构设计［M].北京：国防工业出版社，1980：221-222.  
[10] 银秋华，周建寨.反射面天线增益的快速估算［J].无线电通信技术，2013，39(4)：50-52.Yin Qiuhua， Zhou Jianzhai. Quick estimation the gain of reflector antenna ［J].RadioCommunications Technology，2013，39(4）:50-52.  
[11] 肖明，王娜，刘志勇．大气折射对射电望远镜高精度指向的影响［J］．天文研究与技术，2016,13(1) : 44-51.Xiao Ming，Wang Na，Liu Zhiyong. Atmospheric refractions and radio telescope pointingcorrections [J].Astronomical Research & Technology，2016，13（1）：44-51.  
[12] 项斌斌，刘志勇，杨文军.基于FS 系统对乌鲁木齐VLBI射电望远镜进行天线测量［J].天文研究与技术——国家天文台台刊，2014，11(4)：343-349.Xiang Binbin，Liu Zhiyong，Yang Wenjun. Measurement of the antenna characteristics of theVLBI radio telescope of the Urumqi station ［J]. Astronomical Research & Technology

Publications of National Astronomical Observatories of China，2014，11(4）：343-349.

# The Prime Focus Receiver Positioner Design of Xinjiang QiTai 110m Radio Telescope

Zhao Cong $^ { 1 , 2 }$ , Xu Qian¹，Wang Na’， Xiang Binbin1 (1. Xinjiang Astronomical Observatory，ChineseAcademyof Sciences，Urumqi 830ol1,China，Email:zhaocong@ xao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 10oo49，China)

Abstract：With the rapid development of radio astronomy research，the requirements to the sensitivity and resolution of telescopes，as wellas wider observing band，constantly grow.The low frequency receivers are usually installed at the primary focus of the telescope so that the feed horns are smaller and lighter.The switching system of prime focus receivers must be effective and compact to avoid affcting normal use of the receivers on the secondary focus.A steerable 1OOm aperture radio telescope is supposed to be built in Qitai, Xinjiang（QiTai radio Telescope，QTT).This paper introduces a new solution of the switching system for the QTT primary focus receivers by using a linear module.Through the modeling and simulation of this scheme, and analyzing of the aperture interception to the observing signals，it is shown that our design wellsatisfies the efficiency requirement of QTT.

Key Words: Feed switching method； Radio telescope；Primary focus receiver; Linear module