# 龙眼DIPSY基因在根和叶中的表达及其生物信息学分析

郑威l\*，孙文文¹，董学明'，张秋颖’，于雪飞²，陈宁1(1. 哈尔滨商业大学 药学院，哈尔滨150076；2.哈尔滨商业大学图书馆，哈尔滨150028）

摘要：为研究八氢番茄红素合成酶（Phytoene Synthase）基因在龙眼类胡萝卜素合成途径中的作用机制，我们从龙眼转录组数据中筛选获得一个PSY基因，命名为DIPSY，采用生物信息学方法对龙眼 PSY蛋白的一级结构、理化性质、信号肽、跨膜结构、亚细胞定位、亲疏水性、蛋白质二级结构、蛋白质三级结构、卷曲螺旋域、蛋白质结合位点、系统进化树、蛋白质互作等进行分析和预测；同时运用实时荧光定量PCR(qRT-PCR)技术对DIPSY基因在龙眼根和叶中的差异表达进行分析。实验结果表明：龙眼DIPSY基因长度为 $1 2 6 0 \mathrm { b p }$ ，编码420个氨基酸；生物信息学预测 DIPSY 蛋白具有 Isoprenoid Biosyn C1超家族结构，含有信号肽，为分泌性蛋白，无跨膜结构，是一种可溶性亲水蛋白，定位于膜外；DIPSY蛋白的二级结构主要由α-螺旋和无规则卷曲组成，具有卷曲螺旋。Ramachandran 评估结果表明应用 SWISS-MODEL 构建的蛋白质三级结构模型可靠，其配体结合位点为344Phe 和347Lys。qRT-PCR分析结果表明 DIPSY基因在龙眼根和叶中均有表达，叶中表达量高于其在根中的表达量。该研究的结果为下一步采用遗传学方法提高龙眼中类胡萝卜素的含量奠定理论基础。

关键词：龙眼，PSY基因，生物信息学，基因表达中图分类号： 文献标志码：A 文章编号：

# Expression of DlPSY Gene in roots and leaves of Dimocarpus longan Lour and its Bioinformatics Analysis

ZHENG Weil\*， SUN Wen-wen1， DONG Xue-ming1， ZHANG Qiu-ying1, YU Xue-fei²，CHEN Ning1 (1. School of Pharmacy, Harbin University of Commerce, Harbin 150076; 2.Library, Harbin University of Commerce,Harbin 150028) stract: To study the function of phytoene synthase gene in carotenoid synthesis of $D$ .longan, a

DlPSY gene identified from $D$ . longan RNA-seq data was screened and analyzed in this research by bioinformatics methods including the primary structure of protein, physicochemical properties, signal peptide, transmembrane region, subcellular localization, hydrophilicity, protein secondary structure and tertiary structure, coiled coil domain, protein binding site, phylogenetic tree, as well as protein-protein interaction. In addition,the real-time quantitative PCR (qRT-PCR) was applied in this research to analyze the expression pattern of DlPSY gene in root and leaf tissues. The bioinformatics software used in this research included NCBI BLAST,DNAMAN,NCBI CD search，Protparam， SignalP4.1Server，TMHMM Server， SOSUI， PSORT， ProtScale， SOPMA, COILS, SWISS-MODEL,MolProbity,3DLigandSite,and STRING. The bioinformatics analysis results showed that the length of the DlPSY gene was $1 2 6 0 ~ \mathrm { b p }$ , coding for 420 amino acids; the DIPSY protein was predicted to have ‘Isoprenoid Biosyn C1' superfamily structure; it contained a signal peptide; the DlPSY protein did not contain the transmembrane structure; it was a soluble hydrophilic and secretory protein which was predicted to be located outside the membrane; the DIPSY protein secondary structure was predicted to be mainly composed of $\mathfrak { a }$ -helix and random coil; the DlPSY protein was predicted to have a coiled helix; the Ramachandran evaluation results showed that the tertiary structure model constructed by SWISS-MODEL was reliable,and its ligand binding sites were 344Phe and 347Lys,respectively. In addition, the expression pattern of the DlPSY gene was analyzed by qRT-PCR, the results of which showed that the DlPSY gene was expressed in roots and leaves of D.longan but with the different expression levels.The expression level of DlPSY gene was higher in leaf tissue than that in root tissue.The results of this study wil enrich our knowledge on PSY gene family and also lay a foundation for further improving the carotenoid content in $D$ . longan by genetic methods.

Keywords: Dimocarpus longan Lour.， DlPSY， bioinformatics， gene expression

龙眼（Dimocarpus longan Lour.），又名桂圆、益智，味甘、淡，性平，属于无患子科常青果树，具有清热解毒之功效（黄春燕等，2019）。龙眼原产于我国南方，是主要的栽培水果之一，但在泰国、印度和越南等地也有广泛的种植（Jiang et al.,2002；Campbell&Campbell,2001）。龙眼中含有丰富的膳食纤维、维生素、蛋白质、多糖和矿物质等（Chaikham& Prangthip，2015），对人体的健康十分有益，可以清除自由基，降低血糖，调节免疫系统、神经系统和内分泌系统等（Lietal.，2015；Jiang etal.，2014）。龙眼中也含有多种次生代谢产物，如酚酸、类黄酮和类胡萝卜素等，具有抗氧化、抗血清酶，抗突变、抗炎和抗癌等功效（Prasad et al.，2010；Rangkadilok et al.，2007）。

类胡萝卜素是高等植物中的一类重要的次生代谢产物，属烯萜类化合物，分子式为$\mathrm { C _ { 4 0 } H _ { 5 6 } }$ ，分为胡萝卜素和叶黄素两大类。类胡萝卜素主要存在于植物的叶绿体和色素体膜上，参与光合作用并保护组织不受光氧化损伤等重要功能(Robert etal.,2004; Sanae etal.,2018）。在高等植物中，类胡萝卜素可以使组织和器官等（如花和果实）呈现出鲜艳的颜色，如黄色、橙色和红色等，使植物可以吸引传粉者（Tian etal.，2018；Suzuki etal.，2007）。除此之外，类胡萝卜素还具有多种生物活性，如抗氧化，提高人体免疫力，对心血管疾病、某些肿瘤具有一定的预防和治疗作用（王庆伟，2000）。类胡萝卜素是由八个异戊二烯单位缩合而成的类异戊二烯化合物（Lietal.，1996）。迄今为止，已经报道了约有750种天然类胡萝卜素，它们在光捕获、光保护和信号传导等方面发挥重要的作用（Nisar etal.，2015；Gruszecki&Strzalka，2005）。萜类化合物的生物合成途径有甲基赤藓糖-4-磷酸（MEP）途径和甲羟戊酸（MVA）途径。在光照条件下，类胡萝卜素的合成途径以MEP为主（霍培等，2011）。该途径在很多植物中予以详细阐述（图1），其中类胡萝卜素合成的第一步是由八氢番茄红素合成酶（PSY）催化生成八氢番茄红素。PSY是类胡萝卜素生物合成途径中第一个关键酶，起限速作用（Zhang＆Dubcovsky，2011）。大量研究表明PSY基因的表达水平影响植物中类胡萝卜素的积累（Shewmaker et al.，1999；Fray etal.，1995）。

龙眼在我国的种植面积广，资源丰富，其根、叶、花和种子等因含有类黄酮、萜类、多糖、酚酸等多种药用成分可作为药材使用，在我国已经有一百多年的应用历史(Thitiratsaku&Anprung，2014)。然而龙眼各组织中的药用成分含量较少，限制了龙眼作为中药材的应用范围及药用价值。本文对龙眼类胡萝卜素合成途径中关键的合成酶PSY蛋白进行全面的生物信息学分析，并运用qRT-PCR技术对该基因在龙眼根与叶中的表达进行研究，实验结果将丰富我们对植物PSY家族的认识，同时为今后采用遗传学手段提高龙眼类胡萝卜素的含量提供思路。

![](images/8ececa859612872d75b39571b24ae30df90481539d1103b0e06efb4b74e9ebb7.jpg)  
图1类胡萝卜素的生物合成途径（陈祥慧等，2018)

Fig.1Schematic diagram of the biosynthetic pathway of carotenoids (Chen et al., 2018

# 1材料与方法

# 1.1 材料

# 1.1.1 植物材料

将龙眼种子置于流水中冲洗48h 后播种于哈尔滨商业大学药学院植物培养室的塑胶花盆 $\langle 4 0 \mathrm { c m } \times 3 0 \mathrm { c m } \times 1 0 \mathrm { c m } \rangle$ 中，在恒温 $2 5 \mathrm { { ^ \circ C } }$ 、湿度 $50 \%$ 条件下培养一个月后，选择长势一致且发育良好的龙眼植株；先用清水冲洗龙眼植株的根系除去泥土，快速用吸水纸吸取根上水分，用RNAase-free小剪刀剪取龙眼根尖和幼叶，用锡纸包裹，迅速放入液氮中速冻后置于${ } . 8 0 \mathrm { { ^ { \circ } C } }$ 超低温冰箱中保存备用。

# 1.1.2实验仪器与试剂

主要仪器： $\mathrm { T } 1 0 0 ^ { \mathrm { T M } }$ Themal Cycler 型PCR仪（Bio-Rad，CA，USA），CT15RE 型高速低温离心机（HITACHI，Japan），GelDocTM $\mathrm { X R ^ { + } }$ 型凝胶成像系统（Bio-Rad，CA,，USA），Bio-RadCFX96型实时荧光定量PCR仪（Bio-Rad，CA，USA）。

主要试剂： $2 \times$ TransTaq High Fidelity (HiFi) PCR SuperMix II(Transgen，Beijing，China),TransStart Top Green qPCR SuperMix(TransGen， Beijing， China)， HiScript? I Q Select RTSuperMix for qPCR ( $^ +$ gDNA wiper)(Vazyme，Nanjing， China)。

1.2 方法  
1.2.1生物信息学分析

运用BLAST（https://last.ncbi.nlm.nih.gov/Blast.cgi）和 DNAMAN 进行序列检索比对；运用CD search（http://www.ncbi.nlm.nih.gov/Structure/cdd/wrpsb.cgi）预测保守结构域；运用Protparam（http://www.expasy.org/tools/protparam.html）分析蛋白理化性质；运用SignalP4.1Server（http://www.cbs.dtu.dk/services/SignalP）预测信号肽；运用 TMHMM Serverv.2.0（htp://www.cbs.dtu.dk/services/TMHMM/）预 测 跨 膜区；运 用 SOSUI（http://harrier.nagahama-i-bio.ac.jp/sosui/sosui_submit.html）进行可溶性蛋白预测；运用PSORT（htp://psort.hgc.jp）分析亚细胞定位；运用ProtScale（http://ca.expasy.org/tools/protscale.html）分析亲疏水性；运用SOPMA(https://npsa-prabi.ibcp.fr/cgi-bin/npsa_automat.pl?page $\ L =$ npsa_sopma.html）进行二级结构预测；运用 COILS（htp://www.ch.embnet.org/software/COILS_form.html）进行卷曲螺旋分析;运用 SWISS-MODEL（https://www.swissmodel.expasy.org/）三级结构建模；运用 MolProbity（http://molprobity.biochem.duke.edu）进行拉氏构象图分析；运用3DLigandSite(http://www.sbg.bio.ic.ac.uk $/ { \sim } 3$ dligandsite/）预测配体结合位点；运用STRING（https://string-db.org/）构建候选蛋白与相关蛋白的互作网络。

# 1.2.2龙眼总RNA 提取与cDNA合成

从 $. 8 0 ^ { \circ } \mathrm { C }$ 超低温冰箱中取出龙眼的根和叶，分别将其研磨成细粉状。取 $1 . 5 ~ \mathrm { m L }$ 离心管，将研磨好的细粉放入其中，加入 $7 0 0 { \mu \mathrm { L C T A B } }$ 裂解液，充分震荡混匀， $6 5 ~ \mathrm { { ^ \circ C } }$ 水浴 $1 0 \mathrm { m i n }$ ，每隔 $2 \mathrm { m i n }$ 摇晃一次，冰浴 $2 \mathrm { m i n }$ 。将离心管放入低温离心机， $4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ， $1 2 0 0 0 \mathrm { r / m i n }$ 离心 $2 \mathrm { m i n }$ 取上清液至新的 $1 . 5 \mathrm { m L }$ 离心管中，加入 $3 5 0 ~  { \mu \mathrm { L } }$ 水饱和酚和 $3 5 0 \mu \mathrm { L }$ 氯仿，抽提一次， $4 ^ { \circ } \mathrm { C }$ ，1$2 0 0 0 \mathrm { r / m i n }$ 离心 $2 \mathrm { m i n }$ ，重复一次；加入 $7 0 0 ~ \mu \mathrm { L }$ 氯仿提取一次， $1 2 0 0 0 \mathrm { r / m i n } 4 \mathrm { ~ \textbar { ~ C ~ } ~ }$ 离心 $2 \mathrm { m i n }$ ，重复一次；取上清，加入 $2 5 0 ~ \mu \mathrm { L }$ 无水乙醇和 $2 5 0 \mu \mathrm { L } 8 \mathrm { m o l / L } \mathrm { L i C }$ 1，冰上静置 $2 0 \mathrm { m i n }$ ， $4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ，$1 2 0 0 0 \mathrm { r / m i n }$ 离心 $2 0 \mathrm { m i n }$ ；弃上清， $7 5 \%$ 乙醇洗涤两次，风干 $5 \mathrm { m i n }$ ；加入 $3 0 ~ \mu \mathrm { L }$ DEPC，得到总 RNA。根据 Vazyme 公司 HiScript® II Q Select RT SuperMix for qPCR( $\mathrm { \Phi _ { \ t g D N A } }$ wiper)产品说明书进行逆转录，得到cDNA， $- 2 0 ^ { \circ } \mathrm { C }$ 保存于冰箱备用。

# 1.2.3DIPSY基因差异表达分析

根据DIPSY基因序列，设计qRT-PCR的上游和下游引物。上游引物：ACTGTGTCCGATAAGGCAGC，下游引物:AACGGCTTTAGACAGGTGGG。依据 TransStartTop GreenqPCRSuperMix 试剂盒说明书进行基因定量分析实验。反应体系 $( 2 0 ~ \mu \mathrm { L } )$ ：TransStart Top Green qPCR SuperMix $1 0 \mu \mathrm { L }$ ， $\mathrm { d d H } _ { 2 } \mathrm { O } 7 \mu \mathrm { L }$ ，上、下游引物各 $1 ~ \mu \mathrm { L }$ ，根和叶cDNA模板各 $1 ~ \mu \mathrm { L }$ 。qRT-PCR反应条件为预变性 $9 5 \mathrm { ^ \circ C }$ ，30s； $9 5 ^ { \circ } \mathrm { C }$ 变性30s， $6 0 ^ { \circ } \mathrm { C }$ 退火10s，延伸30s，扩增 40个循环。采用 $2 ^ { - \Delta \Delta C \mathrm { t } }$ 方法(Schmittgen& Livak，2008)计算 PSY基因相对表达量。

# 2结果与分析

# 2.1DIPSY一级结构和理化性质分析

应用 ExPASyProtParam 分析DIPSY 的氨基酸组成及理化性质。结果表明，DIPSY 蛋白由420个氨基酸组成（图2），其中Leu占比最大为 $10 . 2 \%$ ，His占比最小为 $0 . 5 \%$ ；DIPSY蛋白质的总原子数为6717，相对分子量为47593.70，420个氨基酸中有52个是负电荷氨基酸残基 $\mathrm { ( A s p + G l u ) }$ ，60个是正电荷氨基酸残基 $( { \mathrm { A r g } } { + } \mathrm { L y s } )$ ，其预测的理论等电点PI为8.95，呈碱性；在波长 $2 8 0 ~ \mathrm { n m }$ 下，假设所有半胱氨酸均来自胱氨酸，其DIPSY的消光系数为71195M-1cm-1，假设无半胱氨酸残基存在，其消光系数为 $\mathrm { 7 0 8 2 0 M - l ~ c m - l }$ ；DIPSY的不稳定系数为53.51，预测该蛋白为不稳定蛋白；脂肪系数为90.81；DIPSY的总平均亲水性为-0.260，预测DIPSY为亲水蛋白。

1 MSVALLWVVLPNSQLSNCFG   
61 TTTATTGATTCGGTTAGCGATGGAAACCGGCTGATATATTCATCAAGATTGGTGAGGCGG   
21 FIDSVSDGNRLIYSSRLνRR   
121 AATAGGAGTTCCACGTTTGATTGTAGAGGAAAGATTAAAGATAGGAAGCAGAAACGGTAT   
41 N RSSTFDCRGKIKDRKQKRY   
181 GCTTGCTCGATCAACGTCCCTGAAATATCGAGTCTGGTGGCAAGCACGGCTGATGAGCTA   
61 ACSINνPEISSLνASTADEL   
241 GCCGTGTCTTCAGAAGAAAAGGTTTACAATGTGGTGCTGAAGCAGGCAGCTTTGATTAAG   
81 AVSSEEKVYNVνLKQAALIK   
301 GAGCAGTGGAGGTCCAGTCCGGATCTTGATGTGAATCCGGATGTTGTTTTGCCAGGAAAT   
101 EQWRSSPDLDVNPDVVLPGN   
361 TTGGGCTTGTTGAGTGAAGCTTATGAACGGTGTGGAGAAGTATGCGCGGAGTATGCCAAG   
121 LGLLSEAYERCGEVCAEYAK   
421 ACATTCTACTTGGGAACTCTGCTAATGACCCCGGAAAGACGAAAAGCTATATGGGCGATA   
141 TFYLGTLLMTPERRKAIWAI   
481 TATGTGTGGTGTAGGAGAACAGATGAGCTTGTTGATGGACCTAATGCTTCACACATAACT   
161 YVWCRRTDELVDGPNASHIT   
541 CCAACGGCTTTAGACAGGTGGGAGTCCAGGTTGGAAGATCTTTTCCAGGGTCGTCCATAT   
181 PTALDRWESRLEDLFQGRPY   
601 GATATGTTTGATGCTGCCTTATCGGACACAGTAGCCAAGTATCATGTCGACATTCAACCA   
201 DMFDAALSDTνAKYHVDIQP   
661 TTCAGAGATATGATTGAAGGAATGAGGATGGATCTTAGGAAGTCAAGATATAAAAACTTT   
221 FRDMIEGMRMDL RKSRYKNF   
721 GATGAACTATACCTCTATTGTTATAATGTGGCTGGGACAGTTGGACTAATGAGCGTTCCA   
241 DELYLYCYNνAGTνGLMSνP   
781 GTCATGGGCATTGCCCCTGAATCAAAGGCATCCCCTGTGAGCATTTTCGATGCTGCACTG   
261 VMGIAPESKASPVSIFDAAL   
841 GCATTAGGAATCGCTAATCAGCTCACCAACATACTCAGGGATGTTGGAGAAGATGCCAGA   
281 ALGIANQLTNILRDVGEDAR   
901 AGAGGAAGAGTTTATCTACCACAAGATGAGTTGGCGCGAGCGGGGCTTTCAGATGAAGAC   
301 RGRVYLPQDELARAGLSDED   
961 ATATTTGCTGGAAAGGTGACGGACAAATGGAAACGTTTCATGAAGAGTCAAATTAAGAGG   
321 IFAGKVTDKWKRF MKSQIKR   
1021 GCAAAGATGTTCTTTGACAAGGCAGAGAATGGTGTGACCGAGCTGAATGCAGCTAGTAGA   
341 AKMFFDKAENGVTELNAASR   
1081 TGGCCGGTATGGGCATCCTTGCTGCTGTATCGCCAAATATTAGATGAGATTGAAGCCAAT   
361 WPνWASLLLYRQILDEIEAN   
1141 GATTACAACAATTTTACAAAGAGAGCATATGTGAATAAAGCCAAGAAGATAGCTGCTTTG   
381 DYN N AAL   
1201 CCGATTGCGTATACAAGGTCACTCGTACGTCCGTCCAAAAAACTTCTTCCAAGCAAGGTA   
401 P- SKI   
1261 TAA   
421 \*

# 2.2DIPSY蛋白的保守结构域分析

采用 NCBICD search 分析DIPSY蛋白序列保守结构域，结果如图3所示。DIPSY 基因编码八氢番茄红素合成酶，具有 Isoprenoid Biosyn C1 超家族结构。

75 150 225 300 375 420 Query seq. substrate binding Pocket AA W AAAAA A substrate-Hg2+ binding site 地 active site lid residues/ M catalytic residues 1 A4A4 M aspartate-rich region 1 aspartate-richregion 2 Specific hits PLN02632 Superfanilies Isoprenoid_Biosyn_C1 superfamily

![](images/85f8a292c4e2b69d2d9731ea7265642a46b658da305e21963f5bf26acef5c8a7.jpg)  
Fig.2 DiPSY nucleic acid sequence and amino acid sequence   
图3DIPSY 蛋白保守结构域分析  
Fig.3Analysis of conserved domain of DIPSY   
图4SignalP4.1预测DIPSY蛋白的信号肽 Fig.4Prediction of signal peptide of DlPSY protein by SignalP 4.1

2.3DIPSY蛋白的信号肽、跨膜结构域、亚细胞定位及亲疏水性分析

运用 SignalP4.1 Server 对DIPSY 蛋白进行信号肽预测，结果如图4所示。DIPSY 的最大剪切位点值(C-score)为0.413。最大综合剪切位点值(Y-score)为0.439，两个位点都在第 21位氨基酸。最大信号肽值(S-score)在第13 位氨基酸，为0.647，大于阈值0.5，预测 DIPSY蛋白含有信号肽，为分泌性蛋白。

采用TMHMMServer v.2.0 对DIPSY 蛋白跨膜结构进行分析(图5)，结果表明 DIPSY不含有跨膜螺旋(TMHs)，无跨膜区；非跨膜螺旋区(ExpAA)概率为 0.23591，预测该蛋白为非跨膜蛋白；该蛋白质的N末端位于膜内侧的概率为0.17234，总体位于膜外，整条肽链的跨膜结构预测值小于1，推测其不存在跨膜结构域。应用PSORT对DIPSY细胞内定位进行预测，结果如表1所示，预测DIPSY蛋白可能存在于膜外。

![](images/b809ff9b590f687c483a036d03008066cc0792f20889dc6fb5c0d49021f7636c.jpg)  
图5TMHMM对DIPSY蛋白的跨膜性分析Fig.5Transmembrane analysis of DlPSY protein by TMHMM表1PSORT对DIPSY 蛋白的亚细胞定位分析

Table 1Analysis of subcellular location of DlPSY protein by PSORT

<html><body><table><tr><td>定位</td><td>分值 Score</td></tr><tr><td>膜外</td><td>0.370</td></tr><tr><td>Outside</td><td></td></tr><tr><td>Nucleus</td><td>0.180</td></tr><tr><td>溶酶体</td><td>0.190</td></tr><tr><td>Lysosome 内质网（膜）</td><td></td></tr><tr><td>Endoplasmic reticulum (membrane)</td><td>0.100</td></tr></table></body></html>

通过ExPASYProtScale预测DIPSY 氨基酸序列的亲疏水性(图6)，预测结果的正分值越大，疏水性越强，负分值越小，其亲水性越强。分析结果表明，DIPSY最大正分值(2.678)位于肽链中的第6位氨基酸，最小负分值(-3.022)位于第57位氨基酸，整条肽链的亲水性氨基酸数量大于疏水性氨基酸数量，推测DIPSY为可溶性亲水蛋白。

![](images/4c299520cc7326e3eb66a757154749df653dbfecc6f11365ccfc9c06f2578025.jpg)  
图6ProtScale预测DIPSY蛋白的亲疏水性

# 2.4DIPSY蛋白的二级结构分析

采用 SOPMA对DIPSY蛋白二级结构进行预测，结果如图7所示，DIPSY蛋白中有235个氨基酸残基呈现 $\mathbf { \alpha } _ { \mathbf { a } \cdot \mathbf { \alpha } }$ -螺旋结构，占肽链氨基酸总数的 $5 5 . 9 5 \%$ ；49 个氨基酸残基呈延伸链结构，占肽链氨基酸总数的 $1 1 . 6 7 \%$ ；17个氨基酸残基呈 $\beta$ -转角结构，占肽链氨基酸总数的$4 . 0 5 \%$ ；119个氨基酸残基呈无规则卷曲结构，占肽链氨基酸总数的 $28 . 3 3 \%$ 。DIPSY蛋白的主要结构为 $\mathfrak { a }$ -螺旋和无规则卷曲，该结构有助于蛋白质的稳定性。

注：蓝色代表α-螺旋；绿色代表β-折叠；红色代表无规则卷曲；紫色代表延伸链。

![](images/e9b9b88d2294de62338db67c4f352660db29b2cf40d49b63a95c5e6534c2e505.jpg)  
Fig.6Prediction of hydrophilicity and hydrophobicity of DlPSY protein by ProtScale   
图7DIPSY 蛋白的二级结构分析  
Fig.7Analysis of secondary structure of DlPSY protein

Note: Blue indicates $\mathfrak { a }$ -helix; green indicates ${ \beta }$ -fold; red indicates irregular curl; purple indicates extended chain.

# 2.5DIPSY蛋白的卷曲螺旋域分析

应用 ExPASy COILS对DIPSY 蛋白进行卷曲螺旋域预测(图8)，加权与未加权的预测结果一致，推测 DIPSY 蛋白含卷曲螺旋域。

![](images/9d55dfcb432a377afb7eaca80511640459181023ea7f7855e4e1af1fc92a3bfe.jpg)  
图8COILS对DIPSY 蛋白的卷曲螺旋分析 Fig.8Coiled helix analysis of DlPSY by COILS   
图9SWISS-MODEL对DIPSY蛋白三级结构的预测 Fig.9Prediction of protein tertiary structure of DlPSY by SWISS-MODEL

2.6DIPSY蛋白三级结构建模及结合位点预测

利用 SWISS-MODEL 对DIPSY 进行蛋白质三级结构建模(PyMOL视图)(图9)，并利用MolProbity Ramachandran 评估 DIPSY 的三级结构模型(图10)。结果显示，DIPSY 蛋白 $9 5 \%$ 氨基酸位点位于最佳区域内， $100 \%$ 氨基酸位点位于允许区域范围，表明DIPSY蛋白质三级结构模型准确可靠。利用 3DLigand-Site 预测DIPSY蛋白质配体结合位点为344Phe 和347Lys（图11）。

m

![](images/851f37272da5820f36c1bcd8b341746f81286c3b30261ac45a5aff1275e7fe2d.jpg)  
图10MolProbity Ramachandran 分析DlPSY 蛋白三级结构.g.10Tertiary structure analysis of DlPSY protein by MolProbity Ramachandrar

![](images/041629eb35f0dbf383a537106493aa27ef7812d2370fa19c3f8b876b3e1aecb0.jpg)  
图113DLigandSite 对DIPSY 蛋白配体结合位点预测 Fig.11Prediction of ligand binding sites of DlPSY by 3DligandSite

2.7PSY序列比对及系统进化树的构建

应用Bioedit对黄水仙（X78814）、胡椒（X68017）、番茄（KC767847.1）、拟南芥（L25812）、水稻（AY452768）、柑橘(AF152892)、柿子（FJ594485.1）、柚子（KP462726.1）、向日葵（CAC27383.1）、草莓（ACR61392.1）、甜瓜（AEH03199.1）、枸杞（AAW88383.1）、广藿香（AHJ90431.1）、芒果（JQ277716.1）、温州蜜柑（AF220218.1）、苦瓜（AAR86104.1）和南瓜（AEK86564.1）的PSY蛋白进行序列比对（图12），采用MEGA10进行系统进化树的构建（图13），探索PSY蛋白在不同物种之间的进化关系。结果表明，DIPSY与柑橘、温州蜜柑、柚子、芒果的PSY同源性较高，推测它们来自同一个祖先，与甜瓜PSY的同源性较低，亲缘关系较远。

250 260 270 280 290 Dimocarpuslongan 211 VAKYHVDIQPFRDMIEGMRMDLRKSRYKNFDEL Narcissuspseudonarcisus212 SRFPVDIQPFDMVEGMRMDLKKSRYKNFDEL GLMSVP Pipernigrum 216 SKFPVDIQPFRDMIEGMRMDLRKSRYRNFDEL LMSVP Lycopersiconesculentum 204 SNFPVDIQPFRDMIEGMRMDLRKSRYKNFDEL VP Arabidopsisthaliana 216 ARY DIQPFRDMIEGMRMDLKKSRYQNFDEL Oryza sativa 63 SKFP DIQPFKDMIEGMRLDLWKSRYRSFDELYL Citrusreticulata 228 TKFP DIQPFRDMIEGMRMDLRKSRYKNFDELY Diospyroskaki 227 KF DIQPFKDMIEGMRMDLKKSRYMNFDELY Citrusmaxima 230 TKFPVDIQPFRDMIEGMRMDLRKSRYKNFDEL Helianthusannuus 206 SKFPVDIQPFKDMIDGMRMDLRKSRYENFDEI Fragaria xananassa 188 TKYPVDIQPFKDMVEGMRLDLRKSRYONFDEI Cucumismelo 180 VSKFPIDMKPFRDMIEGMRMDTKKCRYENFEEL Lycium barbarum 221 ITKYPVDI QPFRDMIEGMRMDLKKSRYKNFDEL Pogostemonpatchouli 228 VAQFPVDIQPFRDMIEGMRMDLWKSRYKTFDEL Mangiferaindica 221 AKFPVDIQPFRDMIEGMRMDLKSRYKNFDEL Citrusunshiu 228 KFPVDIQPFRDMIEGMRMDLRKSRYKNFDEI Momordicacharantia 211 KFPVEIQPFKDMIEGMRTDLRKSRYKNFDE Cucurbita moschata 220 KFPVDIQPFDMIEGMRTDLRKSRYKNFDELYLYCY TVGLM ClustalConsensus 48 ：： ：： 330 340 350 360 370 Dimocarpuslongan 291 LRDVGEDARRGRVYLPQDELARAGLSDEDIFAGKVTDKWKRFMKSQIKRA Narcissuspseudonarcissus292 ILRDVGEDARRGRYLPQDELAEAGLSDEDFGKVTDKWRSFMKRQIKRA Pipernigrum 296 ILRDVGEDARRGRV LPQDELAQ DEDIFAGRVTDKWRIFMKKQIQRA Lycopersiconesculentum 284 LRDVGEDARRGRV LPODELA GLSDEDIFAGRVTDKWRIFMKKQIHRA Arabidopsisthaliana 296 LRDVGED ARRGRV P DE LSDEDIFAGKVTDKWRNFMKMQLKRA Oryza sativa 143 LRDVGEDSRRGRYLPLDEL AEAGLTEEDIFRGKVTDKWRKFMKGQILRA Citrusreticulata 308 LRDVGEDAPRGRVYL QDE AGLSDDDIFAGEVTKWRNFMKNQIKRA Diospyroskaki 307 LRDVGEDARRGRVYLPQDEL AQAGLSDEDIFAGKVTDKWRSFMKNQINRA Citrusmaxima 310 LRDVGEDAORGRVYLPQDELAQAGLSDDDIFAGEVTKWRNFMKNQIKRA Helianthusannuus 286 ILRDVGEDARRGRVYLPQDELAQAGLSDEDIFAKVTDKWREFMKKQIHRA Fragariaxananassa 268 ILRDVGEDARRGRIYLPQDELAQAGLSDDDIFRGKVTDKWOSFMKGQIKRA Cucumismelo 260 ILRDVGEDATRGRVYLPQDELAQEGLCDADILRMRVSDKWREFMKEQIKRA Lyciumbarbarum 301 ILRDVGEDARRGRVYLPQDELAQAGLSDEDIFAGKVTDKWRIFMKKQIKRA Pogostemonpatchouli 308 ILRDVGEDARRGRVYLPQDELAQAGLSDEDIFAGKVTDKWRIFMKKQIKRA Mangiferaindica 301 LRDVGEDARRGRIYLPQDELAQAGLSDEDIFAGKVSAKWRNFMKNQIERA Citrusunshiu 308 LRDVGEDARRGRV LPQDELAQAGLSDDDIFAGEVTIKWRNFMKNQIKRA Momordicacharantia 291 LRDVGEDARRGR LPQDELAQAGISEEDIFGGRVTDKWRNFMKNQIKRA Cucurbitamoschata 300 RDVGEDARRGR PQDELAQAGLSDEDIFAGRVTDKWRNFMKNQIKRA Clustal Consensus 108

注：红框区域为IsoprenoidBiosynC1高度保守区。

Note: Red frame region is a highly conserved region of Isoprenoid Biosyn C1.

![](images/c58bf23ce7165a291c837262a1b32aa81682a5f6095184a18e42e1c3dd56840c.jpg)  
Fig.13Phylogenetic tree of PSYs

注：黄水仙（X78814）；胡椒（X68017）；番茄（KC767847.1）；拟南芥（L25812）；水稻（AY452768);   
柑橘(AF152892)；柿子（FJ594485.1）；柚子（KP462726.1）；向日葵（CAC27383.1）；草莓（ACR61392.1)；   
甜瓜（AEH03199.1）；枸杞（AAW88383.1）；广藿香（AHJ90431.1）；芒果（JQ277716.1）；温州蜜柑   
（AF220218.1）；苦瓜（AAR86104.1）；南瓜（AEK86564.1）。   
Note: Narcissus pseudonarcissus(X78814); Piper nigrum(X68017); Lycopersicon esculentum(KC767847   
.1); Arabidopsis thaliana(L25812); Oryza sativa(AY452768); Citrus reticulata(AF152892); Diospyr   
os kaki(FJ594485.1); Citrus maxima(KP462726.1); Helianthus annuus(CAC27383.1); Fragaria   
xananassa(ACR61392.1); Cucumis melo(AEH03199.1); Lycium barbarum(AAW88383.1); Pogoste   
mon patchouli(AHJ90431.1); Mangifera indica(JQ277716.1); Citrus unshiu(AF220218.1); Momord   
icacharantia(AAR86104.1);Cucurbita moschata(AEK86564.1).   
图13PSY蛋白质的系统进化树构建结果

# 2.8DIPSY蛋白互作关系

应用 STRING 交互式数据库构建候选蛋白与相关蛋白的相互作用网络，分析预测与DIPSY相互作用的蛋白。选择拟南芥为模式植物，构建出的蛋白互作结果如图14所示,DIPSY与ZDS（ζ-胡萝卜素脱氢酶）、LUT2（番茄红素ε环化酶）、Z-ISO（-胡萝卜素异构酶）、LYC（番茄红素β环化酶）、ABA1（玉米黄质环氧酶）、CRTISO（番茄红素异构酶）、PDS3（15-顺式八氢番茄红素去饱和酶）、GGPS1（牛儿基牛儿基焦磷酸合酶大亚基1）、DXR（1-脱氧-D-木糖 5-磷酸还原异构酶）和CLA1（1-脱氧-D-木酮糖-5-磷酸合成酶）具有

相互作用。

![](images/0a1a43654534332b80f44d6cf5c2a6e76f69c22bf9c668f73f7e0033f1c80f2f.jpg)  
图14PSY 蛋白互作关系Fig.14Interaction of PSYs

# 2.9DIPSY基因在龙眼根和叶中的差异表达分析

采用实时荧光定量PCR技术(qRT-PCR)分析从龙眼转录组数据中筛选获得的DIPSY基因在根和叶中的相对表达量，结果如图15所示，DIPSY基因在龙眼根和叶中均有表达，叶中的表达量高于其在根中的表达量。

![](images/2763ab70fcf8fe5f634519d849cd0202fcf5c1ef765d4f31234a3ddbda07e534.jpg)  
图15DIPSY基因在龙眼根与叶中的表达量分析Fig.15Expression analysis of DlPSY in root and leaf tissues

# 3结论与讨论

类胡萝卜素是植物中的一类重要的次生代谢产物，属于亲脂性类异戊二烯化合物（Walter&Strack，2011），其合成途径在很多植物中给予了详细的介绍。PSY基因是类胡萝卜素合成途径中的首个合成酶基因，起到限速的作用，影响类胡萝卜素在植物组织中的积累（Zhang＆Dubcovsky，2011）。在本研究中，我们根据龙眼转录组数据筛选获得一个DIPSY基因，编码420个氨基酸。生物信息学分析表明，该蛋白为碱性不稳定蛋白，不存在跨膜区，具有可溶和亲水的特性，存在于膜外，二级结构主要为 ${ \bf { \alpha } } { \bf { \alpha } } ^ { - }$ 螺旋和无规则卷曲，该分析结果与桃、枇杷、芒果等PSY蛋白一致（梁敏华等，2018；洪敏等，2018；黄建峰等，2017），推测不同植物种属间PSY蛋白的亲疏水性、蛋白质二级结构等具有一定的保守性。甘薯、芥蓝等PSY蛋白主要位于叶绿体中，直接在细胞器中发挥作用，而龙眼和芒果中的PSY 主要位于膜外，推测其在细胞质中合成前体蛋白后，没有进入其它亚细胞器中，而是经过加工成为成熟的蛋白质后发挥作用（薛生玲等，2017；程洁等，2017）。蛋白质折叠时能够形成亲水表面和疏水内核，并且在跨膜结构中存在高疏水区域（李卿等，2015），本文对PSY蛋白亲疏水性分析结果表明其不存在高疏水区域，由此推断龙眼PSY蛋白为非跨膜亲水蛋白。

qRT-PCR 结果表明 DIPSY基因在根和叶中均有表达，其叶中的表达量高于根。在已研究植物中，PSY基因在不同植物中的各组织表达量存在差异，沟叶结缕草ZmPSY基因在叶中的表达量较高，草莓FaPSY基因在花中的表达量较高，而西瓜CIPSY基因在果实中的表达量较高（董笛等，2017；吕品等，2014；朱海生等，2011）。相关研究表明PSY基因的表达量与类胡萝卜素在组织中的积累呈正相关，在油菜、马铃薯和番茄中转入与类胡萝卜素合成相关的PSY基因后其类胡萝卜素含量也随之提高（罗秀芹等，2018；王玉萍等，2006)，因此我们推测龙眼叶片中的类胡萝卜素的含量较根中高。

综上所述，本文从龙眼转录组数据库中筛选获得一个PSY基因，采用生物信息学的方法对其理化性质、亚细胞定位、亲疏水性和高级结构等进行研究，同时采用qRT-PCR 技术分析DIPSY基因在龙眼根与叶中的差异表达，实验结果为后期即将开展的通过转基因方法提高类胡萝卜素的含量提供了科学依据。

# 参考文献：

CAMPBELL RJ, CAMPBELL CW, 2001.Longan evaluation and selection in Florida, USA[J]. Acta Hortic, (558): 125-127.   
CHAIKHAM P, PRANGTHIP P, 2015. Alteration of antioxidative properties of longan flower-honey after high pressure, ultra-sonic and thermal processing[J]. Food Biosci, 10:1-7.   
CHEN XH， TAN HX， ZHANG L，2018. Research progress on biosynthetic pathway of apo-carotenoids in Crocus sativus[J]. Chin Trad Nerb Drugs, 49(19): 4702-4709.[陈祥慧，谭 何新，张磊,2018．西红花中类胡萝卜素生物合成途径研究进展[J]．中草药,49(19): 4702-4709.]   
CHENG J, ZHAO TF,LIAO ZH, et al., 2017. Cloning and functional verification of sweet potato phytoene synthase gene[J].Plant Physiol J,53(5): 865-872.[程洁，赵腾飞，廖志华，等,2017. 甘薯八氢番茄红素合成酶基因的克隆与功能验证[J]．植物生理学报,53(5):865-872.]   
DONG D, TENG K， YU AD, et al.， 2017. Cloning， subcellular localization and expression analysis of a novel phytoene synthase gene, ZmPSY, in zoysia matrella[J]. Acta Pratacul Sin, 26(11):69-76.[董笛，滕珂，于安东，等,2017．沟叶结缕草八氢番茄红素基因 ZmPSY 的克 隆、亚细胞定位及表达分析[J]．草业学报,26(11):69-76.] FRAY RG, WALLACE A, FRASER PD, et al., 1995. Constitutive expresson of a fruit phytoene synthase gene in transgenic tomatoes causes dwarfism by redirecting metabolites from the gibberelin pathway[J]. Plant J, 8(5): 693-701. GRUSZECKI WI, STRZALKA K, 2005. Carotenoids as modulators of lipid membrane physical properties[J]. Biochim Biophys Acta,1740(2):108-115. HONG M, CHI ZH, SHI S,et al.,2018. Analysis of cloning and expression of phytoene synthase in Eriobotrya japonica lindl[J]. Genom Appl Biol，37(10): 4407-4413.[洪敏，池卓恒，石丝, 等,2018．枇杷八氢番茄红素合成酶基因的克隆及表达分析[J]．基因组学与应用生物学,   
37(10): 4407-4413.] HUANG CY, LIANG J, HUANG TX, et al., 2019. $\mathfrak { a }$ -glucosidase inhibitory activity of extracts from the leaf of Dimocarpus longan Lour[J].Asia-Pacific Trad Med,15(1): 7-9.[黄春燕，梁洁, 黄团心，等,2019．龙眼叶提取物对 $\mathfrak { a }$ -葡萄糖苷酶抑制活性研究[J].亚太传统医药,15(1):   
7-9.] HUANG JF, QIN YL,GAO AP, et al.， 2017. Structural analysis and functional prediction of phytoene synthase gene PSY in mango[J]. SW Chin JAgric Sci, 30(3): 517-523.[黄建峰，秦于 玲，高爱平，等,2017．芒果八氢番茄红素合成酶基因 PSY 的结构分析及功能预测[J]．西 南农业学报,30(3): 517-523.] HUO P, JI J, WANG G, et al.,2011. Plant carotenoid biosynthesis and function[J]. Chin iotechnol,   
31(11):107-113.[霍培,季静,王罡,等,2011．植物类胡萝卜素生物合成及功能[J]．中国生 物工程杂志,31(11):107-113.] JIANG J, MENG FY, HE Z, et al., 2014. Sulfated modification of longan polysaccharide and its immunomodulatory and antitumor activity in vitro[J]. Int JBiol Macromol, 67: 323-329. JIANG Y, ZHANG Z, JOYCE DC, et al.,2002. Postharvest biology and handling of longan fruit (Dimocarpus longan Lour.)[J]. Postharvest Biol Technol, 26(3): 241-252. LI L,XU J,MU Y, et al.， 2015. Chemical characterization and anti-hyperglycaemic effects of polyphenol enriched longan (Dimocarpus longan Lour.) pericarp extracts[J]. JFunct Foods, 13:   
314-322. LI Q,DI P, LU WQ,et al.，2015.Bioinformatics analysis of danshen kebaki pyrophosphate synthase[J].Chin Trad Nerbal Drugs,46（6）:887-894.[李卿，邸鹏，陆文钰，等,2015．丹参 柯巴基焦磷酸合酶的生物信息学分析[J].中草药,46（6）:887-894.] LI ZH, MATTHEWS PD, BURR B, et al.，1996. Cloning and characterization of a maize cDNA encoding phytoene desaturase,an enzyme of the carotenoid biosynthetic pathway[J]. Plant Mol Biol, 30(2): 269-279. LIANG MH, YANG ZF, SU XG, et al., 2018. Cloning and expression analysis of phytoene synthase gene from peach fruit[J].Acta Agric Zhejiangen, 30(3): 399-405.[梁敏华，杨震峰, 苏新国，等,2018．桃果实八氢番茄红素合成酶基因的克隆与表达分析[J]．浙江农业学报,   
30(3): 399-405.] LUO XQ, YANG L, XIAO XH, et al., 2018. Analysis of carotenoids accumulation and main genes expression profile in cassava storage root[J]. J Fujian Agric For Univ (Nat Sci Ed),47(2):   
138-143.[罗秀芹，杨龙，肖鑫辉,等,2018．木薯块根类胡萝卜素积累与主要基因表达谱 分析[J]．福建农林大学学报：自然科学版,47(2):138-143.] LV P,LI N,LIU H, et al., 2014. Cloning and expression analysis of full length lycopene synthase gene from watermelon[J].J Zhengzhou Univ (Nat Sci Ed) 46(2):104-108.[吕品，李娜，刘慧, 等,2014．西瓜八氢番茄红素合成酶基因全长的克隆与表达分析[J]．郑州大学学报(理学 版),46(2): 104-108.]   
NISAR N,LI L,LU S,et al.,2015. Carotenoid metabolism in plants[J]. Mol Plant, 8(1): 68-82.   
PRASAD KN, YANG B, SHI J, et al., 2010. Enhanced antioxidant and antityrosinase activities of longan fruit pericarp by ultra-high-pressure-assisted extraction[J]. J Pharmaceut Biomed Anal, 51(2): 471-477.   
RANGKADILOK N， SITTHIMONCHAI S， WORASUTTAYANGKUM L， et al.， 2007. Evaluation of free radical scavenging and antityrosinase activities of standardized longan fruit extract[J]. Food And Chem Toxicol, 45(2): 328-336.   
ROBERT B, HORTON P, PASCAL AA, et al., 2004. Insights into the molecular dynamics of plant light-harvesting proteins in vivo[J]. Trends Plant Sci, 9(8): 385-390.   
SANAE K, CHIHIRO OY, AKEMI O., 2018. Regulation of carotenoid pigmentation in corollas of petunia[J]. Pl Mol Biol Rep,36(4): 632-642.   
SCHMITTGEN TD,LIVAK KJ, 2008. Analyzing real-time PCR data by the comparative CT method[J]. Nat Protoc, 3(6): 1101-1108.   
SHEWMAKER CK, SHEEHY JA, DALEY M, et al.， 1999. Seed-specific overexpression of phytoene synthase: increase in carotenoids and other metabolic effects[J]. Plant J,20(4): 401-412.   
SUZUKI S,NISHIHARA M,NAKATSUKA T, et al.， 2007. Flower color alteration in lotus japonicusby modification of the carotenoid biosynthetic pathway[J]. Plant Cell Rep,26(7): 951-959.   
THITIRATSAKU B,ANPRUNG P,2014. Prebiotic activity score and bioactive compounds in longan (Dimocarpus longan Lour.): influence of pectinase in enzyme-assisted extraction[J]. Food Sci Technol, 51(9): 1947-1955.   
TIAN H, FANG L, ZHANG QA, et al., 2018. Transcriptome analysis of carotenoid biosynthesis in the Brassica campestris L. subsp. chinensis var. rosularis Tsen[J]. Sci Hort-amsterdam, 235: 116-123.   
WALTER MH, STRACK D，2011. Carotenoids and their cleavage products:biosynthesis and functions[J]. Nat Prod Rep,28(4): 663-692.   
WANG QW,20o0. The research advances of carotenoid and its clinic application[J]. Chin Pharmac Affairs,14(1):58-60.[王庆伟,2000.类胡萝卜素的研究进展与临床应用[J]．中国 药事,14(1): 58-60.]   
WANG YP, LIU QC， ZHAI H, 2006. Expression and regulation of genes related to plant carotenoid biosynthesis and their application in plant gene engineering[J]. Mol Plant Breed, 4(1):103-110.[王玉萍，刘庆昌，翟红,2006．植物类胡萝卜素生物合成相关基因的表达调 控及其在植物基因工程中的应用[J].分子植物育种,4(1):103-110.]   
XUE SL, ZHANG F, JIANG M, et al.，2017. Cloning and prokaryotic expression of phytoene synthase gene in Brassica alboglabra[J]. Genom Appl Biol, 36(2): 734-739.[薛生玲，张芬，江 敏，等,2017．芥蓝八氢番茄红素合成酶基因 BaPSY1 的克隆及原核表达[J].基因组学与应 用生物学,36(2): 734-739.]   
ZHANG W, DUBCOVSKY J, 2011. Erratum to: Association between allelic variation at the phytoene synthase gene and yellow pigment content in the wheat grain[J]. Theor Appl Genet, 123(1): 193.   
ZHU HS,LI YP, WEN QF, 2011. Cloning and expression analysis of phytoene synthase gene in Fragaria ananassa duch[J]. Sci Agric Sin,44(2): 349-357.[朱海生，李永平，温庆放,2011.

草莓八氢番茄红素合成酶基因的克隆及其表达特性[J].中国农业科学,44(2):349-357.]