基础研究

# 差异基因表达谱分析小鼠烧伤早期免疫细胞刺激反应的相关基因靶标

金辉,高艳彬，卢志阳,邹琼，史鹏伟,杨磊南方医科大学南方医院烧伤科，广东广州510515

摘要：目的利用生物信息学方法对小鼠烧伤早期免疫细胞差异基因表达谱进行分析，筛选烧伤早期应对刺激反应相关基因靶标。方法从GEO数据库中下载GSE7404数据集，通过配对样本t检验和倍比法筛选差异表达基因，利用DAVID数据库进行GO功能富集分析筛选刺激反应相关差异表达基因,并进行KEGG通路富集分析，同时应用STRING数据库及Cytoscape软件构建刺激反应相关基因的蛋白互作网络,运用荧光定量PCR技术验证其中部分基因差异表达。结果（1)在烧伤后第1天共有259个刺激反应相关差异基因被选出,其中上调基因118个，下调基因141个。KEGG通路富集分析显示差异基因主要富集于免疫相关通路及细胞生长与死亡相关通路;将259个刺激反应相关差异基因通过STRING数据库及Cytoscape软件进行蛋白互作网络分析,分析显示Lck、Stat1、Myd88、Stat3和Jun基因同时在蛋白互作网络中具有最大互作关系和在子网络中处于中心位置,可能是潜在的诊断及治疗靶标；(2)实时荧光定量PCR技术检测显示Lck、Stat1、Myd88、Stat3和Jun基因表达情况与分析结果相一致。结论 通过对小鼠烧伤后第1天全血游离白细胞基因芯片分析我们发现Lck、Stat1、Myd88、Stat3和Jun基因在烧伤早期刺激反应过程中发挥重要的作用。

关键词：烧伤;刺激反应；基因芯片；蛋白互作网络

# Screening genes related with leukocyte responses early after burn injury: analysis of differentially gene expression profiling data in mice

JINHui, GAO Yanbin,LU Zhiyang,ZHOU Qiong,SHIPengwei,YANG Lei Departmentof Burns,Nanfang hospital,SouthernMedicalUniversity,Guangzhou 5o515,China

Abstract:ObjectiveToscreen thegenes related withleukocyteresponses inmiceearlyafter burn injuryby bioinformatic analysis of te gene expression profiling data.Methods Gene expression profiles were obtainedfrom GEO(GSE7404,Mouse musculus, $2 5 \%$ TBSA,fullthickness) database. After screening of the diferentially expressed genes (DEGs)） through paired-samplet-testand fold-change,DAVIDonline tools wereused toselectthe DEGs related toleukocyteresponses toburns by GO functional enrichment analysis; the interacting genes identified through KEGG pathway enrichment analysis were transferred to STRING toconstructthe protein-protein interaction (PPI) network.Biological annotationof thesub-networks was executed using the software Cytoscape.Real-timePCR was used to verifythe DEGs identified in mice.Results Of the 259 leukocyte response-related DEGs screeed at1 day post-burn,118 were up-regulatedand141 were down-regulated.KEGG pathwayenrichmentanalysisshowed thathepathways were associated with theimmune function,cellgrowthandcell death. PPInetworkand moduleanalysissuggested thatsomeof genes (suchasLck,Statl,Myd,Stat3,andJun)playcriticarolesin thePPInetworkpostburn.R-CRresultswereconsistentwiththoseofbioinformaticanalysis.ConclusionLck,Statyd88, Stat3,and Jun might be critical players inthe development of leukocyte response inmice earlyafter bur injury.Ou finding provides new insights into the pathogenesis ofleukocyteresponseto burn injuryandidentifies several potential biomarkers for burn treatment.

Key words: post-burn injury; stimulus response; gene microarray; protein-protein interaction network

烧伤，尤其是大面积烧伤将引起机体发生一系列的免疫学及病理生理学变化，造成机体免疫功能紊乱[]。

目前对于烧伤免疫方面的研究多是对免疫细胞、免疫因子的作用机制或感染、器官损伤等方面的研究2，这些研究或多或少的揭示了部分烧伤后免疫功能紊乱的发生机制，但在后基因组时代，从单一的基因及因子的研究出发时很难解释整个细胞或系统的变化。2010年Evers等3就已经提出基因芯片从细胞整体基因组水平出发，能为烧伤后免疫紊乱机制的研究提供新的思路及

治疗靶点。

本课题组在前期通过对GEO(Gene ExpressionOmnibus)数据库中一组小鼠烧伤后白细胞基因芯片的数据进行分析发现烧伤后小鼠白细胞表现为免疫系统过程、细胞过程、代谢过程、应对刺激反应等方面的紊乱，并针对免疫系统变化过程深人分析发现Lck、Ccr2、Tlr2及Myd88等基因在烧伤后免疫系统功能变化过程中起到重要作用[4。而对于烧伤后免疫细胞应对烧伤刺激反应过程的变化机制尚未研究。为此本实验应用小鼠烧伤后免疫细胞基因芯片数据来了解烧伤后应对刺激反应的基因表达变化及其生物学特性，旨在阐述烧伤后免疫细胞应对刺激变化过程的分子机制，为临床上烧伤早期诊断及治疗靶点的筛选提供新方向。

# 1材料与方法

# 1.1实验动物与材料

健康成年的雄性BALB/C小鼠180只，体质量 $2 0 \sim$ $2 2 \ \mathrm { g }$ ，由南方医科大学实验中心提供（许可证编号：SCXK粤2011-0015),清洁级饲养。本研究所使用小鼠外周血白细胞分离液试剂盒(细胞培养及分子生物学专用)购自天津市灏洋生物制品科技有限责任公司，柱式法TotalRNA提取试剂盒(TaKaRaMiniBESTUniversalRNAExtractionKit）、反转录试剂盒(PrimeScriptTMRTreagentKitwithgDNAEraser,Takara）、SYBR法Q-PCR试剂盒(SYBRPremixExTaqTM,Takara)购自广州瑞真生物技术有限公司。本研究所使用仪器主要有GeneAmpPCRSystem9700扩增仪及罗氏480荧光定量PCR仪。

# 1.2基因芯片数据处理及分析

本研究所用的 $\mathrm { G S E 7 4 0 4 ^ { [ 5 ] } }$ （小鼠， $2 5 \%$ TBSA,全层烧伤)数据集来源于NCBI的GEO 数据库(http://www.ncbi.nlm.nih.gov/geo/）,是 GPL1261平台 AffymetrixMouseGenome4302.0Array基因芯片，为全血游离白细胞基因芯片数据。我们从中选取烧伤后1d组样本进行分析，共有8个样本，其中4个为烧伤组，4个为对照组。原始数据进行RMA(robustmultiarrayaverage)背景矫正，四分位数法进行归一化处理，并对数据进行汇总以获取表达水平数据[67]。最后采用配对样本t检验和倍比法[8(FC)获取差异表达基因，差异基因需同时满足以下条件： $\textcircled { 1 } \textcircled { 1 }$ -value≤0.01; $\textcircled{2}$ logFC|>1。

# 1.3功能富集分析及刺激反应相关差异基因筛选

将差异基因输人到DAVID[9](Database forAnnotation，Visualization，and Integrated Discovery)(http://david.abcc.ncifcrf.gov/)网络数据库进行GeneOntology（GO）[10]分析,应用EASE(Expression AnalysisSystemicExplorer)方法选取 $\mathrm { E A S E } { < } 0 . 1$ 注释基因条目。并选取刺激反应相关差异基因并进行KEGG通路富集分析，选取与烧伤后免疫细胞刺激反应相关通路。

# 1.4刺激反应相关基因蛋白互作网络构建及分析

将选取的免疫系统相关差异基因应用DAVID进行基因ID转换,将转换的差异基因输入到STRING9.1[1]数据库中，选取交互作用评分大于0.4(中等可信度)的互作关系构建刺激反应相关差异基因的蛋白互作网络(Protein-protein interaction network）。网络分析及MCL子网络聚类分析采用生物图表可视化工具Cytoscape软件进行。

# 1.5动物模型建立及分组

假烫伤组(Sham)36只， $2 5 \%$ IⅢ°烫伤组[13]144只。随机选取烫伤组烫伤后 $2 . 6 , 1 2 . 2 4 \mathrm { h }$ 及假烫伤组分别12只小鼠，腹腔麻醉后，开胸心尖取血，血液行肝素抗凝处理后，立即行白细胞提取。

# 1.6小鼠白细胞总RNA的提取及浓度、纯度的检测

小鼠白细胞总RNA的提取按照柱式法TotalRNA提取试剂盒使用说明书进行操作，并用琼脂糖凝胶电泳判断RNA有无降解，以及用微量核酸定量仪检测所提取RNA的浓度和纯度，RNA的 $\mathrm { A } _ { 2 6 0 / 2 8 0 }$ 吸光值比率在1.8\~2.1范围内者方可进行后续实验。

# 1.7小鼠白细胞mRNA表达水平分析

反转录合成cDNA反应使用反转录试剂盒在PCR扩增仪上操作，cDNA合成后避光保存于 $- 2 0 \ \mathrm { { ^ circ C } }$ 冰箱。荧光定量PCR反应使用SYBR法Q-PCR试剂盒在罗氏480荧光定量PCR仪上操作。Lck、Stat1、Myd88、Stat3、Jun基因和MM-GAPDH内参基因的引物序列（上海英潍捷基贸易公司合成)见表1。最后采用 $2 ^ { - \Delta \Delta \mathrm { c t } }$ 方法[14]计算基因相对表达值。

# 1.8统计学方法

本实验采用SPSS19.0软件进行统计学分析。数

表1实时荧光定量PCR引物 Tab.1 Primers for real-time PCR   

<html><body><table><tr><td>Target Gene</td><td>Primer sequences(5'-→3')</td></tr><tr><td>Stat-1</td><td>Forward primer:TACGGAAAAGCAAGCGTAATCT Reverse primer:TGCACATGACTTGATCCTTCAC</td></tr><tr><td>Lck</td><td>Forward primer: TGGAGAACATTGACGTGTGTG Reverse primer:ATCCCTCATAGGTGACCAGTG</td></tr><tr><td>Myd88</td><td>Forward primer:GGAGTCCGAGAAGCCTTTACAG</td></tr><tr><td rowspan="2">Stat-3</td><td>Reverse primer:GGTCGGACACACACAACTTAAG</td></tr><tr><td>Forward primer:ACCTCCAGGACGACTTTGAT</td></tr><tr><td rowspan="2">Jun</td><td>Reverse primer:TGTCTTCTGCACGTACTCCA</td></tr><tr><td>Forward primer:CTTCTACGACGATGCCCTCAA</td></tr><tr><td rowspan="2">MM-GAPDH</td><td>Reverse primer:GGAAGCGTGTTCTGGCTATGC</td></tr><tr><td>Forward primer:AGGATGTGAAGGATGGGAAG Reverseprimer:TTCTTCAGCCTCTCCAGGTC</td></tr></table></body></html>

据以均数 $\trianglerighteq$ 标准差表示，各组间比较采用单因素方差分析，检验水准 $\mathrm { \dot { \alpha } = 0 . 0 5 }$ $P { < } 0 . 0 5$ 为有统计学意义

# 2结果

# 2.1基因芯片分析结果

在烧伤后第1天差异基因进行基因本体分析(GO分析)显示，共有259个刺激反应相关差异基因被选出，其中上调基因118个，下调基因141个。通过KEGG通路富集结果显示前10个通路符合阈值要求并被显著富集(表2)。主要为免疫系统相关通路(tol样受体信号通路；B细胞受体信号通路;T细胞受体信号通路等);细胞过程中的细胞生长与死亡相关通路(p53信号通路;细胞凋亡通路);环境信息进程中的信号转导相关通路。其中差异基因富集最多、最显著的为toll样受体信号通路，在烧伤后第1天中，差异基因在通路中的富集情况（图2）。

表2差异表达基因富集KEGG通路结果 Tab.2 Results of KEGG pathway enrichment analysis for the interacting genes   
  

<html><body><table><tr><td>Term</td><td>Pathway</td><td>Count</td><td>%</td><td>P</td><td>Class</td></tr><tr><td>mmu04620</td><td>Toll-like receptor signaling pathway</td><td>18</td><td>6.94</td><td>1.30E-10</td><td>Immune system</td></tr><tr><td>mmu04115</td><td>p53 signaling pathway</td><td>12</td><td>4.63</td><td>6.22E-07</td><td>Cell growth and death</td></tr><tr><td>mmu04612</td><td>Antigen processing and presentation</td><td>13</td><td>5.01</td><td>1.56E-06</td><td>Immune system</td></tr><tr><td>mmu04662</td><td>B cell receptor signaling pathway</td><td>12</td><td>4.63</td><td>2.85E-06</td><td>Immune system</td></tr><tr><td>mmu04660</td><td>T cell receptor signaling pathway</td><td>14</td><td>5.41</td><td>4.45E-06</td><td>Immune system</td></tr><tr><td>mmu04210</td><td>Apoptosis</td><td>11</td><td>4.24</td><td>4.10E-05</td><td>Cell growth and death</td></tr><tr><td>mmu04060</td><td>Cytokine-cytokine receptor interaction</td><td>18</td><td>6.94</td><td>7.25E-05</td><td>Signaling molecules and interaction</td></tr><tr><td>mmu04062</td><td>Chemokine signaling pathway</td><td>15</td><td>5.79</td><td>1.15E-04</td><td>Immune system</td></tr><tr><td>mmu05340</td><td>Primary immunodeficiency</td><td>7</td><td>2.71</td><td>1.94E-04</td><td>Immune diseases</td></tr><tr><td>mmu05320</td><td>Autoimmune thyroid disease</td><td>9</td><td>3.47</td><td>3.14E-04</td><td>Immune diseases</td></tr></table></body></html>

![](images/25bcfb36e125f5bb403812fd0efeb9535688624e42476f89e6e8c43277412d9e.jpg)  
图1差异基因在Toll样受体信号通路中的富集情况。红色代表刺激反应上调基因，蓝色代表刺激反应下调基因 Fig.1KEGGpathwaymapoftheTollikereceptorsignalingpathway.Thegridwiththeroundededgerepresentsanotherpathway. Blue-marked nodes are associated with downregulated genes andred-marked nodes with upregulated genes.The green nodes have no specific significance.

# 2.2 刺激反应相关蛋白互作网络分析

刺激反应相关蛋白互作网络共有226个节点，1232

条边组成(图2)。其中前10个具有最高互作关系的基因，如表3所示。MCL分析总共有7个子网络被选出，

如图3所示。通过蛋白互作网络分析显示：Lck、Stat1、Myd88、Stat3和Jun5个基因同时具有最大互作关系和在子网络中处于中心位置。

![](images/f795d58242cc66b909cf524666086de87ea2209a2d42721ed5f1b6e638a6c695.jpg)  
图2刺激反应相关蛋白互作网络 Fig.2 Interaction network of the genes involved in the stimulusresponse.Reddotsrepresent genes upregulatdandbluedotsrepresent genes downregulated.The edges represent interaction.

# 2.3RT-PCR方法验证结果

通过RT-PCR技术检测小鼠烧伤后白细胞中Lck、Stat1、Myd88、Stat3和JunmRNA的表达情况（图4）。Lck基因表达量在烧伤后 $1 2 \mathrm { h }$ 处于较低水平，在 $2 4 \mathrm { h }$ 内较sham组整体表达下降(图4A)。Stat1基因表达量在$2 4 \mathrm { h }$ 内表现出逐渐下降趋势(图4B)。而Myd88、Stat3和Jnu基因表达量在烧伤后 $2 4 \mathrm { ~ h ~ }$ 内皆较 sham明显增加。因此实时荧光定量PCR技术检测显示Lck、Stat1、Myd88、Stat3和Jun基因表达情况与芯片数据分析结果相一致。

# 3讨论

基因芯片技术自发明至今已被应用到生物科学众多的领域之中。基因芯片技术和生物信息学分析方法为从转录水平或DNA层面全面了解烧伤后复杂的病理生理学变化过程提供了可能。在本研究中，在烧伤后第1天差异基因进行基因本体分析(GO分析)显示，共有259个刺激反应相关差异基因被选出，其中上调基因118个，下调基因141个。KEGG通路富集结果显示刺激反应相关差异基因主要与免疫系统、细胞生长与死亡及信号转导等通路相关。通过蛋白互作网络分析显示：Lck、Stat1、Myd88、Stat3和Jun基因同时具有最大互作关系和在子网络中处于中心位置。我们通过动物实验也证明了Lck、Stat1、Myd88、Stat3和Jun基因表达情况与数据分析结果相一致。

表3免疫基因互作网络中互作关系最高的前10个差异基因Tab.3 Top 10 interacting genes in the PPI network  

<html><body><table><tr><td>Gene</td><td>Degree</td><td>Regulation</td><td>Official Full Name</td></tr><tr><td>Jun</td><td>67</td><td>Up</td><td>Jun oncogene</td></tr><tr><td>Stat1</td><td>67</td><td>Down</td><td>signal transducer and activator of transcription 1</td></tr><tr><td>Bcl2</td><td>56</td><td>Down</td><td>B cell leukemia/lymphoma 2</td></tr><tr><td>Stat3</td><td>54</td><td>Up</td><td>signal transducer and activator of transcription 3</td></tr><tr><td>Tlr2</td><td>47</td><td>Up</td><td>toll-like receptor 2</td></tr><tr><td>Myd88</td><td>45</td><td>Up</td><td>myeloid differentiation primary response gene 88</td></tr><tr><td>Jak2</td><td>41</td><td>Up</td><td>Janus kinase 2</td></tr><tr><td>Lck</td><td>40</td><td>Down</td><td>lymphocyte protein tyrosine kinase</td></tr><tr><td>Hck</td><td>38</td><td>Down</td><td>hemopoietic cell kinase</td></tr><tr><td>Ptpn6</td><td>38</td><td>Down</td><td>protein tyrosine phosphatase,non-receptor type 6</td></tr></table></body></html>

Lck基因编码所产生p56(Lck)，是非受体酪氨酸蛋白激酶致癌基因家族成员之一。Lck激酶相对特异地存在于淋巴细胞中，特别是成熟静止的T淋巴细胞，在T细胞活化信号转导及分化调节中起到重要作用[15]。P56(Lck)蛋白锚定到细胞膜并与CD4/CD8共同受体的胞内结构域相互作用,并具有酪氨酸激酶活性[16-17]。Lck激酶参与了IL-2信号转导途径，调节T细胞的增殖。在胸腺细胞中，Lck激酶磷酸化ZAP-70激酶，促进下游信号转导分子的募集,以致影响细胞的增殖和分化[18]。研究表明，选择性抑制Lck激酶可以为T细胞介导的自身免疫性疾病、炎症性疾病及器官移植排斥反应提供治疗[19]。而有文献报道，烧伤后适应性免疫应答的变化主要有T淋巴细胞的增殖能力和其分泌IL-2免疫刺激性因子的功能长时间受抑制，并伴随有T淋巴细胞总数以及CD4/CD8比值降低[20]。本研究结果表明Lck基因在烫伤后 $2 4 \mathrm { h }$ 表达量持续减少，与其功能相结合正支持上述理论，也揭示了Lck在烧伤后刺激反应所致免疫应答中

![](images/9f89d795dde952430d6f079d184128eb2d0a09dabdd3eb80f1735d704752082a.jpg)

![](images/bee3c7389dbb022fc375961e95f16e1d58d15e20833159cf8f7403fb575a49a5.jpg)  
图3MCL网络分析子网络图 Fig.3ClustersA-Jand thesubnetworks inPPI network.Red nodes represent gens upregulatdand blue nodes representgenes downregulated.

![](images/8751686d458e84e4cffdaf7a3e018a9112e5cab8c4e53f9a7c212e92953ea123.jpg)  
图4Lck、Stat1、Myd88、Stat3和Jun 基因在烧伤后24h表达水平Fig.4 Lck, Stat1,Myd88,Stat3 and Jun mRNAexpression changes in mice at $2 4 \mathrm { ~ h ~ }$ post-burn.$^ { * } P { < } 0 . 0 1$ $^ { * * } P { < } 0 . 0 5$ Us sham group.

发挥了重要作用。

信号传导与转录激活因子(STAT)蛋白家族是一组可以被不同的细胞因子受体激活的相关蛋白，在细胞因子-受体相互作用的过程中充当载体，保持信号在细胞内传递的内在特异性[2]。有关研究发现STAT蛋白家族中，STAT1和STAT3在免疫反应过程中发挥重要功能。STAT1活化促进INF-α/β/y的表达,上调MHC-I和ⅡI类分子、共刺激分子和趋化分子表达，促进DC成熟分化[23]。并激活巨噬细胞、NK细胞、肿瘤特异性CTL反应杀伤肿瘤细胞[24]。促进向Thl型细胞分化和促进促炎症性细胞因子产生[25]。然而，STAT3在免疫反应中所起的作用与STAT1恰恰相反[26]。作为免疫系统负调节蛋白的STAT3，诱导免疫抑制因子TGF- $\cdot \beta$ 、IL-10等的表达，通过下调MHC-I类分子、MHC-II类分子、CD80、CD86和IL-12的水平，抑制噬中性粒细胞、NK细胞、DC细胞的活性，从而抑制免疫系统的活性[27]。本实验结果示在烧伤后24hSTAT1基因表达量持续减少，而STAT3基因表达量增加，这反应了在烧伤早期机体已出现免疫功能抑制，从而导致临床上烧伤早期患者免疫功能低下易感染及死亡。

Myd88(髓样分化因子88)分子发现于髓样细胞的分化中，作为衔接蛋白在机体固有免疫应答反应中能直接参与到Toll样受体信号转导通路中。Toll样受体不仅是固有免疫系统识别病原相关分子模式的主要受体，而且其启动的信号通路还能调控适应性免疫应答[28]。Myd88通过启动IRAK-1、IRAK-4和TRAF6等作用快速激活MAPK和NF- $\mathbf { \sigma } _ { \cdot \kappa \mathbf { B } }$ 传导途径来调控IL-1、IL-6和TNF- $\mathbf { \alpha } \cdot \mathbf { a }$ 等炎症因子的转录[29-31]。因此,Myd88作为重要的转导蛋白，不仅在信号途径中发挥着关键作用，还通过调控细胞因子的分泌影响适应性免疫应答。本研究显示烧伤后24hMyd88表达量的升高，这也说明烧伤早期Myd88通过多种机制参与应对刺激反应的免疫应答过程，从而维持内环境的稳定。因此若能研究出新药在分子水平调控Myd88,相信在烧伤早期对病人的治疗上会有新的方法。

Jun基因是转录因子AP-1家族成员之一，Fos蛋白与Jun蛋白在细胞核内通过亮氨酸拉链结构形成异源二聚体复合物-转录因子AP-1,以高亲和力在靶基因的AP-1位点，进一步激活靶基因的表达而最终对刺激做出反应[32]。Jun在绝大多数细胞中呈极低水平表达，参与细胞生长、繁殖、分化等生理过程[33]。而病理条件下，Jun的过度表达及调控变化可能与多种疾病及机体损伤有关[34]。有相关研究发现,Jun在中枢神经系统的表达与伤害性感觉或痛觉有关，Jun可作为中枢神经系统对伤害性刺激反应的标志[35]。因此,本实验结果显示烧伤早期Jun基因表达上调可能与烧伤刺激有关。

综上所述,小鼠烧伤后第1天全血游离白细胞Lck、Stat1、Myd88、Stat3和Jun基因在烧伤早期刺激反应过程中发挥着重要的作用。本研究所筛选出来差异表达基因从分子水平为我们探讨烧伤早期刺激反应机制提供理论依据，为临床上烧伤早期诊断及治疗靶点的筛选提供了新方向。我们会对烧伤后期刺激反应进行进一步研究，探索机体从烧伤至完全恢复全过程差异表达基因的表达情况，为更全面探索烧伤刺激反应机制及临床烧伤诊治提供新的方向。

# 参考文献：

[1]Oppeltz RF, Rani M, Zhang Q,et al. Burn-induced alterations in toll-like receptor-mediated responses by bronchoalveolar lavage cells[J].Cytokine,2011,55(3): 396-401.   
[2]Gardner JC,Noel JG,Nikolaidis NM,et al.G-CSF drives a posttraumatic immune program that protects the host from infection [J].JImmunol,2014,192(5): 2405-17.   
[3]Evers LH,Bhavsar D, Mailander P.The biology of burn injury[J]. Exp Dermatol,2010,19(9): 777-83.   
[4]高艳彬,卢志阳,金 辉,等.小鼠烧伤后时序芯片数据分析及免疫标志 物的初步筛选[J].暨南大学学报:自然科学与医学版,2015(3): 275-81.   
[5]Lederer JA,Brownstein BH,Lopez MC,et al. Comparison of longitudinal leukocyte gene expression after burn injuryor trauma-hemorrhage in mice [J].Physiol Genomics,2008,32(3): 299-310.   
[6]Irizarry RA,Hobbs B,Colin F,et al.Exploration,normalization, and summaries of high density oligonucleotide array probe level data[J]. Biostatistics,2003,4(2): 249-64.   
[7]Gao L,Gao H, Zhou H,et al. Gene expression profiling analysis of the putamen for the investigation of compensatory mechanisms in Parkinson's disease[J].BMC Neurol,2013,13(1):181.   
[8]Mutch DM, Berger A, Mansourian R,et al. The limit fold change model:a practical approach for selecting differentially expressed genes from microarray data[J].BMC Bioinformatics,2002,3(1): 17.   
[9] Huang DW, Sherman BT, Lempicki RA. Systematic and integrative analysis of large gene lists using David bioinformatics resources[J]. Nat Protoc,2009,4(1): 44-57.   
[10]Ashburner M,Ball CA,Blake JA,et al.Gene ontology: tool for the unification of biology. The Gene Ontology Consortium[J].Nat Genet,2000,25(1): 25-9.   
[11]Franceschini A, Szklarczyk D,Frankild S,et al.STRING v9.1: protein-protein interaction networks,with increased coverage and integration [J]. Nucleic Acids Res，2013，41(Database issue): D808-15.   
[12] Shannon P,Markiel A,Ozier O,et al.Cytoscape:a software environment for integrated models of biomolecular interaction networks[J]. Genome Res,2003,13(11): 2498-504.   
[13]刘 毅,薛晓东,贾赤宇,等.恒温恒压电烫仪建立小鼠烫伤模型的实验 研究[J].兰州医学院学报,2001(1):6-8.   
[14] Livak KJ, Schmitgen TD.Analysis of relative gene expression data using real-time quantitative PCR and the 2(-Delta Delta C(T)) Method[J].Methods,2001,25(4): 402-8.   
[15]Straus DB,Weiss A.Genetic evidence for the involvement of the lck tyrosine kinase in signal transduction through the T cell antigen receptor[J].Cell,1992,70(4): 585-93.   
[16]Nika K,Soldani C,Salek M,et al. Constitutively active Lck kinase in T cells drives antigen receptor signal transduction[J]. Immunity, 2010,32(6): 766-77.   
[17]Gascoigne NR,Palmer E. Signaling in thymic selection[J].Curr Opin Immunol, 2011,23(2): 207-12.   
[18]Hermiston ML,Xu Z,Majeti R,et al.Reciprocal regulation of lymphocyte activation by tyrosine kinases and phosphatases[J].J Clin Invest,2002,109(1): 9-14.   
[19]Martin MW,Machacek MR.Update on lymphocyte specific kinase inhibitors:a patent survey[J].Expert Opin Ther Pat, 2O1O,20(11): 1573-93.   
[20]彭代智.我国烧伤免疫的研究[J].中华烧伤杂志,2008,24(5):390-2.   
[21] Lim C P, Cao X. Structure,function,and regulation of STAT proteins [J].Molecular Biosystems,2006,2(11) : 83.   
[22] Jackson SH, Yu CR,Mahdi RM,et al. Dendritic cell maturation requires STAT1 and is under feedback regulation by suppressors of cytokine signaling[J].JImmunol, 2004,172(4): 2307-15.   
[23]Vakkila J,Demarco RA,Lotze MT. Coordinate NF-kappaB and STAT1 activation promotes development of myeloid type 1 dendritic cells[J]. Scand JImmunol, 2008,67(3): 260-9.   
[24]Carson WE,Dierksheide JE,Jabbour S,et al. Coadministration of interleukin-18 and interleukin-12 induces a fatal inflammatory response in mice: critical role of natural killer cell interferongamma production and STAT-mediated signal transduction [J]. Blood,2000,96(4): 1465-73.   
[25]Dunn GP,Koebel CM,Schreiber RD.Interferons,immunity and cancer immunoediting[J].Nat Rev Immunol, 20o6,6(11): 836-48.   
[26]Hong F, Jaruga B,Kim WH,et al. Opposing roles of STAT1 and STAT3 in T cell-mediated hepatitis: regulation by SOCs[J].J Clin Invest,2002,110(10):1503-13.   
[27]Yu H, Kortylewski M,Pardoll D.Crosstalk between cancer and immune cells: role of STAT3 in the tumour microenvironment[J]. Nat Rev Immunol,2007,7(1): 41-51.   
[28]常晓彤,辇晓峰,王振辉.Toll样受体信号转导途径研究进展[J].生理 科学进展,2011(5):340-6.   
[29]Li X,Qin J.Modulation of toll-interleukin 1 receptor mediated signaling[J].JMol Med (Berl),2005,83(4): 258-66.   
[30]Motshwene PG，Moncrieffe MC，Grossmann JG，et al．An oligomeric signaling platform formed by the Toll-like receptor signal transducers MyD88 and IRAK-4[J].JBiol Chem,2009,284 (37): 25404-11.   
[31]Konno H,Yamamoto T,Yamazaki K,et al. TRAF6 establishes innate immune responses by activating NF-kappaB and IRF7 upon sensing cytosolic viral RNA and DNA[J].PLoS One,2009,4(5): e5674.   
[32]Angel P,Karin M. The role of Jun,Fos and the AP-1 complex in cell-proliferation and transformation[J].Biochim Biophys Acta, 1991,1072(2/3): 129-57.   
[33]Macara IG. Oncogenes and cellular signal transduction[J]. Physiol Rev,1989,69(3): 797-820.   
[34]Jorgensen MB，Deckert J，Wright DC，et al.Delayed c-fos proto-oncogene expression in the rat hippocampus induced by transient global cerebral ischemia:an in situ hybridization study[J]. Brain Res,1989,484(1/2): 393-8.   
[35]冯 雪,段银钟,林 珠,等.大鼠实验性牙齿移动诱导中枢立即早期基 因c-fos和c-jun的表达与调节[J].中华口腔医学杂志,2000(4):65.

(编辑：孙昌朋)

# （上接1764页）

embryos were monitored by Time-lapse imaging[J].JAssist Reprod Genet,2011,28(7): 569-73.   
[10]Kirkegaard K,Hindkjaer JJ,Grondahl ML,et al.A randomized clinical trial comparing embryo culture in a conventional incubator with a Time-lapse incubator[J].JAssist Reprod Genet,2012,29(6): 565-72.   
[11]Rubio I, Galan A,Larreategui Z,et al. Clinical validation of embryo culture and selection by morphokinetic analysis:a randomized, controlled trial of the EmbryoScope[J].Fertil Steril,2014,102(5): 1287-1294.e5.   
[12]Siristatidis C,Komitopoulou MA,Makris A,et al. Morphokinetic parameters of early embryo development via Time lapse monitoring and their effect on embryo selection and ICSI outcomes:a prospective cohort study[J].J Assist Reprod Genet,2015,32(4): 563-70.   
[13]De Mouzon J,Goossens V,Bhattacharya S,et al.Assisted reproductive technology in Europe，2Oo6:resultsgenerated from European registers by ESHRE [J].Hum Reprod,2010,25(8): 1851-62.   
[14]Mantzouratou A,Mania A,Fragouli E,et al.Variable aneuploidy mechanisms in embryos from couples with poor reproductive histories undergoing preimplantation genetic screening[J].Hum Reprod,2007,22(7): 1844-53.   
[15] Chawla M,Fakih M, Shunnar A,et al.Morphokinetic analysis of cleavage stage embryos and its relationship to aneuploidy in a retrospective Time-lapse imaging study[J].JAssist Reprod Genet, 2015,32(1): 69-75.   
[16]Kramer YG,Kofinas JD,Melzer K,et al.Assessing morphokinetic parameters via Time lapse microscopy(TLM) to predict euploidy: are aneuploidy risk classification models Universal[J].J Assist Reprod Genet,2014,31(9): 1231-42.   
[17]Campbell A,Fishel S,Bowman N,et al. Retrospective analysis of outcomes after IVF using an aneuploidy risk model derived from Time-lapse imaging without PGS[J]. Reprod Biomed Online,2013, 27(2): 140-6.

（编辑：孙昌朋）