# 基于高通量测序的都匀地区福鼎大白种茶树根茎叶分析

王芬\*，裴会敏，文狄，陈志，刘荣，姚玉仙，马媛（黔南民族师范学院生物科学与农学院贵州都匀558000）

摘要：茶树富含儿茶素、茶氨酸和咖啡碱等多种具有广泛保健功能的植物代谢产物，为探究茶树中茶多酚等产物代谢途径的相关基因，本研究以贵州都匀地区福鼎大白种茶树的根、茎、叶为研究对象，利用高通量测序技术构建茶的转录组数据库并筛选其根、茎、叶差异表达基因。共获得70.88 GbCleanData，各样品CleanData均达到 $6 . 3 3 \ : \mathrm { G b }$ ，Q30 碱基百分比在 $9 3 . 2 2 \%$ 以上。将CleanReads与中国种茶树参考基因组进行序列比对，比对效率从 $8 7 . 8 3 \%$ 到 $9 1 . 1 4 \%$ 。基于比对结果，进行可变剪接预测分析和基因结构优化分析，发掘新基因13 531个，其中10244个得到功能注释。利用 FPKM进行基因表达量分析，根据基因在不同样品中表达量识别差异表达基因。叶与茎的差异基因有5595个，其中2769个在茎中上调，2826下调，叶和根有9650个差异基因，5056个上调，4594个下调，茎和根中有5644个差异基因，2938个上调，2706个下调，并通过GO和KEGG分析，将差异基因进行功能注释和富集分析。研究结果为揭示都匀地区福鼎大白种茶参与类黄酮、茶氨酸和咖啡碱等代谢途径相关的基因提供参考，为选育优良品种等提供理论依据。

关键词：都匀地区，福鼎大白种，根茎叶，高通量测序，差异基因中图分类号：Q945 文献标识码：A

# High-throughput sequencing analysis of root, stem and leaf in Fudingdabai

基金项目：国家自然科学基金（31900486)；贵州省科技厅基础研究计划项目（黔科合基础[2019]1298)；贵州省教育厅青年科技人才成长项目（黔教合 KY 字[2018]420)；黔南民族师范学院科研创新团队项目（Qnsyk201605,QNYSKYTD2018011)；黔南民族师范学院高层次人才引进研究专项项目（qnsyrc201611)；黔南州科技计划项目（黔南科合学科建设农学（2018）5号和黔南科合农字（2017）23）；贵州省教育厅（黔教合人才团队字[2015]68）；黔南民族师范学院重大科研创新基金博士专项基金（QNSY2018BS018)；贵州省植物学重点支持学科开放基金（qnsyzw1809）；黔南民族师范学院继续教育基地项目（QNSY2018ZJ006）[Supported by the National Natural ScienceFoundation of China(31900486)；Guizhou Provincial Scienceand Technology Foundation(QKH Basic research)[2019]1298);GuizhouProvincialEducation Department(QJH-KY-Z[2O18]42O);Researchand Inovation Teamof QiannanNormal University for Nationalities(Qnsyk201605,QNYSKYTD2018011); Scientific Research Project of Qiannan NormalUniversity for Nationalities(qnsyrc201611)； Qiannan Scienceand Technology Bureau(QNKHXKJSNX(2018)5and[QNKHNZ(2O17)23];Guizhou Provincial Education Department([2015]68)；Scientific Research Projectof QiannanNormal University for Nationalities(QNSY2O18BSO18);ScientificResearch Projectof Qiannan Normal University forNationalities(qnsyzw18O9)；ScientificResearchProjectofQiannanNormalUniversityforNationalities(QNSY2018ZJ006)]。作者简介：王芬（1984-），女，山西运城人，博士，讲师，主要从事茶树转录组学研究，(E-mail)

fenmin521 $@$ 163.com。\*通信作者

WANG Fen\*, PEI Huimin,WEN Di, CHEN Zhi, LIU Rong, YAO Yuxian,Ma Yuan (The DepartmentofLife Science and Agriculture,Qiannan Normal Universityfor Nationalities,Duyun 558oo,Guizhou,

China)

Abstract:Tea tree is rich incatechins,theanine,caffeine and other metobolite of health fuction.In order to study the related genes of the metabolisms of the polyphenols.We use high-throughput sequencing technology to studythe root, stem and leaf of Fudingdabai tea and find differential expression genes. The results showed that 70.88 Gb Clean Data was obtained,6.33 Gb Clean Data is in each sample and Q30 is more than $9 3 . 2 2 \%$ . We map the Clean Reads to reference genome, the blast result is from $8 7 . 8 3 \%$ to $9 1 . 1 4 \%$ . Then,alternative splicing and gene structure optimization was analyzed. There are 13 531 new genes,in which,10 244 genes were annotated. GO and KEGG functional annotation and enrichment analysis were carried out in differential expression genes，which were identified according to gene expression level in different samples. There were 5 595 DEGs between leaf and stem,2 769 genes were up-regulated and 2 826 genes were down-regulated.9 650 DEGs were found beween leaf and root, 5 056 genes were up-regulated and 4 594 genes were down-regulated.5 644 genes between stem and root, 2 938 genes were up-regulated and 2 706 genes were down-regulated. The results are expected to provide reference for recognizing genes of catechins,theanine, caeine pathways,provide the theoretical basis for breeding improved seeds.

Key words: Duyun, Fudingdabai, root-stem-leaf, high-throughput sequencing,diferential expression gene

都匀地处云贵高原苗岭山脉南侧，具有低纬度、高海拔、寡日照、多云雾的自然生态环境，适宜茶树生长，资源丰富（陈世军等，2017）。不同品种的适制性、抗逆性和生长势不同，将导致茶品质和产量的不同。90 年代以来，都匀市等地开始大量引种单产高、品质好、适应性强的福鼎大白种茶树，增加了茶树的遗传多样性。目前，关于都匀地区的茶种质资源保护和抗性研究薄弱（张丽娟等，2016），特别是在转录组层面上的研究较少，在一定程度上限制了茶产业的应用发展。而福鼎大白种茶园占全市茶园面积 $8 5 \%$ 以上，因此，开展都匀地区福鼎大白种根、茎、叶的转录组研究对茶树在品质、质量及抗逆相关的遗传改良上具有重要意义。

随着高通量测序技术的出现，由于该技术能快速全面获取研究对象在某一状态下基因转录信息，因此该技术广泛应用于生物体转录组基因表达分析，能够准确发掘重要功能基因。Shi et al.（2011）用RNA-seq 技术对龙井43 的嫩叶、成熟叶、茎、幼根、花蕾以及成熟种子进行测序，总共获得127094个基因，其中包括与茶特有香气相关的代谢产物如咖啡碱、茶氨酸、黄酮等合成相关的基因。王君雅等（2019）利用转录组技术对龙井43和中茶126进行差异基因表达分析，结果表明99个表达模式完全相反的基因参与的生物过程主要有MAPK信号通路、谷胱甘肽和苯丙烷等。利用转录组测序技术可识别编码次生代谢的调节基因和结构基因，也可用来预测未知基因的功能，是进行基因组功能研究的重要工具（Novaes etal.,2008）。本研究利用高通量测序技术，对都匀地区福鼎大白种茶树根、茎、叶中类黄酮相关代谢途径进行研究，探索根、茎、叶中差异表达基因参与的代谢途径，为探讨都匀地区福鼎大白种茶树生长发育及组织间功能差异的分子机制提供理论依据。

# 1材料与方法

1.1 材料

供试材料选用黔南州都匀地区种植的茶树-福鼎大白种。茶苗选用黔南民族师范学院茶园的扦插苗。选取9株培养条件相同长势相同的茶苗分为3组，每组3株，在第1组中取嫩根、嫩茎和嫩叶分别放入3个离心管作为第1组生物学重复的样本，分别标为根的第1个生物学重复，茎的第1个生物学重复，叶的第1个生物学重复。每个样本3个生物学重复，剩余的两组生物学重复分别在剩下的两组茶苗中取样，共9个样本，分别为叶1、叶2、叶3、茎1、茎2、茎3、根1、根2和根3。采样时在茶树上剪取发育阶段相似、部位相同、充分伸展的叶片、茎和根，样品随后迅速放入液氮罐中速冻后放入-80℃冰箱储存备用。

# 1.2转录组测序

将采集的福鼎大白种茶苗根茎叶样品放在干冰中送往北京百迈客生物科技有限公司进行二代Illumina高通量测序，对测序数据进行质量控制，并将二代得到的转录本与已测序的中国种茶树基因组通过序列比对的方法进行比较。然后进行转录组文库质量评估、SNP/InDel分析、可变剪接事件预测、差异基因分析和差异外显子分析等。

Illumina二代测序数据提交至NCBI的 SRA数据库，BioProject的编号为PRJNA562747。

# 2结果与分析

# 2.1测序数据质量分析

从茶苗上分别取福鼎大白的叶、茎和根作为实验材料进行转录组测序，碱基质量值达到Q30的占 $9 3 . 2 2 \%$ 以上，GC含量为 $4 4 . 5 6 \% { \sim } 4 5 . 8 5 \%$ （表1），结果表明转录组文库质量符合分析要求。

Table1 Output statistics among samples   

<html><body><table><tr><td>样品名称 Samples ID</td><td>高质量Reads数目 Clean reads</td><td>数据量 Clean bases</td><td>GC含量 GC content</td><td>准确率>0.999 Q30 (%)</td></tr><tr><td>叶1Leaf 1</td><td>21 828 512</td><td>6 502 479 526</td><td>45.36%</td><td>93.62%</td></tr><tr><td>叶2Leaf 2</td><td>28 450 839</td><td>8 467 453 936</td><td>45.21%</td><td>94.22%</td></tr><tr><td>叶3Leaf 3</td><td>29 057 531</td><td>8 663 984 698</td><td>45.18%</td><td>93.80%</td></tr><tr><td>茎1 Stem 1</td><td>21 212 767</td><td>6 326 706 172</td><td>44.71%</td><td>93.70%</td></tr><tr><td>茎2 Stem 2</td><td>25 760 743</td><td>7 695169 918</td><td>45.35%</td><td>93.65%</td></tr><tr><td>茎3 Stem 3</td><td>26 080 601</td><td>7745 810 876</td><td>44.56%</td><td>93.79%</td></tr><tr><td>根1Root 1</td><td>23 789 995</td><td>7 078 295 558</td><td>45.85%</td><td>93.22%</td></tr><tr><td>根2Root 2</td><td>29 354 206</td><td>8 728 835 412</td><td>45.61%</td><td>93.48%</td></tr><tr><td>根3Root3</td><td>32 496 205</td><td>9 667 694 674</td><td>45.72%</td><td>93.54%</td></tr></table></body></html>

# 2.2转录组与中国种茶树基因组比对

# 2.2.1比对效率

本研究利用 HISAT2（Kimet al.,2015）对测序数据与中国种茶树基因组（Weiet al.,2018）进行比对，利用 StringTie（Pertea et al.,2015）对比对上的reads进行组装和定量，比对到参考基因组上的Reads占CleanReads的百分比从 $8 7 . 8 3 \substack { - 9 1 . 1 4 \% }$ （表2）。

表1样品数据产出统计表  
表2转录组与基因组比对  
Table 2 Transcriptome blast to genome   

<html><body><table><tr><td>样品 Samples</td><td>Clean Reads 数 Total Reads</td><td>比对到参考 基因组上的 Reads数及在 Clean Reads 中占的百分 比</td><td>比对到参考 基因组唯一 位置的Reads 数目及在 Clean Reads 中占的百分</td><td>比对到参考基因组 多处的Reads数及在 Cleans Reads 中占的 百分比 Multiple Map Reads</td><td>比对到参考 基因组正链 的Reads数及 在 Clean Reads中占的 百分比</td><td>比对到参考 基因组负链 的Reads数及 在 Clean Reads 中占的 百分比</td></tr></table></body></html>

<html><body><table><tr><td colspan="2"></td><td rowspan="2">Mapped Reads</td><td colspan="2">比 Uniq Mapped</td><td rowspan="2">Reads Map to ‘+’</td><td rowspan="2">Reads Map to ‘</td></tr><tr><td></td><td></td><td>Reads</td><td></td></tr><tr><td rowspan="2">叶1Leaf 1</td><td>43 657 024</td><td>39 632 673</td><td>37 386 481</td><td>2 246192</td><td>19 481 885</td><td>19 587 096</td></tr><tr><td></td><td>(90.78%)</td><td>(85.64%)</td><td>(5.15%)</td><td>(44.62%)</td><td>(44.87%)</td></tr><tr><td rowspan="2">叶2Leaf 2</td><td>56 901 678</td><td>51 861 422</td><td>48 949 427</td><td>2911995</td><td>25 493 617</td><td>25 604 077</td></tr><tr><td></td><td>(90.09%)</td><td>(86.02%)</td><td>(5.12%)</td><td>(44.80%)</td><td>(45.00%)</td></tr><tr><td rowspan="2">叶3Leaf 3</td><td>58 115 062</td><td>52 353 177</td><td>49 391 581</td><td>2 961 596 (5.10%)</td><td>25 733 339</td><td>25 849 934</td></tr><tr><td></td><td>(90.09%)</td><td>(84.99%)</td><td></td><td>(44.28%)</td><td>(44.48%)</td></tr><tr><td rowspan="2">茎1 Stem1</td><td>42 425 534</td><td>38 353 796</td><td>36 275 113</td><td>2 078 683 (4.90%)</td><td>18 802 471</td><td>18 912 508</td></tr><tr><td></td><td>(90.40%)</td><td>(85.50%)</td><td></td><td>(44.32%)</td><td>(44.58%)</td></tr><tr><td rowspan="2">茎2 Stem 2</td><td>51 521 486</td><td>46 959 156</td><td>44 300 646</td><td>2 658 510 (5.16%)</td><td>22 986 304</td><td>23 138 767</td></tr><tr><td></td><td>(91.14%)</td><td>(85.98%)</td><td></td><td>(44.61%)</td><td>(44.91%)</td></tr><tr><td rowspan="2">茎3Stem3</td><td>52161 202</td><td>46 917 710</td><td>44 231 706</td><td>2 686 004 (5.15%)</td><td>22 960 018</td><td>23 121 829</td></tr><tr><td></td><td>(89.95%)</td><td>(84.80%)</td><td></td><td>(44.02%)</td><td>(44.33%)</td></tr><tr><td rowspan="2">根1Root1</td><td>47 579 990</td><td>41 789 100</td><td>38 194 971</td><td>3 594129 (7.55%)</td><td>19 697 394</td><td>20 253 048</td></tr><tr><td></td><td>(87.83%)</td><td>(80.28%)</td><td></td><td>(41.40%)</td><td>(42.57%)</td></tr><tr><td rowspan="2">根2Root 2</td><td>58 708 412</td><td>52 846 174</td><td>49 318 371</td><td>3 527 803 (6.01%)</td><td>25 605 318</td><td>25 872 980</td></tr><tr><td>64 992 410</td><td>(90.01%)</td><td>(84.01%)</td><td></td><td>(43.61%)</td><td>(44.07%)</td></tr><tr><td rowspan="2">根3Root 3</td><td></td><td>58 353 149</td><td>54 585 798</td><td>3 767 351 (5.80%)</td><td>28 312 409</td><td>28598 694</td></tr><tr><td></td><td>(89.78%)</td><td>(83.99%)</td><td></td><td>(43.56%)</td><td>(44.00%)</td></tr></table></body></html>

# 2.2.2SNP/InDel分析

利用GATK（Mckenna et al.,2010）软件对 Hisat2比对结果中的 SNP 位点和 InDel进行识别，进而分析基因表达水平和基因功能，SNP分析表明基因区SNP位点数多于基因间区，转换型 SNP多于颠换型 SNP（表3)。InDel主要存在于内含子区和基因间区（图1)。

表3 SNP位点统计表Table3 SNPloci statistics  

<html><body><table><tr><td>样品 Sample</td><td>SNP数 目 SNP Number</td><td>基因区 SNP 位点 数 Genic</td><td>基因间区 SNP位点数 Intergenic SNP</td><td>转换型 SNP Transition SNP(%)</td><td>颠换型 SNP Transversion SNP(%)</td><td>杂合型 SNP Heterozygosity(%)</td></tr><tr><td>叶1Leaf 1</td><td>540 707</td><td>SNP 428 327</td><td>112 380</td><td>66.07%</td><td>33.93%</td><td>51.38%</td></tr><tr><td>叶2Leaf 2</td><td>541 852</td><td>413 786</td><td>128 066</td><td>66.25%</td><td>33.75%</td><td>34.86%</td></tr><tr><td>叶3Leaf 3</td><td>583 002</td><td>448 343</td><td>134 659</td><td>66.33%</td><td>33.67%</td><td>45.95%</td></tr><tr><td>茎1 Stem 1</td><td>489 642</td><td>393 947</td><td>95 695</td><td>65.46%</td><td>34.54%</td><td>49.63%</td></tr><tr><td>茎2 Stem 2</td><td>504 670</td><td>394 472</td><td>110 198</td><td>65.89%</td><td>34.11%</td><td>35.85%</td></tr><tr><td>茎3 Stem 3</td><td>638 706</td><td>496 194</td><td>142 512</td><td>65.90%</td><td>34.10%</td><td>50.79%</td></tr><tr><td>根1Root1</td><td>521 166</td><td>409410</td><td>111 756</td><td>65.74%</td><td>34.26%</td><td>50.91%</td></tr><tr><td>根2Root 2</td><td>523 515</td><td>396 706</td><td>126 809</td><td>66.22%</td><td>33.78%</td><td>34.70%</td></tr><tr><td>根3Root3</td><td>582 747</td><td>447260</td><td>135 487</td><td>66.14%</td><td>33.86%</td><td>48.58%</td></tr></table></body></html>

![](images/02fa0841e8028c0aed3bdb9411d24578e84eec33a8f03a009ee95ea84f934785.jpg)  
Fig.1 InDel annotation

1.基因间；2.基因内；3.内含子；4.上游；5.下游；6.受体剪切位点；7.供体剪切位点；8.剪切位点；9.起点 缺失；10.移码；11.密码子缺失；12.密码子插入；13.密码子改变和缺失；14.密码子改变和插入；15．同义编 码区；16.非同义编码区；17．同义终止区；18.终止区；19.终止缺失；20.其他。   
1.Intergenic; 2.Intragenic; 3.Intron; 4.Upstream; 5.Downstream; 6.Splice siteacceptor;7.Splice site donor;8.Splice siteregion; 9.Startlost;10.Frame shift;11.Condondeletion;12.Condon insertion;13.Condon changeplus condon deletion;14.Condon change plus condon insertion;15.Synonymous coding;16. Non synonymous;17.Synonymous stop;   
18. Stop gained; 19. Stop lost; 20. Other.

# 图1InDel注释分类

# 2.2.3可变剪接预测

基因通过转录生成前体 mRNA，再经过不同的剪接，产生不同的成熟mRNA，翻译为不同的蛋白质。利用 Asprofil（Florea etal.,2013）软件对可变剪接类型和表达量进行分析，结果表明在9个样品中5'端和3'端外显子可变剪切最多（图2)。

# C hinaXiv合作期刊

1.可变 ${ } _ { 5 } ,$ 或3端剪切；2.单内含子滞留；3.多内含子滞留；4.多外显子跳跃；5．单外显子跳跃；6.第一个外显子可变剪切；7．最后一个外显子可变剪切；8.可变5'或3端剪切（模糊边界）；9.单内含子滞留（模糊边界）；10.多内含子滞留（模糊边界）；11.多外显子跳跃（模糊边界）；12.单外显子跳跃（模糊边界）。

![](images/6410738e90c61cefe03dd29a2c6979c9aef11ef6ce533ad2b1049512d07f72b5.jpg)  
图2可变剪接事件数量统计 Fig.2 Alternative splicing

1. Ae;2.Ir;3.Mir; 4.Mskip; 5.Skip; 6.Tss;7.Tts; 8. Xae; 9.Xir;10.Xmir;11. Xmskip;12. Xskip.

# 2.2.4基因结构优化

由于处理数据的软件不同或数据本身的局限性，该文对中国种茶树基因组的261个基因结构进行了优化并列出了部分优化的基因 (表4)。

表4优化的基因Table 4 Gene structure optimized  

<html><body><table><tr><td>基因ID Gene ID</td><td>基因座 Locus</td><td>正负 链 Strand</td><td>优化 位置 Site</td><td>原来注释的第一个或 最后一个外显子起止 坐标 Original first or</td><td>优化后第一个或最 后一个外显子起止 坐标 Optimized first or</td></tr><tr><td>TEA004484.1_gene</td><td>Scaffold1014:163897-231030</td><td>+</td><td>5'</td><td>termination region 205 536-205 536</td><td>termination region 163 897-205 536</td></tr><tr><td>TEA000973.1_gene</td><td>Scaffold1019:1350887-1371675</td><td>+</td><td>3'</td><td>1 371 277-1371 277</td><td>1 371 277-1371 675</td></tr><tr><td>TEA016708.1_gene</td><td>Scaffold1045:1434954-1455906</td><td>+</td><td>5'</td><td>1 435 240-1435 240</td><td>1 434 954-1 435 240</td></tr><tr><td>TEA004051.1_gene</td><td>Scaffold1054:303905-308542</td><td>+</td><td>3'</td><td>308 318-308 318</td><td>308 318-308 542</td></tr><tr><td>TEA000171.1_gene</td><td>Scaffold1058:112241-129629</td><td></td><td>5'</td><td>129 534-129 534</td><td>129 534-129 629</td></tr><tr><td>TEA007140.1_gene</td><td>Scaffold1067:122675-156025</td><td>1</td><td>3'</td><td>123 878-123 878</td><td>122 675-123 878</td></tr><tr><td>TEA020092.1_gene</td><td>Scaffold1093:635489-640729</td><td>+</td><td>3'</td><td>640 607-640 607</td><td>640 607-640 729</td></tr><tr><td>TEA020094.1_gene</td><td>Scaffold1093:532337-549457</td><td>1</td><td>5'</td><td>549 397-549 397</td><td>549 397-549 457</td></tr><tr><td>TEA020098.1_gene</td><td>Scaffold1093:1162317-1191258</td><td></td><td>3'</td><td>1 162 515-1 162 515</td><td>1 162 317-1 162 515</td></tr></table></body></html>

<html><body><table><tr><td>TEA001055.1_gene</td><td>Scaffold1099:848040-870252</td><td></td><td>3'</td><td>848 142-848 142</td><td>848 040-848 142</td></tr></table></body></html>

# 2.3新基因

# 2.3.1新基因功能注释

我们对利用 StringTie 拼接出来的转录本与中国种茶树基因组的注释信息进行比较，发掘出了13 531个新基因，并将它们与 Swiss-Prot,COG,Pfam,KEGG,GO 和 NR 数据库进行 BLAST，获得新基因的注释信息 (表5)。

表5新基因功能注释结果  
Table 5 Annotation of new genes   

<html><body><table><tr><td>注释数据库 Annotated databases</td><td>新基因数目 New gene number</td></tr><tr><td>COG</td><td>2 363</td></tr><tr><td>GO</td><td>6218</td></tr><tr><td>KEGG</td><td>3948</td></tr><tr><td>KOG</td><td>5 833</td></tr><tr><td>Pfam Swiss-Prot</td><td>5383</td></tr><tr><td>eggNOG</td><td>6 900 9 243</td></tr><tr><td>nr</td><td>10 107</td></tr><tr><td>All</td><td>10 244</td></tr><tr><td></td><td></td></tr></table></body></html>

# 2.3.2基因表达量

该文通过最大流量算法，采用 FPKM（Fragments Per Kilobase of transcript per Million fragmentsmapped）作为衡量基因表达量高低的标准，FPKM计算公式如下：

# 1I Mapped Fragments(Millions) $x ^ { \prime }$ Transcript Length(kb)

福鼎大白茶根茎叶三个部位的基因表达量的密度分布对比（图3）表明，能够测序到的编码蛋白的基因FPKM值跨越 $1 0 ^ { 2 }$ 到 ${ 1 0 } ^ { 4 }$ 六个数量级。

![](images/c12144d96427207f8ce52181c8ee795ac2ccefc09f86cb429570631ab324b401.jpg)  
图3FPKM密度分布对比Fig.3FPKM density

# 2.4差异表达分析

# 2.4.1差异表达筛选

利用 Deseq（Wang et al.,2010）进行样品间的差异表达分析，并且将 Fold Change≥2，FDR $< 0 . 0 1$ 作为筛选标准，该文列出了部分的差异表达基因并且统计了根茎叶两两样品间的差异基因的数目（表6，表7)。从叶和茎，叶和根，茎和根的差异表达火山图（图4）中可以看出差异基因的统计学显著性以及上调基因和下调基因，红点代表上调，绿点代表下调。此外，我们还计算了三个组织差异表达基因的聚类热图(图5)。

表6差异表达基因Table 6 Differential expression genes  

<html><body><table><tr><td>基因ID GeneID</td><td>错误发现率 FDR</td><td>表达量差异倍数对数值 log2FC</td><td>上调或下调 Regulated</td></tr><tr><td>TEA000001.1_gene</td><td>0.000944095</td><td>2.088239721</td><td>Up</td></tr><tr><td>TEA000014.1_gene</td><td>1.00E-11</td><td>-2.156608862</td><td>Down</td></tr><tr><td>TEA000018.1_gene</td><td>3.88E-39</td><td>-4.204470344</td><td>Down</td></tr><tr><td>TEA000020.1_gene</td><td>4.20E-20</td><td>-2.852144505</td><td>Down</td></tr><tr><td>TEA000025.1_gene</td><td>0.000388739</td><td>2.729470094</td><td>Up</td></tr><tr><td>TEA000028.1_gene</td><td>1.06E-10</td><td>7.71789907</td><td>Up</td></tr><tr><td>TEA000040.1_gene</td><td>3.80E-08</td><td>4.115902534</td><td>Up</td></tr><tr><td>TEA000053.1_gene</td><td>1.02E-12</td><td>-8.291825123</td><td>Down</td></tr><tr><td>TEA000057.1_gene</td><td>2.37E-12</td><td>1.911663895</td><td>Up</td></tr></table></body></html>

![](images/6734c8387b280308bc8c7af0c2a8f6030b9fe5aaff079fc72edddb5ddd956ef7.jpg)  
图4差异表达火山图Fig. 4 Volcano plot

表7差异表达基因数目Table7DEGsnumber  

<html><body><table><tr><td>差异基因集 DEG Set</td><td>差异基因数目 DEGNumber</td><td>上调基因数目 Up-regulated</td><td>下调基因数目 Down-regulated</td></tr><tr><td>叶 VS 茎 Leaf VS Stem</td><td>5 595</td><td>2 769</td><td>2 826</td></tr><tr><td>叶VS 根LeafVSRoot</td><td>9 650</td><td>5 056</td><td>4 594</td></tr><tr><td>茎VS根 Stem VS Root</td><td>5644</td><td>2938</td><td>2 706</td></tr></table></body></html>

![](images/c11b15c0d237f316976c5702d1bbb0e7a6eeb2fb6c1e5c4becad227f96242c0f.jpg)  
图5差异表达基因聚类Fig.5Heatmap of DEGs

# 2.4.2差异基因功能注释和富集分析

对差异基因进行 COG, GO,KEGG, KOG,NR,Pfam,Swiss-Prot 和 eggNOG 功能注释（表8），并且绘制了叶和茎、叶和根、茎和根差异基因的GO 功能分类图（图6)。应用超几何检验，对差异表达基因进行KEGG 通路富集分析，统计了显著性Q值最小的前 20个通路（图7)，图中每个圆圈代表一个pathway通路，圆圈大小代表通路总富集的基因数目，圆圈越大，表示基因越多。圆圈颜色代表qvalue，qvalue 越小，代表差异基因在该通路中的富集性越可靠，所以说该图越靠近右下角的的圆圈，参考价值越大。

表8注释的差异表达基因数量统计表 Table8AnnotationofDEGsindatabase   

<html><body><table><tr><td>差异基 因集 DEG Set</td><td>注释到 的所有 差异基 因数目 Total</td><td>注释到 COG的 差异基 因 COG</td><td>注释到 GO的 差异基 因 GO</td><td>注释到 KEGG 的差异 基因 KEGG</td><td>注释到 KOG的 差异基 因 KOG</td><td>注释到 NR的 差异基 因 NR</td><td>注释到 Pfam 的 差异基 因 Pfam</td><td>注释到 Swissprot 的差异基 因</td><td>注释到 eggNOG 的差异 基因 eggNOG</td></tr><tr><td>叶VS茎 Leaf VS Stem</td><td>5 444</td><td>2 476</td><td>3 019</td><td>1972</td><td>2 738</td><td>5381</td><td>4 662</td><td>Swiss-Prot 4 520</td><td>5337</td></tr><tr><td>叶VS根 Leaf VS Root</td><td>9 331</td><td>4 255</td><td>4 966</td><td>3 357</td><td>4 897</td><td>9 199</td><td>7 900</td><td>7 654</td><td>9 083</td></tr><tr><td>茎VS根 Stem VS Root</td><td>5 454</td><td>2 633</td><td>2 876</td><td>1 899</td><td>2 768</td><td>5363</td><td>4780</td><td>4 629</td><td>5298</td></tr></table></body></html>

![](images/726f4aa9341c071dcb0b0d95a25b7faeb94f769cc0410d366383dd3f839cde53.jpg)

分子功能Molocnlzr fimction

横坐标注：1.代谢过程；2.细胞过程；3．单组织过程；4.生物调节；5．应激反应；6．定位；7.细胞成分组织或 生物合成；8．发育过程；9.多细胞生物过程；10.信号；11.生殖；12.生殖过程；13.多组织过程；14.生长；15. 解毒作用；16．免疫系统过程；17.生物附着；18.生物相；19.节律性过程；20.细胞杀伤性；21.运动；22.细胞； 23.细胞组件；24.细胞器；25.细胞膜；26.细胞膜组件；27.细胞器组件；28．大分子复合物；29.胞外区；30.细 胞膜内控；31.细胞连接；32.共质体；33.超分子复合物；34.拟核；35.病毒粒子；36.病毒粒子组件；37．胞外 区组件；38.催化活性；39.结合；40.转运活性；41.结构分子活性；42.核酸结合转录因子活性；43．电子载体 活性；44.信号转导活性；45.分子功能调节因子；46.抗氧化活性；47.分子转导活性；48．营养库活性；49.转 录因子活性，蛋白结合；50.蛋白标签；51.金属伴侣活性；52．翻译调控活性。   
Abscissa note:1.Metabolc process 2.Cellar process 3.Single-organismprocess;4.Biologicalregulation;5.Response to stimulus; 6.Localization; 7.Cellularcomponent organizationorbiogenesis; 8.Developmental proces; 9.Multicelular organismal process;10.Signaling;11.Reproduction;12.Reproductive process;13.Multi-organismprocess;14.Growth; 15.Detoxification;16.Immune systemproces;17.Biological adhesion;18.Biological phase;19.Rhythmic process;20. Cellkilling;21.Locomoton;2.Cell;23.Cellpart;4.Orgaelle; 25.Membane; 26.Membranepart; 27Orgaeeart; 28.Macromolecular; 29.Extracellular region; 30.Membrane-enclosed lumen; 31.Cell junction; 32.Symplast; 33. Supramolecularcomplex;34.Nucleoid;35.Virion;36.Virionpart; 37.Extracellularregionpart;38.Catalyticactivity;39. Binding; 40.Transporteractivity; 41.Structural moleculeactivity; 42.Nucleicacid bindingtranscription factoractivity; 43. Electron carrer activity; 44.Signal transducer activity; 45.Molecular functionregulator; 46.Antioxidant activity; 47.

Ioleculartransducer activity;48.Nutrientreservoiractivity; 49.Transcription factoractivity，protein binding; 50.Protein tag; 51. Metallochaperone activity; 52. Translation regulator activity.

![](images/f4c1267b8fc7fba64ec3096925c0b017df53b9f476fec875543d9b240c927958.jpg)  
图6差异表达基因GO注释分类 Fig.6 GO functional classification   
图7差异表达基因KEGG通路富集 Fig.7KEGG pathway enrichment

纵坐标注：1.有机含硒化合物代谢；2.类胡萝卜素生物合成；3.类黄酮生物合成；4.糖尿病并发症中的年龄信号通路；5．淀粉和蔗糖代谢；6.碳代谢；7.叶酸碳池；8．半乳糖代谢；9.角质、亚氨酸和蜡的生物合成；10．单萜类生物合成；11.甘氨酸、丝氨酸和苏氨酸代谢；12.光合生物固碳作用；13.乙醛酸和二羧酸代谢；14.氮代谢；15.氰基氨基酸代谢；16.植物激素信号转导；17.叶啉和叶绿素代谢；18.苯丙素的生物合成；19.光合作用-天线蛋白；20.光合作用；21.抗坏血酸和醛酸代谢；22.硫代谢；23.双醌和其它萜烯醌生物合成；24.谷胱甘肽代谢；25．萜类骨架生物合成；26.磷酸戊糖途径；27.脂肪酸降解；28．糖酵解/糖新生；29.亚麻酸代谢；30.二萜生物合成；31．倍半萜和三萜生物合成。

Ordinate note:1.Selenocompound metabolism; 2.Carotenoid biosynthesis;3.Flavonoid biosynthesis; 4.AGE-RAGE   
signaling pathway in diabeticcomplications; 5.Starchand sucrose metabolism; 6.Carbon metabolism;7.One carbonpool   
by folate; 8.Galactose metabolism; 9.Cutin,suberineand wax biosynthesis;10.Monoterpenoid biosynthesis;.Glycine, serine and threonine metabolism;12.Carbon fixation in photosynthetic organism;13.Glyoxylateand dicarboxylate metabolism;14.Nitrogen metabolism; 15.Cyanoamino acid metabolism;16.Plant hormone signal transduction;17. Porphyrin and chlorophyllmetabolism;18.Phenylpropanoid biosynthesis;19.Photosynthesis-ntenna proteins; 20.   
Photosynthesis; 21.Ascorbateand aldarate metabolism; 22.Sulfur metabolism; 23.Biquinone and other terpenoid-quinone   
biosynthesis;24.Glutathione metabolism; 25.Terpenoid backbone biosynthesis; 26.Pentose phosphate pathway;27.Fatty   
acid degradation; 28.Glycolysis/Gluconeogenesis; 29.Alpha-Linolenicacid metabolism;30.Diterpenoid biosynthesis; 31. Sesquiterpenoid and triterpenoid biosynthesis.

# 2.5DEU分析

该文应用 DEXSeq（Anders etal.,2012）进行外显子水平的差异分析，即 DEU（differential exonusage）分析，设置FDR $< 0 . 0 1$ ，该文列出了叶和茎的部分DEU（表9）。

表9差异外显子表达分析Table 9 Differential exon expression  

<html><body><table><tr><td>基因ID Gene ID</td><td>外显子ID Exon ID</td><td>表达量差异倍数 log2(FC)</td><td>P值 P value</td><td>错误发现率 FDR</td></tr><tr><td>TEA018663.1_gene</td><td>E010</td><td>0.403936012</td><td>1.04E-07</td><td>2.12E-05</td></tr><tr><td>TEA018663.1_gene</td><td>E011</td><td>-1.732604999</td><td>6.69E-25</td><td>9.75E-22</td></tr><tr><td>TEA018662.1_gene</td><td>E001</td><td>-0.96779822</td><td>5.47E-05</td><td>0.00551022</td></tr><tr><td>TEA012997.1_gene</td><td>E007</td><td>-0.308323557</td><td>1.95E-10</td><td>6.24E-08</td></tr><tr><td>TEA021927.1_gene</td><td>E001</td><td>0.168112449</td><td>1.33E-08</td><td>3.25E-06</td></tr><tr><td>TEA016026.1_gene</td><td>E002</td><td>-1.273705747</td><td>1.32E-05</td><td>0.001577751</td></tr><tr><td>TEA031666.1_gene</td><td>E001</td><td>0.032790485</td><td>1.98E-06</td><td>0.000300559</td></tr><tr><td>TEA031666.1_gene</td><td>E002</td><td>-0.077595321</td><td>2.13E-06</td><td>0.000320651</td></tr><tr><td>TEA016705.1_gene</td><td>E001</td><td>-0.600866652</td><td>1.58E-07</td><td>3.06E-05</td></tr></table></body></html>

# 3讨论

福鼎大白种茶树是异花授粉的经济作物，基因组杂合度高，具有优良的发芽率、抗寒性和耐旱性（刘本英等，2008)。本研究对都匀地区福鼎大白种根茎叶进行了转录组测序，Q30 碱基百分比不小于 $9 3 . 2 2 \%$ ，样品与参考基因组的比对效率在 $8 7 . 8 3 \% { \sim } 9 1 . 1 4 \%$ 之间。而李明玺等（2018）对静安白茶芽和叶的转录组研究中，Q30值都为 $8 7 . 3 2 \%$ ，Liu etal.（2017）对瑞雪的转录组研究中，Q20为 $9 7 \%$ 左右，Weietal.（2018）对龙井43的转录组研究中，Q30 为 $90 \%$ 左右，因此，福鼎大白种文库构建成功且测序质量良好，可进行下一步分析。SNP位点数目从 $4 8 9 \ 6 4 2 { \sim } 6 3 8 \ 7 0 6$ ，转换类型比例从 $6 5 . 4 6 \% \sim 6 6 . 3 3 \%$ ，颠换类型从 $3 3 . 6 7 \% { \sim } 3 4 . 5 4 \%$ ，杂合型SNP位点比例从 $3 4 . 7 0 \% { \sim } 5 1 . 3 8 \%$ 。对261个基因进行了结构优化，发现了13531个新基因，其中10244个新基因被注释了，注释到COG数据库中有2363个，注释到GO的有6218个，注释到 KEGG的有3948个，注释到KOG的有5 833个，注释到Pfam的有5383个，注释到 SwissProt 的有6900个，注释到eggNOG 的有9 243个，注释到 $\mathrm { { \Omega } _ { n r } }$ 的有10107个。

福鼎大白种根茎叶中有12595个基因参与代谢过程，12507个基因参与催化活性，8176个基因参与细胞组成成分，是基因数最多的三个生物过程。陈琳波等（2015）对"紫鹃"茶树的转录组分析中，Unigene 的GO分析表明，代谢过程、细胞、细胞部分、催化活性等富集程度较高，与本研究结果相一致。三个组织中有1615个基因参与发育过程（278，405，191)，即叶和茎参与此过程的有278个差异基因，叶和根中有405个差异基因，茎和根中有191个。根茎叶有1401个基因参与运输活动（197，356，231)，288个基因参与生长过程（47，65，20），262个基因参与信号转导活动（44，70，30)，200个基因参与免疫反应过程（35，56，36)。

都匀地区茶独特的风味是由叶片中的茶氨酸、萜烯类和类黄酮的代谢产物赋予的。Wu et al.（2013）从茶树叶片的转录组研究中得出大多数基因参与编码合成黄酮类、咖啡碱和茶氨酸等次生代谢途径的重要酶。该文通过KEGG 功能显著性富集分析，发现叶和茎、叶和根、茎和根差异基因参与的部分极其显著的通路有类胡萝卜素生物合成，泛醌和其他萜烯类醌的生物合成，单萜生物合成，甘氨酸、丝氨酸和苏氨酸代谢，乙醛酸和二羧酸代谢，植物激素信号转导，叶啉和叶绿素代谢，苯丙素的生物合成，光合作用天线蛋白和光合作用，类黄酮生物合成，萜类化合物的生物合成，亚麻酸代谢等显著富集。叶和茎的差异表达基因在KEGG 通路中，有90个基因参与碳代谢( $8 . 6 5 \%$

21，69)，占所有差异基因的 $8 . 6 5 \%$ ，其中有21个差异基因在茎中表达上调，69个差异基因在叶中表达上调。79个差异基因参与植物激素信号转导（ $7 . 6 \%$ ，55，24)，75个差异基因参与苯丙素的生物合成（ $7 . 2 1 \%$ ，49，26)，70个差异基因参与淀粉和蔗糖代谢（ $6 . 7 3 \%$ ，46，24，)，64个差异基因参与氨基酸生物合成（ $6 . 1 5 \%$ ，22，42)，43个差异基因参与植物病原体互作通路（ $4 . 1 3 \%$ ，30,13)，19差异基因参与类黄酮的生物合成（ $1 . 8 3 \%$ ，13，6)，20个差异基因参与萜类化合物生物合成（ $1 . 9 2 \%$ ，4，16)，24个差异基因参与卟啉和叶绿素代谢（ $2 . 3 1 \%$ ，1，23)，44个差异基因参与光合作用（ $4 . 2 3 \%$ ，0，44)。以上研究表明都匀地区福鼎大白茶独特的香味和各种健康功能主要归因于萜类物质合成、光合作用、类黄酮的生物合成等生物过程，类黄酮主要赋予茶的苦味，二萜类化合物的水解产物具有令人愉悦的香味和特色风味。为进一步研究都匀地区福鼎大白茶生长发育和遗传育种提供了分子基础，并为揭示与类黄酮相关代谢通路有关基因提供了重要理论依据。

# 参考文献：

ANDERS S,REYES A,HUBER W, 2012. Detecting differential usage of exons from RNA-seq data[J]. Geno Res,22(10): 2008-2017.   
CHEN LB,XIA LF, ZHOU M,et al.， 2015. Mol Plant Breeding，13(10): 2250-2255.Analysis on transcriptome sequenced for tea plant[J].[陈琳波，夏丽飞，周萌，等，2015．基于RNA-Seq 技术的 “紫鹃"茶树转录组分析[J]．分子植物育种,13(10):2250-2255.]   
CHEN SJ, ZHANGMZ, YAOYX, et al., 2017. Establishment of DNA fingerprinting for tea germplasm from qiannan prefecture by SSR markers[J].J.Plant Gene Resour,18(1): 106-111[陈世军，张明泽，姚 玉仙,等，2017.基于 SSR 标记的黔南茶树种质资源 DNA 指纹图谱构建[J]．植物遗传资源学报， 18(1): 106-111.]   
FLOREA L, SONG L, SALZBERG SL, 2013. Thousands of exon skipping events differentiate among splicing patterns in sixteen human tissues[J].F1OOoRes, 2: 188.   
KIM D,LANGMEAD B,SALZBERG SL， 2015. Hisat: A fast spliced aligner with low memory requirements[J]. Nat Methods, 12(4):357-360.   
LI MX, WANG M, GAN YD, et al., 2018. Transcriptome data assembly and gene function annotation of buds and leaves of Cammelia sinensis cultivar Jing'anbaicha[J]. Mod Food Sci Technol,34(5): 93-100. [李明玺，王敏，甘玉迪，等．靖安白茶芽和叶的转录组数据组装机基因功能注释[J]．现代食品科 技,34(5): 93-100.]   
LIU BY, ZHOU J, XU M, et al., 2O08. Tissue culture of immature embryo and parentage identification of hybrids between Camelia taliensis (w.w.Smish) melchior and C. sinensis‘Fuding Dabaicha'[J].Acta Hortic Sin,35:735-740.[刘本英，周健，许枚，等,2008．云南大理茶与福鼎大白茶种间杂交幼胚 的组织培养及亲子鉴定[J]．园艺学报,35:735-740.]   
LIU F, WANG Y, DING ZT, et al.,2017. Transcriptomic analysis of flower development in tea[J]. Gene, 631: 39-51.   
MCKENNA A，HANNA M,BANKS E,et al.， 2010. The genome analysis toolkit: A mapreduce framework for analyzing next-generation dna sequencing data[J]. Geno Res,2O(9): 1297-1303.   
NOVAES E,DROST DR,FARMERIE WG, et al.，2008.High-throughput gene and SNP discovery in Eucalyptus grandis,an uncharacterized genome[J]. BMC Geno, 9:312.   
PERTEA M, PERTEA GM, ANTONESCU CM, et al., 2015. Stringtie enables improved reconstruction of a transcriptome from rna-seq reads[J]. Nat Biotechnol, 33(3): 290-295.

SHI CY, YANG H,WEI CL, et al.,，2O11. Deep sequencing of the Camellia sinensis transcriptome revealed candidate genes for major metabolic pathways of tea-specific compounds[J]. BMC Genomics, 12:131.   
WANG JY, CHEN W,LIU DD,et al.， 2O19. The transcriptome analysis of diffrent tea cultivars in response to the spring cold spells[J].JTea Sci,39(2):181-192.[王君雅，陈玮，刘丁丁，等,2019.不 同品种茶树新梢响应"倒春寒"的转录组分析[J]．茶叶科学,39(2):181-192.]   
WANG L,FENG Z,WANG X, et al.， 2010.DEGseq: An R package for identifying diferentially expressed genes from RNA-seq data[J].Bioinformatics,26:136-138.   
WEI CL, YANG H, WANG SB, et al., 2O18. Draft genome sequence of Camelia sinensis var. sinensis provides insights into the evolution of the tea genome and tea quality[J]. Proc Natl Acad Sci USA, 115(18): E4151-E4158.   
WEI K, ZHANG YZ, WU LY, et al.,2O18. Gene expression analysis of bud and leaf color in tea[J]. Plant Physiol Biochem, 107: 310-318.   
WU HL, CHEN D,LI JX,et al.， 2O13.De Novo Characterization of leaf transcriptome using 454 sequencing and development of EST-SSR marker in tea[J]. Plant Mol Biol Res, 31: 524-538.   
ZHANG LJ, LIU Q, YANG Q, 2015. Advangage and utilization of tea germplasm resources in qiannan prefecture of Guizhou Province[J].Chin Tea Proc,1:38-41[张丽娟，柳青，杨清,2016．贵州省黔南 州茶树种质资源优势及开发利用[J]．中国茶叶加工,1:38-41.]