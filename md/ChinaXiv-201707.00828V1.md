# 进化与未进化小球藻响应苯酚的转录组学分析

周琳1²汪靓²高娟 赵权宇2\*\* 魏伟²孙予罕²(1上海大学生命科学学院上海2004442中国科学院上海高等研究院上海201210)

摘要苯酚是工业废水中典型的环境污染物。小球藻(Chlorella sp.）由于其生长快、抗逆性强，可以有效利用废水中的酚类化合物,是最有潜力的含酚废水处理藻株。但是高浓度苯酚产生的氧化压力会造成小球藻细胞的氧化损伤。通过实验室适应性进化已经得到了可以耐受 $5 0 0 \mathrm { m g / L }$ 苯酚的小球藻藻株(L5)。通过无参比较转录组学数据，在基因组尺度上考察了原始小球藻(L3)和进化后小球藻对高浓度苯酚的响应差异。无参比较转录组学结果表明,进化后小球藻能够耐受并降解高浓度苯酚是多个代谢途径整体调控的结果。相比于原始小球藻,进化后小球藻在$\mathrm { 5 0 0 m g / L }$ 苯酚浓度下对苯酚氧化胁迫的响应增强,主要体现在细胞信号转导、ABC 转运蛋白、热休克蛋白、氮代谢和三羧酸循环(TCA)等相关的转录水平明显上调。进化后小球藻通过这些响应降低高浓度苯酚产生的氧化压力。

关键词苯酚转录组学 氮代谢 三羧酸循环 小球藻

中图分类号 X172

苯酚及其衍生物是石油化工和煤化工等行业排放废水中的重要污染物[1]。含酚废水是水污染治理中的重点之一。苯酚毒性强,具有致癌、致畸和致突变等特点。近年来,微生物方法处理苯酚废水被认为是经济实用的手段。不仅见效快、成本低，而且不会产生二次污染。微藻是一类单细胞生物,具有分布广泛、繁殖快和适应能力强等特点，营养方式有光合自养、光合异养和混合兼养。微藻处理含酚废水后，可将藻细胞回收并用催化等方法转化成化学制品再利用，可以提高废水处理的经济性。

目前,利用细菌处理苯酚废水的研究比较多[24]对于微藻处理苯酚废水的研究相对较少。低浓度的苯酚可以直接被微藻作为碳源利用，并且对微藻的生长和油脂合成有促进作用。但是高浓度的苯酚却抑制微藻的生长，甚至使藻细胞受到损伤。需要说明的是这种抑制作用因藻种而异。为提高小球藻苯酚废水的处理能力，在之前的实验中利用实验室适应性进化强化小球藻对苯酚的耐受性，进化后的小球藻藻株能够耐受并降解 $5 0 0 \sim 7 0 0 \mathrm { m g / L }$ 苯酚[5]。研究细菌等微生物或微藻对苯酚的生物响应有助于了解生物与环境间的相互作用， $\mathrm { L i n } ^ { [ 6 ] }$ 通过qPCR和蛋白质组学研究了不动杆菌Y在降解 $\mathrm { 1 \ 0 0 0 m g / L }$ 的苯酚过程中的压力反应，结果表明不动杆菌Y在苯酚氧化压力下，ABC转运蛋白和膜受体蛋白合成增加，但是三羧酸循环和氧化磷酸化被抑制。ABC转运蛋白和膜受体蛋白合成以及三羧酸循环和氧化磷酸化等途径都是微生物对苯酚氧化胁迫响应的体现。作为微生物的微藻也会对苯酚氧化胁迫做出响应，而且这种响应不仅受诸多因素的影响，还具有藻种特异性。本研究利用无参转录组测序分析进化后小球藻和未进化小球藻在高浓度苯酚条件下对抗苯酚氧化压力所产生的响应差异，以探讨可能的进化机制。

# 1材料与方法

# 1.1藻种和培养方法

一株从废水中筛选得到的小球藻(L3)在 $5 0 0 \mathrm { m g / L }$ 的苯酚浓度下经过实验室适应性进化得到进化后小球藻（L5）[5]。进化后小球藻和原始小球藻在含 $5 0 0 \mathrm { m g / L }$ 苯酚的TAP培养基中进行摇床培养，每组设有3个平行对照。培养条件全光照培养，摇床转速 $1 5 0 \mathrm { r / m i n }$ ，光照强度 $1 5 0 \mu \mathrm { m o l } / ( \textrm { m } ^ { 2 } \cdot \textrm { s } )$ 。

# 1.2 测序样品的制备

培养4天后从每个样品中取 $5 0 \mathrm { m l }$ 藻液， $6 ~ 0 0 0 \mathrm { r / }$ min离心 $5 \mathrm { { m i n } }$ ,用去离子水洗涤藻体2次或3次，液氮速冻后立即转入 $- 8 0 ^ { \circ } \mathrm { C }$ 保存待测。

# 1.3数据处理及denovo拼接

通过IlluminaHiseq400O双端测序得到的原始序列（rawreads），在使用拼接软件对其进行denovo拼接前需要进行预处理，去掉那些低质量的、含有接头的、不确定的序列，得到有效序列（cleanreads）。用拼接软件 Trinity[7]对这些有效序列进行denovo 拼接,形成一个转录组。

# $1 . \dot { 4 } >$ 功能注释及代谢途径分析

将拼接得到的转录本利用 $\mathrm { B l a s t X } ^ { [ 8 ] }$ 算法分别与9 中的non-redundat（）、Srn、SisNGBIPfam[10]和 KEGG[1]数据库进行比对, $E$ -value 的阈值设为1 $^ { \circ } _ { : 0 } \times 1 0 ^ { - 5 }$ ,预测转录本的功能并且对功能进行分类。GO功能注释结果统计得到基于NR和Pfam两部分的蛋白质注释结果，注释后的转录本会得到相应的GO 编号。再将拼接得到的转录组提交到KEGG的$\mathrm { K A S S } ^ { [ 1 2 ] }$ 服务器上。KASS 会对每一条提交的转录本序列进行注释，被注释到的转录本被分配到相应的EC号和代谢途径。通过FPKM值来计算基因的表达水平，EdgeR[13]被用于差异表达分析,且满足 $\mathrm { F D R } { \leqslant } 0 . 0 5 , \log$ $| { \mathrm { F C } } | \geqslant 1$ （log底数为2）。

# 2 结果与讨论

# 2.1转录组测序信息及拼接

本次IlluminaHiseq4000双端测序得到的原始数据经过质控后去除低质量的数据共得到用于拼接的高质量序列，用denovo对这些序列进行拼接后共得到88637个转录本，81885个unigene，长度范围为 $2 0 0 \sim$ 70000bp（表1）。若无特殊说明，后面用于分析数据的全是unigene 数据。

Table 1Summary for splice length frequency distribution   

<html><body><table><tr><td>转录长度区间</td><td>200 ~600bp</td><td>600 ~1.2kb</td><td>1.2~1.8kb</td><td>1.8~2.8kb</td><td>2.8~70kb</td><td>总数</td></tr><tr><td>转录本数</td><td>65 806</td><td>10 700</td><td>5168</td><td>3895</td><td>3068</td><td>88 637</td></tr><tr><td>unigene 数</td><td>63 604</td><td>9183</td><td>4136</td><td>2 868</td><td>2 094</td><td>81 885</td></tr></table></body></html>

# 功能注释及物种相似性分析

拼接得到的所有核苷酸序列利用 BlastX 算法与NR String、Swissprot 和 KEGG 比对后得到相应的注释信息。比对结果显示有 $5 8 . 4 7 \%$ 的转录本能够和 NR数据库的序列比对上，与KEGG库序列吻合的转录本有26188个，与 String库序列一致的转录本数目最少，只有11658个。详细结果见表2。

# 表2转录本的注释结果统计

表1拼接长度频数分布  
Table2Annotation of all transcripts   

<html><body><table><tr><td rowspan="2">Database</td><td rowspan="2">Total transcripts</td><td rowspan="2">Annotated transcripts</td><td rowspan="2">Percentage(%)</td></tr><tr><td></td></tr><tr><td>Pfam</td><td>88 637</td><td>21 014</td><td>23.71</td></tr><tr><td>String</td><td>88 637</td><td>11 658</td><td>13.15</td></tr><tr><td>Swiss-Prot</td><td>88 637</td><td>32 329</td><td>36.47</td></tr><tr><td>KEGG</td><td>88 637</td><td>26188</td><td>29.55</td></tr><tr><td>NR</td><td>88 637</td><td>51 824</td><td>58.47</td></tr></table></body></html>

通过与NR库的比对可以得到与其他物种的相似性信息，其中与Arabidopsisthaliana一致的转录本有17399，同Chlorella variabilis相同的转录本有8630个。

包括小球藻在内的藻类基因组信息还非常有限，其基因注释也不够完善。拟南芥作为植物生理和分子生物学等研究的模式植物，其全基因组信息测定较早。微藻和拟南芥均属于植物，其基因具有相似性是可以理解的。已经测序的小球藻的基因注释也会参考拟南芥的相关信息。根据BlastX算法与GO数据库比对结果，35996个转录本注释到GO 编号，11658个序列与COG数据库一致。根据GO数据库注释结果，转录本分成64类，分别属于生物过程（biologicalprocess）、分子功能（molecularfunction）和细胞组分（cellularcomponent）三大类。COG数据库的注释结果把转录本按照功能分成了26个家族。

# 2.3细胞信号转导途径分析

生物通过检测细胞外的氧化压力和渗透压力变化等来感知外界环境的变化。信号分子有植物激素、活性氧(ROS)和一氧化氮(NO)等。过氧化氢是植物细胞代谢过程中产生的一种活性氧，被认为是植物抵抗压力胁迫的重要信号分子[14]，它能够与蛋白激酶（MAPK级联）、蛋白磷酸酶、转录因子和膜结合钙离子通道等反应，从而影响基因的表达。植物修复重金属污染的过程中最初是由根部感知重金属应力并触发信号转导,从而介导分子、生理和微观结构水平的变化。通过基因调节植物对重金属的反应，激活抗氧化系统和在不同信号分子之间协调分配机制。在高浓度苯酚条件下，小球藻细胞由于氧化损伤产生过量的过氧化氢，过氧化氢作为信号分子使细胞信号转导途径的合成和代谢上调，并将信号级联放大传递下去，进而调控一系列胁迫应答。虽然未进化小球藻也能对苯酚胁迫在细胞信号转导做出一定的响应，但是对进化后小球藻和原始小球藻在 $5 0 0 \mathrm { m g / L }$ 的苯酚浓度下的转录组分析结果显示，进化后小球藻相对于原始小球藻的细胞信号转导途径明显上调(图1）。这说明进化后小球藻在苯酚产生的氧化压力胁迫下能够迅速的感知到这种氧化压力变化并将信号传递下去,以协助细胞做出响应。这和实验室适应性进化过程中进化的小球藻长期置于苯酚环境中有关，持续的苯酚氧化刺激，使进化小球藻的对苯酚氧化胁迫的响应得到了积累，耐受性提高。

cz:aixnnnny 品 9 o C b.0 b 535555 53211 355555 5555555 585331 555175 855555 842334 6565 898870 555555 555455 655881 545455 955999 6659 BRI1 GH3 SnRk2BIN2 EIN3BZR12AUX1 TFPYR AUX BBF1/2

# 2.4热休克蛋白和ABC转运蛋白分析

热休克蛋白（heat shockproteins，HSPs）是从细菌到植物和哺乳动物中都普遍存在的一类热应激蛋白[15]。根据蛋白质的大小将热休克蛋白分为5类,分别为HSP110、HSP90、HSP70、HSP60和小分子热休克蛋白。细胞受到环境压力时，第一反应就是合成热休克蛋白，因此热休克蛋白可以作为细胞应激能力的标志。重金属砷能够对小鸡产生神经性毒性，并检测到Hsp60 和Hsp70 的蛋白质表达上调[16]。热休克蛋白还可以提高细胞的应激能力，持续的非生物氧化胁迫刺激可以使热休克蛋白的表达量上调。研究表明热休克蛋白的生成量和生物的耐受性呈正相关。对进化后小球藻和原始小球藻在 $5 0 0 \mathrm { m g / L }$ 的苯酚浓度下的转录组分析结果显示，进化后小球藻的热休克蛋白 ${ \mathrm { H s p 9 0 } }$ 、Hsp70 和 $\mathrm { H s p } 4 0$ 的基因表达明显上调。Hsp70位于细胞质中,是进化上高度保守的一类热休克蛋白[17],Hsp70家族均有两个功能结构域：一个是约由450个氨基酸组成的高度保守的N端ATPase功能域（ATP-bindingdomain）；另一个是约由200个氨基酸组成的相对保守的C端区域。Hsp70正常情况下不表达或很少表达，在氧化胁迫的条件下表达量迅速增加。本实验检测到Hsp70的5个转录本序列明显上调，Hsp90和$\mathrm { H s p } 4 0$ 各检测到一个转录本上调。Hsp70不仅可以作为分子伴侣监测蛋白质的折叠状态，还可以参与细胞信号转导、细胞周期调控和细胞调亡等，这对处于氧化胁迫条件下的藻细胞调节压力反应尤其重要。

7 -5155 6 5 1 4 三三 3 2 0 8 B 698880 555550 555550 853535 5255515 868611 856959 Hsp70 Hsp40 Hsp90

ABC（ATP-bindingcassette）转运蛋白是一类ATP驱动泵，包括几百种不同的转运蛋白，广泛存在于细菌到人类的各种生物中。从轮虫（Brachionuskoreanus）基因组中鉴定出61个ABC 转运蛋白[18]。根据系统发育分析分成8个不同的亚族（A～H），由11个ABCA基因、19个ABCB基因、14个ABCC 基因、3个ABCD基因、1个ABCE基因、3个ABCF基因、8个ABCG基因和2个ABCH基因组成。ABC转运蛋白是细胞膜上糖、氨基酸、磷脂和肽链的转运蛋白，利用ATP水解产生的能量协助细胞将胞内有毒物质和废物排出。ABC转运蛋白还参与次生代谢产物的积累以及生物和非生物胁迫反应等。Jeong等[19研究了浮游动物中华咸水剑水蚤（Paracyclopinanana）对多环芳烃的响应机制，发现ABCC1是响应多环芳烃的关键基因。 $\mathrm { L i n } ^ { [ 6 ] }$ 发现不动杆菌Y在 $\mathrm { 1 \ 0 0 0 m g / L }$ 的苯酚浓度下产生更多的ABC转运蛋白和膜受体来抵抗苯酚产生的氧化压力。细胞处于氧化压力胁迫时，ABC转运蛋白的合成会上调。本研究的转录组测序检测到在 $5 0 0 \mathrm { m g / L }$ 苯酚浓度下，进化后小球藻ABC转运蛋白与原始小球藻相比PstS、ABCC1O、ABCB1、NiKA、Gltl和CystA明显上调，ABCC1和ABCC4下调。这意味着进化后小球藻在驯化过程中，ABC转运蛋白在苯酚氧化压力下也参与响应。需要指出的是,Lin等[6]分析的是在 $\mathrm { 1 \ 0 0 0 m g / L }$ 苯酚条件下不动杆菌部分基因和蛋白质组在 $0 \sim 1 8 \mathrm { h }$ 的动态变化。而本文分析的是在 $5 0 0 \mathrm { m g / L }$ 苯酚条件下进化小球藻和未进化小球藻的转录组学差异，希望能得到进化小球藻和未进化小球藻的响应差异,进而探讨进化机制。

8 8197900 品 8 5853555 57 品 68530 2   
55551 855155 553335 575355 555314 66401   
PstS ABCC10ABCB1 NikA Gltl CysA ABCC1ABCC4

# 2.5氮代谢途径和三羧酸循环分析

藻类可以利用污水中的普通氮源，并且一般会优先利用氨氮,氨氮完全消耗后才开始利用其他氮源[20]]污水中的 $\mathrm { N H } _ { 4 }$ -N 等无机氮的吸收需要光合作用提供能量和碳骨架，进而构成藻细胞内的含氮有机物，如氨基酸、蛋白质、叶绿素等[21]。Erdal 和 Trk[2-23]研究了镉胁迫对玉米幼苗的氮代谢的影响。发现与对照组相比，施用镉的幼苗中硝酸盐还原酶、亚硝酸盐还原酶、谷氨酰胺合酶(GS)和谷氨酸合酶(GOGAT)的活性显著降低，但是谷氨酸脱氢酶(GDH)活性显著升高，表明镉对氮代谢有明显的抑制作用。 $\mathrm { L i n } ^ { [ 6 ] }$ 利用蛋白质组分析了不动杆菌Y在 $\mathrm { 1 \ 0 0 0 m g / L }$ 苯酚浓度胁迫下的压力应激反应，发现其三羧酸循环和氧化磷酸化途径都被下调，说明苯酚胁迫能够抑制氮代谢和碳代谢途径。之前的叶绿素荧光检测数据也表明苯酚胁迫能够抑制原始小球藻的光合作用，而对进化小球藻的光合作用几乎没有影响。本文的转录组测序发现进化小球藻相对于原始小球藻在 $5 0 0 \mathrm { m g / L }$ 苯酚浓度下的氮代谢途径中大部分基因明显上调(表3）。与原始小球藻相比，进化小球藻的氮代谢途径的10多个酶的相关基因出现上调表达。其中硝酸盐同化途径的有硝酸盐还原酶（NR，EC：1.7.99.4）和亚硝酸盐还原酶（NIRA，EC：1.7.7.1)；催化氨代谢过程的有谷氨酸脱氢酶（GDHA，EC：1.4.1.4）、谷氨酰胺合成酶（GLNA，EC:6.3.1.2）和谷氨酸合成酶（GLT1/GLTB/GLTD，EC：1.4.1.13/1.4.1.14/1.4.7.1）；碳酸酐酶(CA，EC：4.2.1.1)能够催化氨甲酰磷酸反应生成氨和ATP，可以作为藻细胞内源氨的补充。

本文的转录组测序结果显示在 $5 0 0 \mathrm { { m g / L } }$ 的苯酚浓度下，进化后小球藻和原始小球藻相比，三羧酸循环中十几种酶或蛋白质表达上调（表4）。Lin的实验中不动杆菌Y在 $\mathrm { 1 \ 0 0 0 m g / L }$ 的苯酚胁迫下氮代谢和碳代谢下调，而对于本次实验检测出来的结果进化小球藻的氮代谢和碳代谢途径上调是相对于原始小球藻上调，产生这种现象的原因是原始小球藻在苯酚胁迫的条件下碳代谢和氮代谢途径下调，而进化小球藻由于经历长期的苯酚压力胁迫进化后能够解除这种抑制作用而维持原有的氮代谢和氮代谢水平，结果显示是进化小球藻的氮代谢和碳代谢上调。当然，也不能排除有微生物特异性及苯酚浓度差异的影响。Santos和Benndorf[24]利用定量蛋白质组学研究恶臭假单胞菌KT2440对苯酚氧化压力的响应，发现参与氧化应激反应、胁迫应答、能量代谢、脂肪酸生物合成、细胞膜生物合成和小分子转运的蛋白质合成上调，而核苷酸合成和运动相关的蛋白合成下调。不同微生物对苯酚氧化压力的响应有特异性，而且响应机制也不尽相同。进化后小球藻之所以能形成这种抵抗苯酚压力的响应机制和其驯化过程是分不开的，长期的苯酚氧化压力胁迫，使进化后小球藻对苯酚氧化压力的响应累加。Lin测定的是蛋白质组，本文测定是转录组。不同组学数据对同一生物过程的分析可能也会出现差异，因为转录和翻译并不是完全同步的。但是进化后小球藻经过长期苯酚压力胁迫后确实能够耐受高浓度苯酚，这与其对苯酚氧化压力胁迫的特殊响应机制是分不开的。

Table 3Difference of gene expression in nitrogen metabolism pathway   
表4三羧酸循环中的差异表达基因  

<html><body><table><tr><td>酶名称</td><td>EC编号</td><td>序列ID</td><td>logFC(L5-500/L3-500)</td><td>FDR</td></tr><tr><td>硝酸盐还原酶</td><td>1.7.99.4</td><td>c37842_g5</td><td>1.22</td><td>3.07E-3</td></tr><tr><td rowspan="4">Nitrate reductase(NR)</td><td></td><td>c37853_g7</td><td>1. 15</td><td>4.98E-3</td></tr><tr><td></td><td>c29088_g2</td><td>3.40</td><td>3.24E-2</td></tr><tr><td></td><td>c29088_g1</td><td>3.90</td><td>2.44E-2</td></tr><tr><td>1.7.2.5</td><td>c14066_g1</td><td>2.80</td><td>4.68E-2</td></tr><tr><td>Nitric oxide reductase 亚硝酸还原酶 Nitrite reductase</td><td>1.7.2.1</td><td>c45422_g1</td><td>3.63</td><td>7.63E-3</td></tr><tr><td>谷氨酰胺合成酶</td><td>6.3.1.2</td><td>c37454_g1</td><td>4.89</td><td>1.08E-2</td></tr><tr><td>Glutamine synthase(GLNA) 谷氨酸脱氢酶</td><td></td><td>c61772_g1</td><td>6.50</td><td>2.93E-5</td></tr><tr><td></td><td>1.4.1.2</td><td>c46133_g1</td><td>3.06</td><td>1.83E-2</td></tr><tr><td>Glutamate d(NADPH）eGDHA)</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>1.4. 1.4</td><td>c37532_g4</td><td>4.16</td><td>2.06E-2</td></tr><tr><td rowspan="9">谷氨酸合成酶 Glutamate synthase(NADPH) (GLTB)</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>c37237_g2</td><td>4.59</td><td>1.14E-4</td></tr><tr><td>1.4.7.1</td><td>c36626_g2</td><td>3.75</td><td>3.50E-4</td></tr><tr><td></td><td>c37701_g1</td><td>4.35</td><td>4.81E-4</td></tr><tr><td>1.4.1. 13</td><td>c29037_g4</td><td>-3.96</td><td>2.04E-3</td></tr><tr><td></td><td>c29037_g2</td><td>-2.41</td><td>8.73E-3</td></tr><tr><td></td><td>c36626_g1</td><td>2.96</td><td>2.96E-3</td></tr><tr><td>1.4.1. 14</td><td>c29037_g4</td><td>-3.96</td><td>2.04E-3</td></tr><tr><td></td><td>c29037_g2</td><td>-2.41</td><td>8.73E-3</td></tr><tr><td rowspan="6">Nitric oxide reductase</td><td></td><td>c35331_g1</td><td>2.96</td><td>2.96E-3</td></tr><tr><td></td><td>c29037_g1</td><td>-2.75</td><td>4.78E-4</td></tr><tr><td>1.7.1. 14</td><td>c60454_g1</td><td>6.60</td><td>4.75E-48</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>1.7.7.1</td><td>c35063_g1</td><td>3.26</td><td>3.93E-2</td></tr><tr><td>Nitrite reductase A（NIRA)</td><td></td><td>c31099_g1</td><td>5.31</td><td>1.69E-3</td></tr><tr><td rowspan="5">碳酸酐酶 Carbonic anhydrase(CA)</td><td></td><td>c6469_g1</td><td>3.60</td><td>1.27E-4</td></tr><tr><td>4.2.1.1</td><td></td><td>4.39</td><td>7.62E-05</td></tr><tr><td></td><td>c39164_g1</td><td>6.11</td><td>7.92E-4</td></tr><tr><td></td><td>c33606_g2 c33606_g1</td><td>7.28</td><td>4.72E-5</td></tr><tr><td></td><td>c16145_g1</td><td>4.03</td><td>4.33E-2</td></tr><tr><td></td><td></td><td>c31827_g1</td><td>7.40</td><td>1.31E-34</td></tr></table></body></html>

表3氮代谢途径中的基因表达差异  
Table 4Difference of gene expression in TCA cycle pathway   

<html><body><table><tr><td>酶名称</td><td>EC编号</td><td>序列ID</td><td>logFC(L5_500/L3_500)</td><td>FDR</td></tr><tr><td>二氢硫辛酰乙酰转移酶</td><td>2.3.1.12</td><td>c31578_g1</td><td>3.53</td><td>2.16E-2</td></tr><tr><td rowspan="4">Dihydrolipoyl acetyltransferase</td><td></td><td>c35020_g1</td><td>2.71</td><td>4.00E-2</td></tr><tr><td></td><td>c37512_g1</td><td>4.61</td><td>1.10E-5</td></tr><tr><td></td><td>c60153_g1</td><td>3.07</td><td>3.91E-2</td></tr><tr><td>1.2.7.1</td><td>c37837_g4</td><td>1.14</td><td>1.45E-2</td></tr><tr><td>丙酮酸合酶 Pyruvate synthase</td><td></td><td></td><td></td><td></td></tr><tr><td>琥珀酰-CoA合成酶</td><td>6.2.1.4</td><td>c7278_g1</td><td>3.07</td><td>4.07E-2</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Succinyl-CoA synthetase</td><td></td><td></td><td></td><td></td></tr></table></body></html>

（续表4）  

<html><body><table><tr><td>酶名称</td><td>EC编号</td><td>序列ID</td><td>logFC(L5_500/L3_500)</td><td>FDR</td></tr><tr><td>草酰琥珀酸脱羧酶</td><td>1.1.1.42</td><td>c52746_g1</td><td>3.80</td><td>2.15E-2</td></tr><tr><td>Oxalosuccinate decarboxylase</td><td></td><td>c3407_g1</td><td>4.93</td><td>1.68E-3</td></tr><tr><td>2-氧代酸氧化还原酶</td><td>1.2.7.11</td><td>c76505_g1</td><td>3.72</td><td>2.34E-2</td></tr><tr><td>2-oxoacid oxidoreductase</td><td></td><td>c27441_g1</td><td>3.39</td><td>2.58E-2</td></tr><tr><td></td><td></td><td>c38616_g1</td><td>3.46</td><td>2.64E-2</td></tr><tr><td></td><td></td><td>c34824_g1</td><td>3.68</td><td>2.20E-2</td></tr><tr><td>ATP 柠檬酸合酶</td><td>2.3.3.8</td><td>c35348_g1</td><td>4.26</td><td>1.73E-2</td></tr><tr><td>ATP citrate synthase</td><td></td><td></td><td></td><td></td></tr><tr><td>苹果酸脱氢酶</td><td>1. 1. 1.37</td><td>c52908_g1</td><td>5.70</td><td>8.17E-4</td></tr><tr><td>Malate dehydrogenase</td><td></td><td>c61382_g1</td><td>5.48</td><td>1.26E-3</td></tr><tr><td></td><td></td><td>c59960_g1</td><td>2.00</td><td>2.71E-9</td></tr><tr><td>二氢硫辛酸脱氢酶</td><td>1.8.1.4</td><td>c35851_g1</td><td>4.04</td><td>6.58E-3</td></tr><tr><td>Dihydrolipoyl dehydrogenase ;</td><td></td><td>c34235_g1</td><td>2.88</td><td>3.42E-2</td></tr><tr><td></td><td></td><td>c34729_g1</td><td>3.82</td><td>3.04E-3</td></tr><tr><td>琥珀酸脱氢酶</td><td>1.3.5.1</td><td>c14707_g1</td><td>4.35</td><td>2.31E-2</td></tr><tr><td>Succinate dehydrogenase</td><td></td><td></td><td></td><td></td></tr><tr><td>磷酸烯醇丙酮酸羧激酶</td><td>4. 1.1.49</td><td>c34546_g1</td><td>-3.16</td><td>8.43E-19</td></tr><tr><td>Phosphoenolpyruvate carboxykinase （ATP)</td><td></td><td>c33496_g1</td><td>3.86</td><td>6.38E-3</td></tr><tr><td>乌头酸水合酶</td><td>4.2.1.3</td><td>c37471_g1</td><td>4.25</td><td>7.24E-4</td></tr><tr><td>Aconitate hydratase</td><td></td><td>c34863_g1</td><td>2.70</td><td>2.74 E-2</td></tr><tr><td></td><td></td><td>c36106_g3</td><td>3.20</td><td>8.52E-3</td></tr><tr><td>延胡索酸水合酶</td><td>4.2.1.2</td><td>c37696_g1</td><td>3.79</td><td>2.69 E-2</td></tr><tr><td>Fumarate hydratase</td><td></td><td></td><td></td><td></td></tr><tr><td>苹果酸脱氢酶</td><td>1.1.5.4</td><td>c37805_g4</td><td>1.22</td><td>3.40 E-2</td></tr><tr><td>Malate dehydrogenase</td><td></td><td></td><td></td><td></td></tr><tr><td>硫辛酸转琥珀酰基酶 Dihydrolipoic transsuccinylase</td><td>2.3.1.61</td><td>c37157_g2</td><td>3.61</td><td>3.39E-3</td></tr><tr><td></td><td></td><td>c37053_g3</td><td>3.19</td><td>3.86E-2</td></tr><tr><td rowspan="6">丙酮酸脱羧酶 Pyruvate decarboxylase</td><td></td><td>c22365_g1</td><td>4.71</td><td>1.38E-5</td></tr><tr><td></td><td>c37650_g31</td><td>-3.14</td><td>2.53E-2</td></tr><tr><td>1.2.4.1</td><td></td><td></td><td></td></tr><tr><td></td><td>c76505_g1</td><td>3.72</td><td>2.34E-2</td></tr><tr><td></td><td>c27441_g1</td><td>3.39</td><td>2.58E-2</td></tr><tr><td></td><td>c38616_g1 c34824_g1</td><td>3.46 3.68</td><td>2.64E-2 2.20E-2</td></tr></table></body></html>

# 3结论

(1)未进化小球藻和进化小球藻在苯酚氧化压力下都会在做出响应，这些响应主要体现在信号转导、蛋白质合成和基础代谢方面。

(2)进化后小球藻在进化过程中，由于长期处于苯酚氧化压力下，对苯酚氧化胁迫的响应得到积累，并且通过增加细胞信号转导、热休克蛋白和ABC转运蛋白的合成，与原始小球藻相比上调碳代谢和氮代谢等来增强对高浓度苯酚的响应，能够快速清除苯酚诱导产生的活性氧，使其对苯酚的耐受性提高。

(3)氮代谢途径和三羧酸循环作为苯酚氧化胁迫的间接响应，为细胞提供足够的能量用于对活性氧的清除。

# 参考文献

[1］Adav SS,Lee DJ.Physiological characterization and interactions of isolates in phenol-degrading aerobic granules.Journal of Applied Microbiology and Biotechnology，2008，78（5）：899- 905.   
[2]Li HQ，Han HJ，Du M A，et al.Removal of phenols, thiocyanate and ammonium from coal gasification wastewater using moving bed biofilm reactor.Bioresource Technology，2O11，102 (7)：4667-4673.   
[3］Basak B，Bhunia B，Dey A．Studies on the potential use of sugarcane bagasse as carrier matrix for immobilization of Candida tropicalisPHB5forphenolbiodegradation. International Biodeterioration & Biodegradation，2014,93（1）：107-117.   
[4]Rezvani F,Azargoshasb H,Jamialahmadi O,et al.Experimental study and CFD simulation of phenol removal by immobilization of soybean seed coat in a packed-bed bioreactor.Biochemical Engineering Journal,2015，101（1） :32-43.   
[5]Wang L B,Xue C Z，Wang L，et al．Strain improvement of Chlorella sp.for phenol biodegradation byadaptive laboratory evolution．Bioresource Technology，2016,205(1）：264-268.   
[6］Lin J.Stress responses of Acinetobacter strain Y during phenol degradation．Archives of Microbiology，2016,31(3）：1-11.   
[7]Grabherr，MG，Haas BJ，Yassour M，et al．Full-length transcriptome assembly from RNA-Seq data without a reference genome.Nature Biotechnology，2011,29（7）: 644-652.   
8]Gish W, States D J.Identification of protein coding regions by a database similarity search．Nature Genetics，1993,3（3）：266- 00272. ） Camacho C，Coulouris G，Avagyan V，et al．BLAST ： $^ +$ architecture and applications．BMC Bioinformatics，2009，10 (1) :421. 0 Conesa A，Gotz S，Garcia-Gomez JM，et al.Blast2GO：a universal tool for annotation， visualizationand analysisin functional genomics research．Bioinformatics，2005，21（18）： 3674-3676.   
[11] Xie C, Mao X, Huang J,et al. KOBAS 2.O: a web server for annotation and identification of enriched pathways and diseases. Nucleic Acids Research,2011,39(52）: W316-322.   
[12]Hochberg Y，Ba Y.Controlling the false discovery rate：a practical and powerful approach to multiple testing.Journal of the RoyalSt   
[13]Robinson M D，McCarthy D J，Smyth G K.Edge R：a Bioconductor package for differential expression analysis of digital gene expression data. Bioinformatics，,2010,26(1）:139-140.   
[14]Mittler R，Vanderauwera S，Gollery M，et al．.Reactive oxygen gene network of plants．Trends in Plant Science，2OO2,9（10）： 490-498.   
[15]Luo Z B,He J,Polle A,et al.Heavy metal accumulation and signal transduction in herbaceous and woody plants:paving the way for enhancing phytoremediation efficiency.Biote Chnology Advances，2016,34(6):1131-1148.   
[16]Feder M E，Hofmann G E.Heat-shock proteins，molecular chaperones，and the stress response：evolutionary and ecological physiology．Annual Review of Physiology，1999,61（1）：243- 282.   
[17］Zhao P,Guo Y，Zhang W，et al．Neurotoxicity induced by arsenic in Gallus：Regulation of oxidative stress and heat shock protein response.Chemosphere,2017,97(1）：238-245.   
[18]Chaurasia M K，Nizam F,Ravichandran G，et al．Molecular importance of prawn large heat shock proteins 6O,7O and 90. Fish & Shelfish Immunology，2016,48（9）:228-238.   
[19]Jeong C B，Kim H S,Kang H M，et al.Genome-wide identification of ATP-binding cassette（ABC）transporters and conservation of their xenobiotic transporter function in the monogonontrotifer（Brachionuskoreanus ）．Comparative Biochemistry and Physiology Part D：Genomics and Proteomics, 2017,21(13): 17-26.   
[20］Jeong C B，Kim D H，Kang H M，et al.Genome-wide identification of ATP-binding cassette（ABC）transporters and their rolesinresponse topolycyclicaromatic hydrocarbons （PAHs）in thecopepod Paracyclopina nana.Aquatic Toxicology，2017,183（1）：144-155.   
[21]Ohmori M,Ohmori K,Strotmann H,et al．Inhibition of nitrate uptake by ammonia in a blue-green alga，Anabaena cylindrica. Archives of Microbiology，1977,114(3）:225-229.   
[22]Mcgriff E C，Mckinney R E.The removal of nutrients and organics by activated algae．Water Research，1972,6（10）: 1155-1164.   
[23]Erdal S,Turk H. Cysteine-induced upregulation of nitrogen metabolism-related genes and enzyme activities enhance tolerance of maize seedlingsto cadmium stress.Environmental and Experimental Botany，2016,132(23）：92-99.   
[24]Santos P M，Benndorf D. Insights into Pseudomonas putida KT2440 response tophenol-induced stressbyquantitative proteomics．Proteomics，2004，4（9）:2640-2652.

# Transcriptomic Analysis of Response to Phenol of Evolved and Unevolved Chlorella Strains

AbstractPhenol isa typical environmental pollutant.Chlorella sp.is potential strain for wastewater treatment because of its fast growth and strong resistance.Chlorella sp.could degrade phenol in industrial wastewater but oxidative stress induced by high concentration of phenol could cause oxidative damage in algal cells.Adaptive evolution was performed to improve the tolerance to phenol of Chlorella sp.（L5）in previous study.The response mechanism of Chlorella sp.to oxidative stress induced by high concentration phenol was explored by de novo comparative transcriptomic analysis on genome scale.It was shown that the evolved strain could tolerate and degrade phenol was related to metabolic regulations in multiple pathways. The results of $d e$ novO comparative transcriptomic analysis showed that the genes related to signal transduction，ABC transporter and heat shock protein were significantly up-regulated at $5 0 0 \mathrm { m g / L }$ phenol concentration compared to those in the original（L3）cells. Those genes in nitrogen metabolism and tricarboxylic acid cycle（TCA）were also upregulated.The evolved strain（L5）could reduce oxidation pressure induced by high concentration of phenol through the metabolic regulations in these metabolic pathways.

lKey wordsPhenol TranscriptomicsNitrogen metabolismTCA cycle Chlorella