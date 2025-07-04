# 利用SpyTag/SpyCatcher构建胞内自组装多酶复合体实现高效生物合成

刘璐殷亮 黄飞 张勇刘倩 冯雁 \*\*（上海交通大学生命科学技术学院 微生物代谢国家重点实验室上海200240)

摘要SpyCatcher和 SpyTag可通过自发反应形成共价键，产生稳定的分子自组装体。酶分子自组装体因具有高效有序的催化特性在合成生物学和纳米技术领域具有重要的应用价值。为探索 SpyTag/SpyCatcher在大肠杆菌胞内多酶复合体系形成有序自组装分子能力，将SpyCatcher和SpyTag分别与P450BM3m单加氧酶和葡萄糖脱氢酶GDH进行融合表达，以期产生具有辅酶再生循环系统、高效生物合成靛蓝分子的 SpyTag/SpyCatcher双酶自组装复合体。首先，通过电泳及质谱对重组工程菌表达蛋白进行分析，证实 SpyCatcher-P450BM3m与 SpyTag-GDH在胞内成功形成了自组装多酶复合体；然后，系统分析了不同培养条件下组装体合成靛蓝的能力，结果发现，经 $0 . 5 \mathrm { m m o l / L }$ IPTG诱导后，菌体在16℃继续培养 $1 8 \mathrm { h }$ 后，工程菌对吲哚（2mmol/L）与葡萄糖（ $\mathrm { \cdot } 4 \mathrm { m m o l / L }$ ）的全细胞催化能力最强，靛蓝产量最高达 $2 5 8 ~ \mathrm { m g / L }$ ，是未组装多酶系统的1.9倍，比 $\mathrm { P } 4 5 0 \mathrm { B M } 3 \mathrm { m }$ 单酶表达系统高约2.4倍；反应 $7 0 \mathrm { m i n }$ 后达到反应平衡，转化率为 $52 \%$ 。本研究成功实现了 SpyTag/SpyCatcher介导的多酶体系在大肠杆菌细胞中的自组装和高效转化体系，为胞内多酶复合物组装体的设计提供了新思路。

关键词 SpyTag/SpyCatcher 自组装多酶复合物辅酶再生靛蓝

# Construction of Intracellular Self-assembled Multienzyme Complex by SpyTag/SpyCatcher to Achieve Efficient Biosynthesis

LIU Lu YIN Liang HUANG Fei ZHANG Yong LIU Qian FENG Yan\*\* (State Key Laboratory of Microbial Metabolism，School of Life Sciences and Biotechnology, Shanghai Jiaotong University，Shanghai 2Oo24o，China)

AbstractSpyCatcher can form an ireversible covalent linkage to its partner SpyTag via a spontaneous isopeptide bond. To explore the potential application of SpyTag/SpyCatcher system in the self-assembly of multiple enzyme complex in Escherechia coli, SpyCatcher and SpyTag were fused with P450BM3m monooxygenase and glucose dehydrogenase(GDH),respectively. The fusion proteins co-expressed in vivo were expected to self-assemble into a double-enzyme complex with the ability of coenzyme regeneration and eficient biosynthesis of indigo.At first, the self-assembled multienzyme complex formed via SpyTag/SpyCatcher system in vivo was confirmed by SDS-PAGE and Nano-Liquid Chromatography. After that, the ability to synthesize indigo by multienzyme complex was systematically analyzed under different culture conditions. When induced at $1 6 ~ \mathrm { { ^ circ C } }$ with $0 . 5 \ \mathrm { m m o l / L }$ IPTG, the engineered bacteria showed robust ability to catalyze indole $( 2 ~ \mathrm { \ m m o l / L }$ ）and glucose $( 4 ~ \mathrm { \ m m o l / L } )$ .The yield of indigo produced by self-assembled complex cells was up to $2 5 8 ~ \mathrm { m g / L }$ ,which was 1.9 and 2.4 times higher than that of cells with free enzymes and $\mathrm { P } 4 5 0 \mathrm { B M } 3 \mathrm { m }$ single enzyme system accordingly. The conversion rate was $52 \%$ when reaction was balanced after $7 0 ~ \mathrm { \ m i n }$ . These findings suggest that the SpyTag/SpyCatcher system can successfully assemble multienzyme complex for efficient biosynthesis of chemicals,which provide a new idea for the design of intracellular multienzyme complex assembly.

Key WordsSpyTag/SpyCatcherSelf-assemblymultienzyme complexcoenzyme regenerationindigo

多酶复合体系因其高效的整体催化能力已成为合成生物学的研究热点，构建高效稳定的人工多酶反应器在生物催化领域具有广阔的应用前景[1]。近年来，研究者通过蛋白脚手架、DNA脚手架及多肽或蛋白介导的无骨架自组装技术等在胞内成功构建了多个人工多酶反应系统。如JayD.Keasling等利用自组装信号通路蛋白，在胞内将甲羟戊酸途径酶组装起来，使其产量提高77倍[2]；RobertJ等利用锌指结构与DNA结合序列之间高亲和力特异的相互作用机制，设计了可控的DNA-蛋白质骨架系统，将白藜芦醇在大肠杆菌中产量提高了50 倍[3]；Wei 等利用 SHM相互作用蛋白的介导，在胞内对人参皂苷合成途径的关键酶进行共组装，使人参皂苷前体达玛烯二醇-ⅡI在毕赤酵母中产量提高了2.1倍[4]。然而上述研究多采用非共价的组装模块，易受细胞生长环境如温度、pH、离子强度等因素的影响，导致多酶复合体系不稳定，从而影响级联反应的催化效率[5,6]。因此探索和挖掘共价偶联组装模块，构建更加稳定的多酶催化组装体系仍具有重要实际意义。

源于CnaB2结构域的 SpyTag/SpyCatcher体系，以其在多种条件下均能自发形成稳定异肽键的优势在蛋白质领域获得广泛应用，如生物耦联、疫苗的合成和耐热酶的制备等[7-10]。CnaB2 是 Streptcoccuspyogenes 纤粘连蛋白 FbaB 中分离出来的一个结构域[11]。CnaB2 可被拆分为两个部分：SpyTag（13 个氨基酸残基)和 SpyCatcher（116 个氨基酸残基）[12]。SpyTag 中的 Asp 和 SpyCatcher上的Lys能自发反应生成异肽共价键[13]。因此SpyTag/SpyCatcher 体系在作为多酶自组装工具上，有着重要的应用潜力。

为了探索 SpyTag/SpyCatcher体系在构建人工多酶反应系统中的应用，我们设计将 SpyCatcher和 SpyTag 分别与P450BM3（A74G/F87V/L188Q）单加氧化酶和葡萄糖脱氢酶GDH进行融合，通过胞内共表达，以实现双酶自组装，产生高效的辅酶再生循环系统，应用于生物合成靛蓝分子。P450BM（A74G/F87V/

L188Q）是来源于Bacillusmegaterium的细胞色素单加氧酶突变体[14]，作为一类NADPH依赖型氧化还原酶能催化吲哚产生靛蓝分子[15]。已有研究暗示大肠杆菌胞内NADPH无法满足细胞工厂持续进行生物合成靛蓝，可通过设计高效的辅酶再生循环系统，提高其生物合成效率[16]。研究中，我们选择了来源于Bacillussubtilis 的葡萄糖脱氢酶(glucose dehydrogenase，GDH)作为NADPH辅因子的循环再生的驱动酶。通过细胞内自组装多酶复合体的构建，将 $\mathrm { P } 4 5 0 \mathrm { B M } 3 \mathrm { m }$ 和GDH在空间上组装起来，使两酶之间形成有序的辅酶传递通道，从而实现高效生物合成[17]。

本实验中，我们将 SpyCatcher、SpyTag 分别与 P450BM3m 和GDH进行基因融合，通过胞内共表达 SpyCatcher-P450BM3m 和 SpyTag-GDH，成功构建一个自组装多酶复合物，实现了靛蓝分子生物合成。随后对自组装多酶系统进行优化，分析了构建的辅酶再生循环系统效能，证实了含有自组装辅酶再生系统的细菌具有更优生物合成效率。该研究为进一步利用 SpyTag/SpyCatcher作为自组装工具在合成生物学的应用奠定了基础。

# 1材料与方法

# 1.1 材料

1.1.1菌种与质粒E.coliBL21(DE3)，表达质粒pET28a $( + )$ ，pACYCDuet-1购自 Novagen 公司。含目的基因的质粒 pET28a-GDH、pET28a-SpyTag-GDH、pET28a-P450BM3m及pET28a-SpyCatcher-P450BM3m均已由本实验构建保存。  
1.1.2 培养基 LB 培养基 $( \mathbf { g } / \mathrm { L } )$ ：胰蛋白陈 $1 0 \mathrm { { g } }$ ，酵母提取物 ${ 5 } \mathrm { g }$ ，氯化钠 $1 0 \mathrm { { g } }$ 。添加 $2 \%$ 的琼脂为LB 固体培养基。  
1.1.3 工具酶与试剂限制性内切酶购自Fermentas 公司，T4DNA连接酶购自NEB公司，PrimeSTARMaxDNA聚合酶购自TaKaRa公司，质粒提取试剂盒和PCR 纯化试剂盒购自Axygen公司。其他均为分析纯试剂。

# 1.2自组装多酶复合物细胞的构建

1.2.1GDH重组质粒构建将 pET28a-GDH（GDH基因序列位于载体的 NcoI 和XhoI之间）经NcoI和XhoI双酶切后与同样双酶切的载体pACYCDuet-1连接后转入BL21（DE3)，送至华大基因（上海）有限公司测序。构建成功的重 组质 粒命 名为 pACYCDuet1-GDH。pET28a-SpyTag-GDH（SpyTag-GDH基因序列位于载体的NcoI和XhoI之间）与载体pACYCDuet-1双酶切后连接的重组质粒命名为pACYCDuet1-SpyTag-GDH。

1.2.2SpyTag/SpyCatcher 结合位点突变构建对照质粒以pACYCDuet1-SpyTag-GDH为模板，设计引物（G-F:TGATGGTGGCCGCCTATAAGCCGACCA，G-R:TTATAGGCGGCCACCATCACGATATGG，下划线为用Ala替代SpyTag的Asp），用Primer Star进行全质粒PCR扩增，构建成功的重组质粒命名为 pACYCDuet1-mSpyTag-GDH 。 以pET28a-SpyCatcher-P450BM3m 为模板，设计引物(P-F:AGTTCAGCGCCCGCGATGAAGACGGCA，P-R: TCATCGCGGGCGCTGAACTTGATGTGG，下划线为用Ala 替代SpyCatcher上的结合位点Lys）进行全质粒PCR扩增，构建成功的重组质粒命名为pET28a-mSpyCatcher-P450BM3m。

1.2.3自组装辅酶再生循环体系细胞的构建将pET28a-SpyCatcher-P450BM3m和pACYCDuetl-SpyTag-GDH 质 粒同时转入 E.coliBL21(DE3)，共表达SpyCatcher-P450BM3m 和 SpyTag-GDH 的重 组菌 命名为E.coli BL21(DE3)-S。按照表1构建其余8种重组工程菌作为对照。

表1表达重组质粒的EcoliBL21(DE3)工程菌的构建  
Table1 Construction of E.coli BL21 (DE3) expressing recombinant plasmid   

<html><body><table><tr><td rowspan="2">Plasmid</td><td colspan="8">Bacterial Strain E.coliBL21(DE3)-X</td></tr><tr><td>1</td><td>2</td><td>mSl)</td><td>4</td><td>5</td><td>NS2)</td><td>7</td><td>8</td><td>S3)</td></tr><tr><td>pACYCDuetl-mSpyTag-GDH</td><td>+</td><td>=</td><td>+</td><td></td><td>1</td><td></td><td></td><td></td><td></td></tr><tr><td>pET28a-mSpyCatcher-P450BM3m</td><td></td><td>+</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>pACYCDuet1-GDH</td><td></td><td></td><td></td><td></td><td></td><td>+</td><td></td><td></td><td></td></tr><tr><td>pET28a-P450BM3m</td><td></td><td></td><td></td><td></td><td>+</td><td>+</td><td></td><td></td><td></td></tr><tr><td>pACYCDuet1-SpyTag-GDH</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>+</td></tr><tr><td>pET28a-SpyCatcher-P450BM3m</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>+</td><td>+</td></tr></table></body></html>

$^ { 1 ) } E$ .coli BL21(DE3)-mSco-expresing mSpyTag-GDHandmSpyCatcher-P450BM3m;²E.coliBL1(DE3)-NSco-expressngGDHand P450BM3m; $^ { 3 ) } E .$ coli BL21 (DE3)-Sco-expressing SpyTag-GDHand SpyCatcher-P450BM3m

# 1.3胞内自组装验证

1.3.1融合蛋白共表达将 E.coli BL21(DE3)-NS、E.coli BL21 (DE3)-S 和 E.coliBL21 (DE3)- $. m \mathrm { s }$ 接种于含 $1 0 0 ~ \mathrm { \mu g / m l }$ 卡纳霉素和 $2 5 ~ \mathrm { \mu g / m l }$ 氯霉素的LB 培养基中， $3 7 \ \mathrm { ^ { \circ } C } , 2 2 0 \ \mathrm { r / m i n }$ 培养至 $\mathrm { O D } _ { 6 0 0 }$ 值为0.6,加入终浓度为 $0 . 1 \mathrm { m m o l / L }$ 的IPTG于 $1 6 ~ \mathrm { { ^ \circ C } }$ ， $2 2 0 ~ \mathrm { r / m i n }$ 的条件下培养 $1 8 \mathrm { h }$ 。培养结束后取等体积相同 $\mathrm { O D } _ { 6 0 0 }$ 的菌体进行SDS-PAGE蛋白电泳，以分析蛋白组装情况。

1.3.2纳米液相四级杆飞行时间质谱将蛋白条带用胰蛋白酶在 $5 8 \mathrm { ~ \textdegree C }$ 水浴下快速酶解 $3 0 \mathrm { m i n }$ ，酶解干燥后的多肽用Sep-Pak 脱盐柱处理样品。洗脱的样品干燥后用 $3 0 \mu \mathrm { L } 2 \% \mathrm { A C N } , 0 . 1 \% \mathrm { F A }$ 的上样缓冲液溶解样品，LC-MS分析。

HPLC-MS条件及过程：液相色谱分析柱为C18反相分析柱 $7 5 \mu \mathrm { m } \times 1 5$ $\mathsf { c m } \times 3 \ \mu \mathrm { m } )$ ；多肽富集柱为C18反相柱 $7 5 \ \mu \mathrm { m } { \times } 2 \ \mathrm { c m } { \times } 3 \ \mu \mathrm { m } )$ 。流动相A为$9 9 . 9 \%$ 水和 $0 . 1 \%$ 甲酸混合液，流动相B为 $9 9 . 9 \%$ 乙腈和 $0 . 1 \%$ 甲酸混合液，流动相流速为 $3 0 0 ~ \mathrm { { n L / m i n } }$ 。ESI+模式，质谱电喷雾毛细管电压设置为2000$\mathrm { \Delta V }$ ，气体流速设置为 $2 . 0 \mathrm { L } / \mathrm { m i n }$ ，离子源温度为 $1 2 0 \ \mathrm { ^ { \circ } C }$ ，选择母离子质核比

为350-1500的进行二级碎裂。

数据处理：使用DataAnalysis4.1软件提取离子峰。Mascot2.4搜索引擎搜索蛋白数据库。母离子质量容差： $2 . 5 { \times } 1 0 ^ { - 5 }$ ，二级谱图质量容差：$0 . 0 5 0 \mathrm { u }$ ，胰酶最大漏切位点数为2。

# 1.4重组GDH和P450BM3酶催化活性分析

1.4.1GDH及P450BM3蛋白浓度测定Ni-NTA亲和层析纯化后的GDH、SpyTag-GDH采用BCA 法测定蛋白浓度，其方法参照BCAProteinQuantificationKit操作手册进行（翊圣生物公司，上海）。

P450BM3m、SpyCatcher-P450BM3m采用CO差示光谱图法测定酶浓[18]。取 $1 0 \mathrm { m g }$ 连二硫酸盐加入到酶液中，将酶液分为两部分，加到两试管中。其中一根试管中通入CO约 $1 . 5 \mathrm { m i n }$ ，然后立即使用紫外分光光度计对酶液进行扫描。扫描波长范围为 $4 0 0 { - } 5 0 0 ~ \mathrm { n m }$ ， $\mathrm { P 4 5 0 B M 3 m }$ 浓度由得到的CO 差示光谱图按照摩尔消光系数 $\Xi _ { 4 5 0 - 4 9 0 } { = } 9 1 \ \mathrm { m M ^ { - 1 } { \cdot } c m ^ { - 1 } }$ 计算。

$$
\mathrm { C _ { P 4 5 0 } [ \mathrm { { \mu m o l / L } ] = \Omega ( A 4 5 0 \mathrm { { - } A 4 9 0 ) \ ^ { \ast } 1 ^ { \ast } 1 0 0 0 / 9 1 } } }
$$

1.4.2GDH 及 $\mathrm { P } 4 5 0 \mathrm { B M } 3 \mathrm { m }$ 酶活力 测定GDH、SpyTag-GDH酶活测定体系：20mmol/LTris-HCl缓冲液（ $\mathrm { p H } 8 . 0 \AA )$ ， $0 . 1 \ \mathrm { m o l / L } \ \mathrm { N a C l }$ ， $2 0 0 \mathrm { m m o l / L }$ 葡萄糖，$2 0 0 \mu \mathrm { m o l / L N A D P ^ { + } }$ ， $2 \mu \mathrm { m o l / L }$ 待检测酶，加超纯水补齐至 $\mathrm { 1 ~ m l }$ 。在酶标仪上检测 $3 4 0 \mathrm { n m }$ 处吸光值的变化。酶活力单位定义： $2 5 \ \mathrm { { ^ \circ C } }$ 下每分钟催化产生 $1 \mu \mathrm { m o l } \mathrm { N A D P H }$ 所需的酶量。

P450BM3m、SpyCatcher-P450BM3m 酶活 测 定体系： $2 0 \ \mathrm { m m o l / L }$ Tris-HCl缓冲液（ $\mathrm { \cdot p H } 8 . 0 )$ ， $0 . 1 \ \mathrm { m o l / L } \ \mathrm { N a C l }$ ， $5 \mathrm { m m o l / L }$ 吲哚， $1 0 0 \mathrm { \ : \mu m o l / L }$ NADPH, $1 \mu \mathrm { m o l / L }$ 待检测酶，加超纯水补齐到 $\mathrm { 1 ~ m l }$ 。在酶标仪上检测340nm 处吸收值的变化。酶活力单位定义： $2 5 \ \mathrm { { ^ \circ C } }$ 下每分钟消耗 $1 \mu \mathrm { m o l }$ NADPH所需的酶量。

1.5靛蓝浓度检测重组菌诱导培养结束后，向培养液中加入吲哚和葡萄糖进行反应。 $1 6 ~ \mathrm { { ^ \circ C } }$ 下反应 $1 0 \mathrm { m i n }$ 后， $8 0 0 0 ~ \mathrm { r / m i n }$ 离心 $1 0 \mathrm { m i n }$ ，去掉上清，向沉淀物加入适量N,N-二甲基甲酰胺，超声溶解， $8 0 0 0 ~ \mathrm { r / m i n }$ 离心 $1 0 \mathrm { m i n }$ ，测定上清液在610nm 处的吸光值[19]。靛蓝浓度由标准曲线求得（ $\scriptstyle \cdot \mathbf { A } _ { 6 1 0 } = 0 . 0 3 8 + 0 . 9 1 8 \mathbf { C }$ ， $\mathrm { R } ^ { 2 } { = } 0 . 9 9 6 \$ ）

# 2结果与讨论

# 2.1胞内自组装蛋白表达及组装验证

将SpyTag 和 SpyCatcher分别与GDH和P450BM3m基因融合，构建自组装基 元 SpyTag-GDH 与 SpyCatcher-P450BM3m。 为了 验 证 SpyTag-GDH 与SpyCatcher-P450BM3m在胞内完成了自组装，按照表1构建了9种重组工程菌。将9种重组菌诱导表达 $1 8 \mathrm { ~ h ~ }$ 后取等体积相同 $\mathrm { O D } _ { 6 0 0 }$ 的菌体进行 SDS-PAGE电泳分析。GDH、SpyTag-GDH分子量分别为30、 $3 5 \mathrm { { k D a } }$ ，P450BM3 和 SpyCatcher-P450BM3m分子量为119、 $1 3 1 \mathrm { { k D a } }$ ，自组装多酶复合物分子量约为 $1 6 6 \mathrm { { k D a } }$ 。从图1可以看出，对比分析含组装基元的重组菌，共表达 SpyTag-GDH与

SpyCatcher-P450BM3m的大肠杆菌体内有检测到目标自组装多酶复合物条带，而表达单组装基元的重组菌没有检测到目标自组装蛋白条带（图1中7、8、9泳道），说明 SpyTag-GDH与 SpyCatcher-P450BM3m 的共表达是实现GDH 和P450BM3m 在胞内自组装的关键。与不带 SpyTag/SpyCatcher的细胞比较，不带SpyTag/SpyCatcher的重组菌未检测到自组装复合物条带（图1中4、5、6泳道），说明GDH和 $\mathrm { P 4 5 0 B M 3 m }$ 自组装是通过 SpyTag 和 SpyCatcher 相互作用实现的。与组装基元结合位点突变的重组菌比较，SpyTag/SpyCatcher结合位点失活的细胞没有检测到自组装多酶复合物条带（图1中1、2、3泳道)，该结果与文献报道的自组装机制相一致：SpyTag/SpyCatcher体系通过 Spytag 的天冬氨酸与SpyCatcher的赖氨酸形成共价键实现分子粘合[12]。

![](images/b0962cd870dd65caf1880336193bf2441cb1fc327157a8a36f5b45577ee77538.jpg)  
图1SDS-PAGE电泳分析SpyTag-GDH和SpyCatcher-P450BM3m组装图 Fig.1 SDS-PAGE analysis of assembly of SpyTag-GDH and SpyCatcher-P450BM3m

LaneM:Protein Marker;lane1:bacteriaexpressingmSpyTag-GDH;lane2:bacteriaexpresingmSpyCatcher-P450BM3m;lane3: bacteria co-expressing $m$ SpyTag-GDH and mSpyCatcher-P450BM3m; lane 4: bacteria expressng GDH;lane 5:bacteria expressing P450BM3m;lne6:bacteriacexpressgGDHand45BM3m;lane7:bacteriaexpresingSpyg-GH;lane8:bacteriaepsing SpyCatcher-P450BM3m; lane 9: bacteria co-expressing SpyTag-GDH and SpyCatcher-P450BM3m.

对SDS-PAGE检测到的自组装蛋白条带用纳米液相四级杆飞行时间质谱进行定性分析。Mascot 软件分析 SpyTag-GDH 和 SpyCatcher-P450BM3m 的序列，自组装蛋白条带 SpyTag-GDH和 SpyCatcher-P450BM3m 的 coverage 分别为 $74 \%$ 和 $63 \%$ 。对筛选到的 $\mathbf { P } { < } 0 . 0 1$ 肽段手动提取质谱原始图谱进行二次验证，图2a是 SpyCatcher-P450BM3mMS/MS 质谱图，2b 显示是 SpyTag-GDHMS/MS 质谱图。从这两个蛋白的二级质谱图分析得出，该自组装蛋白条带包含 SpyTag-GDH和SpyCatcher-P450BM3m蛋白,结合图1SDS-PAGE 结果可以证实 SpyTag-GDH和SpyCatcher-P450BM3m在大肠杆菌体内成功完成了自组装。

![](images/c082067bd209074d526e1fd38e81b096c62e7f4054b6aac9f636979c44faff60.jpg)  
图2SpyTag-GDH和SpyCatcher-P450BM3的MS/MS图谱 Fig.2MS/MS spectrums ofSpyTag-GDH and SpyCatcher-P450BM3m

(a) MS/MS spectrum of SpyCatcher-P450BM3m (b) MS/MS spectrum of SpyTag-GDH

# 2.2重组GDH和P450BM3m酶活测定

为了研究融合的 SpyTag 和 SpyCatcher 对GDH 和P450BM3m 酶活的影响，我们将含有 GDH、P450BM3m、SpyTag-GDH 和 SpyCatcher-P450BM3m 重组基因的大肠杆菌诱导培养 $1 8 \mathrm { { h } }$ 后，用镍柱亲和层析纯化各蛋白，对纯化后的蛋白进行酶活测定，酶活测定结果如表2所示。融入短肽后的 SpyTag-GDH与原始GDH的酶活几乎一致，且融合蛋白SpyCatcher也不会改变原始细胞色素P450BM3（A74G/F87V/L188Q）的酶活。结果表明，融合的 SpyTag 和 SpyCatcher不会影响GDH和 $\mathrm { P } 4 5 0 \mathrm { B M } 3 \mathrm { m }$ 的酶活。

表2重组蛋白酶活比较Table2 Comparison of specific acitivites of recombinant enzymes  

<html><body><table><tr><td>Protein</td><td>Specific activity (U/mg)</td></tr><tr><td>GDH</td><td>3.076±0.42</td></tr><tr><td>SpyTag-GDH</td><td>3.13±0.86</td></tr><tr><td>P450BM3m</td><td>180.22±17.5</td></tr><tr><td>SpyCatcher-P450BM3m</td><td>187.83±8.2</td></tr></table></body></html>

# 2.3自组装多酶复合物细胞应用于靛蓝制备

目前已知影响大肠杆菌发酵产量的因素主要包括培养基、温度、诱导时间以及 IPTG浓度等[20]。为了进一步提高自组装多酶细胞的靛蓝产量，我们对其生物合成工艺作进一步优化。

不同浓度诱导剂对自组装细胞和共表达非组装细胞的催化速率影响较大。将E.coli BL21 (DE3)-S 和 E.coli BL21 (DE3)-NS 培养至 $\mathrm { O D } _ { 6 0 0 }$ 为0.6时，分别加入终浓度为 $0 . 0 5 , 0 . 1 , 0 . 2 , 0 . 3$ 和 $0 . 5 \mathrm { m m o l / L }$ 的 IPTG诱导培养 $1 8 \mathrm { h }$ 后加入终浓度为 $2 \mathrm { m m o l / L }$ 的吲哚和 $4 \mathrm { m m o l / L }$ 的葡萄糖进行反应，测定单位体积相同 $\mathrm { O D } _ { 6 0 0 }$ 的靛蓝产量。如图3所示，IPTG浓度在 $0 . 2 \mathrm { m m o l / L }$ 时，未组装细胞的靛蓝产量达到最大 $1 7 0 { \pm } 6 . 8 \ \mathrm { m g / L }$ ，IPTG 浓度在 $0 . 5 \mathrm { m m o l / L }$ 时，自组装细胞的靛蓝产量达到最大 $2 5 1 { \pm } 1 3 . 9 \mathrm { m g / L }$ ，且在此浓度下，自组装与未组装细胞的催化速率相差最大，自组装细胞的催化速率是未组装细胞的1.89倍，说明在该浓度下自组装多酶复合物形成的辅酶传递通道对反应催化速率影响最大，因此选择 $0 . 5 \mathrm { m m o l / L }$ IPTG为最佳诱导剂量。

![](images/82f69e77a98b6c92300d7053a6a2fdd3157de94ae3aca085d1fafe445f644005.jpg)  
图3IPTG浓度对靛蓝产量的影响  
Fig.3The effect of different IPTG concentrations on indigo production

E.coli BL21 (DE3)-NS co-expressing GDH and P450BM3m；E.coli BL21 (DE3)-S co-expressing SpyTag-GDH and SpyCatcher-P450BM3m.

温度对细胞生长速率和蛋白折叠速率都有较大影响[2I]。将E.coli BL21(DE3)-S 和 E.coliBL21(DE3)-NS 分别在 $1 6 ^ { \circ } C \cdot 2 0 ^ { \circ } C \cdot 2 5 ^ { \circ } C$ 和 $3 0 \ \mathrm { ^ { \circ } C }$ 水平下诱导表达 $^ { 1 8 \mathrm { ~ h ~ } }$ 后加入终浓度为 $2 \mathrm { m m o l / L }$ 的吲哚和 $4 \mathrm { m m o l / L }$ 的葡萄糖进行反应，测定各细胞的靛蓝产量。如图4所示，在诱导温度为 $1 6 ~ \mathrm { { ^ \circ C } }$ 时，自组装多酶细胞和共表达未组装细胞的靛蓝产量均达到最大，且自组装体细胞与未组装体细胞的靛蓝产量相差最大，因此选取 $1 6 ~ \mathrm { ^ { \circ } C }$ 为最佳诱导温度。

![](images/36d1db1deb97958a330b4a5524ec9b29aa231e2d819b7625d2ac7f3171559523.jpg)  
图4诱导温度对靛蓝产量的影响

# Fig.4 The effect of different induction temperatures on indigo production

E.coli BL21 (DE3)-NS co-expressing GDHand P450BM3m; E.coli BL21 (DE3)-S co-expressing SpyTag-GDHanc SpyCatcher-P450BM3m.

在本实验中，吲哚、葡萄糖分别是P450BM3、GDH的底物，为了研究吲哚与葡萄糖的配比对靛蓝产量的影响,E.coli BL21(DE3)-S和E.coli BL21(DE3)-NS诱导培养 $1 8 \mathrm { h }$ 后，将吲哚和葡萄糖分别按照1:1、1:2、1:3、1:5 和1:10 的比例（吲哚浓度固定为2mmol/L)加入到培养液中进行反应,测定单位体积相同 $\mathrm { O D } _ { 6 0 0 }$ 的细胞靛蓝产量。如图5所示，吲哚与葡萄糖的不同配比对自组装多酶细胞靛蓝产量有较大影响，对未组装细胞几乎没有影响。当底物比例为1:2，即吲哚浓度$2 \ \mathrm { m m o l / L }$ 和葡萄糖浓度 $4 \mathrm { m m o l / L }$ 时，自组装多酶复合物细胞靛蓝产量达到$2 5 8 { \pm } 1 3 . 9 3 ~ \mathrm { m g / L }$ ，与未组装细胞的靛蓝产量相差最大，自组装细胞的靛蓝合成效率是未组装细胞的1.90倍。因此，吲哚与葡萄糖的最佳配比为1:2。

![](images/e631365811057e8d371ebf86403d4e8b0900ab4802827adb24f5c48a095a4a03.jpg)  
图5吲哚与葡萄糖比例对靛蓝产量的影响

Fig.5 The effect of different [indole concentration]:[glucose concentration] ratios on indigo production E.coliBL21 (DE3)-NSco-expressing GDHandP450BM3m；E.coliBL21 (DE3)-Sco-expressingSpyTag-GDHand SpyCatcher-P450BM3m.

# 2.4自组装辅酶再生循环系统效能分析

为了研究自组装辅酶再生循环系统对 $\mathrm { P } 4 5 0 \mathrm { B M } 3 \mathrm { m }$ 催化吲哚产生靛蓝的影响，将表达单酶 E.coli BL21 (DE3)-pET28a-P450BM3m，共表达未组装 E.coli BL21(DE3)-NS 和自组装多酶 E.coli BL21 (DE3)-S 的催化效率进行了对比分析。将这三种工程菌诱导培养 $1 8 \mathrm { h }$ 后，向培养液中加入 $2 \mathrm { m m o l / L }$ 吲哚和 $4 \mathrm { m m o l / L }$ 葡萄糖进行反应，检测各细胞单位体积相同 $\mathrm { O D } _ { 6 0 0 }$ 的靛蓝产量。图6a显示反应 $1 0 \mathrm { m i n }$ 时，自组装辅酶再生循环细胞已经有靛蓝产生，但是表达单酶的细胞和共表达未组装细胞没有明显的变化。图6b显示，加入终浓度相同的吲哚和葡萄糖进行反应，表达单酶的细菌吲哚转化率为 $9 . 4 0 \%$ ，表达双酶的E.coli BL21(DE3)-NS 和E.coli BL21(DE3)-S 转化率分别为 $12 . 9 1 \%$ 和 $2 2 . 5 6 \%$ ，且自组装多酶细胞展现出更高的催化效率，是表达P450BM3单酶细菌的2.4倍。结果表明，SpyTag 和SpyCatcher在胞内自组装后，葡萄糖脱氢酶驱动的NADPH辅酶再生循环体系能有效的提高P450BM3m的催化效率。

![](images/1b1444d1e7aa0ee54ceefd419b91c25b681beb9f75b782a3bb79f4b4ed4a5c9f.jpg)  
图6单酶细胞和辅酶再生细胞催化合成靛蓝反应的比较

Fig.6 Comparison of indigo-synthetized in single enzyme cels and coenzyme-regeneration cells.

(a) The solution states of indigo produced in different systems after reaction for $1 0 \mathrm { m i n }$ ；（b）The conversion ratio for indigo-synthetized reactionscatalyzedbyE.coliBL21(DE3)-pET28a-450BM3m(singleenzymecell、EcoliBL21(DE3)-NS（Non-asembled）andE.coli

BL21 (DE3)-S (assembled).

对自组装辅酶再生系统的催化进程进行研究，将E.coliBL21(DE3)-S诱导$1 8 \mathrm { h }$ 后，向培养液中加入 $2 \mathrm { m m o l / L }$ 吲哚和 $4 \mathrm { m m o l / L }$ 葡萄糖进行反应，测定 $9 0 \mathrm { m i n }$ 内吲哚的转化率。图7显示在反应 $1 0 \mathrm { m i n }$ 内，反应快速进行，达到 $24 \%$ 的转化率。反应 $7 0 \mathrm { m i n }$ 时，吲哚转化率达到了 $52 \%$ ，继续反应转化率增长非常缓慢。

![](images/7fdb450d566ab5129f48b192a9053507c59849be0e56d27cfd29d2ac5b0f086c.jpg)  
图7E.coliBL21(DE3)-S合成靛蓝的催化进程  
Fig.7 Catalytic process curve for indigo synthesis catalyzed by E.coli BL21 (DE3)-S

# 3结论

本研究中，通过SpyTag/SpyCatcher 体系，我们在大肠杆菌体内成功构建了自组装多酶复合物，实现了靛蓝分子生物合成。通过SDS-PAGE及纳米液相四级杆飞行时间质谱成分定性分析，证实 SpyCatcher-P450BM3m与SpyTag-GDH在大肠杆菌体内完成了自组装。在最优培养条件下，自组装细胞靛蓝产量达到$2 5 8 ~ \mathrm { m g / L }$ ，是共表达非组装细胞的1.9倍，且该自组装辅酶再生细胞还体现更优的催化效能，含 SpyTag/SpyCatcher 体系的自组装辅酶再生细胞的催化效率是单酶细胞的2.4倍。通过上述分析，本研究成功实现了SpyTag/SpyCatcher系统介导的多酶体系在大肠杆菌细胞中的自组装，且自组装形成的多酶复合物能有效增加酶促反应催化效率，为进一步研究利用 SpyTag/SpyCatcher作为自组装工具在生物催化反应中的应用奠定基础。

# 参考文献

[1] Hirakawa H, Haga T,Nagamune T.Artificial protein complexes for biocatalysis.Topics in Catalysis, 2012, 55(16-18):1124-1137.   
[2] Dueber JE,Wu GC,Malmirchegini GR,et al. Synthetic protein scaffolds provide modular control over metabolic flux. Nature biotechnology,2009, 27(8):753.   
[3] Conrado RJ, Wu GC, Boock JT, et al. DNA-guided assembly of biosynthetic pathways promotes improved catalytic efficiency.Nucleic acids research,2011, 40(4):1879-1889.   
[4] Zhao C, Gao X,Liu X,et al. Enhancing biosynthesis of a ginsenoside precursor by self-assembly of two key enzymesin Pichia pastoris. Journal of agricultural and food chemistry， 2016, 64(17):3380-3385.   
[5] Kang HJ, Coulibaly F, Clow F,et al. Stabilizing isopeptide bonds revealed in gram-positive bacterial pilus structure. Science,2007,318(5856):1625-1628.   
[6] Kang HJ, Baker EN. Intramolecular isopeptide bonds: protein crossinks built for stress? Trends in biochemical sciences,2011,36(4):229-237.   
[7] Chen AY, Deng Z, Billings AN, et al. Synthesis and patterning of tunable multiscale materials with engineered cells. Nature materials,2014, 13(5):515.   
[8] Brune KD, Leneghan DB, Brian IJ,et al. Plug-and-Display: decoration of Virus-Like Particles via isopeptide bonds for modular immunization. Scientific reports, 2016,6:19234.   
[9] Wang J, Wang Y, Wang X,et al. Enhanced thermal stability of lichenase from Bacillus subtilis 168 by SpyTag/SpyCatcher-mediated spontaneous cyclization. Biotechnology for biofuels,2016,9(1):79. [10] Veggiani G, Zakeri B,Howarth M. Superglue from bacteria: unbreakable bridges for protein nanotechnology. Trends in biotechnology,2014, 32(10):506-512.   
[11] Amelung S,Nerlich A，Rohde M,et al. The FbaB - type fibronectin - binding protein of Streptococcus pyogenes promotes specific invasion into endothelial cels. Cellular microbiology, 2011, 13(8):1200-1211.   
[12] Zakeri B,Fierer JO, Celik E,et al. Peptide tag forming a rapid covalent bond to a protein, through engineering a bacterial adhesin. Proceedings of the National Academy of Sciences，2012, 109(12):E690-E697.   
[13] Hagan RM, Bjornsson R, McMahon SA, et al. NMR spectroscopic and theoretical analysis of a spontaneously formed Lys-Asp isopeptide bond. Angewandte Chemie, 2010,122(45):8599-8603. [14] Li QS,Schwaneberg U,Fischer P, et al. Directed Evolution of the Fatty - Acid Hydroxylase P450 BM-3into an Indole - Hydroxylating Catalyst. Chemistry-A European Journal， 2000, 6(9):1531-1536. [15] Lundemo MT, Woodley JM. Guidelines for development and implementation of biocatalytic P450 processes.Applied microbiology and biotechnology,2015, 99(6):2465-2483.   
[16] Beyer N,Kulig JK,Bartsch A，et al. P45O BM3 fused to phosphite dehydrogenase allows phosphite-drivenselectiveoxidations.Appliedmicrobiologyandbiotechnology， 2017, 101(6):2319-2331.   
[17] Rocha -Martin J，Rivas Bdl， Munoz R，et al. Rational co - immobilization of bi- enzyme cascades on porous supports and their applications in bio - redox reactions with in situ recycling of soluble cofactors. ChemCatChem,2012, 4(9):1279-1288.   
[18] Omura T,Sato R. The carbon monoxide-binding pigment of liver microsomes I. Evidence for its hemoprotein nature. Journal of Biological Chemistry,1964, 239(7):2370-2378.   
[19] Lu Y,Mei L. Co-expresson of P450 BM3 and glucose dehydrogenase by recombinant Escherichia coli and its application in an NADPH-dependent indigo production system.Journal of industrial microbiology & biotechnology,2007,34(3):247-253.   
[20] Riesenberg D, Guthke R. High-cell-density cultivation of microorganisms. Applied microbiology and biotechnology, 1999,51(4):422-430.   
[21] Ma X, Su E, Zhu Y, et al. High-level expression of glutaryl-7-aminocephalosporanic acid acylase from Pseudomonas diminuta NK703 in Escherichia coli by combined optimization strategies. Journal of biotechnology,2013, 168(4):607-615.