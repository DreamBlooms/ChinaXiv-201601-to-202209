编号：164269

# $\mathbf { H } _ { 2 } \mathbf { O }$ 对沸石咪唑酯骨架材料 $\mathbf { C O } _ { 2 }$ 捕获性能的影响研究

胡建波 刘晶顾晨凯（华中科技大学煤燃烧国家重点实验室，湖北武汉430074）

摘要：沸石咪唑酯骨架(ZIFs)材料是一种新型的温室气体 $\mathrm { C O } _ { 2 }$ 吸附材料。本文采用巨正则蒙特卡洛(GCMC)模拟的方法研究了 $\mathrm { H } _ { 2 } \mathrm { O }$ 对 ZIF-8及ZIF-90的 $\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能的影响。研究结果表明，ZIF-90 的 $\mathrm { C O } _ { 2 }$ 吸附及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能要强于ZIF-8。在ZIF-8中， $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在对该材料的 $\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 选择性分离性能几乎没有影响。 $\mathrm { H } _ { 2 } \mathrm { O }$ 对 $\mathrm { C O } _ { 2 }$ 在 ZIF-90 中的吸附具有协同吸附作用， $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在对材料吸附 $\mathrm { C O } _ { 2 }$ 及分离 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 具有明显的促进作用。

关键词：二氧化碳；水；沸石咪唑酯骨架材料；巨正则蒙特卡洛模拟中图分类号：TQ028.14 文献标识码：A

# The Effect of ${ \bf H } _ { 2 } \mathbf { O }$ on $\mathbf { C O } _ { 2 }$ Capture in Zelolitic Imidazolate Frameworks

Hu Jian-Bo Liu JingGu Chen-Kai (State Key Laboratory of Coal Combustion, Huazhong University of Science and Technology,Wuhan 430074, China)

Abstract: Zelolitic imidazolate frameworks (ZIFs) are a new porous materials for $\mathrm { C O } _ { 2 }$ capture.In this work, we study the effect of $_ \mathrm { H } _ { 2 } \mathrm { O }$ on $\mathrm { C O } _ { 2 }$ adsorption and $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ separation in ZIF-8 and ZIF-9O using Grand Canonical Monte Carlo (GCMC） simulations.The results shows that the $\mathrm { C O } _ { 2 }$ uptake amount and $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ selectivity in ZIF-9O are higher thant that in ZIF-8.In ZIF-8, the presence of $_ { \mathrm { H } _ { 2 } \mathrm { O } }$ have no effect on $\mathrm { C O } _ { 2 }$ adsorption and $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ separation. In ZIF-90, $\mathrm { H } _ { 2 } \mathrm { O }$ has a cooperative effect on the adsorption of $\mathrm { C O } _ { 2 }$ ，the $\mathrm { C O } _ { 2 }$ uptake amount and $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ selectivity increased with the presence of $_ \mathrm { H } \sb { 2 } \mathrm { O }$

Key words: $\mathrm { C O } _ { 2 }$ $\mathrm { H } _ { 2 } \mathrm { O }$ ; Zelolitic imidazolate frameworks; Grand Canonical Monte Carlo simulations

# 0引言

大气中 $\mathrm { C O } _ { 2 }$ 浓度的增加所导致的全球变暖是人类发展所面临的一项重大挑战。燃煤电厂是我国最大的 $\mathrm { C O } _ { 2 }$ 排放源。使用多孔吸附剂从电厂烟气中捕获 $\mathrm { C O } _ { 2 }$ ，从而抑制大气中的 $\mathrm { C O } _ { 2 }$ 浓度，被认为是最为有效的 $\mathrm { C O } _ { 2 }$ 减排方法之一[1]。近年来，多种多孔材料被应用于燃烧后 $\mathrm { C O } _ { 2 }$ 捕获研究，其中金属有机骨架(MOF，metal-organic framework)材料由于其良好的热稳定性和化学稳定性，超大的比表面积，超高且可调的孔隙率，且可根据实际应用需求加以设计、控制等特点，被认为是极具潜力的 $\mathrm { C O } _ { 2 }$ 捕获材料[2]。

沸石咪唑酯骨架(ZIFs，zeolitic imidazolateframeworks)材料是一系列具有类沸石结构的MOFs材料衍生物[3]。该类材料由过渡金属原子(一般为 $Z \mathrm { n }$ 或Co)连接官能化的咪唑(IM)有机链而成，相对于传统的MOFs材料，ZIFs材料具有更为优异的化学稳定性和热稳定性[4]。此外，ZIFs材料还具有非常优异的 $\mathrm { C O } _ { 2 }$ 捕获和分离性能。Banerjee 等[5]的研究表明在 $2 7 3 \mathrm { ~ K ~ }$ 及 $1 0 0 ~ \mathrm { { k P a } }$ 条件下，1LZIF-69可以储存 $8 3 \mathrm { L }$ 的 $\mathrm { C O } _ { 2 }$ ，明显高于BPL 碳等材料。

实际烟气中除了 $\mathrm { C O } _ { 2 }$ 和 $\mathbf { N } _ { 2 }$ 之外，还具有相当数量的水蒸气。研究表明，水蒸气对MOFs材料吸附 $\mathrm { C O } _ { 2 }$ 和分离 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 混合气体具有一定影响。Kizzie等[发现少量的水会促进 $\mathrm { C O } _ { 2 }$ 在HKUST-1中

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

的吸附，而Ni-MOF-74的 $\mathrm { C O } _ { 2 }$ 吸附量在水存在的情况下有所降低。然而，烟气中的 $\mathrm { H } _ { 2 } \mathrm { O }$ 对ZIFs材料的 $\mathrm { C O } _ { 2 }$ 捕获性能影响的研究则鲜见报道[7]。在我们前期研究中发现[7]， $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在会降低ZIF-68的$\mathrm { C O } _ { 2 }$ 的吸附量，但会提高材料的 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离系数。要衡量ZIFs材料在燃烧后 $\mathrm { C O } _ { 2 }$ 捕获领域的应用潜力，必须考察烟气中的 $_ { \mathrm { H } _ { 2 } \mathrm { O } }$ 对ZIFs 材料 $\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能的影响。

本文针对两种具有相同拓扑结构但包含有不同有机链的ZIFs材料，ZIF-8和ZIF-90，采用巨正则蒙特卡洛(GCMC)模拟的方法研究烟气中的 $\mathrm { H } _ { 2 } \mathrm { O }$ 对这两种ZIFs 材料的 $\mathrm { C O } _ { 2 }$ 吸附及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能的影响。对比两种材料在 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 } / \mathrm { H } _ { 2 } \mathrm { O }$ 两种混合气体中的 $\mathrm { C O } _ { 2 }$ 吸附量及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离系数，研究 $\mathrm { H } _ { 2 } \mathrm { O }$ 对ZIFs材料 $\mathrm { C O } _ { 2 }$ 捕获性能的影响，并对其影响机理进行分析。本文的研究结果对设计满足实际工况应用条件的ZIFs材料提供了理论依据。

# 1计算模型与方法

# 1.1 ZIFs模型

ZIF-8及ZIF-90模型中各原子的位置采用XRD测定的实验数据[8,9]确定并构建模型，模型如图1所示。ZIF-8及ZIF-90具有相同的 SOD拓扑结构，由金属原子Zn与不同的有机链链接而成。ZIF-8包含有甲基咪唑有机链，而ZIF-90则由醛基咪唑构成。两种材料的结构性质如表1所示。其中，可接触比表面积和总自由体积通过MaterialsStudio[1o]计算得到。一个直径等于 $\mathbf { N } _ { 2 }$ 动力学直径 $( 0 . 2 8 ~ \mathrm { n m } )$ 的探针分子用于计算材料的可接触比表面积 $( S _ { \mathrm { a c c } } )$ 。材料的总自由体积为未被骨架原子占据的体积，因此直径为0 nm 的探针分子用于计算材料的总自由体积$( V _ { \mathrm { f r e e } } ) ^ { [ 1 1 ] }$ 。

# 1.2力场与原子电荷

选用Lennard-Jones 12-6 势能模型和 coulombic势能模型描述，静电作用采用Ewald求和方法描述气体-气体及气体-吸附剂之间的相互作用力：$\begin{array} { r } { \mathbf { u } _ { \mathrm { i j } } ( \mathbf { r } ) = \underset { \beta \in \mathfrak { j } } { \sum } \biggl \lbrace 4 \varepsilon _ { \alpha \beta } \biggl [ \biggl ( \frac { \sigma _ { \alpha \beta } } { \gamma _ { \alpha \beta } } \biggr ) ^ { 1 2 } - \biggl ( \frac { \sigma _ { \alpha \beta } } { \gamma _ { \alpha \beta } } \biggr ) ^ { 6 } \biggr ] + \frac { q _ { \alpha } q _ { \beta } } { 4 \pi \varepsilon _ { 0 } \gamma _ { \alpha \beta } } \biggr \rbrace ( 1 ) } \end{array}$ 式中: $\varepsilon _ { 0 } = 8 . 8 5 4 2 \times 1 0 ^ { - 1 2 } \mathrm { C } ^ { 2 } \mathrm { N } ^ { - 1 } \mathrm { m } ^ { - 2 }$ ，为真空电容率；$\sigma _ { \mathrm { { \scriptscriptstyle a \beta } } }$ ， $\varepsilon _ { \mathrm { { \mathfrak { a } } \beta } }$ 分别为碰撞直径和阱深。 $\mathrm { C O } _ { 2 }$ 和 $\mathbf { N } _ { 2 }$ 分子力场参数取自TraPPE 模型[12]。在该模型中， $\mathrm { C O } _ { 2 }$ 为刚性线型模型，其中C-O键长为 $0 . 1 1 6 \ \mathrm { n m }$ 。为了描述 $\mathrm { C O } _ { 2 }$ 分子的四极矩，C原子电荷为 $0 . 3 5 \mathrm { e }$ ，O原子电荷为- $. 0 . 7 \mathrm { e }$ 。 $\mathbf { N } _ { 2 }$ 分子为三点刚性模型，其中N-N键长为0.11nm。 $\mathrm { ~  ~ N ~ }$ 原子电荷为-0.482e，为平衡分子电荷，在两个N原子中性放置一个带有 $+ 0 . 9 6 4 \mathrm { e }$ 的虚拟原子。 $\mathrm { H } _ { 2 } \mathrm { O }$ 则取自TIP4P 模型[13]，该模型包括有三个电荷原子和一个LJ中心原子。气体分子力场参数如表2所示。

表1ZIF-8及ZF-90 材料的结构特性Table 1 Structural properties of ZIF-8 and ZIF-90  

<html><body><table><tr><td rowspan="2">ZIFs</td><td rowspan="2">晶格参 数/nm</td><td rowspan="2">p/g.cm-3</td><td rowspan="2">Sacc /m²g</td><td rowspan="2">Vfree/cm3g</td></tr><tr><td></td></tr><tr><td>ZIF-8</td><td>1.699</td><td>0.924</td><td>2482</td><td>0.56</td></tr><tr><td>ZIF-90</td><td>1.729</td><td>0.988</td><td>2267</td><td>0.52</td></tr></table></body></html>

![](images/f53a1e4e50d9efdf3eadea71f71ea365e4c8365bbbba8d5404aa964d93336140.jpg)  
图1材料结构模型 (a)ZIF-8 (b)ZIF-90Fig.1 Atomic structures of(a) ZIF-8 and (b) ZIF-90.

ZIF-8及ZIF-90力场参数取自UFF力场[14]，该力场参数能准确描述气体分子与ZIFs材料骨架原子之间的相互作用力。为了更好的描述气体分子在ZIF-8及ZIF-90中的吸附行为，LJ参数取自优化后的UFF 力场[15]。骨架原子力场参数如表3所示。ZIFs材料骨架原子电荷取自通过DFT计算拟合得到的ESP电荷[15]。原子电荷如图2所示。

表2气体分子L-J势能参数及原子电荷   
Table2LJParametersand Chargesfor GuestGasMolecules   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">LJ 参数</td><td rowspan="2">电荷</td></tr><tr><td>气体分子</td><td>0</td><td>ε/kb</td></tr><tr><td>CO2</td><td>CO_C</td><td>2.8</td><td>27</td><td>0.70</td></tr><tr><td rowspan="3">N2</td><td>CO2_0</td><td>3.05</td><td>79</td><td>-0.35</td></tr><tr><td>N2_N</td><td>3.3</td><td>36</td><td>-0.5075</td></tr><tr><td>N2_com</td><td>0</td><td>0</td><td>1.015</td></tr><tr><td>HO</td><td>H2O_H</td><td>0</td><td>0</td><td>0.52</td></tr></table></body></html>

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

<html><body><table><tr><td>HO_0</td><td>3.1536</td><td>78.03</td><td>0</td></tr><tr><td>HO_com</td><td>0</td><td>0</td><td>-1.04</td></tr></table></body></html>

表3ZIFs材料中骨架原子L-J势能参数Talbe 3LJParameters for ZIF atoms  

<html><body><table><tr><td>原子类型</td><td>0</td><td>ε/kb</td></tr><tr><td>Zn</td><td>2.338</td><td>43.084</td></tr><tr><td>0</td><td>3.118</td><td>20.847</td></tr><tr><td>C</td><td>3.259</td><td>36.483</td></tr><tr><td>N</td><td>3.997</td><td>23.974</td></tr><tr><td>H</td><td>2.440</td><td>15.288</td></tr></table></body></html>

![](images/7debacb069f01772e1508a88266a3d23276f233476b72fe8be17f6f16217a34e.jpg)  
图2骨架各原子电荷(a)ZIF-8(b)ZIF-90 Fig.2 Partial Atomic Charges of(a) ZIF-8 and(b) ZIF-90

# 1.3巨正则蒙特卡罗模拟细节

使用巨正则蒙特卡罗(GCMC)模拟方法计算ZIF-8和ZIF-90材料在298K温度条件下的单一组分气体吸附量以及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 } / \mathrm { H } _ { 2 } \mathrm { O }$ 三元混合气体中各组分气体吸附量及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离系数。骨架中各原子为刚性，且固定在各自位置。考虑到周围环境对材料吸附 $\mathrm { C O } _ { 2 }$ 的影响，在计算中使用三维周期性边界条件。为保证计算精度，模拟盒子选取为 $2 \times 2 \times 2$ 个单元晶胞，截断半径为 $1 . 2 8 \ \mathrm { n m }$ ，模拟步数为 $2 \times$ ${ 1 0 } ^ { 7 }$ ，其中，前 $1 \times { 1 0 } ^ { 7 }$ 用于平衡体系，后 $1 \times { 1 0 } ^ { 7 }$ 用于热力学统计研究。模拟计算结果为绝对吸附量，而实验测量结果为相对吸附量，两者之间的转换公式中， $n _ { \mathrm { e x } }$ 表示相对吸附量， $\mathtt { n } _ { \mathrm { a b s } }$ 表示绝对吸附量，$V _ { \mathrm { g } }$ 表示吸附剂孔体积， $\rho _ { \mathrm { g } }$ 为吸附质气体密度。 $\rho _ { \mathrm { g } }$ 可通过Peng-Robinson方程计算得到。气体分离系数计算公式为：

$$
{ \sf S } = ( { \bf x } _ { 1 } / { \bf x } _ { 2 } ) ( { \bf y } _ { 2 } / { \bf y } _ { 1 } )
$$

其中 $\mathbf { x }$ 和 $\mathrm { \Delta y }$ 分别是相应组分气体在吸附相以及气相中的摩尔分数。

# 2结果与讨论

# 2.1力场参数的验证

在对模型进行分子模拟研究时，选择合适的力场参数对于模拟结果的可靠性有决定性作用。本文将GCMC 模拟所得到的ZIF-8与ZIF-90的 $\mathrm { C O } _ { 2 }$ 及$\Nu _ { 2 }$ 吸附等温线与实验所得到的吸附等温线相对比，结果如图3所示。结果表明模拟结果与实验结果很吻合。因此本文所选取的力场参数和电荷可靠。

![](images/9b36f51e9df7f33137ed4883c792418b95553d13dcd416f21d16c3819b28ecb7.jpg)  
图3模拟与实验吸附等温线对比:(a)298K,(b)295K Fig. 3 Comparison of simulated and experiment adsorption isotherms: (a)298K,(b)295K

# 2.2单一气体吸附

图4给出了在298 K时 $\mathrm { C O } _ { 2 }$ ， $\Nu _ { 2 }$ 及 $\mathrm { H } _ { 2 } \mathrm { O }$ 在ZIF-8及ZIF-90上的吸附等温线。其中 $\mathrm { C O } _ { 2 }$ 压力范围为： $0 \ \mathrm { { \ k P a } { - } 1 0 0 \ \ k P a }$ ， ${ \bf N } _ { 2 }$ 压力范围为： $0 ~ \mathrm { { \ k P a } - 1 0 0 }$ kPa， $\mathrm { H } _ { 2 } \mathrm { O }$ 的压力范围为 $0 \ \mathrm { k P a } { - } 1 0 \ \mathrm { k P a }$ 。由图4中可以看出， $\mathrm { C O } _ { 2 }$ 在ZIF-8及ZIF-90中的吸附量明显高于 $\Nu _ { 2 }$ ，这表明ZIF-8及ZIF-90 是一种很好的$\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离材料。 $\mathrm { H } _ { 2 } \mathrm { O }$ 在 ZIF-8中的吸附量很低,这是因为- $\mathrm { . C H } _ { 3 }$ 官能团是憎水基团，会阻碍 $\mathrm { H } _ { 2 } \mathrm { O }$ 在ZIF-8中的吸附。由于ZIF-90中的-CHO具有亲水

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

性， $\mathrm { H } _ { 2 } \mathrm { O }$ 在 ZIF-90中的吸附量远高于 $\mathrm { C O } _ { 2 }$ 在ZIF-90 中的吸附量。

![](images/f16ee6c5da2c50c45d0ec091740ac3b3010da9bdfcd1722d6288f801a12c8400.jpg)  
图 $4 \mathrm { C O } _ { 2 }$ ， $\mathbf { N } _ { 2 }$ 及 $\mathrm { H } _ { 2 } \mathrm { O }$ 在(a)ZIF-8及(b)ZIF-90中的吸附等温线

# 2.3混合气体吸附

为了研究烟气中的 $_ \mathrm { H _ { 2 } O }$ 对ZIF-8及ZIF-90的$\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能的影响，本文考虑了两种不同的气体混合物: 1) $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ ，2)$\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 } / \mathrm { H } _ { 2 } \mathrm { O }$ ，为模拟实际烟气， $\mathrm { C O } _ { 2 }$ 分压为15$\mathbf { k P a }$ ， $\mathrm { H } _ { 2 } \mathrm { O }$ 为 $5 ~ \mathrm { \ k P a }$ ，模拟烟气总压为 $1 0 0 ~ \mathrm { { \ k P a } }$ 。采用 $\Nu _ { 2 }$ 平衡混合气体总压。

图5给出了ZIF-8和ZIF-90在两种混合气体中的 $\mathrm { C O } _ { 2 }$ 吸附量及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离系数。从图5中可以看出，在 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 混合气体中，ZIF-90 的 $\mathrm { C O } _ { 2 }$ 吸附量及 $\mathrm { C O } _ { 2 }$ 选择性要高于ZIF-8的 $\mathrm { C O } _ { 2 }$ 选择性。这是因为ZIF-90中有机链上的官能团-CHO是极性官能团，而在ZIF-8中的- $\mathrm { . C H } _ { 3 }$ 官能团则是非极性官能团。极性官能团相比非极性官能团更能增强 $\mathrm { C O } _ { 2 }$ 在骨架上的吸附作用能[16]。因此当采用极性官能团取代时， $\mathrm { C O } _ { 2 }$ 与骨架原子之间会具有更高的亲和力，从而会增大材料的 $\mathrm { C O } _ { 2 }$ 吸附量及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离系

数。此外，我们还可以发现 $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在对ZIF-8 吸附 $\mathrm { C O } _ { 2 }$ 及分离 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 没有影响。这是因为 $\mathrm { H } _ { 2 } \mathrm { O }$ 在ZIF-8中的吸附量极低，远低于 $\mathrm { C O } _ { 2 }$ 在材料内的吸附。另一方面，尽管 $\mathrm { H } _ { 2 } \mathrm { O }$ 在ZIF-90中的吸附量相当可观，但 $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在却对材料吸附 $\mathrm { C O } _ { 2 }$ 及分离$\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 有一定的促进作用。从表5中可以看出，$_ { \mathrm { H } _ { 2 } \mathrm { O } }$ 的存在会提高 $\mathrm { C O } _ { 2 }$ 在 ZIF-90中的吸附热，因此， $_ \mathrm { H } _ { 2 } \mathrm { O }$ 对 $\mathrm { C O } _ { 2 }$ 在 ZIF-90 中的吸附具有一定的协同吸附效应，从而提高材料的 $\mathrm { C O } _ { 2 }$ 吸附量。而 $_ \mathrm { H } _ { 2 } \mathrm { O }$ 与 $\Nu _ { 2 }$ 之间则缺乏这一作用，因此因此 $_ { \mathrm { H } _ { 2 } \mathrm { O } }$ 的存在增强了 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 选择性系数。

![](images/07624b4c5cafa0c291cb59f7279278285f189f81a4ae56438c7519d8ded84b0c.jpg)  
Fig.4 Simulated $\mathrm { C O } _ { 2 }$ ， $\mathbf { N } _ { 2 }$ ，and $\mathrm { H } _ { 2 } \mathrm { O }$ adsorption isotherms in (a) ZIF-8 and (b) ZIF-90   
图5ZIF-8和ZIF-90在两种混合气体中的 $\mathbf { \tau } ( \mathbf { a } ) \mathbf { C O } _ { 2 }$ 吸附量和 $\mathrm { ( b ) C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离系数 Fig. 5 (a) $\mathrm { C O } _ { 2 }$ uptake amount and (b) $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ selectivity from two mixture in ZIF-8 and ZIF-90

表5ZIF-8和ZIF-90在两种混合气体中的 $\mathrm { C O } _ { 2 }$ 吸附热Table $5 \mathrm { C O } _ { 2 }$ adsorption heat from two mixtures in ZIF-8 andZIF-90  

<html><body><table><tr><td>ZIFs</td><td>CO2/N2</td><td>CO/N/HO</td></tr><tr><td>ZIF-8</td><td>16.65</td><td>16.63</td></tr><tr><td>ZIF-90</td><td>20.53</td><td>24.56</td></tr></table></body></html>

# 3结论

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

本文使用巨正则蒙特卡罗模拟(GCMC)方法计算了 $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在对ZIF-8与 ZIF-90 的 $\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能的影响。研究结果表明，ZIF-90的 $\mathrm { C O } _ { 2 }$ 吸附及 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能要强于ZIF-8。在ZIF-8中， $\mathrm { H } _ { 2 } \mathrm { O }$ 的吸附量远低于 $\mathrm { C O } _ { 2 }$ 的吸附量，而在 ZIF-90中， $\mathrm { H } _ { 2 } \mathrm { O }$ 的吸附量高于 $\mathrm { C O } _ { 2 }$ 的吸附量。$_ { \mathrm { H } _ { 2 } \mathrm { O } }$ 的存在对ZIF-8的 $\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能没有影响，而在ZIF-90中， $\mathrm { H } _ { 2 } \mathrm { O }$ 与 $\mathrm { C O } _ { 2 }$ 之间存在协同吸附作用。 $\mathrm { H } _ { 2 } \mathrm { O }$ 的存在对 ZIF-90 的 $\mathrm { C O } _ { 2 }$ 吸附性能和 $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ 分离性能有明显的促进作用。

# 参考文献

[1] Figueroa JD,Fout T, Plasynski S,et al. Advances in $\mathrm { C O } _ { 2 }$ Capture Technology—the U.S. Department of Energy's Carbon Sequestration Program[J]. International Journal of Greenhouse Gas Control, 2008,2(1): 9--20   
[2] Sumida K,Rogow D L,Mason J A,et al. Carbon Dioxide CaptureinMetal-OrganicFrameworks[J]. Chemical Reviews,2012,112(2): 724--781   
[3] Banerjee R,Phan A,WANG Bo,et al.High-Throughput SynthesisofZeoliticImidazolateFrameworksand Application to $\mathrm { C O } _ { 2 }$ Capture[J]． Science,2008,319(5865): 939--943   
[4] Park K S,NI Zheng, Coté A P, et al. Exceptional Chemical and Thermal Stability of Zeolitic Imidazolate Frameworks[J]. Proceedings of the National Academy of Sciences,2006, 103(27): 10186--10191   
[5] Banerjee R,Furukawa H, Britt D,et al. Control of Pore Size andFunctionalityin Isoreticular Zeolitic Imidazolate Frameworks and Their Carbon Dioxide Selective Capture Properties[J]. Journal of the American Chemical Society, 2009,131(11): 3875--3877   
[6] Kizzie A C,Wong-Foy A G,Matzger A J. Effect of Humidity on the Performance of Microporous Coordination Polymers as Adsorbents for $\mathrm { C O } _ { 2 }$ Capture[J]. Langmuir, 2011,27(10): 6368--6373   
[7]LIU Yang,LIU Jing,LIN Y S, et al. Effects of Water Vapor and Trace Gas Impurities in Flue Gas on $\mathrm { C O } _ { 2 } / \mathrm { N } _ { 2 }$ Separation Using ZIF-68[J]. The Journal of Physical Chemistry C, 2014,118(13): 6744-6751   
[8]HUANG Xiaochun, LIN Yanyong, ZHANG Jiepeng, et al. Ligand-Directed Strategy for Zeolite-Type Metal-Organic Frameworks: Zinc(II) Imidazolates with Unusual Zeolitic Topologies[J]. Angewandte Chemie, 2006,118(10): 1587-- 158y   
[9] Morris W, Doonan C J, Furukawa H, et al. Crystals as molecules: Postsynthesis Covalent Functionalization of ZeoliticImidazolateFrameworks[J]. Journal ofthe American Chemical Society,2008,130(38):12626--12627   
[10] Dassault Systemes BIOVIA. Materials Studio Modeling Environment, release 2017; Dassault Systemes BIOVIA.: San Diego, CA, 2016.   
[11] HU Jianbo, LIU Jing,LIU Yang, et al. Improving Carbon Dioxide Storage Capacity of Metal Organic Frameworks by Li Alkoxide Functionalization: A Molecular Simulation Study[J]. The Journal of Physical Chemistry C，2016, 120(19): 10311--10319   
[12] Potoff J J,Siepmann J I. Vapor-Liquid Equilibria of MixturesContaining Alkanes， Carbon Dioxide, and Nitrogen[J]. AIChE journal, 2001, 47(7): 1676--1682   
[13] Jorgensen W L，Chandrasekhar J，Madura JD，et al. Comparison of Simple Potential Functions For Simulating Liquid Water[J]. The Jourmal of Chemical Physics,1983, 79(2): 926   
[14] Rapp A K, Casewit C J,Colwell K,et al. UFF,a Full Periodic Table Force Field for Molecular Mechanics and MolecularDynamicsSimulations[J]. Journal ofthe American Chemical Society,1992,114(25): 10024--10035   
[15] Amrouche H, Aguado S, Pérez-Pellitero J, et al. Experimental and Computational Study of Functionality Impact on Sodalite-Zeolitic Imidazolate Frameworks for （204号 $\mathrm { C O } _ { 2 }$ Separation[J]. The Journal of Physical Chemistry C, 2011,115(33): 16425--16432   
[16] LIU Yang,LIU Jing,CHANG Ming，et al. Effect of Functionalized Linkeron $\mathrm { C O } _ { 2 }$ Bindingin Zeolitic Imidazolate Frameworks: DensityFunctional Theory Study[J]. The Journal of Physical Chemistry C，2012, 116(32): 16985--16991