# 质谱方法实现抗体类药物糖链修饰的鉴定与定量研究

# ldentification and Quantitative Study on glycosylation Chain Modification of Antibody Drugs by Mass Spectrometry

黄怡’²，李晓宇²，田芳²，钱小红²，应万涛1.2二

(1 安徽医科大学 安徽 合肥 230032)

(2 蛋白质组学国家重点实验室北京蛋白质组学研究中心 国家蛋白质科学中心军事医学科学院放射与辐射医学研究所 北京102206)

摘 要：目的：基于液质联用的串联质谱技术，建立基于完整糖肽水平的抗体药糖型定性定量分析方法，并用于生物仿制药糖型研究。方法：基于液相色谱质谱技术，从完整糖肽水平对糖型进行定性定量分析，同时与传统超高效液相荧光检测（UItra Performance LiquidChromatography_Fluorescence detection，UPLC-FLR）结果比较，获得最优分析策略，并用于曲妥珠单抗仿制药批次间糖型定性定量分析。结果：UPLC-FLR方法定量分析了贝伐单抗7种糖型；液质联用方法定量19种糖型；经亲水相互作用色谱（Hydrophilic interactionchromatography，HILIC）富集后，定量22种糖型。曲妥珠单抗仿制药批次间糖型定量结果显示良好的一致性。结论：基于液质联用的方法，具有速度快、灵敏度高、检测糖型种类多等优势，有望作为一种稳定的抗体药物糖蛋白位点特异性定量分析策略。

关键词：超高效液相荧光检测、液质联用、抗体药物、完整糖肽定量中图分类号：Q816

Huang Yi1²，Li Xiao-yu²，Tian Fang²，Qian Xiaohong²，Ying Wan-tao1,2\* （1 Anhui Medical University，Hefei230032，China) (2 State Key Laboratory of Proteomics，Beijing Proteome Research Center，National Center for Protein Science, Beijing Institute of Radiation Medicine， Beijingl02206，China)

Abstract Objective: To establish a qualitative and quantitative method for the determination of antibody glycosylation from the level of intact glycopeptides based on LC/MS,and to apply it to qualitative and quantitative analysis of biomimetic drugs. Methods: The qualitative and quantitative analysis of glycoforms was carried out from the level of intact glycopeptides, and compared with the results from UPLC-FLR, the traditional glycan analysis approach. The optimal analysis strategy was established and used for the analysis of N-glycans on antibody biosimilars. Result: The UPLC-FLR methods obtained the quantitative result of seven glycoforms from bevacizumab; While the method of mass spectrometry quantified 19 glycoforms. After enrichment by hydrophilic interaction chromatography (HILIC)，22 glycan forms were quantified. The quantitative results of the glycosylation mass of the trastuzumab showed good agreement. Conclusion:Based on the method of LC / MS,it has the advantages of fast speed, high sensitivity and high detection of glycoforms,and it is expected to be a stable quantitative strategy for site - specific glycosylation analysis of biopharmaceuticals.

Key words UPLC-FLR； LC/MS； Antibody drugs；Intact glycopeptides quantification

# 1引言

近年来，生物医药产业在全球医药市场份额中所占的比重越来越大，从2006年占比仅 $1 4 \%$ 上升到2013年占比 $2 3 \%$ ，预计到2020年占比将超过 $1 / 4$ ，真正迎来生物技术药物蓬勃发展的时代。生物技术药物，例如单克隆抗体、融合蛋白、生长因子、酶和激素等。这些药物的出现为心血管疾病、自身免疫性疾病，尤其是癌症等重大疾病的治疗提供了更多的可能。

糖基化修饰是最复杂的翻译后修饰类型之一，生物技术药物大多含有不同比例的糖链组成，大量的研究报道表明：蛋白质糖基化修饰多方面影响着糖蛋白药物，包括其稳定性、体内清除率、免疫原性、抗体依赖细胞毒性、补体依赖细胞毒性等，从而影响着药物的临床疗效[2。N-糖基化修饰的一致性是确保生物技术药物治疗有效性和安全性的关键因素，而获得一致的N-糖基化修饰对于生物制药行业来说是巨大的工艺挑战。因此，对于不同批次之间生物技术药物N-糖基化修饰的检测是至关重要的。为此，美国食品药品管理局（U.S．Foodand DrugAdministration，FDA）和欧洲药品管理局（European Medicines Agency，EMA）也明确规定对于生物技术药物要进行全面分析表征，向监管机构提交的药学研究材料中也要包含蛋白药物的氨基酸序列、二硫键、翻译后修饰（Post-translational modifications，PTMs）等尽可能反映该药物理化性质的信息[3。因此，糖修饰的结构鉴定与定量分析，在糖蛋白药物质量属性研究中，越来越受到关注。

目前，超高效液相荧光检测（UPLC-FLR）联合荧光标记（如：2-氨基苯甲酰胺（Anthranilamide，2-AB）、2-邻氧基苯甲酸（2-Ethoxybenzoic acid，2-AA）等）检测糖蛋白药物寡糖是生物制药行业糖基化修饰研究的“金标准”[4]。该方法是用肽糖苷F酶将糖蛋白上的N-聚糖进行释放，并用2-AB等荧光试剂标记聚糖还原末端，衍生化后的聚糖在UPLC-FLR中产生荧光检测信号。该方法具有良好的稳定性，被生物制药行业广泛应用于抗体药物的糖型鉴定与定量分析[5]。但是该方法周期长、灵敏度和分辨率都不高，且存在不完全标记，导致各个实验室得到的结果差异也比较大[6。贝伐单抗是一种人源化重组单克隆抗体，是美国第一个批准上市的抑制肿瘤血管生成的抗体药物，被FDA批准用于治疗转移性结肠癌等[。在本研究中，我们以贝伐单抗为测试品，从糖肽水平出发，优化建立糖肽高灵敏度、全覆盖的定性定量分析技术流程，并同时重复了荧光标记鉴定和定量N-聚糖的方法。结果显示，糖肽的质谱分析方法在单克隆抗体糖修饰结构分析中明显优于荧光检测的结果。运用以上建立的完整糖肽分析方法，我们对三个批次的曲妥珠单抗仿制药进行了糖型的定性与定量分析。

# 2材料与方法

# 2.1材料

2.1.1试剂

贝伐单抗（罗氏，批号H0139B06)，三批次曲妥珠单抗来自合作研究公司，尿素（Urea),Tris-Hcl，二硫苏糖醇（DTT)，碘乙酰胺（IAA)，碳酸氢铵（NH4HC03），氯化钠（NaCl)，三氟乙酸（TFA），甲酸（FA），HPLC 级乙腈，冰醋酸，DMSO，2-AB 荧光标记试剂，氰基硼氢化钠，甲酸铵，肽糖苷F酶（300U）等均购于Sigma-Aldrich 公司；HILIC 填料购于天津博纳艾杰尔公司；超纯水；测序级胰蛋白酶购于Promega 公司， $3 0 \mathrm { { k D } }$ 超滤管购于Millipore公司；C8 膜购于3M公司，Dextran Ladder 购于Waters 公司。

# 2.1.2仪器

$\mathsf { Q }$ -Exactive HF 质谱仪，Easy-nano LC 1200 液相系统均为 Thermo Fisher公司，DNA 混悬仪（宁波新芝），色谱柱（ACQUITY UPLC BEHGlycan Column 2.1$\times 1 5 0 \mathrm { m m }$ ， $1 . 7 \mu \mathrm { m } \dot { }$ ，ACQUITYUPLCH-Class液相系统均为Waters公司。

# 2.2方法

# 2.2.1FASP蛋白酶解

等量取3份贝伐单抗或3批次曲妥珠仿制药蛋白质（各 $1 0 0 \mu \mathrm { ~ g ~ } )$ ，加入变性剂8MUA（8M尿素溶于0.1M的Tris-Hcl，pH8.5）补齐至 $5 0 0 ~ \mu \mathrm { ~ 1 ~ }$ ，全部转移至$3 0 \mathrm { k D }$ 超滤管， $1 4 0 0 0 \mathrm { g }$ ，离心20min，以替换样品贮存液。加入 $1 0 0 \mu \mathrm { ~ l ~ }$ DTT（浓度 $2 0 \mathrm { m M }$ ，溶于8MUA）， $3 7 ^ { \circ }$ 恒温培养箱孵育4h。取出， $1 4 0 0 0 \mathrm { g }$ ，离心15min后，加入 $1 0 0 \mu \mathrm { ~ l ~ }$ IAA（浓度 $5 0 \mathrm { m M }$ ，溶于8MUA)，暗处反应30min。 $1 4 0 0 0 \mathrm { g }$ ，离心15min,再次加入 $1 0 0 \mu \mathrm { ~ l ~ }$ DTT（浓度 $2 0 \mathrm { m M }$ ，溶于8MUA)，暗处反应15min，以中和多余的IAA。 $1 4 0 0 0 \mathrm { g }$ ，离心15min，加入 $2 0 0 \mu \mathrm { ~ l ~ }$ ABC（终浓度 $5 0 \mathrm { m M \ N H { 4 H C O 3 } }$ ，溶于纯水，pH8.0）清洗， $1 4 0 0 0 \mathrm { g }$ ，离心15min，并重复此步骤一次。更换新套管，按照酶：蛋白 $\mathbf { \zeta } = 1 : 5 0$ ，每管加入 $2 \mu \ g$ 胰蛋白酶，加入终浓度1mM的 $\mathrm { { N a C l } }$ ，放入 $3 7 ^ { \circ }$ 恒温培养箱反应过夜 $\mathrm { ( > 1 2 h ) }$ 。取出， $1 4 0 0 0 \mathrm { g }$ ，离心15min，回收液体，依次加入 $2 0 0 \mu \mathrm { ~ l ~ }$ ABC 和超纯水， $1 4 0 0 0 \mathrm { g }$ ，离心15min，回收液体并合并，放入真空浓

缩蒸发仪热干，放入 $\cdot ^ { - 8 0 ^ { \circ } }$ 冻存待用。

# 2.2.2蛋白聚糖的释放

等量取3份贝伐单抗样品 $4 \mu \updownarrow$ （ $1 0 0 ~ \mu \mathrm { ~ g ~ } )$ ，步骤同FASP蛋白酶解方法，按照酶：蛋白 $^ { = 1 }$ ：20，每管加入5UPNGaseF酶，加入终浓度 $0 . 1 \%$ 的RapiGest,以促进酶切反应，稳定酶切反应体系，放入 $3 7 ^ { \circ }$ 恒温培养箱反应过夜（ $\mathrm { > } 1 2 \mathrm { h } )$ 。取出， $1 4 0 0 0 \mathrm { g }$ ，离心15min，回收液体，依次加入 $2 0 0 \mu \mathrm { ~ l ~ }$ ABC 和超纯水， $1 4 0 0 0 \mathrm { g }$ 离心15min，回收液体并合并，放入真空浓缩蒸发仪热干，放入 $- 8 0 ^ { \circ }$ 冻存待用。

# 2.2.3糖肽或聚糖富集

称取5mgHILIC 填料于离心管，加入适量体积 $0 . 1 \% \mathrm { T F A }$ ，放置于DNA 混悬仪上慢速摇动15min后取下离心管，在掌上离心机上短暂离心，用移液枪吸除上层液体（避免吸入下层HILIC 填料)，再加入BBH（80：20： $0 . 2 \mathrm { = }$ 乙腈：双蒸水：TFA)，放置于DNA 混悬仪上慢摇15min，并重复此步骤3次；将用BBH复溶的酶切样品用移液枪转移至含有填料的离心管中，放置于DNA混悬仪上慢速摇动 2h，让填料与样品充分结合；将悬浮有HILIC填料的混合液利用移液枪加入到填有C8 筛板的枪头中，利用注射器将上层溶液打下，从而使糖肽保留在HILIC 小柱上；加入BBH的溶液清洗HILIC上非特异性吸附的非极性肽段，重复2次；再用80 $\mathrm { ~ \textmu ~ 1 ~ } ~ 0 . ~ 1 \% \mathrm { T F A }$ 洗脱糖肽2次，合并热干，于 $- 8 0 ^ { \circ } \mathrm { C }$ 冻存待用。

# 2.2.4蛋白聚糖的2-AB荧光标记

称取 $5 \mathrm { m g \ 2 - A B }$ 标记试剂，另称取6mg 氰基硼氢化钠（还原剂)，用移液枪量取 $1 5 0 \mu \mathrm { ~ l ~ }$ 冰醋酸加入 $3 5 0 \mu \mathrm { ~ l ~ } \mathrm { D M S } 0$ ，震荡以充分混合。取出 $1 0 0 \mu \mathrm { ~ l ~ }$ 冰醋酸/DMSO混合溶液加入称取好的2-AB标记试剂中，混合涡旋，使其充分溶解，再将该混合溶液全部转移至称取好的氰基硼氢化钠中，混合至完全溶解。取富集后的热干样本，每个样本加入 $2 0 \mu \mathrm { ~ l ~ }$ 配制好的标记试剂，混合涡旋，使样本充分溶解；封口膜封口， $6 5 ^ { \circ } \mathrm { C }$ 金属浴孵育样本3h，全程避光。孵育完成后将样本进行HILIC富集，步骤同糖肽富集方法。

# 2.2.5糖肽质谱检测

取酶解样本，溶解于A液 $\mathrm { 9 9 . 9 \mathrm { 9 \mathrm { \Omega } 9 0 H 2 0 / 0 . 1 \mathrm { \Omega } _ { 0 } ^ { \mathrm { 0 } } F A ) } }$ ， $1 4 0 0 0 \mathrm { g }$ 离心10min，取上清通过 Easy nano-LC 1200 结合 $\mathsf { Q }$ -ExactiveHF质谱仪进行分析。色谱条件：色谱柱：ReproSil-PurC18-AQ，填料粒径： $1 . 9 \mathrm { u m }$ ；毛细管柱内径： $1 5 0 \mathrm { u m }$ ，长度：$1 2 \mathrm { c m }$ 。流动相：A： $9 9 . 9 \%$ $\mathrm { H 2 0 + 0 . 1 \% F A }$ ；B： $8 0 \% \mathrm { A C N } { + } 1 9 . 9 \%$ $\mathrm { H 2 0 ~ + ~ 0 . ~ 1 \% F A }$ 。流速： $6 0 0 \mathrm { n l / m i n }$ ；洗脱条件：0-5min， $5 \% - 1 2 \% \mathrm { B }$ ； $5 \mathrm { - } 3 4 \mathrm { { m i n } }$ ， $1 2 \mathrm { - } 2 4 \% B$ ； 34-41min,$2 4 \mathrm { - } 4 2 \% \mathrm { B }$ ；41-42min, $4 2 \mathrm { - } 9 5 \% \mathrm { B }$ ： $9 5 \% \mathrm { B }$ 维持4min。质谱条件：数据采集时间：75min，喷雾电压（sprayvoltage）：1.95KV；离子传输管温度： $3 2 0 ^ { \circ } \mathrm { C }$ ；碰撞能量：32;采集质量范围： $3 0 0 { - } 2 0 0 0 \mathrm { { D a } }$ ；采集数据依赖的正离子模式，在全扫描中选择 20个信号最强的离子进行串联质谱分析，动态排除时间12s；质谱数据以raw文件保存。

# 2.2.6聚糖UPLC荧光检测

配制流动相A： $5 0 \mathrm { m M }$ 甲酸铵溶液， $\mathrm { P H } { = } 4 . 4$ 和LC-MS级水；流动相B： $1 0 0 \%$ 乙腈，色谱柱为：ACQUITY UPLC BEH Glycan Column $2 . 1 \times 1 5 0 \mathrm { m m }$ ，1.7um设置柱温： $4 0 . 0 \mathrm { { ^ \circ C } }$ ；样品温度： $1 0 . 0 \mathrm { { ^ { \circ } C } }$ ，最大耐受压力范围（psi）： $0 \sim 1 5 0 0 0$ ；FLR波长： $\mathrm { E X 3 3 0 / E M 4 2 0 n m }$ ；FLR采样速率： $\boldsymbol { 1 0 \mathrm { H z } }$ ；用乙腈和双蒸水（乙腈：水 $\scriptstyle \mathtt { . - 6 0 }$ ：40）混合溶液 $1 0 \mu \mathrm { ~ l ~ }$ 溶解热干样本，上样 $5 \mu \updownarrow$ 。洗脱梯度为：0-2.06min， $7 0 \% \mathrm { B }$ ，流速 $0 . 4 \mathrm { { m } 1 / \mathrm { { m i n } } }$ ； $2 . 0 6 \mathrm { - } 3 4 . 8 \mathrm { { m i n } }$ ， $7 0 \% - 5 3 \% \mathrm { B }$ ，流速 $0 . 4 \mathrm { { m } 1 / \mathrm { { m i n } } }$ ； 34.8-36min,$5 3 \% \mathrm { - 2 0 \% B }$ ，流速 $0 . 2 5 \mathrm { m l / m i n }$ ； $3 6 { - } 3 9 \mathrm { { m i n } }$ ， $2 0 \% B$ ，流速 $0 . 2 5 \mathrm { m l / m i n }$ ；39-40min,$2 0 \% \mathrm { - } 7 0 \% B$ ，流速 $0 . 4 \mathrm { { m } 1 / \mathrm { { m i n } } }$ ；40-45min， $7 0 \% B$ ，流速 $0 . 4 \mathrm { { m } 1 / \mathrm { { m i n } } }$ 。

# 3结果与讨论

# 3.1实验设计方案

在本次实验中，我们首先重复了抗体糖型UPLC荧光检测的方法。另一方面，将样品进行胰蛋白酶（Trypsin）酶解，直接进入质谱检测，或者将酶解肽段经HILIC 富集后进入质谱检测，进行数据处理后，从完整糖肽水平，对贝伐单抗进行糖型的鉴定与定量（图1)。通过实验线路图可以看到：（1）将样品直接酶切成肽段送入质谱检测所需样本初始量及上样量均低于UPLC荧光检测的方法；（2）UPLC 荧光检测的方法用时明显较长；（3）UPLC荧光检测的方法前处理步骤多，极端的标记环境可能造成样品修饰不完全，从而影响实验结果。

![](images/b00b57b5358b87af981873e90d1f9e3a54ed2f5597fd65a0ef470623cacacbca.jpg)  
图1、实验线路图

Figl.Experimental design

# 3.2糖型鉴定及其定量结果

利用UPLC荧光检测方法鉴定到的贝伐单抗的糖型及定量结果（图2、4)，与网络公布的贝伐单抗药物总结验证报告=和Waters公司验证UPLC方法"所检测到的糖型定量结果一致。针对串联质谱分析结果，我们对鉴定到的每种糖型提取二级图谱进行手工解析（图3)；通过将贝伐单抗经Trypsin酶解后直接进行质谱检测和经过HILIC富集之后的糖肽进行质谱检测，所鉴定的N-聚糖定量分布图可以看到（图5、6)，糖肽水平上可鉴定到的糖型明显多于UPLC-FLR法，可以实现低丰度糖型的定量，并检测到含唾液酸的糖型；而经过HILIC 富集之后鉴定到的糖型结果较富集前更为丰富，可以鉴定到更多低丰度的糖型，并实现定量分析。说明亲水富集提高了N-聚糖的检测效率。在完整糖肽水平鉴定到的糖型要多于糖链水平，且亲水富集对于更多低丰度糖型的检测是有很大助益的（图7)。比较三种方法鉴定到的具体糖型及其定量结果（表1)，可以看到，HN4H3F1、HN4H4F1为贝伐单抗最主要的两种糖型，在所有糖型所占比例中高达 $9 0 \%$ 以上。

![](images/219b35f5881676d8fd99210fb7e19a1a0bf765544cbd7f8683eed880ae76626d.jpg)  
图2、贝伐单抗N-聚糖荧光标记色谱图

Fig2. Chromatograms of N-glycans from Bevacizumab after fluorescent labeling

![](images/f5f1664d7c6cb553be5ca75f275f156f6e5b2399c5e2307f49aad3d17c194574.jpg)  
图3、贝伐单抗N-糖肽HN4H3F1_EEQYNSTYR二级谱图解析

Fig3.MS/MS spectrum of glycopeptide HN4H3F1_EEQYNSTYR from Bevacizumab

![](images/e480eeaf99506c8c2caeb914a557dac65ee4c2bbaf7ffa592ee486990ae608e1.jpg)  
图4、UPLC-FLR糖型定量结果

Fig 4.Quantitative result of glycoforms from UPLC-FLR analysis

![](images/8ff0eb7d9f082a97b270ba605c48894b2d74b8f7f6e008e5fdb2954480703093.jpg)  
Fig5. Quantitative results of glycoforms after trypsin digestion

![](images/c66cdcf0e400d1d7bae95d725a3c2178dc74867c01d6fd9f1358822f3bb0c431.jpg)  
图5、Trypsin酶切后糖型定量结果  
图6、HILIC富集后糖型定量结果

Fig 6.Quantitative res μlts of glycoforms after HILIC enrichment

![](images/d5d0f65d934cdbbfad1cb00e14658407a693f7401955b2dae19c2d593031c2bc.jpg)  
图7、三种方法糖型鉴定结果相关性分析  
Figure 7. Correlative Analysis of three methods for glycoforms identification results

表1、三种方法糖型定量结果比较  
Table 1. Comparison of three methods for the quantitatiion of glycans   

<html><body><table><tr><td>糖型</td><td>UPLC-FLR（%) (x±s)</td><td>Trypsin(%) (x±s)</td><td>HILIC(%) (x±s)</td></tr><tr><td>HN( 4H2 5F(31</td><td>0.47±0.243</td><td>0.69±0.152</td><td>1.01±0.035</td></tr><tr><td>HN4H4F1</td><td>29.63±0.091</td><td>10.30±0.027</td><td>15.47±0.016</td></tr><tr><td>HN4H3F1</td><td>63.92±0.018</td><td>75.76±0.068</td><td>75.79±0.018</td></tr><tr><td>HN4H3</td><td>3.75±1.020</td><td>2.47±0.013</td><td>1.42±0.003</td></tr><tr><td>HN3H3F1</td><td>0.46±1.25</td><td>5.66±0.761</td><td>3.60±0.411</td></tr><tr><td>HN3H3</td><td>0.19±0.032</td><td>0.49±0.004</td><td>0.086±0.000</td></tr><tr><td>HN2H5</td><td>1.58±0.013</td><td>0.64±0.081</td><td>0.27±0.014</td></tr><tr><td>HN5H4F1</td><td></td><td>0.08±0.002</td><td>0.09±0.004</td></tr><tr><td>HN5H4</td><td></td><td>0.02±0.040</td><td>0.04±0.001</td></tr><tr><td>HN5H3</td><td></td><td>0.14±0.003</td><td>0.17±0.008</td></tr><tr><td>HN4H5F1SA1</td><td></td><td>0.04±0.011</td><td>0.11±0.001</td></tr><tr><td>HN4H4F1SA1</td><td></td><td>0.06±0.000</td><td>0.14±0.003</td></tr><tr><td>HN4H4</td><td></td><td>0.38±0.013</td><td>0.60±0.461</td></tr><tr><td>HN3H6F1SA1</td><td></td><td>0.01±0.001</td><td>0.02±0.001</td></tr><tr><td>HN3H6F1</td><td></td><td>0.02±0.002</td><td>0.03±0.002</td></tr><tr><td>HN3H4F1</td><td></td><td>0.50±0.194</td><td>0.59±0.045</td></tr><tr><td>HN5H3F1</td><td></td><td></td><td>0.33±0.010</td></tr><tr><td>HN4H5F2</td><td></td><td></td><td>0.01±0.006</td></tr><tr><td>HN4H5</td><td></td><td></td><td>0.11±0.012</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">HN3H4 0.03±0.009</td></tr><tr><td colspan="2">HN2H8 0.05±0.034</td></tr><tr><td colspan="2">HN2H6 0.04±0.100</td></tr><tr><td>HN3H4F1SA1 0.04±0.003</td><td></td></tr><tr><td>HN2H4</td><td>0.02±0.002</td></tr><tr><td>HN2H3 0.02±0.010</td><td></td></tr></table></body></html>

注释：(1)HN=HexNAc；(2)H=Hex；(3)F=Fuc；(4) SA=NeuAc.

# 3.3实验方法的重现性比较

实验方法良好的重现性是保证定量结果可靠性的前提。所以，我们对三种实验方法分别进行了三次平行实验，并对结果进行分析（表2)。三种方法三次平行实验主要糖型的定量结果CV值都 $\textless 1 0 \%$ ，说明定量结果真实可靠，三种方法都具有良好的重现性。

# 表2、三种方法平行实验RSD值比较

Table 2. Comparison of three methods of parallel experimental RSD values   

<html><body><table><tr><td rowspan="3">糖型</td><td colspan="2">UPLC-FLR</td><td colspan="2">Trypsin</td><td colspan="2">HILIC</td></tr><tr><td>x±s</td><td>RSD%</td><td>x±s</td><td>RSD%</td><td>x±s</td><td>RSD%</td></tr><tr><td>HN(4H(2 5F(1</td><td>0.47±0.02</td><td>3.9</td><td>0.69±0.07</td><td>9.89</td><td>1.01±0.02</td><td>1.79</td></tr><tr><td>HN2H5</td><td>1.58±0.09</td><td>5.78</td><td>0.64±0.03</td><td>4.25</td><td>0.27±0.02</td><td>5.95</td></tr><tr><td>HN4H4F1</td><td>29.7±1.02</td><td>3.44</td><td>10.30±0.76</td><td>7.39</td><td>15.47±0.41</td><td>2.66</td></tr><tr><td>HN3H3</td><td>0.18±0.01</td><td>7.41</td><td>0.49±0.01</td><td>2.71</td><td>0.09±0.003</td><td>3.81</td></tr><tr><td>HN4H3</td><td>3.75±0.24</td><td>6.47</td><td>2.47±0.15</td><td>6.14</td><td>1.42±0.03</td><td>2.43</td></tr><tr><td>HN4H3F1</td><td>63.9±1.25</td><td>1.96</td><td>75.76±1.08</td><td>1.43</td><td>75.80±0.46</td><td>0.61</td></tr><tr><td>HN3H3F1</td><td>0.46±0.03</td><td>7.07</td><td>5.66±0.19</td><td>3.43</td><td>3.6±0.05</td><td>1.26</td></tr></table></body></html>

注释：（1）HN=HexNAc；(2）H=Hex；（3）F=Fuc

# 3.4三个批次曲妥珠单抗仿制药糖型的鉴定与定量结果

运用液质联用的方法对三个批次的曲妥珠单抗仿制药糖型的定性及定量结果进行比较分析（表3)，可以看到直接酶切进入LC-MS检测三个批次均鉴定到16 种糖型，而HILIC富集之后，三个批次鉴定到的糖型鉴定到21种糖型。且从表格中我们可以看到：富集之后能够鉴定到更多低丰度的糖型，尤其是含唾液酸的糖型。而此次鉴定到的主要糖型与之前文献中报道的曲妥珠单抗原研药的主要糖型是一致的8。从定量结果来看：HN4H3F1是曲妥珠单抗的最主要糖型，三个批次定量结果都在 $7 5 \%$ 以上，批次间的 $\mathrm { R S D \% }$ 值 $ 1 0 \%$ ；也有少数低丰度的糖型定量差异较大，猜测与样品前处理操作或者仿制药生产工艺有关。

# 表3、三个批次间曲妥珠单抗仿制药糖型定量结果比较

Table 3.Comparison of the quantitative results of the mixture of trastuzumab monoclonal antibody between three batches   

<html><body><table><tr><td>Glycoform</td><td>HILIC</td><td>Trypsin</td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td></td><td>B006</td><td>B007</td><td>B008</td><td>B006</td><td>B007</td><td>B008</td></tr><tr><td>HN 4H 5F31</td><td>0.35</td><td>0.34</td><td>0.36</td><td>0.35</td><td>0.35</td><td>0.62</td></tr><tr><td>HN3H4F1</td><td>0.43</td><td>0.46</td><td>0.41</td><td>0.39</td><td>0.39</td><td>0.42</td></tr><tr><td>HN2H5</td><td>3.48</td><td>3.83</td><td>3.84</td><td>4.70</td><td>4.70</td><td>5.67</td></tr><tr><td>HN4H4F1</td><td>7.20</td><td>6.76</td><td>7.30</td><td>6.55</td><td>6.56</td><td>8.81</td></tr><tr><td>HN2H6</td><td>0.22</td><td>0.24</td><td>0.23</td><td>0.21</td><td>0.21</td><td>0.24</td></tr><tr><td>HN2H4</td><td>0.10</td><td>0.12</td><td>0.08</td><td>0.11</td><td>0.11</td><td>0.12</td></tr><tr><td>HN3H3</td><td>0.11</td><td>0.20</td><td>0.06</td><td>0.14</td><td>0.14</td><td>0.17</td></tr><tr><td>HN4H3</td><td>0.19</td><td>0.27</td><td>0.15</td><td>0.11</td><td>0.11</td><td>0.14</td></tr><tr><td>HN4H3F1</td><td>80.00</td><td>76.53</td><td>80.54</td><td>79.43</td><td>79.40</td><td>76.28</td></tr><tr><td>HN2H7</td><td>0.07</td><td>0.08</td><td>0.06</td><td>0.11</td><td>0.11</td><td>0.08</td></tr><tr><td>HN2H3</td><td>0.02</td><td>0.02</td><td>0.01</td><td>0.04</td><td>0.04</td><td>0.03</td></tr><tr><td>HN2H8</td><td>0.04</td><td>0.03</td><td>0.04</td><td>0.05</td><td>0.05</td><td>0.05</td></tr><tr><td>HN3H3F1</td><td>6.48</td><td>7.05</td><td>5.99</td><td>7.45</td><td>7. 47</td><td>6.94</td></tr><tr><td>HN5H3F1</td><td>0.42</td><td>0.38</td><td>0.38</td><td>0.22</td><td>0.22</td><td>0.24</td></tr><tr><td>HN3H5F1</td><td>0.04</td><td>0.04</td><td>0.03</td><td>0.05</td><td>0.05</td><td>0.05</td></tr><tr><td>HN5H4F1</td><td>0.08</td><td>0.07</td><td>0.07</td><td>0.08</td><td>0.08</td><td>0.12</td></tr><tr><td>HN4H4F1SA（1</td><td>0.20</td><td>0.13</td><td>0.12</td><td></td><td></td><td></td></tr><tr><td>HN4H5F1SA1</td><td>0.09</td><td>0.06</td><td>0.05</td><td></td><td></td><td></td></tr><tr><td>HN3H4F1SA1</td><td>0.11</td><td>0.08</td><td>0.06</td><td></td><td></td><td></td></tr><tr><td>HN4H4</td><td>0.28</td><td>3.26</td><td>0.15</td><td></td><td></td><td></td></tr><tr><td>HN5H3</td><td>0.09</td><td>0.05</td><td>0.05</td><td></td><td></td><td></td></tr></table></body></html>

注释：(1)HN=HexNAc；(2)H=Hex；(3)F=Fuc；(4) SA=NeuAc.

# 4结论

由上述结果，我们比较了不同方法，用于贝伐单抗糖链的定量分析。基于蛋白酶消化和LC-MS分析，我们检测并定量了贝伐单抗19 种糖型，曲妥珠单抗仿制药16 种糖型；而经亲水富集后，我们检测到了贝伐单抗22种糖型，曲妥珠单抗仿制药21种糖型，说明亲水富集对于糖型的鉴定有很大助益。HILIC富集原理是水-水溶性有机溶剂混合物为流动相，亲水作用材料表面吸附水分子形成富水层，分析物中的亲水成分会浓缩在所形成的富水层中，疏水成分留在高含量有机溶剂的流动相中。由于糖肽相对非糖肽具有更强亲水性，使其更易保留在亲水材料上，从而达到富集目的，且不会对糖链结构造成破坏。经HILIC富集去除了非糖肽的干扰，更有利于低丰度糖型的检测。本次实验利用建立的LC-MS分析方法，比较了不同批次曲妥珠单抗仿制药N-糖基化修饰的一致性，从而用于评价生产工艺的稳定性。该方法快速简便、稳定高效，经济实惠、重现性好，适用于市场上各种抗体药物糖基化修饰的检测。相较于传统的UPLC-FLR检测方法，不仅能够对高丰度糖型进行更加准确的定性、定量；并且能够鉴定到更多低丰度糖型。

本次实验使用的贝伐单抗样品为药用级，符合药典对于生物技术类药物的质量标准要求，纯度很高；另外，贝伐单抗为单克隆抗体，只含有一个糖基化修饰肽段（EEQYNSTYR)，在1min内完全出峰，可以判定所得糖型结果不是由其他杂质或污染物产生的，如杨芃原[实验室在最近发表的文章中也指出同一个完整糖肽上所有糖型出峰时间基本是一致的。本研究所建立的方法不需要标准品作为参照，实验周期短，步骤简单，可以直接对糖蛋白样品进行定性、定量分析。但是需要提示的一点是UPLC荧光检测方法可以将糖型的同分异构体区分开来，例如 Hex(4)HexNAc(4)Fuc(1)，其外围半乳糖可能连接在双天线糖的1，3或1，6天线上，利用其同分异构体在超高效液相上的保留时间不同，从而对其进行分别定量。但是从糖肽水平进行质谱鉴定的方法尚不可做到这点，这也是该方法需要进一步改进的关键。

参考文献

[1]翁锦玉.国际生物医药产业发展趋势分析[J].科技与创新，2017(1)：1-2.doi：10.15913/j.cnki.kjycx.2017.01.001Weng JY. Analysis of international biomedical industry development trend [J]. Science andTechnology & Innovation，2017(1): 1-2.  
[2]刘艳玲，刘晓志，赵伟，等.糖蛋白药物的多糖结构解析进展[J].生物技术进展，2016,6(4)：244-248. doi: 10.3969/j.issn.2095-2341.2016.04.04Liu YL， et al. Progress on Glycan Analysis of Therapeutic Glycoprotein [J]. CURRENTBIOTECHNOLOGY，2016，6(4): 244-248.  
[3]Yang X， Kim S M， Ruzanski R， et al. Mltrafast and high-throughput N-glycan analysis formonoclonal antibodies[C].MAbs.Taylor & Francis，2016，8(4): 706-717.  
[4]Reusch D，Haberger M，Maier B， et al. Comparison of methods for the analysis oftherapeutic immunoglobulin G Fc-glycosylation profiles—part 1 : Separation-basedmethods[C].MAbs. Taylor & Francis，2015，7(1): 167-179.  
[5]Yang N， Goonatilleke E， Park D， et al. Quantitation of Site-Specific Glycosylation inManufactured Recombinant Monoclonal Antibody Drugs [J]. Analytical Chemistry， 2016,88(14): 7091-7100.  
[6]Planinc A，Dejaegher B，Vander Heyden Y，et al. Batch-to-batch N-glycosylation study ofinfliximab， trastuzumab and bevacizumab，and stability study of bevacizumab[J]. Eur JHospPharm，2016: ejhpharm-2016-001022.  
[7]Sanchez-De Melo I, Grassi P, Ochoa F，et al. N-glycosylation profile analysis of Trastuzumabbiosimilar candidates by Normal Phase Liquid Chromatography and MALDI-TOF MSapproaches [J]. Journal of proteomics，2015，127: 225-233.  
[8]任跃明．国内外生物技术类制品质量标准差异浅析[J]．中国执业药师,2012,9(9):60-64.doi: 10.3969/j.issn.1672-5433.2012.09.012

Ren YM.Discussion on the Official Standards of Biotechnological Products in Chinese and European Pharmacopeias[J].CHINA LICENSED PHARMACIST.2012,09:9

[9] 高凯，徐志凯，任跃明，等．关于我国药典单克隆抗体类生物治疗药物总论的思考[J]．中国生物工程杂志,2014,34(1):127-134.doi: 10.13523/j.cb.20140117Gao K,Xu ZK,Ren YM, et al.Points to Consider for the General Monograph of MonoclonalAntibody Based Biotherapeutics in Chinese Pharamacopeia [J].China Biotechnology,2014,34(1): 127-134  
[10] Liu M Q, Zeng W F, Fang P, et al. pGlyco 2.0 enables precision N-glycoproteomics withcomprehensive quality control and one-step mass spectrometry for intact glycopeptideidentification[J]. Nature communications, 2017, 8.  
作者简介：黄怡，2015级安徽医科大学与军事医学科学院联合培养硕士研究生  
通信地址：北京蛋白质组研究中心，国家蛋白质科学中心，军事医学院放射与辐射医学研究所，北京市昌平区中关村生命科学园科学园路38号，102206  
常用电话：15205515056  
电子邮箱：15205515056@163.com