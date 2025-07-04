# 基于低精度布料采样的多精度布料构建方法

钟李涛，侯进，龚随，张娟，唐源皓(西南交通大学 信息科学与技术学院，成都 611756)

摘要：为了兼顾布料仿真的逼真度和计算效率，提出一种基于低精度布料采样的多精度布料构建方法。首先，通过对低精度布料运动仿真实例进行数次采样，获取布料各区域在仿真过程中的平均变形度，用顶点平均变形度和边碰撞标记对其进行表示；再根据平均变形度将低精度网格区域划分为高变形区、中变形区和低变形区；然后利用改进的自适应细分算法对三种变形区进行不同程度地细分，从而构建出低精度布料对应的多精度布料几何模型；最后基于多精度几何模型对布料质点质量和弹簧系数进行定义，得到多精度物理模型。实验结果表明，相对于高精度布料，多精度布料减少了网格数量，提高了计算效率；相对于低精度布料，它又提高了仿真的逼真度。

关键词：布料仿真；多精度网格；区域划分；自适应细分；低精度布料采样 中图分类号：TP391.7 doi:10.3969/j.issn.1001-3695.2017.08.0896

# Multi-resolution cloth construction based on low-resolution cloth sampling

Zhong Litao,Hou Jin†, Gong Sui, Zhang Juan, Tang Yuanhao Schoolof Information Science&Technology,SouthwestJiaotong University,Chengdu 611756,China

Abstract:Inorder totakeintoaccountthefidelityandcomputationalefficiencyofcloth simulation,this paperpresenteda construction methodof multi-resolution cloth basedonlow-resolution cloth sampling.Firstly,through samplinga simulation exampleoflow-resolutioncloth movementseveraltimes,this paperobtained theaverage deformationdegree,whichrepresented bythe aerage deformation degreeofthe vertex andtheedgecollsion mark.Then,according to theresultsof sampling,it divided theregionoflow-resolution into high deformationarea,middle deformationareaand lowdeformation area.Next,it usedthe improvedadaptivesubdivisionalgorithmtorefinethethree deformationareas indiferent extent,soas toconstructthe multi-resolutiogeometricmodel.Finallytroughtedefinitionoftemassadthespringcoficientofthecloth,itobtaied the multi-resolution physical model.This paperreduces mult-resolution grid numberand improves computational effciency relativeto the high-resolution grid.It also improves the fidelityofcloth simulation compare to the low-resolutiongrid.

Key Words:cloth simulation; multi-resolution mesh; region division; adaptive subdivision;low resolution cloth sampling

# 0 引言

在虚拟服装仿真系统中，随着计算机图形学的不断发展，虚拟现实成为21世纪迅速崛起的一个新兴产业，而其中的布料仿真技术也逐渐成为研究的热点。布料作为一种轻柔灵活的特殊材质，在外力的作用下易发生复杂形变，快速逼真地模拟形变产生的褶皱成为布料仿真技术中的难点之一。一种理想的布料模拟方法是对其进行高精度建模，即用高密度的网格对布料进行几何建模，但这种高密度的网格往往包含上万个几何图元，这在增加计算机的计算负担的同时也会占用大量的内存资源。为了在不增加计算代价的同时展示布料逼真的褶皱效果，一些有效的褶皱增强的方法相继被提出。Cutler 等人[1]在衣服表面相应位置标记褶皱基线，最终根据褶皱基线、自定义的褶皱形状以及褶皱半径生成三维褶皱。Rohmer等人[2]也是基于褶皱基线对褶皱进行模拟，其中褶皱基线根据粗网格仿真效果的分析得到，该方法更具有客观性。Zurdo 等人[3]从另一个角度出发，结合低精度布料和高精度布料仿真实例，提出了一种快速模拟逼真皱褶的方法。此外，Jing 等人[4基于粗糙网格也提出了一种褶皱增强算法。这些褶皱增强的方法虽然更加逼真地模拟了布料细节特征，但是只适用于静态布料。为了真实地模拟布料动态过程中的褶皱效果，Li等人[5提出了一种基于三角网格自适应细分和简化的布料仿真方法，该方法采用曲率准则对网格进行细分和简化，并结合Baraff模型对服装动画效果进行了模拟。Simnett等人[从边的角度出发，提出了一种基于网格边的自适应网格细分和简化的布料仿真方法。一种较新颖的方法是Lee等人[7提出的逆向简化自适应网格法，该方法首先通过Loop曲面细分[8建立高精度布料模型，然后通过简化动态平坦区域降低网格数量。除此之外，还有大量的研究工作[9-12]基于自适应网格法对动态布料进行了仿真。

另外一种常用的动态布料模拟方法为实例数据法[13\~15],该方法基于视频数据和实际的运动数据重构动态的服装效果。为了提高服装模拟的实时性，Aguiar等人[16提出了增广线性动力学系统，对服装动画进行了快速稳定的合成。Wang 等人[17]则利用大量实例数据模拟了服装褶皱。为了预测布料的运动趋势，石敏等人[18]提出了一种基于实例数据分析的多精度网格布料动画方法，该方法构建的多精度布料在类似运动驱动下可以得到较好的细节变形特征，有效地提高了计算效率，但提取弯曲变形模式会耗费大量时间。

自适应网格法在布料仿真过程中需要不断地更新网格的拓扑结构以及受力关系，计算复杂且连续性较差。实例数据法根据数据合成动画的过程会消耗较多的时间。针对这些问题，本文提出一种基于低精度布料采样的多精度布料构建方法。该方法的主要思想是：通过对一段低精度布料仿真实例中的布料网格各区域变形度进行采样分析，从而将布料模型划分为高变形、中变形和低变形区域；然后利用改进的自适应细分算法对高变形区进行一次或两次细分，对中变形区进行一次细分，低变形区不进行细分，从而构建出适用于类似运动的多精度布料模型。该方法预处理时间短，计算复杂度低，构建的多精度布料在类似运动驱动下的仿真中能较好地保持褶皱细节，同时还可以通过调节变形区域划分阈值来控制仿真逼真度和计算效率。

# 1 平均变形度获取

本文虽然布料在外力作用下变形复杂，但是在同一种运动下布料网格的变形区域分布情况相同。例如人体着装行走时，服装产生褶皱的区域主要分布在腰部以及与腿部产生碰撞的区域。同时，布料在稳定外力作用下，即在没有瞬时较大外力下其褶皱变形的产生及变化都相对稳定[18]。基于此，为了快速有效地获得布料网格区域在指定运动下的变形度，本文通过对一段指定运动模式下的低精度布料变形度进行采样分析，获得布料网格区域在此段运动仿真过程中的平均变形度。然后根据采样数据处理结果对布料各区域的变形情况进行预测并划分。

# 1.1布料变形度表示

# 1.1.1顶点权重变形度

布料运动过程中的褶皱区域就是三角网格中变形的区域，为了刻画网格区域的变形程度，可以选择常用的高斯曲率作为衡量标准，但是高斯曲率计算复杂且鲁棒性差[8]。另一种常用的衡量标准是二面角[19]，即两个三角面之间的夹角。虽然二面角的计算复杂度比高斯曲率低，但是准确度却更低。为了更加准确地度量网格区域的变形程度，本文在结合高斯曲率和二面角两种标准优点的基础上，充分考虑三角面片的面积对变形程度的影响，提出了基于三角形面积权重的顶点变形度，简称顶点权重变形度。

首先定义网格顶点的单位法向量：

$$
n _ { \nu } = { \frac { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i } } { \displaystyle \left\| \sum _ { i = 1 } ^ { N } u _ { i } \right\| } }
$$

其计算方法是将顶点相邻面的法向量 $u _ { i }$ 求和后再进行单位化，其中 $N$ 为顶点相邻面的个数，符号 $\Vert \ \Vert$ 表示对向量的求模运算。

三角网格中的顶点权重变形度定义为

$$
F _ { \nu } = \frac { 1 } { S _ { t o t a l } } \sum _ { i = 1 } ^ { N } \Bigl [ \bigl ( \pmb { n } _ { \nu } \cdot \pmb { N } _ { i } \bigr ) \times S _ { i } \Bigr ]
$$

其中： $N$ 为顶点相邻面的个数； $S _ { t o t a l }$ 为顶点相邻面的面积总和；${ \pmb n } _ { \nu }$ 为顶点的单位法向量； $\mathbf { \delta } _ { N _ { i } }$ 为顶点第 $i$ 个相邻面的法向量； $S _ { i }$ 为顶点第 $i$ 个相邻面的面积；符号·表示点积。顶点1邻域区域几何信息如图1所示。

![](images/83261f7d920940fc7eaf4d942dac281920758546a68c43a027b73e95a9e75d55.jpg)  
图1顶点1邻域示意图

根据顶点权重变形度的定义可知，如果顶点1邻域区域变形程度越低，那么顶点的单位法向量和其相邻面的单位法向量就越接近于平行状态，这样顶点权重变形度就越接近于1；相反，如果顶点1邻域区域变形程度越高，则顶点权重变形度就越接近于0。

# 1.1.2边碰撞标记

除了用顶点权重变形度表示网格变形度外，本文还将对发生碰撞的边进行标记，如图2（a）所示。因为在边与对象发生碰撞处的网格区域也应该发生形变，这时也需要对该区域的碰撞边进行细分，这样才能更逼真地展示仿真效果，如图2（b)所示。在构建多精度几何模型的时候，被标记的边将参与细分。

![](images/4c03f0d6a7ffa90ced8fb67f5d7846e63b8e64bcbefa18fc526f0da76c43e04d.jpg)  
图2碰撞边标记示意图

# 1.2变形度采样及处理

为了减少数据采样和处理的时间，提高计算效率，本文将选择对低精度布料动态过程中每个顶点的顶点权重变形度进行

$K$ 次采样。采样次数 $K$ 根据低精度布料仿真过程中的变形复杂度确定。在整个仿真过程中，如果布料变形形式多变且复杂，采样次数则取较大值；相反，则取较小值。本文选取的采样次数 $K$ 远小于动态仿真总的帧数。仿真过程中的布料不是在每两帧之间都会出现大幅度的形变，每个形变的状态都会持续一段时间，在这种形变状态变化前对它进行一次采样就可以得到变形的特征。

设低精度布料仿真过程中第 $i$ 个顶点在第 $k$ 次采样得到的顶点变形度为 $F _ { i } \left( k \right)$ ，则该顶点在 $K$ 次采样后得到的平均变形度为

$$
\overline { { F _ { i } } } = \frac { \displaystyle \sum _ { k = 1 } ^ { K } F _ { i } \left( k \right) } { K }
$$

本文将处理后的顶点平均变形度作为衡量低精度布料顶点1邻域区域在整个仿真过程中变形大小的标准，然后再根据它与细分阈值的大小关系确定该顶点将参与几次细分。

# 2 多精度布料模型的构建

# 2.1多精度几何模型的构建

本文采用基于顶点平均变形度和边碰撞标记的自适应细分算法，细分方式基于Loop 细分模式。下面对自适应细分算法中相关的定义进行说明。为了将网格区域划分为三种变形区域，首先需要设置两个阈值参数 $\beta _ { 1 }$ 和 $\beta _ { 2 }$ ， $\beta _ { 1 } \leq \beta _ { 2 }$ 且其大小介于0、1之间。当顶点的平均变形度 $\overline { { F } }$ 小于 $\beta _ { 1 }$ 时，则将该点的活性置为2；大于 $\beta _ { 2 }$ 时，活性置为0；介于两者之间时，活性置为1。若三角面三个顶点的活性之和大于3时，则该三角区域划分为高变形区；小于等于3且大于0时，则划分为中变形区；等于0时，则划分为低变形区，本文对高变形区进行一次或两次细分，中变形区进行一次细分，低变形区不进行细分。

当点的活性为0时，则称为固点。当网格边的两个端点活性之和等于0时，则称该边为固边，不等于0时称为活边；当网格边被标记为碰撞边时，该边也为活边；当网格三角面三个顶点都为固点时，则该面为固面，其他情况则为活面。在细分过程中，固点、固边和固面都不进行细分。根据以上定义可知，顶点的平均变形度、碰撞边的标记情况以及设置的阈值控制着整个网格的自适应细分情况。

算法改进的自适应细分算法

a)在网格的顶点、边和面对象产生的时候，将它们分别标记为固点、固边和固面。

b)遍历三角网格顶点，将低精度网格采样处理后的平均变形度赋值给对应的顶点，然后根据顶点平均变形度与阈值参数的大小关系，更新点的活性。

c)遍历网格所有三角面，根据三角面所含的固点的个数以及碰撞边标记情况更新边和面的活性。

d)根据Loop细分模式新顶点的计算公式更新所有顶点的位置。

e)计算新边点。对于固边，不计算新边点；对于活边，根据Loop 细分模式新边点的计算公式计算新边点，并将其活性设置为两端点活性的平均值。

f)产生新面。对于固面，不进行细分；对于活面，其细分方式根据所含活点的情况按图3所示的方式进行细分。

g）遍历所有顶点，将其活性减去1，如果顶点活性小于0,则置为0。

h)若只对高变形区进行一次细分，则结束细分；若对高变形区进行多次细分且存在顶点的活性减1后还大于0，则转d)继续执行。

![](images/56f6941100e5077b35703624b5178af6e7b0b7dfe99b665d8eee8371a6887967.jpg)  
图3活面细分示意图

图3（a）为细分前的原始网格，（b）和（c）是面包含两条活边时的细分情况。当顶点的平均变形度大于 $V _ { 0 }$ 的平均变形度，按图3（b）所示进行细分，反之则按图3（c）所示进行细分。图3（d）为三条活边时的细分情况，此时为标准的Loop 细分模式。

# 2.2多精度布料模型参数

2.2.1质点质量

本文采用质点弹簧模型作为力学模型。只要布料模型的大小确定，低精度布料模型和多精度布料模型的质量应该是相同的。但是多精度布料模型的质点分布不均匀，若其中的每个质点的质量都一样，多精度网格模型的质量必然大于低精度网格质量，这就会违背质量守恒原则，构建的多精度网格布料模型在仿真中也会变形失真。为了让布料保持现实中的质量属性，本文根据质点影响域的大小确定其质量。

设布料的密度为常数 $\rho$ ，质点 $i$ 的影响域 $A _ { i }$ 定义为质点相邻三角面面积总和的三分之一，即

$$
A _ { i } = \frac { 1 } { 3 } \sum _ { j = 1 } ^ { k } A _ { j }
$$

其中：为该质点相邻三角面的个数， $A _ { j }$ 为质点第 $j$ 个相邻面的面积。

计算质点的影响域后，其质量 $m _ { i }$ 就可近似为

$$
m _ { i } = \rho \times \tau \times A _ { i }
$$

其中： $\tau$ 为布料模型的厚度，本文取 $\tau = 1$ 。

# 2.2.2弹簧弹性系数

在多精度网格模型中，不同区域的网格大小是不同的，所以在构建多精度网格力学模型时，不同长度的弹簧需要使用不同的弹性系数。一般情况下，弹簧弹性系数大小和弹簧的长度成反比。为了防止弹簧过度拉伸而产生“超弹性”现象，本文采用分段线性弹性力计算的方法，如下面公式所示：

$$
F _ { 1 } = l \times k _ { 1 } \quad ( l < \tau )
$$

$$
F _ { 2 } = \tau \times k _ { 1 } + ( l - \tau ) \times k _ { 2 } ( l > \tau )
$$

当弹簧形变量 $l$ 小于设定的阈值 $\tau$ 时，弹簧力为 $F _ { 1 }$ ；当弹簧形变量i大于设定的阈值 $\tau$ 时，弹簧力为 $F _ { 2 }$ 。其中 $k _ { 1 }$ 和 $k _ { 2 }$ 分别为两个大小不同的弹性系数。该方法通过设置两个不同大小的弹性系数来模拟现实环境中弹簧力和弹簧形变度之间非线性的关系，如图4所示。

# 4 本文算法框架

本文算法总体框架如图6所示，主要分为预处理和动态模拟两个阶段。在预处理阶段，首先对一段低精度布料仿真实例中网格区域的变形度进行采样,同时标记碰撞边；然后将采样数据进行处理得到网格区域在整个仿真过程中的平均变形度。根据平均变形程度将网格划分为高变形、中变形和低变形区，接着采用改进的自适应细分算法对三种区域进行细分，从而得到多精度网格几何模型。在动态模拟阶段，需要对多精度网格的质点质量和弹簧系数进行定义，然后再添加重力或者风力作用，最后对人体构建椭球包围盒并对布料质点与包围盒的碰撞进行处理，就可得到多精度布料仿真效果。

![](images/7a99b1fc3d5e21e866c4c226fe39b478362c35d69ff1164881f6f6373a9f9346.jpg)  
图4分段线性弹性力

# 3 碰撞检测与响应

鉴于本文中的碰撞处理分为两种情况：一是布料和小球的碰撞处理，二是服装和人体模型的碰撞处理。其中布料与小球的碰撞检测和响应算法较为简单,这里不再赘述，关键点在于处理布料边与小球的穿透。本文采用膨胀算法对小球进行膨胀，用膨胀后的小球半径参与碰撞检测和响应计算就可以消除边穿透现象。

在处理服装和人体模型的碰撞时，为了提高仿真的实时性，本文在文献[20]的算法基础上进行改进，即采用椭球包围盒对人体模型进行自适应拟合估计，在动态仿真过程中，用这些椭球包围盒完全代替人体模型进行运动并与服装之间进行碰撞处理。椭球包围盒的自适应构建结果以及运动示意图如图5所示。

![](images/6879113f0ddea34b03faf6c51a4b7f767ec442d55bc69c8f287f9e30c394a337.jpg)  
图5椭球包围盒的构建及运动示意图

![](images/f8d7e94b7f0d4b00bae205153310cb26df4c8cb46785829dab4581801bd4c7f6.jpg)  
图6算法总体框架

# 5 实验结果及分析

本文采用布料和两种裙装模型进行实验，实验条件分为三种情况：a)让小球和布料进行碰撞，其中布料的四个角被固定；b)为裙子的裙摆部分添加风力，裙子的上半部分被固定；c)人体着装运动。本实验为了兼顾仿真的实时性，在自适应细分时将高变形区和中变形区只进行一次细分；后面与文献算法对比实验时则将高变形区进行两次细分。在算法对比中本文使用另外两种场景进行实验对比分析，具体见5.3节。通过对比不同精度网格模型的仿真效果和效率，对本文方法进行分析。同时也将本文方法与文献[9]、文献[18]中的方法进行对比分析。其中，布料仿真的数值计算采用文献[21]提出的方法。本文实验环境为Inter(R)Core(TM)i3-2350MCPU@2.30 GHz，编译环境为VS2010，采用 $\mathrm { C } { + } { + }$ 语言编写代码。

# 5.1构建多精度网格模型

本文使用布料模型及两种裙装模型进行实验，其中两种裙装模型分别称为裙子1和裙子2。实验首先对低精度布料仿真中的网格变形度进行指定次数的采样，将采样结果进行平均处理后根据划分阈值就可将布料网格区域划分为低变形、中变形和高变形区。表1给出了低精度布料仿真中不同模型面的数量、采样次数及仿真耗时，相应的仿真效果和区域划分结果如图7所示。划分阈值按模型先后顺序分别设置为0.99和0.98、0.97和0.96、0.96和0.95。

![](images/c8f5d1dcda57f7dc8141612f0bf0a17182a10972bf7049ca3a9d4b97756b4b5a.jpg)

表1低精度模型仿真数据  

<html><body><table><tr><td>模型</td><td>三角面数</td><td>采样次数</td><td>仿真帧数</td><td>总耗时/s</td></tr><tr><td>布料</td><td>320</td><td>20</td><td>1021</td><td>19.323</td></tr><tr><td>裙子1</td><td>606</td><td>15</td><td>363</td><td>16.522</td></tr><tr><td>裙子2</td><td>843</td><td>15</td><td>165</td><td>31.772</td></tr></table></body></html>

图7（a）为三种模型低精度布料仿真效果图，（b）为三种模型对应变形区域划分结果图。其中红色区域表示在整个低精度布料仿真期间的高变形区，绿色和深黄色分别表示中变形和低变形区。由于布料和小球碰撞以及裙装1在风力作用下的运动较为复杂，所以变形的区域较多，实验结果图7也证明了此分析。图7（b）中将裙子2与腿部碰撞的部分及腰部等区域划分为中、高变形区，符合实际人体着装情况，由此说明本文对低精度布料变形区域的提取方法有效，从而较准确地对低精度网格区域进行了划分。

根据网格变形区域划分结果，利用改进的自适应细分算法对网格不同区域进行不同程度地细分。低变形区不进行细分，高变形区和中变形区进行一次细分，这样就得到了三种实验模型各自的多精度网格几何模型，如图8所示。本实验在自适应细分过程中针对不同的模型设置不同细分阈值。布料和裙子1的自适应细分阈值分别设置为0.99和0.97，对于裙子2模型，这里使用两种自适应细分阈值来进行细分对比，图8（c）中阈值为0.96，（d）为0.95。

![](images/6d00b84cea7f73ae0dae8384787a2d4dd99d672e51530d513139b529eeefab97.jpg)  
(a)布料低精度和多精度网格对比

![](images/5ee9cbb0ece6d7939c6f31beb32f13da9eea2c242450964b6b51506e79388f2f.jpg)

图7低精度布料仿真效果及区域划分  
图8低精度和多精度几何模型对比

![](images/59b46dd24961eaf0ad1f15bcf9e55d294f9e37ba690cefefb2cb790b7437a7db.jpg)  
(b)裙子1低精度和多精度网格对比

对比图8（c）和（d）可以知道使用不同的细分阈值可以控制高精度网格占整个多精度网格的比重，满足不同应用背景对模拟效果和效率的不同需求。结合图7（a）和图8可以看出，多精度网格中网格分布密度与实际过程中的网格区域变形度具有一致性。这说明了本文提出的顶点权重变形度能够有效地衡量网格不同区域的变形程度，同时顶点的平均变形度可以作为网格区域在整个仿真过程中变形程度的衡量标准。综上所述，本文提出的方法能够有效地对动态仿真过程中的变形区域进行划分，在结合改进的自适应细分算法的基础上，能够正确地构建多精度网格几何模型。

# 5.2仿真效果及效率对比

本文使用布料和两种裙装模型的低精度网格、多精度网格和高精度网格三种精度网格进行动态仿真对比分析。对比分析的内容包括不同精度模型的仿真效果以及仿真效率。为了能准确对比分析仿真的结果，本文选用网格面数、帧频、步长、每帧仿真时间以及仿真总耗时五个指标作为参考指标。本文实验仿真数据如表2所示，仿真效果如图 $9 \sim 1 2$ 所示。

表2不同精度模型仿真数据  

<html><body><table><tr><td>模型</td><td>网格密度</td><td>帧频/fps</td><td>步长</td><td>平均每帧耗时/ms</td><td>总耗时/s</td></tr><tr><td rowspan="3">布料</td><td>低精度</td><td>55.6</td><td>0.005</td><td>18</td><td>19.323</td></tr><tr><td>多精度</td><td>5.8</td><td>0.0016</td><td>172</td><td>284.539</td></tr><tr><td>高精度</td><td>2.9</td><td>0.0017</td><td>343</td><td>380.375</td></tr><tr><td rowspan="3">裙子1</td><td>低精度</td><td>22.2</td><td>0.014</td><td>45</td><td>16.522</td></tr><tr><td>多精度</td><td>3.1</td><td>0.0025</td><td>322</td><td>359.130</td></tr><tr><td>高精度</td><td>1.9</td><td>0.0015</td><td>512</td><td>798.797</td></tr><tr><td rowspan="3">裙子2</td><td>低精度</td><td>5.2</td><td>0.015</td><td>190</td><td>31.772</td></tr><tr><td>多精度</td><td>1.3</td><td>0.006</td><td>763</td><td>117.538</td></tr><tr><td>高精度</td><td>0.3</td><td>0.0048</td><td>3027</td><td>454.180</td></tr></table></body></html>

![](images/5b381805b05ff0b45a691b3ce866a26a541c2b6ce5b400e0926999aebe478e56.jpg)

![](images/07e0301b0735eaf604b7b39ff4c5e4d63287dd4c6a2b5b9558e1a1f025a4d947.jpg)  
图10不同精度的裙子1仿真对比

![](images/d75525f65b6f625b1be3bcb7b7c7fa993bab4bcdf744f6a5ffbdb529db83c41f.jpg)  
图11不同精度的裙子2仿真正面对比  
图12不同精度的裙子2仿真侧面对比

本文从低精度网格模型的仿真效果图9(a）、10(a）、11（a)及12（a）可以看出，低精度网格仿真视觉效果较差，整个模型表现出刚性，丢失了大量的细节褶皱信息。对比图9(b)和（c)可知，多精度布料网格仿真效果和高精度网格仿真效果比较接近，都在布料的正前方处出现了较为逼真的褶皱。从图10（b)可知，在风力作用下，多精度裙子模型也较好地展示了皱褶变形，提高了仿真的逼真度。对比图11（b）和（c）可知，由于多精度网格在服装的腰部以及腿部区域采用的高密度网格，所以多精度裙装模型和高精度裙装模型的整体仿真效果很接近，都在腰部以及腿部产生了褶皱变形。由此可知，基于低精度布料采样的多精度布料构建算法能较好保留布料高变形区域的细节信息，提高仿真的逼真度。

多精度和高精度网格三角面数对比如图13所示，多精度和高精度网格每帧仿真时间对比如图14所示。

![](images/46256239adf2d2642af2779a755188fcddbcff4a9dfbcb5397d8eb9fe8d2a70b.jpg)  
图13多精度和高精度网格三角面数对比  
图14多精度和高精度网格每帧仿真时间对比

高精度模型A多精度模型/ 42%200布料1 裙子1 裙子2

从表2中的仿真数据可知，低精度布料仿真帧频高，仿真步长大，每帧仿真时间短，总耗时少，计算效率高，但从其仿真效果图9（a）、10（a）、11（a）及12（a）可知,它在仿真中会丢失大量的褶皱细节。结合表2、图13、14可以看出，多精度网格的三角网格数以及平均每帧仿真时间都比高精度网格少，帧频和计算效率也更高，同时步长很接近。与高精度布料相比，多精度布料面片降低了 $3 1 . 7 \%$ ，帧更新频率提高了1倍，每帧仿真频率提高约 $50 \%$ ；多精度裙子1的面片数降低了 $23 . 1 \%$ 帧更新频率提高了约0.5倍，每帧仿真效率提高了近 $40 \%$ ；多精度裙子2的面片数降低了 $45 . 8 \%$ ，帧更新频率提高了4倍，每帧仿真效率提高了约 $7 5 \%$ 。总的来说，本文构建的多精度网格在计算效率和更新效率上都比高精度网格更优，基于此分析，本文构建的多精度布料模型有效的提高了布料的仿真效率。

# 5.3 算法分析与对比

为了验证本文方法的优越性，将本文方法与文献[9]和文献[18]的方法进行对比。表3为本文方法与文献[9]提供的开源系统 ArcSim的仿真运行时间及帧频对比。其中对比的场景为同一块布料分别与一个小球和两个小球在重力作用下进行碰撞仿真，本文称为场景1和2。图15为相应的仿真效果对比。其中图15（a）科（b）为使用本文方法构建的对应于场景1和2的多精度网格。表4为本文方法和文献[18]方法对比结果，对比模型选用裙子1和布料模型。文献[9]与本文方法remesh总耗时对比如图16所示。

由表3可知，在低精度布料实例仿真采样及多精度模型构建阶段本文方法会花费较长时间，但因为这些操作在整个仿真过程中只进行一次，所以对仿真性能影响较小。而文献[9]的方法需要在布料每帧计算中根据布料变形程度和边碰撞情况对网格进行动态细分和简化，这不仅影响了仿真的连续性，而且还影响了计算效率。结合表3和图16可以看出，本文方法的帧频较文献[9]的方法更高，这表明本文方法的连续性更好；同时，从图16（a）和（b）可以看出，本文方法在不同的场景中预处理的耗时是一定的，与文献[9]中动态remesh操作耗时相比，使用本文方法的计算效率明显更高。例如在场景1中，仿真帧数超过50帧后，本文算法就表现出其优越性；场景2中，仿真帧数超过35帧后，本文算法计算效率就更高。由此可知，当场景的仿真帧数越大时，本文方法的优势就越明显。同时，由图15(c） $\sim$ （f)可以看出，本文方法构建的多精度布料仿真效果和采用文献[9]方法得到的布料仿真效果逼真度相近，都较好地展示了布料的褶皱细节。综上所述，本文方法相比文献[9]的方法更优。

表3本文方法和文献[9]方法仿真时间对比  

<html><body><table><tr><td rowspan="2">场景</td><td rowspan="2">使用方法</td><td rowspan="2">采样及预 处理时间/s</td><td rowspan="2">帧频/fps</td><td rowspan="2">平均每帧 remesh 时间/s</td></tr><tr><td></td></tr><tr><td rowspan="2">场景1</td><td>文献[9]</td><td>0</td><td>0.68</td><td>1.475</td></tr><tr><td>本文方法</td><td>22.195</td><td>7.3</td><td>0</td></tr><tr><td rowspan="2">场景2</td><td>文献[9]</td><td>0</td><td>0.63</td><td>1.589</td></tr><tr><td>本文方法</td><td>16.613</td><td>4.3</td><td>0</td></tr></table></body></html>

如表4所示，本文是对运动的低精度布料采样，采样对象的网格数分别为320和606，而文献[18]是对运动的高精度布料采样，采样对象的网格数为2424和1280，本文算法计算量明显更小。本文针对裙子和布料模型分别进行了15次和20次采样，而使用文献[18]的方法则需要对模型分别进行1560次和1108 次采样，采样操作耗时是本文方法的近百倍。此外，本文在对采样数据进行处理时，使用计算复杂度较低的平均算法，降低了计算消耗。综上所述，本文构建多精度网格几何模型的算法计算效率优于文献[18]中的算法。

![](images/9bb08b48e687137cf4eb37d5e33948d9b35b2e627e12ac880a5a7d2df676c7c0.jpg)  
图15文献[9]与本文仿真效果对比

![](images/c066c19b289bfea330ec664dfd06f8b10d75730e3e01354674e0064d35868371.jpg)  
图16文献[9]与本文方法remesh总耗时对比

# 6 结束语

本文针对布料动态仿真的逼真度和效率问题，提出一种基于低精度布料采样的多精度布料构建方法。与高精度布料仿真相比，本文构建的多精度布料在保持较多的细节特征的同时提高了计算效率；与低精度布料相比，多精度布料显著地提高了布料仿真的逼真度。同时本文方法可以根据逼真度和效率的不同需求，通过调节细分阈值灵活地控制不同区域的网格精度。

但是与经典动态自适应算法[10]相比，本文方法仍存在局限性：a)不太适合复杂程度较高的运动驱动模式，即当布料运动太过于复杂多变时，本文方法的计算效率会下降；b)需要人工参与前期的预处理，即自适应细分时需要键入命令执行细分程序，灵活性还有待提高；c)只适用于类似运动驱动的布料仿真，即低精度布料采样时的运动驱动模式和利用本文方法构建出的多精度布料进行仿真时的运动驱动模式应该类似，否则将会失效。因此，如何提高算法的适应性和灵活性是未来的研究重点。

# 参考文献：

表4本文方法和文献[18]方法对比结果  

<html><body><table><tr><td>模型</td><td>采样方法</td><td>采样对象网格数</td><td>采样次数</td><td>采样数据处理方法</td></tr><tr><td rowspan="2">裙子1</td><td>文献[18]</td><td>2424</td><td>1560</td><td>数据聚类</td></tr><tr><td>本文方法</td><td>606</td><td>15</td><td>数据平均</td></tr><tr><td rowspan="2">布料</td><td>文献[18]</td><td>1280</td><td>1108</td><td>数据聚类</td></tr><tr><td>本文方法</td><td>320</td><td>20</td><td>数据平均</td></tr></table></body></html>

[1]Cutler L D,Gershbein R,Wang X C,et al.An art-directed wrinkle system for CG character clothing [Cl//Proc of ACM SIGGRAPH//Eurographics Symposium on Computer Animation.New York:ACMPress,20o5:117-125   
[2]RohmerD,Popa T,Cani MP,etal.Animation wrinkling: augmenting coarse cloth simulations with realistic-looking wrinkles [J].ACM Transactions on Graphics,2010,29 (6):article No.157   
[3]Zurdo JS,Brito JP, Otaduy MA.Animating wrinkles by example on nonskinned cloth [J]. IEEE Trans on Visualization and Computer Graphics, 2013,19 (1): 149-158.   
[4]Jing M,He B,Lvy Y. Cloth wrinkle enhancement based on the coarse mesh simulation [C]//Proc of 14th International Conference on Smart Homes and Health Telematics.Switzerland: Springer International Press,2O16: 293-301.   
[5]Li L,Volkov V. Cloth animation with adaptively refined meshes [C]//Proc of the 28th Australasian Computer Science Conference.Darlinghurst: Australian Computer Society Press,2005:107-114.   
[6]Simnett T JR,Laycock S D,Day A M.An edge-based approach to adaptively refining a mesh for cloth deformation[C]//Proc ofthe 7th Theory and Practice of Computer Graphics Conference.Geneve: Eurographics Association Press,2009: 77-84.   
[7]Lee Y,Yoon S,Oh S,et al. Multi-resolution cloth simulation [J]. Computer Graphics Forum,2010,29(7): 2225-2232.   
[8]Wu JHS,Liu W J, Wang TR.Adaptive refinement scheme for subdivision surfaces based on triangular meshes [C]// Proc of the 9th International Conference on Computer Aided Design and Computer Graphics.Los Alamitos: IEEE Computer Society Press,2005: 119-124.   
[9]Narain R, Samii A, O'Brien JF.Adaptive anisotropic remeshing for cloth simulation [J].ACM Trans on Graphics,2012,31(6): 1-10.   
[10]De Oliveira SMF,Vidal CA,Cavalcante-Neto JB.Cloth simulation with triangular mesh adaptivity[C]//Proc of the 27th SIBGRAPIConference on Graphics,Patterns and Images.Los Alamitos: IEEE Computer Society Press, 2014:235-242.   
[11] Narain R,Pfaff T, O'Brien JF.Folding and crumpling adaptive sheets [J]. ACM Trans on Graphics,2013,32 (4):1-8.   
[12]Koh W,Narain R,O'Brien JF.View-dependent adaptive cloth simulation with buckling compensation [J].IEEE Trans on Visualization and Computer Graphics,2015,21(10):1138-1145.   
[13] White R,Crane K,Forsyth DA.Capturing and animating occluded cloth [J]. ACM Trans on Graphics,2007,26(3):34.   
[14] SumnerRW,Popovic'J.Deformation transfer for triangle meshes [J].ACM Trans on Graphics,2004,23 (3):399-405.   
[15] Bradley D,Popa T, ShefferA,et al.Markerless garment capture [J].ACM Trans on Graphics,2008,27(3):Article No.99.   
[16] De Aguiar E, SigalL,Treuille A,et al. Stable spaces for real-time clothing [J].ACM Trans on Graphics,2010,29 (4): 1-9.   
[17]Wang H M,Hecht F,Ramamoorthi R,et al.Example-based wrinkle synthesis for clothing animation [J].ACM Trans on Graphics,2010,29 (4): 1-9.   
[18]石敏，毛天露，王兆其．基于实例数据分析的多精度网格布料动画[J]. 计算机学报,2015,38(6):1296-1306.   
[19]李桂清，吴壮志，马维银．自适应细分技术研究进展[J].计算机辅助 设计与图形学学报,2006,18(12):1789-1798.   
[20]唐勇，杨偶偎，吕梦雅．自适应椭球包围盒改进织物碰撞检测方法[J]. 计算机辅助设计与图形学学报,2013,25(10):1589-1596.   
[21]王崴，周诚，杨云，等．基于改进弹簧-质点模型的柔性绳索仿真 [J].计算机辅助设计与图形学学报,2015,27(11):2230-2236.