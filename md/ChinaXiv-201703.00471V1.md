# 原子质量修饰对碳链聚合物热导率的影响

廖全文 涂润春　刘志春　刘 伟(华中科技大学能源与动力工程学院，武汉430074)

摘要实现聚合物热导率调控，对扩大其在柔性集成电路热管理中的应用非常重要。过去的十年中，学者们从纳米结构材料的制造方面做了大量工作，但是各种各样的官能团与聚合物导热性质的关系仍没有明确。本文使用分子动力学方法，通过原子质量修饰简化模型，探究了碳链聚合物单链的热导率与多种等效取代基的关系。研究发现，氢原子质量修饰能显著调控碳链聚合物单链的热导率，随着原子修饰质量的增加，热导率单调递减。分析表明，氢原子质量修饰会影响与其成键的碳原子的振动模式，越大的原子修饰质量会越多地散射碳链中的低频声子，因而使碳链聚合物单链的热导率显著降低。本研究对理解聚合物热导率调控与多种取代基之间的关系具有指导意义。

关键词聚合物；导热系数；取代基；分子动力学中图分类号：TQ317 文献标识码：A 文章编号:0253-231X(2017)03-0619-06

# lailoring Thermal Conductivity of Carbon-chain Polymers through Atomic Mass Modification

LIAO Quan-Wen TU Run-Chun LIU Zhi-Chun LIU Wei

SchoolofEnergyandPowerEnginering,Huazhong UniversityofScienceand Technology，Wuhan430074,China

AbstractTailoring the thermal conductivity of polymers is central to enlarge their applications in the thermal management of flexible integrated circuits. Progress has been made over the past decade by fabricating materials with various nanostructures,but a clear relationship between various functional groups and thermal properties of polymers remains to be established. Here, we numerically study the thermal conductivity of single-stranded carbon-chain polymers with multiple substituents of hydrogen atoms through atomic mass modification. We find that their thermal conductivity can be tuned by atomic mass modifications as revealed through molecular dynamics simulations. The simulation results suggest that heavy substituents do not assst heat transport. Our analysis indicates that atomic mass modifications influence the phonon bands of bonding carbon atoms. The heavier atomic mass modifications decrease the thermal conduction by scattering more low-frequency phonons in carbon backbones. Our study provides fundamental insight into how to tailor the thermal conductivity of polymers through variable substituents.

Key wordspolymer; thermal conductivity; substituents,molecular dynamics

# 0引言

虽然聚合物因其韧性高、密度低、价格低廉、抗腐蚀性能好等特点被广泛应用，但是聚合物的导热系数非常低，室温下大约在 $0 . 1 ~ \mathrm { W m ^ { - 1 } K ^ { - 1 } ^ { [ 1 ] } }$ ，非常差的导热性能限制了其在传热领域的应用[2-5]。聚合物低的导热性能主要源于其单链的随机缠绕，这种结构会引入大量的声子散射[6,7]，使得载热声子的平均自由程降低。近年来，强化聚合物的导热性能，使其热导率远高于无定形态聚合物的热导率水平，已吸引了国内外学者广泛的研究兴趣。[8-11]

通常，我们可以将强化聚合物导热性能的方法分为两类：基于掺杂的导热强化方法和基于聚合物的导热强化方法。基于掺杂的导热强化方法就是将少量高热导率的材料，例如石墨烯[12-14]、碳纳米管[15-21]、金属粉末[22]等，添加到低热导率的聚合物中，用填充材料的高导热能力来补偿聚合物的低导热能力，也是提高聚合物导热性能的常用方法。Marconnet 等[19]系统研究了碳纳米管掺杂密度对增强环氧树脂热导率效果的影响，研究结果表明，掺杂体积分数为 $1 7 \%$ 的多壁碳纳米管时，碳纳米管/环氧树脂复合材料的热导率能够增加18倍。我们之前的工作也证实了，理想的定向掺杂碳纳米管/聚乙烯模型[21]能够显著地提高聚合物的导热系数。然而，在实际应用中，填料较差的分散性和填料与基体之间高的界面热阻[12,23,24]，极大地限制了实际导热强化效果，使得取得的导热性能并不理想。再者，将掺杂物填充进聚合物，对聚合物本身出色的物理性能也可能造成危害。

第二种方法是基于聚合物的导热强化方法，这种方法基于陈刚等[8,9]对聚乙烯单链热导率的研究,陈刚课题组开拓了利用晶体化方式增强聚合物导热系数的相关领域。此方法的核心思想是使用特殊方法制造高度定向的晶体化聚合物，通过减少材料中的缺陷数量以达到降低声子散射水平，提高导热性能的目的。基于上述思想，陈刚等在实验和数值模拟的研究中，聚合物的导热系数均得到了显著地提升，为如何设计和制造高导热的聚合物提供了理论指导。随后的一些工作表明，通过机械拉伸的方式或者使用纳米尺度模板的方法[4,9,11,25,26]，来增加无定形态聚合物中链的定向程度，能够极大地增加其导热系数。例如，近期的实验研究表明，单纯的聚噻吩纳米纤维[11]热导率能够达到 $4 . 4 ~ \mathrm { W m ^ { - 1 } K ^ { - 1 } }$ ，大约是其块体的20倍，并且纳米纤维仍然保持着无定形态结构。Kim 等[27]通过实验研究了两种共混相容性好，而且链与链之间能够形成特定氢键联接结构聚合物，研究结果表明，链与链之间的氢键形成了密度高并分布均匀的导热网络，因而共混聚合物的面内导热系数得到了明显提升，达到了 $1 . 5 ~ \mathrm { W m ^ { - 1 } K ^ { - 1 } }$ 以上。罗等[5]研究了多种聚合物纳米纤维的热导率,发现其热导率非常依赖于聚合物的主链结构。这些工作为提高聚合物的热导性能，扩大聚合物材料的应用范围铺平了道路。

尽管国内外学者在提升聚合物导热性能方面已经取得了众多进展，但是各种官能团对聚合物导热系数的影响仍是一个待解决的问题。基于简化模型，我们的模拟结果给出了原子质量修饰影响碳链聚合物单链导热系数的基本规律。在下面的章节中，我们首先介绍了模型结构和模拟方法，然后讨论了模拟结果，并分析了导热性能演变机理。

# 1 模型和方法

在本文中，我们使用分子动力学模拟的方法，研究了各种碳链聚合物单链的热导率。碳链聚合物单链由聚乙烯单链中的氢原子被各种官能团替换得到，这些官能团可以是卤素原子、羟基、羧基和酚基等。为了易于多种官能团模型的实现，我们通过修改聚乙烯单链中氢原子的原子质量来代表多种官能团，而不是被实际的官能团替换，并且碳原子与被修饰氢原子之间的键能保持不变。另外，我们忽略了实际取代基对单链的分子结构可能造成的变化。图1给出了通用力场[28,29]下势阱深度 $\left( k _ { \mathrm { I J } } \right)$ 和修饰的相对原子质量 $( m )$ 的比值与相对原子质量的关系，修饰原子质量的简化方法得到的结果与真实原子的结果基本吻合，说明我们使用的简化模型的合理性。

![](images/fed6375bf3fbd2d1d8495c2e34b2a6c453f7d72153a53572c8c4172a756b7c18.jpg)  
图1通用力场下势阱深度 $( k _ { \mathrm { I J } } ) \dot { } $ ）和修饰的相对原子质量 $( m )$ 的比值与相对原子质量的关系，其中实心圆点是真实原子与四面体碳原子形成的共价键的情况，空心圆点是氢原子质量修饰模型中碳氢键的数据，两者基本吻合  
Fig.1 The depth of potential well per unit mass $( k _ { \mathrm { I J } } / m )$ versus relative atomic mass $( m )$ ）under the Universal force field(UFF).The solid dots represent covalent bonds between tetrahedral carbon and main group elements.The open squares represent covalent bonds between tetrahedral and hydrogen atoms with mass modifications

原子质量修饰的聚乙烯单链的结构示意图如图2所示，深灰色原子代表碳(C）原子，白色原子代表氢(H）原子，灰色原子代表被原子质量修饰过的氢原子，用X表示。在下文中，聚乙烯单链用 PE 表示，被原子质量修饰过的聚乙烯单链代表简化的碳链聚合物单链，用MPE表示。在分子动力学的计算中，取如图2所示的特定长度单链结构作为最小重复单元 (Basiccell)，使用周期性边界可以模拟无限长的单链结构。

我们使用分子动力学软件LAMMPS[30]来计算PE 和MPE的热导率，平衡分子动力学计算热导率由格林－库伯公式[31]得到

$$
\kappa = \frac { 1 } { 3 k _ { \mathrm { B } } T ^ { 2 } V } \int _ { 0 } ^ { \infty } { \langle \vec { J } \left( \tau \right) \cdot \vec { J } \left( 0 \right) \rangle } \mathrm { d } \tau
$$

其中 $k _ { \mathrm { B } }$ 是玻尔兹曼常数， $V$ 是模拟系统的体积， $T$ 是绝对温度， $\overrightarrow { J } \left( \tau \right) \cdot \overrightarrow { J }$ （0）是自相关函数, $\langle \rangle$ 代表统计平均。本文模拟采用自适应分子间反应经验键序

(AIREBO）[32]来描述PE 中碳氢原子的相互作用,也用来描述MPE中各原子的相互作用，这个势函数适用于由碳氢原子组成的系统，势函数形式为

$$
\begin{array} { c } { E = \displaystyle \frac { 1 } { 2 } \sum _ { i } \sum _ { j \neq i } \Bigg [ E _ { i j } ^ { \mathrm { R E B O } } + E _ { i j } ^ { L J } + } \\ { \displaystyle \sum _ { k \neq i , j } \sum _ { l \neq i , j , k } E _ { k i j l } ^ { \mathrm { T O R S I O N } } \Bigg ] } \end{array}
$$

其中 $E ^ { \mathrm { R E B O } }$ 项描述 C-C、H-H 和 C-H 之间的短程相互作用，其截断距离为 $\mathrm { 0 . 2 \ n m }$ ; $E ^ { \mathrm { L J } }$ 项描述原子之间的长程相互作用，作用范围为 $0 . 2 { \sim } 0 . 8 5$ nm; $E ^ { \mathrm { T O R S I O N } }$ 项为一种四体势，设置碳氢系统中的各种二面角参数。模拟的过程中，在三个方向都是周期性边界，但是在横截面方向尺寸足够大，使得链与链之间没有相互作用。单链的有效导热横截面积取为 $0 . 1 8 ~ \mathrm { n m ^ { 2 } }$ [8]，这与理想聚乙烯晶体晶格结构中单链的有效截面积一致。

![](images/2ed8002196b37f990d6ead30e99dc2e405e8abab0dfeed659a1f777c3c4878f8.jpg)  
图2氢原子质量修饰的聚乙烯单链的结构示意图 Fig.2 The representative models of PE structures with atomic mass modifications

在热导率的计算中，使用速度Verlet 算法积分运动方程，分子动力学模拟的步长设置为0.2fs。首先，在正则系综（NVT）下使用 Nose-Hoover 热浴,使系统在300K达到平衡态，这个过程历时 $4 0 0 ~ \mathrm { p s }$ 。然后，在等温等压系综（NPT）下，保持 $3 0 0 ~ \mathrm { K }$ 运行$4 0 0 ~ \mathrm { p s }$ 得到零压尺寸。得到零压结构之后，再于微正则系综下运行2ns以消除热浴的影响。最后再保持微正则系综运行 $5 ~ \mathrm { n s }$ ，每0.4fs记录一次热流值，以得到热流自相关函数。通过式 (1)，由热流自相关函数积分可以得到热导率，最终的热导率由多个不同初始速度的算例平均得到。

# 2结果与讨论

首先，使用平衡分子动力学方法，我们计算了PE单链的热导率，长度为 $2 0 \mathrm { n m }$ 的PE单链的热导率如图3所示，图3(a)表示不同初始速度条件下热导率的积分曲线，图3(b)表示平均的热流自相关函数（HFACF）曲线及其热导率积分曲线。在热导率计算中，通常需要使用不同的初始速度条件计算多次，然后取平均值。一方面是因为热流自相关函数记录中存在噪声，随着自相关时间的增加，热流自相关函数信号会逐渐衰减至0，而热噪声的强度却认为基本保持不变。当信号衰减到与噪声同量级或者更小时，噪声就会显著影响热导率的最终结果。另一方面是增加结果的遍历性，理论上模拟的次数越多、时间越长，结果越准确，而实际上不可能实现，所以使用不同初始条件计算多次，使最终热导率结果尽可能准确。在图3(b)中，可以看出随着自相关时间的增加，平均的热流自相关函数信号逐渐减弱，平均的热导率曲线先波动增加然后收敛，在收敛处即可取得 20nm的PE单链的热导率值。

![](images/ff87dae3fe6e4516c7c43703ddd685aa9113f0eadf4fad5c0f5321f4199e2b6f.jpg)  
图3 $3 0 0 ~ \mathrm { K }$ 下 $2 0 ~ \mathrm { n m }$ 的PE单链热导率数据：(a）不同初始速度条件下热导率的积分曲线；(b）不同初始速度条件下平均的热流自相关函数曲线及其热导率积分曲线  
Fig.3 The thermal conductivity of PE chains at a length of $2 0 \mathrm { n m }$ at 30oK.(a) The integral thermal conductivity curves under various initial velocity conditions;(b) The averaged heat flux auto-correlation function and corresponding integral thermal conductivity curve

在计算MPE的热导率之前，首先需要研究热导率的尺寸效应。尺寸效应即纳米尺度材料的热导率随材料尺寸变化而变化，是在纳米尺度热输运中普遍存在的现象。我们使用上述方法计算了不同链长的PE单链的热导率，图4给出了 $3 0 0 ~ \mathrm { K }$ 下PE单链的热导率与长度的关系，可以看出随着长度由10nm增加到 $8 0 ~ \mathrm { n m }$ 的过程中，热导率基本不发生变化。因此，长度为 $1 0 \mathrm { n m }$ 的PE单链就能够克服尺寸效应了，更大的单链长度对热导率的结果影响可以忽略。因此，权衡了计算准确性与计算资源需求之后，以下关于MPE的模拟都采用 $1 0 \ \mathrm { n m }$ 作为MPE的长度。

![](images/60da698526f5826ed6d7a824b7d4087c14352d32c000ae4b05dadfd5ec452938.jpg)  
图4 $3 0 0 ~ \mathrm { K }$ 下PE单链的热导率与长度的关系 Fig.4ThethermalconductivitydependenceofPEchains upon length at $3 0 0 ~ \mathrm { K }$

然后使用相同的方法，我们计算了不同氢原子修饰质量下 $1 0 ~ \mathrm { n m }$ 的 MPE 的热导率，得到了MPE热导率与氢原子修饰质量 $( m _ { \mathrm { X } } )$ 的关系。图5给出了修饰质量为 $8 0 ~ \mathrm { g / m o l }$ 时，MPE 单链热导率数据。图5(a)是不同初始速度条件的热导率结果，图 5(b)是平均之后的热流自相关函数曲线和平均值后的热导率积分曲线。可以发现，热流自相关函数曲线与热导率曲线基本与 PE一致，但与 PE 热导率 56.7$\mathrm { W m ^ { - 1 } K ^ { - 1 } }$ 相比，修饰质量为 $8 0 ~ \mathrm { g / m o l }$ 的MPE的热导率大幅降低，约为 $2 1 . 5 ~ \mathrm { W m ^ { - 1 } K ^ { - 1 } }$ ，下降了约$6 2 . 1 \%$ 。图6给出了不同原子修饰质量的MPE的导热系数，修饰质量的取值范围是0.5到 $1 2 7 \ \mathrm { g / m o l }$ 与真实原子的原子质量基本一致。从导热系数与修饰质量的关系可知，导热系数随着修饰质量的增加而单调下降，指数拟合得到斜率为 $- 0 . 2 1 { \pm } 0 . 0 2$ ，表明较轻的原子质量有利于MPE的热传导。为了提升碳链聚合物的导热性能，在链结构的合成过程中，应该有目的的避免较重原子质量的取代基。

为了分析MPE热导率变化趋势的原因，然后我们分别记录了C原子和X原子的速度自相关函数，由快速傅里叶变换得到各自的声子功率谱。图7分析了不同给修饰质量的MPE单链中C原子和X原子的振动功率谱。可以看出，C原子和X原子的声子模式均强烈依赖于修饰原子X的原子质量。随着$m _ { \mathrm { X } }$ 增加，X原子的声子模式逐渐从高频移向低频，最终集中在 $\mathrm { 0 { \sim } 1 0 T H z }$ 。由于C 原子和X 原子之间的共价键联接，C原子的声子模式也出现了明显变化，随着 $m _ { \mathrm { X } }$ 的增加，C原子的低频声子逐渐减弱，表明越来越多的低频声子被散射了。低频声子因有较大的群速度，在导热贡献中起主要作用，然而原子质量修饰对X原子声子模式的影响散射掉了碳链中的低频声子，所以 MPE 的热导率随着 $m _ { \mathrm { X } }$ 的增加而逐渐降低。

![](images/c09846f296808272407ad5e25b8ce70d1f1e3349abbf30dbd72129920bd6ab44.jpg)  
图5300K下氢原子修饰质量为 $8 0 ~ \mathrm { g / m o l }$ 的 $1 0 ~ \mathrm { n m }$ 的MPE单链热导率数据：(a)不同初始速度条件下热导率的积分曲线；(b)不同初始速度条件下平均的热流自相关函数曲线及其热导率积分曲线

Fig.5 The thermal conductivity of PE chains with hydrogen atomic mass modifications of $8 0 \mathrm { g / m o l }$ at alength of $1 0 \mathrm { n m }$ at 300K.(a) The integral thermal conductivity curves under various initial velocity conditions;(b) The averaged heat flux auto-correlation function and corresponding integral thermal conductivity curve

为进一步验证我们的结果，我们使用COM-PASS[33] 势函数计算了PE、聚乙烯醇（PVA）和聚丙烯(PP）单链的热导率，图8给出了各单链的热导率与长度的关系。使用AIREBO和COMPASS计算得到的PE单链的热导率基本一致。可以看出，它们的热导率均随长度的变化不大，在长度为 $1 6 0 ~ \mathrm { n m }$ 时,PVA和PP单链的热导率分别为 $7 . 0 1 \mathrm { W m ^ { - 1 } K ^ { - 1 } }$ 和 $5 . 8 3 ~ \mathrm { W m ^ { - 1 } K ^ { - 1 } }$ 。PVA 和 PP 单链的热导率非常相近，而远小于PE单链的热导率，这与我们MPE热导率与修饰质量的结果基本一致。PVA和PP的热导率值相近，是因为羟基和甲基的质量相近。它们的热导率远小于MPE修饰质量为 $\mathrm { 1 2 ~ g / m o l }$ 和17$\mathrm { { g } / \mathrm { { m o l } } }$ 的热导率，是因为PVA和PP中只有 $5 0 \%$ 的碳原子上有取代行为发生，碳链上碳原子之间本身就存在着声子模式差异，而MPE中碳链上碳原子的声子模式是一致的。

![](images/a3f1f5baba5e5a22907bb3ff2f64c9c70bd368456dcd7d2a7dc8cdfe891e5bf4.jpg)  
图6MPE 的导热系数与原子修饰质量 $( m _ { \mathrm { X } } )$ 的关系Fig.6 The thermal conductivity of MPE with varied $m _ { \mathrm { X } }$ （204号

![](images/12952c1fcc235f33a0a9fcdd527398a4e1a1f24c7ec5d4f86e4720c6f433fb94.jpg)  
图8 使用COMPASS 势函数计算 PE、PVA 和 PP单链的导热系数与长度的关系Fig.8 The thermal conductivity of PE,PVA and PP chainsat different lengths using COMPASS potential

![](images/103e40f438ad73e75829395d4cb5955aff0eadef76fd9d29be08ed7b6ce42e5e.jpg)  
图7不同原子修饰质量时 MPE 中碳原子 (C)和修饰原子(X)的功率谱Fig.7 The normalized power spectrum of C atoms and Xatoms in MPE with varied $m \mathrm { x }$ （204

# 3结论

本文使用平衡分子动力学方法，首先研究了聚乙烯单链的尺寸效应，然后通过原子质量修饰简化模型，探究了碳链聚合物单链的热导率与多种等效取代基的关系。研究发现，氢原子质量修饰能显著调控碳链聚合物单链的热导率，随着原子修饰质量的增加，热导率单调递减。分析表明，氢原子质量修饰会影响与其成键的碳原子的振动模式，越大的原子修饰质量会越多地散射碳链中的低频声子，因而使碳链聚合物单链的热导率显著降低。使用COM-PASS势函数模拟的聚乙烯、聚乙烯醇和聚丙烯单链的热导率结果基本验证了我们的结论。本研究对基于各种取代基的聚合物热导率调控具有指导意义。

# 参考文献

[1]HALLJF.History and Bibliography of Polymeric Insulators for Outdoor Applications [J].IEEE Transactions on Power Delivery, 1993,8(1):376-385   
[2] CHOY C.Thermal Conductivity of Polymers [J].Polymer,1977,18(10):984-1004   
[3] ASEGUN H.Thermal Transport in Polymers [J].Annual Review of Heat Transfer,2013,17:485-520   
[4] HU G-J,CAO B-Y,LI Y-W.Thermal Conduction in a Single Polyethylene Chain Using Molecular Dynamics Simulations [J]. Chinese Physics Letters,2014,31(8): 086501   
[5] ZHANG T,WU X,LUO T.Polymer Nanofibers with Outstanding Thermal Conductivity and Thermal Stability: Fundamental Linkage between Molecular Characteristics and Macroscopic Thermal Properties [J].The Journal of Physical Chemistry C,2014,21148-21159 [6] HU Y,ZENG L,MINNICH A J,et al． Spectral Mapping of Thermal Conductivity Through Nanoscale Ballistic Transport [J].Nature nanotechnology, 2015,10(8):   
701-706 [7] ZENG L,COLLINS K C,HU Y,et al. Measuring Phonon Mean Free Path Distributions by Probing Quasiballistic Phonon Transport in Grating Nanostructures [J]. Scientific reports,2015,5:17131 [8] HENRY A,CHEN G.High Thermal Conductivity of Single Polyethylene Chains Using Molecular Dynamics Simulations [J].Physical Review Letters,2008,101(23):235502 [9] SHENS,HENRY A,TONG J,et al.Polyethylene Nanofibres With Very High Thermal Conductivities [J]. Nature Nano,2010,5(4):251-255 [10] HAN Z,FINA A.Thermal Conductivity of Carbon Nanotubes and Their Polymer Nanocomposites: a Review [J]. Progress in Polymer Science,2011,36(7):914-944 [11] SINGH V,BOUGHER T L，WEATHERS A，et al. High Thermal Conductivity of Chain-oriented Amorphous Polythiophene [J]． Nature nanotechnology， 2014，9(5):   
384-390 [12] WANG M, GALPAYA D,LAI Z B, et al. Surface Functionalization on the Thermal Conductivity of Graphenepolymer Nanocomposites [J]. International Journal of Smart and Nano Materials, 2014,5(2): 123-132 [13] SONG S H,PARK K H,KIM B H,et al. Enhanced Thermal Conductivity of Epoxy-Graphene Composites by Using Non-Oxidized Graphene Flakes with Non-Covalent Functionalization [J]．Advanced Materials,2013,25(5):   
732-737 [14]EKSIKO,BARTOLUCCI SF,GUPTA T,et al.A Novel Approach to Enhance the Thermal Conductivity of Epoxy Nanocomposites Using Graphene Core-shell Additives [J]. Carbon,2016,101:239-244 [15] IIJIMA S.Helical Microtubules of Graphitic Carbon [J]. Nature,1991,354(6348): 56-58 [16] YANG N,XU X, ZHANGG,et al. Thermal Transport in Nanostructures [J].AIP Advances,2012,2(4):041410 [17] YU K, LEE JM,KIM J,et al. Semiconducting Polymers with Nanocrystalites Interconnected via Boron-Doped Carbon Nanotubes [J].Nano Letters,2014,14(12):7100-   
7106 [18] MINUS ML,CHAE HG,KUMAR S.Polyethylene Crystallization Nucleated by Carbon Nanotubes Under Shear [J]. ACS Applied Material $\&$ Interfaces,2012,4(1):326-   
330 [19] MARCONNET A M, YAMAMOTO N,PANZER M A, et al.Thermal Conduction in Aligned Carbon Nanotubepolymer Nanocomposites With High Packing Density [J]. ACS Nano, 2011, 5(6): 4818-4825 [20] LIAO Q,LIU Z, YANG N,et al. Spontaneous Migration of Polyethylene Molecule Sheathed inside Single-Walled Carbon Nanotube for Nano-Heat Pipe [J]. Scientific Reports,2016,6: 26441 [21]LIAO Q,LIU Z,LIU W,et al.Extremely High Thermal Conductivity of Aligned Carbon Nanotube-Polyethylene Composites [J]. Scientific Reports,2015,5:16543 [22] SU J,LIU X,CHARMCHI M,et al.Experimental and Numerical Study of Anisotropic Thermal Conductivity of Magnetically Aligned PDMS/Ni Particle Composites [J]. International Journal of Heat and Mass Transfer,2016,   
97: 645-652 [23] HUXTABLE S T,CAHILL D G, SHENOGIN S,et al. Interfacial Heat Flow in Carbon Nanotube Suspensions [J]. Nature Materials, 2003, 2(11):731-734 [24] CLANCY T C,GATES T S.Modeling of Interfacial Modification Effects on Thermal Conductivity of Carbon Nanotube Composites [J].Polymer,2006,47(16): 5990-5996 [25] CAO B-Y,LI Y-W, KONG J, et al. High thermal Conductivity of Polyethylene Nanowire Arrays Fabricated by an Improved Nanoporous Template Wetting Technique [J]. Polymer,2011, 52(8):1711-1715 [26] LIU J,YANG R. Tuning the Thermal Conductivity of Polymers with Mechanical Strains [J].Physical Review B,   
2010,81(17): 174122 [27] KIM G H,LEE D,SHANKER A,et al.High Thermal Conductivity in Amorphous Polymer Blends by Engineered Interchain Interactions [J]. Nature Materials, 2015,   
14(3):295-300 [28] RAPP A K, CASEWIT C J, COLWELL K, et al. UFF, a Full Periodic Table Force Field for Molecular Mechanics and Molecular Dynamics Simulations [J]. Journal of the American Chemical Society, 1992,114(25):10024-10035 [29]RAPPEAK,GODDARD III WA.Charge Equilibration for Molecular Dynamics Simulations [J]. The Journal of Physical Chemistry,1991, 95(8):3358-3363 [30] PLIMPTON S.Fast Parallel Algorithms for Shortrange Molecular Dynamics [J]. Journal of Computational Physics,1995,117(1):1-19 [31]HOOVER W G,EVANS D J,HICKMAN R B,et al. Lennard-Jones Triple-point Bulk and Shear Viscosities. Green-Kubo theory, Hamiltonian mechanics,and nonequilibrium molecular dynamics [J]. Physical Review A,1980,   
22(4):1690-1697 [32]BRENNER D W.Empirical Potential for Hydrocarbons for Use in Simulating the Chemical Vapor Deposition of Diamond Films [J].Physical Review B,1990,42(15):   
9458-9471 [33] SUN H.COMPASS:an ab Initio Force-field Optimized for Condensed-phase Applications Overview with Details on Alkane and Benzene Compounds [J]. The Journal of Physical Chemistry B,1998,102(38): 7338-7364