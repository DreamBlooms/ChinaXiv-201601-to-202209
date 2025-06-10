# 二维U型弯管流动中湍流模型的性能研究

王 菁1雍小松1柳阳威1,2 陆利蓬1,2(1．北京航空航天大学能源与动力工程学院航空发动机气动热力国家级重点实验室，北京，100191;2．先进航空发动机协同创新中心，北京100191)

摘要采用 FLUENT中8个湍流模型以及曲率修正后的模型对U型弯管中的二维流动进行了模拟，详细对比了两个雷诺数 $1 0 ^ { 5 }$ 和 $1 0 ^ { 6 }$ 下速度、湍动能、湍流剪切应力、摩擦系数和静压力系数的实验和模拟结果。研究发现，当$R e = 1 0 ^ { 5 }$ ，Realizable $k - \varepsilon$ 模型、Spalart-Allmaras模型、RNG $k - \varepsilon$ 模型能准确模拟出流动分离的位置；当 $R e { = } 1 0 ^ { 6 }$ 新所有模型预测到的分离位置都滞后。曲率修正对 SKE 以外的湍流模型预测性能基本上没有改善;SKE 模型对曲率修正的影响最为敏感，对速度、湍动能、内壁面处的摩擦系数的模拟结果都有一定的改善。

关键词湍流模型；U型弯管；数值模拟；曲率流动中图分类号：TK05 文献标识码：A 文章编号：0253-231X(2017)04-0710-09

# Performance Study of the Turbulence M6dels in a Two-dimensional U-bend Du

WANG Jing1 YONG Xiao-Song1LIU Yang-Wei $^ { 1 , 2 }$ LU Li-Peng $^ { 1 , 2 }$ （20 (1. National Key Laboratoryof Science and TechnologyAero-Engine Aero-Thermodynamics,Scholof Energyand power Engineering,BeihaDg University，Beijing l00191, China 2. Collaborative Innovation Ceter of Advanced Aero-Engine,Beijing 100191, China)

AbstractThe flow in 2D of thejDend is simulated, with eight common turbulence models and curvature correction model respeetively. By comparing the simulation and experimental results of velocity， turbulence kinetic ergy, turbulent shear stress， friction coefficient and static pressure coefficient under two kihds of Reynolds number $1 0 ^ { 5 }$ and $1 0 ^ { 6 }$ , it is find that the Realizable $k - \varepsilon$ model, Spalart-Allmaras model and RNG $k - \varepsilon$ model have a good simulati6n results about the position of the flow separation when the Reynolds number is $1 0 ^ { 5 }$ . BesidesXthe separation positions predicted by all models are lagging behind. The models with curvature correction are not better than before expect SKE. The model of SKE is more sensitive to the mfdence of curvature, and there is a greater improvement on simulation about velocity and turbulence kinetic energy.

Key wordsturbulence models; U-bend; numerical simulation; curvature flow

# 0引言

航空发动机和燃气轮机（简称“两机"）应用广泛，发展先进“两机”技术，对动力、节能、减排、降噪等都有重大意义。设计高性能“两机”，离不开先进的CFD手段、目前，准确预测“两机”内的复杂流动 (如大尺度分离等)对当前CFD提出了巨大的挑战。DNS、LES、hybridLES/RANS等高精度方法由于计算耗费太大而无法应用于日常工程设计，而工程广泛应用的RANS方法存在湍流模型模拟准确性的问题[1]。

现有湍流模型主要分为两大类：一类是以Boussinesq涡黏性假设为基础的涡黏性模型；另一类是雷诺应力模型 (RSM)。尽管RSM 模型能够模拟出一些局部典型复杂流动现象，但是由于仍然留有固有的物理不足，以及收敛性不好，较大的复杂性和计算量等多种原因，至今难以应用于航空发动机的研制。而涡黏湍流模型都是基于简单边界、平衡湍流、各向同性假设发展起来的。航空发动机中的流动非常复杂，存在着大分离流动和复杂涡系，常处于湍流非平衡、各向异性的状态，使得常用涡黏模型难以准确模拟。大曲率是航空发动机中流动复杂的主要影响因素之一，而常用涡黏湍流模型没有考虑曲率对流动的影响。在这种背景下，Spalart 和 Shur[2]提出了一种曲率修正方法，并有效提高了Spalart-Allmaras 模型的精度。Smirnov 和 Menter[3] 把这一修正方法应用到了SST $k { - } \omega$ 模型中，也有效提高了该模型的精度。但到目前为止，对大曲率流动中常用湍流模型性能的系统研究还较少，亟需进一步开展深入研究。

U 型弯管流动很好地体现了大曲率对流动的影响，因此成为了研究曲率影响的经典流动。其中NASA 的 Monson 等[4,5] 对 U 型弯管流动进行了详细的实验测量，提供了丰富的流场数据。本文针对该二维U型弯管流动，采用最常用的8个湍流模型对其进行数值模拟。8种湍流模型分别是Spalart-Allmaras 模型 [6 (SA)、Standard $k - \varepsilon$ 模型[7](SKE)、Realizable $k - \varepsilon$ 模型[8](RKE)、RNG$k - \varepsilon$ 模型[9](RNG KE)、Standard $k { - } \omega$ 模型[10](SKW)、SST $k - \omega$ 模型[11,12](SST KW)、v2-f 模型[13,14](V2F）和雷诺应力模型[15,16](RSM)。通过模拟结果与实验结果的对比，系统的分析各湍流模型对大曲率流动的预测能力。进一步采用带有曲率修正的 SA、SKE、RNGKE、RKE、SKW和 SSTKW对该算例进行了模拟，分析曲率修正对湍流模型性能的影响。 ）  
X

# 1二维U型弯管模型建立

# 1.1二维U型弯管参数简介

本文模拟的二维U型弯管参数以及实验数据均来自 Monson 等[4,17]的实验，U型管参数如图1所示。管高度 $H = 3 . 8 1 \ \mathrm { c m }$ ，入口段长度为 $1 0 H = 3 8 . 1$ cm，出口段长度为 $1 2 H = 4 5 . 7 2 \ \mathrm { c m }$ ，弯管处内壁半径 $r _ { \mathrm { i } } { = } 1 . 9 1 \ \mathrm { c m }$ ，外壁半径 $r _ { \mathrm { { o } } } { = 5 . 7 2 \ \mathrm { c m } }$ ， $s$ 为沿U型管中心线的自然坐标系，以入口段和弯管交界处为原点，入口段为负，弯管处和出口段为正。 $Y$ 轴的座标值在内壁面处为零，且恒为正值，外壁面处最大值为 $H$ ， $X$ 轴坐标值在入口段为负，出口段为正，弯管处采用极坐标，原点为内外壁面的圆心。作图时位置都用管径 $H$ 做了无量纲化处理，速度都以入口速度 $U _ { \mathrm { r e f } }$ 为基准做了无量纲化处理。

# 1.2实验数据

实验数据来源于Monson等[4]的实验，进口速度为 $U _ { \mathrm { r e f } } = ~ 3 2 ~ \mathrm { m / s }$ 0 $M a \approx 0 . 1 )$ ，进口总压分别为$P _ { \mathrm { { t } } } = 1 . 2 P _ { 0 }$ 和 $1 2 \mathrm { ~ } P _ { 0 }$ ， $P _ { 0 }$ 为标准大气压，出口压力与进口压力一样，分别可以达到进口雷诺为 $R e = 1 0 ^ { 5 }$ 和 $1 0 ^ { 6 }$ ，实验数据测量主要运用二维LDV(激光多普勒测速)技术测量了流动速度，此外还测量了U 型管的表面摩擦力、湍动能、湍流切应力压力等参数，关于更多的数据测量细节可以参考Monson等[4]的工作。

![](images/10450e5440865078870bf2d7ab7f310ccd4e08fae0aa139064b8d4deebe9da9b.jpg)  
图1U型弯管参数示意图[4] Fig.1 The geometry of U-bend[4]

# 2数值计算设置

# 2.1网格的设置

为了减小网格对模拟结果的影响，根据各湍流模型对壁面网格的要求，在近壁面采用的增强壁面模型，近壁面网格 $y ^ { + } \approx 1$ 。同时本文通过调整网格分布以及网格数，采用了三套网格，如图2和表1所示，进行了网格无关性检验。通过模拟进口 $R e = 1 0 ^ { 5 }$ 条件下不同截面的速度分布曲线来对网格无关性进行分析。

![](images/c774275c0bbf3f9ce6325fbf271c1830dfdca715626b26aa26521950c51e1eba.jpg)  
图2U型弯管网格示示意[4] Fig.2 The mesh ofU-bend

# 表1网格节点分布情况

Table 1 The grid node distribution   

<html><body><table><tr><td>节点数</td><td>a</td><td>b</td><td>C</td><td>h</td><td>网格总数</td></tr><tr><td>第一套</td><td>104</td><td>125</td><td>125</td><td>97</td><td>34388</td></tr><tr><td>第二套</td><td>125</td><td>150</td><td>150</td><td>117</td><td>49735</td></tr><tr><td>第三套</td><td>150</td><td>180</td><td>180</td><td>140</td><td>71400</td></tr></table></body></html>

三套网格均为 SKE 模型对进口 $R e \mathrm { ~ = ~ } 1 0 ^ { 5 }$ 的二维U型弯管进行模拟。通过对 $s / H = - 4$ ， $\theta =$ $0 ^ { \circ }$ 、 $\theta = 9 0 ^ { \circ }$ 、 $\theta = 1 8 0 ^ { \circ }$ 、 $s / H = 2$ 、 $s / H = 4$ 以及出口位置的速度分布进行对比 (限于篇幅没有给出)，发现三套网格的模拟结果完全吻合，做到了网格无关解。因此，本文采用第二套网格进行后期的数值模拟计算。

# 2.2边界条件及湍流模型

根据实验文献[4]中提供的数据，选取上游处距离弯曲段进口 $4 H$ 处的物理量作为进口条件。马赫数为0.1时静压与总压的比值 $\pi = 0 . 9 9 3$ 。雷诺数 $R e$ $= 1 0 ^ { 5 }$ 时，进口静压设置为 $P = 1 2 0 7 8 7 \mathrm { P a }$ ；当雷诺数 $R e = 1 0 ^ { 6 }$ 时，进口静压设置为 $P = 1 2 0 7 8 7 0 \ \mathrm { P a } _ { \circ }$ （20出口设置为压力出口静压与进口静压相等。

为了比较不同湍流模型对模拟结果的影响，在本文的研究中，采用SA模型、SKE 模型、RKE 模型、RNGKE模型、SKW模型、SSKKW模型、V2F模型和RSM模型8种常用的湍流模型对U型管内的流动进行了计算。SKE模型、RKE 模型、RNGKE模型和RSM模型在近壁区采用了增强壁面处理模型。为了研究曲率修正后的湍流模型的模拟性能，本文最后也对带曲率修正的SACC模型、SKECC模型、RKECC模型、RNGKECC模型、SKWCC模型和 SST KW CC 模型对流动进行了模拟。

# 3常用湍流模型的模拟结果

# 3.1速度模拟结果

从图3(a)和图3(b）中可以看到，由于曲率影响， $0 ^ { \circ }$ 截面位置流速已经发生了偏移，由于气流流动中产生的离心力与径向压力梯度的不平衡，导致U 型管中形成一个较大的低压区，从而使其流速增加，而外侧壁面由于较大离心力的作用，使外侧壁面处产生一个较大的高压区，使得外侧壁面处速度较低。在该截面处，所有模型在内侧壁面处的模拟结果都偏大，各湍流模型模拟结果相差不大。

在 $9 0 ^ { \circ }$ 截面位置，内侧速度达到了最大值，外侧速度降为最低值，如图3(c）和图3(d)。该截面处，内外侧壁面的模拟结果同实验结果有明显的差异。其 RSM 模型在外侧壁面处的模拟结果模拟的最好，SKW 模型和 SSTKW 模型在内侧壁面处的模拟结果同实验吻合的最好。整体来说，RSM 模型模拟的结果同实验最为接近。

![](images/d639f55c426a73a05e11336976a977492552fb04c438814384f2381cb20828c6.jpg)

![](images/f83f534b617a4d088b5bf9801f6f3a3cf03f73e5959f07c294c1fc237802b81d.jpg)  
图3弯曲段各截面的速度分布曲线Fig.3 The cross section of velocity distribution

在 $1 8 0 ^ { \circ }$ 截面位置，各湍流模型模拟结果差异较大，如图3(e)和图3(f)。当 $R e = 1 0 ^ { 5 }$ ,RKE 模型的模拟结果与实验结果最接近，而当 $R e = 1 0 ^ { 6 }$ ，RSM模型与实验结果最为接近。 A

从图3可以看到，相比 $R e = 1 0 ^ { 5 }$ ，各湍流模型在 $R e = 1 0 ^ { 6 }$ 时的模拟结果与实验结果更加吻合。

为了更好的分析模拟结果与实验结果间的差异性,本文对 $R e = 1 0 ^ { 6 }$ 流动下, $9 0 ^ { \circ }$ 截面位置的湍动能的分布情况进行了进一步研究。如图4所示，该截面在外侧壁面附近湍动能的实验结果出现了峰值，各湍流模型的模拟结果偏小。结合图3 (c）和图3(d)中该截面的速度分布情况，外侧壁面处速度模拟结果偏小可能是由于该处湍动能模拟结果不准确造成的。在内侧壁面处，SKW和SSTKW模型出现了峰值，这与实验结果偏差较大。整体来看，对于湍动能的模拟结果，RSM模型模拟结果更加吻合。

和出口截面位置的湍动能模拟结果。从图6中可以看到，在 $s / H = 2$ 截面，内侧壁面附近模拟的湍动能峰值均比实验值偏小，而在弯管中心靠近外侧壁面附近出现了湍动能平台区，与实验结果有所偏差。

![](images/5c421e9fc92b0390b530df6089c53c84205ab3b12621a6bd0dbe313461524928.jpg)  
图4湍动能分布图 $\theta = 9 0 ^ { \circ }$ ， $R e = 1 0 ^ { 6 }$ Fig.4 Turbulent kinetic energy distribution

图5显示了雷诺数 $R e = 1 0 ^ { 5 }$ 和 $R e = 1 0 ^ { 6 }$ 时在下游 $s / H = 2$ / $s / H { = } 4$ 和出口截面处流速分布的模拟情况。图5显示，相对于弯曲段，在下游直管段不同湍流模型间的模拟结果差异性较大，各湍流模型模拟结果与实验结果相差较大。从图5中可以看到，在内侧壁面处各模型模拟结果都偏小，随着流动向下游发展，这种偏差在逐渐减小，如图5(e）和图5(f)，在出口内侧壁面处模拟结果与实验结果的偏差较小。从图5（c)和图5(d）可以看到，与实验结果相比，模拟结果得到了一个较薄的边界层，而在出口处，如图5 (e)和图5 (f)，当流动逐渐从曲率影响中恢复时，湍流模型预测的结果恢复的较慢。

为了进一步分析下游的直管流动情况，图6和图7中给出了雷诺数 $R e \mathrm { ~ = ~ } 1 0 ^ { 6 }$ 时，在 $s / H = 2$

结合图5 (a)和图5(b)，在相同位置出现了速度平台以及在内侧壁面处模拟结果偏小，可能是由于各湍流模型对湍动能的模拟结果不准确导致的。其中SKE 模型的模拟结果偏差最大，而RSM模型模拟结果吻合较好。从图7中出口湍动能实验结果显示，湍动能已逐渐恢复平稳，而各模型的湍动能模拟结果仍然有较大的波动，因此从另一个角度也说明湍流模型预测的流动从曲率影响中恢复比实验结果更晚一些。

![](images/9732b0750e20a50d6a7a1d4df27836c88afdbed189bcefb63eccddec0432f79b.jpg)  
图5下游直管段各截面速度分布图Fig.5 The velocity profiles of the downstream sectionsht

![](images/28397143d94208f5102a9ff52c9b8f7725fa3eef6de97535b0164f64798b87ce.jpg)  
Fig.6 Turbulent kinetic energy distribution $s / H = 2$

![](images/11dc39f7e0cb2f765f4618f7624f33900e8bf8003566fbe1a968722e0aec4252.jpg)  
图6 $s / H = 2$ 处湍动能分布 $R e = 1 0 ^ { 6 }$   
图7出口处湍动能分布 $R e = 1 0 ^ { 6 }$   
Fig.7 Turbulent kinetic energy distribution Outlet,

# 3.2分离区的模拟结果

根据 Sandborn[18] 的弯管实验可以发现，在雷诺数 $R e = 1 0 ^ { 5 }$ 时，分离位置在 $1 7 0 ^ { \circ }$ 左右，分离区平均最大高度为 $0 . 0 4 \ H$ ，分离再附的位置在下游0.5$H { \sim } 1 H$ 的位置处。在雷诺数 $R e = 1 0 ^ { 6 }$ 时，通过实验发现，分离位置在 $1 5 0 ^ { \circ }$ 位置，分离区平均最大高度为 $0 . 1 4 ~ H$ ，分离再附的位置在下游 $1 \ H \sim 1 . 5 \ H$ 的位置处。

置的模拟结果都比实验结果推后，其中 SA 模型偏差最大。对比表2和表3，各湍流模型在较高的雷诺数时，对分离涡的模拟更加准确，而SKE模型在两种流动条件下，模拟结果均最差，没有模拟到分离流动的存在。整体来看，当雷诺数较高时，RSM模型和RNGKE 模型对分离的预测能力较好。

表2和表3显示了两种流动条件下，各湍流模型对流动分离的模拟情况。

# 3.3表面摩擦系数和壁面静压力系数的模拟结果

图8和图9中显示了两种流动情况下，内外侧壁面的摩擦系数绝对值曲线。

表2 $R e = { \bf 1 0 ^ { 5 } }$ 时，分离位置统计情况

$$
R e = 1 0 ^ { 5 }
$$

Table 2 The separation position statistics,   
表3 $\mathbf { \mathit { R e } } \mathbf { = } \mathbf { 1 0 } ^ { 6 }$ 时，分离位置统计情况  

<html><body><table><tr><td colspan="4">Re=10°</td></tr><tr><td>模型/实验</td><td>分离位置/()</td><td>再附位置</td><td>竖直高度</td></tr><tr><td>实验</td><td>170</td><td>0.5H~1.5H</td><td>0.04H~0.16H</td></tr><tr><td>SA</td><td>160</td><td>1.67H</td><td>0.016H</td></tr><tr><td>SKE</td><td>无</td><td>无</td><td>无</td></tr><tr><td>RKE</td><td>160</td><td>1.23H</td><td>0.11H</td></tr><tr><td>RNG KE</td><td>162</td><td>1.15H</td><td>0.08H</td></tr><tr><td>SKW</td><td>145</td><td>1.71H</td><td>0.19H</td></tr><tr><td>SSTKW</td><td>140</td><td>1.98H</td><td>0.24Hy</td></tr><tr><td>V2F</td><td>155</td><td>2H</td><td>子</td></tr><tr><td>RSM</td><td>128</td><td>1.25H</td><td>10.18H</td></tr></table></body></html>

Table 3 The separation Position statistics, Re = 106   

<html><body><table><tr><td>模型/实验</td><td>分离位置/()</td><td>再附位置</td><td>竖直高度</td></tr><tr><td>实验</td><td>150</td><td>1.0H~1.5H</td><td>0.14H~0.23H</td></tr><tr><td>SA</td><td>171</td><td>1.4H</td><td>0.09H</td></tr><tr><td>SKE</td><td>无</td><td>无</td><td>无</td></tr><tr><td>RKE</td><td>160</td><td>1.36H</td><td>0.14H</td></tr><tr><td>RNGKE</td><td>165</td><td>1.26H</td><td>0.12H</td></tr><tr><td>SKW</td><td>164</td><td>1.2H</td><td>0.13H</td></tr><tr><td>SSTKW</td><td>162</td><td>1.47H</td><td>0.16H</td></tr><tr><td>V2F</td><td>166</td><td>1.52H</td><td>0.17</td></tr><tr><td>RSM</td><td>162</td><td>1.17H</td><td>0.16H</td></tr></table></body></html>

从表2中，可以看到当 $R e = 1 0 ^ { 5 }$ 时,SKE 模型模拟结果是最差的，没有模拟到流动的分离情况。RKE模型和RNGKE模型对分离点位置模拟最接近实验分离点，而RSM模型的分离位置要明显比实验结果提前。而对于再附位置，SKW模型、SSTKW模型和V2F模型比实验结果推迟了很多，这些模型对分离涡高度的模拟结果也偏大。整体来看，SKW模型和 SSTKW模拟到的分离区更大一些。各模型模拟分离位置点都比实验结果靠前，再附位置比实验结果推后，分离区平均最大高度也较大，因此对于分离涡的大小，整体模拟结果比实验结果要大。

当 $R e = 1 0 ^ { 6 }$ 时，如表3所示，各模型对分离位

![](images/d1511fef071bbc70cef85defcc316f5e5556eba9360f90fc69ae7d612c75af8a.jpg)  
图8内外壁面的摩擦系数绝对值分布 $R e = 1 0 ^ { 5 }$ Fig.8 The wall friction coefficient absolute value distribution of inner wall and outer wall, $R e = 1 0 ^ { 5 }$

当流动接近弯曲段时，内侧壁面流体加速，摩擦系数 $C _ { \mathrm { f } }$ 急剧增加。在 $R e = 1 0 ^ { 5 }$ 时，各湍流模型模拟到弯曲段的内侧壁面的摩擦系数峰值明显偏大，如图8 (a)。而在 $R e = 1 0 ^ { 6 }$ 时，该处的模拟结果有所改善，如图9 (a)。在弯曲段后部，流动减速， $C _ { \mathrm { f } }$ 快速降低，发生分离，出现了零值点。从图8(a）中也可以看到，在 $R e = 1 0 ^ { 5 }$ 时，各湍流模型预测的再附点都比实验结果推后，导致下游摩擦系数偏小。而在$R e = 1 0 ^ { 6 }$ 时，各模拟结果模拟到的再附点同实验结果吻合较好，如图9 (a)。

异性很小，而且同实验吻合程度较大，而当流动分离后，各湍流型对流动模拟有明显的不同。在下游分离后，各湍流模型模拟结果都比实验偏大。整体来看，RSM模拟结果相对较好。

![](images/f482f81556f52d6a638a2ad29818c65bd148a7809a8930fb7ea597dbd025c6dd.jpg)  
图9内外壁面的摩擦系数绝对值分布 $R e = 1 0 ^ { 6 }$ Fig.9 The wall friction coefficient absolute value distrik of inner wall and outer wall, $R e = 1 0 ^ { 6 }$ （204号 ?

![](images/1bf16b787f50f80ba515fae22d021e0eb3c719fcc0113e619de5f01608aaed8e.jpg)  
图10外壁面的压力系数绝对值分布 $R e = 1 0 ^ { 5 }$ Fig.10 The wall pressure coefficient absolute value distribution of inner wall and outer wall, $R e = 1 0 ^ { 5 }$

除了摩擦系数 $C _ { \mathrm { f } }$ 以外，壁面静压力系数 $C _ { \mathrm { p } }$ 在工程中也是非常重要的参数。图 10 和图11显示了各湍流模型的壁面静压力系数 $C _ { \mathrm { p } }$ 绝对值的模拟结果。

同摩擦系数相反的，如图10（a）和图11(a）所示， $C _ { \mathrm { p } }$ 在弯曲段内侧壁面，流速增加，压力降低，静压系数达到最低的峰值，随着流速的下降，压力降到最低值后，急剧上升，产生很大的径向压力梯度，导致流动分离，最终曲线逐渐恢复至平线。由于在此过程中，有流动损失形成，因此下游的静压力系数值要低于进口段的值。同时，从图10以看到，在分离区之前，各湍流模型对压力系数的模拟结果差

![](images/6da5b2e43e7f2d1566b2f161b1094188a0548abcedab50231ddead6dfea2c41b.jpg)

![](images/012d69624a1e37a62c237493cecc90bf227a547495004981783aac4a81c44b44.jpg)  
图11外壁面的压力系数绝对值分布 $R e = 1 0 ^ { 6 }$ （204号Fig.11 he wall pressure coefficient absolute value distributionof inner wall and outer wall, $R e = 1 0 ^ { 6 }$ （204号

# 4带曲率修正的湍流模型的模拟结果

针对常用的湍流模型没有考虑曲率对流场的影响，一些学者提出了湍流模型基于曲率的修正方法，在Fluent 中提供了基于曲率修正的6种滞流模型,分别是 SA CC，SKE CC，RNGxKE CC，RKECC，SKW CC 和 SST KW CC文将用这6种曲率修正后的湍流模型对 $R e \widehat { \Rightarrow } \lambda \dot { 0 } ^ { \dot { 6 } }$ 时的流动进行模拟计算，评估其模拟性能。

从图12可以看到，相对于原湍流模型，带曲率修正后的SKE 模型在内侧壁面处实验更加吻合，而其他曲率修正后的模型在内侧壁面模拟性能反而变差，但在外侧壁面附近速度值有所增加，同实验值吻合较好；整体来看，对于速度分布模拟结果，曲率修正后的 SKE 湍流模型比原模型的模拟性能略好些。而对于另外5个湍流模型，曲率修正对预测性能基本上没有改善甚至个别湍流模型还有一些恶化(限于篇幅没有给出)。也就是说，本文所采用的曲率修正方法，对于这种U型弯管流动，未能很好考虑其中的湍流非平衡输运机理和各向异性机理，没能对预测性能带来本质的改善，还需要进一步开展深入研究。

为了进一步探究曲率修正对湍流模型模拟性能的影响，还对比了实验测量截面处的湍动能分布情况 (限于篇幅未全部给出)。其中，图13给出了在 $9 0 ^ { \circ }$ 截面处SKE 模型采用曲率修正前后的对比情况。修正后的SKE湍流模型对湍动能的模拟性能有很大的改善，在内侧壁面处的湍动能峰值基本消失了，而在外侧壁面处的峰值有所增加，这与实验结果趋势相吻合。同时也说明曲率是造成该种湍动能峰值出现的最主要的原因。而对于另外5个湍流模型，曲率修正使得这一位置的湍动能分布有一点改善，对SKW模型影响稍大一些，对于另外4个影响很小。总体来说，和预测的速度分布类似，曲率修正对SKE的性能影响最为明显。

![](images/a3054a98a4670a778d7cb1ab5c44d3dc0d58e951977e6eb3fd29f9fb121506b5.jpg)

![](images/f055fba15886782cf9b6448b4622de1a1853e96143b4849fa0f4bc8f63d4df3c.jpg)  
图12 KE和 SKECC在 $s / H = 2$ 截面的速度分布曲线， $R e = 1 0 ^ { 6 }$ （20Fig.12 The velocity distribution with SKE and SKE CCturbulence models, $s / H = 2$ ， $R e = 1 0 ^ { 6 }$ （204  
图13 SKE 和 SKE CC 模型在 $9 0 ^ { \circ }$ 截面的湍动能分布曲线， $R e = 1 0 ^ { 6 }$ （20Fig.13 The velocity distribution with different turbulencemodels, $\theta = 9 0 ^ { \circ }$ ， $R e = 1 0 ^ { 6 }$

与对速度和湍动能的模拟结果影响类似，曲率修正对内壁面处的摩擦系数的模拟结果，也是SKE模型的改进最为明显(如图14所示，其余模型结果限于篇幅未给出)。带修正后的模型模拟到再附点的位置会比实验值推后，使得下游直管段的模拟结果偏小。对于内壁面的静压力系数，其影响结果与摩擦系数类似，这里就不再赘述。综合以上对比，表明SKE模型对曲率修正最为敏感。

![](images/b3aa8022fb1e32d1d27848be851c8a91f184d12bcd3742adc28f5103b9d22fe3.jpg)  
图14 SKE 和 SKECC 模型内壁面的摩擦系数绝对值分布， $R e = 1 0 ^ { 6 }$ （204号Fig.14 The wall friction coefficient absolute valuedistribution of inner wall, $R e = 1 0 ^ { 6 }$ （204号

# 5结论

本文针对二维U型弯管内的流动，研究了常用的8中湍流模型对弯管流动的模拟性能，系统分析了常用涡黏湍流模型对弯管流动的模拟能力，同时用带曲率修正的湍流模型对流动进行模拟，通过对比，分析了曲率修正对模型性能的影响作用。得到了以下几点结论：

1）从速度分布曲线的模拟结果来看，相对于弯曲段，在下游直管段不同湍流模型间的模拟结果差异性较大。各湍流模型预测流动从曲率影响中恢复的速度比实验结果慢。相比Re，各湍流模型在 $R e = 1 0 ^ { 6 }$ 时对速度分布的模拟结果与实验结果更加吻合。

2）各湍流模型对分离涡大小模拟结果偏小。SKE没有模拟到分离流动的存在，模拟效果最差。整体来看，当雷诺数较高时，RSM模型和RNGKE模型对分离的预测能力较好。

3)从湍动能分布和湍流剪切应力分布的模拟结果来看，RSM 模型比其他模型好。同时，对于摩擦系数和静压力系数的模拟结果，RSM模型模拟的结果也与实验最为吻合。

4）曲率修正对 SKE以外的湍流模型预测性能基本上没有改善，SKE 模型对曲率修正的影响最为敏感。相对来说，修正后的 SKE 模型对于速度、湍动能、内壁面处的摩擦系数的模拟结果都有一定的改善，但仍有不小的偏差。

综上，现有湍流模型无法准确模拟U型管流动，采用Spalart 和Shur 提出的曲率修正方法，也不能很好的计入大曲率流动中的湍流非平衡输运特性和各向异性，针对大曲率流动的湍流机理和湍流模型改进工作还需要进一步开展。

# 参考文献

[1]Spalart P R.Philosophies and Fallacies in Turbulence

1-15 [2] Spalart PR, Shur M. On the Sensitization of Turbulence Models to Rotation and Curvature [J]. Aerospace Science and Technology,1997,1(5): 297-302 [3] Smirnov P E,Menter F R. Sensitization of the SST Turbulence Model to Rotation and Curvature by Applying the Spalart-Shur Correction Term [J].Journal of Turbomachinery, 2009,131(4):041010 [4] Monson D J, Seegmiller H L,McConnaughey P K.Comparison of LDV Measurements and Navier-Stokes Solutions in a Two-dimensional 18O-degree Turn-around Duct [R].AIAA-89-0275,1989 [5] Monson D J, Seegmiller H L,McConnaughey P K.Comparison of Experiment with Calculations Using CurvatureCorrected Zero and Two Equation Turbulence Models for a Two-Dimensional U-duct [C]//AIAA,Fluid Dynamics, 2lst Plasma Dynamics and Lasers Conference, 2lst, Seattle,WA1990   
[6]Menter F R.Two-eEquation Eddy-Viscosity Turbulence Models for Engineering Applications [J]. AIAA Journal, 1994,32(8): 1598-1605 [7] FLUENT 6.1 User Guide,(2001). Fluent Inc.,Lebanon, USA. http://www.fluent.com [8] Launder B E,Spalding D B.Lectures in Mathematical Models of Turbulence [M].London: Academic Press,1972   
[9] Shih T H, Liou W W,Shabbir A,et al.A New k-e Eddy Viscosity Model for High Reynolds Number Turbulent Flows [J]. Computers & Fluids,1995,24(3): 227-238   
[10] Yakhot V, Orszag S A. Renormalization-Group Analysis of Turbulence [Jl Physical Review Letters,1986,57(14): 1722   
[11] LaunderBE, Reece G J, Rodi W. Progress in the Development of a Reynolds-Stress Turbulence Closure [J]. Journal of Fluid Mechanics,1975,68(03): 537-566 2]Launder B E, Shima N. Second-Moment Closure for the Near-Wall Sublayer-Development and Application [J]. AIAA Journal, 1989,27(10): 1319-1325   
[13] Menter FR,Kuntz M, Langtry R.Ten Years of Industrial Experience with the SST Turbulence Model [J].Turbulence,Heat and Mass Transfer,2003,4(1):625-632   
[14] Durbin P A. Near-Wall Turbulence Closure Modeling Without “Damping Functions”[J]. Theoretical and Computational Fluid Dynamics,1991, 3(1):1-13   
[15] Wilcox D C. Turbulence Modeling for CFD [M]. Canada, CA:DCW Industries,1998:103-217   
[16] Gibson M M, Launder B E.Ground Effects on Pressure Fluctuations in the Atmospheric Boundary Layer [J]. Journal of Fluid Mechanics,1978,86(03): 491-511   
[17] Shur ML,Strelets M K,Travin A K,et al． Turbulence Modeling in Rotating and Curved Channels: Assessing the Spalart-Shur Correction [J].AIAA Journal, 2000,38(5): 784-792   
[18] Sandborn V A.Measurement of Turbulent Flow Quantities in a Rectangular Duct with a 180 Degree Bend [C]//NASA Conference Pub,1988:10-12