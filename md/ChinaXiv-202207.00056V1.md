# 冠状动脉粥样硬化性心脏病患者心外膜脂肪组织的生物信息学分析

摘要:

目的：

通过生物信息学方法挖掘冠状动脉粥样硬化性心脏病（Coronaryarterydisease，CAD）患者心外膜脂肪组织（Epicardial adipose tissue，EAT）中的关键基因，通过富集分析、构建蛋白-蛋白互相作用网络，探讨免疫细胞浸润情况，联合CAD 患者外泌体（ExoSome）差异表达基因推测 EAT来源外泌体差异表达基因并进行验证，从细胞及分子水平上探讨 EAT 在CAD 疾病过程中的作用机制。

方法：

从GEO 数据库下载GSE64554、GSE120774数据集，根据临床信息将心外膜脂肪组织的测序数据分为冠心病组和对照组，利用R语言及相关软件包进行生物信息学分析。首先获取CAD患者与对照组EAT间差异表达基因，并进行富集分析，构建蛋白-蛋白相互作用网络，以评估所选基因的生物学功能及可能参与其调控的转录因子。构建GSE64554数据集中心外膜脂肪组织的加权基因共表达网络（Weighted gene co-expression network analysis，WGCNA），获取同冠心病表型相关的基因模块，将所获 EAT 间差异表达基因与模块内 Hub 基因取交集获得关键基因，同时通过Cibersort反卷积算法对EAT组织的免疫细胞浸润情况进行分析。通过exoRbase数据库获取CAD 患者与健康对照组血液外泌体间差异表达基因，CAD患者同健康对照组EAT 间差异表达基因与CAD患者同健康对照组外泌体间差异表达基因区交集，将其作为CAD的诊断治疗标记物并收集临床样本通过rt-qPCR 对其进行验证。对所选基因进行GO/KEGG 富集分析和 Metascape 富集分析。

结果：

获得心外膜脂肪组织间差异表达基因1511个，其中表达上调的基因956个，表达下调的基因555个。构建 EAT组织表达谱的加权基因共表达网络，获得同CAD 表型相关的模块，将模块内Hub 基因与差异表达基因取交集获得 EAT在CAD 发生发展中的关键基因 DDX47、FEM1C、NOL11、SRP54、ABI1、PATL1、BNIP2、C1orf159、CHCHD4。免疫细胞浸润分析显示，CAD 患者 EAT中幼稚$\mathrm { C D 4 } ^ { + }$ T细胞丰度升高而静息树突状细胞表达丰度减低（ ${ \mathrm { ~ P ~ } } < { \mathrm { ~ 0 . ~ 0 5 } } { \mathrm { ; } }$ ）。获得CAD患者外泌体差异基因1658个，其中表达上调的基因278个，表达下调的基因1380 个，将所获EAT间差异表达基因与外泌体间差异表达基因交集，共获得129 个基因，选取表达丰度较高的 BPI、BIRC5、CXCL12、RNASE1、F2R 作为CAD患者潜在诊断治疗标记物，并同过rt-qPCR进行验证。

GO/KEGG 富集分析表明EAT间差异表达基因主要富集于细胞质基质、MHC 蛋白复合物、RNA 降解、抗原加工和呈递等，构建PPI网络，通过Cytoscape 软件Cytohubba 插件 MCC 算法获得连接度最高的基因 RPS27A。Metascape 富集分析差异表达基因主要富集于细胞对DNA损伤刺激反应、RNA代谢、调节细胞对压力的反应、适应性免疫系统等，TRRUST数据库预测CIITA转录因子可能参与了EAT间差异表达基因的调控。

结论：

（1）心外膜脂肪组织可能通过促炎和免疫途径参与CAD的发生发展，  
DDX47、FEM1C、NOL11、SRP54、ABI1、PATL1、BNIP2、C1orfl59、CHCHD4、  
RPS27A可能作为关键基因并发挥重要作用。（2）CAD患者EAT中幼稚 $\mathrm { C D 4 } ^ { + }$ T细胞丰度升高而静息树突状细胞表达丰  
度减低。（3）BPI、BIRC5、CXCL12、RNASE1、F2R可能由心外膜脂肪组织分泌并  
可作为CAD的诊断标记物。  
关键词：冠心病；心外膜脂肪组织；外泌体；生物信息学分析；免疫浸润The bioinformatics analysis of epicardial adipose tissue from patients with coronaryartery disease

Abstract.

Objective:

This paper is mainly to identify the differential genes and possible pathogenesis of Epicardial adipose tissue (EAT) and Exosome in CAD patients at the cellular and molecular levels.

Methods:

We downloaded the GEO database and analyzed the genes differentially expressed in epicardial adipose tissue from healthy patients and coronary artery disease patients and established the Weighted gene co-expression network by using R language and related software packages. We also used GO/KEGG enrichment analysis and Metascape enrichment analysis to explore the protein interaction network and biological pathways of the choosen genes and analyzed key genes and pathways to find potential targets for use. Last, We interacted the di erentially expressed genes in EAT and exosomes from healthy patients and coronary artery disease patients and Q-PCR was performed the genes which are higher expression.

Results:

Compared with the epicardial adipose tissue with healthy individuals, the epicardial adipose tissue of CAD patients had 1511 differential genes, including 956 genes with up-regulated expression and 555 genes with down-regulated expression. According to the WGCNA， the study identified 9 module which phenotype is the most highly associated with CAD. By interacting the dierentially expressed genes and Hub genes in modules,we identified the key gene DDX47、FEM1C、NOL11、SRP54、 ABI1、PATL1、BNIP2、 C1orf159、CHCHD4.A total of 129 differential genes were obtained by cross-tabbing EAT and EXO,and Q-PCR was performed to analyze the expression of BPI、BIRC5、CXCL12、RNASE1、F2R,the differences were proved to be significant after statistical analysis. GO enrichment analysis showed that differential genes were mainly involved in the cytosol、MHC protein complex integral component of lumenal side of endoplasmic reticulum membrane、 lumenal side of endoplasmic reticulum membrane 、MHC class I protein complex. KEGG signaling pathway enrichment analysis is mainly for RNA degradation, antigen processing, and presentation. By TRRUST datasets, we predicted that transcription factors CIITA may play a vital role in epicardial adipose tissue.

Conclusion:

DDX47、FEM1C、NOL11、SRP54、ABI1、PATL1、BNIP2、C1orf159、CHCHD4 is the key gene in the pathogenesis of epicardial adipose tissue (EAT). Immunocytic infiltration analysis showed that the abundance of naive $\mathrm { C D 4 + }$ T cells in EAT which from CAD patients was significantly increased ( $( \mathbf { P } < 0 . 0 5 )$ .BPI、BIRC5、CXCL12、 RNASE1、F2R may excrete from epicardial adipose tissue and have the potential in CAD diagnosis.

Key word: CAD;EAT; Exosome; Bioinformatics; Immune cell infiltration

动脉粥样硬化（Atherosclerosis，AS）导致的心血管疾病(Cardiovascular heart disease，CVD)是全球死亡的主要原因，世界卫生组织预测 2030 年将有 2360 万人死于心血管疾病[。动脉粥样硬化形成机制复杂，主要涉及血管内皮损伤，单核巨噬细胞粘附，脂质沉积等[2，但其如何影响动脉粥样硬化过程尚未完全清楚，如果能利用基因芯片技术对临床患者标本进行检测分析，筛选出一些具有价值的基因，进而深入研究冠心病的发病机制将更有意义。肥胖是心血管疾病的独立危险因素，但肥胖的主要评价指标 BMI指数却同AS 患者死亡率呈“U”型关联，这种现象被称为肥胖悖论，因此脂肪组织不再被认为是单纯的“能量仓库”，而是一种代谢活跃的内分泌和旁分泌器官[3]。心外膜脂肪组织（Epicardial adiposetissue，EAT）在解剖上与冠状动脉紧密相连，同动脉粥样硬化、心房颤动、心力衰竭等心血管疾病密切相关[4-6]。多项研究发现功能失调的EAT通过分泌外泌体和生物活性物质促进动脉粥样硬化疾病进展，但其作用机制仍需进一步研究。本研究通过多种生物信息学方法对冠心病患者心外膜脂肪组织和外泌体的测序数据进行挖掘，深入探讨了心外膜脂肪组织参与动脉粥样硬化的分子生物学过程，联合外泌体测序数据获得心外膜脂肪组织来源的外泌体基因并对其诊断价值进行了验证，最终发现 BPI、BIRC5、CXCL12、RNASE1、F2R可能由心外膜脂肪组织分泌并可作为CAD的诊断标记物，为心外膜脂肪组织在冠状动脉粥样硬化中的机制研究以及临床诊治

提供了理论基础。

# 1．材料与方法

1.1数据集的下载与预处理

（1）在GEO 数据库官网内，以“epicardial adipose tissue OR EAT”为关键词，选择“Homo sapiens”为研究对象检索，根据数据集提供的相关信息，获得所需芯片GSE64554、GSE120774。下载 seriesmatrix的数据，采用“combat”R语言包去除批次效应，合并基因表达矩阵。

（2）通过exoRbase数据库（exorbase.org）获取冠状动脉粥样硬化性心脏病患者与健康者血液外泌体基因表达谱。

# 1.2差异基因的筛选

通过“Limma”R语言包对合并后数据集中CAD 患者与非CAD 患者 EAT间差异表达基因（Differentially Expressed Genes，DEGs）和CAD 患者与非CAD 患者外泌体间 DEGs 进行筛选，以 $\mathrm { P } { < } 0 . \ : 0 5$ 为条件，并将结果可视化为火山图和热图。

# 1.3加权基因共表达网络的构建与CAD相关模块的识别

为了防止合并数据集对基因关联度的影响，我们使用“WGCNA”R语言包构建GSE64554数据集基因共表达网络并识别出模块。选择满足无尺度网的标准的软阈值β使得构建基因共表达网络，转化拓扑重叠矩阵（Topological overlapmatrix，TOM），采用动态剪枝法对模块进行初步划分。根据GSE64554数据集样本临床信息，决定纳入的临床信息有疾病（Disease）和年龄（Age），得到相关性最高的模块进行后续分析。计算基因与模块的相关系数（Module membership,MM）来评估基因与模块之间的相关性，以 $| \mathrm { M M } | { > } 0 . 8$ 筛选模块内Hub 基因。

# 1. 4 基因的功能分析

通过“ClusterProfiler”R语言包将所获基因进行富集分析，以FDR 值<0.05为筛选标准，进行通路富集分析。通过GO分析，可得所选基因所富集的生物过程（biological process，BP）、细胞组分（cellular components，CC）及分子功能（molecularfunction，MF）。通过KEGG分析，可得到所选基因所富集的信号通路。并将所获基因导入Metascape在线数据库[进行基因的富集分析以及转录因子预测。

# 1.5蛋白相互作用网络的构建与枢纽基因筛选

将所选基因倒入STRING 数据库（https://string-db.org）构建蛋白-蛋白相互作用(protein-protein interaction,PPI)网络,将PPI 网络倒入Cytoscape（Version 3.9.0）软件[1]通过CytoHubba 插件 MCC 算法获得连接度最高的10 个基因作为关键基因，并进行画图。

# 1.6免疫细胞浸润分析

在 Cibersort 网站（https://cibersort.stanford.edu/）下载 22 种免疫细胞的基因表达矩阵。采用Cibersort反卷积算法。计算GSE64554芯片中 46 个样本的免疫细胞浸润情况，并作图对组织的免疫细胞浸润情况进行对比。

# 1.7临床样的本采集

从山西医科大学第二附属医院介入手术室采集冠脉造影患者20 例外周血，其中冠心病患者及非冠心病患者各10 例，血液样本在进行进一步实验之前储存在液氮中。所有受试者均已签署知情同意书，临床标本采集使用方案经山西医科大学第二医院研究伦理委员会批准。

1.8实时荧光定量 PCR(Quantitative real-time PCR，qRT-PCR)

照总RNA快速提取试剂盒（RP4001，百泰克公司）的说明提取血浆中的总RNA，cDNA 的合成按照HiScript III RT SuperMix for qPCR（ $\mathrm { \dot { \Psi } + g D N A }$ wiper)试剂盒的步骤进行，第一步去除总RNA中的残余的DNA，第二步反转录cDNA，得到的cDNA 保存于 $- 2 0 ^ { \circ } \mathrm { C }$ 冰箱，接下来以cDNA为模板，进行qRT-PCR。反应程序为：$9 5 \mathrm { ^ \circ C }$ 3 min; $9 5 ^ { \circ } \mathrm { C }$ 5s， $6 0 ^ { \circ } \mathrm { C }$ 10 s， $7 2 ^ { \circ } \mathrm { C }$ 30 s，40个循环； $9 5 ^ { \circ } \mathrm { C }$ 15 s, $6 5 ^ { \circ } \mathrm { C }$ 5s， $9 5 ^ { \circ } \mathrm { C } ~ 5 0 ~ \mathrm { ~ s ~ }$ 。结果用 $2 ^ { - }$ 进行计算分析。

1.9.统计学分析：应用SPSS26软件包进行统计学分析，实验所得数据均采用mean $\pm \mathrm { S D }$ ，两组对照比较采用 $t$ 检验， $P \langle 0 . 0 5$ 有统计学意义。

# 2.结果

2.1冠状动脉粥样硬化性心脏病患者外膜脂肪组织间的差异表达基因

# 2. 1. 1 差异表达基因的获取

采用“limma”包选获取CAD 患者与非CAD 患者 EAT 间差异表达的基因，以$\mathrm { P } { < } 0 . \ : 0 5$ 作为筛选差异基因的阈值，得到差异表达的1511个mRNA，其中上调956个，下调 555个。

![](images/606d449dc4ca341d7a958d0d75e791df19f1a1a9d5acd06d38ccfe224674ac8b.jpg)  
图1：CAD患者与非CAD患者心外膜脂肪组织间差异表达基因火山图

![](images/f636158954ba483e73d1c56bbc9d84dc2ed930e022868885636f63f8abf76efe.jpg)  
图2：CAD患者与非CAD患者心外膜脂肪组织间差异表达基因热图

2.1.2EAT差异表达基因的GO/KEGG分析与蛋白相互作用网络

对合并后CAD组较正常对照组EAT差异表达基因进行GO 富集分析，共获得符合筛选条件的GO 术语共 800 条，其中生物学过程（Biological process，BP）567条，主要涉及细胞压力反应、细胞DNA 损伤刺激反应等。获得细胞成分（CellularComponent，CC）127条，主要涉及细胞质基质、MHC 蛋白复合物、内质网膜腔侧的组成部分等。获得分子功能（Molecularfunction，MF）106条，主要涉及MHCII类蛋白复合物结合、特殊核糖核酸酶激活等。共富集到KEGG 通路 20 个，主要涉及RNA 降解、病毒性心肌炎、移植物抗宿主病、I型糖尿病等信号通路。

![](images/03e17cdecfde10779fc0684d602574475ce5c3cccf664b2d30125df08e60c6ab.jpg)  
图3：EAT差异表达基因的GO富集分析

![](images/fc125ff253074b422fbba49fe03060003a25dde861830351f0c415ed2244a050.jpg)  
图4：EAT差异表达基因的KEGG富集分析

将所获EAT间差异表达基因输入STRING数据库，构建PPI网络，其中实际上有互作关系的节点有1507个，有1258条边，每个节点的平均Degree为1.67分。将PPI 网络图倒入Cytoscape 软件，使用CytoHubba 插件根据 MCC 算法得到连接度前10 的基因并作图，分别为。RPS27A、PSME4、PSMA1、PSMA5、GLI3、GLI1、PSME2、PSMB、SUFU和SHH。

![](images/0fa52708aca2bc916073277ebc06d6f41d4d14eae8babd3d72663f7622857a70.jpg)  
图5：EAT差异表达基因的PPI网络与关键基因   
图6：EAT差异表达基因的Metascape富集分析

2.1.3 EAT差异表达基因的Metascape 富集分析

对合并后CAD组较对照组EAT差异表达基因进行Metascape 富集分析，发现差异表达基因主要富集于嗅觉转导、细胞对DNA损伤刺激反应、单纯疱疹病毒1型感染、RNA代谢、调节细胞对压力的反应、适应性免疫系统等，TRRUST数据库预测CIITA转录因子可能参与了EAT间差异表达基因的调控。

hsa04740: Olfactory transduction GO:0006974: cellular response to DNA damage stimulus R-HSA-8953854:MetabolismofRNA hsa05168:Herpes simplex virus1 infection GO:008ol35:regulation of cellular response to stress R-HSA-1280218: Adaptive Immune System GO:1903311: regulation of mRNA metabolic process hsa04612:Antigen processing and presentation R-HSA-3700989: Transcriptional Regulation by TP53 GO:0009895:negative regulation of catabolic process GO:0006886: intracellular protein transport GO:0022613:ribonucleoprotein complex biogenesis GO:0046649:lymphocyte activation R-HSA-5619115:Disordersof transmembrane transporters GO:0019438:aromatic compound biosynthetic process R-HSA-8953897: Cellular responses to stimuli GO:0030l62:regulation of proteolysis R-HSA-5653656:Vesicle-mediated transport GO:006o341: regulation of cellular localization GO:0001934: positive regulation of protein phosphorylation 0 2 4 6 8 10 12 -og10(P)

![](images/b87f77cb521bfd3373bcf79713c4c3022281f14288aacb9bba3b10a296b696a5.jpg)  
图8:EAT差异表达基因的TRRUST数据库预测转录因子

# 2.2 EAT组织的WGCNA分析

2.2.1EAT组织WGCNA软阈值的选择与模块的初步划分

本研究最终以 $\mathrm { ~ \AA ~ } = 5$ 作为软阈值来构建共表达网络，设置每个基因模块中基因数目最小为30，设定基因的聚类高度上限为0．995。最终得到156个网络模块，模块中的基因个数从30个到2169个不等。根据拓扑重叠程度，制作模块相关性图。

![](images/a80a6e37f738e7ac87133a4b1b6196e5a8bcced5345bebba11e8fb24eb21d0e8.jpg)  
图9:软阈值参数网络拓扑结构的分析

（左图为不同β下计算的无尺度符合指数，右图为不同β下计算的平均连接度

![](images/ab5d1c77fef2161a7b21b003e6fc4a9300acecdf22b001b63ea9f3a5a011d8bd.jpg)  
图10：基因聚类树状图

2.2.2临床信息关联与Hub基因的获取

将各个划分出的模块与临床信息进行关联分析，得到与动脉粥样硬化患者的心外膜组织样本临床信息最为相关的模块进行后续研究。结果发现，动脉粥样硬化患者心外膜脂肪组织与 green4模块（ $\mathrm { r } { = } 0 . 5 0$ ， $\mathrm { p { = } 0 . 0 2 }$ ）、slateblue模块（ $\mathrm { r = } 0 . 5 4$ ， $\mathrm { p { = } 8 . 0 { * } 1 0 ^ { - 3 } }$ ）、darkseagreen4模块（ $\mathrm { { r } = 0 . 5 5 }$ ， $\mathrm { p { = } 6 . 4 { * } 1 0 ^ { - 3 } }$ ）、darkolivegreenl （ $\mathrm { { r } = 0 . 5 5 }$ ， $\mathrm { p { = } 7 . 0 { * } 1 0 ^ { - 3 } }$ ）sienna4（ $\mathrm { r } { = } 0 . 5 6$ ， $\mathrm { p } { = } 5 . 6 { * } 1 0 ^ { - 3 }$ ）、brown3 ( $\mathrm { r } { = } 0 . 5 7$ ， $\mathrm { p { = } 4 . 2 { * } 1 0 ^ { - 3 } }$ ）正相关，与deeppink（ $\mathrm { r } { = } 0 . 5 0$ ， $\mathrm { \ p = 0 . 0 1 }$ ）lavender( $\mathrm { { \Phi } _ { r = 0 . 6 0 } }$ ， $\mathrm { p { = } 2 . 6 { * } 1 0 ^ { - 3 } }$ ）、lavenderblush3（ $\mathrm { r } { = } 0 . 5 6$ ， $\mathrm { p { = } 5 . 9 { * } 1 0 ^ { - 3 } } .$ ）负相关，以 $| \mathrm { M M } | { > } 0 . 8$ 筛选所选模块内 Hub 基因。

![](images/763297b1e57a1060c35e0b165b956199c3dc8bdb0057b820aa3c62cbb44cb864.jpg)  
图11:基因模块与临床信息关联性

# 2.3关键基因的获得

将差异表达基因同模块内Hub 基因取交集,获得差异表达的模块内Hub基因，将其作为EAT 组织参与动脉粥样硬化病理生理过程的关键基因，其中上调 Hub 基因为DDX47、FEM1C、NOL11、SRP54、ABI1、PATL1、BNIP2，下调 Hub 基因 C1orf159、CHCHD4。

![](images/ddcbdfe7fca2e90cfa4b6b99473765c42ed5c118d671489f4ea15eecbd0b9492.jpg)  
图12:差异表达基因与模块内Hub基因Venn图

# 2.4免疫细胞浸润分析

通过Cibersort反卷积算法。计算GSE64554芯片中冠心病和非冠心病患者EAT组织的免疫细胞浸润情况。研究发现，冠心病患者EAT组织较对照组中初始CD4T 细胞较对照组表达丰度升高（ $\mathrm { P = } 0 . 0 4 8 \$ ），静息树突状细胞表达丰度减低（ $\mathrm { P = } 0 . 0 4 4$ ）。

![](images/9129551d70efedc6de7dec9cf2cbb347ac13f808da0e6932061ab3c5ae6ab262.jpg)  
图13:GSE645554数据集EAT组织免疫细胞浸润柱状图

![](images/e3ff995c46cd2cbebd8773f3c568fd504a595df8abe7348b6dcae7a7440d2f1b.jpg)  
图14:GSE645554数据集 EAT组织免疫细胞浸润小提琴图

(红色为CAD组，蓝色为正常对照组)

2.2 CAD患者与非CAD患者外泌体间差异表达基因

采用“1imma”包选获取CAD患者与非CAD 患者外泌体间差异表达的基因，以 $\mathrm { P } { < } 0 . 0 5 , \mathrm { l o g } ^ { | \mathsf { F o l d c h a n g e } | } { > } 1$ 作为筛选差异基因的阈值，共得到差异表达基因1658个，其中上调 278个，下调1380个。

![](images/f63effc4b087fb5379ceee2eed6a7b0c7347a2ec3af73e6793f1a629cdfb1639.jpg)  
图15：CAD患者与非CAD患者外泌体间差异表达基因火山图

![](images/9b6fd9101cd02bb492910f42899ecd4d3ebb3f384a5b4814f2504451e0fcb1f7.jpg)  
图16：CAD患者与非CAD患者外泌体间差异表达基因热图

# 2.4心外膜脂肪组织来源外泌体

脂肪组织作为人体外泌体最大的来源之一，心外膜脂肪族可能通过外泌体参与AS 疾病进展，将CAD 患者与非CAD 患者心外膜、外泌体间差异表达的基因取交集并做Venn图，共获得129个基因，其中上调16，下调113个，经筛选，将 BPI、BIRC5、CXCL12、RNASE1、F2R 作为关键基因并通过rt-qPCR 进行验证。

![](images/f31918c714dffa2e55e9070123018fc83833c72379b779d77095a6553fbd9897.jpg)  
图17：CAD患者EAT组织、外泌体差异表达基因Venn图

2.5心外膜组织来源外泌体间差异表达基因的验证

收集冠心病患者和健康对照者外周血，运用qRT-PCR 验证生物信息学分析所得的心外膜脂肪组织来源外泌体基因BPI、BIRC5、CXCL12、RNASE1、F2R的 mRNA水平。结果表明，与对照组相比，CAD患的5个所选基因的表达水平显著变化，其中BPI、BIRC5、CXCL12 和 RNASE1的 mRNA 水平显著升高（ $\mathrm { ( P < 0 . 0 5 ) }$ ），F2R基因的mRNA水平显著下调（ $\mathrm { . P } { < } 0 . 0 5 \$ ）。

冠心病与非冠心病患者外泌体差异性基因表达（ $\stackrel { - } { x } \pm s )$ （204   

<html><body><table><tr><td>组别</td><td>样本数</td><td>BPI</td><td>BIRC5</td><td>CXCL12</td><td>RNASE1</td><td>F2R</td></tr><tr><td>冠心病</td><td>10</td><td>2.14±0.32</td><td>1.98±0.23</td><td>2.91±0.89</td><td>4.47±1.56</td><td>0.45±0.06</td></tr><tr><td>非冠心病</td><td>10</td><td>0.99±0.17</td><td>1.02±0.11</td><td>1.14±0.44</td><td>1.28±0.56</td><td>1.00±0.12</td></tr><tr><td>F</td><td></td><td>2.99</td><td>3.73</td><td>3.82</td><td>4.32</td><td>5.02</td></tr><tr><td>显著性</td><td></td><td>0.10</td><td>0.07</td><td>0.07</td><td>0.052</td><td>0.058</td></tr><tr><td>t</td><td></td><td>-9.95</td><td>-12. 07</td><td>-5.63</td><td>-6.01</td><td>12. 637</td></tr><tr><td>p</td><td></td><td>0.01</td><td>0.01</td><td>0.00</td><td>0.01</td><td>0.00</td></tr></table></body></html>

表1：心外膜组织来源外泌体内关键基因在外周血的表达情况

3．讨论

心血管疾病已成为国民致死、致残和医疗费用增长的重要原因，是我国面临的重大公共卫生问题，因此找寻新的诊断靶点，为CAD患者的临床精准治疗提供理论参考依据有重要意义。心外膜脂肪组织作为一种特殊的脂肪组织，解剖结构上紧贴冠状动脉，在病理环境中其向炎症表型转化，通过分泌促炎细胞因子和外泌体参与血管内皮损伤、血管重塑、免疫细胞粘附等AS 病理生理过程。心外膜脂肪组织的炎症反应是动脉粥样硬化的全新诊断治疗靶点[5，Evangelos 等人通过影像组学技术将心外膜脂肪衰减系数（Fat AttenuationIndex，FAI）应用于冠心病患者的早期筛查[12]，而目前已广泛应用于临床的钠-葡萄糖协同转运蛋白2(sodium-dependent glucose transporters 2，SGLT-2)抑制剂达格列净则可以通过减轻 EAT 炎症而对减少糖尿病患者心血管病事件的发生率[13]。但心外膜脂肪组织在CAD 中的作用机制仍需进一步研究。

首先我们通过生物信息学分析的方法从数据集GSE64554和GSE120774中获得出CAD 和对照组心外膜脂肪组织中的差异基因1511个，通过富集分析发现差异表达基因主要富集于细胞质基质、MHC 蛋白复合物、MHCII蛋白复合物、RNA降解、抗原加工和呈递等。目前动脉粥样硬（Atherosclerosis，AS）被认为是一种慢性炎症性疾病，MCHII作为T细胞的呈递抗原，通过抗原识别、细胞活化、产生细胞因子等方式在炎症过程和CAD 进展中发挥作用[14]。通过Meatscape 富集分析中的 TRRUST数据库，我们预测到转录因子 MHC-II反式激活蛋白（CIITA）可能在 EAT中发挥了重要的调节作用。研究发现，CIITA通过其转录后修饰甲基化[15]、去乙酰化[16,17调节 MHC II 的转录而参与AS。通过免疫细胞浸润分析本研究发现CAD 患者EAT中幼稚 $\mathrm { C D 4 } ^ { + }$ T细胞丰度升高，早在2015年 SalvadorLborra 等人便18指出可以通过观察幼稚 $\mathrm { C D 4 } ^ { + }$ T 细胞的体外分化程度评估动脉粥样硬化程度，Gaddis DE 等人[9指出动脉粥样硬化通过影响糖酵解而损害幼稚 $\mathrm { C D 4 } ^ { + }$ T细胞功能。综上所述，MHCII在AS中发挥了重要作用，但其在CAD 患者心外膜脂肪组织中的作用和调控机制仍需进一步研究。

通过筛选CAD 患者与对照组EAT 间差异表达基因，构建 EAT组织加权基因共表达网络，我们获得了DDX47、FEM1C、NOL11、SRP54、ABI1、PATL1、BNIP2、C1orf159、CHCHD4，RPS27A共10个基因作为心外膜脂肪组织参与CAD病理生理过程的关键基因。目前仅有关键基因被发现在心血管疾病中的发挥作用，Xiaxiaodong等人[2通过生物信息学技术发现免疫相关基因RPS27A可能参与AS 的病理过程，Huangjing 等人[21]指出 RPS27A基因在糖尿病视网膜病变的关键基因且同幼稚 $\mathrm { C D 4 } ^ { + }$ T 密切相关。Li等人[22发现 MBNL1通过对ABI1的剪切调控AS 中平滑肌细胞的表型转换。因此，关键基因仍需进一步细胞以及动物实验证明其在EAT中的差异表达以及相关功能。

内皮细胞、平滑肌细胞、心肌细胞、脂肪细胞和血小板来源的外泌体通过转运蛋白质、RNA、DNA 和其他生物活性物质在缺血再灌注损伤、血管钙化、动脉粥样硬化和心脏重塑中发挥了重要作用，已成为CAD 的全新诊断治疗靶点[23]。脂肪组织是循环中外泌体最大的来源之一[24]，冠状动脉血管周围脂肪组织是一种特殊的心外膜脂肪组织[25]，Liuyi 等人[26]发现血管周围脂肪组织来源外泌体中 miR-382-5p 通高 ABCA1/ABCG1信号通路调节泡沫巨噬细胞形成。Li Xinzhi 等人发现血管周围脂肪组织来源外泌体中miR-221-3p 通过接到血管重塑参与AS。ZhaoQi等人发现芒果苷诱导血管周围脂肪组织衍生的外泌体可以改善AS 中的内皮功能障碍，因此心外膜脂肪组织来源外泌体在AS 中的作用具有重要的研究价值。

为进一步探讨心外膜脂肪组织在冠状动脉粥样硬化的心脏病中的作用机制，我们将CAD 患者与健康对照组的心外膜脂肪组织间差异表达基因、外泌体间差异表达的基因取交集，共获得129个基因，并筛选表达程度较高、有意义的基因RNASE1、BPI、BIRC5、CXCL12、F2R。其中前4个基因为CAD 患者中上调基因。核糖核酸酶1（RNase1)是一种可分泌的耐热蛋白，具有强大的心脏保护功能[28],，其通过保护内皮细胞在炎症中的损伤而成为血管稳态的关键调控者[29]，在CAD 中，EAT 可能通过外泌体释放 RNase1进而调节冠状动脉内皮细胞的炎性损伤。血管生成趋化因子介导细胞趋化、白细胞脱粒和血管生成，CXCL-12同动脉粥样硬化密切相关[30]，其通过CXCL12-CXCR4 轴参通过平滑肌细胞表型转化保护血管稳态[31]，特异性过表达巨噬细胞 IGF-1 通过减少 CXCL12 介导的单核细胞募集和增加ABCA1依赖性巨噬细胞脂质外流增加动脉粥样硬化斑块的稳定性[32]，但目前尚无关于外泌体内CXCL12 的相关研究。BIRC5 是凋亡抑制蛋白（IAP）家族的成员，Li 等人[33]通过对小鼠颈动脉单细胞测序发现 BIRC5 可能同血流紊乱所致血管巨噬细胞聚集相关。早在2002 年便有报道指出 BPI的单核苷酸多态性同心肌梗死密切相关[34]，Onno B Blei jerveld 等人[35]便通过循环中粒细胞的深度蛋白质组分析发现了BPI可以作为严重动脉粥样硬化性冠状动脉狭窄的生物标志物，这表明 BPI可以作为晚期CAD乃至预测急性心血管事件的标记物。凝血因子2受体（F2R）是血管壁炎症和血栓形成的关键调节剂，其多态性同氯吡格雷疗效密切相关[36]，但目前少有F2R在AS 中的研究。

综上所述，本研究共确定了DDX47、FEM1C、NOL11、SRP54、ABI1、PATL1、BNIP2、C1orf159、CHCHD4，RPS27A共10 个关键基因，RNASE1、BPI、BIRC5、CXCL12、F2R共5个可能源自心外膜脂肪外泌体的基因进行了验证，证明其在冠心病中的诊疗意义，此外还探讨了CAD 患者EAT免疫浸润情况，为动脉粥样硬化性心脏病的基础研究提供理论支持。

# 参考文献

[1]Napoli C, Crudele V, Soricelli A,Al-Omran M, Vitale N, Infante T, Mancini FP. Primary prevention of atherosclerosis: a clinical challenge for the reversal of epigenetic mechanisms? Circulation. 2012 May 15;125(19):2363-73.   
[2]Alkhalil M, Choudhury RP. Current concepts in atherosclerosis. Indian J Thorac Cardiovasc Surg. 2018 Dec;34(Suppl 3):198-205.   
[3] BEL J S, TAI T C, KHAPER N, et al. Mirabegron: The most promising adipose tissue beiging agent[J/OL].Physiological Reports,2021, 9(5)[2021-06-28].   
[4] PATEL K HK, HWANG T, SE LIEBERS C, et al. Epicardial adipose tissue as a Circulatory Physiology, 2022, 322(2): H129-H144.   
[5]CONTE M, PETRAGLIA L, POGGIO P, el. Inflammation and Cardiovascular Diseases in the Elderly: The Role of Epicardial Adipose Tissue[J/OL]. Frontiers in Medicine, 2022, 9: 844266.   
[6]SONG Y, SONG F, WU C, et al. The roles of epicardial adipose tissue in heart failure[J/OL]. Heart Failure Reviews, 2022, 27(1): 369-377.   
[7]ZHAO Q, YANG J, LIU B, et al. Exosomes derived from mangiferin-stimulated perivascular adipose tissue ameliorate endothelial dysfunction[J/OL]. Molecular Medicine Reports,2019[2021-05-09].   
[8]SMYTHG K, MICHAUD J, SCOTT H S. Use of within-array replicate spots for assessing differential expression in microarray experiments[J/OL]. Bioinformatics, 2005,21(9): 2067-2075.   
[9] YU G, WANG L G, HAN Y, et al. clusterProfiler: an R Package for Comparing Biological Themes Among Gene Clusters[J/OL]. OMICS: A Journal of Integrative Biology, 2012, 16(5): 284-287.   
[10] ZHOU Y, ZHOU B, PACHE L,et al. Metascape provides a biologist-oriented resource for the analysis of systems-level datasets[J/OL]. Nature Communications, 2019,10(1): 1523.   
[11] SHANNON P, MARKIEL A，OZIER O，et al. Cytoscape: A Software Environment for Integrated Models of Biomolecular Interaction Networks[J/OL]. Genome Research, 2003,13(11): 2498-2504.   
[12] OIKONOMOU E K, WILLIAMS MC, KOTANIDIS C P, et al. A novel machine learning-derived radiotranscriptomic signature of perivascular fat improves cardiac risk prediction using coronary CT angiography[J/OL]. European Heart Journal, 2019, 40(43): 3529-3543.   
[13] SATO T, AIZAWA Y, YUASA S, et al. The effect of dapagliflozin treatment on epicardial adipose tissue volume[J/OL]. Cardiovascular Diabetology, 2018, 17(1): 6.   
[14] SAGE A P, MURPHY D,MAFFIA P, et al. MHC Class II-Restricted Antigen Presentation by Plasmacytoid Dendritic Cells Drives Proatherogenic T Cell Immunity[J/OL]. Circulation, 2014, 130(16): 1363-1373.   
[15] FAN Z, LI J, LI P, 等. Protein arginine methyltransferase 1 (PRMT1) represses MHC II transcription in macrophages by methylating CIITA[J/OL]. Scientific Reports,2017, 7(1): 40531. DOI:10.1038/srep40531.   
[16] WU X, KONG X, CHEN D, et al. SIRT1 links CIITA deacetylation to MHC II activation[J/OL]. Nucleic Acids Research,2011, 39(22): 9549-9558.   
[17] KONG X, FANG M, LI P, et al HDAC2 deacetylates class II transactivator and suppresses its activity in macrophages and smooth muscle cells[J/OL]. Journal of Molecular and Cellular Cardiology, 2009, 46(3): 292-299.   
[18] Iborra S, Gonzalez-Granado JM. In Vitro Differentiation of Naive CD4 $\boxed { \begin{array} { r l } \end{array} }$ T Cells: A Tool for Understanding the Development of Atherosclerosis.Methods Mol Biol.

2015;1339:177-89.[19]GADDIS D E，PADGETTL E，WUR， etal. Atherosclerosis Impairs Naive CD4 T-Cell Responses via Disruption of Glycolysis[J/OL]. Arteriosclerosis， Thrombosis, and Vascular Biology， 2021， 41(9): 2387-2398.

[20] Xia X, Wang M, Li J, Chen Q, Jin H, Liang X, Wang L. Identification of potential genes associated with immune cell infiltration in atherosclerosis. Math Biosci Eng. 2021 Mar 5;18(3):2230-2242.

[21] HUANG J, ZHOU Q. Identification of the Relationship between Hub Genes and Immune Cell Infiltration in Vascular Endothelial Cells of Proliferative Diabetic Retinopathy Using Bioinformatics Methods[J/OL]. Disease Markers, 2022, 2022: 1-21.

[22] LI Y, GUO X, XUE G, et al. RNA Splicing of the Abil Gene by MBNL1 contributes to macrophagelike phenotype modulation of vascular smooth muscle cell during atherogenesis[J/OL]. Cell Proliferation, 2021, 54(5)[2022-03- 20].

[23] CHEN A Q, GAO X F, WANG Z M, et al. Therapeutic Exosomes in Prognosis and Developments of Coronary Artery Disease[J/OL]. Frontiers in Cardiovascular Medicine, 2021, 8: 691548.

[24] BOND S T, CALKIN A C, DREW B G. Adipose-Derived Extracellular Vesicles: Systemic Messengers and Metabolic Regulators in Health and Disease[J/OL]. Frontiers in Physiology, 2022,13: 837001.

[25] AHMADIEH S,KIM H W, WEINTRAUB N L. Potential role of perivascular adipose tissue in modulating atherosclerosis[J/OL]. Clinical Science, 2020, 134(1): 3-13.

[26] LIU Y, SUN Y, LIN X,et al. Perivascular adipose-derived exosomes reduce macrophage foam cell formation through miR-382-5p and the BMP4-PPARγ- ABCA1/ABCG1 pathways[J/OL]. Vascular Pharmacology, 2022, 143: 106968.

[27]LI X, BALLANTYNE L L, YU Y, et al. Perivascular adipose tissue-derived extracellular vesicle miR2213p mediates vascular remodeling[J/OL]. The FASEB Journal, 2019, 33(11): 12704-12722.

;] MARKOVIC D, JEVTOVIC-STOIMENOV T, COSIC V, et al. Clinical Utility of Survivin (BIRC5), Novel Cardiac Biomarker, as a Prognostic Tool Compared to High-Sensitivity C-Reactive Protein, Heart-Type Fatty Acid Binding Protein and Revised Lee Score in Elderly Patients Scheduled for Major Non-Cardiac Surgery: A Prospective Pilot Study[J/OL]. Journal of Medical Biochemistry, 2018, 37(2): 110-120.

[29] BEDENBENDER K， SCHMECK B T. Endothelial Ribonuclease 1in Cardiovascular and Systemic Inflammation[J/OL]. Frontiers in Cell and Developmental Biology, 2020, 8: 576491.

[30] TAVAKOLIAN FERDOUSIE V, MOHAMMADI M, HASSANSHAHI G, et al. Serum CXCL10 and CXCL12 chemokine levels are associated with the severity of coronary artery disease and coronary artery occlusion[J/OL]. International Journal of Cardiology, 2017, 233: 23-28.

[31] MAUSE S F, RITZEL E, DECK A, . et al Engagement of the CXCL12-CXCR4 Axis in the Interaction of Endothelial Progenitor Cell and Smooth Muscle Cell to Promote Phenotype Control and Guard Vascular Homeostasis[J/OL]. International Journal of Molecular Sciences, 2022, 23(2): 867.

2] SNARSKI P, SUKHANOV S, YOSHIDA T, et al. Macrophage-Specific IGF-1 Overexpression ReducesCXCL12 Chemokine Levelsand Suppresses AtheroscleroticBurden in Apoe-DeficientMice[J/OL]. Arteriosclerosis, Thrombosis,and Vascular Biology, 2022, 42(2): 113-126.

[33] LI F, YAN K, WU L, et al. Single-cell RNA-seq reveals cellular heterogeneity of mouse carotid artery under disturbed flow[J/OL]. Cell Death Discovery, 2021, 7(1): 180. DO1:10.1038/s41420-021-00567-0.

[34] HUBACEK J A，PITHA J， SKODOVA Z，et al. Polymorphisms in the Lipopolysaccharide-Binding Protein and Bactericidal/Permeability-Increasing Protein in Patients with Myocardial Infarction[J/OL]. Clinical Chemistry and Laboratory Medicine,2002 40(11)[2022-03-20].

[35] BLEIJERVELD O B, WIJTEN P, CAPPADONA S, et al. Deep Proteome Profiling of Circulating Granulocytes Reveals Bactericidal/Permeability-Increasing Protein

as a Biomarker for Severe Atherosclerotic Coronary Stenosis[J/OL]. Journal of Proteome Research, 2012, 11(11): 5235-5244. [36] COLE J W. F2R Polymorphisms and Clopidogrel Efficacy and Safety: Another Step Toward Precision Medicine[J/OL]. Neurology, 2021, 96(1): 10-11.